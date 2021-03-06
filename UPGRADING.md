# How to upgrade/downgrade Rubygems:

## For RubyGems 1.5.0 and 1.5.1:

RubyGems 1.5.0 and 1.5.1 shipped with a broken `gem update --system`. You will
need to use the Manual Upgrade Recipe below.

## On Ruby 1.9.x:

### From stock ruby shipping with 1.9:

Use the Normal Upgrade Method below. (finally!)

## On Ruby 1.8.x:

### From rubygems 1.3.x:

Use the Normal Upgrade Recipe below.

### From rubygems 1-1.x through 1.2.x:

RubyGems 1.1 and 1.2 have problems upgrading when there is no rubygems-update
installed. You will need to use the following instructions if you see "Nothing
to update".

Use the Manual Upgrade Recipe below.

### From rubygems < 1.1.x:

Use the Normal Upgrade Recipe below.

## Downgrade Recipe

### Normal Downgrade

#### With rubygems 1.5.2 and higher:

    $ gem update --system 1.3.7

#### With rubygems 1.5.1 and lower:

Use sudo/su as appropriate:

    $ gem install rubygems-update -v 1.3.7
    $ update_rubygems _1.3.7_

Replace 1.3.7 with whatever version you want to downgrade to. This recipe can
also be used to upgrade to a specific version instead of the latest.

Do make sure that you don't have any other versions of rubygems-update
installed when you run the second command.

### 1.9.2 Downgrade from Rubygems 1.4.x+ to stock 1.9 rubygems:

Use sudo/su as appropriate:

    $ ruby --disable-gems -S gem which rubygems
    ~/.rvm/rubies/ruby-1.9.2-p136/lib/ruby/site_ruby/1.9.1/rubygems.rb
    $ rm ~/.rvm/rubies/ruby-1.9.2-p136/lib/ruby/site_ruby/1.9.1/rubygems.rb
    $ rm -rf ~/.rvm/rubies/ruby-1.9.2-p136/lib/ruby/site_ruby/1.9.1/rubygems
    $ gem -v
    1.3.7

## Upgrade Recipes

### Normal Upgrade

Use sudo/su as appropriate:

    $ gem update --system

### Manual Upgrade

If you have an older version of RubyGems installed, then you can still do it
in two steps:

Use sudo/su as appropriate:

    $ gem install rubygems-update
    $ update_rubygems

### Manual Install

If you don't have any RubyGems install, there is still the pre-gem approach to
getting software, doing it manually:

Use sudo/su as appropriate:

*   Download from: https://rubygems.org/pages/download
*   Unpack into a directory and cd there
*   Install with: ruby setup.rb
