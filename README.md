# Research Assistant Application

A Spring Boot-based backend service integrated with Google's Gemini API to provide content summarization and research suggestions. Designed to work with a Chrome extension for seamless content processing.

# Features

- Content Summarization**: Generate concise summaries from provided text
- REST API: Simple endpoint for processing research requests
- Chrome Extension Integration: Frontend interface for easy content submission

# Prerequisites

- Java 17+
- Maven
- Google Gemini API key
- Chrome browser (for extension usage)

# Create application.properties in src/main/resources

gemini.api.url=https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key=
gemini.api.key=your_api_key_here

# API Documentation
Endpoint: POST /api/research/process

Chrome Extension Setup

Create a new Chrome extension with:
Content script to capture selected text
Popup interface with operation selection
API communication to your running Spring Boot service

/extension
  ├── manifest.json
  ├── popup.html
  ├── content.js
  └── background.js

  Ensure the extension makes POST requests to:
http://localhost:8080/api/research/process

# Configuration Options
Customize in application.properties:

Server port: server.port=8080

CORS settings: Modify @CrossOrigin annotation in ResearchController

Timeout settings for Gemini API calls

# Development Stack

Java 17
Spring Boot 3.x
Lombok
WebFlux
Google Gemini API
Chrome Extension API
