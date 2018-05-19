# Certificate Authoritative Portal
A web-app for those Certificate Authoritative wannabe: create, sign, revoke(delete) easily with some click, and it's secure.

Notes:

- CA Root Certificate should be installed to the Authoritative system, so our intermediate certificate got trusted.
- CA Private key should be stored securely in a highly monitored place (if you can afford it tho), and it should be offline.
  If you wanted to create a new Intermediate Cert, you should do it manually.
- Define your own certificate path and name Convenctions, i'll tell you my own later.


Role that should be implemented:

- [BASIC] Able to add Intermediate Cert with it's private key and validate it.
- [BASIC] Able to add CSR, extract it's info, and generate a ceritifate with selected intermediate cert.
- [BASIC] Able to select a cert to sign the certificate
- [BASIC] Able to revoke cert
- [ADVANCE] Able to give a CSR Submitter (Cert Requestor) a confirmation page, emailed for notifications, and give them a last opportunity to change the data.
- [ENHANCE] The requestor able to enter payment option so they can pay it. (so the generation of the certificate will be holded untill the requestor paid it.)

Potential Charge option:
- Create (per Private key)
- Revoke (30% of the creation price) [Free for upgrade?]
- Per purpose price, more risk more price.
- SSL Wildcard support
- SAN (Alternative Name) per line (or other)
- Provide a Intermediate Certification for batch with notes and strict agreement (per month license).
- Per month certificate option.

## Update
I just found the OpenCA for things like this, but there's no much update of it, and i wanted a new one of things like that. So i will still keep this idea updated.

## Project Update
I'll use NodeJS since the OpenSSL support are huge + the community are superawesome. I'll tkae my time with this.