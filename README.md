# Electronero PHP SDK
A Electronero library written in PHP by [Electronero Integrations](https://electronerointegrations.com).</br>
Forked by [Interchained](https://github.com/interchained) for Electronero Network](https://github.com/electronero)</br>
</br>
This is compatible with all of Electronero Network coins: ETNX, ETNXP, LTNX, GLDX, and CRFI. 
</br>
Each coin has their own PHP wrapper in the `/src` directory </br>
</br>
Telegram: https://t.me/electronero </br>
Twitter: https://twitter.com/_electronero </br>
</br>
Daemon Docs > https://github.com/electronero/electronero-php-sdk/blob/master/electronerophp/docs/daemonRPC.md </br>
Wallet Docs > https://github.com/electronero/electronero-php-sdk/blob/master/electronerophp/docs/walletRPC.md </br
______________________________
## How It Works
This library has 3 main parts:

1. A Electronero daemon JSON RPC API wrapper, `daemonRPC.php`
2. A Electronero wallet (`electronero-wallet-rpc`) JSON RPC API wrapper, `walletRPC.php`
3. A Electronero/Cryptonote toolbox, `cryptonote.php`, with both lower level functions used in Electronero related cryptography and higher level methods for things like generating Electronero private/public keys.

In addition to these features, there are other lower-level libraries included for portability, *eg.* an ed25519 library, a SHA3 library, *etc.*

## Preview
![Preview](https://user-images.githubusercontent.com/4107993/38056594-b6cd6e14-3291-11e8-96e2-a771b0e9cee3.png)

## Documentation

Documentation can be found in the [`/docs`](https://github.com/sneurlax/electronerophp/tree/master/docs) folder.

## Configuration
### Requirements
 - Electronero daemon (`electronerod`, `pulsed`, `litenerod`, `goldnerod`, `crystaleumd`)
 - Webserver with PHP, for example XMPP, Apache, or NGINX
    - cURL PHP extension for JSON RPC API(s)
    - GMP PHP extension for about 100x faster calculations (as opposed to BCMath)

Debian (or Ubuntu) are recommended.
 
### Getting Started

1. Start the Electronero daemon (`electronerod`) on testnet.
```bash
electronerod --testnet
```

2. Start the Electronero wallet RPC interface (`electronero-wallet-rpc`) on testnet.
```bash
electronero-wallet-rpc --testnet --rpc-bind-port 12345 --disable-rpc-login --wallet-dir /path/to/wallet/directory
```

3. Edit `example.php` with your the IP address of `electronerod` and `electronero-wallet-rpc` (use `127.0.0.1:54321` and `127.0.0.1:12345`, respectively, for testnet.)

4. Serve `example.php` with your webserver (*eg.* XMPP, Apache/Apache2, NGINX, *etc.*) and navigate to it.  If everything has been set up correctly, information from your Electronero daemon and wallet will be displayed.
