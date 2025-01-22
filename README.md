# Digitalist Directus Helm Chart

This is the Digitalist Helm chart for [Directus](https://directus.io/).
Based on the [Directus Community Helm Charts](https://github.com/directus-community/helm-chart).

## Documentation

Chart documentation is found in the [chart directory](charts/directus/README.md).

## Modifications to the original chart

The chown command, run in the init container write-permissions, should be disabled when deploying with persistence of storageclass type EFS. To support this a variable runChown.enabled is introduced and a conditional clause that checks if this variable is set to true or whether persistence has been enabled is evaluated first to determine if the command should be run.
