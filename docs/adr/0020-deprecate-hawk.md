# Deprecate Hawk authentication on fxa-auth-server

- Deciders: Danny Coates, Ryan Kelly, Les Orchard, Ben Bangert
- Date: 2020-05-27

## Context and Problem Statement

The new FxA settings page introduces a new service in the form of a GQL API that will provide account and profile data to the browser. This service needs to make api requests to the auth-server on behalf of logged in users. The auth-server uses hawk authentication so adding another service between the browser and auth-server is not straightforward. In [ADR-0017](0017-switch-settings-auth-to-sessiontoken.md) we decided to allow the browser to share the session token with the GQL server so that it can make hawk authenticated requests. This leads us to question whether we should deprecate our use of hawk altogether.

## Decision Drivers

- Security

## Considered Options

- Deprecate use of hawk
- Continue using hawk in future work

## Decision Outcome

We will stop using hawk in future work that requires authentication. Selecting a preferred scheme is out of scope of this ADR. Sharing the session token with trusted services is an acceptable interim solution.

## Pros and Cons of the Options

### Deprecate use of hawk

### Continue using hawk in future work
