# github-actions
Reusable GitHub Actions

## gitops-apply-terraform

Pass `client_id`, `subscription_id`, `tenant_id`, `tf_storage_account`, and `environment`.
A file named `<environment>.tfbackend` replaces the fallback state key.
Do not put a real resource name in the fallback key.

## Public content

Do not add organization names, product names, host names, tenant ids, or subscription ids to files.
A guard workflow scans each push.
The word list stays outside this repository.
