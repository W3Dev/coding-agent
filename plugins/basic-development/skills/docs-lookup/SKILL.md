# Docs Lookup Skill

Use this skill when the user asks to look up documentation, find examples, or learn about a library/framework.

## When to Use

- User asks "how do I use X library?"
- User wants to find documentation for an API
- User needs code examples for a specific framework
- User asks about best practices for a technology

## Instructions

1. First, use the `mcp__context7__resolve-library-id` tool to find the library ID
2. Then use `mcp__context7__query-docs` to get relevant documentation
3. If the user needs real-world code examples, use `mcp__grep__searchGitHub` to find patterns
4. For questions about GitHub repositories, use `mcp__deepwiki__ask_question`
5. For general web searches or current information, use `mcp__exa__web_search_exa`

## Example Workflow

When user asks: "How do I set up authentication in Next.js?"

1. Resolve library: `context7.resolve-library-id("next.js", "authentication setup")`
2. Query docs: `context7.query-docs("/vercel/next.js", "authentication setup middleware")`
3. Find examples: `grep.searchGitHub("getServerSession", language=["TypeScript"])`
