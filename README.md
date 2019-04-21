# LND SDK for Lightning Network (BTC) nodes

[![Build Status](https://travis-ci.org/lnpay/lnd_ruby_sdk.svg?branch=master)](https://travis-ci.org/lnpay/lnd_ruby_sdk) [![Code Climate](https://codeclimate.com/github/lnpay/lnd_ruby_sdk.svg)](https://codeclimate.com/github/lnpay/lnd_ruby_sdk)

This is a SDK for ruby applications that can help you communicate with your Lightning Network node. There is still a lot to do before this gem can be used by others, but I will try to update it and create a stable version as soon as possible. If you would like to help, check out the Contributing section below.

## Requirements

This SDK requires that you have access to the **macaroon file** and a **tls certificate** generated by your LND node. By default, these can be found at `~/.lnd/data/chain/bitcoin/mainnet/admin.macaroon`
and `~/.lnd/tls.cert`.

This SDK **does not** work with other servers than [LND](https://github.com/lightningnetwork/lnd). If your node is running on [c-lightning](https://github.com/ElementsProject/lightning), it wont work.

## Installation

Add this line to your application's Gemfile:

```
gem 'lnd_ruby_sdk', '~> 0.1.0'
```

And then execute:

```
$ bundle install
```

Or install it yourself as:

```
$ gem install lnd_ruby_sdk
```

## Configuration
Here's an example of how to configure your app. If you are using this gem with Rails, you may create a new initializer in your `config/initializers` folder named `lightning.rb`

```ruby
Lightning.configure do |config|
  config.grcp_host = '127.0.0.1'
  config.grcp_port = '10009'
  config.macaroon_path = '~/.lnd/data/chain/bitcoin/mainnet/admin.macaroon'
  config.certificate_path = '~/.lnd/tls.cert'
end
```

## Documentation
SDK documentation and all available commands can be found at [https://lnpay.github.io/lnd_ruby_sdk/Lightning.html](https://lnpay.github.io/lnd_ruby_sdk/Lightning.html)

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

A good way to start would be by running `rake spec` to check out the list of `Pending` tests.

### Progress

**Method**|**Added to SDK version**
-----|-----
genseed|
initwallet|
unlockwallet|
changepassword|
walletbalance|
channelbalance|
gettransactions|
estimatefee|
sendcoins|
listunspent|
subscribetransactions|
sendmany|
newaddress|
signmessage|
verifymessage|
connectpeer|
disconnectpeer|
listpeers|
getinfo|0.1.0
pendingchannels|0.1.1
listchannels|0.1.1
subscribechannelevents|
closedchannels|0.1.1
openchannelsync|
openchannel|
closechannel|
abandonchannel|
sendpayment|
sendpaymentsync|
sendtoroute|
sendtoroutesync|
addinvoice|0.1.0
listinvoices|0.1.0
lookupinvoice|
subscribeinvoices|
decodepayreq|0.1.0
listpayments|
deleteallpayments|
describegraph|
getchaninfo|
getnodeinfo|0.1.1
queryroutes|
getnetworkinfo|0.1.1
stopdaemon|
subscribechannelgraph|
debuglevel|
feereport|
updatechannelpolicy|
forwardinghistory|
exportchannelbackup|
exportallchannelbackups|
verifychanbackup|
restorechannelbackups|
subscribechannelbackups|


## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/lnpay/lnd_ruby_sdk.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
