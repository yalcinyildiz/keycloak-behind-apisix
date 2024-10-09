## Keycloak Login

- Open a new window in your browser
- Go [Keycloak login page](http://keycloak:8080/admin)
- Use "admin" as username, and "admin" as password
- Hit "Sign In" button

## Create web realm

- Click "master" realm, then click Create Realm
- Name realm as "web"
- Press "Create" button

## Create web client

- Select "web" realm
- Go to "Clients" menu
- Hit "Create client" button
- General Settings
  - Client ID: client_web
- Capability config
  - Client authentication: Off
  - Authentication flow: select Standard flow
- On "Client details" page
  - Settings
    - Valid redirect URIs: *
    - Valid post logout redirect URIs: *
    - Web origins: *
    - Front channel logout: On
    - Front-channel logout URL: http://localhost:3000
    - Backchannel logout URL: http://localhost:3000
    - Backchannel logout session required: On
    - Backchannel logout revoke offline sessions: On
  - Advanced
    - Advanced Settings
      - Access Token Lifespan: Expires in 1 Minutes

## Create apisix client

- Select "web" realm
- Go to "Clients" menu
- Hit "Create client" button
- General Settings
  - Client ID: apisix
- Capability config
  - Client authentication: On
  - Authentication flow: select Standard flow, Direct access grants, and Service accounts roles
- Client details
  - Valid redirect URIs: *
  - Front channel logout: Off
  - Backchannel logout session required: Off
  - Backchannel logout revoke offline sessions: Off

## Create john user

- Select "web" realm
- Go to "Users" menu
- Hit "Add user" button
- Create user
  - Username: john
  - Email verified: On
- Go "User details" page
- Select "Credentials" menu
- Hit "Set Password" button
  - Password: john
  - Password confirmation: john
  - Temporary: Off