# iOS Vibe Rules - BRAIN Network

> **Last Updated:** 2025-12-26 | **For:** SwiftUI, Swift 6, iOS 18+

## Golden Combo: LSP + Sosumi

For iOS/Swift: Use LSP for code navigation + Sosumi for Apple docs

LSP Operations: findReferences on @State, hover for types, goToDefinition

Sosumi: mcp__sosumi__searchAppleDocumentation, mcp__sosumi__fetchAppleDocumentation

## SwiftUI State

LSP findReferences on @StateObject → LSP outgoingCalls → LSP incomingCalls → Map flow

## Swift 6 Concurrency

Before actors: Sosumi search + LSP hover @MainActor + LSP findReferences

Common issues: @Published in actor WON'T WORK, use LSP to find access patterns

## Refactoring Swift

Safe rename: LSP findReferences → Present impact → Get approval → Rename → LSP verify

## Checklist

- LSP: No orphaned views
- Sosumi: API verified
- LSP: @MainActor annotations
- No circular deps (LSP)

---
**Mantra:** LSP precision + Sosumi correctness
