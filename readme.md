# Using MTA GTFS API with Node

This repo is a quick example of how to get data from the MTA GTFS API with Node.

## What the app does

1. Forms a request URL with using your API key

	The URL is formed like this:

	```
	'http://datamine.mta.info/mta_esi.php?key=' + apiKeys.mta + '&feed_id=2'
	```

	Where:

	- `apiKeys.mta` is your API key (see "How to run section below")
	- `'&feed_id=2'` is the feed for the L Train (the feed with the least amount of data, for a little brevity)

1. Makes a get request to that URL
1. If a valid response is received, parses the data into JavaScript objects and logs some of the data in your console


## How to run

Before you start, you will need an API key from the [MTA developer portal](http://web.mta.info/developers/).

1. Fork and clone the repo
1. `npm install`
1. Make a file called `config.js` in the top level directory, adding this code:

	```
	module.exports = {
		mta: "<YOUR_API_KEY>"
	}
	```

1. `npm start`

## Results

Logged in your terminal will be `feed.entity.trip_update` for each `entity` with a `trip_update`. 

This is the same example that can be found in the readme for the [`gtfs-realtime-bindings` NPM module](https://github.com/google/gtfs-realtime-bindings/tree/master/nodejs).

## Resources

- [MTA developer portal](http://web.mta.info/developers/)
- [`gtfs-realtime-bindings` NPM module](https://github.com/google/gtfs-realtime-bindings/tree/master/nodejs)
- [GTFS-realtime explanation on Google Developers](https://developers.google.com/transit/gtfs-realtime/)