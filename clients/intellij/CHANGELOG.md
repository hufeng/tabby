## 0.5.0

### Incompatible Changes:

- Node.js version requirement is now v18+.
- System proxy environment variables are now ignored, including `http_proxy`, `https_proxy`, `all_proxy` and `no_proxy`. Before this change, proxy environment variables are processed, but requests will fail due to lack of supporting for https over http proxy and socks proxy.

### Fixes:

- Fixed a bug that causes auto-completion requests cannot be cancelled.
- Migrated Tabby cloud authorization tokens and anonymous usage tracking id from the old data directory to the new one.

## 0.4.0

### Features:

- Relocated the user data directory from `$HOME/.tabby/agent` to `$HOME/.tabby-client/agent` to avoid conflicts with Tabby server data. Note that the old data will not be migrated automatically. Please update the config file manually if you have made changes in the old path.
- Added a template config file for Tabby client agent located at `$HOME/.tabby-client/agent/config.toml`.
- Added check for Node.js installation and notify the user if it is not valid.
- Improved code suggestion filtering by indentation context. Suggestions now prioritize completing the current line or logic block, preventing excessively long suggestions.
- Added adaptive completion debouncing for auto-completion requests.
- Added timeout for auto-completion requests. The default timeout is 5 seconds. Added statistics for completion response time and notifies the user if it is too slow.

### Fixes:

- Fixed a bug that caused the plugin throw errors when initializing without user data file.

## 0.2.0

### Features:

- Added support for Tabby Cloud hosted server authorization.

### Fixes:
- Fixed inlay text rendering issues.

