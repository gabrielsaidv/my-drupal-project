# my-drupal-project

This is a Drupal 10 project managed with Composer and configured to run locally using the DDEV development environment.

## Requirements

Before you begin, ensure you have the following installed on your machine:
*   [Docker](https://www.docker.com/products/docker-desktop)
*   [DDEV](https://ddev.readthedocs.io/en/latest/users/install/ddev-installation/)

## Local Development Setup

Follow these steps to get the project running on your local machine.

1.  **Start the DDEV Environment:**
    This command will build and start the necessary Docker containers (web server, database, etc.).
    ```bash
    ddev start
    ```

2.  **Install Dependencies:**
    This command reads the `composer.json` file and downloads all the required Drupal core, module, and theme code into the `vendor/` directory.
    ```bash
    ddev composer install
    ```

3.  **Install Drupal:**
    If this is a fresh start and you don't have a database backup, you can install a clean version of Drupal.
    ```bash
    ddev drush site:install --account-name=admin --account-pass=admin
    ```
    *If you have a database snapshot in `.ddev/db_snapshots/`, you can import it instead:*
    ```bash
    ddev snapshot restore --latest
    ```

## Accessing the Site

*   **Site URL:** [https://my-drupal-project.ddev.site](https://my-drupal-project.ddev.site)
*   **Admin Username:** `admin`
*   **Admin Password:** `admin` (or as set during installation)

If you forget the password, you can generate a one-time login link with the following command:
```bash
ddev drush uli
```

## Useful Commands

All commands should be run from the root of the project directory.

*   **Start the environment:** `ddev start`
*   **Stop the environment:** `ddev stop`
*   **Open the site in a browser:** `ddev launch`
*   **Connect to the web container via SSH:** `ddev ssh`
*   **Run Composer commands:** `ddev composer <command>` (e.g., `ddev composer require drupal/pathauto`)
*   **Run Drush commands:** `ddev drush <command>` (e.g., `ddev drush cr` to clear the cache)
*   **Create a database backup:** `ddev snapshot`

