# Getting Started

This is a quick how to on how to get started using fog-softlayer, we try to cover all aspects from zero to hero using this library.

## Installation

You can just use as a gem on your system installing it as a global gem:

```bash
gem install fog-softlayer
```

or you can add to your Gemfile

```ruby
gem 'fog-softlayer
```

This is the only necessary step, after configure your credentials on fog file (see how next on usage section) you can test your setup executing the contents according to this [gist](https://gist.github.com/fernandes/58908649f25b218cc4a7)

## Usage

The first step to get into fog-softlayer is configure your __~/.fog__ file, this is useful to not type your credential access every single time you wanna use fog softlayer.

If you do not configure, you need to make start every time configuring your access like:

```ruby
@sl = Fog::Compute.new(provider: "softlayer", softlayer_username: "SLUSERNAME", softlayer_api_key: '860e03c168c3aef304341b492ba9984ac1080bb5')
```

Its not cool, and you can leak your credentials sometime, whats could result in security issues, so lets not repeat ourselves and avoid api key leaks.

Write a configure file like this under __~/.fog__

```yaml  
default:
  softlayer_username: example-username
  softlayer_api_key: 1a1a1a1a1a1a1a1a1a11a1a1a1a1a1a1a1a1a1 
  softlayer_default_domain: example.com
  softlayer_cluster: cluster # needed for storage access
```

After this file is configured you just need to use:

```ruby
@sl = Fog::Compute[:softlayer]
```

Remembering, you can always specify the username and api key to connect using another credential.