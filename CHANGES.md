## QUICK-CA CHANGELOG


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
