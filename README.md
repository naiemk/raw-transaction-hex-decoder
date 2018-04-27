# Raw Transaction Decoder

This library's methods return information of a transaction, given this transaction `HEX` as input.

## Supported coins

- Ethereum
- Bitcoin

## Usage

- `npm install transaction-hex-decoder`


### Ethereum Raw Tx

```javascript
const txHexDecoder = require("transaction-hex-decoder");

// Transaction https://etherscan.io/tx/0x09b092b86ffc8f425b405d3ac0ef1ec51269fa024e64b4b5778961a4d588c982 -> Tool/utilities to check rawTx
const ethEncodedRawTx = "0xf86e82cd70850bdfd63e00827918943c601b93eaad76d2f66f71a0b8c22dbbf2e71db688287bb23d4c9350008025a09f3842a8fd9d6228d4ee226524e249c81eba22c53a87855f2244b2064c8036d6a073c767ae047bce30dee587e5233649acbae36b10d97b39d11fb9b2ccabf9b925";
const ethDecodedRawTx = txHexDecoder.decodeEthRawTx(ethEncodedRawTx);
console.log("Decoded Transaction : "+JSON.stringify(ethDecodedRawTx));
/* OUTPUT Example:
{
   "nonce":52592,
   "gasPrice":51000000000,
   "startGas":31000,
   "to":"0x3c601b93eaad76d2f66f71a0b8c22dbbf2e71db6",
   "valueInWei":2917121160000000000,
   "valueInEther":2.91712116,
   "inputData":"0x",
   "v":"0x25",
   "r":"0x9f3842a8fd9d6228d4ee226524e249c81eba22c53a87855f2244b2064c8036d6",
   "s":"0x73c767ae047bce30dee587e5233649acbae36b10d97b39d11fb9b2ccabf9b925"
}*/
```

### Bitcoin Raw Tx

```javascript
const txHexDecoder = require("transaction-hex-decoder");

const btcEncodedRawTx = "0100000001d144583347ebdb81263ea30c731fa44725f23692918c0bc495df53b26ec3d7920000000000ffffffff01983a0000000000001976a914406f4066bb99985efe9d36b0ac7c4c96c799104888ac00000000";
const btcDecodedRawTx = txHexDecoder.decodeBtcRawTx(btcEncodedRawTx);
console.log("Decoded transaction : "+JSON.stringify(btcDecodedRawTx));
/* OUTPUT Example:
{
   "version":1,
   "locktime":0,
   "ins":[
      {
         "hash":{
            "type":"Buffer",
            "data":[]
         },
         "index":0,
         "script":{
            "type":"Buffer",
            "data":[

            ]
         },
         "sequence":4294967295,
         "witness":[

         ]
      }
   ],
   "outs":[
      {
         "value":15000,
         "script":{
            "type":"Buffer",
            "data":[]
         }
      }
   ],
   "totalValue":15000
}
*/

```