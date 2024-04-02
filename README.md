# Quick CA v2024.04
  
  
## What is Quick CA?
Quick CA is a bash script that automates the creation of Root CA and an Issuing CA using the OpenSSL utility. This script is capable of setting up a two-tier PKI within two minutes. It is designed to work on Linux operating systems with OpenSSL 3.x. This script may not function as expected with OpenSSL 1.1.1 due to its utilization of OpenSSL 3.x command syntax.
  
  
  
  
## How does it work?
QuickCA only requires information relevant to your PKI tasks. It automatically executes the necessary OpenSSL commands to complete these tasks. The script always stores all CA-related files inside the $HOME/CA directory. The private key is encrypted using the /etc/machine-id of your Linux machine. Additionally, the templates for Root CA and Issuing CA are auto-generated based on the user input during setup.
  
  
  
  
## Directory Structure of Quick CA
Here's an example for what the directory structure might look like after you finish setting up root and issuing ca.

CA/  
├── bin			: Contains all executable scripts.  
├── myIssuing		: Directory structure for ISSUING CA.  
│   ├── cert  
│   ├── crl  
│   ├── csr  
│   ├── data  
│   ├── issued_certs  
│   └── private  
├── myRoot		: Directory structure for ROOT CA.  
│   ├── cert  
│   ├── crl  
│   ├── csr  
│   ├── data  
│   ├── issued_certs  
│   └── private  
└── web			: Location used for storing an updated CA certificate and CRLs. Can be used as a source for AIA and CDP.  
    ├── cert  
    └── crl  
  
  
  
  
## List of executables and their purpose.
  
 - ca_examine_cert ......... : examine a certificate issued by the ISSUING CA.
 - ca_generate_cert ........ : generates a new private key with a CA signed certificate.
 - ca_issue_ca_cert ........ : sign a certificate request for another certificate authority.
 - ca_issue_cert ........... : sign a certificate request.
 - ca_list_issued_certs .... : lists of all certificates issued by the issuing CA.
 - ca_revoke_cert .......... : revoke an issued certificate and updates the CRL.
 - ca_help ................. : display help.
