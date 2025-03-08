> **NOTICE:** This project is undergoing active refactoring to centralize functions and improve design patterns. Some functionality may be in the process of being consolidated across files. Please refer to the code comments for the most up-to-date implementation details.

# GeminiCV – Resume and Cover Letter Creation Tool

GeminiCV is a Google Apps Script add-on that enhances Google Docs with AI-powered resume and cover letter creation and editing capabilities. Now updated to leverage **Google Gemini 2.0** (the latest version) and released under the **MIT License**, this tool is designed to help you craft professional documents tailored to your career needs.

![GitHub License](https://img.shields.io/github/license/d4551/GeminiFinancialAnalysis)
![Open Source](https://img.shields.io/badge/Open%20Source-Yes-brightgreen)
![Google Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-V8-blue)
![Gemini AI](https://img.shields.io/badge/Gemini%20AI-1.5%20Pro-orange)

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [File Structure & Functionality](#file-structure--functionality)
  - [Google Apps Script Files (.gs)](#google-apps-script-files-gs)
  - [HTML Files (.html)](#html-files-html)
  - [Configuration File](#configuration-file)
- [How GeminiCV Works](#how-geminicv-works)
- [Manual Setup & Script Copying](#manual-setup--script-copying)
- [Usage](#usage)
- [License](#license)
- [References & Additional Resources](#references--additional-resources)

---

## Overview

GeminiCV integrates AI-driven content generation with advanced document formatting and analysis. It provides an interactive, chat-based interface and guided workflows that help you:

- **Create polished resumes and cover letters**
- **Tailor documents for specific job applications**
- **Improve existing documents with AI suggestions**
- **Apply professional formatting and custom styles**

Being open source under the MIT License, you’re free to use, modify, and distribute this tool.

---

## Key Features

- **Guided Document Creation:**  
  An interactive sidebar guides you through the process of creating resumes or cover letters.

- **AI-Powered Content Generation:**  
  Utilizes the Gemini 2.0 API for generating tailored content based on user input and context.  
  **API Key Setup:** Obtain your API key from [Google AI Studio](https://aistudio.google.com/apikey).

- **Document Formatting & Styling:**  
  Applies pre-defined and custom style templates to ensure a professional look.

- **Job-Specific Tailoring:**  
  Analyzes job posting URLs or Google Doc IDs to customize documents for specific roles.

- **Real-Time Chat Assistance:**  
  Provides an interactive chat interface for guidance and on-the-fly content editing.

- **Document Analysis & Improvement:**  
  Offers AI-driven insights to enhance content and style.

- **Settings and Customization:**  
  Manage API keys, select default models, adjust style preferences, and set advanced options.

- **Versioning and History:**  
  Automatically saves document versions and tracks revisions.

---

## File Structure & Functionality

### Google Apps Script Files (.gs)

- **`Code.gs`**
  - **Entry Point & Menu:**  
    Initializes the add-on menu in Google Docs.
  - **Sidebar & Dialog Handlers:**  
    Functions to display the sidebar and dialogs (Settings, About, API Key Prompt).
  - **Document Operations:**  
    Creates new resumes, cover letters, or job-specific documents and handles formatting/analysis.
  - **Utility Functions:**  
    Manages user properties and chat history.

- **`DocumentManager.gs`**
  - **Document Formatting:**  
    Provides AI-assisted formatting and applies style templates.
  - **Document Creation:**  
    Generates and styles resume and cover letter documents.
  - **Template Management:**  
    Manages built-in and custom style templates.
  - **Content Structuring:**  
    Organizes resume content using AI.

- **`ChatManager.gs`**
  - **Chat Session Management:**  
    Starts, continues, and clears chat sessions.
  - **Context Handling:**  
    Provides document context for improved AI responses.
  - **Document Generation:**  
    Converts chat history into a structured document outline.

- **`ApiHandler.gs`**
  - **Gemini API Interaction:**  
    Implements classes to interact directly with the Gemini 2.0 API.
  - **Content Generation:**  
    Handles API calls to generate tailored resume and cover letter content.
  - **Model Management:**  
    Lists available models, validates API keys, and formats model data.
  - **User Settings Integration:**  
    Applies custom user settings in API calls.

- **`StyleManager.gs`**
  - **Style Templates:**  
    Manages resume and cover letter style templates.
  - **Template Application:**  
    Applies chosen templates to documents.
  - **Formatting Functions:**  
    Implements specific formatting actions (e.g., one-page optimization).
  - **Custom Style Creation:**  
    Enables creation and saving of custom styles.

- **`Utils.gs`**
  - **Data Extraction & Validation:**  
    Extracts job details, validates API keys, and retrieves contact information.
  - **Formatting & Conversion:**  
    Converts markdown to HTML.
  - **Utility Functions:**  
    Handles timestamped names, error logging, and unique ID generation.

### HTML Files (.html)

- **`Sidebar.html`**
  - **User Interface:**  
    Contains tabs for "Create New", "Job Application", and "Format & Style", along with an interactive chat interface.
  
- **`Settings.html`**
  - **Settings Dialog:**  
    Organized into tabs for API Key (with model selection), Custom Styles, and Advanced options.
  - **API Key Setup:**  
    Enter and validate your Gemini API key.

- **`Style.html`**
  - **CSS Styles:**  
    Defines the visual appearance and responsive design for the sidebar and dialogs.

### Configuration File

- **`appsscript.json`**
  - **Project Manifest:**  
    Contains project metadata, runtime version, dependencies, OAuth scopes, and menu configurations.

---

## How GeminiCV Works

1. **User Interaction:**  
   Access GeminiCV via a custom menu in Google Docs that opens the interactive sidebar and settings dialog.

2. **Document Creation & Editing:**  
   Follow guided steps to input details and receive AI-generated content for new or existing documents.

3. **AI Integration via Gemini 2.0:**  
   The script calls the Gemini 2.0 API to generate or improve content, which is then processed and inserted into your document.

4. **Document Formatting & Style Management:**  
   Pre-defined or custom styles are applied to ensure your document is professionally formatted.

5. **Settings & Data Storage:**  
   Manage API keys, custom styles, and advanced settings through the settings dialog. Document versions and chat histories are stored using Google Apps Script’s PropertiesService.

---

## Manual Setup & Script Copying

To set up your own instance of GeminiCV or manually copy the script from an existing Google Document:

1. **Open the Google Document:**
   - Locate the document containing the GeminiCV script.
   - Open it in Google Docs.

2. **Access the Script Editor:**
   - Navigate to **Extensions > Apps Script** in Google Docs.
   - This opens the Apps Script editor with all the attached project files.

3. **Copy or Duplicate the Project:**
   - **To Copy:**  
     Use **File > Make a copy** in the Apps Script editor to duplicate the project in your Google Drive.
   - **To Set Up Your Own:**  
     Create a new project in the Apps Script editor and manually copy the contents of each file from the source document.

4. **Configure API Keys and Settings:**
   - Open the **Settings** dialog from the add-on menu in Google Docs.
   - Enter your Gemini API key (obtainable from [Google AI Studio](https://aistudio.google.com/apikey)) and adjust other settings as needed.

5. **Deploy or Test:**
   - Deploy the add-on as a test or run it directly from the script editor to ensure functionality.

---

## Usage

1. **Installation:**
   - Install GeminiCV from the Google Workspace Marketplace or set it up manually following the instructions above.

2. **API Key Setup:**
   - Open **Resume & Cover Letter > Settings > API Key**.
   - Enter your Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey).

3. **Document Creation:**
   - Open the sidebar via **Resume & Cover Letter > Open Assistant Sidebar**.
   - Select your document type (Resume/CV or Cover Letter) and style.
   - Click **Start Guided Creation** to begin the interactive session.
   - Follow the prompts and click **Generate Full Document** once ready.

4. **Job-Specific Applications:**
   - In the **Job Application** tab, enter a job posting URL or Google Doc ID.
   - Optionally, select an existing resume document.
   - Click **Analyze & Create Application** to generate tailored documents.

5. **Document Formatting & AI Improvements:**
   - In the **Format & Style** tab, select a style template and click **Apply Style**.
   - Use the **AI Improvement Suggestion** feature for content enhancements.

6. **Settings Management:**
   - Configure API keys, default models, and style preferences via the settings dialog.

---

## License

GeminiCV is released under the **MIT License**.  
You are free to use, modify, and distribute this software as permitted by the license terms.  
For full details, see the [MIT License Full Text](https://opensource.org/licenses/MIT).

---

## References & Additional Resources

- **Google Gemini 2.0 API Documentation:**  
  Detailed information on interacting with the Gemini 2.0 API.
  [https://ai.google.dev/api](https://ai.google.dev/api)

- **Google AI Studio – API Key:**  
  [https://aistudio.google.com/apikey](https://aistudio.google.com/apikey)

- **Google Apps Script Documentation:**  
  Tutorials and reference material for developing with Google Apps Script.
