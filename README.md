# pvc-migrate
For when you wish to change storage controller and clone data.

This was inspired and "cloned" from https://justyn.io/til/migrate-kubernetes-pvc-to-another-pvc/

First make it execuatable: chmod +x migrate.sh.

This script expects 3 parameters:
1. Source PVC
2. Target PVC
3. namespace.

Example: ./migrate.sh source-pvc target-pvc testnamespace
