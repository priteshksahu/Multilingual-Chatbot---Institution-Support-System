# AI Knowledge Assistant - Enhanced Data Flow Diagram

## System Overview

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                        AI KNOWLEDGE ASSISTANT SYSTEM                           │
│                    (Document Analysis + General Knowledge)                     │
└─────────────────────────────────────────────────────────────────────────────────┘

┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   FRONTEND      │    │    BACKEND      │    │   DATABASE      │
│   (index.html)  │    │   (server.py)   │    │  (SQLite/JSON)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## Enhanced Capabilities

### 1. DUAL MODE OPERATION
```
┌─────────────────────────────────────────────────────────────────┐
│                    KNOWLEDGE MODES                             │
├─────────────────────────────────────────────────────────────────┤
│  📚 DOCUMENT MODE          🌍 GENERAL KNOWLEDGE MODE           │
│  • PDF/DOCX/PPTX/TXT       • General Knowledge                 │
│  • Image OCR               • Mathematics                       │
│  • Document-specific Q&A   • Geopolitics                       │
│  • Content extraction      • Entertainment                     │
│                            • News & Current Affairs            │
│                            • Science & Technology              │
│                            • History & Geography               │
└─────────────────────────────────────────────────────────────────┘
```

## Complete Data Flow

### 1. USER INPUT PROCESSING
```
┌─────────────────────────────────────────────────────────────────┐
│                    USER INTERACTION LAYER                      │
├─────────────────────────────────────────────────────────────────┤
│  Input Types:                                                   │
│  • Text Questions (Any topic)                                  │
│  • Voice Questions (Speech-to-Text)                            │
│  • Document Upload (PDF, DOCX, PPTX, TXT, PNG, JPG)           │
│  • Mixed: Document + Questions                                 │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    INTELLIGENT ROUTING                         │
├─────────────────────────────────────────────────────────────────┤
│  Decision Logic:                                               │
│  • Has Document? → Document Mode + General Knowledge           │
│  • No Document? → Pure General Knowledge Mode                  │
│  • Voice Input? → Transcribe + Process                        │
│  • Language? → Multilingual Processing                         │
└─────────────────────────────────────────────────────────────────┘
```

### 2. BACKEND PROCESSING PIPELINE
```
┌─────────────────────────────────────────────────────────────────┐
│                    FASTAPI SERVER                              │
├─────────────────────────────────────────────────────────────────┤
│  • Request Analysis                                            │
│  • Mode Detection (Document vs General)                       │
│  • Language Detection                                          │
│  • Input Validation                                            │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    DOCUMENT PROCESSING (if applicable)         │
├─────────────────────────────────────────────────────────────────┤
│  • PDF: PyPDF2 → Text Extraction                               │
│  • DOCX: python-docx → Paragraph Extraction                    │
│  • PPTX: python-pptx → Slide Text Extraction                   │
│  • TXT: Direct Text Reading                                     │
│  • Images: Tesseract OCR → Gemini Vision Fallback              │
│  • Text Chunking (20K chars per chunk)                         │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    AUDIO PROCESSING (if applicable)            │
├─────────────────────────────────────────────────────────────────┤
│  • WebM Audio → Gemini 1.5 Flash → Text Transcription         │
│  • Language Detection & Processing                              │
│  • Audio Quality Optimization                                  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    AI PROCESSING ENGINE                        │
├─────────────────────────────────────────────────────────────────┤
│  Mode Selection:                                               │
│  ┌─────────────────┐  ┌─────────────────┐                     │
│  │  DOCUMENT MODE  │  │  KNOWLEDGE MODE │                     │
│  ├─────────────────┤  ├─────────────────┤                     │
│  │ • Document text │  │ • General AI    │                     │
│  │ • User query    │  │ • Knowledge base│                     │
│  │ • Context-aware │  │ • Real-time     │                     │
│  │ • Citation      │  │ • Comprehensive │                     │
│  └─────────────────┘  └─────────────────┘                     │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    GEMINI 1.5 FLASH PROCESSING                 │
├─────────────────────────────────────────────────────────────────┤
│  Input Construction:                                            │
│  • System Prompt (Mode-specific)                               │
│  • Document Content (if available)                             │
│  • User Question                                               │
│  • Language Context                                            │
│  • Response Formatting                                         │
└─────────────────────────────────────────────────────────────────┘
```

### 3. KNOWLEDGE DOMAINS COVERAGE
```
┌─────────────────────────────────────────────────────────────────┐
│                    KNOWLEDGE DOMAINS                           │
├─────────────────────────────────────────────────────────────────┤
│  📚 ACADEMIC SUBJECTS          🎯 PRACTICAL APPLICATIONS       │
│  • Mathematics                 • Current Affairs               │
│  • Science (Physics, Chem, Bio) • Geopolitics                 │
│  • History                     • Technology News               │
│  • Geography                   • Entertainment Updates         │
│  • Literature                  • Sports News                   │
│  • Economics                   • Business & Finance            │
│  • Political Science           • Health & Medicine             │
│  • Philosophy                  • Environmental Issues          │
│  • Psychology                  • Social Issues                 │
│  • Computer Science            • Cultural Events               │
└─────────────────────────────────────────────────────────────────┘
```

### 4. RESPONSE GENERATION
```
┌─────────────────────────────────────────────────────────────────┐
│                    RESPONSE INTELLIGENCE                       │
├─────────────────────────────────────────────────────────────────┤
│  Response Types:                                               │
│  • Factual Answers (with citations)                            │
│  • Step-by-step Solutions (Math, Science)                      │
│  • Current Events (with disclaimers)                           │
│  • Explanatory Content (Educational)                           │
│  • Comparative Analysis (Multiple perspectives)                │
│  • Creative Responses (Entertainment, Literature)              │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    MULTILINGUAL OUTPUT                         │
├─────────────────────────────────────────────────────────────────┤
│  Language Support:                                             │
│  • English (Primary)                                           │
│  • Hindi (हिंदी)                                              │
│  • Malayalam (മലയാളം)                                        │
│  • Marathi (मराठी)                                            │
│  • Telugu (తెలుగు)                                           │
│  • Bhojpuri (भोजपुरी)                                        │
└─────────────────────────────────────────────────────────────────┘
```

## Enhanced System Architecture

### Frontend Capabilities
```
┌─────────────────────────────────────────────────────────────────┐
│                    ENHANCED FRONTEND                           │
├─────────────────────────────────────────────────────────────────┤
│  UI Features:                                                  │
│  • Universal Question Input (Any topic)                        │
│  • Document Upload (6 formats)                                 │
│  • Voice Input/Output (6 languages)                            │
│  • Real-time Chat Interface                                    │
│  • Language Selection                                          │
│  • Chat History Management                                     │
│  • Response Actions (Copy, Regenerate, Speak)                  │
│  • File Preview & Management                                   │
└─────────────────────────────────────────────────────────────────┘
```

### Backend Intelligence
```
┌─────────────────────────────────────────────────────────────────┐
│                    ENHANCED BACKEND                            │
├─────────────────────────────────────────────────────────────────┤
│  Processing Capabilities:                                      │
│  • Smart Mode Detection                                        │
│  • Document Analysis (6 formats)                               │
│  • OCR Processing (Images)                                     │
│  • Voice Transcription                                         │
│  • Multilingual AI Processing                                  │
│  • Context-Aware Responses                                     │
│  • Knowledge Domain Routing                                    │
│  • Error Handling & Recovery                                   │
└─────────────────────────────────────────────────────────────────┘
```

## Use Case Examples

### 1. Academic Questions
```
User: "Explain quantum mechanics"
AI: [Comprehensive explanation with examples, formulas, and applications]

User: "What is the capital of Bhutan?"
AI: [Direct answer with additional geographical context]

User: "Solve this math problem: 2x + 5 = 15"
AI: [Step-by-step solution with explanation]
```

### 2. Document Analysis
```
User: [Uploads research paper] "Summarize the main findings"
AI: [Document-based summary with specific citations]

User: [Uploads image] "What does this diagram show?"
AI: [OCR + AI analysis of the visual content]
```

### 3. Current Affairs
```
User: "What's happening in Ukraine?"
AI: [Current geopolitical analysis with context]

User: "Latest developments in AI technology"
AI: [Recent AI news and technological advances]
```

### 4. Entertainment & Culture
```
User: "Tell me about the latest Bollywood movies"
AI: [Recent movie releases, reviews, and cultural context]

User: "Explain the rules of cricket"
AI: [Comprehensive explanation of cricket rules and gameplay]
```

## Technical Implementation

### Database Schema (Enhanced)
```sql
-- Chat Sessions
CREATE TABLE chat_sessions (
    session_id TEXT PRIMARY KEY,
    title TEXT,
    language TEXT,
    mode TEXT, -- 'document', 'general', 'mixed'
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Messages
CREATE TABLE messages (
    message_id INTEGER PRIMARY KEY AUTOINCREMENT,
    session_id TEXT,
    sender TEXT, -- 'user' or 'assistant'
    content TEXT,
    message_type TEXT, -- 'text', 'voice', 'file', 'general'
    domain TEXT, -- 'math', 'science', 'geopolitics', etc.
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (session_id) REFERENCES chat_sessions(session_id)
);

-- File Uploads
CREATE TABLE file_uploads (
    file_id INTEGER PRIMARY KEY AUTOINCREMENT,
    session_id TEXT,
    filename TEXT,
    file_type TEXT,
    file_size INTEGER,
    upload_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (session_id) REFERENCES chat_sessions(session_id)
);
```

## Performance Optimizations

### 1. Smart Caching
- Frequently asked questions
- Document processing results
- Language-specific responses

### 2. Response Streaming
- Real-time response generation
- Progressive text display
- Voice synthesis streaming

### 3. Resource Management
- Document size limits
- Processing timeouts
- Memory optimization

## Security & Privacy

### 1. Data Protection
- Local database storage
- No external data sharing
- Secure API key management

### 2. Input Validation
- File type restrictions
- Size limitations
- Content filtering

### 3. Error Handling
- Graceful failure recovery
- User-friendly error messages
- Logging and monitoring

## Future Enhancements

### Phase 1: Advanced Features
- Real-time news integration
- Custom knowledge bases
- Advanced mathematical solving
- Code generation and debugging

### Phase 2: Specialized Modes
- Exam preparation mode
- Research assistant mode
- Creative writing mode
- Technical documentation mode

### Phase 3: Integration
- LMS integration
- Cloud storage sync
- API marketplace
- Third-party plugins

This enhanced system transforms your Document Assistant into a comprehensive AI Knowledge Assistant that can handle any question while maintaining its document analysis capabilities!
