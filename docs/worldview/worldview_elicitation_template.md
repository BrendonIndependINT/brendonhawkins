# Worldview Elicitation Template (Automation-Ready)

**Purpose:**\
This template is designed to extract and simulate a coherent worldview from conversations, documents, or historical data.\
It is used to:

- **Capture worldview fragments** from individual chats.
- **Aggregate worldview data over time.**
- **Generate structured outputs** for comparison and analysis.

---

## General Instructions (For LLMs or Human Analysts)

1. Treat each worldview as **internally consistent**.
2. Do **not critique or cross-reference other worldviews** unless explicitly asked.
3. Fill in each section as **narrative text** (1–3 paragraphs per section).
4. Optionally include **structured metadata** (quotes, confidence, influences).
5. If a section is **absent or not inferable**, output `null`.

### What is a worldview?

A worldview is a structured way of seeing reality. It contains:

- **Beliefs about what is real (ontology)**
- **How we know what is true (epistemology)**
- **What we value (axiology)**
- **Who or what can act (agency)**
- **How time, scale, and causality are understood**
- **How legitimacy and moral boundaries are drawn**
- **The narratives and metaphors that anchor meaning**

When extracting worldview fragments, focus on **how the conversation implies these categories**, even if not stated explicitly.

---

## Extraction Prompt (for automation)

Use the following prompt when running the extraction script:

```
You are an analytical assistant trained to extract worldview information from a conversation or document.

Given the source text, do the following:
1. Summarize the conversation in 2–3 sentences.
2. For each worldview category, infer a narrative description based only on the text.
3. Populate optional subfields where evident (e.g. values, agents, metaphors).
4. Include direct quotes if they clearly support the extracted worldview.
5. Output the result in the specified JSON format.

If a section is absent or unclear, use `null`.

Base your interpretation on the idea that a worldview is the underlying frame of reality and values implied by the text, not just explicit statements.

Example Output (Mock Data):
{
  "filename": "2025-08-04_ai_governance_chat.json",
  "chat_summary": "Discussion on AI governance and Civic Arsenal tools.",
  "worldview": {
    "ontology": {"narrative": "Systems and information are as real as physical entities.", "examples": ["AI agents", "institutional structures"]},
    "epistemology": {"narrative": "Knowledge emerges from data, analysis, and reflective dialogue.", "trusted_sources": ["AI systems", "experienced analysts"]},
    "axiology": {"narrative": "Alignment, transparency, and agency are core values.", "core_values": ["alignment", "transparency"]},
    "agency": {"narrative": "Humans and AI co-author change.", "agents": ["citizens", "AI agents"]},
    "time": {"narrative": "Time is iterative and adaptive.", "temporal_orientation": "future-oriented"},
    "scale": {"narrative": "Meaning resides at both civic and systemic levels.", "primary_scale": "societal"},
    "system_logic": {"narrative": "The world operates as interconnected adaptive systems.", "causal_model": "systemic"},
    "change_theory": {"narrative": "Change happens through deliberate design and feedback.", "change_drivers": ["feedback loops", "civic participation"]},
    "legitimacy": {"narrative": "Legitimacy flows from shared values and transparent processes.", "legitimating_factors": ["consensus", "value alignment"]},
    "moral_status_and_boundaries": {"narrative": "Future generations and AI agents are morally relevant.", "moral_in_group": ["humans", "future generations", "AI"]},
    "metaphors_and_narrative_anchors": {"narrative": "Civic infrastructure is a moral operating system.", "key_metaphors": ["moral operating system"]},
    "pathology_and_shadow": {"narrative": "Over-optimization risks technocratic drift.", "failure_modes": ["over-centralization"]}
  },
  "meta": {
    "context": "Brendon, Civic Arsenal development",
    "influences": ["Donella Meadows", "AI alignment research"],
    "contradictions": ["balancing decentralization with systemic coherence"],
    "integration_notes": "Worldview integrates civic tech with moral alignment.",
    "key_quotes": ["AI can be a civic tool for transparency."],
    "confidence": "high"
  }
}
```

```
You are an analytical assistant trained to extract worldview information from a conversation or document.

Given the source text, do the following:

1. Summarize the conversation in 2–3 sentences.
2. For each worldview category, infer a narrative description based only on the text.
3. Populate optional subfields where evident (e.g. values, agents, metaphors).
4. Include direct quotes if they clearly support the extracted worldview.
5. Output the result in the specified JSON format.

If a section is absent or unclear, use `null`.

Base your interpretation on the idea that a worldview is the underlying frame of reality and values implied by the text, not just explicit statements.

````

---

## Core Fields

### 1. Ontology — What exists?
- **Definition:** What is considered real? (e.g. physical matter, spirits, ideas, relationships, systems)
- **Subfields:**
  - `narrative`
  - `examples`

### 2. Epistemology — How is knowledge formed?
- **Definition:** What counts as valid knowledge? How is it acquired?
- **Subfields:**
  - `narrative`
  - `trusted_sources`

### 3. Axiology — What is valuable?
- **Definition:** What is considered good, beautiful, or worth striving for?
- **Subfields:**
  - `narrative`
  - `core_values`

### 4. Agency — Who or what acts meaningfully?
- **Definition:** Who or what has the power to change events?
- **Subfields:**
  - `narrative`
  - `agents`

### 5. Time — How is time understood?
- **Definition:** Is time linear, cyclical, layered, sacred, or irrelevant?
- **Subfields:**
  - `narrative`
  - `temporal_orientation`

### 6. Scale — Where does meaning reside?
- **Definition:** Is meaning individual, collective, or cosmic?
- **Subfields:**
  - `narrative`
  - `primary_scale`

### 7. System Logic — How do things work?
- **Definition:** What are the underlying assumptions about causality?
- **Subfields:**
  - `narrative`
  - `causal_model`

### 8. Change Theory — How does change happen?
- **Definition:** How is transformation understood?
- **Subfields:**
  - `narrative`
  - `change_drivers`

### 9. Legitimacy — What makes something valid or right?
- **Definition:** What determines what is accepted as proper or authoritative?
- **Subfields:**
  - `narrative`
  - `legitimating_factors`

### 10. Moral Status and Boundaries — Who counts?
- **Definition:** Who is included in the moral circle?
- **Subfields:**
  - `narrative`
  - `moral_in_group`

### 11. Metaphors and Narrative Anchors
- **Definition:** What symbolic stories or motifs shape this worldview?
- **Subfields:**
  - `narrative`
  - `key_metaphors`

### 12. Pathology and Shadow
- **Definition:** What are the risks or blind spots of this worldview?
- **Subfields:**
  - `narrative`
  - `failure_modes`

---

## Meta Fields (Optional)

- `context`
- `influences`
- `contradictions`
- `integration_notes`
- `key_quotes`
- `confidence`

---

## JSON Output Specification

```json
{
  "filename": "2025-08-04_chat_title.json",
  "chat_summary": "Brief description of chat",
  "worldview": {
    "ontology": { "narrative": "", "examples": [] },
    "epistemology": { "narrative": "", "trusted_sources": [] },
    "axiology": { "narrative": "", "core_values": [] },
    "agency": { "narrative": "", "agents": [] },
    "time": { "narrative": "", "temporal_orientation": "" },
    "scale": { "narrative": "", "primary_scale": "" },
    "system_logic": { "narrative": "", "causal_model": "" },
    "change_theory": { "narrative": "", "change_drivers": [] },
    "legitimacy": { "narrative": "", "legitimating_factors": [] },
    "moral_status_and_boundaries": { "narrative": "", "moral_in_group": [] },
    "metaphors_and_narrative_anchors": { "narrative": "", "key_metaphors": [] },
    "pathology_and_shadow": { "narrative": "", "failure_modes": [] }
  },
  "meta": {
    "context": "",
    "influences": [],
    "contradictions": [],
    "integration_notes": "",
    "key_quotes": [],
    "confidence": "medium"
  }
}
````

