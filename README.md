# py-workedtask
## Integrity Verification

Both the Python and C++ implementations support optional self-integrity verification to detect tampering prior to execution.

### Python Implementation (`workedtask.py`)

The Python script computes the SHA-256 digest of its own source file (`__file__`) at startup and compares it against the `JAVELIN_EXPECTED_SHA256` environment variable (case-insensitive). If `JAVELIN_EXPECTED_SHA256` is unset or empty, the check is skipped. If set and the hash does not match, the process performs a guarded exit with a non-zero status code (`1`).


