# AI-Powered Real Estate Lead Qualification System
  
**Platform:** N8N Workflow Automation  
**Integration:** WhatsApp Business API, Google Sheets, OpenAI GPT-4

## Overview

This project implements a comprehensive AI-powered lead qualification system for real estate that automates lead processing, data collection, and agent coordination via WhatsApp. The system conducts interactive conversations with potential clients, scores leads based on qualification criteria, and coordinates with real estate agents for property suggestions and viewing scheduling.


## 🏗️ System Architecture

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Lead Intake   │────▶│  AI Qualification│────▶│   Lead Scoring│
│   (Form/WebHook)│     │      Agent      │     │   & Assignment  │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                │                         │
                                ▼                         ▼
                        ┌─────────────────┐     ┌─────────────────┐
                        │ Google Sheets   │     │ Agent Matching  │
                        │  Data Logger    │     │ & Notification  │
                        └─────────────────┘     └─────────────────┘
                                                          │
                                                          ▼
                                                ┌─────────────────┐
                                                │WhatsApp Business│
                                                │   Integration   │
                                                └─────────────────┘
```

### Google Sheets Integration
The system uses 4 interconnected sheets for complete data management:
- **leads_master**: Main lead database with scoring and assignments
- **agent_assignments**: Lead-agent mapping and coordination
- **agents**: Agent profiles with location coverage and specialties  
- **conversations**: Complete conversation logs with AI responses

## 📋 Core Components

### 1. **Lead Capture & Processing**
- Form trigger with comprehensive data collection
- Phone number validation and formatting
- Lead scoring algorithm (A/B/C grades)
- Automatic Google Sheets logging

### 2. **WhatsApp AI Coordination Hub**
- AI agent with 4 specialized tools:
  - Lead Lookup Tool
  - Lead Score Updater Tool  
  - Agent Assignment Lookup Tool
  - WhatsApp Messenger Tool
- Conversation memory and context tracking
- Agent vs Lead identification

### 3. **Automatic Agent Assignment**
- Location-based agent matching
- A/B grade lead prioritization
- Real-time agent notifications
- Assignment tracking in Google Sheets

## 🛠️ Technical Implementation

### Agent Architecture
- **Qualification Agent**: Conversational interface, data validation
- **Scoring Agent**: Lead quality assessment, routing decisions  
- **Coordinator Agent**: Agent communication, property matching

### Integration Stack
- **Google Sheets API**: Data storage and management
- **WhatsApp Business API**: Real-time communication via Twilio
- **OpenAI GPT-4**: Natural language processing
- **N8N**: Workflow orchestration platform

### Google Sheets Schema
**leads_master Sheet:**
- lead_id, created_at, name, phone, email
- property_type, budget, location, timeline, requirements
- status, lead_score, assigned_agent, agent_notified

**agent_assignments Sheet:**
- lead_id, phone, assigned_agent, agent_phone
- assignment_date, status, notes

**conversations Sheet:**
- timestamp, phone, message, ai_response, message_sid

**agents Sheet:**
- agent_id, agent_name, agent_phone, location_coverage, speciality

## 🔄 Workflow Process

### Initial Lead Processing
1. **Form Submission** → Data processing & validation
2. **Lead Scoring** → A/B/C grade assignment based on:
   - Budget range (40% weight)
   - Timeline urgency (30% weight)  
   - Financing status (20% weight)
   - Requirements clarity (10% weight)
3. **Google Sheets Logging** → Complete lead profile storage
4. **WhatsApp Welcome** → Personalized initial contact

### AI-Powered Qualification
1. **WhatsApp Message Reception** → Twilio webhook trigger
2. **Sender Identification** → Agent vs Lead detection
3. **AI Agent Processing** → Context-aware responses using tools
4. **Database Updates** → Real-time information storage
5. **Conversation Logging** → Complete interaction history

### Agent Coordination
1. **Automatic Assignment** → Location-based agent matching
2. **Agent Notification** → Comprehensive lead summary via WhatsApp
3. **Property Suggestions** → Agent recommendations forwarding
4. **Viewing Coordination** → Schedule management and confirmations

## 📱 WhatsApp Integration Features

- **Lead Qualification**: Interactive data collection conversations
- **Agent Communication**: Property suggestions and lead updates  
- **Viewing Scheduling**: Time coordination and confirmations
- **Conversation Memory**: Context preservation across interactions
- **Error Handling**: Graceful failure management

## 🎯 Lead Scoring System

### A-Grade Leads (80+ points)
- High budget ($600k+), immediate timeline, cash/pre-approved
- Premium agent assignment within 15 minutes

### B-Grade Leads (60-79 points)  
- Medium budget ($200k-$600k), 1-6 month timeline
- Standard agent assignment within 1 hour

### C-Grade Leads (Below 60 points)
- Lower budget or longer timeline
- Basic agent assignment with nurture sequence

## 📊 Data Management

All interactions logged to Google Sheets with structured format:
- Complete lead profiles with qualification responses
- Conversation transcripts and AI responses
- Agent assignments and communication history
- Response times and conversion tracking


## 📁 Repository Structure

```
├── workflow.json                                    # Complete N8N workflow 
├── README.md                                       # This documentation
├── SETUP_INSTRUCTIONS.md                          # Configuration guide for deployment
├── Real Estate Lead Qualification Form Template.md # Data collection criteria
├── TODO.md                                        # Implementation guide
├── take_home_assignment.pdf                       # Original requirements
├── Agent_assignement_sheet.png                    # Google Sheets agent assignments screenshot
├── Agent_conv1.png                                # WhatsApp agent conversation demo 1
├── Agent_conv2.png                                # WhatsApp agent conversation demo 2
├── Agents_sheet.png                               # Google Sheets agents database screenshot
├── Conversations_sheet.png                        # Google Sheets conversation logs screenshot
├── Lead.png                                       # WhatsApp lead conversation demo
└── leads_master_sheet.png                         # Google Sheets lead master data screenshot
```

## 🚀 Deployment Instructions

⚠️ **IMPORTANT**: The workflow.json file has been sanitized to remove all personal data, phone numbers, and API credentials. 

**See [SETUP_INSTRUCTIONS.md](SETUP_INSTRUCTIONS.md) for detailed configuration steps.**

### Quick Setup:
1. **Import Workflow**: Load `workflow.json` into N8N instance
2. **Replace Placeholders**: Update phone numbers, Google Sheets ID, and credentials
3. **Configure Credentials**: Set up Google Sheets, Twilio, and OpenAI APIs
4. **Create Google Sheets**: Set up required sheet structure
5. **Test & Activate**: Verify all integrations and enable workflow

## 📈 Success Metrics

- **Conversation Quality (30%)**: Natural dialogue, complete data collection
- **System Integration (25%)**: Google Sheets logging, WhatsApp functionality  
- **Agent Coordination (20%)**: Effective communication between agents
- **Data Accuracy (15%)**: Proper validation, scoring, routing
- **User Experience (10%)**: Smooth interactions, error handling

## 🎬 Demo Video & Evidence

The repository includes comprehensive visual evidence of the working system:

### Demo Video Features
- End-to-end lead qualification demo
- WhatsApp agent communication in real-time
- Google Sheets logging demonstration
- Lead scoring logic explanation  
- Agent coordination and property suggestions
- Complete viewing scheduling workflow

### Supporting Screenshots
The repository includes Google Sheets screenshots showing the complete data structure and sample data, plus WhatsApp conversation examples demonstrating the full lead qualification and agent coordination flow.

## 🔧 Advanced Features

- **Conversation Memory**: Context preservation across WhatsApp interactions
- **Concurrent Processing**: Multiple leads handled simultaneously
- **Error Handling**: API failure recovery and fallback mechanisms
- **Agent Availability**: Smart routing based on agent workload
- **Follow-up Automation**: Scheduled reminders for unresponsive leads


For questions about implementation or setup, refer to the comprehensive guides in:
- `TODO.md` - Technical implementation details
- `Real Estate Lead Qualification Form Template.md` - Data collection schema
- `workflow.json` - Complete N8N workflow configuration
- Screenshots/ - Visual evidence of working system

## 📁 Repository Structure

```
├── workflow.json                                    # Complete N8N workflow (sanitized)
├── README.md                                       # This documentation
├── SETUP_INSTRUCTIONS.md                          # Configuration guide for deployment
├── Real Estate Lead Qualification Form Template.md # Data collection criteria
└── Screenshots/                                    # Visual evidence and demo materials
    ├── Agent_assignement_sheet.png                # Google Sheets agent assignments
    ├── Agent_conv1.png                            # WhatsApp agent conversation demo 1
    ├── Agent_conv2.png                            # WhatsApp agent conversation demo 2
    ├── Agents_sheet.png                           # Google Sheets agents database
    ├── Conversations_sheet.png                    # Google Sheets conversation logs
    ├── Lead_conv.png                              # WhatsApp lead conversation demo
    └── leads_master_sheet.png                     # Google Sheets lead master data
```

## 🎯 Assignment Deliverables Status

✅ **N8N Workflow Export** - Complete system workflow (`workflow.json`)  
✅ **Documentation** - Comprehensive README with system architecture  
✅ **Google Sheets Integration** - All 4 sheets with structured data logging  
✅ **WhatsApp Business API** - Complete agent and lead communication  
✅ **Lead Qualification System** - AI-powered conversation flow  
✅ **Agent Coordination** - Automatic assignment and property suggestions  
✅ **Visual Evidence** - Screenshots demonstrating all functionality  
✅ **Testing Scenarios** - Working examples with real conversations

## 🧪 Testing Scenarios

**Scenario 1: High-Quality Lead**
- Premium buyer with $600k+ budget, immediate timeline, specific requirements
- Expected: A-grade scoring, premium agent assignment, property suggestions

**Scenario 2: Lead Qualification Flow**  
- AI assistant conducts natural conversation to collect all required data
- Expected: Complete data collection, lead scoring, agent assignment

**Scenario 3: Agent Coordination**
- Agent receives lead notification and provides property recommendations
- Expected: Property suggestions forwarded to lead, viewing coordination initiated

---

**Generated with:** N8N Workflow Automation Platform  
**AI Model:** OpenAI GPT-4  
**Integration APIs:** Google Sheets, Twilio WhatsApp Business  
