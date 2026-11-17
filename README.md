# pg-compare
Compare two PostgreSQL databases schema and data, and get dependency-ordered fix scripts. Windows, runs locally.



# PG Compare

Compare two PostgreSQL databases (schema and data) and get ready-to-run SQL fix scripts.

## What it checks
- Schema: tables, columns, constraints, foreign keys, indexes, sequences, functions, grants, comments
- Data: missing and changed rows, NULL-safe (IS DISTINCT FROM). Compared in key ranges by hash, so big tables are not pulled over the network.

## Fix scripts
- Numbered SQL files in dependency order, plus a zip
- Changed rows go to a separate REVIEW script so you can check them first
- Safe to run twice
- PG Compare never runs the scripts. You review and run them yourself.

## Security
Connects only to the two databases you enter. No telemetry, no other network calls.
Never writes to the databases it compares.

## Quick start
1. Download `PgCompare-v5.2.exe` from Releases (Windows x64, self-contained, no .NET install needed)
2. Verify: `certutil -hashfile PgCompare-v5.2.exe SHA256`
Expected: `cfe9d987358a9aef4974a54369b6ddafdfe4f22e819e679c2112e31db6038c2a`
3. Run it. It opens in your browser on localhost.
4. Enter source and target connections, click Compare, review the report, download the scripts.

Windows may show a SmartScreen warning because this beta is unsigned. Click "More info", then "Run anyway".

## Before running fix scripts
Scripts change the target database. Review every script, take a backup, and test on a copy first. Use at your own risk.

## Status
Free beta. Tested on PostgreSQL 17.

## Changelog
- 5.2: Fixed "out of memory" (PostgreSQL error 54000) when comparing tables with wide rows.

## Feedback
Open an Issue or message me on LinkedIn. Bugs, wrong diffs and missing objects are all welcome.

## License
All rights reserved. Free to use during the beta.
