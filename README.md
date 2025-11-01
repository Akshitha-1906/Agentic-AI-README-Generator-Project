# 🚀 Project Introduction

This project provides a robust solution for automating data processing and transformation by leveraging the power of n8n workflows and Node.js. It seamlessly integrates with Google Sheets for data input and output, and harnesses Google's Generative AI (Gemini) to perform advanced data manipulation, summarization, and extraction tasks. The primary goal is to empower users to streamline repetitive data operations and enrich their datasets with intelligent AI capabilities.

## ✨ Features

*   🔄 **Automated Data Fetching**: Effortlessly retrieve data from Google Sheets.
*   💻 **Programmatic Data Processing**: Execute custom JavaScript logic for flexible data manipulation.
*   🧠 **AI Integration with Gemini**: Utilize Google's Gemini AI for advanced text processing, analysis, and generation.
*   📤 **Smart Data Output**: Write processed and AI-enhanced data back into Google Sheets.
*   🧩 **Flexible Workflow Design**: Easily configure and extend workflows using n8n's intuitive visual builder.
*   ⚙️ **Node.js Extensibility**: Incorporate custom Node.js scripts for complex logic or standalone processing.

## ⚙️ Workflow Overview

The heart of this project lies in its n8n workflow, which orchestrates the entire data pipeline from fetching raw data to enriching it with AI and storing the results.

*   **n8n Workflow Description:**
    *   The journey begins with a `Start` node, acting as the trigger for the automated process.
    *   A `Google Sheets` node, configured for a `Read` operation, fetches the initial dataset from a specified Google Sheet, serving as the raw data input.
    *   Following this, a `Function` node processes the incoming data. This node typically contains custom JavaScript logic to prepare the data for AI interaction, structure it appropriately, or perform preliminary transformations.
    *   The prepared data then flows into a `Google Gemini` node. Here, the data is sent along with a defined prompt to the Google Gemini AI model. The AI processes the input and returns AI-generated responses, which might include summaries, sentiment analysis, entity extraction, or content generation.
    *   Finally, another `Google Sheets` node, configured for an `Append` operation, takes the AI-processed and transformed data and writes it back into a designated Google Sheet, ensuring the results are saved and accessible.

*   **Screenshot Descriptions:**
    *   `n8n-workflow-screenshot-1.png`: This image displays the initial segment of the n8n workflow. It shows the `Start` node connected to the first `Google Sheets` node (configured for reading), which then links to the `Function` node. This visually represents the data fetching and preliminary processing steps.
    *   `n8n-workflow-screenshot-2.png`: This screenshot illustrates the latter part of the n8n workflow. It depicts the connection from the `Function` node to the `Google Gemini` node, and subsequently to the final `Google Sheets` node (configured for appending data). This highlights the AI integration and the ultimate output of the processed data.

*   **Node.js Script (`index.js`):**
    The `index.js` script, as defined in `package.json`, serves as a standalone data processing component or can be integrated into the n8n workflow (e.g., within a `Function` node or executed via an `Execute Command` node). It utilizes libraries like `csv-parser` for handling CSV data, `node-fetch` for making HTTP requests to external APIs, and `@google/generative-ai` for direct, programmatic interaction with Google's AI models. This script is responsible for core data transformations, AI prompting, and result handling outside of the n8n visual flow.

*   **Video Demonstrations:**
    *   `video.mp4`: This video likely demonstrates the setup and execution of the n8n workflow. It may show how to configure credentials for Google Sheets and Google Gemini nodes, walk through the data flow within the workflow, and provide a quick overview of input and output data in Google Sheets.
    *   `video-1.mp4`: This video probably offers a more in-depth walkthrough of the entire project, potentially covering the execution of the `index.js` script, guiding on setting up environment variables, and showcasing a comprehensive end-to-end demonstration of the data processing, AI enrichment, and final data storage.

## 🧪 Example Output

The `output.json` file contains a sample of the transformed and AI-enriched data. This demonstrates how raw input is processed and enhanced by the Gemini AI model, providing structured and insightful results.

```json
[
  {
    "record_id": "tx001",
    "original_description": "The new software update significantly improved performance and fixed several bugs. Users are very happy.",
    "ai_summary": "Software update enhances performance and fixes bugs, leading to high user satisfaction.",
    "sentiment": "positive",
    "keywords": ["software update", "performance", "bug fix", "user satisfaction"]
  },
  {
    "record_id": "tx002",
    "original_description": "Shipping was delayed by two days, which was a minor inconvenience, but the product arrived intact.",
    "ai_summary": "Minor shipping delay (2 days), but product arrived undamaged.",
    "sentiment": "neutral",
    "keywords": ["shipping delay", "product intact", "minor inconvenience"]
  },
  {
    "record_id": "tx003",
    "original_description": "Customer service was unresponsive to my query about a faulty unit. Very disappointing experience.",
    "ai_summary": "Unresponsive customer service regarding faulty unit; disappointing.",
    "sentiment": "negative",
    "keywords": ["customer service", "unresponsive", "faulty unit", "disappointing"]
  }
]
```

## 🚀 Getting Started

To get this project up and running, follow these steps:

### Installation Steps

1.  **Prerequisites:**
    *   **Node.js:** Ensure you have Node.js (LTS version recommended) and npm installed.
    *   **n8n:** Have an n8n instance ready (Desktop App, Docker, or Cloud).
    *   **Google Cloud Project:** Access to a Google Cloud Project with the Generative AI API enabled and appropriate service account/OAuth credentials configured.
    *   **Google Sheet(s):** Prepare Google Sheets for your input data and where you want the processed output to be written.

2.  **Node.js Project Setup:**
    *   Clone this repository to your local machine:
        ```bash
        git clone https://github.com/your-username/data-processor.git
        cd data-processor
        ```
    *   Install the project dependencies:
        ```bash
        npm install
        ```
    *   Create a `.env` file in the root of your project directory for environment variables. Populate it with your Google Generative AI API key and any other necessary credentials.
        ```dotenv
        GOOGLE_API_KEY=YOUR_GEMINI_API_KEY
        # Add other environment variables as needed
        ```

### How to Run the Project

1.  **Running the Node.js Script:**
    *   Ensure your `.env` file is correctly configured.
    *   Execute the `index.js` script from your terminal:
        ```bash
        npm start
        ```
    *   This will run the standalone data processing logic defined in `index.js`.

2.  **Running the n8n Workflow:**
    *   Open your n8n instance.
    *   Import the `n8n-workflow.json` file. You can usually do this via `File > Import from File` or `Workflows > New > Import from file`.
    *   **Configure Google Sheets Nodes:**
        *   Edit the `Google Sheets` (Read) node. Select your Google OAuth2 credentials and specify the `Spreadsheet ID` and `Range` where your input data is located.
        *   Edit the `Google Sheets` (Append) node. Select your Google OAuth2 credentials and specify the `Spreadsheet ID` and `Range` where the processed output should be written.
    *   **Configure Google Gemini Node:**
        *   Edit the `Google Gemini` node. Select or create your Google Generative AI credentials (API key or OAuth).
        *   Define the `Prompt` that will be sent to the Gemini model, making sure to reference input data using n8n expressions (e.g., `{{ $json.yourInputDataField }}`).
    *   **Activate and Execute:**
        *   Save the workflow.
        *   Click the "Activate" toggle to enable it.
        *   You can then execute the workflow manually by clicking "Execute Workflow" or set up a trigger (e.g., a webhook or schedule) for automated runs.

## 🛠️ Tech Stack

*   **n8n**: Workflow automation platform for building visual automations.
*   **Node.js**: JavaScript runtime environment for server-side logic and custom scripts.
*   **Google Sheets API**: Programmatic interface for interacting with Google Spreadsheets.
*   **Google Generative AI (Gemini API)**: AI model for advanced text understanding, generation, and transformation.
*   `@google/generative-ai`: Official Node.js client library for Google Generative AI.
*   `csv-parser`: A fast CSV parser for Node.js (used in `index.js` for CSV data handling).
*   `dotenv`: Module to load environment variables from a `.env` file.
*   `googleapis`: Google APIs client library for Node.js, providing access to various Google services.
*   `node-fetch`: A light-weight module that brings `window.fetch` to Node.js for making HTTP requests.

## 👤 Author is akshitha reddy