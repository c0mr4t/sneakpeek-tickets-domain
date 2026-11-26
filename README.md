# tickets.sneakpeek.mazecomrat.de

The passkey domain (WebAuthn rpId) for Sneakpeek's end-to-end encrypted tickets. It serves one file,
`/.well-known/assetlinks.json`, which lets the Sneakpeek app (release key only) use passkeys for this domain.

Deliberately nothing else: no HTML, no JavaScript, no `/.well-known/webauthn`. A page served here could ask a
passkey's PRF in a browser, so this site is kept apart from the app's server, with its own hosting and credentials.
Change it only to rotate the signing certificate.
