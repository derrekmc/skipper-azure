# [<img title="skipper-azure - Azure Storage adapter for Skipper" src="http://i.imgur.com/P6gptnI.png" width="200px" alt="skipper emblem - face of a ship's captain"/>](https://github.com/lukasreichart/skipper-azure) Azure Blob Adapter

[![NPM version](https://badge.fury.io/js/skipper-azure.png)](http://badge.fury.io/js/skipper-azure) &nbsp; &nbsp;


Azure adapter for receiving [upstreams](https://github.com/balderdashy/skipper#what-are-upstreams). Particularly useful for handling streaming multipart file uploads from the [Skipper](https://github.com/balderdashy/skipper) body parser.

## Installation

```
$ npm install skipper-azure --save
```

Also make sure you have skipper itself [installed as your body parser](http://beta.sailsjs.org/#/documentation/concepts/Middleware?q=adding-or-overriding-http-middleware).  This is the default configuration in [Sails](https://github.com/balderdashy/sails) as of v0.10.


## Usage

```javascript
req.file('avatar')
.upload({
  adapter: require('skipper-azure'),
  key: 'thekyehthethaeiaghadkthtekey'
  secret: 'AB2g1939eaGAdesoccertournament'
  container: 'my_stuff'
}, function whenDone(err, uploadedFiles) {
  if (err) return res.negotiate(err);
  else return res.ok({
    files: uploadedFiles,
    textParams: req.params.all()
  });
});
```

For more detailed usage information and a full list of available options, see the Skipper docs, especially the section on "[https://github.com/balderdashy/skipper#uploading-files-to-s3](Uploading to S3)".


## License

**[MIT](./LICENSE)**
&copy; 2015-

[Lukas Reichart](http://antum.ch), [Antum](http://antum.ch) & contributors

See `LICENSE.md`.

This module is part of the [Sails framework](http://sailsjs.org), and is free and open-source under the [MIT License](http://sails.mit-license.org/).


![image_squidhome@2x.png](http://i.imgur.com/RIvu9.png)


[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/a22d3919de208c90c898986619efaa85 "githalytics.com")](http://githalytics.com/balderdashy/skipper-s3)