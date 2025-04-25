# Changelog

All notable changes to this library will be documented in this file.

Entries should be ordered as follows:

- [CHANGE]
- [FEATURE]
- [ENHANCEMENT]
- [BUGFIX]

Entries should include a reference to the pull request that introduced the change.

## 5.20.0
- [BUGFIX] Fixed a defect in the naming pattern for analytics datasource parameters. Parameters matching `*_DATASOURCE-ANALYTICS_*` were renamed to `*_DATASOURCEANALYTICS_*` to ensure consistency with naming conventions and avoid misconfiguration.
- [CHANGE] Updated the application to the latest version.

## 5.19.0
- [CHANGE] Increased minimum Kubernetes version requirement to `>= 1.20.0-0` to guarantee compatibility with `startupProbe`.
- [FEATURE] Added `startupProbe` configuration for pods to handle slow-starting applications gracefully. The probe checks `/api/management/health/readiness` on the `http` port, ensuring the application is fully initialized before receiving traffic.

## 5.18.1
- [FEATURE] Added support for Patroni database clustering configuration in the `datasources` section. If Patroni is enabled, `dbHost` in `mainDatasource` and `analyticsDatasource` will be ignored, and database connections will be established using the Patroni hosts instead.

## 5.18.0
- [FEATURE] Added support for custom deployment labels via `labels.deployment` configuration block. This allows users to define additional labels for deployments, enhancing resource identification and management.
- [FEATURE] Added support for external secrets management in the image pull authentication configuration. Introduced a new toggle `useExternalSecret` to allow users to choose between traditional Kubernetes secrets and external secrets (e.g., External Secrets Operator). This enhances flexibility for integrations with tools like ArgoCD and HashiCorp Vault.
