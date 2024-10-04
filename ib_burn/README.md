## Quickstart

1. Put your node names in config.json
2. Install perftest on all nodes (`< all-nodes parallel --tag --bar ssh {} 'sudo apt install perftest'`)
3. Run `ib_fabric.sh` to extract the Infiniband switching topology
4. Run `./ib_burn.py` to find the smallest subset of P2P tests that span all physical links (IIUC) and generate the testing script
5. Run `bash ib_burn.sh` and wait for it to finish

## Analyze (very rudimentary)

1. `tail -n 2 ib_burn_logs/*` should reveal show a bandwidth measurement or an error
2. For a more aggregated view `grep -c -- '---------------------------------------------------------------------------------------' ib_burn_logs/*` outputs 4 if the particular P2P test succeeded
