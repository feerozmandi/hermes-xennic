User: Ahmad Firouzmandi (احمد فیروزمندی), B.Sc. Electrical Power Engineering. Founder of Zar Noor Niroo Yekta company, registration in progress.
§
Obsidian vault for Zar Noor Niroo Yekta docs: F:/ahmad/obsidian/xennic/xennic. All company actions documented here.
§
Obsidian vault path: F:/ahmad/obsidian/ZNNY-Xennic-Vault (not xennic/xennic). MCP server configured for this vault with tool sets: notes_write, vault_analysis.
§
When a file the user references isn't at the assumed path, search across all locations BEFORE declaring it missing — use `find` on parent directories, not just the expected path.
§
Xennic infrastructure: n8n localhost:5678 (v2.42.6), Open Notebook localhost:5055 (v1.15.0), Qdrant localhost:6333 (v1.18.3), E5-large TEI localhost:8001 (1.9.4). RAG collection: xennic_shared_knowledge (1024d, Cosine). Webhook search: localhost:5678/webhook/search?query={q}&limit=5. Obsidian vault: F:\ahmad\obsidian\ZNNY-Xennic-Vault (Git dev, obsidian-git backup every 10 min). MCP: obsidian (42 tools), n8n-official (51 tools). Rules: docs in 00_Meta/Integration/, use node-template.md for nodes, Webhook GET for Persian (not MCP tool_call), custom skills: xennic-node-developer, xennic-documentation.