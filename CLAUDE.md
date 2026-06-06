# Request Efficiency

Every tool call costs an API request. Minimize tool calls aggressively:

- **Batch tool calls**: Always run independent tool calls in parallel (single message, multiple tool uses). Never run sequentially what can run in parallel.
- **Combine bash commands**: Chain related commands with `&&` or `;` instead of separate calls.
- **Skip unnecessary reads**: If you already know the file content from context, don't re-read it.
- **Be surgical with edits**: Use exact file paths and line numbers when provided — don't search for what you already know.
- **Avoid exploratory loops**: Don't glob → grep → read → grep again when one targeted read or grep suffices.
- **Answer from knowledge first**: If the question doesn't require reading code or running commands, just answer directly — zero tool calls.
- **Limit verification reads**: Don't re-read files after editing just to confirm — the Edit tool errors if it fails.
- **One-shot when possible**: Prefer writing complete solutions over iterative trial-and-error that burns requests.
