# Notes for Module 2 Workflow Orchestration

When running the default docker-compose.yml, it creates a new volume called 02-workflow-orchestation-ny_taxi_postgres_data, but not using the existing volume: ny_taxi_postgres_data created in module 1.

To connect to the existing volume, I added "external: true" flag in the top-level volumes declaration so that it will not create a new one.
```yaml
  ny_taxi_postgres_data:
    external: true
  kestra_postgres_data:
    driver: local
  kestra_data:
    driver: local
```
