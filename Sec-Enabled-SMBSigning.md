# Enable SMB signing via GPO

1) create new GPO "Sec-Enable-SMBSigning"
2) Configure:
Computer Configuration > Policies > Windows Settings > Security Settings > Local Policies > Security Options
Microsoft network server: Digitally sign communications (always) -- ENABLED
Microsoft network client: Digitally sign communications (always) -- ENABLED
3) Link GPO to OU level to apply to all computers (both servers and clients)
