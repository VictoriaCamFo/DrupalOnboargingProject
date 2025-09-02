# Drupal Onboarding Project

Practice repository using **Drupal 10** and **Lando**.  
This repo includes basic site building tasks: URL alias patterns, a Projects listing page, and a “Latest Projects” sidebar block — all stored in configuration and versioned in Git.

---

## Requirements

- Docker + [Lando](https://lando.dev/) installed  
- [Composer](https://getcomposer.org/) 2.x  
- Git  

> **Note:** The local domain `drupalonboarding.lndo.site` is created by Lando and only works on your machine.

---

## Quick Start (first-time setup)

```bash
# Clone the repository (SSH recommended)
git clone git@github.com:YOUR-USERNAME/drupal-onboarding-project.git
cd drupal-onboarding-project

# Start containers (PHP, DB, etc.)
lando start

# Install PHP dependencies (creates /vendor)
lando composer install

# Install the site from exported configuration (uses config/sync)
# This creates the DB and imports all configuration automatically.
lando drush si --existing-config -y

# Clear caches and get a one-time admin login link
lando drush cr
lando drush uli
```
## Features
- **Project content type** with fields (Title, Body, Image, Tags)  
- Automatic Pathauto URL aliases → `/projects/[node:title]`  
- **Projects View**:
  - Page at `/projects` (teaser display)  
  - Block “Latest Projects” in the sidebar  
- SEO ready with **Metatag** module  
- Full configuration export in `config/sync`  
