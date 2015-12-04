npm-outdated(1) -- Check for outdated packages
==============================================

## SYNOPSIS

    npm outdated [[<@scope>/]<pkg> ...]

## DESCRIPTION

This command will check the registry to see if any (or, specific) installed
packages are currently outdated.

In the output:

* `wanted` is the maximum version of the package that satisfies the semver
  range specified in `package.json`. If there's no available semver range (i.e.
  you're running `npm outdated --global`, or the package isn't included in
  `package.json`), then `wanted` shows the currently-installed version.
* `latest` is the version of the package tagged as latest in the registry.
  Running `npm publish` with no special configuration will publish the package
  with a dist-tag of `latest`. This may or may not be the maximum version of
  the package, or the most-recently published version of the package, depending
  on how the package's developer manages the latest dist-tag(1).
* `location` is where in the dependency tree the package is located. Note that
  `npm outdated` defaults to a depth of 0, so unless you override that, you'll
  always be seeing only top-level dependencies that are outdated.
* `package type` (when using `--long` / `-l`) tells you whether this package is
  a `dependency` or a `devDependency`. Packages not included in `package.json`
  are always marked `dependencies`.

## CONFIGURATION

### json

* Default: false
* Type: Boolean

Show information in JSON format.

### long

* Default: false
* Type: Boolean

Show extended information.

### parseable

* Default: false
* Type: Boolean

Show parseable output instead of tree view.

### global

* Default: false
* Type: Boolean

Check packages in the global install prefix instead of in the current
project.

### depth

* Default: 0
* Type: Int

Max depth for checking dependency tree.

## SEE ALSO

* npm-update(1)
* npm-dist-tag(1)
* npm-registry(7)
* npm-folders(5)
