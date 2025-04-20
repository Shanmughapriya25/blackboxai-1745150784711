# Content Summarizer & Chat Extension

This is a browser extension that allows you to summarize selected content on any webpage, listen to the summary via text-to-speech with avatars, and chat with an AI assistant that answers questions related only to the selected content or webpage.

## Features

- Two avatars (male and female) displayed in the extension popup.
- Summarize selected text on the webpage.
- Text-to-speech feature where avatars speak the summary.
- Chat panel to ask questions related to the selected content.
- Uses Ollama 3.2 API for language model interaction.
- Retrieval-Augmented Generation (RAG) to answer questions based on the content.
- Flask backend to handle API requests.
- React frontend for the extension popup UI.

## Setup Instructions

### Backend (Flask)

1. Navigate to the `backend` directory:
   ```bash
   cd backend
   ```

2. Create a virtual environment and activate it (optional but recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Replace the placeholder API key in `app.py` with your actual Ollama 3.2 free API key:
   ```python
   OLLAMA_API_KEY = "your_free_api_key_here"
   ```

5. Run the Flask backend:
   ```bash
   python app.py
   ```

   The backend will run on `http://localhost:5000`.

### Frontend (Browser Extension)

1. Load the extension in your browser (Chrome/Edge):

   - Open the browser and go to `chrome://extensions/`
   - Enable "Developer mode" (toggle in the top right)
   - Click "Load unpacked"
   - Select the project root directory (where `manifest.json` is located)

2. Open any webpage, select some text, then click the extension icon.

3. Use the popup UI to summarize the selected text, listen to the summary, or ask questions related to the content.

## Notes

- The extension uses the browser's native speech synthesis for text-to-speech.
- Ensure the Flask backend is running before using the extension features.
- The Ollama API key is required for the backend to communicate with the Ollama 3.2 model.
- The RAG approach is implemented by sending the selected content along with the question to the model.

## Technologies Used

- React with Tailwind CSS for frontend UI.
- Flask for backend API.
- Ollama 3.2 API for language model.
- Chrome Extension Manifest V3.

## License

This project is provided as-is without warranty.
