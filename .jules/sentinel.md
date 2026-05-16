## 2024-05-16 - Add CodeQL static analysis

**Vulnerability:** Lack of automated static analysis and security scanning (SAST) in CI/CD pipeline.
**Learning:** For a bare-bones repository like this, running CodeQL on javascript-typescript requires a source file. If no JS/TS files exist, CodeQL throws a fatal 'no-source-code-seen' error during dataset finalization.
**Prevention:** Always ensure a dummy source file (e.g., `src/index.ts`) is present when initially configuring CodeQL for JS/TS in empty or highly minimal repositories. Set `FORCE_JAVASCRIPT_ACTIONS_TO_NODE24: true` in the workflow environment to avoid Node 20 deprecation warnings.