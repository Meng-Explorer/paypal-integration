# PayPal Payment Integration

A Spring Boot web application that demonstrates a PayPal checkout flow. Users can enter a payment amount, select USD or EUR, and approve the payment through PayPal. The app handles the success, cancellation, and error pages.

## Requirements

- Java 25
- PayPal developer account with sandbox API credentials

The project includes the Gradle wrapper, so a separate Gradle installation is not required.

## Configure PayPal

Set your PayPal credentials and mode as environment variables before starting the app. Spring Boot reads these environment variables as overrides for the `paypal.*` settings:

**PowerShell**

```powershell
$env:PAYPAL_CLIENT_ID = "your-sandbox-client-id"
$env:PAYPAL_CLIENT_SECRET = "your-sandbox-client-secret"
$env:PAYPAL_MODE = "sandbox"
```

Use sandbox credentials and `sandbox` mode for testing. Do not commit credentials to source control. The existing credentials in `src/main/resources/application.yaml` should be rotated and replaced with environment-based configuration. The `.env.example` file is a reference only; Spring Boot does not load `.env` files automatically.

## Run the application

From the project root:

```powershell
.\gradlew.bat bootRun
```

Open [http://localhost:8081](http://localhost:8081) in a browser. The application listens on port `8081`.

To create a payment, submit the checkout form and approve it in the PayPal sandbox. Use a sandbox buyer account to complete the test.

## Build and test

```powershell
.\gradlew.bat build
```

Run tests only:

```powershell
.\gradlew.bat test
```
