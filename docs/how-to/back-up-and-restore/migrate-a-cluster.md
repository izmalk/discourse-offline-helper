
```{note}All commands are written for `juju v.3.1.7+````

# How to migrate to a new cluster via restore

This is a guide on how to restore a backup that was made from a different cluster, (i.e. cluster migration via restore).

To perform a basic restore (from a local backup), see [How to restore a local backup](/how-to/back-up-and-restore/restore-a-local-backup).

## Prerequisites

Restoring a backup from a previous cluster to a current cluster requires:
* At least 3x Charmed OpenSearch units deployed and running
* Access to an S3-compatible storage
* Configured settings for the S3-compatible storage
* Backups from the previous cluster in your S3-compatible storage

---

## List backups

To view the available backups to restore, use the command `list-backups`:

```none
juju run opensearch/leader list-backups
Running operation 335 with 1 task
  - task 336 on unit-opensearch-0

Waiting for task 336...
backups: |2-
   backup-id           | backup-status
