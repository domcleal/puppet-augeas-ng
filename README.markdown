# puppet-augeas-ng: next generation Puppet-Augeas integration

This module is a development ground for the Augeas provider in Puppet.  It will
also bring changes being merged into master (i.e. the next Puppet release) to
existing versions of Puppet.

## Using puppet-augeas-ng

A new resource type will be provided, similar to the existing `augeas` type but
will add new features.

Change existing resource types from `augeas` to `augeasng` to take advantage of
the new providers.  The type parameters are all backwards-compatible, no more
changes are required.

## Issues

Please file any issues or suggestions on Github:
  https://github.com/domcleal/puppet-augeas-ng/issues
