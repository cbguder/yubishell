# Yubishell

## Installation

1. Add contents of `gpg-agent.conf` to `~/.gnupg/gpg-agent.conf`

       curl https://raw.githubusercontent.com/cbguder/yubishell/master/gpg-agent.conf >> ~/.gnupg/gpg-agent.conf

2. Add contents of `yubishell.sh` to `~/.bash_profile`

       curl https://raw.githubusercontent.com/cbguder/yubishell/master/yubishell.sh >> ~/.bash_profile

## Prerequisites

1. Install gpg via homebrew

       brew install gpg

2. Generate GPG keys on YubiKey

       $ gpg --edit-card
       gpg: directory '/Users/cbguder/.gnupg' created
       gpg: keybox '/Users/cbguder/.gnupg/pubring.kbx' created

       Reader ...........: Yubico Yubikey 4 OTP U2F CCID
       Application ID ...: <REDACTED>
       Version ..........: 2.1
       Manufacturer .....: Yubico
       Serial number ....: <REDACTED>
       Name of cardholder: [not set]
       Language prefs ...: [not set]
       Sex ..............: unspecified
       URL of public key : [not set]
       Login data .......: [not set]
       Signature PIN ....: not forced
       Key attributes ...: rsa2048 rsa2048 rsa2048
       Max. PIN lengths .: 127 127 127
       PIN retry counter : 3 0 3
       Signature counter : 0
       Signature key ....: [none]
       Encryption key....: [none]
       Authentication key: [none]
       General key info..: [none]

       gpg/card> admin
       Admin commands are allowed

       gpg/card> passwd
       gpg: OpenPGP card no. <REDACTED> detected

       1 - change PIN
       2 - unblock PIN
       3 - change Admin PIN
       4 - set the Reset Code
       Q - quit

       Your selection? 1
       PIN changed.

       1 - change PIN
       2 - unblock PIN
       3 - change Admin PIN
       4 - set the Reset Code
       Q - quit

       Your selection? 3
       PIN changed.

       1 - change PIN
       2 - unblock PIN
       3 - change Admin PIN
       4 - set the Reset Code
       Q - quit

       Your selection? q

       gpg/card> name
       Cardholder's surname: Guder
       Cardholder's given name: Can Berk

       gpg/card> login
       Login data (account name): cbguder

       gpg/card> lang
       Language preferences: en

       gpg/card> generate
       Make off-card backup of encryption key? (Y/n) n
       What keysize do you want for the Signature key? (2048) 4096
       The card will now be re-configured to generate a key of 4096 bits
       Note: There is no guarantee that the card supports the requested size.
             If the key generation does not succeed, please check the
             documentation of your card to see what sizes are allowed.
       What keysize do you want for the Encryption key? (2048) 4096
       The card will now be re-configured to generate a key of 4096 bits
       What keysize do you want for the Authentication key? (2048) 4096
       The card will now be re-configured to generate a key of 4096 bits
       Please specify how long the key should be valid.
                0 = key does not expire
             <n>  = key expires in n days
             <n>w = key expires in n weeks
             <n>m = key expires in n months
             <n>y = key expires in n years
       Key is valid for? (0)
       Key does not expire at all
       Is this correct? (y/N) y

       GnuPG needs to construct a user ID to identify your key.

       Real name: Can Berk Guder
       Email address: cbguder@example.com
       Comment:
       You selected this USER-ID:
           "Can Berk Guder <cbguder@example.com>"

       Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? o
       gpg: /Users/cbguder/.gnupg/trustdb.gpg: trustdb created
       gpg: key <REDACTED> marked as ultimately trusted
       gpg: directory '/Users/cbguder/.gnupg/openpgp-revocs.d' created
       gpg: revocation certificate stored as '/Users/cbguder/.gnupg/openpgp-revocs.d/<REDACTED>.rev'
       public and secret key created and signed.

       gpg/card> quit
       pub   rsa4096 2017-10-19 [SC]
             <REDACTED>
       uid                      Can Berk Guder <cbguder@example.com>
       sub   rsa4096 2017-10-19 [A]
       sub   rsa4096 2017-10-19 [E]

## Credits

Initial version created by [Christopher Brown](https://github.com/xoebus)
