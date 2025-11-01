# 🚀 Project Introduction

Welcome to the **Groq Content Generator**! This project provides a user-friendly Streamlit web application that leverages the powerful Groq API to generate content using various Large Language Models (LLMs). It offers an interactive interface for users to input prompts, select their preferred LLM, and instantly receive generated text, making LLM content creation accessible and efficient.

## ✨ Features

*   🎯 **Interactive User Interface:** Built with Streamlit for a seamless and intuitive user experience.
*   🧠 **LLM Content Generation:** Utilizes the Groq API to tap into high-performance Large Language Models.
*   ⚙️ **Model Selection:** Allows users to choose between different LLM models (e.g., Llama 3, Mixtral) directly from the sidebar.
*   📝 **Dynamic Prompt Input:** Provides a text area for users to enter custom prompts.
*   💡 **Clear Output Display:** Presents generated content prominently on the interface.
*   🌙 **Dark Theme:** Configured with a dark theme for enhanced visual comfort.

## ⚙️ Workflow Overview

The application follows a straightforward workflow to generate content:

*   **1. Access Application:** The user launches the Streamlit application, which presents the main interface.
*   **2. Select LLM Model:** From the sidebar, the user can select their desired Large Language Model (e.g., `llama3-8b-8192` or `mixtral-8x7b-32768`).
*   **3. Enter Prompt:** The user inputs their specific content request into the provided text area.
*   **4. Generate Content:** Upon clicking the "Generate Content" button, the application initiates the content generation process.
*   **5. API Interaction:** The application sends the user's prompt and selected model to the Groq API.
*   **6. Receive Output:** The Groq API processes the request using the chosen LLM and returns the generated text.
*   **7. Display Result:** The received content is then displayed back to the user on the Streamlit web page.

**Visual Workflow Description:**
*   **`input.png`**: This image showcases the initial state of the Streamlit application. It displays the "Groq Content Generator" title, the sidebar with the "Select LLM Model" dropdown (showing 'llama3-8b-8192' selected), a text area for entering a prompt, and the "Generate Content" button. This visualizes where the user provides input.
*   **`output.png`**: This image illustrates the application after content has been generated. It maintains the same layout as `input.png` but now shows the output below the "Generate Content" button, displaying the LLM's response to the user's prompt (e.g., an explanation of quantum computing).

## 🧪 Example Output

A typical output will display the generated content directly on the web page below the input prompt and "Generate Content" button. For instance, if the prompt is "Explain quantum computing in simple terms," the output section will contain a detailed, easy-to-understand explanation provided by the selected LLM.

## 🚀 Getting Started

Follow these steps to set up and run the Groq Content Generator locally.

### Installation Steps

1.  **Clone the Repository:**
    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```
    *(Replace `<repository_url>` and `<repository_directory>` with actual values if known.)*

2.  **Create a Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate # On Windows use `venv\Scripts\activate`
    ```

3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Set Up Groq API Key:**
    *   Obtain your `GROQ_API_KEY` from the [Groq Console](https://console.groq.com/keys).
    *   Create a `.streamlit` directory in your project root if it doesn't exist.
    *   Inside the `.streamlit` directory, create a file named `secrets.toml`.
    *   Add your API key to `secrets.toml` in the following format:
        ```toml
        GROQ_API_KEY="your_groq_api_key_here"
        ```
        *Replace `"your_groq_api_key_here"` with your actual API key.*

### How to Run the Project

1.  **Start the Streamlit Application:**
    ```bash
    streamlit run input.py
    ```

2.  Your web browser will automatically open to the Streamlit application (usually `http://localhost:8501`).

## 🛠️ Tech Stack

*   **Python:** The core programming language.
*   **Streamlit:** Used for creating the interactive web user interface.
*   **Groq API:** Provides access to high-performance Large Language Models for content generation.
*   **LLM Models:** Specifically uses `llama3-8b-8192` and `mixtral-8x7b-32768` via Groq.

## 👤 Author is akshitha reddy

Akshitha Reddy