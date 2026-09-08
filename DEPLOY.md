# Deployment Notes

Self-hosted CloudFlare-ImgBed (fork of MarSeventh/CloudFlare-ImgBed).

## Resources

| Resource | Name | ID |
|---|---|---|
| Worker | `imgbed` | — |
| D1 Database | `imgbed` | `97e2fac3-e80b-46f3-9a63-c58143494b19` |
| R2 Bucket | `imgbed` | — |
| KV Namespace | `imgbed` (unused, D1 preferred) | `7b2028bb2eae48848f07ab25745ff318` |

## Secrets (Actions)

- `CLOUDFLARE_API_TOKEN` — custom token (Workers Scripts / D1 / KV / R2: Edit)
- `CLOUDFLARE_ACCOUNT_ID`
- `D1_DATABASE_ID`
- `R2_BUCKET_NAME`
- `WORKER_NAME`

## Deploy

Auto-deploys on every push to `main` via `.github/workflows/deploy-worker.yml`.
Manual trigger: Actions → "Deploy to Cloudflare Workers" → Run workflow.

## Sync upstream

Use GitHub "Sync fork" → **Update branch** (never "Discard commits", it wipes local files).
