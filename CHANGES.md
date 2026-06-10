## QUICK-CA CHANGELOG


### [June-2026]

#### - New Features:
        + added ML-KEM support.
       	+ setup_root and setup_issuing takes less input.
        + ca_revoke_cert and ca_revoke_root_issued_cert, moves the revoked certificates from issued_certs to revoked_certs directory, after signing the CRL.
	+ changes to setup_ocsp.
       	+ added options to set custom CPS, CDP, AIA, ocsp : DONE.
        + added a new script 'ca_list_root_issued_certs' to list all certificates issued by the ROOT CA.
        + added a new script 'ca_list_root_revoked_certs' to list all certificates revoked by the ROOT CA.
        + added a new script 'ca_revoke_root_issued_cert' to revoke a certificate issued by the ROOT CA.
        + added colour to highlight the "important note" to setup environment variables.
        + VERSION number is not hardcoded in the script anymore.
        + Improvements in ca_generate_cert

	#### - Bug fixes:
        - fixed a bug in ca_issue_cert
       	- fixed an issue that occurs with FIPS module is used.

<br>


### [May-2025]

#### NEW:
	+ ca_revoke_cert now asks for a revocation reason to be specified.
	+ added ca_get_ca_chain to retrieve a cacerts file.
	+ added support for mldsa algorithm for the ROOT and the ISSUING CA.

#### FIXES:
	* Fixed a bug in ca_list_issued_cert.




### [Feb-2025]

#### NEW:
	+ Added 'ca_get_issued_cert' to retrieve a certificate signed by an issuing ca.
	+ Added 'ca_verify_cert' to check validity of a certificate.
#### FIXES:
	+ Fixed a bug in ca_issue_ca_cert




### [Sep-2024]

#### NEW:
	+ new CA utility scripts -
		- ca_get_root_cert	: returns Root CA certificate
		- ca_get_issuer_cert	: returns Issuing CA certificate.
		- ca_list_revoked_certs	: lists all revoked certificates.
	+ Older version of QuickCA can now be updated using "update_QuickCA" script.
	+ Integrity of all CA utilities can be checked using "check_integrity" script.
