# Start from the development variant which includes a shell and package manager
FROM cgr.dev/ORG/airflow-core:latest-dev

# Switch to a privileged user in order to install additional packages
USER 0

# Install the pip package, then install the application dependencies
RUN apk update && \
    apk add --no-cache py3.12-pip && \
    pip install --no-cache-dir "apache-airflow[auth,amazon,postgres,kubernetes,cncf-kubernetes,fab,git]==3.0.4" --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-3.0.4/constraints-3.12.txt"

# Switch back to the non-privileged user
USER 50000