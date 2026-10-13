Mining
------

- The built-in CPU miner is back. `setgenerate true [genproclimit] [address]` starts it,
  `setgenerate false` stops it, `gethashespersec` reports its speed and `getmininginfo` gained
  `generate`, `genproclimit` and `hashespersec` fields. It can also be started at launch with
  `-gen`, `-genproclimit=<n>` and `-miningaddress=<addr>`. It is meant for regtest, signet and
  testnet; on mainnet use `getblocktemplate` with an external miner.

- Defaults are now suited to running behind the [DATUM Gateway](https://github.com/OCEAN-xyz/datum_gateway):
  `-blockmaxsize` and `-blockmaxweight` default to 3985000 (leaving room for the pool's generation
  transaction), `-maxmempool` to 1000, `-blockreconstructionextratxn` to 1000000 and
  `-blockreconstructionextratxnsize` to 100 (MB). Nodes that want the previous behaviour can set
  `-blockmaxsize=300000 -blockmaxweight=1200000 -maxmempool=300 -blockreconstructionextratxn=32768
  -blockreconstructionextratxnsize=10`. See `contrib/datum` for configuration examples and a setup script.
