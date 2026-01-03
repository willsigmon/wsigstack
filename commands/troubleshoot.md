## Legend
| Symbol | Meaning | | Abbrev | Meaning |
|--------|---------|---|--------|---------|
| → | leads to | | prod | production |
| & | and/with | | impl | implementation |
| w/ | with | | info | information |

Execute immediately. Add --plan flag if user wants to see plan first.

Troubleshoot & resolve issues in code or system in $ARGUMENTS.

Thinking flags (optional):
- --think→multi-component debugging w/ context
- --think-hard→complex system issues & race conditions
- --ultrathink→critical prod issues or elusive bugs

Examples:
- `/user:troubleshoot --investigate --think` - Debug w/ full context
- `/user:troubleshoot --five-whys --think-hard` - Deep root cause analysis
- `/user:troubleshoot --prod --ultrathink` - Critical prod debugging

Mode selection:

--investigate flag:
- Focus→understanding & analyzing issue | Use debugging tools & techniques→gather info
- Document findings w/o necessarily impl fixes | Useful→complex problems requiring deep analysis

--fix flag:
- Complete full bug-fixing workflow | Create tests, impl solution & verify resolution
- Document the fix and prevention measures
- Default mode if no flag specified

When --five-whys flag is present:
- Apply root cause analysis methodology
- Ask "why" iteratively to uncover underlying causes
- Document each level of analysis
- Propose systemic improvements to prevent recurrence

When --prod flag is present:
- Focus on production-specific issues
- Analyze logs, monitoring data, and metrics
- Consider performance and scaling factors
- Ensure minimal disruption to live services
- Implement safe rollout strategies

Comprehensive troubleshooting workflow:

1. **Reproduce & Understand**
   - Create minimal reproduction steps
   - Document expected vs actual behavior
   - Identify affected components and users
   - Determine severity and business impact

2. **Investigate & Isolate**
   - Use debugging tools and strategic logging
   - Apply binary search to narrow problem scope
   - Check recent changes (git blame/history)
   - Analyze logs, stack traces, and monitoring data
   - Rule out environmental factors

3. **Root Cause Analysis**
   - Identify the underlying cause, not just symptoms
   - Use five-whys technique if needed
   - Consider systemic issues
   - Document contributing factors

4. **Solution Development** (if --fix flag)
   - Create failing test that reproduces the issue
   - Implement minimal fix addressing root cause
   - Ensure backward compatibility
   - Consider edge cases and side effects

5. **Verification & Prevention**
   - Verify fix resolves the issue completely
   - Run full test suite for regressions
   - Test in realistic conditions
   - Add monitoring for early detection
   - Document lessons learned

Investigation techniques:
- Strategic logging and breakpoints
- Performance profiling for bottlenecks
- Memory analysis for leaks
- Network inspection for API issues
- Database query analysis

For production issues:
- Correlate with deployment timeline
- Check for traffic patterns
- Review configuration changes
- Analyze resource utilization
- Consider rollback if critical

Research before fixing:
- Search for known issues → WebSearch "[error message] [library version]"
- Check library bug trackers → C7 documentation for known problems
- Verify error patterns → Official troubleshooting guides required
- Framework-specific issues → Must check official documentation first
- Never assume root cause without researching similar cases
- Document all research sources in fix explanation

Report Output:
- Root cause analysis: `.claudedocs/incidents/rca-<timestamp>.md`
- Incident documentation: `.claudedocs/incidents/incident-<timestamp>.md`
- Investigation findings: `.claudedocs/reports/investigation-<timestamp>.md`
- Ensure directory exists: `mkdir -p .claudedocs/incidents/ .claudedocs/reports/`
- Include report location in output: "📄 Report saved to: [path]"

Deliverables: 
- For investigation: Root cause analysis, detailed findings report, recommended solutions
- For fix: Implemented solution with tests, prevention measures, incident documentation