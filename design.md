# CodeTutor AI – System Design Document

## 1. Overview

CodeTutor AI is an AI-powered coding mentor designed for students, self-taught developers, and early-career engineers in India.  
It focuses on **understanding-first learning**, helping users explain code, debug errors, summarize documentation, and improve productivity through a simple, chat-based interface.

Unlike traditional AI coding tools that prioritize code generation, CodeTutor AI prioritizes **clarity, learning, and mentorship**, making it especially useful for beginners and learners in Tier 2 and Tier 3 cities.

---

## 2. Design Goals

- Explain code instead of just generating it
- Reduce learning friction for beginners
- Work without complex prompt engineering
- Be scalable, secure, and cost-efficient
- Support future regional language expansion
- Deliver fast, low-latency responses

---

## 3. High-Level Architecture

**Frontend**
- React.js web application
- Hosted on AWS Amplify
- Clean UI with Home Screen and Output Screen

**Backend**
- API Gateway handles HTTP requests
- AWS Lambda (Python) processes user input
- Input Analyzer classifies requests

**AI Layer**
- Amazon Bedrock
- Models: Claude 3.5 Sonnet / LLaMA
- Generates explanations, fixes, summaries, and tips

**Storage & Monitoring**
- Amazon S3 for anonymized logs and cached summaries
- Amazon CloudWatch for monitoring, logging, and error tracking

---

## 4. Component Design

### 4.1 Frontend (React App)

**Screens**
- Home Screen:
  - Input text area
  - Action buttons:
    - Explain This Code
    - Fix My Error
    - Summarize Docs
    - Get Productivity Tips
- Output Screen:
  - AI response card
  - Buttons:
    - Copy
    - Save Note
    - Make Simpler

**Design Principles**
- Beginner-friendly UI
- Minimal distractions
- Mobile-responsive layout

---

### 4.2 Input Analyzer (Lambda)

The Input Analyzer determines the nature of the user input:
- Code Snippet
- Error Message
- Documentation Text
- General Question

**Logic**
- Pattern matching
- Keyword detection
- Syntax indicators
- Error stack trace recognition

---

### 4.3 AI Processing Layer (Amazon Bedrock)

Based on input type:
- **Code** → Line-by-line explanation
- **Error** → Root cause + fix
- **Docs** → Key points + usage tips
- **Question** → Actionable advice

Responses include:
- Simple explanations
- Remembering techniques
- Real-world applications

---

## 5. Data Flow

1. User submits input from frontend
2. Request sent to API Gateway
3. Lambda function processes input
4. Input Analyzer classifies request
5. Prompt sent to Amazon Bedrock
6. AI response generated
7. Response returned to frontend
8. Optional anonymized data stored in S3

---

## 6. Security & Privacy

- No permanent storage of user code
- Logs are anonymized
- HTTPS enforced via API Gateway
- IAM roles with least privilege access

---

## 7. Scalability & Performance

- Serverless architecture ensures auto-scaling
- Stateless Lambda functions
- CloudWatch monitors latency and errors
- S3 caching reduces repeat computation

---

## 8. Future Enhancements

- Regional language support using Amazon Translate
- IDE plugins (VS Code)
- User accounts and learning history
- Voice-based input/output
- Offline learning summaries

---

## 9. Alignment with Bharat Initiatives

- Supports Digital India and Skill India
- Democratizes access to quality tech education
- Reduces dependence on costly coaching
- Enables learners from non-metro regions to compete globally
