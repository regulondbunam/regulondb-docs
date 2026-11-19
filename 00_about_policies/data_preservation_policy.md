<img src="../assets/icons/about.svg" alt="" width="48">

# Data Preservation and Continuity Policy

This page defines the public policy framework used by RegulonDB to preserve data integrity, ensure long-term availability, and support continuity of service.

## Purpose

To provide transparent guidance on how RegulonDB preserves curated data, maintains versioned access, and manages continuity risks over time.

## Scope

This policy applies to:

- Curated biological data and associated metadata.
- Public documentation and release information.
- Publicly accessible data access channels (web interface, downloads, APIs).

## Preservation Principles

RegulonDB follows these preservation principles:

- **Integrity:** curated records are maintained with traceability to evidence and source literature.
- **Versioning:** public releases are managed with identifiable versions and changelog records.
- **Recoverability:** operational practices support restoration in case of service interruption.
- **Continuity:** critical services are maintained through coordinated curation and technical operations.

## Public Preservation Practices

RegulonDB applies the following preservation practices:

- **Persistent identifiers for releases:** RegulonDB releases are registered in Zenodo with a DOI (for example, RegulonDB v12.0.0: [doi:10.5281/zenodo.8346680](https://doi.org/10.5281/zenodo.8346680)).
- **Deployable releases:** each version is distributed as Docker images and database dumps, so that any release can be deployed and queried locally (see [Database Dumps](../02_data_access/database_dumps.md) and the [Docker Installation Guide](../07_technical_reference/rdb_docker_instance.md)).
- **Versioned source code:** software and configuration are maintained under version control in GitHub ([github.com/regulondbunam](https://github.com/regulondbunam)).
- **Mirror site:** a mirror of RegulonDB is maintained at the International Laboratory for Human Genome Research (LIIGH-UNAM): [regulondb.liigh.unam.mx](https://regulondb.liigh.unam.mx/).
- **Backups:** regular backups of databases and services are performed.
- **Versioned documentation:** release notes and version history are published with each release.
- **Governance oversight:** policies and documentation are reviewed periodically.

Related pages:

- [Version History](../05_releases_updates/version_history.md)
- [Release Notes](../05_releases_updates/release_notes.md)
- [FAIR Data Policy](fair_policy.md)
- [Governance and Scientific Advisory](governance_advisory.md)

## Continuity and Risk Management (Public Summary)

RegulonDB maintains continuity through:

- Coordinated responsibilities across leadership, curation, and infrastructure teams.
- Periodic operational review and prioritization of critical services.
- Documentation updates when major changes affect data access or release processes.

Detailed operational procedures (for example, backup schedules and infrastructure implementation details) are managed internally.

## Roles and Responsibilities

- Governance and leadership: policy oversight and continuity priorities.
- Biocuration team: content quality, provenance, and consistency.
- Software and infrastructure team: operational maintenance and service reliability.

## Review Cycle

- This policy is reviewed at least annually.
- Additional updates may be published after major infrastructure or release-process changes.

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
