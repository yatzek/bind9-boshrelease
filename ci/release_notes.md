## New Features

- **Recursive Resolution** - A BIND9 cluster (master + slaves) can
  now be configured to recursively forward requests for RRs it
  is not authoritative for, to one or more upstream name servers.
  By default, this behavior is off.  Thanks @geofffranks!

- **Configuration / Zone Checks** - Before `named` is started
  (either on the master or slave jobs), a full configuration
  check, including the zone database files on `master` is
  performed.  If any problems are found (usually bad zone files),
  the job is terminated and marked as failing, so that the cluster
  can remain healthy and BOSH will halt the deployment.
