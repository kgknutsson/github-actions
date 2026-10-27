# github-actions
Reusable GitHub Actions

## gitops-apply-terraform

Pass `client_id`, `subscription_id`, `tenant_id`, `tf_storage_account`, and `environment`.
A file named `<environment>.tfbackend` replaces the fallback state key.
Do not put a real resource name in the fallback key.

## Public content

Do not add organization names, product names, host names, tenant ids, or subscription ids to files.
A guard workflow scans each push.

Keep private terms in `.denylist.local` in your clone. Put one term on each line. Git ignores that file.

Run this command once in each clone:

`git config core.hooksPath .githooks`

The pre-commit hook reads `.denylist.local` and scans staged files. If that file is missing, the hook fails.

The guard workflow on each push checks built-in patterns only. Those patterns are a GUID, an email address, an Atlassian site host, and the owner prefix. The workflow does not read the private word list.
