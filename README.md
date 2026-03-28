# The Seed to grow your Moodle site with MuTMS plugins

This package can be used to install or upgrade a Moodle site with MuTMS plugins using Composer.

## New site installation

Requirements:

- PHP
- [Composer dependency manager](https://getcomposer.org)
- Standard Moodle requirements - see [Moodle release notes](https://moodledev.io/general/releases)

Installation steps:

1. Copy this seed project to your web server.
2. Add additional required plugins.
3. Start Composer installer.
4. Create Moodle config.php.

For example, if you want to use Programs:

```bash
git clone https://github.com/mutms/seed.git mysite
cd mysite

composer require "mutms/moodle-tool_muprog"

composer install
```

## Upgrade

Upgrade steps:

1. Run Composer update

For example:

```bash
cd mysite

composer update
```

---
This project is based on the Seed created by Andrew Lyons at https://github.com/moodle/seed.
