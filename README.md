# pvc-migrate
For when you wish to change storage controller and clone data.

This was inspired and "cloned" from https://justyn.io/til/migrate-kubernetes-pvc-to-another-pvc/

First make it execuatable: chmod +x migrate.sh.

This script expects 3 parameters:
1. Source PVC
2. Target PVC
3. namespace.

Example: ./migrate.sh source-pvc target-pvc testnamespace

Post execution a new file will be created called migrate-job-sourcepvcname.yaml.
Run this file by using kubectl apply -f migrate-job-sourcepvcname.yaml.
This will create a job and corresponding pod.

Find the job by running kubectl get job -n namespace.
Find the pod by running kubectl get pods -n namespace.

Once the job/pod is done, it will be marked as completed:

migrate-pv-testpvc-w9sqj                 0/1     Completed   0          50m

You can freely clean up by removing the pod.
