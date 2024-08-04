# Analytics Application #124241242

## Deploying a new build
All you need to do is push your updated code and Dockerfile to this repo!
- AWS CodeDeploy will automatically create a new Docker image based on your latest changes and upload it to the "my-repository" ECR repository (based on the `buildspec.yml` in the project root)

The application will be hosted on a Kubernetes cluster via the AWS EKS service, the details of which can be updated by those familiar with K8s by changing the YAML files in the `deployment` directory.

## Monitoring
You can view the nitty gritty details via the Kubernetes command line, but we also forward logs to CloudWatch via a K8s Daemonset that automatically pulls and publishes logs from all running pods (see the `/aws/containerinsights/my-cluster/application` log group).
