# MuTMS Seed for Moodle 5.1

A Composer project template to seed a new Moodle 5.1.x site with MuTMS plugins.

> **Note:** Multi-tenancy is not supported in this seed. For a multi-tenant setup, please refer to the [MuTMS documentation](https://docs.mutms.org).

## Requirements

- [Composer dependency manager](https://getcomposer.org)
- All standard Moodle 5.1 requirements — see [Moodle release notes](https://moodledev.io/general/releases#moodle-51)

## New site installation

1. Create a new project from the seed template:

   ```bash
   cd /var/www
   composer create-project mutms/seed mysite
   cd mysite
   ```

   Composer will install the latest stable Moodle 5.1.x release and all required plugins under `moodle/`.

2. Add any MuTMS plugins you want, for example:

   ```bash
   composer require mutms/moodle-tool_muprog
   ```

   See [Optional plugins](#optional-plugins) below for the full list.

3. Run the update to install the added plugins:

   ```bash
   composer update
   ```

4. Point your web server document root to `/var/www/mysite/moodle/public`.

## Update

```bash
cd /var/www/mysite
composer update
```

This updates Moodle to the latest stable 5.1.x release and all installed plugins to their latest compatible versions.

## Major version upgrade

To upgrade to Moodle 5.2 or later, switch to the corresponding MuTMS seed for that release. Migration instructions will be provided once Moodle 5.2 is released.

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

## Project structure

After installation, the `/var/www/mysite/` directory will contain:

| Path | Description |
|---|---|
| `composer.json` | Defines Moodle version and installed plugins. |
| `composer.lock` | Records exact installed versions. Do not edit manually. |
| `config.php` | Moodle site configuration created during installation. |
| `moodle/` | Moodle and all plugins installed by Composer. Do not edit directly. |
| `data/` | Suggested location for Moodle data directory. |
| `vendor/` | Composer dependencies. |

The seed is hosted at [github.com/mutms/seed](https://github.com/mutms/seed). If you need to customise the project template, fork the repository, clone your fork to the server, and run `composer install` instead of `composer create-project`.

---

Based on the [Moodle Seed](https://github.com/moodle/seed) project by Andrew Lyons.
