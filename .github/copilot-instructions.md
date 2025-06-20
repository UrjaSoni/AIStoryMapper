# copilot-instructions.md

## Project Purpose
This project processes raw meeting transcripts and notes from software development discussions, and extracts structured user stories, spikes (research tasks), and clarifying questions.

## Preferred Formats
User stories and spikes must follow this format:

---
**Title:** [Brief summary]  
**As a** [persona]  
**I want to** [goal]  
**So that** [value]  
**Description:** [Context or motivation]  
**Acceptance Criteria:**  
- [ ] ...  
- [ ] ...  
**Tags:** [Optional]  
**Clarifying Questions / Gaps:**  
- [ ] ...  
**Status:** Ready | Refinement  
---

## Special Instructions
- Extract only well-supported insights; avoid speculation.
- If a point is unclear, mark it as a Clarifying Question with a “Status: Refinement”.
- Use markdown formatting.
- In code, prefer modular parsing functions (e.g., `extract_user_stories()`, `classify_chunk()`).
- Support working with transcript files in `./transcripts/` directory.
- The main transcript is at `transcripts/customer-meeting.txt`.

## Preferred Terminology
- “Spike” means a research item.
- “Clarifying Question” means an incomplete or vague idea needing follow-up.
- The persona should reflect the speaker’s role: "PM", "Developer", "TPM", etc.

