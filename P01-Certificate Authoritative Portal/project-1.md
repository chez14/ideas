## Project details and quick draft.
The project will be node-js based, with expressjs i think, then the certs, private and such are placed within a special restricted folder.

The proejct will have:
1. Daemon
2. Main App (will make sure the cycle runs normally.)
3. Web Interface App

The daemon will run in a specific user, and responsible for the certificate.

The Main app will responsible to comunicate with the daemon, and recieving the Web App requests, and make sure the cycle are running properly, such as monitoring purposes and more.

The Web Interface are consists with 3 main parts:
- Web App for User, to handle Certificate Request
- Web App for OCSP (OSCP? idk lol) Responder, for revocation and validation stuffs.
- Web App for API, we'll support API for requestor etc.

## Info Needed
I need more info with the OCSP Protocol, since it's comunicationg over HTTP, and there's no much people talking about it. I hope i could hear the comunity shououts.

I need more info with the OID and stuffs like that.