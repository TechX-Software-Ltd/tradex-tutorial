create file _client.js_

`touch client.js`{{execute}}

Copy following content to _client.js_:

<pre class="file" data-filename="client.js" data-target="replace">
var socketCluster = require('socketcluster-client');
var scCodecMinBin = require('sc-codec-min-bin');

var options = {
  port: 8000,
  hostname:'beta.vcsc.com.vn',
  codecEngine: scCodecMinBin,
  secure: true
  };

// Initiate the connection to the server
var socket = socketCluster.create(options);

socket.on('connect', function () {
  console.log('CONNECTED');
  });

//------------------- subscribe channel market.stock.bidoffer ------------------------
var bidOfferChannel = socket.subscribe('market.stock.bidoffer');
  bidOfferChannel.on('subscribeFail', function (err) {
  console.error('Failed to subscribe to the bidOfferChannel channel due to error: ' + err);
  });

bidOfferChannel.watch(function (data) {
  console.log('bidOfferChannel: ', data);
  });
</pre>


###### Run client.js with node.js
`node client.js`{{execute}}
