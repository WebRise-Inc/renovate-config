# WebRise Renovate configuration

`org-inherited-config.json` supplies defaults to WebRise-Inc repositories where the Mend Renovate GitHub App is installed.

## Update policy

- Process npm package files only.
- Disable dependency updates by default, then allow only `@webriseottawa/analytics`.
- Propose patch, minor, and major upgrades, including v2. Update the declared version range and associated lockfile.
- Keep automatic merging disabled.
- Disable independent lockfile-maintenance updates.
- Use shared configuration without requiring a separate onboarding config in every repository. Repositories without this dependency receive no package upgrade PR.

## Client rollout

Before merging the analytics v2 upgrade, configure and verify the client’s GTM container so GA4 and Microsoft Clarity initialize only after explicit analytics consent. Updating the package alone cannot change published GTM triggers.

## New repositories and overrides

New repositories inherit this policy when the Mend Renovate app can access them. Repository-level Renovate configuration can override inherited defaults; keep local rules consistent with the analytics-only policy.

The app must be installed on this configuration repository when this file is committed or changed. Mend detects that commit and enables inherited configuration for the organization.

## References

- [Mend inherited config](https://docs.renovatebot.com/mend-hosted/hosted-apps-config/#inherited-config)
- [Renovate configuration precedence](https://docs.renovatebot.com/config-overview/)
- [Package rules](https://docs.renovatebot.com/configuration-options/#packagerules)
