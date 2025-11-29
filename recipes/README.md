# Recipes Folder (`recipes`)

This folder is part of a modern Drupal system that helps manage the initial setup and ongoing updates of your site's core components.

### What is a "Recipe"?

In Drupal, a **recipe** is a set of instructions that tells Composer what to do with a software package. It's more advanced than just downloading code. A recipe can:

*   Place files in specific directories (like putting Drupal's `index.php` in the `web/` folder).
*   Add lines to your `.gitignore` file.
*   Scaffold entire directory structures.

Essentially, recipes are the "assembly instructions" for your Drupal site. They take the raw code downloaded by Composer and arrange it into a working Drupal application structure.

### Key Files and Directories

*   `README.txt`
    *   **Purpose:** The default README file from the Drupal recipe system.
    *   **Details:** Provides a brief, official explanation of the directory's purpose.

### How It Works: A Visual Guide

This diagram shows the relationship between Composer, recipes, and your project structure.

```
+-----------------+      +-----------------+      +-----------------------+
|                 |      |                 |      |                       |
| `composer.json` |----->|  Drupal Recipes |----->|  Your Project Files   |
| (Lists packages)|      | (Instructions)  |      |  (Arranged correctly) |
|                 |      |                 |      |                       |
+-----------------+      +-----------------+      +-----------------------+

Example Flow:
1. `composer.json` says "we need `drupal/core`".
2. Composer downloads the `drupal/core` package.
3. The `drupal/core-recipe` is triggered.
4. The recipe copies the necessary files from the downloaded package into the correct locations, like `web/core/`.
```

You will rarely need to interact with this folder directly, but it's a crucial part of the underlying system that makes your modern Drupal project work so well.
