# Security Notes

## Token File Location

OAuth tokens are stored in `.tokens/tokens.json` by default.

**Important:** Ensure this path is excluded from any cloud sync tools:

- OneDrive: Add `.tokens/` to OneDrive's excluded folders list
- Dropbox: Add `.tokens/` to your Dropbox ignored paths
- iCloud: Keep the project folder outside of iCloud Drive

Never commit `.tokens/` or any `tokens.json` file to version control.

## Azure App Registration

This server uses a single-tenant Azure App Registration scoped to:

- Tasks.Read
- Tasks.ReadWrite
- User.Read

Do not expand these permissions. Do not change tenant type to multi-tenant.

## Token Lifetime

Refresh tokens expire after 14 days of inactivity and 30 days maximum.
Re-run `pnpm run auth` to re-authenticate when tokens expire.
