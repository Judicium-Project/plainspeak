# Code quality checklist

Use this when writing or reviewing code beyond a short snippet.

- Prefer simple, readable solutions. Avoid abstractions that only serve one caller.
- Keep functions and modules focused on one job.
- Share code when a clean shared version is clearly better. Do not force it.
- Do not optimize before there is a measured problem.
- Remove dead code in the area you change.
- Handle errors where they can be handled. Do not swallow them silently.
- Validate external and user-controlled input at the boundary.
- Do not add a dependency without a clear reason. Check that it exists and is maintained.
- Before calling an API, confirm it exists, read its request and response format, and check the required behavior.
- Keep exact identifiers, paths, URLs, error strings, and package names unchanged.
- Run the project's linter, type checker, tests, or build when available. Report what passed and what did not.
