SWAPBlocks alphanet node.  To learn more about swapblocks visit http://swapblocks.io


This version is still alpha, use at your own risks


## Details

This version of swapblocks is a clone of ARK.  Future architecture and vision can be 
found by reading our [white paper](https://view.publitas.com/swapblocks/swapblocks_wp/page/1)



### Planned features:
- Asset issuance
- Permissioned Smart Contracts 
- Decentralized Exchange
- Consortium Governance 


## Developer Installation


Install essentials:

```
sudo apt-get update
sudo apt-get install -y curl build-essential python git
```

Install PostgreSQL (min version: 9.5.2)

```
sudo apt-get install -y postgresql postgresql-contrib libpq-dev
sudo -u postgres createuser --createdb --password $USER
```

Install Node.js (tested with version 6.9.2, but any recent LTS release should do):

```
sudo apt-get install -y nodejs npm
sudo npm install -g n
sudo n 6.9.2
```

Install grunt-cli (globally):

```
sudo npm install forever -g
sudo npm install grunt-cli -g
```

Clone this repository
```
git clone https://github.com/SwapBlocks/swapblocks-node.git 
cd swapblocks-node
```

Install node modules:
```
npm install libpq secp256k1
npm install
```

## Launch
To launch swapblocks on testnet:
```
createdb test_swapblocks 
npm run start:testnet
```

To launch swapblocks on alphanet (when launched):
```
createdb swapblocks 
npm run start:alphanet
```

**NOTE:** The **port**, **address**, **genesis block** and **config-path** can be overridden by providing the relevant command switch:
```
node app.js -p [port] -a [address] -c [config-path] -g [genesisBlock-path]
```
This allow you to run several different networks, or your own private chain


## Launch your own private or public chain
Generate a genesisBlock.json + a default config.json containing all passphrases of genesis delegates
```
node tasks/createGenesisBlock.js
```

## Tests
Load git submodule [ark-js](https://github.com/SwapBlocks/ark-js):
```
git submodule init
git submodule update
```

You should run using test configurations

```
npm run start:test
```

Run the test suite:

```
npm test
```

Run individual tests:

```
npm test -- test/api/accounts.js
npm test -- test/api/transactions.js
```

**NOTE:** The master passphrase for this test genesis block is as follows:

```
peace vanish bleak box tuna woman rally manage undo royal lucky since
```


## Authors
- FX Thoorens <fx.thoorens@ark.io>
- Boris Povod <boris@crypti.me>
- Pavel Nekrasov <landgraf.paul@gmail.com>
- Sebastian Stupurac <stupurac.sebastian@gmail.com>
- Oliver Beddows <oliver@lisk.io>

## License

The MIT License (MIT)

Copyright (c) 2016-2017 Ark
Copyright (c) 2016 Lisk
Copyright (c) 2014-2015 Crypti

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:  

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
