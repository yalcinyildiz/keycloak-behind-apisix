# Test positioning IAM after API GW

## Components

PoC contains 4 different components.

- Keycloak data will be stored in PostgreSQL database
- Web application will force users to log in to Keycloak
- APISIX will run on standalone mode and positioned in front of Keycloak


## Component Configurations

- [Keycloak](Configurations-Keycloak.md)