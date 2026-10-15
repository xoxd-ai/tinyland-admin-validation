# tinyland-admin-validation (RETIRED)

**Retired 2026-10-14 (uplift wave U2, rulings RU2/RU7/RU8). This repository is archived and read-only.**

`@tummycrypt/tinyland-admin-validation` held Zod schemas and validators for admin
user records (`adminUserSchema`, `createAdminUserSchema`, `updateAdminUserSchema`,
`adminActivityLogSchema`, `validate*`, `sanitizeAdminUser`).

## Why it was retired

No live app or registry module consumes it. A code search across `xoxd-ai` and
`Jesssullivan` on 2026-10-14 found no import of the npm package and no
`bazel_dep(name = "tummycrypt_tinyland_admin_validation", ...)` outside this
repository and its own registry entries. The only other copy was the
`packages/tinyland-admin-validation` workspace in `xoxd-ai/tinyland.dev`, which is
being removed during the monorepo decomposition.

## What to use instead

- Admin role and permission vocabulary (`ADMIN_ROLES`, `AdminRole`,
  `AdminPermission`): use `@tummycrypt/tinyland-auth`, consumed as the Bazel module
  `tummycrypt_tinyland_auth` from
  [xoxd-ai/bazel-registry](https://github.com/xoxd-ai/bazel-registry). This package
  only mirrored that vocabulary.
- Admin user request schemas: there is no replacement module. Define them in
  the app that owns the admin surface.

## Distribution

- Bazel registry: `tummycrypt_tinyland_admin_validation` 0.2.2 and 0.2.3 stay
  resolvable in `xoxd-ai/bazel-registry` and are marked `deprecated`. Nothing is
  yanked.
- npm: no new versions will be published. Existing npmjs versions stay
  installable (nothing is unpublished) and are marked deprecated as an
  operator step.
- Tags `v0.1.0`, `v0.2.0`, `v0.2.2` and `v0.2.3` are kept.
