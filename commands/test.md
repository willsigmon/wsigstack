## Legend
| Symbol | Meaning | | Abbrev | Meaning |
|--------|---------|---|--------|---------|
| → | leads to | | E2E | end-to-end |
| & | and/with | | MCP | model context protocol |
| w/ | with | | DB | database |

Execute immediately. Add --plan flag if user wants to see plan first.

Create or run comprehensive tests for code in $ARGUMENTS.

Thinking flags (optional):
- --think→multi-component test planning
- --think-hard→complex test arch & strategy
- --ultrathink→comprehensive test system design

MCP flags (optional):
- --pup→browser-based E2E testing w/ Puppeteer | --c7→testing framework docs
- --seq→complex test scenario planning | --no-mcp→native test runners only

Examples:
- `/user:test --e2e --pup --think` - E2E tests w/ Puppeteer & context analysis
- `/user:test --e2e --pw --think` - E2E tests w/ Playwright UI verification
- `/user:test --coverage --c7` - Test w/ framework docs support
- `/user:test --integration --seq --think-hard` - Complex test scenarios w/ deep planning

Pre-test cleanup:
- Clean test output dirs (coverage/, test-results/) | Remove test artifacts from previous runs
- Reset test DB/state→clean baseline | Clear test cache & temp files

When --coverage flag is present:
- Generate comprehensive coverage reports
- Identify untested code paths
- Aim for >80% code coverage
- Focus on critical business logic

When --watch flag is present:
- Set up automatic test execution on file changes
- Provide fast feedback during development
- Only run affected tests for efficiency
- Continuous integration during development

When --interactive flag is present:
- Interactive test runner with real-time feedback
- Allow test selection and filtering
- Step-through debugging for failing tests
- Live code coverage visualization

When --e2e flag is present:
- Create end-to-end tests for user flows
- Test critical paths through the application
- Include both happy paths and error scenarios
- Use appropriate E2E testing frameworks
- If --pw flag is present or UI verification is required, use Playwright:
  - Navigate key pages & critical flows
  - Capture snapshots/screenshots at key states
  - Check console for errors/warnings
  - Exercise core interactions (forms, navigation, modals)
  - Pause for user input when a decision is needed (auth, destructive action)

Test types to implement:
- Unit tests: Test individual functions, logic, and utilities in isolation
- Integration tests: Test APIs, services, and database interactions
- E2E tests: Test complete user workflows and critical paths

## Testing Best Practices

Follow testing standards:
- Use descriptive test names that explain what is being tested
- Follow AAA pattern: Arrange, Act, Assert
- Use appropriate mocking for external dependencies
- Create fixtures for consistent test data
- Ensure tests are independent and can run in any order

Research requirements for testing:
- Testing frameworks → C7 documentation lookup for framework-specific patterns
- Test patterns → Must verify with official testing guides and best practices
- E2E testing → WebSearch for accessibility and user experience standards
- Performance testing → Research benchmarking patterns for the specific stack
- Never implement test patterns without documentation backing
- All test implementations must cite sources: // Source: [testing guide reference]

Report Output:
- Coverage reports: `.claudedocs/metrics/coverage-<timestamp>.html`
- Test summaries: `.claudedocs/summaries/test-results-<timestamp>.md`
- Ensure directory exists: `mkdir -p .claudedocs/metrics/ .claudedocs/summaries/`
- Include report location in output: "📄 Coverage report saved to: [path]"

Deliverables: Comprehensive test suite, coverage reports, testing documentation, and test strategy guide.
