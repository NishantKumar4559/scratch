# Documenatation Workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related document.

## Types of documents

### Type1

_the points below in describes admin Portal:_

* Using the admin portal, the administrator can now retrieve an individual's lost RID or misplaced RID. 

* Using the admin portal, the admin can now control the levels of location hierarchy they require while creating the registration centres. The level of the hierarchy can be configured through configuration property value.

* Using the admin portal, the administrator can now map the users to a registration centre and to a zone.

* Using the Admin portal, the administrator can now create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc.

* Using the admin portal, the administrator can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type 2 

_Steps for setting up Registration client:_

Step 1: Download TPM utility and run the to get machine keys.
Find the instructions to check out, build and run the utility here.

Step 2: Whitelist the machine keys in server db.
Machine name and keys output from utility should be updated in server.

_use the below api to create / whitelist your machine_

curl -X POST "https://<HOSTNAME>/v1/masterdata/machine"

**NOTE**: 
  
  * Replace appropriate HOSTNAME in the above curl command

  * In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value 

Step 3: Know your userid and required roles.
  Create the user in the keycloak.
Map the user to same centre as that of the machine that is created/whitelisted in Step 2.
Either one of these roles must be assigned to the user in keycloak - "Registration_Supervisor, "Reg_OFFICER"
  
Step 4: Download registration client and start reg-client
Registration client package can be downloaded from below URL, if env is setup with MOSIP standard deployment.
  
  https://docs.mosip.io/1.2.0/modules/registration-client
  
