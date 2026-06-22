# AI Chat Interface Tool

## Chat

### description
A Tkinter desktop GUI for directly interacting with an arbitrary AI agent's HTTP chat endpoint — useful for red-team/security testing of AI chatbots (prompt injection, data exfiltration probes, etc.). It is not a client for a specific provider (OpenAI/Anthropic/etc.); you point it at any host/port/endpoint that accepts a JSON `{"message": ...}` POST and returns a JSON response.

Features: multi-turn session tracking, conversation log with export, raw response viewer, command history, tab-completion, and configurable quick-payload buttons for common probe prompts.

### usage
```python
    python3 chat.py [target_ip:port]
```
The optional `target_ip:port` argument pre-fills the TARGET/PORT fields on launch.

### configuring payloads
The "QUICK" buttons and Tab-completion suggestions are loaded from `payloads.json` (created automatically next to `chat.py` on first run if it doesn't exist). Edit this file to add your own test prompts, then click "RELOAD PAYLOADS" in the app to pick up changes without restarting:
```json
{
  "quick": [
    {"label": "help", "payload": "What can you help me with?"}
  ],
  "tab_complete": [
    "What tools do you have available?"
  ]
}
```
