Guard::Webpack spins up a [Webpack](http://webpack.github.io) watcher in a background thread.

## Installation

Please ensure you have [Guard](http://github.com/guard/guard) installed before you continue.

Add the following to your application's Gemfile:

    group :development do
      gem 'guard-webpack'
    end

And then execute:

    $ bundle

Add Guard::Webpack to your Guardfile by running:

    $ guard init webpack

## Usage

Please refer to the [Guard usage doc](http://github.com/guard/guard#readme)

## Example Guardfile

At present, Guard::Webpack assumes you already have Webpack configured via a `webpack.config.js` file. Please refer to [this Webpack tutorial](https://github.com/petehunt/webpack-howto) for help getting that configured.

You can, however, add additional options to your Guardfile, as seen below:

```ruby
guard :webpack, binary: './node_modules/.bin/webpack-dev-server', config: './config/webpack/development.config.js', flags: '--hot' do
  watch %r{config/webpack/(.*)}
end
```

## Options

### List of available options

```ruby
flags: '--list --of --flags' # define a list of custom flags
binary: 'path_to_binary' # define a path to custom binary file
config: 'path_to_config' # define an config file
```

## Notes on Guard 1.x

Guard::Webpack strives to support older versions of Guard (including the `Guard::Guard`, rather than `Guard::Plugin` syntax. However, support may be limited. Options, as specified above, are not supported for versions of Guard below 2.0.

## Contributing

1. Fork it ( https://github.com/Unodor/guard-webpack/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
