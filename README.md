# oss-workflows

Shared GitHub Actions workflows for PruvoNet's **public** repos. Private repos use `PruvoNet/.github`, which public repos cannot call.

| Workflow | Use |
|---|---|
| `ci-node.yml` | Install, build and test a Node package on a Node × OS matrix (yarn, npm or pnpm) |
| `publish-npm.yml` | Publish to npmjs through npm trusted publishing (OIDC, no token) |
| `zizmor.yml` | Fail on any workflow security finding |

Callers pin a commit SHA (`uses: PruvoNet/oss-workflows/.github/workflows/ci-node.yml@<sha> # v1`); Dependabot keeps the pin current.

npm trusted publishing checks the **calling** workflow's filename, so the npm trusted publisher names the package repo's `publish.yml`, not `publish-npm.yml`.

Ticket: PRV-7340 / PRV-7914.
