# Quick CA v2025.05
  
  
### What is Quick CA?
Quick CA is a bash script that automates the creation of Root CA and an Issuing CA using the OpenSSL utility. This script is capable of setting up a two-tier PKI within two minutes. It is designed to work on Linux operating systems with OpenSSL 3.x. This script may not function as expected with OpenSSL 1.1.1 due to its utilization of OpenSSL 3.x command syntax.
  
  
  
  
### How does it work?
QuickCA only requires information relevant to your PKI tasks. It automatically executes the necessary OpenSSL commands to complete these tasks. The script always stores all CA-related files inside the $HOME/CA directory. The private key is encrypted using the /etc/machine-id of your Linux machine. Additionally, the templates for Root CA and Issuing CA are auto-generated based on the user input during setup.
  
  
  
  
### Directory Structure of Quick CA
Here's an example for what the directory structure might look like after you finish setting up root and issuing ca.

CA/<br>
├── bin			: Contains all executable scripts. <br>
├── myIssuing		: Directory structure for ISSUING CA. <br>
│   ├── cert <br>
│   ├── crl <br>
│   ├── csr <br>
│   ├── data <br>
│   ├── issued_certs <br>
│   └── private <br>
├── myRoot		: Directory structure for ROOT CA. <br>
│   ├── cert <br>
│   ├── crl <br>
│   ├── csr <br>
│   ├── data <br>
│   ├── issued_certs <br>
│   └── private <br>
├── web			: Location used for storing an updated CA certificate and CRLs. Can be used as a source for AIA and CDP. <br>
│    ├── cert <br>
│    └── crl <br>
├── check_integrity : checks the integrity of QuickCA scripts. <br>
└── setenv.sh : sets the required environment variables for QuickCA. <br>
  
  
  
### List of executables and their purpose.

 - ca_about ................ : prints information about Quick CA.
 - ca_examine_cert ......... : examine a CA issued certificate.
 - ca_generate_cert ........ : generates a private key and a signed certificate.
 - ca_get_ca_chain ......... : returns cacert file.
 - ca_get_root_cert ........ : returns your Root CA certificate.
 - ca_get_issuer_cert ...... : returns your Issuing CA certificate.
 - ca_get_issued_cert ...... : returns a certified issued by Issuign CA.
 - ca_issue_ca_cert ........ : generates a certificate for another certificate authority.
 - ca_issue_cert ........... : generates a CA signed certificate using a certificate request.
 - ca_list_issued_certs .... : displays a list of all active certificates issued by CA.
 - ca_list_revoked_certs ... : displays a list of all certificates revoked by the Issuing CA.
 - ca_revoke_cert .......... : revokes an issued certificate.
 - ca_verify_cert .......... : checks for the validity of a certificate.
 - ca_help ................. : displays this help.


### Quick-CA Updater
- If you already have an older version of QuickCA installed, then please use update_QuickCA script found inside the tarball to update the scripts.
- Updater checks the integrity of all scripts before copying them into your existing QuickCA setup.
- Expected output as follows :-
  
Signature Verified Successfully
bin/ca_about: OK
bin/ca_examine_cert: OK
bin/ca_generate_cert: OK
bin/ca_get_issuer_cert: OK
bin/ca_get_root_cert: OK
bin/ca_help: OK
bin/ca_issue_ca_cert: OK
bin/ca_issue_cert: OK
bin/ca_list_issued_certs: OK
bin/ca_list_revoked_certs: OK
bin/ca_revoke_cert: OK
Quick CA updated.
