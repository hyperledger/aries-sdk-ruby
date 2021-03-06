# aries-sdk-ruby

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

A [ruby gem](https://rubygems.org/gems/aries-sdk-ruby) for [aries-sdk](https://github.com/hyperledger/aries-sdk).

## Migration notice

Aries Code Repositories are in the process of being migrated from various other locations, including Hyperledger Indy repositories where the Aries work was incubated. Some of the code requires refactoring work to split it from unrelated assets prior to migration.

The status of these code migrations is under regular discussion on the #aries channel on chat.hyperledger.org and in the Aries Working Group weekly call. Please join us there to understand migration status and help identify places where help is needed.

When the appropriate code is migrated to this repoisitory, this README file will be updated.

## Installation

Create a new rails application:

    $ rails new aries-sdk-ruby-rails --skip-active-record
    $ cd aries-sdk-ruby-rails
    $ 

Then, add this line to your application's Gemfile:

```ruby
gem 'aries-sdk-ruby'
```

You *must* have rust installed *and* set LIBRARY_PATH:

    $ export LIBRARY_PATH=/your/path/to/indy-sdk/libindy/target/debug/

See [these instructions](https://github.com/hyperledger/indy-sdk#installing-the-sdk) to install or build the Indy SDK.  Then, execute:

    $ bundle

WARNING: You may have to wait a bit for the native extension to build the aries-sdk-ruby gem.

## Usage

To try out the gem, execute:

    $ bundle exec rails c
    > wallet = AriesWallet.new("mywallet")
    > wallet.create
    > pool = AriesPool.new("mypool")
    > pool.create
    > 

If you check ~/.indy_client/pool and ~/.indy_client/wallet directories, you should see the pool and wallet you created.

## Development

First, you *must* have rust installed *and* set LIBRARY_PATH:

    $ export LIBRARY_PATH=/your/path/to/indy-sdk/libindy/target/debug/

See [these instructions](https://github.com/hyperledger/indy-sdk#installing-the-sdk) to install or build the Indy SDK.  Then, clone the repo and execute:

    $ rake
    $ rspec
    $

## Gem Building

Bump the gem version number up in the gemspec file, then:

    $ bundle
    $ gem build aries-sdk-ruby.gemspec
    Successfully built RubyGem
    Name: aries-sdk-ruby
    Version: 0.0.x
    File: aries-sdk-ruby-0.0.x.gem
    $ gem push aries-sdk-ruby-0.0.x.gem

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/hyperledger/aries-sdk-ruby.

## Example

A sample rails app is available [here](https://github.com/johncallahan/aries-rails)

## Changelog

* 0.0.8
** Support for AriesPool::sign_and_submit

## License

The gem is available as open source under the terms of the [Apache 2.0 License](https://opensource.org/licenses/Apache-2.0).
