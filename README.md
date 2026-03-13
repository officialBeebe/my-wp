# Getting started

I use **DDEV** to develop themes and plugins:

1. Navigate to the WordPress core.
2. Execute `ddev config` to configure a fresh development environment.
3. Once configured, edit a new `.ddev/docker-compose.mounts.yaml` file and [add the following block](https://stackoverflow.com/a/57432155) (using relative or absolute paths to map your monorepo clone):

```yaml
services:
  web:
    volumes:
      # Relative to the .ddev directory
      - /home/dylan/my-wp/themes/my-theme:/var/www/html/wp-content/themes/my-theme
```

4. Now execute `ddev start` and each specified theme or plugin will be available in the WordPress admin dashboard.

# Summary

This procedure describes a workflow for rapidly iterating on WordPress themes and plugins with minimal setup, utilizing **DDEV** and custom Docker overrides to create an ephemeral development environment and mount remote directories for the WordPress core to reference inside a Docker container.
