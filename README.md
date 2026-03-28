# MuTMS Seed

A Composer project template to seed a new Moodle LMS site with MuTMS plugins.

> **Note:** Multi-tenancy is not supported in this seed. For a multi-tenant setup, please refer to the [MuTMS documentation](https://docs.mutms.org).

## Requirements

- [Composer dependency manager](https://getcomposer.org)
- All standard Moodle requirements — see [Moodle release notes](https://moodledev.io/general/releases)

## New site installation

1. Create a new project from the seed template:

   ```bash
   cd /var/www
   composer create-project mutms/seed mysite
   cd mysite
   ```

   Composer will install Moodle and all required plugins under `moodle/`.

2. Add any MuTMS plugins you want, for example:

   ```bash
   composer require mutms/moodle-tool_muprog
   ```

   See [Optional plugins](#optional-plugins) below for the full list.

3. Run the update to install the required plugins:

   ```bash
   composer update
   ```

4. Point your web server document root to `/var/www/mysite/moodle/public`.

## Upgrade

```bash
cd mysite
composer update
```

This updates Moodle and all installed plugins to their latest compatible versions.

## Optional plugins

| Package | Description |
|---|---|
| `mutms/moodle-tool_muprog` | Programmes |
| `mutms/moodle-tool_mucertify` | Certifications |
| `mutms/moodle-tool_mutrain` | Training credits |
| `mutms/moodle-tool_murelation` | Supervisors and teams |
| `mutms/moodle-tool_musudo` | Privileged sessions (sudo) |
| `mutms/moodle-tool_mupwned` | Compromised password blocking |
| `mutms/moodle-tool_muloginas` | Log-in-as via Incognito window |
| `mutms/moodle-tool_muhome` | Custom home pages |
| `mutms/moodle-mod_mubook` | Interactive book |

See [docs.mutms.org](https://docs.mutms.org) for full documentation on each plugin.

## Moodle version

This seed requires Moodle 5.1 or later.

---

Based on the [Moodle Seed](https://github.com/moodle/seed) project by Andrew Lyons.
