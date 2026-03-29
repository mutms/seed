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

2. Add any MuTMS plugins you want:

   ```bash
   composer require mutms/moodle-tool_muprog
   composer require mutms/moodle-tool_mucertify
   composer require mutms/moodle-tool_mutrain
   composer require mutms/moodle-tool_murelation
   composer require mutms/moodle-tool_musudo
   composer require mutms/moodle-tool_mupwned
   composer require mutms/moodle-tool_muloginas
   composer require mutms/moodle-tool_muhome
   composer require mutms/moodle-mod_mubook
   ```

   See [MuTMS project](https://github.com/mutms) page for a full list of available plugins.

3. Point your web server document root to `/var/www/mysite/moodle/public`, or create a symlink to serve it as a subdirectory of an existing web server:

   ```bash
   ln -s /var/www/mysite/moodle/public /var/www/html/mysite
   ```

4. Open your Moodle site in a web browser to complete installation. Composer will have already created `config.php` and set up the database during `create-project`. Visiting the site triggers Moodle upgrade to register any added plugins.

> **Note:** To skip the interactive installer, place a pre-configured `config.php` in the seed directory before running `composer create-project`. In this case database installation and plugin registration must be triggered manually by visiting the site or running the CLI installer.

## Update

To update Moodle and all installed plugins to their latest 5.1.x compatible versions:

```bash
cd /var/www/mysite
composer update
```

Then open your site in a web browser or run the CLI upgrade to apply any database changes.

## Add plugins to existing site

To add a new plugin to an existing site:

```bash
cd /var/www/mysite
composer update
composer require mutms/moodle-tool_muprog
```

Then open your site in a web browser or run the CLI upgrade to register the new plugin.

## Major version upgrade

To upgrade to Moodle 5.2 or later, switch to the corresponding MuTMS seed for that release. Migration instructions will be provided once Moodle 5.2 is released.

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
