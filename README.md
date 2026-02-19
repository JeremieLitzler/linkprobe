# Dead Link Checker

A CLI tool to detect broken links on any website. Given a starting URL, it crawls all internal pages recursively, collects external links, checks their HTTP status codes, and outputs a CSV report.

## Features

- Recursive crawling of all internal links
- External links checked but not followed
- Visited URL tracking to prevent infinite loops
- Parallel HTTP requests for performance
- CSV output: `link, referrer, http_status_code`

## Usage

> The tool is under active development. Usage instructions will be added once the CLI is available.

## Output Format

Results are written to a CSV file with the following columns:

| Column             | Description                               |
|--------------------|-------------------------------------------|
| `link`             | The URL that was checked                  |
| `referrer`         | The page that contained the link          |
| `http_status_code` | HTTP response code (e.g. 200, 404, 500)  |

## Testing

A sample website is available to test the tool against:

```
https://deadlinkchecker-sample-website.netlify.app
```

## Development

This project uses a multi-agent pipeline powered by Claude Code. Describe a feature request or bug fix and the orchestrator coordinates specialist agents automatically.

| Agent         | Role                                          |
|---------------|-----------------------------------------------|
| Specification | Writes detailed specs from the user request   |
| Coder         | Implements the feature based on specs         |
| Tester        | Validates the implementation with tests       |
| Versioning    | Commits to a Git Flow branch and pushes       |

Human approval gates pause the pipeline after specs and after coding.

### Pipeline artifacts

```
.agents/
├── user-requests.md   # your input
├── specs.md           # specification output
├── code-ready.md      # coder output
├── test-results.md    # test output
└── status.md          # current pipeline stage
```

### Branch naming

| Change type | Branch prefix |
|-------------|---------------|
| New feature | `feature/`    |
| Bug fix     | `fix/`        |
| Docs only   | `docs/`       |

## License

See [LICENSE](LICENSE).
