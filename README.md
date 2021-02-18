# MasternodeSetup


### Local wallet configuration

### Send the coins to your wallet. Open Console (Tools => Debug console)
1. Create a new address. `getnewaddress MN1`
2. Send exactly 100000.00 coins to the generated address. (Send all coins in one transaction, fees should be paid additionally on top on 100k amount)
3. Wait for the at least 1 confirmation of the transaction.
4. Generate a new masternode private key by running the following command in wallet debug console `masternode genkey`.
5. Take txID of collateral transaction by running the following command in wallet debug console `masternode outputs`. 
6. Do not close console, or copy results to any place.

Recommended server configuration:  
   - OS: Ubuntu 16.04 or higher
   - Memory: 1GB
   - Storage: 10GB minimum free space


### Add masternode on the desktop wallet

1. Open your local wallet 
2. Open 'masternode.conf' file in text editor from the main/top menu (Tools->Open Masternode Configuration File)
3. Add new line and construct the new Masternode configuration by copying your masternode private key, transaction id and transaction index
   
  *It should look like:* 
  MN1 [IP address]:30001 masternodeprivkey [100K desposit transaction id. 'masternode outputs'] [100K desposit transaction index. 'masternode outputs']
   
  *For example:* 
  `MN1 192.168.1.1:30001 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0`

   - Label: `MN1`
   - IP Address and port: `192.168.1.1:30001`
   - Private key: `93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg`
   - Transaction ID: `629dc27b721f57c97550868cac9f7e41049d12cce8ac344732b7f74a9fc81815`
   - Output index:  `0`

  

4. Save file (masternode.conf)
5. Restart wallet.
6. You must wait 15 confirmations of collateral transaction (100000.00 TRTT)


### VPS wallet configuration

OS requirements: Ubuntu 16.04 or higher

Run this command as root user to start the installation, then follow the instructions:

```
bash <( curl https://raw.githubusercontent.com/Trittium/MasternodeSetup/master/install.sh )
```
