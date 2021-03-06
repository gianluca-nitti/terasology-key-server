# Endpoints not requiring special headers

## /api/user_account
- [x] POST: register a new user.
- [x] PATCH: confirm the account. This must be called to enable the account if an email was specified in the registration, specifying the session token received in the email.

### /api/user_account/passwordReset
- [x] POST: create a new password reset request. Requires login name and email.
- [x] DELETE: finalize the password reset. Requires the token sent to the mailbox.

## /api/session
- [x] POST: given username and password, creates a new session (login with a new client); returns a session token.

# Endpoints requiring a Session-Token header

## /api/session
- [x] GET: returns information about the session's owner (e.g. user name)
- [x] DELETE: forces expiration of a session, given the token (logout).

## /api/client_identity
- [x] GET: given a session token, returns all the client identities for the user which owns the session
- [x] POST: given a session token, a server public certificate and a client identity, stores the client identity associated with the specified server for the user which owns the session. If an identity for the same server already exists, it is overwritten.

### /api/client_identity/{serverID}
- [x] GET: given a session token and a server ID, returns the identity of the user which owns the session on the specified server.
