<!-- This is an example of a use case related to a different software project named ReUse ITESO -->

# UC1 : Log in through device biometrics

## Parent Functional Idea

This Use Case refines the functional idea:

**Biometrics and fast-access. Allowing users to log in using device biometrics (Face ID, Fingerprint) or authenticator apps for streamlined mobile authentication**

## Description

Allowing users to log in to ReUse ITESO using their current device’s available biometrics log in methods.

## Primary Actor

ReUse ITESO user

## Supporting Actors

- Device biometrics OAUTH service

## Benefit

User gains access to ReUse ITESO using their biometric data

## Trigger

Selecting a “Log in with biometrics” option when trying to log in

## Preconditions

- User has a registered ReUse ITESO account
- User’s device allows biometric data OAUTH
- User has allowed ReUse ITESO to access the device’s biometrics OAUTH service

## Primary Flow

1. User opens the ReUse ITESO login page
2. User selects the “Log in through biometrics” option
3. User provides the biometric data needed to log in through the device’s available methods
4. The device’s biometrics OAUTH service validates the provided data
5. The device’s biometrics OAUTH service confirms successful user auth
6. The user receives access to ReUse ITESO

## Postconditions

- The device’s biometrics OAUTH service confirms user auth
- User has access to ReUse ITESO

## Alternate Flows

### AF1 — Too many attempts

User biometrics auth fails multiple times and the device falls back to pin/passcode
- User provides the biometric data needed to log in through the device’s available methods
- The device’s biometrics OAUTH service validates the provided data
- The device’s biometrics OAUTH service rejects user auth
- User tries again multiple times
- After multiple attempts, the device automatically falls back to the lock screen pin/passcode 
- User enters pin/passcode

The device valdiates user auth and returns to the Primary Flow.

## Exception Flows

### EF1 — Not confirmed user auth

The user fails to provide valid biometric data

The user is not authenticated, does not gain access to ReUse ITESO and returns to main log in page.

### EF2 — ReUse ITESO app has no access to the device's biometrics OAUTH service

The app doesn't have the necessary permission to use the biometrics OAUTH service 

The user does not gain access to ReUse ITESO and returns to main log in page.

### EF3 — Current device has no biometrics OAUTH service

The user's current device does not have any biometric auth methods

The user does not gain access to ReUse ITESO and returns to the main log in page.