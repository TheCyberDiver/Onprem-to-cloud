# Onprem-to-cloud
Setting up On prem to azure cloud

This document is in-progress and demonstrates setting up Azure AD to connect to an on prem AD.

1. Make a tenant # I noticed many people online had troubles accessing the azure portal and getting a 403 error but that was due to not making a tenant
2. Once you make your tenant you will be able to access the AD portal in Azure
3. Download Microsoft Azure AD Connect onto your on PREM server.
4. Setup the features that you would like. NOTE: When you connect your directories use a non ADM account. You need to import the adsyncconfig.psm1 file and the run a Set-ADSyncPasswordHashsyncpermissions command on the account you want to use
5. For optional Features choose password hash sync and password write back//Password write back will update the passwords back to both Onprem and cloud
6.  You need to import the adsyncconfig.psm1 file and the run a Set-ADSyncPasswordHashsyncpermissions command on the account you want to use for the Hashsync which I will list here. This part had me stumped until i found this link: https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-configure-ad-ds-connector-account
7.  This gives the following commands that I ran 
Import-Module "C:\Program Files\Microsoft Azure Active Directory Connect\AdSyncConfig\AdSyncConfig.psm1" &
Set-ADSyncPasswordHashSyncPermissions -ADConnectorAccountName <ADAccountName> -ADConnectorAccountDomain <ADDomainName>
  Put the account that will do that hash and the domain its on.
 
