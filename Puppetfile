# This file manages Puppet module dependencies.
#
# It works a lot like Bundler. We provide some core modules by
# default. This ensures at least the ability to construct a basic
# environment.

# Shortcut for a module from GitHub's boxen organization
def github(name, *args)
  options ||= if args.last.is_a? Hash
    args.last
  else
    {}
  end

  if path = options.delete(:path)
    mod name, :path => path
  else
    version = args.first
    options[:repo] ||= "boxen/puppet-#{name}"
    mod name, version, :github_tarball => options[:repo]
  end
end

# Shortcut for a module under development
def dev(name, *args)
  mod name, :path => "#{ENV['HOME']}/src/boxen/puppet-#{name}"
end

# Includes many of our custom types and providers, as well as global
# config. Required.

github "boxen", "3.4.2"

# Core modules for a basic development environment. You can replace
# some/most of these if you want, but it's not recommended.

github "dnsmasq",     "1.0.1"
github "gcc",         "2.0.100"
github "git",         "2.2.2"
github "homebrew",    "1.6.1"
github "hub",         "1.3.0"
github "inifile",     "1.0.3", :repo => "puppetlabs/puppetlabs-inifile"
github "module-data", "0.0.3", :repo => "ripienaar/puppet-module-data"
github "pkgconfig",   "1.0.0"
github "repository",  "2.3.0"
github "stdlib",      "4.1.0", :repo => "puppetlabs/puppetlabs-stdlib"
github "sudo",        "1.0.0"
github "xquartz",     "1.1.1"

# Optional/custom modules. There are tons available at
# https://github.com/boxen.

# OS X APPS
github "chrome",      "1.1.2"
github "firefox",     "1.1.8"
github "alfred",      "1.1.7"
github "googledrive", "1.0.2"
github "dropbox",     "1.2.0"
github "libreoffice", "4.1.5"
github "wunderlist",  "1.0.0"
github "onepassword", "1.1.0"
github "caffeine",    "1.0.0"
github "slack",       "1.0.4"
github "mou",         "1.1.3"
github "skype",       "1.0.8"
github "spotify",     "1.0.1"
github "teamviewer",  "1.0.1"
