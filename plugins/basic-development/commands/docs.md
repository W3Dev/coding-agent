# /docs - Look up library documentation

Look up documentation for any library or framework using Context7 and provide relevant examples.

## Usage

```
/docs <library-name> [query]
```

## Examples

```
/docs react hooks
/docs next.js authentication
/docs express middleware
```

## Behavior

1. Resolve the library name to a Context7 library ID
2. Query the documentation with the provided query
3. Return relevant documentation snippets and code examples
4. If helpful, supplement with real-world examples from GitHub

## Arguments

- `library-name` (required): The name of the library to look up
- `query` (optional): Specific topic or feature to search for
