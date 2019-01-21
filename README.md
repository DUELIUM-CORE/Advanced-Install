# Nodemaster - by MotoAcidic

The **Nodemaster** scripts is a collection of utilities to manage, setup and update masternode instances.

I am quite confident this is the single best and almost effortless way to setup different crypto masternodes, without bothering too much about the setup part.

If this script helped you in any way, please contribute some feedback. BTC donations also welcome and never forget:

**Have fun, this is crypto after all!**

https://steemit.com/masternodes/@swcrypto/ccbc-easy-guide-to-setup-multiple-masternodes-on-1-vps


## Installation

SSH to your VPS and clone the Github repository:

```bash
git clone https://github.com/DUELIUM-CORE/Advanced-Install.git && cd Advanced-Install
```

Install & configure your desired master node with options:

```bash
./install.sh -p DUELIUM
```

## Examples for typical script invocation

These are only a couple of examples for typical setups. Check my [easy step-by-step guide for [vultr](/docs/masternode_vps.md) that will guide you through the hardest parts.

**Install & configure 4 DUELIUM masternodes:**

```bash
./install.sh -p DUELIUM -c 4
```

**Update daemon of previously installed DUELIUM masternodes:**

```bash
./install.sh -p DUELIUM -u -n "6"
```

**Install 6 DUELIUM masternodes with the git release tag "tags/v1.0.0.5"**

```bash
./install.sh -p DUELIUM -c 6 -r "tags/v1.0.0.5"
```

**Wipe all DUELIUM masternode data:**

```bash
./install.sh -p DUELIUM -w
```

**Install 2 DUELIUM masternodes and configure sentinel monitoring:**

```bash
./install.sh -p DUELIUM -c 2 -s
```

## Options

The _install.sh_ script support the following parameters:

| Long Option  | Short Option | Values              | description                                                         |
| :----------- | :----------- | ------------------- | ------------------------------------------------------------------- |
| --project    | -p           | project,   "DUELIUM"| shortname for the project                                           |
| --net        | -n           | "4" / "6"           | ip type for masternode. (ipv)6 is default                           |
| --release    | -r           | e.g. "tags/v1.0.0.2"| a specific git tag/branch, defaults to latest tested                |
| --count      | -c           | number              | amount of masternodes to be configured                              |
| --update     | -u           | --                  | update specified masternode daemon, combine with -p flag            |
| --sentinel   | -s           | --                  | install and configure sentinel for node monitoring                  |
| --wipe       | -w           | --                  | uninstall & wipe all related master node data, combine with -p flag |
| --help       | -h           | --                  | print help info                                                     |
| --startnodes | -x           | --                  | starts masternode(s) after installation                             |

## Troubleshooting the masternode on the VPS

If you want to check the status of your masternode, the best way is currently running the cli e.g. for $DUELIUM via

```
/usr/local/bin/DUELIUM-cli -conf=/etc/masternodes/DUELIUM_n1.conf getinfo

{
    "version" : 1000004,
    "protocolversion" : 70004,
    "walletversion" : 61000,
    "balance" : 0.00000000,
    "zerocoinbalance" : 0.00000000,
    "blocks" : 15719,
    "timeoffset" : 0,
    "connections" : 21,
    "proxy" : "",
    "difficulty" : 47075.67091216,
    "testnet" : false,
    "moneysupply" : 8015522.58694497,
    "zDLsupply" : {
        "1" : 1.00000000,
        "5" : 5.00000000,
        "10" : 10.00000000,
        "50" : 50.00000000,
        "100" : 100.00000000,
        "500" : 0.00000000,
        "1000" : 0.00000000,
        "5000" : 0.00000000,
        "total" : 166.00000000
    },
    "keypoololdest" : 1537990754,
    "keypoolsize" : 1001,
    "paytxfee" : 0.00000000,
    "relayfee" : 0.00010000,
    "staking status" : "Staking Not Active",
    "errors" : ""
}
```
# Helpful Commands

## Start Coin on initial install
```
/usr/local/bin/activate_masternodes_DUELIUM
```
## Stop coin
```
/usr/local/bin/DUELIUM-cli -conf=/etc/masternodes/DUELIUM_n1.conf stop
```
## Start Coin
```
/usr/local/bin/DUELIUMd -conf=/etc/masternodes/DUELIUM_n1.conf
```
## Getinfo
```
/usr/local/bin/DUELIUM-cli -conf=/etc/masternodes/DUELIUM_n1.conf getinfo
```


# Help, Issues and Questions

I activated the "[issues](https://github.com/masternodes/vps/issues)" option on github to give you a way to document defects and feature wishes. Feel free top [open issues](https://github.com/masternodes/vps/issues) for problems / features you are missing here: [https://github.com/masternodes/vps/issues](https://github.com/masternodes/vps/issues).

I might not be able to reply immediately, but i do usually within a couple of days at worst. I will also happily take any pull requests that make masternode installations easier for everyone ;-)

If this script helped you in any way, please contribute some feedback. BTC donations also welcome and never forget:

**Have fun, this is crypto after all!**

```
BTC  1JfM1MU6Ro8e9VBiYzSTvYbzJUyLiupcNr
```

## Management script (not yet implemented)

The management script release will follow within the next couple of days.

| command                                  | description                                  |
| :--------------------------------------- | -------------------------------------------- |
| nodemaster start DUELIUM (all\|number)   | start all or a specific pivx masternode(s)   |
| nodemaster restart DUELIUM (all\|number) | stop all or a specific pivx masternode(s)    |
| nodemaster stop DUELIUM (all\|number)    | restart all or a specific pivx masternode(s) |
| nodemaster cleanup DUELIUM (all\|number) | delete chain data for all pivx masternodes   |
| nodemaster status DUELIUM (all\|number)  | systemd process status for a pivx masternode |
| nodemaster tail DUELIUM (all\|number)    | tail debug logs for a pivx masternode        |

# Todo

* provide my Dockerfile & Vagrantfile
* write more test cases
* implement a binary option (?)
* output all supported cryptos as list within help

# Errors

* currently not fully idempotent

Ping me at contact@marsmenschen.com for questions and send some crypto my way if you are happy.

**Have fun, this is crypto after all!**

```
BTC  1JfM1MU6Ro8e9VBiYzSTvYbzJUyLiupcNr - all credits to MotoAcidic
```
