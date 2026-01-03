# iOS API Integration Pattern

Implement secure API integration for iOS apps.

## Requirements:
- Use modern URLSession async/await
- Implement proper error handling
- Add retry logic with exponential backoff
- Secure credential storage (Keychain)
- Certificate pinning (if applicable)
- Request/response logging (debug only)
- Proper cancellation support

## Structure:
1. API client protocol
2. Live implementation
3. Mock implementation for testing
4. Error types
5. Response models (Codable)
6. Unit tests
