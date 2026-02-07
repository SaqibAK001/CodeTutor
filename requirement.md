# CodeTutor AI – Requirements Specification

## 1. Introduction

This document defines the functional and non-functional requirements for CodeTutor AI, an AI-powered learning assistant designed to improve coding understanding, debugging skills, and productivity for Indian developers.

---

## 2. Functional Requirements

### 2.1 Code Explanation
- Users must be able to paste code snippets
- System shall return line-by-line explanations
- Explanations must be in simple, beginner-friendly English
- System should provide real-life applications of concepts

---

### 2.2 Error Debugging
- Users must be able to paste error messages with or without code
- System shall identify the root cause of the error
- System shall suggest fixes and best practices
- Common runtime and compile-time errors must be supported

---

### 2.3 Documentation Summarization
- Users must be able to paste technical documentation
- System shall generate a concise, structured summary
- Key points and usage tips must be highlighted

---

### 2.4 Productivity & Workflow Coaching
- Users may ask productivity-related questions
- System shall provide actionable development tips
- Suggestions should be context-aware and practical

---

### 2.5 Beginner Mode
- System must support a Beginner Mode toggle
- When enabled, responses must be simplified further
- Mode must be switchable at any time

---

### 2.6 Output Actions
- Users must be able to:
  - Copy AI responses
  - Save notes locally
  - Request simpler explanations

---

## 3. Non-Functional Requirements

### 3.1 Performance
- Average response time < 5 seconds
- Must handle concurrent users efficiently

---

### 3.2 Scalability
- Must auto-scale based on demand
- No manual server management

---

### 3.3 Availability
- System uptime target: 99.9%
- Fault-tolerant architecture

---

### 3.4 Security
- Secure API endpoints
- No permanent storage of sensitive user data
- IAM-based access control

---

### 3.5 Usability
- Simple, intuitive UI
- No prompt engineering required
- Suitable for beginners and students

---

## 4. Technology Requirements

| Component | Technology |
|--------|-----------|
Frontend | React.js + CSS |
Hosting | AWS Amplify |
Backend | AWS Lambda (Python) |
API | Amazon API Gateway |
AI Engine | Amazon Bedrock (Claude 3.5 / LLaMA) |
Storage | Amazon S3 |
Monitoring | Amazon CloudWatch |
Future | Amazon Translate |

---

## 5. Constraints

- Internet connectivity required
- AI responses depend on model limitations
- Free-tier limits may affect large-scale usage

---

## 6. Assumptions

- Users have basic programming exposure
- Users primarily access via web browser
- English is the default language

---

## 7. Future Requirements

- Regional language support
- User profiles and learning history
- Mobile application
- IDE integrations

---

## 8. Success Criteria

- Reduced time spent debugging
- Improved learner confidence
- High usability for beginners
- Positive feedback from students and educators
