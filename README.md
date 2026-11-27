# tickets.sneakpeek.mazecomrat.de

The passkey domain (WebAuthn rpId) for Sneakpeek's end-to-end encrypted tickets. It serves one file,
`/.well-known/assetlinks.json`, which lets the Sneakpeek app (release key only) use passkeys for this domain.

Deliberately nothing else: no HTML, no JavaScript, no `/.well-known/webauthn`. A page served here could ask a
passkey's PRF in a browser, so this site is kept apart from the app's server, with its own hosting and credentials.
Change it only to rotate the signing certificate.

Keep both relations in the file, `handle_all_urls` and `get_login_creds`. With `get_login_creds` alone, Play services
refused to make passkeys here ("[50152] RP ID cannot be validated", 27 November 2026), although Google's Digital Asset
Links API listed the statement.
