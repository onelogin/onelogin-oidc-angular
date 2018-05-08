# OneLogin OpenId Connect Angular

This repo contains a bare bones Angular 4 application that makes use of the OpenId Connect Implicit flow to authenticate a user.

## Prerequisites
In order to authenticate a user in this sample you will need to create an OpenId Connect
app in your OneLogin Admin portal. You can [read more about how to do that here](https://developers.onelogin.com/openid-connect/connect-to-onelogin).

If you don't have a OneLogin developer account [you can sign up here](https://www.onelogin.com/developer-signup).

To run the sample you will need Angular CLI installed

```sh
npm install -g @angular/cli
```

## Setup
In production you would initialize these variables in your environment configuration but for the same of keeping the sample simple we have hardcoded them in `src/app/services/auth.service.ts`.

Replace the following with your own values

- **authority** - Your OneLogin subdomain `https://replace-with-your-subdomain.onelogin.com/oidc`
- **client_id** - The Client Id for the OpenId Connect app you created in the OneLogin portal. e.g. `78d1d040-20c9-0336-5146-067351775fae92222`

You should also make sure that you have configured `http://localhost:4200/auth-callback` as a **redirect uri** on the Configuration tab of your app.

## Run

Run the sample from the `client` directory in this repo with `ng serve`.

## What can I use these for
OpenId Connect is a great way to add user authentication to your application
where you are depending on another party to manage the user identities.

In this case OneLogin can manage the identity of your users making it
faster to get up and running.

## Single Sign On (SSO)
By implementing OpenId Connect via OneLogin you are creating a OneLogin
session which can be used to single sign on from your custom app
into other apps that your users may have access to via the OneLogin portal

## MFA
If MFA is enabled for a user in OneLogin then they will be prompted to
enter a token during the authentication. OneLogin takes care of all of this
for you, making strong authentication much easier to implement in your app.

## Credits
This project is based off [a great walkthrough provided by Scott Brady](https://www.scottbrady91.com/Angular/SPA-Authentiction-using-OpenID-Connect-Angular-CLI-and-oidc-client)which is worth checking out if you want a step by step guide on how to create the AuthGuard and AuthService etc.
