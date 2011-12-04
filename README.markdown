# puppet-augeas-ng: next generation Puppet-Augeas integration

This module is a development ground for the Augeas provider in Puppet.  It will
also bring changes being merged into master (i.e. the next Puppet release) to
existing versions of Puppet.

## Using puppet-augeas-ng

A new resource type will be provided, identical to the existing `augeas` type
but will add new features via providers.

Change existing resource types from `augeas` to `augeasng` to take advantage of
the new providers.  The type parameters are all backwards-compatible, no more
changes are required.

## Requirements

Ensure both Augeas and ruby-augeas bindings are installed and working as normal.

See the providers section below for specific requirements.  Generally use the
latest version possible to get the most out of this module and enable all
features.

  * On RHEL 4, 5 and derivatives, use EPEL versions of Augeas and ruby-augeas
  * On RHEL 6 and derivatives, use Augeas from main and optional channels,
    ruby-augeas from EPEL.  This may not be the latest version, do check beta
    channels too (e.g. RHEL 6.2).
  * On Fedora, use Augeas and ruby-augeas from main updates repo.  Consider
    checking updates-testing.
  * On Debian, use Augeas and libaugeas-ruby\* from main repo, or backports if
    available.  Ensure you use the correct libaugeas-ruby1.8, 1.9 or 1.9.1
    package for your version of Ruby.
  * On Ubuntu, as with Debian.  Also see [raphink's PPA repo](https://launchpad.net/~raphink/+archive/augeas/+packages)
    for fresh Augeas packages.

## Merged changes

The following changes are already merged in development or new versions of
Puppet and are included here too:

  * [#6494](http://projects.puppetlabs.com/issues/6494):
    New commands, defvar, defnode, mv and setm (in 2.7.0)
  * [#2728](http://projects.puppetlabs.com/issues/2728):
    Add diff output for changes made by Augeas provider (in 2.7.3)
  * [#2744](http://projects.puppetlabs.com/issues/2744):
    Display file diffs through the Puppet log system (in 2.7.8)
  * [#7285](http://projects.puppetlabs.com/issues/7285):
    Use Augeas NO\_LOAD/incl to optimise loading based on context (in 2.8)
  * [#5606](http://projects.puppetlabs.com/issues/5606):
    Print Augeas' /augeas//error info to debug on save failure (in 2.8)

## Providers

The following providers are planned along with their dependencies.  Some deps
will be very new or unreleased versions.

  * `augparse` provider, legacy parsing of commands and direct use of
    ruby-augeas API.
    * augeas: any version
    * ruby-augeas: any version
  * `augsrun` provider, using aug\_srun for commands
    * augeas: 0.10.0 or higher
    * ruby-augeas: development
  * `augcond` provider, using aug\_srun for commands and parsing for `onlyif`
    support
    * augeas: 0.10.0 or higher
    * ruby-augeas: development

## Issues

Please file any issues or suggestions on Github:
  https://github.com/domcleal/puppet-augeas-ng/issues
