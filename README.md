# apex-plugins

This repository contains a JSON directory of plugins for the Apex Markdown Processor. Users can browse available plugins and install them using `apex --list-plugins` and `apex --install-plugin <id>`.

## Adding a Plugin to the Directory

To add your plugin to the central directory:

1. **Fork** the `ApexMarkdown/apex-plugins` repository on GitHub to your own account or organization.

2. **Clone** your fork locally and create a new branch for your plugin entry (for example, `add-my-plugin`).

3. Open the `apex-plugins.json` file in the root of your fork and add a new object to the `plugins` array with the following fields:
   - `id` (must match the `id` in your plugin's `plugin.yml`)
   - `title`
   - `description`
   - `author`
   - `homepage`
   - `repo` (canonical Git URL for the plugin repository)

   Example entry:
   ```json
   {
     "id": "my-plugin",
     "title": "My Plugin",
     "description": "A brief description of what the plugin does.",
     "author": "Your Name",
     "homepage": "https://github.com/yourusername/apex-plugin-my-plugin",
     "repo": "https://github.com/yourusername/apex-plugin-my-plugin"
   }
   ```

4. Commit your changes and **push** the branch to your fork on GitHub.

5. From your fork, open a **pull request** against the `main` branch of `ApexMarkdown/apex-plugins`, briefly describing your plugin and confirming that the `id` and `repo` match your published plugin repository.

6. Once the pull request is reviewed and merged, your plugin will show up in `apex --list-plugins` and be installable via `apex --install-plugin <id>`.

## Plugin Requirements

Before submitting your plugin, ensure:

- Your plugin repository contains a `plugin.yml` manifest file at its root
- The `plugin.yml` includes at least `id`, `phase`, and either `handler.command` (for external plugins) or `pattern`/`replacement` (for declarative plugins)
- The `id` in `plugin.yml` matches the `id` in your `apex-plugins.json` entry
- Your plugin repository is publicly accessible via the `repo` URL

## More Information

For detailed information on creating plugins, including plugin manifest format, processing phases, external handler plugins, and declarative regex plugins, see the [Apex Plugins documentation](https://github.com/ApexMarkdown/apex/wiki/Plugins).
