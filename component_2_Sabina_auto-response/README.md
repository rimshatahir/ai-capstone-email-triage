# Auto Response Drafting

**Owner:** Sabina Ruzieva

## Description

This component creates a Flowise LLM chain that generates draft responses for common email categories, including FAQ answers, complaint acknowledgments, and request-for-information replies. An n8n workflow sends generated drafts to a review queue in Airtable so a human can approve, edit, or reject them before sending.

## Tools

- Flowise (LLM chain builder)
- Groq API or Hugging Face text generation API
- n8n (workflow to send drafts to review queue)
- Airtable (response drafts table)

## Status

- [ ] Design complete
- [ ] Flowise chain configured
- [ ] Category-specific prompt templates created
- [ ] n8n review queue workflow built
- [ ] Testing with sample classified emails
- [ ] Integration with other components
- [ ] Documentation complete