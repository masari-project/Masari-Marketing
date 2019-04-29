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
 * Private view key: Used to view transactions entering the wallet.  Commonly this is used to setup a [view-only wallet]() on a hot computer which can see incoming transactinos live on the blockchain as they are sent to your cold wallet.
6. On a piece of paper, **NEATLY** write down your *mnemonic seed*, *private spend key*, *private view key*, and *public address*.
 * Either check 3 times that everything is correct or physically write everything 3 times.
 * **DO NOT LOOSE THIS PIECE OF PAPER**. It alone contains the information required to access your Masari, and recover your wallet.
7. OPTIONAL: Copy/paste (do not type) your *public address* and *private view key* to a text file and save on a USB stick^1.  This can be used to more easily create a view only wallet later.

(1) This USB can be used with relative abandon.  The only consequence being, if someone gets ahold of your address and private view key, they could view the funds in your wallet.  They would not be able to, however, spend any funds.

8. Delete any copy of the wallet generator left over on the device you used.
9. Restart your computer.
10. Reconnect to the internet.
11. Congrats! You sucessfully generated a paper wallet.

## Booting With a Linux USB (more secure)

**Skill Required:**

This option requires a moderate understanding of Monero, network security, and general computer knowledge.

**Hardware/Software Required:**

*1x Hot Computer*

*1x USB Stick (3 is helpful)*

*1x Paper*

*1x Pen*

*1x Hash Utility.  I personally use either the built in [Windows 10 utility](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/certutil#BKMK_hashfile) or Ubuntu utility (https://help.ubuntu.com/community/HowToSHA256SUM). An easy to use and well known GUI utility is [QuickHash](https://sourceforge.net/projects/quickhash/).

**Generating the Wallet:**

Follow the instructions here: https://www.reddit.com/r/masari/comments/89tis3/masariusbcoldwalletgenerator_100_initial_release/

If you are not comfortable downloading a user created zip file, you can download the individual files yourself (links provided in guide), and then follow the guide.
