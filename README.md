# OAuth for Wear OS with Compose

A Kotlin Wear OS sample exploring phone-assisted OAuth authentication and a Compose interface.

## What to review

- `AuthViewModel`: creates an OAuth request using `CodeVerifier` and `CodeChallenge`, launches phone-assisted authorization with `RemoteAuthClient`, and exchanges the authorization code for a token.
- `authService`: Ktor client and request helpers for authentication calls.
- `WearApp` and `QRCodeScreen`: Compose navigation and a QR-code presentation example.
- `DataLayerListenerService`: Wear OS data-layer integration.

## Local setup

1. Clone this repository and open it in Android Studio.
2. Use the checked-in Gradle wrapper and Android SDK 34. The wear module declares a minimum SDK of 26.
3. Configure an OAuth application with your provider and align the client identifier, authorization/token endpoints, and redirect configuration in the sample.
4. Run on a Wear OS device or emulator with a compatible paired phone for the phone-assisted flow.

## Sample status

This is an authentication integration sample. Its existing token request includes a `CLIENT_SECRET` field in client-side code; review and adapt that flow to your provider’s native-client requirements before reuse. Do not embed confidential credentials in a shipped application.

The QR screen is a separate example; it is not evidence of a complete OAuth device-authorization grant implementation. Build and end-to-end provider authentication have not been verified as part of this documentation update.
