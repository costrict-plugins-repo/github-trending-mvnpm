---
name: mvnpm
description: Search and add NPM packages as Maven or Gradle dependencies. Use when the user wants to add an NPM/JavaScript package to a Java project, convert NPM package names to Maven coordinates, check Maven Central sync status, browse artifact contents, or generate ES module import maps.
---

# mvnpm - NPM packages as Maven dependencies

Use the mvnpm MCP tools to help users work with NPM packages in Java/Maven/Gradle projects.

## Available tools

- `search_packages` — Find NPM packages available through mvnpm
- `get_package_info` — Get full package metadata (licenses, dependencies, maintainers)
- `list_versions` — List all available versions including dist-tags (latest, next, etc.)
- `get_maven_coordinates` — Convert an NPM package name to Maven/Gradle dependency snippets
- `get_pom` — Generate the Maven POM XML for a specific package version
- `get_import_map` — Get an ES module import map JSON for a package
- `browse_artifact_contents` — Explore files inside JAR or TGZ archives
- `download_jar` — Download or create a JAR (this also triggers Maven Central sync)
- `check_sync_status` — Check if a package version has been synced to Maven Central
- `list_sync_pipeline` — View the sync pipeline stages and their status
- `get_event_log` — Access sync events and error logs

## NPM to Maven name mapping

- Non-scoped packages: `lit` becomes `org.mvnpm:lit`
- Scoped packages: `@hotwired/stimulus` becomes `org.mvnpm.at.hotwired:stimulus`
- The groupId is always under `org.mvnpm`

## Typical workflows

1. **Adding an NPM package to a Java project**: Use `search_packages` to find it, then `get_maven_coordinates` to get the dependency snippet for pom.xml or build.gradle
2. **Checking availability on Maven Central**: Use `check_sync_status` to see if the version is already synced
3. **Generating import maps**: Use `get_import_map` for projects using ES modules via importmap
4. **Exploring package contents**: Use `browse_artifact_contents` to see what files are in the JAR
