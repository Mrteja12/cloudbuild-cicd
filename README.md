  - name: 'gcr.io/cloud-builders/docker'
    args: ['build', '-t', 'gcr.io/[test-chary]/[nginx-4]:[cassandra]', '.']
  - name: 'gcr.io/cloud-builders/kubectl'
    args:
      - 'apply'
      - '-f'
      - '[PATH_TO_CASSANDRA_YAML]'
    env:
      - 'CLOUDSDK_COMPUTE_ZONE=[us-east1-b]'
      - 'CLOUDSDK_CONTAINER_CLUSTER=[my-first-cluster-3]'