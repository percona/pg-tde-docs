# pg_tde: Transparent Database Encryption for PostgreSQL Documentation

Welcome to `pg_tde` documentation! 

## Overview

Transparent Data Encryption offers encryption at the file level and solves the problem of protecting data at rest. 
The encryption is transparent for users allowing them to access and manipulate the data and not to worry about the encryption process. 
As a key provider, the extension supports the keyringfile, [Hashicorp Vault](https://www.vaultproject.io/) and KMIP-compatible servers.

### This extension provides two `access methods` with different options:

#### `tde_heap_basic` access method
- Works with community PostgreSQL 16 and 17 or with [Percona Server for PosgreSQL 17](https://docs.percona.com/postgresql/17/postgresql-server.html)
- Encrypts tuples and WAL
- **Doesn't** encrypt indexes, temporary files, statistics
- CPU expensive as it decrypts pages each time they are read from bufferpool

#### `tde_heap` access method
- Works only with [Percona Server for PostgreSQL 17](https://docs.percona.com/postgresql/17/postgresql-server.html)
- Uses extended Storage Manager and WAL APIs
- Encrypts tuples, WAL and indexes
- **Doesn't** encrypt temporary files and statistics **yet**
- Faster and cheaper than `tde_heap_basic`

This repository contains the source files for [`pg_tde` documentation](https://docs.percona.com/pg-tde/index.html). 
The documentation is written in [Markdown markup language](https://www.markdownguide.org/) and is created using [MkDocs](https://www.mkdocs.org/).

The `pg_tde` code is in the [postgres](https://github.com/percona/postgres) repository since the extension is supplied with Percona Server for PostgreSQL.


## Contributing

We welcome all contributors. For how to contribute to documentation, read the [Contributing guide](https://github.com/percona/pgsm-docs/blob/main/CONTRIBUTING.md).
 
## Licensing

Percona is dedicated to **keeping open source open**. Wherever possible, we strive to include permissive licensing for both our software and documentation. For this project, we are using the Apache License 2.0 license. 
