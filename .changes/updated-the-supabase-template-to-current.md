---
type: changed
breaking: true
---
Changed the Supabase template to use Envoy, PostgreSQL 17, and RustFS

- Envoy serves HTTP on port 8000; its gateway does not provide Kong's HTTPS listener on port 8443
- The S3 backend now uses RustFS instead of Silo; objects in the previous storage volume are not copied automatically
- The S3 bucket can be configured with `GLOBAL_S3_BUCKET` and defaults to `stub`
- RustFS bucket initialization uses the container credentials, and optional SMTP/OpenAI settings default to empty
- Coolify's S3 storage and integrated log collection remain enabled
