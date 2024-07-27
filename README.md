# InsightInk

InsightInk is an advanced PDF chat application that enables users to interact with their PDF documents using a conversational AI interface. It leverages modern AI models to provide accurate and detailed responses based on the content of uploaded PDFs.

## Features

- **Upload and Process PDFs**: Easily upload multiple PDF files for processing.
- **Text Extraction**: Efficiently extracts text from the PDFs.
- **Chunking**: Splits text into manageable chunks for better analysis.
- **Vector Store**: Utilizes FAISS for indexing and similarity searches.
- **Conversational AI**: Provides intelligent responses to user queries based on the content of the PDFs.
- **Interactive UI**: Engaging and user-friendly interface built with Streamlit.

## Live Demo

Experience InsightInk in action: [Live Demo](https://insightink.streamlit.app/)

## Installation

Follow these steps to set up InsightInk locally:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/prateek08s/InsightInk.git
   cd InsightInk
   ```

2. **Set Up a Virtual Environment:**

   ```bash
   python -m venv venv
   ```

3. **Activate the Virtual Environment:**

   - **Windows:**

     ```bash
     venv\Scripts\activate
     ```

   - **macOS/Linux:**

     ```bash
     source venv/bin/activate
     ```

4. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

5. **Configure Environment Variables:**

   Copy the `.env.example` file to `.env` and add your Google API key:

   ```bash
   cp .env.example .env
   ```

   Edit the `.env` file to include:

   ```env
   GOOGLE_API_KEY=your_google_api_key_here
   ```

6. **Run the Application:**

   ```bash
   streamlit run app.py
   ```

## Troubleshooting

### StreamlitAPIException

If you encounter the error:

```
StreamlitAPIException: set_page_config() can only be called once per app page, and must be called as the first Streamlit command in your script.
```

Ensure `st.set_page_config()` is the very first Streamlit command in your script:

```python
import streamlit as st
# other imports...

st.set_page_config(page_title="Chat PDF", layout="wide")
# rest of the code...
```

### Deserialization Error

For issues with deserialization:

```
Failed to process user input: The de-serialization relies on loading a pickle file...
```

You need to enable dangerous deserialization if you trust the source of your pickle files. Add the following to your Streamlit configuration:

```python
st.set_option('allow_dangerous_deserialization', True)
```

Ensure that this option is only used with trusted sources to avoid security risks.

### AxiosError 403

If you encounter an AxiosError with status code 403:

```
AxiosError: Request failed with status code 403
```

This typically indicates a permissions issue or a problem with accessing the API. Here's how to address it:

1. **Verify API Key**: Ensure that your Google API key is correct and has the necessary permissions. Check the [Google API Console](https://console.cloud.google.com/) for your API key settings.

2. **Streamlit Configuration**: If deploying on Replit or similar platforms, create a `.streamlit` folder in your project directory and add a `config.toml` file with the following content:

   ```toml
   [server]
   enableXsrfProtection = false
   enableCORS = false
   ```

3. **Check API Quotas**: Ensure you have not exceeded your API quotas or limits set by Google.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Open a Pull Request.


## Acknowledgments

- **Streamlit**: For building the interactive web application framework.
- **LangChain**: For the language models and tools used in this project.
- **Google Generative AI**: For the AI models used in text generation and embeddings.


