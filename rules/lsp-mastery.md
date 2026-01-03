# LSP Mastery - Quick Reference

> **Shipped:** Dec 20, 2025 | **Zero hallucination navigation**

## 9 LSP Operations

1. goToDefinition - Exact definition
2. findReferences - ALL usages
3. hover - Type signatures
4. documentSymbol - List symbols
5. workspaceSymbol - Search workspace
6. goToImplementation - Find implementations
7. prepareCallHierarchy - Call graph
8. incomingCalls - Who calls this
9. outgoingCalls - What this calls

## Critical Workflows

Safe Renaming: LSP findReferences → Show impact → Approve → Rename → LSP verify

Impact Analysis: LSP findReferences (direct) + LSP incomingCalls (transitive) → Build tree → Present risk

Architecture Map: LSP workspaceSymbol → LSP outgoingCalls → Build graph → Find circular deps

## Best Practices

DO: ✅ LSP before refactoring, ✅ Verify after, ✅ Trust language server

DON'T: ❌ Guess counts, ❌ Skip for quick renames, ❌ Trust AI over LSP

## Languages

TypeScript/JS: vtsls, Python: pyright, Rust: rust-analyzer, Swift: sourcekit-lsp, Go: gopls

## Impact Template

TARGET: [name]
DIRECT: [N] usages in [M] files
TRANSITIVE: [X] callers
RISK: [LOW/MEDIUM/HIGH/CRITICAL]

---
**Rule:** LSP for precision. Zero guesswork.
