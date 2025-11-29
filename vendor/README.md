# Vendor Folder (`vendor`)

This folder is the "pantry" for your project. It contains all the actual PHP code for every third-party dependency your project needs to run.

**CRITICAL: You should almost never edit any files in this directory by hand.** This entire folder is managed automatically by Composer.

### What's Inside?

*   **Drupal Core:** The code for Drupal itself lives in `vendor/drupal/`.
*   **Contributed Modules & Themes:** When you run `ddev composer require drupal/pathauto`, the code for the Pathauto module is downloaded and stored in here.
*   **PHP Libraries (Dependencies):** Drupal is built on top of many other open-source libraries (like Symfony, Twig, and Guzzle). The code for all of these foundational libraries is also stored here.

### How It Works: A Visual Guide

This diagram shows how Composer uses your `composer.json` file to build the `vendor` directory.

```
+--------------------------+
|                          |
|  `composer.json`         |
|  (The "Shopping List")   |
|   - drupal/core          |
|   - drupal/gin           |
|   - drupal/webform       |
|                          |
+------------|-------------+
             |
             | 1. `ddev composer install` reads the list
             v
+--------------------------+
|                          |
|  Composer                |
|  (The "Shopper")         |
|                          |
+------------|-------------+
             |
             | 2. Downloads all packages from the internet
             v
+--------------------------+
|                          |
|  `vendor/` Folder        |
|  (The "Pantry")          |
|   - /drupal/core/        |
|   - /drupal/gin/         |
|   - /drupal/webform/     |
|   - ...and all their     |
|     dependencies         |
+--------------------------+
```

### Why is this a good thing?

This approach separates the "code you own" (your custom themes and modules) from the "code you use" (Drupal core and contributed modules). This makes your project much cleaner, more reliable, and easier to update. Because all the contributed code is in one place, you can update everything with a single `ddev composer update` command, and you don't have to worry about accidentally modifying core files.
