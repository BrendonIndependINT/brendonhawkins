

## **Project Outline**

This project started when I realised that the systems lens that I was applying to values alignment was a product of my own worldview. I wanted to understand what aspects of how I construct reality led me to thinking the way that I think. So, I approached it the way that I would any intelligence problem: by systematically looking at the information available and stepping it up through processing layers until it was in a condition suitable for analysis. I then analysed the individual elements and brought it together into a final report.

Choosing the corpus of information was an easy decision. I had years of archived conversations with Chat GPT which contained rich rambling conversations about a range of topics which contained worldview-relevant information. It was structured in JSON and I’d previously indexed the data in a database with thematic categories extracted by an LLM. It was set up as an MCP server which I could use with Claude Desktop.

Through some research and conversations with LLMs I settled on 12 worldview categories and built out a process to for analysis. I coded it up and tested it on small samples, then vibe coded a more robust system in Cursor which could perform analysis across all the conversations. The whole production run cost about $30 in API credits.

The output was incredible. I can’t share it, it’s too personal. It told me things about the way that I approach the world, where I’m coherent, and where I’m conflicted. I would love to develop it out into a more robust tool in the future, if anyone has any interest in giving me a hand, please let me know.

## **Core Project Architecture**

### **Data Foundation:**
- Started with 700+ exported ChatGPT conversation files (processed from JSON exports)
- Raw conversations stored in PostgreSQL database with structured conversation and message tables
- Chat processor (`chat_processor.py`) handles conversation parsing and database ingestion
- Database connection managed through dedicated connector (`db_connect.py`)

### **Analysis Pipeline:**

1. **Conversation Processing & Categorization**
   - `categorize_conversations.py` - Classifies conversations into thematic categories using Gemini API
   - `summarize_conversations.py` - Generates conversation summaries
   - Uses Google's Gemini models (2.0-flash for efficiency, 2.5-pro for complex reasoning)

2. **Worldview Extraction Layer**
   - **Core Engine**: `process_worldview.py` - Extracts worldview fragments from individual conversations
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
   - `process_worldview.py --month YYYY-MM` Monthly aggregation of individual conversation worldviews
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
  
### **Analysis Outputs**

The system has successfully produced:
- **731 individual conversation worldview extractions**
- **12 comprehensive category analysis reports**
- **Final integrated worldview report** (3,600 words)
      - *EXECUTIVE SUMMARY* (2-3 paragraphs): Overview of worldview evolution, key patterns, and significance
      - *CORE THEMES* (List): Major themes that cut across multiple categorie
      - *EVOLUTION PATTERNS* (2-3 paragraphs): How the worldview has developed over time
      - *STABLE FOUNDATIONS* (list): Core beliefs and patterns that remained consistent
      - *EMERGENT DEVELOPMENTS* (list): New themes and developments that appeared
      - *INTEGRATION INSIGHTS* (2-3 paragraphs): How different worldview components relate to each other
      - *WORLDVIEW COHERENCE* (2-3 paragraphs): The level of coherence of the user's worldview
      - *FUTURE TRAJECTORIES* (2-3 paragraphs): Where this worldview might be heading
      - *WORLDVIEW ELEMENTS* (1-2 paragraphs each): Synthesis of each of the 12 worldview elements

## **Limitations**
1.	Corpus Selection: The Chat GPT conversations were fantastic because they were rich, raw, and varied. However, they suffered from being influenced by how I interact with LLMs and that I don’t discuss huge parts of my social and personal life with LLMs.
Remedy: Include an interview style process in the future. Include other text sources.

2.	Worldview Categories: I know enough about worldview to be dangerous but am not an expert. The categories and their definitions were created by my research and conversations with LLMs. I think I covered it reasonably well, but it the categories need to be more robust if I am to put this out for public use.
Remedy: Find a philosopher and build out a better template. I hear you can find them in poorly lit pubs.

3.	Vibe coding: I don’t have the skill to build production systems. I can do analysis fine, but at a certain level of complexity I’m getting an LLM to do the coding for me. This works if all I’m doing is exploring something of my own and I understand the limitations. It isn’t good enough if I want to push this out as a tool to the general public.
Remedy: Get funding, hire a software developer. They could probably polish this in a few weeks.

## **Novel Features of This Approach**
*Note: This list was generated by an LLM. I can't write this sort of thing ahout my own work so handed it over to a more neutral observer.*

1. **Systematic Worldview Extraction** - Unlike typical conversation analysis that focuses on topics or sentiment, this extracts deep structural elements of worldview (fundamental assumptions about reality, knowledge, values, and agency).
2. **12-Category Philosophical Framework** - A comprehensive taxonomy covering ontology, epistemology, axiology, agency, time, scale, system logic, change theory, legitimacy, moral status, metaphors, and pathology - capturing the philosophical foundations that shape all thinking.
3. **Temporal Evolution Tracking** - Tracks how worldview elements change and develop over time, revealing intellectual development patterns that would be invisible in snapshot analysis.
4. **AI-Assisted Self-Analysis at Scale** - Uses LLMs for systematic philosophical self-examination across hundreds of conversations, moving beyond typical productivity or entertainment applications.
5. **Intelligence Analysis Methodology Applied to Personal Data** - Treats personal conversations like intelligence data, applying systematic categorization, synthesis, and pattern recognition techniques to self-knowledge.
6. **Values-Aware Systems Integration** - Connects personal worldview analysis to systems design, using self-understanding to inform how to build better, more human-centric systems.
7. **Coherence and Conflict Detection** - Identifies internal contradictions and trade-offs within worldview elements, enabling targeted personal growth and development.
8. **Community Aggregation Potential** - Framework designed to scale from individual analysis to community-level worldview mapping, enabling understanding of collective value systems.
9. **Low-Cost, High-Insight Production** - Achieved sophisticated analysis with minimal resources ($30 in API credits), making deep self-analysis accessible and practical.
10. **Structured Output with Validation** - Generates comprehensive reports with quality controls, ensuring meaningful insights rather than random AI-generated content.


## **Where to from Here?**

This is a project that has enormous potential. I'm going to need collaborators if I want to take it further:
1.	Individuals can come to understand their own worldview. This is an essential first step before building an appreciation that some people think differently from themselves.
2.	Individual worldviews can be used to understand why people take different approaches to solving problems. For example, an epistemic view that knowledge flows from evidence will produce different conclusions than one that states that knowledge is established by authority figures.
3.	Individuals can test their own worldviews for internal coherence and consistent application. By diagnosing fault lines, we can work on personal growth to gently nudge our personal worldview elements.
4.	Worldview can be aggregated across communities. This then informs values and goals and descries how we build common understanding of reality across a society.
5.	There is also the possibility of intentionally engineering a personal or collective worldview. This is the ultimate systems leverage point. I’m not sure how comfortable I am with this… But if you flip the focus, you may be able to diagnose how others are shaping individuals to serve their ends.

