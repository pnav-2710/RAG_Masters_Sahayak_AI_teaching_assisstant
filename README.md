# Sahayak App

Sahayak is an AI-powered teaching assistant platform for educators in India. It provides multimodal tools for lesson planning, worksheet generation, assessment evaluation, and visual learning aids, leveraging Google Vertex AI, Firebase, and Streamlit.

## Features

- **VidyaMitra Agent**: Multimodal AI assistant for lesson plans, worksheets, explanations, and reading assessments.
- **SmartEval Agent**: Automated MCQ and descriptive answer evaluation with feedback and markdown reports.
- **ConceptCanvas**: Generate diagrams, illustrations, and animated videos for educational concepts.
- **User Authentication**: Secure login and signup with Firebase Authentication.
- **File Uploads**: Upload and store files (images, PDFs, videos) in Firebase Storage.
- **Chat History**: Stores and retrieves chat history using Firestore.

## Project Structure

```
sahayak-app/
  backend/
    main.py                # Flask backend with AI agent endpoints
    requirements.txt       # Backend dependencies
    functions/
      main.py              # Firebase Cloud Functions (Python)
      requirements.txt
    firebase.json          # Firebase configuration
    .firebaserc            # Firebase project settings
  frontend/
    streamlit_app.py       # Streamlit frontend app
  .gitignore
  README.md                # (You are here)
```

## Getting Started

### Prerequisites

- Python 3.10+
- Node.js (for Firebase CLI)
- [Google Cloud SDK](https://cloud.google.com/sdk/docs/install)
- [Firebase CLI](https://firebase.google.com/docs/cli)
- Service account with access to Vertex AI and Firestore

### Backend Setup

1. **Install dependencies:**
   ```sh
   cd backend
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   pip install -r requirements.txt
   ```

2. **Set up Google Cloud credentials:**
   - Ensure `GOOGLE_APPLICATION_CREDENTIALS` is set to your service account JSON key.

3. **Run the backend server:**
   ```sh
   python main.py
   ```
   The backend will start on `http://127.0.0.1:6000`.

4. **(Optional) Deploy Firebase Functions:**
   ```sh
   cd functions
   pip install -r requirements.txt
   firebase deploy --only functions
   ```

### Frontend Setup

1. **Install frontend dependencies:**
   ```sh
   cd ../frontend
   pip install streamlit pyrebase4 google-cloud-firestore google-cloud-texttospeech pillow streamlit-geolocation
   ```

2. **Run the Streamlit app:**
   ```sh
   streamlit run streamlit_app.py
   ```

3. **Access the app:**
   - Open the provided local URL in your browser.

### Configuration

- Update `FIREBASE_CONFIG` in `frontend/streamlit_app.py` with your Firebase project details.
- Ensure your Google Cloud project has Vertex AI, Firestore, and Text-to-Speech APIs enabled.

## Usage

- **Login/Signup**: Create an account or log in using your email and password.
- **VidyaMitra**: Chat with the AI assistant, upload files, and get contextual educational content.
- **SmartEval**: Upload answer key and student sheets for automated evaluation.
- **ConceptCanvas**: Generate images or videos for educational concepts and view history.

## Notes

- The backend uses Google Vertex AI for generative tasks and Firestore for chat history.
- File uploads are stored in Firebase Storage.
- Ensure your service account has the necessary permissions for all Google Cloud services used.

## License

This project is for educational purposes.

---

**Developed with RAG_Masters_Sahayak_AI_teaching_assisstant
