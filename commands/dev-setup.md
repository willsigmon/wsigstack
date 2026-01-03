## Legend
| Symbol | Meaning | | Abbrev | Meaning |
|--------|---------|---|--------|---------|
| → | leads to | | CI/CD | continuous integration/deployment |
| & | and/with | | cfg | configuration |
| w/ | with | | env | environment |

Execute immediately. Add --plan flag if user wants to see plan first.

Setup comprehensive dev env or CI/CD pipeline based on $ARGUMENTS.

Thinking flags (optional):
- --think→multi-tool env coordination
- --think-hard→complex CI/CD pipeline architecture  
- --ultrathink→enterprise dev infrastructure design

Examples:
- `/user:dev-setup --install --think` - Tool installation w/ dependency analysis
- `/user:dev-setup --ci --think-hard` - CI/CD pipeline w/ comprehensive workflow design
- `/user:dev-setup --monitor --ultrathink` - Complete observability infrastructure

--install flag:
- Install & cfg dev tools (Node.js, Git, Docker, DBs) | Setup IDE cfgs→consistent dev experience
- Create npm scripts→common tasks | Cfg pre-commit hooks→code quality | Setup linting & testing frameworks

--ci flag:
- Cfg CI/CD pipelines (GitHub Actions, GitLab CI, other platforms) | Setup build, test & deployment stages
- Cfg envs: dev, staging & prod | Add security scanning & dep checking | Setup deployment automation

--monitor flag:
- Cfg observability tools | Setup logging & monitoring | Add perf tracking
- Cfg error reporting | Setup alerts→critical issues

## Best Practices & Security

Ensure all cfgs follow security practices & include comprehensive docs.

Research requirements:
- Dev tools→C7 docs for installation & cfg patterns | CI/CD platforms→WebSearch platform-specific practices & guides
- Security tools→research OWASP & security scanning docs | Monitoring→check official observability platform docs
- Never cfg w/o docs - verify setup patterns | All cfgs cite sources: // Source: [setup guide ref]

Report Output:
- Setup logs: `.claudedocs/reports/dev-setup-<timestamp>.md`
- Cfg summaries: `.claudedocs/summaries/environment-config-<timestamp>.md`
- Ensure dirs: `mkdir -p .claudedocs/reports/ .claudedocs/summaries/`
- Include location: "📄 Setup report saved to: [path]"

Deliverables: Cfg scripts, CI/CD pipeline files, setup docs, env-specific cfgs & security validation report.