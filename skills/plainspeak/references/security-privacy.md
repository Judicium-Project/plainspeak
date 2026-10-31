# Security and privacy checklist

Use this for any app that handles user data, accounts, uploads, payments, or secrets.

## Secrets
- Never put API keys or secrets in client code, repos, or logs.
- Load secrets from environment variables or a secret manager.
- Disable debug mode in production.

## Access
- Protect admin routes. Enforce authentication where required.
- Check authorization on every privileged action, not just in the UI.
- Validate database permissions and security rules.

## Input and output
- Validate and sanitize all user input on the server.
- Prevent XSS: escape output and avoid unsafe HTML injection.
- Prevent SQL injection: use parameterized queries.
- Secure file uploads: check type and size, store outside the web root, and rename files.

## Transport and cookies
- Use HTTPS in production.
- Set secure, httpOnly, and sameSite flags on cookies.
- Add CSRF protection to state-changing requests.
- Set CORS to a specific origin list, not `*` on credentialed routes.
- Add security headers: Content-Security-Policy, Strict-Transport-Security, X-Content-Type-Options, Referrer-Policy.

## Abuse
- Rate-limit login, signup, password reset, and other abuse-prone endpoints.
- Set spend limits on paid APIs.

## Personal data
- Before collecting personal data, state the legitimate purpose.
- Disclose what is collected, why, how it is used, who receives it, how long it is kept, and how users exercise their rights.
- Provide a privacy policy where the law requires one.
- Provide a data deletion or access request path where it applies.
- Get consent for non-essential cookies and tracking where the law requires it.
- Ask the user whether personal data should be encrypted at rest.

## Reporting
- When you are not sure whether a regulation applies, say so and name the regulation to check. Do not give legal conclusions as fact.
