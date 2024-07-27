# InsightInk

InsightInk is an advanced PDF chat application that enables users to interact with their PDF documents using a conversational AI interface. It leverages modern AI models to provide accurate and detailed responses based on the content of uploaded PDFs.

![InsightInk](https://your-image-url-here.com/image.png)  <!-- Replace with an actual image URL if available -->

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

## Usage

1. **Upload PDF Files**: Use the file uploader in the sidebar to select and upload your PDF documents.
2. **Ask Questions**: Type your questions in the input box and press Enter to receive answers based on the content of the PDFs.

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




