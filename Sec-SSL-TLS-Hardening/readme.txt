# registry setting based on the modifications from IIS Crypto from Nartac.
# See reference:
# https://support.nartac.com/article/16-what-registry-keys-does-iis-crypto-modify
README

2 Files needs to be imported into the registry, usually via GPP.
Recommend copying the .reg to a managed script location on sysvol.

1: HKLM-CryptoConfiguration.reg
This file sets the crypto configuration's allows ciphers and priorities their use.
Only the weak ciphers (RC2/RC4) here are disabled.

2: HKLM-SecurityProviders-TLS1.[0|1|2].reg
ONE of these files shold be imported/merged.
Choose based on the minimum TLS version to support.
All settings configure SSL2/3 to disabled.
