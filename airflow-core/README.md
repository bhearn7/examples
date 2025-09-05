# airflow-core

- Spec: [https://images.chainguard.dev/directory/image/airflow-core/specifications](https://images.chainguard.dev/directory/image/airflow-core/specifications)

## Setup

- [Install chainctl](https://edu.chainguard.dev/chainguard/chainctl-usage/how-to-install-chainctl/)
- [Authenticate to Chainguard's Registry](https://edu.chainguard.dev/chainguard/chainguard-images/chainguard-registry/authenticating/#authenticating-with-the-chainctl-credential-helper)

## Instructions

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
docker build -t airflow-core:cgr-latest -f ./Dockerfile.$ORG .
```

## Next Steps

**Secure Your Application Dependencies**

Instead of pulling potentially malicious dependencies from PyPI/MavenCentral/NPM, eliminate even more vulnerabilities in your applications by utilizing libraries built from source:

- [Announcing Chainguard Libraries for Python: Malware-Resistant Dependencies Built Securely from Source](https://www.chainguard.dev/unchained/announcing-chainguard-libraries-for-python-malware-resistant-dependencies-built-securely-from-source)
- [Guarding the Python Ecosystem Against the Growing Number of Severe Malware Attacks](https://www.chainguard.dev/unchained/guarding-the-python-ecosystem-against-the-growing-number-of-severe-malware-attacks)
- [Mitigating Malware in the Python Ecosystem with Chainguard Libraries](https://www.chainguard.dev/unchained/mitigating-malware-in-the-python-ecosystem-with-chainguard-libraries)
- [Malware-Resistant Python without the Guesswork](https://www.chainguard.dev/unchained/malware-resistant-python-without-the-guesswork)
- [Chainguard Libraries Overview](https://edu.chainguard.dev/chainguard/libraries/overview/)