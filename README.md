# shpell

A spell check command for Claude Code using [typos-cli](https://github.com/crate-ci/typos).

## Install

```bash
claude plugin marketplace add brentgreeff/shpell
claude plugin install shpell@shpell
```

Or in Claude Code:
```
/plugin marketplace add brentgreeff/shpell
/plugin install shpell@shpell
```

Then restart Claude Code for the command to be available.

## Prerequisites

Install typos-cli:

```bash
brew install typos-cli
```

## Usage

```
/shpell [path]
```

Examples:
- `/shpell .` - Check entire project
- `/shpell src/` - Check src directory
- `/shpell README.md` - Check single file

## Features

- Prompts for path if not provided
- Identifies likely false positives (code terms, proper nouns)
- Offers to auto-fix real typos
- Suggests adding persistent ignores to `.typos.toml`
