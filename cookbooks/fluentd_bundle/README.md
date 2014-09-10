# fluentd_bundle-cookbook

Install fluentd with rbenv to `/opt/fluentd`(default).

## Supported Platforms

- Ubuntu14.04
- Joyent SmartOS 14.xx

## Attributes

|key|usage|default|
|----|-----|----|
| | | |

### bundle.rb

|key|usage|default|
|----|-----|----|
|node[:fluentd_bundle][:bundler][:pre_commands] | run shell command before bundle | [] |
|node[:fluentd_bundle][:bundler][:force_bundle] | run bundle install forcefully with no update to Gemfile.| false |

### default.rb

|key|usage|default|
|----|-----|----|
|node[:fluentd_bundle][:root] | fluentd base directory | '/opt/fluentd' |
|node[:fluentd_bundle][:ug] | run as specific user |` {
  :user => 'fluentd',
  :uid  => nil,
  :group => 'fluentd',
  :gid  => nil
} `|


### depends_smartos.rb

packages list and logadm settings.

### depends_ubuntu.rb

packages list and loglotate settings.


### gemfile.rb

`Gemfile` for fluentd settings.

### rbenv.rb

rbenv settings.

## Recipes

### default.rb

Install rbenv and fluentd.

## Usage

add `fluentd_bundle::default` to your run_list.

### Mange fluentd

This cookbook creates `./scripts/start.sh` and `./scripts/stop.sh`.

```
./scripts/start.sh 
starting fluentd ...

## puts pid to ./var/fluentd.pid
## outputs log to log/fluentd.log
```

```
# ./scripts/stop.sh 
stopping fluentd .OK
```

You can set these scripts to the process manager such as monit.


## TODO

- version controle
- not_if bundle check
- bundle update or outdate check
- get latest version automatically

## Contributing

1. Fork the repository on Github
2. Create a named feature branch (i.e. `add-new-recipe`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request

## License and Authors

Author:: HiganWorks LLC. (<sawanoboriyu@higanworks.com>)
