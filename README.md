# eNIFTY
![Alt text](PNG/1.png?raw=true"")

eNIFTY is an NFT marketplace where where people can efficiently use the NFTs owned by them in various ways like trading and using them as collateral for loans.

## Installation API

Download [node.js](https://nodejs.org/en/download/) to install eNIFTY API.

To setup the solana blockchain environment make sure to install [Rust](https://www.rust-lang.org/tools/install) and [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools#use-solanas-install-tool).

You'll know you've done it right if you can run `solana --version`, `git --version`, and `cargo --version` and see outputs like:
```
solana --version
solana-cli 1.7.10 (src:03b93051; feat:660526986)
```
And
```
cargo --version
cargo 1.54.0 (5ae8d74b3 2021-06-22)
```

Download the whole code using.
```bash
git clone https://github.com/kjain333/eNIFTY.git
```

Set the solana cluster (network) to [devnet](https://docs.solana.com/clusters#devnet).
```
solana config set --url https://api.devnet.solana.com
```

Create a [keypair](https://docs.solana.com/terminology#keypair) for your account. This will be your public / private key. **This is an [insecure method for storing keys](https://docs.solana.com/wallet-guide/cli#file-system-wallet-security), please use this account for testing only.**

You'll be prompted for a password.
```
mkdir solana-wallet
solana-keygen new --outfile solana-wallet/keypair.json
```

Fund your account on devnet, we can use a faucet.
Command line faucet:
```
solana airdrop 5 $(solana-keygen pubkey solana-wallet/keypair.json)
```

Build the program
```
cargo build-bpf
```

Deploy the program. The output from the previous step will give you the command to execute to deploy the program. It should look similar to this(or any other command use recieve after cargo build):
```
solana program deploy target/deploy/eNIFTY-API.so --keypair solana-wallet/keypair.json
```

You'll see an output like:
```
RPC URL: https://api.devnet.solana.com
Default Signer Path: solana-wallet/keypair.json
Commitment: confirmed
Program Id: Your Program Id
```

In the project folder, run the following command to install all the necessary dependencies for this project.
```bash
npm install
```

Then go to the client folder using
```bash
cd client/src
```

Create new file name keys.js and store your API key there.
```bash
const API_KEY = 'YOUR STARDUST_API KEY'
module.exports = API_KEY;
```

Now start the API using
```bash
npm start
```

The API is now started and should be successfully running at localhost:8080.

## Installation FLUTTER-APP

To setup the Flutter mobile application
```bash
cd eNIFTY/eNIFTY-App
flutter pub get
```

Change the API call URL to your localhost then
```bash
flutter run
```
To ease out the process we have also provided a special guest access in our app apk file which can be used without any setup but with limited features. It can be accessed from:
[APK](https://github.com/kjain333/eNIFTY/blob/main/SUBMISSION/app-release.apk)

A postman collection of our API's:
[Postman Collection](https://github.com/kjain333/eNIFTY/blob/main/SUBMISSION/eNIFTY%20API%20Endpoints.postman_collection.json)

For more please go through our detailed powerpoint [Presentation](https://github.com/kjain333/eNIFTY/blob/main/SUBMISSION/Solana%20Ignition(eNIFTY-Team%20X%20%C3%86%20A-12).pptx)

