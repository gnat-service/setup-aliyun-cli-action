# Setup Aliyun Cli Action

## Usage

```yaml
jobs:
    some-job:
    - name: Setup Aliyun Cli
      uses: gnat-service/setup-aliyun-cli-action@v2
      with:
        region: <region> # "cn-hangzhou" for instance.
        access-key-id: <access-key-id> # your aliyun access key id
        access-key-secret: <access-key-secret> # your aliyun access key secret
        version: <aliyun-cli-version> # Specify aliyun cli version to download a different release from `https://github.com/aliyun/aliyun-cli/releases/`. default is "", which let you use github preset aliyun cli version.

    - name: Use Your Aliyun Cli
      run: |
        # This command returns a kubeconfig for you to access the specific k8s cluster.
        aliyun --region <region> cs DescribeClusterUserKubeconfig --ClusterId <k8s-cluster-id> --TemporaryDurationMinutes 30
        # or any other commands you want to run
```
