PuffCoin (PUF)
===========

Scrypt Hashcash PoW Template

## Linux
```
sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.3-dev libdb5.3++-dev git pyqt5-dev-tools libminiupnpc-dev zlib1g-dev libssl-dev
```

```
git clone https://github.com/puffcoin/puffcoin.git
cd puffcoin/src
make -f makefile.unix USE_UPNP=- (or makefile.osx if you're on Mac OS)
```
Now I'm ready to run it–in testnet mode and with a connection to my “other” computer. This is kind of tricky, because you need to start the coin on both computers with the -connect=x.x.x.x variable, each with the IP of the other PC:
```
./puffcoind -testnet -connect=x.x.x.x &
```

```
tail -f ~/.puffcoin/testnet3/debug.log
```

Now's a good time to brush up on the command line API calls syntax for interacting with the bitcoin client from this wiki page: https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_Calls_list
```
./puffcoind getinfo
```
Lovely, they line up and each have a single connection. Now we can make one of them (or both) begin generating coins by using the following command:
```
./puffcoind setgenerate true 16
```

### Qt4 GUI
```
sudo add-apt-repository ppa:rock-core/qt4

sudo apt update



sudo apt-get install qt4-qmake libqt4-dev build-essential libboost-dev libboost-system-dev \
    libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev \
    libssl-dev libdb5.3++-dev
```

## Mac OS
```
brew install autoconf automake libtool boost miniupnpc openssl@1.1 pkg-config protobuf qt
```

RPC PORT: 55883->8856
P2P PORT: 55884->8857

Testnet RPC Port: 45883->18856
Testnet P2P Port: 45884->18857
