# LIKE API ME - FIXED V2

Changes in this build:
- Restored the ME/account-pool based structure from the ME fixed version.
- Corrected the request-side account cap to 50 (the previous code accidentally sliced 2000 while claiming 50).
- Kept the original region routing and protobuf files intact.
- Removed Python bytecode/cache artifacts from the package.

## If /like still returns zero likes
Check the server logs for:
1. JWT token generation failures.
2. Empty or malformed account files (expected `UID:PASSWORD` per line).
3. HTTP errors from the LikeProfile endpoint.
4. A successful HTTP 200 response that is not reflected immediately in the profile counter.

Do not commit account files or passwords to a public repository. Rotate any credentials that have been exposed publicly.
