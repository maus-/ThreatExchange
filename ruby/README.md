# ThreatExchange

A ruby library to interface with Facebooks ThreatExchange API. This is still very much in development so feel free to contribute :)

## Installation
Install required dependencies 

    bundle install

Install this gem locally

    rake install

Add this to your application

    require 'ThreatExchange'

## Usage

The ThreatExchange library provides a base set of abstractions for the ThreatExchange API. You instanciate a new ThreatExchange::Client and provide it with your access token.

```ruby

access_token = 'abc123'
TE = ThreatExchange::Client.new(access_token)

```
To query the ThreatExchange API you create a hash with parameters for your query

```ruby

 query = { 
    threat_type: 'COMPROMISED_CREDENTIAL',
	type: 'EMAIL_ADDRESS',
	fields: 'indicator,passwords',
	limit: 30
}
```

Then call the query with the respective method. 
```ruby

result = TE.threat_indicators(query)
```

The result will return either a string, a singular hash or an array of hashes and then from there you can manipulate the data as you like.
If you would like to see examples of each type of query take a look at the script in the example directory. 



## Contributing

1. Fork it ( https://github.com/facebook/ThreatExchange/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
