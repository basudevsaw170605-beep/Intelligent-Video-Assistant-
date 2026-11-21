# 🎬 Intelligent Video Assistant

### AI-Powered Video & Meeting Intelligence | Transcribe • Summarize • Extract Insights • Chat

\<p align="center">
&#x20; An AI-powered assistant that transforms long videos, meetings, and audio recordings into meaningful, searchable insights.
\</p>

\<p align="center">
&#x20; \<img src="[https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python\&logoColor=white)" alt="Python">
&#x20; \<img src="[https://img.shields.io/badge/Streamlit-UI-FF4B4B?logo=streamlit&logoColor=white](https://img.shields.io/badge/Streamlit-UI-FF4B4B?logo=streamlit\&logoColor=white)" alt="Streamlit">
&#x20; \<img src="[https://img.shields.io/badge/LangChain-Framework-1C3C3C?logo=langchain&logoColor=white](https://img.shields.io/badge/LangChain-Framework-1C3C3C?logo=langchain\&logoColor=white)" alt="LangChain">
&#x20; \<img src="[https://img.shields.io/badge/LLM-Mistral-orange](https://img.shields.io/badge/LLM-Mistral-orange)" alt="Mistral">
&#x20; \<img src="[https://img.shields.io/badge/RAG-ChromaDB-green](https://img.shields.io/badge/RAG-ChromaDB-green)" alt="RAG">
&#x20; \<img src="[https://img.shields.io/badge/Status-Active-success](https://img.shields.io/badge/Status-Active-success)" alt="Project status">
\</p>

---

## 🚀 Overview

**Intelligent Video Assistant** is an AI-powered application designed to make video and meeting content easier to understand, organize, and explore.

Instead of spending hours watching recordings or reading lengthy transcripts, simply provide a YouTube URL or a local audio/video file path.

The application processes the audio, generates a transcript, creates an AI-powered summary, identifies important action items and decisions, and lets you ask questions about the original content through a Retrieval-Augmented Generation (RAG) pipeline.

Whether you're reviewing meetings, learning from educational videos, or analyzing recorded discussions, this assistant helps turn unstructured conversations into useful information.

## ✨ Key Features

| Feature                        | Description                                                     |
| ------------------------------ | --------------------------------------------------------------- |
| 🎥 YouTube Processing          | Extract audio from YouTube videos using yt-dlp                  |
| 📁 Local Media Processing      | Process local audio and video files                             |
| 🎙️ AI Transcription           | Convert speech into text using OpenAI Whisper                   |
| 🌐 Hinglish Transcription      | Use Sarvam AI to transcribe Hinglish speech into English        |
| 🧠 AI Summarization            | Generate concise, structured meeting summaries                  |
| 🏷️ Automatic Title Generation | Generate professional titles from transcripts                   |
| ✅ Action Item Extraction       | Identify tasks, responsible owners, and mentioned deadlines     |
| 🔑 Key Decision Extraction     | Extract important decisions from conversations                  |
| ❓ Open Question Detection      | Identify unresolved questions and follow-up topics              |
| 💬 Chat with Your Content      | Ask natural-language questions about the transcript             |
| 🔍 Semantic Search             | Retrieve relevant transcript sections using vector embeddings   |
| 📊 Interactive Dashboard       | Monitor processing stages and explore results through Streamlit |

## 🖥️ Application Workflow

The application follows a multi-stage AI processing pipeline:

```text
       YouTube URL / Local Media
                  |
                  ▼
          Audio Extraction
                  |
                  ▼
          Audio Conversion
                  |
                  ▼
          Audio Chunking
                  |
                  ▼
          Speech Transcription
          /              \
      English           Hinglish
       Whisper          Sarvam AI
          \              /
                  |
                  ▼
             Transcript
                  |
         ┌────────┼─────────┐
         ▼        ▼         ▼
      Summary   Action    Key Decisions
                Items
         │        │         │
         └────────┼─────────┘
                  |
                  ▼
           Open Questions
                  |
                  ▼
          Embedding Creation
                  |
                  ▼
             ChromaDB
                  |
                  ▼
             RAG Pipeline
                  |
                  ▼
          Ask Questions About
             Your Content
```

## 🛠️ Technology Stack

| Technology            | Purpose                                                     |
| --------------------- | ----------------------------------------------------------- |
| Python                | Core application development                                |
| Streamlit             | Interactive web interface                                   |
| OpenAI Whisper        | Local speech recognition                                    |
| Sarvam AI             | Hinglish speech-to-text translation                         |
| Mistral AI            | Summarization, title generation, and information extraction |
| LangChain             | LLM orchestration and RAG pipeline                          |
| ChromaDB              | Persistent vector database                                  |
| Hugging Face          | Sentence embeddings                                         |
| Sentence Transformers | Semantic representation of transcript chunks                |
| yt-dlp                | YouTube audio extraction                                    |
| Pydub                 | Audio conversion and processing                             |
| FFmpeg                | Media decoding and conversion                               |

## 🏗️ Project Structure

```text
Intelligent-Video-Assistant/
│
├── app.py
│   └── Streamlit web application
│
├── main.py
│   └── Command-line processing pipeline
│
├── Requirements.txt
│   └── Python dependencies
│
├── .env.example
│   └── Example environment configuration
│
├── .gitignore
│
├── core/
│   ├── extractor.py
│   │   └── Action items, decisions, and questions
│   │
│   ├── rag_engine.py
│   │   └── Retrieval-Augmented Generation
│   │
│   ├── summarizer.py
│   │   └── AI summarization and title generation
│   │
│   ├── transcriber.py
│   │   └── Whisper and Sarvam transcription
│   │
│   └── vector_store.py
│       └── Embeddings and ChromaDB operations
│
└── utils/
    └── audio_processor.py
        └── Downloading, conversion, and chunking
```

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/basudevsaw170605-beep/Intelligent-Video-Assistant-.git
```

Navigate into the project:

```bash
cd Intelligent-Video-Assistant-
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

**Windows PowerShell**

```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r Requirements.txt
```

### 4. Install FFmpeg

FFmpeg is required for audio extraction and media conversion.

Download it from:

[https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)

Make sure FFmpeg is added to your system PATH.

### 5. Configure API credentials

Create a local `.env` file in the project root.

You can use `.env.example` as a template:

```bash
# Windows PowerShell
Copy-Item .env.example .env

# macOS / Linux
cp .env.example .env
```

Add your API credentials:

```env
# Mistral AI — LLM features
MISTRAL_API_KEY=your_mistral_api_key

# Sarvam AI — Hinglish transcription
SARVAM_API_KEY=your_sarvam_api_key

# Optional model configuration
WHISPER_MODEL=small
SARVAM_STT_MODEL=saaras:v2.5
```

Get your API credentials:

- **Mistral AI:** [https://console.mistral.ai/](https://console.mistral.ai/)
- **Sarvam AI:** [https://dashboard.sarvam.ai/](https://dashboard.sarvam.ai/)

**Security:** Never upload your `.env` file or expose your API credentials publicly. The `.env` file is excluded through `.gitignore`.

## ▶️ Run the Application

### Option 1 — Streamlit Web Interface

Start the application:

```bash
streamlit run app.py
```

Open the local URL displayed in your terminal.

**How to use:**

1. Enter a YouTube URL or local audio/video file path in the sidebar.
2. Select the transcription language: `english` or `hinglish`.
3. Click **Analyse**.
4. Wait for the processing pipeline to complete.
5. Explore the generated title, summary, transcript, action items, decisions, and open questions.
6. Ask questions using the **Chat with your Meeting** interface.

### Option 2 — Command-Line Interface

Run:

```bash
python main.py
```

Enter your media source when prompted:

```text
Enter YouTube URL or local file path:
```

Choose the transcription language:

```text
Language (english/hinglish):
```

The application generates the analysis and opens an interactive question-and-answer session in the terminal.

## 🧠 How the RAG System Works

The project uses **Retrieval-Augmented Generation (RAG)** to answer questions using the processed transcript.

The workflow:

1. Split the transcript into smaller text chunks.
2. Generate embeddings using the `all-MiniLM-L6-v2` model.
3. Store the embedded chunks in ChromaDB.
4. Convert the user's question into a retrieval query.
5. Retrieve the four most relevant transcript chunks.
6. Pass the retrieved context and question to Mistral AI.
7. Generate an answer grounded in the available transcript context.

The RAG prompt instructs the assistant to say when the requested information cannot be found in the transcript rather than inventing an answer.

## 🌍 Transcription Modes

The application supports two transcription paths:

**English — OpenAI Whisper**

- Runs locally using the Whisper model.
- Default model: `small`.
- Processes audio chunks and combines their transcripts.

**Hinglish — Sarvam AI**

- Uses Sarvam's speech-to-text translation API.
- Translates Hinglish speech into English text.
- Splits audio into 25-second pieces before sending requests.

The selected language determines which transcription engine is used.

## ⚡ Processing Details

- Audio is converted to mono, 16 kHz WAV format.
- Audio is divided into 10-minute chunks.
- Whisper handles English transcription.
- Sarvam handles the Hinglish transcription path.
- Mistral AI powers summarization and information extraction.
- ChromaDB stores transcript embeddings for semantic retrieval.

## 📌 Requirements & Notes

- Python 3.10 or newer is recommended.
- FFmpeg must be installed separately.
- Mistral API credentials are required for LLM-powered features.
- Sarvam API credentials are required when using Hinglish transcription.
- Whisper downloads its selected model when first used.
- Hugging Face downloads the embedding model when first used.
- Vector database files and downloaded media are generated locally.

**Hardware note:** The current vector-store implementation specifies a GPU device for embeddings. A compatible GPU environment may be required. For CPU-only systems, configure the embedding device as `cpu` in `core/vector_store.py`; for NVIDIA CUDA systems, use the appropriate PyTorch-supported CUDA device.

## 🔐 Security & Privacy

This project follows basic security practices:

- API credentials are stored in local environment variables.
- `.env` is excluded from Git.
- Virtual environments are excluded from version control.
- Generated vector databases and downloaded media are kept out of the repository.

Do not commit API keys, private recordings, transcripts, or other sensitive information.

## 🚧 Future Enhancements

Potential improvements for future versions:

- [ ] Speaker identification and diarization
- [ ] Multi-language transcription support
- [ ] PDF and TXT export for summaries
- [ ] Downloadable meeting reports
- [ ] Improved transcript search and filtering
- [ ] Meeting analytics and insights
- [ ] Cloud deployment
- [ ] Persistent multi-session chat history

## 🤝 Contributing

Contributions, suggestions, and feature requests are welcome!

1. Fork this repository.
2. Create a feature branch.
3. Make your changes.
4. Submit a pull request.

## ⭐ Support

If you find this project useful, consider giving the repository a **Star ⭐** on GitHub.

Your support and feedback are appreciated!

## 👨‍💻 Author

**basudevsaw170605-beep**

GitHub: [https://github.com/basudevsaw170605-beep](https://github.com/basudevsaw170605-beep)

**Project:** [Intelligent Video Assistant](https://github.com/basudevsaw170605-beep/Intelligent-Video-Assistant-)

---

\<p align="center">
&#x20; Built with ❤️ using Python, LangChain, Whisper, Mistral AI, and Streamlit.
\</p>
