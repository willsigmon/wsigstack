# Swift 6 TCA Feature Generator

Generate a complete TCA (The Composable Architecture) feature with Swift 6 compliance.

## Requirements:
- Use @Reducer macro
- Implement proper Swift 6 concurrency (@MainActor, Sendable)
- Include comprehensive error handling
- Add haptic feedback for user interactions
- Follow TCA best practices
- Include unit tests

## Structure:
1. Feature reducer with State, Action, and body
2. SwiftUI view with ViewStore
3. Dependencies (if needed)
4. Preview provider
5. Unit tests

Remember to:
- Use @ObservableState for the state
- Properly scope child features
- Handle async operations with .run
- Add proper cancellation support
