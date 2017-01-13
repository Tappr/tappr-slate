Tappr API documentation V1.0


Overview
------------
Tappr's first version of the API docs. Private release only at this stage. This is very much still in development, however we'll begin to work with third-party developers before the official release.

Based on Slate <a href="https://github.com/lord/slate">https://github.com/lord/slate</a>


Getting Started 
------------------------------

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 2.2.5 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

1. Fork this repository on Github.
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/Tappr/slate.git`
3. `cd slate`
4. Initialize and start Slate. You can either do this locally, or with Vagrant:

```shell
# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

You can now see the docs at http://localhost:4567. Whoa! That was fast!




