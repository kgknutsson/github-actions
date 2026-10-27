# github-actions
Reusable GitHub Actions

## gitops-apply-terraform

Pass `client_id`, `subscription_id`, `tenant_id`, `tf_storage_account`, and `environment`.
A file named `<environment>.tfbackend` replaces the fallback state key.
Do not put a real resource name in the fallback key.

## Public content

Do not add organization names, product names, host names, tenant ids, or subscription ids to files.
A guard workflow scans each push.

Set repository variable `PUBLIC_REPO_DENYLIST` under **Settings → Secrets and variables → Actions → Variables**.
Use one term per line. Repo admins can view and edit this variable.
For local commits, set `DENYLIST_FILE` to a path outside the repository and run `.githooks/pre-commit`.
The guard loads the list through the GitHub API when possible. Otherwise it uses the masked repository secret `PUBLIC_REPO_DENYLIST`.

When you change the repository variable, update the repository secret with the same value. Example:

`gh secret set PUBLIC_REPO_DENYLIST -R kgknutsson/REPO --body "$(gh variable get PUBLIC_REPO_DENYLIST -R kgknutsson/REPO)"`
