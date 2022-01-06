
# Electronero Network PHP Library 
A Electronero library written in PHP by the [Monero Integrations](https://monerointegrations.com) [team](https://github.com/monero-integrations/monerophp/graphs/contributors).

Forked by [Interchained](https://github.com/interchained) for Electronero Network](https://github.com/electronero/electronero)</br>
Thank you [`Monero Intergrations`](https://github.com/monero-integrations/monerophp)
</br>
This is compatible with all of Electronero Network coins: ETNX, ETNXP, LTNX, GLDX, and CRFI. 
</br>
Each coin has their own PHP wrapper </br>
</br>
Telegram: https://t.me/electronero </br>
Twitter: https://twitter.com/_electronero </br>
</br>
Daemon Docs > https://github.com/electronero/electronero-php-sdk/blob/master/electronerophp/docs/daemonRPC.md </br>
Wallet Docs > https://github.com/electronero/electronero-php-sdk/blob/master/electronerophp/docs/walletRPC.md </br
______________________________
## How It Works
This library has 4 main parts, for each native electronero coin we need the appropriate daemonRPC, and walletRPC PHP files and a single jsonRPCClient.php & cryptonote.php:

1. A Electronero daemon JSON RPC API wrapper, `daemonRPC.php`
2. A Electronero wallet (`electronero-wallet-rpc`) JSON RPC API wrapper, `walletRPC.php`
3. A Electronero/Cryptonote toolbox, `cryptonote.php`, with both lower level functions used in Electronero related cryptography and higher level methods for things like generating Monero private/public keys.
4. jsonRPCClient.php Written using the JSON RPC specification.

In addition to these features, there are other lower-level libraries included for portability, *eg.* an ed25519 library, a SHA3 library, *etc.*

## Preview
![Preview](https://user-images.githubusercontent.com/4107993/38056594-b6cd6e14-3291-11e8-96e2-a771b0e9cee3.png)

## Documentation

Documentation can be found in the [`/docs`](https://github.com/electronero/electronero-network-php-sdk/tree/master/docs) folder.

## Configuration
### Requirements
 - Electronero daemon (`electronerod`, `pulsed`, `litenerod`, `goldnerod`, `crystaleumd`)
 - Webserver with PHP, for example XMPP, Apache, or NGINX
    - cURL PHP extension for JSON RPC API(s)
    - GMP PHP extension for about 100x faster calculations (as opposed to BCMath)

Debian (or Ubuntu) are recommended.
 
### Getting Started

example with electronerod, repeat the process for each native electronero network coin with their matching DaemonRPC and WalletRPC.
1. Start the Electronero daemon (`electronerod`) on testnet.
```bash
electronerod --testnet --detach
```

2. Start the Monero wallet RPC interface (`monero-wallet-rpc`) on testnet.
```bash
electronero-wallet-rpc --testnet --rpc-bind-port 28083 --disable-rpc-login --wallet-dir /path/to/wallet/directory
```

3. Edit `example.php` with your the IP address of `electronerod` and `monero-wallet-rpc` (use `127.0.0.1:28081` and `127.0.0.1:28083`, respectively, for testnet.)

4. Serve `example.php` with your webserver (*eg.* XMPP, Apache/Apache2, NGINX, *etc.*) and navigate to it.  If everything has been set up correctly, information from your Electronero daemon and wallet will be displayed.
