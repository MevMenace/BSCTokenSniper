* BSCTokenSniper v1.4 Beta is available for testing, please check the telegram link for a link to the testing group where you can find the zip file.

* v1.3 and earlier versions are now abandoned in favour of v1.4. The code isn't available on github yet and more testing still needs to be done but it is mostly reliable.

* This description is still a bit of a mess as new features are still being added and tested constantly to v1.4. Some parts of the description are irrelevant or outdated.

<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.S
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
<!--[![Contributors][contributors-shield][contributors-url] -->
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
<!--[![LinkedIn][linkedin-shield]
[linkedin-url]-->

## Environment 
<p align='left'>
  <img src='https://img.shields.io/badge/OS-Windows10-007ef9?style=for-the-badge&logo=microsoft' alt='Windows11'>
  <img src='https://img.shields.io/badge/OS-Linux-blue?style=for-the-badge&logo=linux' alt='Linux'>
  <img src='https://img.shields.io/badge/OS-Android12-green?style=for-the-badge&logo=android' alt='Android'>
  <img src='https://img.shields.io/badge/IDE-VSCode%20-44b26f?style=for-the-badge&logo=visualstudiocode&logoColor=44b26f' alt='VSCode'>



<!-- PROJECT LOGO -->
<!--
 <br />
 <p align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a> -->

  <h3 align="center">BSCTokenSniper</h3>

  <p align="center">
    A sniper bot written in Python to buy tokens as soon as liquidity is added and sell on later when the price increases.
    <br />
    <a href="https://github.com/BytePhoenixData/BSCTokenSniper/"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/BytePhoenixData/BSCTokenSniper/archive/refs/heads/main.zip">Download zip</a>
    ·
    <a href="https://github.com/BytePhoenixData/BSCTokenSniper/issues">Report Bug</a>
    ·
    <a href="https://github.com/BytePhoenixData/BSCTokenSniper/issues">Request Feature</a>
    ·
    <a href="https://t.me/joinchat/7TtO_mvE90UzYmM0">Telegram Group</a>
  </p>
</p>



<!-- Snipe the shit -->
<details open="open">
  <summary>Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About the project</a>
      <ul>
        <li><a href="#built-with">Built with</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#operating-system">Operating System</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
<!--    <li><a href="#usage">Usage</a></li> -->

<li><a href="#configuration-file">Configuration File</a></li>
    <li><a href="#mini-audit">Mini audit</a></li>
    <li><a href="#things-to-note">Things to note</a></li>
    <li><a href="#common-errors-and-how-to-fix-them">Common errors and how to fix them</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li>
        <a href="#contributing">Contributing</a>
    </li>
    <li>
      <a href="#version">Versions</a>
      <ul>
        <li><a href="#v13">v1.3 Beta</a></li>
        <li><a href="#v12">v1.2</a></li>
        <li><a href="#v11">v1.1</a></li>
      </ul>
    </li>    
    <li><a href="#risks">Risks</a></li>
    <li><a href="#faqs">FAQs</a></li>
    <li><a href="#donations">Donations</a></li>
    <li><a href="#things-to-do--improve--fix">Things to do / improve / fix</a></li>
  
  </ol>
</details>


<!-- ABOUT THE PROJECT -->
## About The Project

<!--[![Product Name Screen Shot][product-screenshot]](https://example.com)-->

The aim of BSC Token Sniper is to buy new tokens with a specified amount of BNB, with the aim of the price rising. Once the bot detects a PairCreated event, it is able to check the token (mini audit). It then later sells the token when the price is high enough.

 It can check if:
-	Token's source code is verified.
- Token is a honeypot
- Token is a test

The user can decide whether to enable the mini audit or turn it off (bear in mind you will likely be investing in a lot of scams / rugpulls / honeypots if you don’t).
Once the token has/hasn't been through a mini audit the bot will then attempt to buy X amount of tokens with the specified amount of BNB.
The bot will buy the tokens directly through the Binance Smart Chain using the PancakeSwap v2 router and factory address, so it is much quicker than the PancakeSwap web interface.

By avoiding web interfaces & Metamask and directly with Ethereum & EVM Nodes you can snipe tokens faster than any of the web-based platforms. This allows tokens to be sniped almost instantly. During our testing we found the bot would typically be within the first 3 buy transactions of all tokens it finds.
The bot buys the tokens using the user's wallet address and private key. This information is kept secure, is only stored locally on your computer, and is only ever used to buy tokens (look through the code to see for yourself).

The bot does not incur any additional fees except from the dev fees on profit made, only fees are BSC network transaction fees and PancakeSwap fees.

From v1.3 onwards, the bot's source code will be heavily obfuscated and compiled to prevent people stealing code and scammers trying to bypass this system as this has happened before. If you have concerns about the security of this bot then you should create a new wallet with a small amount of BNB and use that wallet's details in the config file. If you make a profit then that can be transferred to your main wallet.

How do the developers make money? 

From v1.4 onwards the bot will have a tax on profit made: in the launch sniper a tax of 5% will be auto sent to the dev's wallet when a profit is made. For the multi sniper, a tax of 10% is used. The tax is only sent when profit is made and there is no dev fees if you break even or lose money. This allows us to offer everyone the bot free of charge, as we believe it isn't fair that some developers are charging often $1000's for similar bots. The fees made massively support the project and allow us to test out new features.



© 2021

### Built With

This project is built with:

* [Python3.9](https://www.python.org/downloads/)
* [Web3](https://web3py.readthedocs.io/en/stable/)
* [BscScan Api](https://bscscan.com/apis)


<!-- GETTING STARTED -->
## Getting Started

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple steps.

### Prerequisites

BSCTokenSniper is completely free to use and there are no setup costs.

- Windows, Mac, Linux or Android OS (windows preferred)
- a reasonably fast internet connection
- Python 3 or later installed (ideally 3.9.7 or later)
- BscScan API key (free of charge, create an account on BscScan and generate a free API key)
- BSC wallet address and private key (not seed phrase)
- a private node (generate one free of charge from moralis.io - steps are available further below)
- enough BNB in your wallet to snipe tokens

### Operating System

The bot can be run on the following OS's:
  1.  Windows
  2.  Linux 
  3.  Mac 
  4.  Android (more advanced) 

## Installation

### Windows

1. Download git [Git](https://git-scm.com/)
2. Download python [Python3.9](https://www.python.org/)
3. Clone the repo: 

      ```sh
      git clone https://github.com/BytePhoenixData/BSCTokenSniper.git 
      ```

4. Go to repo directory

5. and run : 
      ```sh
      cd BSCTokenSniper
      ```
6. Install Web3:

      ```sh
      pip install web3
      ```

   If you facing an error during the web3 installation, you may need the following microsoft visual studio build tool.
   use this [link](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019).
   
## Linux User
   
  Install the package With 

  ```sh 
  sudo
  ```
Debian / Ubuntu: 
1. install all dependencies using command below.

```sh
apt install git && apt install python3-pip && pip install web3
```

2. Clone repository and install web3

```sh
git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper && pip install web3
```

Fedora Linux / Centos
 1. install all dependency using command below.

```sh
dnf install git && dnf install python3-pip && pip install web3 
``` 

2. Clone repository and install web3

```sh
git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper && pip install web3
```

Arch Linux
 1. install all dependency using command below.

 ```sh
 pacman -S git && pacman -S install python3-pip && pip install web3 
 ``` 

2. Clone repository and install web3

```sh
git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper && pip install web3
```

- If you all find the error try this bellow command and may fix your problem.

```
pip uninstall web3 && pip install web3
```

or

```sh
pip install -U web3
```

## Mac (Intel / Universal)

1) Make sure python 3 is installed

- open terminal window
- type : python3 --version
- if you get an error message and python3 isn't installed, you need to add it.

- go to https://www.python.org/ and install latest version of python for mac

- in terminal window one last check to see you have Python 3 installed
- type : python3 --version
- should see Python 3.9.7 showing

2) Install web3

- open terminal window
- type : pip3 install web3
- wait while web3 installs
- NOTE : part way through the install you may be prompted to install xcode
- if this happens carry on and install xcode
- some errors may be now showing in terminal window
- go back to terminal and type : pip3 install web3
- after this (xcode installation) web3 should be good to go

3) Edit config.json

- recommended opening a fresh metamask wallet for sniper testing
- Edit lines 2+3 of config.json with your wallet address + private key
   "walletAddress": "put_your_wallet_address_here",
   "walletPrivateKey": "put_your_private_key_here",
- To get private key from metamask click the 3 dots just under the favicon
- Select 'Account Details'
- Select 'Export Private Key'

- Add Speedy Node to line 13
   "bscNode": "put_your_mainnet_url_here",
- https://admin.moralis.io/register to get your free speedy node
- Go to 'Speedy Nodes' on the left
- Choose yellow BSC Network icon on right
- Click Endpoints
- Take key from top line and paste in (address must start with wss://)

- Add your BscScan private API key to line 14
   "bscScanAPIKey": "put_BSC_API_key_here",
- To get a free API key just register at https://bscscan.com/
- Go to API-KEYs menu option on left
- Click blue '+Add' button next to text 'My API Keys'
- Choose name for API key (can be anything)
- Copy key value from 'API-Key token' column


4) Run script 

- Get in terminal window
- Make sure you are in the directory of the script before you run it.
- type : python3 BSCTokenSniper.pyc

## Android
1. Install Termux [Link](https://play.google.com/store/apps/details?id=com.termux&hl=en&gl=US)
2. Update

  ```sh
  pkg update && pkg upgrade
  ```

   3. Install dependency

```sh 
pkg install git python3 python3-pip
```

   4. Install web3 

```sh
pip install web3
```

```sh
pip install -U web3
```

   5. Clone the repo using git

```sh
git clone https://github.com/BytePhoenixData/BSCTokenSniper.git && cd BSCTokenSniper
```

Note:
You may encounter an error when installing web3 in android. You should install the dependency needed by web3 manually using pip.
The web3 version that work for this bot is web3 5.x.x, if your web3 is 3.x.x or lower then the bot will not work.
 
## Run python script

Assuming you are in BSCTokenSniper Directory:
run 

```sh
python3 BSCTokenSniper.py
```

for V1.3 or latest, you should install Python3.9

# Configuration File

When you download the bot, you will find a config.json file. This is where you need to add the following data.

* walletAddress: your BSC wallet address (e.g., Metamask)
* walletPrivateKey: your private key of your wallet address (your private key is kept safe and not shared in any other place: DO NOT share with anyone else)
* amountToSpendPerSnipe: The amount in BNB you want your wallet to spend on every new token. (e.g., 0.00025 means a new snipe will spend 0.00025 BNB on the new token)
* transactionRevertTimeSeconds: Time to spend before transaction reverts. Recommended to leave at default.
* gasAmount: amount of max gas to use per transaction. Recommended to leave at default.
* gasPrice:  max price of gas to use per transaction. Recommended to leave at default.
* bscNode: Address for custom BSC node. Recommended to leave at default.
* bscScanAPIKey: Your API key from BscScan.
* liquidityPairAddress: Address for liquidity pairs. Recommended to leave at default.
* minLiquidityAmount: The minimum amount of liquidity in BNB in a token that the bot will purchase. The bot detects the amount of BNB in a newly detected token, and only buys * tokens that have liquidity higher than the amount specified in the config file. Set to -1 to disable.
* observeOnly: enabling this will bypass the mini audit feature which allows you to observe how the bot audits tokens. Recommended to try this at the start to make sure the bot can scan for new tokens.

# Mini audit

The bot has an optional mini audit feature which aims to filter some of the scam coins (eg. wrongly configured, honeypots). Obviously, this is not going to be as good as a proper audit (eg. CertiK) but at least the coins the bot will buy will be higher quality and if you enable the options, you should be able to sell the tokens later on (provided it hasn’t been rugged).

The following json entries are for mini audit. Set all to false to disable mini audits, although beware you will probably be buying a lot of scam coins.
checkSourceCode: checks if source code is verified. This function is needed for all the other functions so if you disable this be sure to disable all the other audit options. Recommended. v1.3 onwards will use RugDoc tool to check for honeypots and high fee tokens.

checkValidPancakeV2: checks if the correct PancakeSwap v2 router address is used in the code. Be aware some contracts may externally set their router address so this function may reject a potentially good token. Not recommended.

checkMintFunction: checks if a mint function is present in the code. Recommended.

checkHoneypot: checks the code to see if it might be a honeypot (where you can buy tokens but cannot sell). Recommended.

checkPancakeV1Router: checks to see if the PancakeSwap v1 router address is used in the code. You will not be able to sell the tokens later on if PCS v1 router address is used. Highly recommended.

checkForTest: checks for tokens that are named 'test'. Often these tokens don't work or are not an investment opportunity.

Note: be very careful when editing config.json and make sure to not alter the syntax. For mini audit options, either use “True” or “False” making sure to capitalise the 1st letter. Any other spelling will not work.

# Things to note

-	Do not worry if you are not seeing any new tokens being detected. There are often around 10-20 new tokens being created per minute but that can vary quite a lot. Sometimes no new tokens may be detected for a few minutes.

- make sure your input a private key (eg. 7d655977921bf61e25d29075712ec7aace28b8d71aa4c7ddd5d403e28efed8a9) into the program and not a seed phrase.

-	The bot only buys tokens whose liquidity is paired with Wrapped BNB (WBNB). You could alter the code to buy tokens paired with another currency if you wanted.

-	Please check that you have enough BNB in your wallet to afford sniping new tokens. If you don’t the bot will not work.
-	Please be careful when editing the config.json file. If you delete a comma or quotation mark etc. the bot will not work and throw an error.
-	To launch the bot, run the ‘launchBSCTokenSniper.bat’. The bot should then open in a cmd window and load.
-	Don’t left click in the cmd window as it will enable select mode and stop the output (you will see ‘Select’ in the title). If this happens right click your mouse to deselect it. 

To use other version you need to go to the directory needed and run the python script.


# Common errors and how to fix them

```Incorrectly configured config.json file```
This means the bot cannot read your config.json file. Check that it is syntactically correct with no missing symbols, all fields are 
filled out correctly and restart the program.

```Cannot connect to BSC node```
The bot cannot connect to the BSC node. Make sure that you are using a valid BSC websocket node (starting with wss://) and restart.

```ValueError: {'code': -32000, 'message': 'transaction underpriced'}```
You are using too low gas. Increase gas price / limit and restart.

```websockets.exceptions.ConnectionClosedError: code = 4040 (private use), reason = Draining connection```
The bot cannot connect properly to the node. Make sure the node not overloaded / your internet connection is good enough / you dont have firewall software interfering with the bot / try a different node and try again.

```RuntimeError: Bad magic error in .pyc file```
Your python version is too low. Use the latest version of python (3.9.7 has been tested and works well) and uninstall older versions of python.

```ValueError: {'code': -32000, 'message': 'insufficient funds for gas * price + value'}```
You do not have enough BNB in your wallet to snipe with, or you dont have enough of the liquidity paired token specified (eg. BUSD). Make sure your wallet has enough BNB / specified pair token and try again.

```ModuleNotFoundError: No module named 'web3'```
You do not have web3 installed or python does not recognise it. Install it with ```pip install web3``` in cmd line or reinstall if faulty.

```ModuleNotFoundError: No module named 'keyboard'```
You do not have keyboard module installed or python doesn't recognise it. Install it with ```pip install keyboard``` in cmd line or reinstall if faulty.

```PancakeLibrary: INSUFFICIENT_INPUT_AMOUNT```
Haven't found solution yet, come back later for solution.








<!-- USAGE EXAMPLES -->
<!--
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

-->


## Versions
Here are the latest versions. v1.4 is being worked on and will be released shortly.
### V1.3

#### v1.3 and below are abandoned in favour of v1.4, it is available in telegram group's pinned messages.

Improvements:

- Can queue a token if 2 are detected (rare but can happen)

- PCS factory address now editable from config.json

- detects if pancakeswaprouteraddress is in code more accurately (previously would ignore if text was different upper or lower case from config file)

- Users are now warned if config.json file is incorrectly configured and program exits.

- program automatically detects whether os is windows or not and applies appropriate title code (same script should work universally on any os with python)

- rugdoc API integrated. This will reject tokens that are dodgy, have high fees (over 10%) and honeypots.

- antibot delay implemented. This allows you to delay purchase for x amount of seconds specified in config file, as some bots will have a very high tax in the first
few blocks

- prevents tokens being bought that are same as previous

- autosell feature now working (STILL GOT ISSUES WITH IT - SOMETIMES GIVES ERRORS)

- some bits of code tidied up

### V1.2

Improvements:

- Added code blacklist (code_exceptions.txt): the program will ignore any program with code that is in this file

- Added min liquidity checker (won't buy token unless it has certain amount of liquidity) - edit threshold in config.json

- Fixed issue with buy - saying transaction failed when it was fine

- Changed to websocketprovider instead of httpprovider - alot more reliable and also faster, should be less crashing as well

- You can now change websocketprovider node in config.json instead of being in code

- Some bits of code tidied up

(SpecifiedTokenSniper is not updated and still in v1.1 folder, will be integrated in main program and in GUI in future)

Also massive thanks to Christiaan Van AS, Muhammed Nurhaqqin and everyone else on Telegram for development and support with this project.



### V1.1

Just a few improvements, but largely untested. Would greatly appreciate if you could give me feedback. Thanks!

Improvements:

- Added 'check for test' to ignore tokens which have 'test' in their name.

- Added 'try' and 'catch' clauses for buy token and listenForTokens function to avoid exiting with error

- Added function to detect WBNB pair in either pair 1 or pair 2 (currently only detects WBNB in pair 1 which potentially ignores alot of tokens)

- Created 'SpecifiedTokenSniper' script - this allows you to snipe a specific token at launch as soon as it gains liquidity, if you know the token address. 
If you're lucky (like the refinable bot) you could make huge amounts of money.

- You can now pick what liquidity pair address you would like. It is set to WBNB by default (recommended) but you can change to anything if you wish.

New config.json entries:

- "checkForTest": choose whether "test" is in the token's name. Only enable if checkSourceCode is enabled. Recommended.

- "liquidityPairAddress": Leave it unless you want to change the liquidity pair address.


### BSCTokenSniper v1.0
A bot written in Python to automatically buy tokens on the Binance Smart Chain as soon as liquidity is provided.

BSCTokenSniper is a bot written in Python to detect new PairCreated events in the Binance Smart Chain (when a liquidity pair has been created) and buy the token. It is quite reliable and works well but it is the first version, so if you find any problems/improvements/suggestions please let me know by raising an issue.




# FAQs

I've sniped loads of coins - but how can I check which ones have made a profit?
-	For this go to poocoin.app, click 'Wallet' and connect your Web3 wallet that you are using for your bot (eg. Metamask).
-	It will then give you the list of tokens in your wallet and show you which ones have made the highest profit.
-	Click the descending arrow next to the balance tab to show highest to lowest tokens value.
-	Then you can manually sell the tokens which have made you a profit on PancakeSwap.

I keep getting ‘Transaction failed’ – what’s going on?
Either:
-	Gas amount / price too low
-	Wallet address / private key incorrect
-	Not enough BNB to pay for the token and TX fees

The bot isn’t sniping that fast (eg. couple seconds between detection and buying)
- This is mainly due to internet speed and computer processing power. 

# Risks

Investing in BSC tokens / shitcoins is risky and be aware you could lose all your money. For this reason, do not invest more money than you are prepared to lose.
It is pretty much impossible to snipe bots very early and be sure it isn’t a rug pull. When people create tokens in most situations, they will manually create liquidity in PancakeSwap. This is when the bot will detect the token. If they burn / lock liquidity, they will then usually send their LP tokens manually to a deadcoin address or put them in a liquidity locker. Therefore, you can’t immediately snipe the tokens with 100% certainty they aren’t rugpulls.

The mini audit feature can’t be 100% accurate but aims to filter out the majority of scams / hacks and reduce the chance of losing your money.
If a programmer creates token code in a unique way, they may be able to bypass detection although this is generally quite rare, as the majority of tokens are forks of big projects with very little of the code having been changed e.g., Safemoon.

# Things to do / improve / fix

 - Look into rugpull detection (in development) - unfortunately current there's so many scams on BSC. We are looking for the best way to filter out scams and get the gems
 
- Modify bot to work on different blockchains eg. Ethereum, Polygon

- Improve reliability: the program can sometimes unexpectedly freeze / quit. This is being investigated.

- Allow user to set slippage percentage - currently bot just selects the best slippage automatically 


## Donations

Any donation of any token is massively appreciated and helps alot with the development of the project.

| Dev | BSC Address |
|:---:|:---:|
| BytePhoenix (founder) | 0x17fC36Fd733D2b2762c020e34E45b5C95723c9b3 |
| CVA_CryptoPlayground | 0x3a5A12dfffD327AFdaC7BEA60ECF7A48410E873a |
| Geeks121 | 0xbeeF1858CBDdb48319893b028bE9D914d45f51D9 |


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
<!--[contributors-shield]: https://img.shields.io/github/BytePhoenixData/BSCTokenSniper.svg?style=for-the-badge
[contributors-url]: https://github.com/BytePhoenixData/BSCTokenSniper/graphs/contributors -->
[forks-shield]: https://img.shields.io/github/forks/BytePhoenixData/BSCTokenSniper.svg?style=for-the-badge
[forks-url]: https://github.com/BytePhoenixData/BSCTokenSniper/network/members
[stars-shield]: https://img.shields.io/github/stars/BytePhoenixData/BSCTokenSniper.svg?style=for-the-badge
[stars-url]: https://github.com/BytePhoenixData/BSCTokenSniper/stargazers
[issues-shield]: https://img.shields.io/github/issues/BytePhoenixData/BSCTokenSniper.svg?style=for-the-badge
[issues-url]: https://github.com/BytePhoenixData/BSCTokenSniper/issues
[license-shield]: https://img.shields.io/github/license/BytePhoenixData/BSCTokenSniper.svg?style=for-the-badge
[license-url]: https://github.com/BytePhoenixData/BSCTokenSniper/blob/master/LICENSE.txt
<!-- [linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555 -->
<!--[linkedin-url]: https://linkedin.com/in/othneildrew -->
[product-screenshot]: images/screenshot.png
