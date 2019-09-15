# Auracoin Peer List
Official peer list for Auracoin.

## What list should I use?
If you are wanting to directly contribute to the Auracoin network, we suggest
using the `main-firstlevel.aup` peer list.

If you're testing out a new feature that you are wanting to implement on the
network, we suggest using the `test-firstlevel.aup` peer list. You can also
host your own peer list on your site or webserver so that you an do local
testing.

## How do I use one of the peer lists?
> **Note:** By default, the Auracoin configuration file includes the
> `main-firstlevel.aup` peer list. You can skip this section if you wish to
> use the main peer list and you already have it as default!

You'll need to update your Auracoin configuration file in order to use one of
the peer lists. You do this, edit the file located at
`%userprofile%\.auracoin\config.auc` (Windows) or `~/.auracoin/config.auc`
(Mac/Linux) and edit the `peerList` property under the `Peers` group like so:

```ini
peerList = https://aur.xyz/auracoin-peers/main-firstlevel.aup
```

The example above is for the `main-firstlevel.aup` peer list. Feel free to
change the peer list to one like `test-firstlevel.aup`!

Your `config.auc` file should now look similar to this:

```ini
[Account]
address = xxxxxxxxxx
publicKey = 00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
privateKey = 0000000000000000000000000000000000000000000000000000000000000000

[Peers]
peerList = https://aur.xyz/auracoin-peers/main-firstlevel.aup
outboundIP = 0.0.0.0
outboundPort = 5000
peerTimeout = 3
```

## How do I add my node to the peer list?
> **Note:** Please make sure that you have the `outboundIP` and `outboundPort`
> fields populated in `config.auc` ─ we suggest having the `outboundIP` set
> to `0.0.0.0` so that you can do port forwarding.

Firstly, you will need to port forward your node to the internet; please check
your local ISP's documentation on how to do this (there normally is just an
option that allows port forwarding of your IP address in your router's admin
page).

Secondly, you'll need a GitHub account. With a GitHub account, fork this
repository, and add your node's public IP address to a peer list (we suggest
`main-firstlevel.aup`) like this:

```
http://123.123.123.123:5000
```

Of course, substitute `123.123.123.123` to your node's IP address (it should
not be `0.0.0.0`, `127.0.0.1` or `localhost` and it shouldn't start with
`192.168.` as they're all local) for your own IP address, and substitute `5000`
for your node's port (which is normally `5000`, but it is configurable).

Finally, open up a pull request on **this repository** (not the forked one, but
it may work if you're lucky as long as you are careful with what options you
choose) to merge your cloned repository into our repository. An example of what
the pull request settings would look like if you were called `aurabot`:

`base repository: aurora/auracoin` `base: master` ← `head repository: aurabot/auracoin` `compare: master`
