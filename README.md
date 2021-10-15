-----
Vanitygen PLUS!  
-----

Note: For generating a Zcash or Zclassic address please see the Z repo: https://github.com/exploitagency/vanitygen_z

Forked from samr7/vanitygen and exploitagency/vanitygen-plus, then modified by socialruins to support RTM


**WARNING!** This program has not been thoroughly tested.  Please attempt importing an address first.  
Send a tiny amount you don't mind losing to the address.  Then perform a test spend.  
I will not be held liable for lost funds as a result of the use of this program.  
Also do not use this program for nefarious purposes!  I do not condone illegal activity.  
The chances of actually brute forcing an address is nearly impossible anyways.  

Be sure to report any issues or bugs and fixes, I am happy to accept pull requests!  
If you have an altcoin you would like to add please let me know.  

-----
Getting Started  
-----  

**For generating addresses using the CPU(slower) use: vanitygen !**  
**For generating addresses using the GPU(faster) use: oclvanitygen !**  

**NOTES:**	All arguments are case sensitive!  
	Address prefix must be at the end of the command.  
	oclvanitygen requires OpenCL and correct drivers.  

**Get a list of the supported Coins with:**  
Linux CPU: `./vanitygen -C LIST`  
Linux GPU: `./oclvanitygen -C LIST`  
Windows CPU: `vanitygen.exe -C LIST`  
Windows GPU: `oclvanitygen.exe -C LIST`  

A list of all the supported crypto coins will be output.  

Choose your coin from the list noting the ARGUMENT needed for the coin located in the left hand column.  
For RTM it is simply RTM.  For Bitcoin it is BTC.  Etc...  

**Now lets generate a RTM address with the prefix "RTEST":**  
Linux CPU: `./vanitygen -C RTM -o results.txt -i -k RTEST`  
Linux GPU: `./oclvanitygen -C RTM -o results.txt -i -k RTEST`  
Windows CPU: `vanitygen.exe -C RTM -o results.txt -i -k RTEST`  
Windows GPU: `oclvanitygen.exe -C RTM -o results.txt -i -k RTEST`  

 * `-C RTM` : Chooses the RTM coin  
 * `-o results.txt` : saves the matches to results.txt  
 * `-i` : case-Insensitive(do not add this flag to match exact case)  
 * `-k` : keep going even after match is found(do not add this flag to stop after the first match)  
 * `RTEST` : the address you are searching for(RTM addresses start with "R")  

Example output of above command:  
>Generating RTM Address                                                                    
>RTM Address: bTEST6jSVcid5MQAJBrGUR6MLDpdyb8oiQ  
>RTM Privkey: wrRxctq3f7A1zkpyWoZRifRk5eAC2UM9idh83SPLhz6gAFfqdL  

-----
Encrypting and Decrypting a vanitygen or oclvanitygen private key  
-----  
**Encrypting generated private key:**  
Linux: `./vanitygen -E password -C AC Aa`  
Windows: `./vanitygen -E password -C AC Aa`  
*For GPU use "oclvanitygen" in place of "vanitygen"*  

 * `-C AC Aa` Choose AsiaCoin and address prefix "Aa"  
 * `-E password` Encrypt key with password as "password",  
**NOTE:** It is more secure to use option `-e` with no trailing password,  
then vanitygen prompts for a password so theres no command history.  
Also please choose a stronger password than "password".  

>Generating AC Address  
>Difficulty: 23   
>AC Pattern: Aa                                                                      
>AC Address: Aa853vQs6QGrTuTHb7Q45tbeB8n4EL47vd  
>AC Protkey: yTYFUWAsgFmMxCbKtu3RdrrJXosZrjxiQFA2o43neB4jPpfLe5owNNrteTs8mpvua8Ge  

**Decrypting generated ProtKey with Keyconv:**  
Linux: `./keyconv -C AC -d yTYFUWAsgFmMxCbKtu3RdrrJXosZrjxiQFA2o43neB4jPpfLe5owNNrteTs8mpvua8Ge`  
Windows: `keyconv.exe -C AC -d yTYFUWAsgFmMxCbKtu3RdrrJXosZrjxiQFA2o43neB4jPpfLe5owNNrteTs8mpvua8Ge`  

 * `-C AC` Specifies AsiaCoin  
 * `-d` means decrypt the protected key of "yTYFUWAsgFmMxCbKtu3RdrrJXosZrjxiQFA2o43neB4jPpfLe5owNNrteTs8mpvua8Ge"  

>Enter import password:  --- Enter "password" or whatever you specified as password and press enter  
>Address: Aa853vQs6QGrTuTHb7Q45tbeB8n4EL47vd  
>Privkey: 66GRP2W5H4sWbgrBRAuPc3qZxUtP5boubJ9N2M5wZio6fhWjzbr  

Current List of Available Coins for Address Generation  
-----
|**Argument(UPPERCASE)** | **Coin** | **Address Prefix**  |
| --------------------------------------- | -------------------------------------------- | ------------ |
|42 | 42coin | 4  |
|AC | Asiacoin | A  |
|ACM | Actinium | N |
|AIB | Advanced Internet Block by IOBOND | A  |
|ANC | Anoncoin | A  |
|ARS | Arkstone | A  |
|ATMOS | Atmos | N  |
|AUR | Auroracoin | A  |
|AXE | Axe | P |
|BLAST | BLAST | B  |
|BLK | Blackcoin | B  |
|BWK | Bulwark | b  |
|BQC | BBQcoin | b  |
|BTC | Bitcoin | 1  |
|TEST | Bitcoin Testnet | m or n  |
|BTCD | Bitcoin Dark | R  |
|CARE | Carebit | C  |
|CCC | Chococoin | 7  |
|CCN | Cannacoin | C  |
|CDN | Canadaecoin | C  |
|CLAM | Clamcoin | x  |
|CNC | Chinacoin | C  |
|CNOTE | C-Note | C |
|CON | PayCon | P  |
|CRW | Crown | 1  |
|DASH | Dash | X  |
|DEEPONION | DeepOnion | D  |
|DNR | Denarius | D  |
|DGB | Digibyte | D  |
|DGC | Digitalcoin | D  |
|DMD | Diamond | d  |
|DOGED | Doge Dark Coin | D  |
|DOGE | Dogecoin | D  |
|DOPE | Dopecoin | 4  |
|DVC | Devcoin | 1  |
|EFL | Electronic-Gulden-Foundation | L  |
|EMC | Emercoin | E  |
|EXCL | Exclusivecoin | E  |
|FAIR | Faircoin2 | f  |
|FLOZ | FLOZ | F  |
|FTC | Feathercoin | 6 or 7  |
|GAME | GameCredits | G  |
|GAP | Gapcoin | G  |
|GCR | Global Currency Reserve | G  |
|GRC | GridcoinResearch | R or S  |
|GRLC | Garlicoin | G  |
|GRN | GreenCoin | G  |
|GRS | Groestlcoin | F  |
|GRV | Gravium | G  |
|GUN | Guncoin | G or H  |
|HAM | HamRadiocoin | 1  |
|HBN | HoboNickels(and BottleCaps) | E or F  |
|HODL | HOdlcoin | H  |
|IC | Ignition Coin | i  |
|IXC | Ixcoin | x  |
|JBS | Jumbucks | J  |
|JIN | Jincoin | J  |
|KMD | Komodo (and assetchains) | R  |
|KORE | Kore | K  |
|LBRY | LBRY | b  |
|LEAF | Leafcoin | f  |
|LMC | LomoCoin | L  |
|LTC | Litecoin | L  |
|MGD | MassGrid | M  |
|MMC | Memorycoin | M  |
|MNC | Mincoin | M  |
|tMNC | Mincoin Testnet | m or n  |
|MNP | MNPCoin | M  |
|MOG | Mogwai | M  |
|MONA | Monacoin | M  |
|MUE | Monetary Unit | 7  |
|MYRIAD | Myriadcoin | M  |
|MZC | Mazacoin | M  |
|NEET | NEETCOIN | N  |
|NEOS | Neoscoin | S  |
|NLG | Gulden | G  |
|NMC | Namecoin | M or N  |
|NVC | Novacoin | 4  |
|NYAN | Nyancoin | K  |
|OK | OK Cash | P  |
|OMC | Omnicoin | o  |
|PIGGY | Piggycoin | p  |
|PINK | Pinkcoin | 2  |
|PIVX | PIVX | D  |
|PKB | Parkbyte | P  |
|PND | Pandacoin | P  |
|POT | Potcoin | P  |
|PPC | Peercoin | P  |
|PTC | Pesetacoin | K  |
|PTS | Protoshares | P  |
|QTUM | QTUM | Q  |
|RBY | Rubycoin | R  |
|RDD | Reddcoin | R  |
|RIC | Riecoin | R  |
|ROI | ROIcoin | R  |
|RTM | Raptoreum | R |
|RVN | Ravencoin | R |
|SCA | Scamcoin | S  |
|SDC | Shadowcoin | S  |
|SKC | Skeincoin | S  |
|SPR | Spreadcoin | S  |
|START | Startcoin | s  |
|SXC | Sexcoin | R or S  |
|TPC | Templecoin | T  |
|TUX | Tuxcoin | T  |
|UIS | Unitus | U  |
|UNO | Unobtanium | u  |
|VIA | Viacoin | V  |
|VIPS | VIPSTARCOIN | V  |
|VPN | Vpncoin | V  |
|VTC | Vertcoin | V  |
|WDC | Worldcoin Global | W  |
|WKC | Wankcoin | 1  |
|WUBS | Dubstepcoin | D  |
|XC | XCurrency | X  |
|XPM | Primecoin | A  |
|YAC | Yacoin | Y  |
|YTN | Yenten | Y  |
|ZNY | BitZeny | Z  |
|ZOOM | Zoom coin | i  |
|ZRC | Ziftrcoin | Z  |
