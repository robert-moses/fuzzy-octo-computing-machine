# Secure SNMP settings
### Disable SNMP v1/v2 -- NOT SECURE
### SNMP v3 -- NOT SUPPORTED
### Disable SNMP - supported alternative is WMI/WinRM

1) create new GPO "Sec-Secure-SNMP"

### Disable SNMP if not in use
2) Configure:
Computer Configuration\Policies\Windows Settings\Security Settings\System Services
  SNMP Service -> disable

3) Link GPO to OU level to apply to all computers (both servers and clients)



### *** notes for refernce SNMP v2c ***
 Customize for management, auth settings.
1) Configure:
Computer Configuration\Policies\Administrative Template\Network\SNMP\Communities
  Enabled: "E32aYtgKavdH9TEkpqX6JU5" --- RANDOM EXAMPLE DO NOT USE
 Computer Configuration\Policies\Administrative Template\Network\SNMP\Permitted Managers
   Enabled: permitted managers - "localhost" -- RESTRICT TO LOCAL HOST listener
 Computer Configuration\Policies\Administrative Template\Network\SNMP\Trap for public community
  Disabled
