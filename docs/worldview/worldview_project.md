# Personal Worldview Analysis System

## Full Project Description: Personal Worldview Analysis System

You've built a sophisticated multi-layered system to analyze your own worldview through extensive conversation data. This represents a unique approach to self-knowledge and intellectual development tracking.

### **Core Project Architecture**

**Data Foundation:**
- Started with 757+ exported ChatGPT conversation files (processed from JSON exports)
- Raw conversations stored in PostgreSQL database with structured conversation and message tables
- Chat processor (`chat_processor.py`) handles conversation parsing and database ingestion
- Database connection managed through dedicated connector (`db_connect.py`)

**Analysis Pipeline:**

1. **Conversation Processing & Categorization**
   - `categorize_conversations.py` - Classifies conversations into thematic categories using Gemini API
   - `summarize_conversations.py` - Generates conversation summaries
   - Uses Google's Gemini models (2.0-flash for efficiency, 2.5-pro for complex reasoning)

2. **Worldview Extraction Layer**
   - **Core Engine**: `worldview/process_worldview.py` - Extracts worldview fragments from individual conversations
   - **Template System**: 12-category worldview framework covering:
     - Ontology (what exists)
     - Epistemology (how knowledge is formed) 
     - Axiology (what is valuable)
     - Agency (who acts meaningfully)
     - Time, Scale, System Logic, Change Theory
     - Legitimacy, Moral Status, Metaphors, Pathology/Shadow
   - **Enforcement**: `enforced_output_spec.py` ensures consistent JSON output structure
   - **Quality Controls**: Minimum content thresholds, user vs. AI content filtering

3. **Temporal Synthesis**
   - Monthly aggregation of individual conversation worldviews
   - Cross-time pattern identification and evolution tracking
   - Synthesis using advanced Gemini 2.5-pro for complex reasoning

4. **Category Analysis**
   - `worldview_report.py` - Generates comprehensive category-by-category reports
   - Tracks evolution of each worldview component across time periods
   - Identifies stable foundations vs. emergent developments
   - Creates trend narratives with supporting evidence

5. **Final Integration**
   - `final_synthesis.py` - Combines all category analyses into comprehensive worldview report
   - Uses competitive process to synthesize key insights
   - Generates final markdown report with executive summary and detailed analysis

### **Key Innovation: Structured Worldview Framework**

Your system is built around a sophisticated 12-category worldview taxonomy that captures both philosophical foundations and practical orientations. This isn't just sentiment analysis or topic modeling - it's a systematic extraction of deep epistemological and ontological patterns.

### **Analysis Outputs**

The system has successfully produced:
- **731 individual conversation worldview extractions** (in `worldview/analysed/`)
- **12 comprehensive category analysis reports** (in `worldview/reports/`)
- **Final integrated worldview report** showing evolution from "philosophical observer" to "ethical systems architect"

### **Core Findings**

Your analysis revealed a clear intellectual evolution:
- **Initial Phase**: Broad diagnostic critique of societal systems
- **Middle Phase**: Synthesis around "systemic misalignment" as core diagnosis
- **Current Phase**: Identity as "Ethical Systems Architect" focused on building human-centric alternatives

The system identified consistent themes like systems thinking, dual-source epistemology (objective analysis + subjective experience), and rejection of incrementalism in favor of "greenfield" solutions.

### **Technical Stack**

- **Languages**: Python 3, JavaScript (some tooling)
- **Database**: PostgreSQL with JSONB for metadata
- **AI**: Google Gemini API (2.0-flash, 2.5-pro)
- **Architecture**: Modular pipeline with enforced data validation
- **Output**: Structured JSON → Markdown reports

This represents a sophisticated personal knowledge management and self-analysis system that goes far beyond typical conversation analysis - it's essentially a systematic approach to tracking philosophical and intellectual development over time using AI-assisted pattern recognition.

## Project Structure

```
mcp_ai/
├── worldview/                          # Main worldview analysis system
│   ├── process_worldview.py           # Core extraction engine
│   ├── worldview_report.py            # Category analysis generator
│   ├── final_synthesis.py             # Final report synthesis
│   ├── enforced_output_spec.py        # Data validation & structure
│   ├── worldview_elicitation_template.md  # 12-category framework
│   ├── analysed/                      # Individual conversation extractions (731 files)
│   ├── reports/                       # Category analysis reports (12 files)
│   └── final/                         # Final integrated reports
├── processed/                         # Raw conversation files (757 files)
├── chat_processor.py                  # Database ingestion
├── categorize_conversations.py        # Conversation categorization
├── summarize_conversations.py         # Conversation summarization
├── db_connect.py                      # Database connector
└── tools/                            # Supporting utilities
```

## Key Files

- **`worldview/worldview_elicitation_template.md`** - The foundational 12-category worldview framework
- **`worldview/process_worldview.py`** - Main extraction engine with month-by-month processing
- **`worldview/final_synthesis.py`** - Creates comprehensive final reports from category analyses
- **`worldview/final/worldview_report.md`** - The ultimate output: your complete worldview evolution analysis

## Running the System

The system processes conversations through several stages:

1. **Individual Extraction**: `python worldview/process_worldview.py --month 2025-04 --api-key YOUR_KEY`
2. **Monthly Synthesis**: `python worldview/process_worldview.py --month 2025-04 --api-key YOUR_KEY --synthesize`
3. **Category Analysis**: `python worldview/worldview_report.py --api-key YOUR_KEY`
4. **Final Report**: `python worldview/final_synthesis.py --api-key YOUR_KEY`

## Impact & Innovation

This project represents a novel application of large language models for systematic self-analysis and intellectual development tracking. By creating a structured framework for worldview extraction and applying it consistently across a large corpus of personal conversations, it enables unprecedented insight into philosophical and intellectual evolution over time.

The system goes beyond traditional text analysis by focusing on deep structural elements of worldview - the fundamental assumptions about reality, knowledge, values, and agency that shape all thinking and decision-making.
