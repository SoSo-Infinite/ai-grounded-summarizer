📝 AI Grounded Summarizer

A web application built to generate concise, factual summaries using the Gemini API's Search Grounding feature. This ensures that all generated content is based on up-to-date, verifiable information from Google Search, providing users with accurate summaries accompanied by direct source citations.

✨ Key Features

Factually Grounded Summaries: Utilizes the Google Search tool within the Gemini API to root all generated text in current, real-time web data.

Source Citation: Automatically extracts and displays web links (URIs) and titles of the sources used by the model to ground the response.

Customizable Prompts: Allows users to input any topic or query they need summarized.

Clean, Responsive Interface: Built with a single HTML file using Tailwind CSS for a modern, accessible user experience.

💻 Technology Stack

Frontend: HTML5, JavaScript

Styling: Tailwind CSS (via CDN)

LLM Integration: Gemini API (gemini-2.5-flash-preview-09-2025 model)

🚀 Getting Started

Since this application is designed for a single-file environment, setup is minimal.

Prerequisites

You need access to a Google Gemini API Key. Although this application is designed to run in an environment that provides the key automatically (apiKey is left as "" in the provided code), if you run it elsewhere, you must insert your own key for the fetch request to work.

Core Implementation Logic

The application uses a standard POST request to the generateContent endpoint. The critical part of enabling factual grounding is the inclusion of the tools property in the API payload:

const payload = {
    contents: [{ parts: [{ text: userQuery }] }],
    // This tool property enables Google Search grounding
    tools: [{ "google_search": {} }],
    systemInstruction: {
        parts: [{ text: systemPrompt }]
    },
};


The application then processes the response to extract both the generated text and the groundingAttributions (citations) to display them to the user.

📁 File Structure

The entire application is contained within a single file:

Filepath

Description

index.html

Contains all HTML structure, Tailwind CSS styling, and JavaScript logic for handling input, API calls, and output rendering.

🤝 Contribution

This project is intended as a clear and functional example of API grounding. Suggestions for improving the UI/UX, refining the prompt handling, or optimizing the citation display are welcome.
