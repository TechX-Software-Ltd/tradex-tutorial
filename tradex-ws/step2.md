SocketCluster JavaScript Client

#### To install, run:
`npm install socketcluster-client`{{execute}}
`npm install sc-codec-min-bin`{{execute}}

#### Import socketcluster-client
**With Browser:**
The socketcluster-client script is called socketcluster.js (located in the main socketcluster-client directory). Embed it in your HTML page like that:

`<script type="text/javascript" src="/socketcluster.js"></script>`
`<script type="text/javascript" src="/sc-codec-min-bin.js"></script>`

- Note that the src attribute may be different depending on how you setup your HTTP server

**With node.js:**
`var socketCluster = require('socketcluster-client');`
`var scCodecMinBin = require('sc-codec-min-bin');`
