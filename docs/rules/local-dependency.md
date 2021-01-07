# Validates the casing for `file:` and `link:` dependencies in the `package.json` files (local-dependency)

Yarn allows developers to add local dependencies using `file:` or `link:` syntax. If the casing of these paths are incorrect yarn does
not sub out the link when releasing. Having an incorrect casing in the dependency path will cause errors
when your package is published but will go unnoticed when the package is running locally. The `local-dependency` rule goes through all
dependencies, peer dependencies, and dev dependencies checking all `link:`and `file:` paths for incorrect casing.

## Rule Details

This rule aims to ensure that `package.json` uses the correct 'link' and 'file' paths. Imagine this is
your file structure:

-   package.json
-   src
    -   Folder
        -   package.json
    -   AnotherFolder

This:

    ```json
    "devDependencies": {
            "some-package": "link:./src/folder",
    }
    ```

Should be:

    ```json
    "devDependencies": {
            "some-package": "link:./src/Folder",
    }
    ```

### Options

This rule has no options.
