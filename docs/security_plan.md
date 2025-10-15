# Security & Secrets Plan (AICraftr)

## 1. Secret Classes
- Local dev: .env (gitignored), OS keychain optional
- Staging/Prod: Cloud Secret Manager (GCP) / AWS Secrets Manager
- CI/CD: GitHub Actions OIDC + env vars from Secret Manager

## 2. Rotation Policy
- Refresh tokens rotated every 30 days
- Immediate rotation on suspected leak
- Principle of least privilege for all tokens

## 3. Storage & Access
- Developers: local `.env` only
- Runners/containers: inject at runtime from secret manager
- No secrets in code, logs, or READMEs

## 4. Auditing & Monitoring
- Log only redacted tokens
- Access logs enabled in Secret Manager
- Quarterly review of secret inventory

## 5. Incident Response
- Kill switch: `AUTO_PUBLISH=false`
- Revoke compromised tokens
- Post-incident retrospective & hardening
