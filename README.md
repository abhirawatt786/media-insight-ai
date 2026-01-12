# Media Insights AI

**Media Insights AI** is an AI-powered platform that transforms audio and video recordings into **searchable, verifiable knowledge**.  
Upload recordings, ask questions in natural language, and get **accurate answers with exact timestamps**—so you can instantly verify where the answer came from.

This project demonstrates how to build a **scalable, cloud-native AI system** using transcription, retrieval-augmented generation (RAG), and a thoughtful user experience.

---

## 🚀 Why Voice Insights AI?

Teams spend hours:
- Rewatching meetings
- Searching through long recordings
- Manually summarizing conversations

Voice Insights AI removes that friction by letting users **talk to their recordings** and jump straight to the moment that matters.

---

## ✨ Key Features

- 🎙️ **Automatic Transcription**  
  Upload audio or video files and get transcripts generated automatically in multiple languages.

- 🤖 **Chat With Your Media**  
  Ask questions about one file or multiple files.  
  AI answers include **clickable timestamps** that play the media at the exact moment the answer appears.

- ⚡ **Streaming AI Responses**  
  Responses are streamed in real time using WebSockets for a smooth, conversational experience.

- 🌍 **Multilingual Support**  
  Ask questions in one language, analyze media in another, and view subtitles in your preferred language.

- 🧠 **AI-Powered Analysis Templates**  
  Generate summaries, reports, action items, topics, and next steps using customizable templates.

- 🔐 **Secure & Scalable by Design**  
  Authentication, async processing, and fully decoupled frontend/backend architecture.

---

## 🏗️ High-Level Architecture

Voice Insights AI follows a production-grade, cloud-native architecture:

1. **Frontend (React + CloudFront)**  
   Static web app hosted on S3 and served globally via CloudFront.

2. **Authentication (Amazon Cognito)**  
   Secure user authentication and API access control.

3. **File Uploads (Amazon S3)**  
   Media files are uploaded using presigned URLs for efficiency and security.

4. **Async Processing Pipeline**  
   - Transcription and optional media analysis run asynchronously  
   - Event-driven workflows handle background processing  
   - Job status tracked reliably

5. **Knowledge Base + RAG**  
   - Transcripts are embedded and indexed  
   - AI retrieves relevant chunks to answer questions  
   - Answers include precise timestamps for validation

6. **State & Metadata Storage**  
   Job states and analysis templates stored in DynamoDB.

📌 Architecture diagrams are available in the `diagram/` directory.

---

## 📂 Repository Structure

```text
.
├── docs/        # API documentation, usage guides, and design notes
├── frontend/    # React frontend application
├── infra/       # Backend logic and infrastructure (AWS CDK + Lambda)
├── tests/       # Automated tests for backend and integrations
└──README.md

## 🧩 How It Works

1. User uploads an audio or video file  
2. File is stored in S3  
3. Transcription runs asynchronously  
4. Transcript is indexed into a knowledge base  
5. User asks a question  
6. AI retrieves relevant sections and generates an answer  
7. UI highlights exact timestamps for verification  

---


