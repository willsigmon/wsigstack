## Legend  
| Symbol | Meaning | | Abbrev | Meaning |
|--------|---------|---|--------|---------|
| → | leads to | | bld | build |
| & | and/with | | impl | implementation |
| w/ | with | | TDD | test-driven development |

@include shared/command-templates.yml#Command_Header

Build project/feature based on req in $ARGUMENTS.

@see shared/mcp-flags.yml ∀ MCP controls

Examples:
- `/user:build --react --magic` - React app w/ UI gen
- `/user:build --api --c7` - API w/ docs
- `/user:build --react --magic --pup` - Build & test UI

Pre-build: Remove artifacts (dist/, build/, .next/) | Clean temp files & cache | Validate deps | Remove debug

Build modes:
**--init:** New project w/ stack (React|API|Fullstack|Mobile|CLI) | TS default | Testing setup | Git workflow
**--feature:** Impl feature→existing patterns | Maintain consistency | Include tests  
**--tdd:** Write failing tests→minimal code→pass tests→refactor

Templates:
- **React:** Vite|TS|Router|state mgmt|testing
- **API:** Express|TS|auth|validation|OpenAPI  
- **Fullstack:** React+Node.js+Docker
- **Mobile:** React Native+Expo
- **CLI:** Commander.js+cfg+testing

**--watch:** Continuous build | Real-time feedback | Incremental | Live reload
**--interactive:** Step-by-step cfg | Interactive deps | Build customization

@see shared/research-first.yml ∀ research req

Workflow: Research→Setup→Impl→Test→Integrate

Deliverables: Working code, tests, docs, integration instructions.