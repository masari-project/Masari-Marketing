*DATE: 26Apr2019*

*Created by JeuTheIdit*

This is a guide on how to securely store Masari in a paper wallet using either a hot computer or bootable usb drive.

Creating a paper wallet can be completed in a variety of ways, each providing different security levels. In this guide we will focus on two:
1. Simply disconnecting from the internet and running the generator on your every-day hot computer (least secure).
2. Creating a bootable USB stick with any Linux distro, disconnecting from the internet, booting from the USB stick, running the generator, and destroying the USB stick afterwards (more secure).

For most users, option 1 will suffice and your MSR will be fairly secure. However, if you generate a wallet while your computer is infected, you risk losing your funds. Option 2 is a more secure option for a few reasons:

* You are generating on an OS that you know is clean (non-infected).
* Assuming you wipe (or even better, destroy) the USB afterwards, that OS and paper wallet data will never be able to hit the internet.

This, however, doesnt prevent any hardware based attacks such as [Spectre and Meltdown](https://ds9a.nl/articles/posts/spectre-meltdown/), since you are using the same computer hardware on the hot OS. This is where  an air-gapped computer comes in, where you can generate a paper wallet or complete [offline transaction signing](https://www.reddit.com/r/Monero/comments/68qt9f/reminder_how_to_use_offline_signing/) on a machine that was never, nor ever will be, connected to the internet. Any point of entry for attack is prevented, barring a physical attack. This method will not be covered.

It should go without saying, but it is up to **you** to determine threat level and act accordingly.

You can get [printable paper wallets here](https://github.com/masari-project/Masari-Marketing/tree/master/Paper%20Wallets)
. 


## Using A Hot Computer (least secure):

**Skill Required:**

This option requires a moderate understanding of Masari and little computer knowledge.

**Hardware/Software Required:**

*1x Hot computer*

*OPTIONAL: 1x USB drive*

*1x Paper*

*1x Pen*

*1x Hash Utility.  I personally use either the built in [Windows 10 utility](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/certutil#BKMK_hashfile) or Ubuntu utility (https://help.ubuntu.com/community/HowToSHA256SUM). An easy to use and well known GUI utility is [QuickHash](https://sourceforge.net/projects/quickhash/).

**Generating the Wallet:**

1. Download the paper wallet generator zip from here: https://github.com/masari-project/masari-wallet-generator
2. Disconnect from the internet.
3. *Optional but recommended:* Check that the sha256 hash matches the following: 8897902B264D143EBC4705B9D787676C2425A68255397C359B6E2B8CCF78966A
4. Unzip and open `masari-wallet-generator.html`.
5. Click "GENERATE WALLET", which will generate four important items:
 * Public address: Used to recieve funds to the wallet. You give this to anyone who will be sending funds to your wallet.
 * Mnemonic seed: A method of storing the entire wallet that is easily recognizable to humans. This is all you need to restore your wallet at a later date.
 * Private spend key: Used to send funds from the wallet.
 * Private view key: Used to view transactions entering the wallet.  Commonly this is used to setup a [view-only wallet]() on a hot computer which can see incoming transactions live on the blockchain as they are sent to your cold wallet.
6. On a piece of paper, **NEATLY** write down your *mnemonic seed*, *private spend key*, *private view key*, and *public address*.
 * Either check 3 times that everything is correct or physically write everything 3 times.
 * **DO NOT LOSE THIS PIECE OF PAPER**. It alone contains the information required to access your Masari, and recover your wallet.
7. OPTIONAL: Copy/paste (do not type) your *public address* and *private view key* to a text file and save on a USB stick^1.  This can be used to more easily create a view only wallet later.

(1) This USB can be used with relative abandon.  The only consequence being, if someone gets a hold of your address and private view key, they could view the funds in your wallet.  They would not be able to, however, spend any funds.

8. Delete any copy of the wallet generator left over on the device you used.
9. Restart your computer.
10. Reconnect to the internet.
11. Congrats! You sucessfully generated a paper wallet.

## Booting With a Linux USB (more secure)

**Skill Required:**

This option requires a moderate understanding of Linux, Masari, network security, and general computer knowledge.

**Hardware/Software Required:**

*1x Hot Computer*

*OPTIONAL: 1x Air-gapped Computer (instead of the hot computer)*

*2x USB Stick (3+ is helpful)*

*1x Paper*

*1x Pen*

*1x Hash Utility.  I personally use either the built in [Windows 10 utility](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/certutil#BKMK_hashfile) or Ubuntu utility (https://help.ubuntu.com/community/HowToSHA256SUM). An easy to use and well known GUI utility is [QuickHash](https://sourceforge.net/projects/quickhash/).

**Generating the Wallet:**

You can either download a user created pre-zipped file that has all the tools you need using [this guide](https://github.com/JeuTheIdit/Masari-usb-cold-wallet-gen), or follow the instructions below to download the required programs yourself.

1. On your computer, navigate to https://github.com/masari-project/masari-wallet-generator and download the zip file by clicking the green box labeled "Clone or download" and then "Download ZIP". 
2. Check that the sha256sum of the downloaded zip file is `8897902B264D143EBC4705B9D787676C2425A68255397C359B6E2B8CCF78966A`.
3. Download your prefered program to format and create bootable USB flash drives.  I personally use [Rufus](https://rufus.ie/) because it is open source. Checking the sha256sum is recommended.
4. Donwload your prefered Linux iso (Linux Mint is recommended for people who are used to Windows). Checking the sha256sum is recommended.
5. Format your USB stick (if the USB is not new) and create a bootable USB drive with the linux iso.
6. Copy the checked wallet generator onto the newly created USB drive.
7. Unplug / disable internet access, and shut down the computer.
8. After booting into the Linux distro on your hot computer (or better yet, on an air-gapped machine), navigate to the wallet generator. Paranoid users can double check that the sha256sum is still the same by opening a terminal, navigating to the location of the zip file and typing `sha256sum masari-wallet-generator-master.zip`
9. Unzip the file and open `masari-wallet-generator.html`.
10. Click "GENERATE WALLET", which will generate four important items:
 * Public address: Used to recieve funds to the wallet. You give this to anyone who will be sending funds to your wallet.
 * Mnemonic seed: A method of storing the entire wallet that is easily recognizable to humans. This is all you need to restore your wallet at a later date.
 * Private spend key: Used to send funds from the wallet.
 * Private view key: Used to view transactions entering the wallet.  Commonly this is used to setup a [view-only wallet]() on a hot computer which can see incoming transactions live on the blockchain as they are sent to your cold wallet.
11. On a piece of paper, **NEATLY** write down your *mnemonic seed*, *private spend key*, *private view key*, and *public address*. Alternatively (and more conveniently), print these out using a printer that has no wifi capability, has never been connected to the internet, and never will be. The older the printer, the better. You can also copy them to freshly bought USB sticks that have never been connected to the internet, and never will be. Paranoid users can keep 1 copy of printed wallet info and 1 copy of digital wallet info in a safe in their house, and 1 copy of printed wallet info and 1 copy of digital wallet info in a sealed plastic bag filled with rice, inside a PVC pipe that is sealed on both ends with 4" of silicone, buried under the birdbath.
 * Either check 3 times that everything is correct or physically write everything 3 times.
 * **DO NOT LOSE THIS PIECE OF PAPER**. It alone contains the information required to access your Masari, and recover your wallet.
12. OPTIONAL: Copy/paste (do not type) your *public address* and *private view key* to a text file and save on a USB stick^1.  This can be used to more easily create a view only wallet later.

(1) This USB can be used with relative abandon.  The only consequence being, if someone gets a hold of your address and private view key, they could view the funds in your wallet.  They would not be able to, however, spend any funds.

13. Delete any copy of the wallet generator left over on the device you used.
14. Restart your computer back into your normal OS.
15. Reconnect to the internet.
16. Congrats! You sucessfully generated a paper wallet.
