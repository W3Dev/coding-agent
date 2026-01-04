# /search-code - Find real-world code examples

Search for code patterns and examples from public GitHub repositories using Grep.

## Usage

```
/search-code <pattern> [--lang=<language>]
```

## Examples

```
/search-code "useState(" --lang=TypeScript
/search-code "async function" --lang=Python
/search-code "ErrorBoundary" --lang=TSX
```

## Behavior

1. Search GitHub repositories for the specified code pattern
2. Filter by programming language if provided
3. Return relevant code snippets with context
4. Provide repository links for further exploration

## Arguments

- `pattern` (required): The code pattern to search for (supports regex)
- `--lang` (optional): Filter by programming language (TypeScript, Python, Go, etc.)
