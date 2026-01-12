# media-insight-ai
AI-powered platform that transcribes audio/video and lets users ask questions with timestamped, verifiable answers using RAG and cloud-native architecture.
AI-Powered Audio & Video Intelligence Platform

ReVIEW is an AI-powered web application that helps teams extract insights from audio and video recordings.
Upload recordings, ask questions in natural language, and instantly get accurate answers with exact timestamps—so you can verify results yourself.

Built for speed, scale, and clarity, ReVIEW combines speech transcription, retrieval-augmented generation (RAG), and a thoughtful user experience to turn long recordings into actionable knowledge.

🚀 What Problem Does ReVIEW Solve?

Teams spend hours:

Rewatching meetings

Searching through long recordings

Manually summarizing conversations

ReVIEW eliminates that friction by:

Transcribing recordings automatically

Letting users “chat” with their media

Jumping directly to the moment where an answer appears

🔑 Core Features
🎙️ Smart Transcription

Upload audio or video files

Automatic transcription in multiple languages

Real-time processing status in the UI

🤖 Chat With Your Media

Ask questions about one file or many files

AI answers with clickable timestamps

Media plays automatically at the relevant moment

Streaming responses for fast, conversational UX

🌍 Language Freedom

Ask questions in any language

Get answers in the same language

View subtitles translated into your preferred language

🧠 AI-Powered Analysis

Generate summaries, reports, and insights

Identify topics, action items, blockers, and next steps

Create and manage custom analysis templates directly from the UI

🔐 Secure & Scalable

User authentication via Amazon Cognito

Fully decoupled frontend and backend

Built on cloud-native, scalable AWS services

🏗️ High-Level Architecture

ReVIEW follows a clean, production-grade architecture:

Frontend (React + CloudFront)
Users access a fast, global web interface hosted on S3 and CloudFront.

Authentication (Cognito)
Secure login enables protected API access.

File Uploads (S3 + Presigned URLs)
Media files are uploaded directly to S3 for efficiency.

Transcription & Processing

Audio/video is transcribed automatically

Optional AI video analysis extracts additional context

Events trigger background workflows for processing

Knowledge Base & AI Reasoning

Transcripts are embedded and indexed

AI retrieves relevant segments and generates answers

Responses include precise timestamps for verification

State & Metadata

Job statuses and templates stored in DynamoDB

📌 Architecture diagrams are available in the diagram/ directory.

🧩 Why This UX Matters

AI answers are only useful if users can trust them.

ReVIEW ensures trust by:

Showing exact timestamps for every answer

Allowing instant playback for verification

Making AI outputs transparent and explainable

This design makes ReVIEW suitable for:

Meetings & interviews

Research & education

Media analysis

Internal knowledge management

🔧 Deployment Overview

ReVIEW is deployed using AWS CDK (Python) and consists of four main stacks:

Backend Stack – transcription, processing, and job tracking

RAG Stack – search, embeddings, and knowledge base

API Stack – REST + WebSocket APIs

Frontend Stack – React app served via CloudFront

Deployment is fully automated and repeatable.

📂 Repository Structure
infra/        → Infrastructure & backend logic (CDK + Lambdas)
frontend/     → React frontend application
docs/         → API docs and usage guides
diagram/      → Architecture and system diagrams
tests/        → Automated tests


Each layer is cleanly separated to support independent scaling and replacement.

🔄 Frontend Flexibility

The frontend is fully replaceable.

All communication happens via:

REST APIs

WebSocket APIs (for streaming AI responses)

This allows teams to:

Build custom UIs

Integrate with existing products

Use ReVIEW purely as a backend AI service

Detailed API documentation is available in the docs/ folder.

🔒 Security Philosophy

ReVIEW is designed with security in mind:

Authenticated API access

Least-privilege IAM roles

Encrypted data at rest and in transit

⚠️ This project is a proof-of-value, not a hardened production system.
Teams should apply additional security controls based on their compliance needs.

⚠️ Common Pitfalls & Tips

Long-running AI tasks may require increased API timeouts

WebSocket connectivity depends on correct endpoint configuration

Ensure S3 CORS and file size limits are configured correctly

Verify Cognito user pool setup if authentication fails
