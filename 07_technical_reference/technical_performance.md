<img src="../assets/icons/technical.svg" alt="" width="48">

# Technical Performance

This page provides a public summary of technical performance practices for RegulonDB, aligned with transparent service stewardship and continuity goals.

## Purpose

To describe how service reliability is monitored and maintained in a public, non-sensitive format suitable for portal documentation.

## Public Reporting Scope

This document covers:

- Service availability intent.
- Operational reliability practices.
- Monitoring and incident-response principles.
- Public communication of relevant service-impacting events.

It does not disclose sensitive infrastructure details.

## Service Reliability Principles

RegulonDB technical operations follow these principles:

- **Availability:** maintain stable access to web interface, downloads, and APIs.
- **Stability:** prioritize continuity for critical access paths.
- **Traceability:** document release-impacting technical changes.
- **Recoverability:** maintain internal operational procedures for restoration.

## Public Operational Commitments

- Keep core access services operational under normal conditions.
- Document major release changes through public release notes.
- Communicate significant service-impacting updates when applicable.
- Periodically review performance and reliability practices.

## Monitoring and Response (Public Summary)

RegulonDB maintains routine operational monitoring to detect service degradation and support response prioritization across:

- Web platform access.
- API/data access channels.
- Release-dependent data availability.

Response coordination is handled by software and infrastructure teams, in alignment with governance and continuity priorities.

## Alternative Access

If the main site is not available, users can still access RegulonDB through:

- The **mirror site** at LIIGH-UNAM: [regulondb.liigh.unam.mx](https://regulondb.liigh.unam.mx/).
- A **local instance** of any release, deployed with Docker: [How to Install a Local Instance of RegulonDB](rdb_docker_instance.md).
- The **release dump** (MongoDB) of each version: [Database Dumps](../02_data_access/database_dumps.md).

## Related Content
- [Data Preservation and Continuity Policy](../00_about_policies/data_preservation_policy.md)
- [Governance and Scientific Advisory](../00_about_policies/governance_advisory.md)
- [Release Notes](../05_releases_updates/release_notes.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
