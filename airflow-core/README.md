# airflow-core

- Spec: [https://images.chainguard.dev/directory/image/airflow-core/specifications](https://images.chainguard.dev/directory/image/airflow-core/specifications)

### Setup

- [Install chainctl](https://edu.chainguard.dev/chainguard/chainctl-usage/how-to-install-chainctl/)
- [Authenticate to Chainguard's Registry](https://edu.chainguard.dev/chainguard/chainguard-images/chainguard-registry/authenticating/#authenticating-with-the-chainctl-credential-helper)

### Instructions

1. Change into the current directory:

```sh
git clone https://github.com/bhearn7/examples.git
cd examples/airflow-core
```

2. In the FROM line of your Dockerfile, replace `ORG` with your Chainguard registry:

```sh
ORG=example-org
sed "s|/ORG/|/$ORG/|" ./Dockerfile > dfc.tmp && mv dfc.tmp ./Dockerfile.$ORG
```

3. Build the image:

```sh
docker build -t airflow-core:latest -f ./Dockerfile.$ORG .
```