# Configure SSL/TLS and Crypto Registry Settings
Default crypto and cipher suites settings have vulnerabilities. These settings will need to be disabled on the systems directly.
1) need to disable SSLv2, SSLv3, and other protocols
2) need to disable RC4 ciphers, and other weak ciphers
3) need to reorder ciphers, disabling weak/broken groups.

## See the reg files that can be added to a GPO (copied to SYSVOL)
1) GPO: Name GPO "Sec-SSL-TLS-Hardening"
2) Add GPP for registry (point to .reg files) (Registry for crypto/cipher settings)
3) Link to OU to apply GPO to all server/PCs

## Registry files:
[HKLM-Policies-Crypto-CipherOrder.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Policies-Crypto-CipherOrder.reg) - Cipher order (with only enabled best practices ciphers)

[HKLM-Schannel-Ciphers.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Schannel-Ciphers.reg) - best practice ciphers only

[HKLM-Schannel-Hashes.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Schannel-Hashes.reg) - best practice hashes only

[HKLM-Schannel-KeyExchangeAlgorithms.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Schannel-KeyExchangeAlgorithms.reg) - best practice key exchange configuration

[HKLM-Schannel-Protocols.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Schannel-Protocols.reg) - Best practice protoclas, disables SSL2/3. enables TLS1.0+

{optional} [HKLM-Schannel-Protocols-Disable-TLS1.0.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Schannel-Protocols-Disable-TLS1.0.reg) - disables TLS 1.0 client and server

{optional} [HKLM-Schannel-Protocols-Disable-TLS1.1.reg](https://raw.githubusercontent.com/robert-moses/fuzzy-octo-computing-machine/master/Sec-SSL-TLS-Hardening/HKLM-Schannel-Protocols-Disable-TLS1.1.reg) - disables TLS 1.1 client and server
