# POC MVP Document: Regulatory News Investment Analysis Platform

## Version 1

## Executive Summary

This document outlines the development of an automated investment analysis platform that monitors UK regulatory and stock news, identifies key corporate events through customizable keyword filtering, and performs comprehensive due diligence analysis using AI agents to support investment decision-making.

## System Overview

The platform consists of four main components:

1. **News Monitoring & Filtering System** (UK-focused)
2. **Data Collection & Processing Engine**
3. **AI Agent Analysis Framework**
4. **Decision Support Interface** (Single-user MVP)

## Functional Requirements

### 1. News Monitoring & Filtering System

**Core Functionality:**

- Real-time monitoring of UK regulatory news sources
- Customizable keyword/phrase filtering system
- Alert generation for matched criteria
- Expected volume: 25+ alerts per day

**Key Trigger Phrases/Events (User Customizable):**

- Delayed announcement dates
- Accounting date changes
- Director changes (appointments/resignations)
- Ownership changes (stake building/selling)
- Profit warnings/upgrades
- Strategic reviews
- M&A activity
- Regulatory investigations
- *User can add/modify/remove keywords and phrases*

**UK-Focused Data Sources:**

- London Stock Exchange RNS feed
- Companies House filings
- AIM company announcements
- UK financial news (Financial Times, Reuters UK, etc.)
- FCA regulatory announcements
- UK company investor relations pages

**Keyword Management Interface:**

- Add new keywords/phrases
- Edit existing trigger terms
- Enable/disable specific filters
- Set priority levels for different types of alerts
- Boolean operators for complex searches (AND, OR, NOT)

### 2. Data Collection & Processing Engine

**Automated Data Gathering:**
Upon user selection of a news item, the system automatically fetches:

- Annual reports and accounts (last 3-5 years) from Companies House
- Interim financial statements
- Director and management biographies
- Shareholder registers and ownership structures
- Corporate governance documents
- Historical RNS announcements
- Analyst reports and price targets (where available)
- Industry/sector reports

**Financial Processing:**

- Extract financial data from PDF documents using OCR/AI
- Normalize data into standardized formats
- Calculate key financial ratios and metrics
- Build historical trend analysis
- Generate UK peer comparison datasets

### 3. AI Agent Analysis Framework

**Agent Structure (as per attached configuration):**

**Research Phase:**

- **Researcher Agent**: Collects comprehensive company information
- Outputs: Financial data collection, industry competitive analysis, management governance analysis, liquidity risk assessment

**Analysis Phase:**

- **Victoria Clarke (Equity Analyst)**: Investment thesis and exit strategy analysis
- **Daniel Osei (Forensic Accountant)**: Financial due diligence and integrity review
- **Dr. Priya Deshmukh (Industry Specialist)**: Competitive and industry analysis
- **Louis Ramirez (Regulatory Analyst)**: Risk assessment and regulatory compliance
- **Sarah van Dijk (Corporate Lawyer)**: Management governance and legal analysis
- **Alexei Popov (Data Scientist)**: Quantitative models (not active in MVP but configured)

**Decision Phase:**

- **Richard Bernstein (Portfolio Manager)**: Final investment recommendation using Richard Bernstein persona and knowledge base

**Standard Agent Outputs:**

- `{company}_investment_thesis.md`
- `{company}_financial_due_diligence.md`
- `{company}_industry_competitive_analysis.md`
- `{company}_management_governance_analysis.md`
- `{company}_risk_assessment.md`
- `{company}_exit_strategy_liquidation_analysis.md`
- `{company}_decision_report.md`

### 4. Decision Support Interface (Single-User MVP)

**User Interface Components:**

- **News Dashboard**: Filtered alerts with keyword highlighting
- **Keyword Management Panel**: Add/edit/remove trigger phrases
- **Company Analysis Initiation**: "Get Additional Information" button with company context
- **Progress Tracker**: Real-time status of data collection and agent analysis
- **Report Viewer**: Sequential display of agent outputs
- **Decision Summary**: Final recommendation with reasoning
- **Simple Archive**: Access to completed analyses

## Technical Architecture

### Backend Systems

- **News Aggregation Service**: UK-focused real-time monitoring
- **Keyword Engine**: Flexible phrase matching with user configuration
- **Data Extraction Service**: UK Companies House API, PDF parsing, web scraping
- **Agent Orchestration Engine**: CrewAI-based sequential processing
- **Document Processing**: Automated financial data extraction
- **Database Integration**: Save all outputs to client database

### UK-Specific APIs and Integrations

- Companies House API
- London Stock Exchange data feeds
- FCA regulatory data
- UK financial news aggregators
- Morningstar UK data (if available)

### Data Flow

1. News monitoring → Keyword filtering → User alert
2. User selection → Data collection → Document processing
3. Agent sequential analysis → Report generation
4. Final decision → Database storage

## User Journey

1. **Alert Reception**: User receives UK news alert matching custom keywords
2. **Alert Review**: User sees highlighted keywords and company context
3. **Analysis Decision**: User clicks "Get Additional Information" for investigation
4. **Data Collection**: System gathers UK company data and filings
5. **Agent Processing**: Sequential agent analysis (researcher → analysts → decision maker)
6. **Progress Monitoring**: User tracks analysis completion status
7. **Report Review**: User reviews sequential agent outputs
8. **Final Decision**: Richard Bernstein agent provides investment recommendation
9. **Database Storage**: Complete analysis saved automatically

## MVP Scope and Limitations

**MVP Includes:**

- UK market focus only
- Single-user interface
- Customizable keyword/phrase filtering
- Core data collection from UK public sources
- Full agent analysis workflow (7 agents, 12 tasks)
- Sequential report generation
- Basic web interface
- Database integration for storage
- Expected 25+ daily alerts handling

**MVP Excludes:**

- Multi-user access and permissions
- Portfolio management system integration
- Real-time trading connections
- Advanced data visualization
- Mobile application
- Non-UK markets
- Historical data retention management
- Custom report formatting

## Success Metrics

- **Alert Relevance**: 80%+ of filtered alerts actionable for investment analysis
- **Data Collection Success**: 90%+ of required UK company data successfully gathered
- **Analysis Completion**: <2 hours from initiation to final decision report
- **System Reliability**: 95%+ uptime for news monitoring
- **User Satisfaction**: Effective keyword customization and clear decision outputs

## Technical Requirements

**News Monitoring:**

- Real-time UK regulatory feed processing
- Flexible keyword matching engine
- Alert prioritization and queuing
- 25+ daily alert capacity

**Data Collection:**

- Companies House API integration
- PDF document processing for annual reports
- Financial data extraction and normalization
- UK peer company identification

**Agent Framework:**

- CrewAI sequential processing
- Knowledge source integration (Richard Bernstein persona)
- Structured markdown output generation
- Error handling and retry logic

**User Interface:**

- Responsive web application
- Keyword management interface
- Progress tracking dashboard
- Report viewing system
- Simple, intuitive navigation

## Development Considerations

**Phase 1 (MVP)**:

- Core UK news monitoring with keyword filtering
- Basic agent analysis workflow
- Single-user web interface
- Database integration

**Future Phases**:

- Multi-user access control
- Additional market coverage
- Advanced analytics and visualization
- Mobile access
- Portfolio integration capabilities

## Risk Mitigation

**Technical Risks:**

- UK data source reliability → Multiple redundant sources
- Agent processing failures → Error handling and manual override
- Keyword false positives → User feedback loop for refinement

**Operational Risks:**

- High alert volume → Prioritization and filtering mechanisms
- Data quality issues → Validation and quality checks
- User adoption → Simple, intuitive interface design


