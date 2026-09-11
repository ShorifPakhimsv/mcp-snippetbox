# mcp-snippetbox

MCP server template I base new tools on

Side project, maintained when I have time.

## Highlights

- Five tools: add / get / update / delete / list notes
- Includes a Claude Desktop config snippet with absolute paths
- Atomic saves (temp file + os.replace) behind a write lock
- Notes path set by MCP_NOTES_FILE or --notes-file
- A missing note raises instead of returning the string 'not found'
- Every tool carries a real docstring, so clients get descriptions

## Examples

```bash
# claude_desktop_config.json  (use ABSOLUTE paths: Claude does not
# run from the repo directory, so a bare "server.py" is not found)
# {
#   "mcpServers": {
#     "notes-box": {
#       "command": "python",
#       "args": ["/abs/path/to/mcp-snippetbox/server.py"],
#       "env": {"MCP_NOTES_FILE": "/abs/path/to/notes.json"}
#     }
#   }
# }
python server.py --help
```

## Installation

```bash
pip install -r requirements.txt
```

## Project structure

```text
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── configuration.md
│   ├── development.md
│   ├── faq.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── tests/
│   └── test_notes.py
├── .gitignore
├── CODE_OF_CONDUCT.md
├── LICENSE
├── SECURITY.md
├── requirements.txt
└── server.py
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT licensed, see LICENSE.
