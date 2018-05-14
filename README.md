# Zcash-miner
Funakoshi Equihash Cuda Miner

In release v2.3 added simple telemetry, fixed bugs wasting cpu, and improved stability.

In release v2.2 there is a jump in performance when using multiple gpu's (rig).

A breakthrough in performance has been implemented in release v2.1


Now Funakoshi-Miner is the fastest equihash solver.

## Can be used for mining:

     All equihash crypto coins: Zcash (ZEC), ZClassic (ZCL), ...
     via any of the supported pools (using SSL ports).

## Download Funakoshi Miner:

https://github.com/funakoshi2718/funakoshi-miner/releases

## No Virus attached:

    Ask McAfee

## Developer fee:

    1.5 %

## Speed:

    Over 500 solves per-second for GTX 1080 (without overclocking).
    
    Nvidia Pascal GPUs auto manage the clock depending on current load.
    
    Note: The statistical nature of the EquiHash algorithm causes
    the reported solves per second to change all the time.
    
    Each 15 seconds, Funakoshi solver logs its counters of hashes/secs and solves/secs (no cheating).
    Disregard the first reported speed (it is lower due to initial handshake with the pool).
    
    What's important to you is the pool measurement. From the pool you earn your money.
    Thus when you want to compare the speed of different miner programs ask the pool.
    Note that the pool also changes its estimation of miner speed all the time. So,
    you should take the avarage over time.
    
    The miner submits to the pool only a small portion of the solves (depending
    on the current target difficulty), and the pool estimates the miner speed.
    Each submit event is logged.
    
    Exactly 1.5 percent of all submited solves are used as developer fee.

## Supported pools:

    * Slushpool
    * Supernova
    * Flypool
    * Nanopool
    * Miningspeed
    * Coinmine
    * Miningpoolhub
    * Nibirupool
    * Luckpool

## Why SSL:

    Only secured ports (SSL connections) are supported.
    The reason for that is to protect the developer fee
    from being removed or redirected by proxy servers.
    
## Privacy:

    Funakoshi-Miner collects absolutely nothing about its users.
    Funakoshi-Miner opens only a single connection (to the user specified pool).
    This can be verified by using a sniffer or a firewall.
    Thus theoreticaly no data about users can be collected by the miner.
 
## Supported Operating Systems:

     * Windows-7 and above  (file: funakoshiMiner.exe)
     * The following Linux distributions: Ubuntu, Fedora  (file: funakoshiMiner)

## Tested on:

    * Windows 7, 10 
    * Ubuntu 16.4, 17.10
    * Fedora 26, 27

## Not working on:

    * Centos 6, 7

## Supported GPUs:

    * Nvidia Pascal and above

## Tested GPUs:

    * Nvidia GTX 1070
    * Nvidia GTX 1070 Ti
    * Nvidia GTX 1080
    * Nvidia GTX 1080 Ti
    * Titan Xp collector's edition

## Command-Line arguments:

    * Selected GPUs  : -cd 0 1 2 ... (selects which cuda-devices meaning GPUs to use - starting from 0)
                            The default when -cd arg is not specified is to use all found Nvidia gpu cards
                            (from v2.5).
    * Pool Address   : -l poolDomain:sslPort  (domain of pool server plus SSL port)
                            Port number is optional for: flypool, nanopool, suprnova, slushpool, coinmine.
                            For these pools the port number is auto fixed to the pool's ssl port when port
                            number is not specified or non ssl (from v2.5).
    * Pool User      : -u user.worker (your account name in the pool plus worker name)
    * Wallet Address : -u tWalletAddress.worker (your t wallet address plus worker name)
    * Max Temperature: -temp-max t1 t2 ... one value (celsius) per each GPU. When reached
                        solver suspends work until temp' drops to corresponding -temp-min
    * Min Temperature: -temp-min t1 t2 ... one value (celsius) per each GPU. When GPU temp'
                        drops from corresponding temp-max to temp-min work is resumed
    * Max Temp' all  : -temp-max-all t (defines same upper temperature bound for all GPUs).
    * Min Temp' all  : -temp-min-all t (defines same lower temperature bound for all GPUs).
    * Password       : -p x (usually not required)
    * Log File       : -f fileName (from release v0.9)
    * Telemetry      : -tele-port p  (activating http telemetry and listening on 127.0.0.1:p).

Notes:

    Pascal GPUs auto control clock speed to prevent the temperature from going too high.
    To be on the safe size you can set -temp-max to 83 and -temp-min to 75 (for example).

    Some pools require you to sign-up and define an account. For those pools the account-name
    is passed in the -u argument. Other pools require you to pass your 't' wallet address and
    for those pools your wallet-address is passed in the -u argument.
    
    When running the miner and Chrome (for viewing telemetry) on the same machine, Chrome may
    prevent Pascal GPUs from auto boosting. Thus it is recommended to run Firefox on the same
    machine or to run Chrome on another machine and use SSH tunnel.

## Usage example (on Linux & via Slushpool & using 1 Nvidia device):

    funakoshiMiner -cd 0 -l zec.slushpool.com:4443 -u userName.workerName

## Usage example (on Linux & via Supernova & using 1 Nvidia device & max GPU temperature):

    funakoshiMiner -cd 0 -l zec.suprnova.cc:2242 -u userName.workerName -temp-max 82 -temp-min 75

## Usage example (on Windows & via Flypool Europe server & using 3 Nvidia devices):

    funakoshiMiner.exe -cd 0 1 2 -l eu1-zcash.flypool.org:3443 -u tYourWalletAddress.workerName

## Usage example (on Linux & via Nanopool Europe server & using 2 Nvidia devices):

    funakoshiMiner -cd 0 1 -l zec-eu1.nanopool.org:6633 -u tYouWalletAddress.workerName

## Usage example (on Linux & Mining ZClassic via Miningspeed US server & using 3 Nvidia devices):

    funakoshiMiner -cd 0 1 2 -l us.miningspeed.com:3054 -u tYouWalletAddress.workerName

## Usage example (on Windows & Mining ZClassic via Coinmine & using 4 Nvidia devices):

    funakoshiMiner.exe -cd 0 1 2 3 -l zcl.coinmine.pl:7017 -u userName.workerName

## Usage example (on Windows & Mining Zcash via Miningpoolhub US-East server & using 4 Nvidia devices):

    funakoshiMiner.exe -cd 0 1 2 3 -l us-east.equihash-hub.miningpoolhub.com:20570 -u userName.workerName

## Usage example (on Windows & Mining ZEN via Nibirupool  & using 4 Nvidia devices):

    funakoshiMiner.exe -cd 0 1 2 3 -l zen.nibirupool.com:7777 -u znYourWalletAddress.workerName

## Usage example (on Windows & Mining Zcash via Luckpool  & using 4 Nvidia devices):

    funakoshiMiner.exe -cd 0 1 2 3 -l luckpool.org:3358 -u tYourWalletAddress.workerName
