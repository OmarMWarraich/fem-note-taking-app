# Note-Taking App

A simple CLI and web-based note-taking application built with Node.js. Notes are stored in a local JSON file, and you can manage them via command-line or a minimal web interface.

## Features

- Add new notes with optional tags
- List all notes
- Search notes by content
- Remove notes by ID
- Remove all notes
- View notes in a web browser
- Persistent storage in `db.json`
- Fully tested with Jest

## Installation

1. **Clone the repository:**
	 ```bash
	 git clone <repo-url>
	 cd note-taking-app
	 ```

2. **Install dependencies:**
	 ```bash
	 npm install
	 ```

3. **(Optional) Set Node version using mise:**
	 ```
	 mise use node@18
	 ```

## Usage

### CLI

The CLI is available via the `note` command (see `package.json` bin config).

#### Commands

- **Add a new note:**
	```bash
	note new "Your note content" --tags tag1,tag2
	```
- **List all notes:**
	```bash
	note all
	```
- **Find notes by content:**
	```bash
	note find "search term"
	```
- **Remove a note by ID:**
	```bash
	note remove <id>
	```
- **Remove all notes:**
	```bash
	note clean
	```
- **Launch web interface:**
	```bash
	note web [port]
	# Default port is 5000
	```

### Web Interface

- Run `note web` to start a local server and open your notes in the browser.
- Notes are displayed with their content and tags.
- The HTML template is styled for clarity and simplicity.

## Data Storage

- Notes are stored in `db.json` as an array of objects:
	```json
	{
		"notes": [
			{
				"tags": ["tag1", "tag2"],
				"content": "hello world",
				"id": 1759801855498
			}
		]
	}
	```

## Testing

- Tests are written with Jest (see `tests/notes.test.js`).
- To run tests:
	```bash
	npm test
	```

## Project Structure

```
note-taking-app/
├── db.json                # Notes data storage
├── index.js               # CLI entry point
├── mise.toml              # Node version config
├── package.json           # Project metadata and scripts
├── src/
│   ├── commands.js        # CLI command definitions (yargs)
│   ├── db.js              # Database read/write helpers
│   ├── notes.js           # Note operations (CRUD)
│   ├── server.js          # Web server for notes
│   ├── template.html      # HTML template for web interface
│   └── utils.js           # Utility functions (e.g., listNotes)
└── tests/
		└── notes.test.js      # Jest tests for note logic
```

## Dependencies

- [yargs](https://www.npmjs.com/package/yargs) - CLI argument parsing
- [open](https://www.npmjs.com/package/open) - Open browser for web interface
- [jest](https://jestjs.io/) - Testing framework

## License

ISC

---


