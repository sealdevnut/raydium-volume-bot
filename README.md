
# Raydium Volume Bot Version 2

This bot is designed to automate the distribution of SOL to multiple wallets and execute endless buy and sell swap transactions simultaneously on the Raydium platform. It leverages Solana's blockchain technology to perform these operations efficiently.
## Contact

   If you need help or upgraded version, plz contact here: 
   
   [Telegram](https://t.me/sealdevnut)

   
## 🔧 Last Version's Demerits
- ❌ **Repetitive buy and sell with one wallet**: The last version of the Raydium Volume Bot used fixed wallets, so it was apparent on DexScreener that some wallets performed repetitive buy and sell actions.
- ❌ **No increase in the number of makers**: It didn't increase the number of pool makers, only the volume.
- ❌ **Gathering token instead of SOL**: When gathering, if there were tokens left, it didn't sell them before gathering. Instead, it just gathered tokens to the main wallet.
- ❌ **Equal number of buys and sells**: One-time buy and one-time sell actions left sell pressure at the end, as there was always a sell at the end of the volume operation.

## 🚀 Improvements
- ✅ **Transferring SOL to new wallet**: After buying and selling in one wallet, it transfers SOL to a newly created wallet and continues buying and selling there.
- ✅ **Maker increase**: New wallets are created every round of buying and selling, increasing the number of makers.
- ✅ **Sell before gather**: When gathering, if there are tokens left in the wallet, it sells the tokens first and gathers only SOL (the token account rent of 0.00203 SOL is reclaimed).
- ✅ **More buys than sells**: It randomly buys twice with SOL in the wallet and sells all tokens after some time, making the number of buys twice as many as sells, thus creating more buy pressure.

## 🌟 Features
- ⚙️ **Automated SOL Distribution**: Distributes SOL to new wallets.
- 🔄 **Endless Buy and Sell Swaps**: Performs simultaneous buy and sell transactions.
- 🚀 **Swap with Jupiter V6**: Swap is performed with Jupiter V6 swap aggregator.
- 🛠️ **Configurable Parameters**: Allows customization of buy amounts, intervals, distribution settings, and more.

## 📋 Environment Variables

The bot uses the following environment variables. Rename the `.env.copy` file to `.env` and set the necessary variables.

```env
PRIVATE_KEY=                 # Private key for the main wallet
RPC_ENDPOINT=                # RPC endpoint for Solana
RPC_WEBSOCKET_ENDPOINT=      # RPC WebSocket endpoint for Solana

####### BUY SETTING #######
BUY_UPPER_PERCENT=60         # Higher percent limit of SOL that can be used to buy token in wallet
BUY_LOWER_PERCENT=30         # Lower percent limit of SOL (30 means, it buys with larger than 30% of SOL in wallet when buy)

BUY_INTERVAL_MAX=30          # Upper limit of seconds to wait after second buy
BUY_INTERVAL_MIN=2           # Lower limit of seconds (it waits from 2 to 30 secs after second buy before second buy)

SELL_INTERVAL_MAX=30         # Upper limit of seconds to wait after sell
SELL_INTERVAL_MIN=3          # Lower limit of seconds (it waits from 2 to 30 secs after sell to transfer SOL)

DISTRIBUTE_WALLET_NUM=4      # Number of wallets that run in parallel which makes volume (max: 20)

SLIPPAGE=50                  # Slippage in percent

TOKEN_MINT=7MFX5LySd9CdaD8irWnLLKanpDw6gxbBuhEg3qCHWc4C   # Mint address of token to increase volume

# 👤 Author


### Telegram: [@sealdevnut](https://t.me/sealdevnut)   


You can always find me here, for help, or for other projects.
