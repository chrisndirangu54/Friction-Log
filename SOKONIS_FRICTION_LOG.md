# Sokonis — Amazon Developer Hackathon Friction Log

Project: [Sokonis Alexa/AWS integration](https://github.com/chrisndirangu54/Sokonis-open-source)  
Hackathon: Build, Ship, Shape Amazon Developer Hackathon (2026)

This record distinguishes actual development work from integrations not yet tested end-to-end. No unobserved AWS or Alexa errors are attributed to the services.

## 1. Alexa and Firebase integration
- **Task:** Extend the existing Flutter/Firebase grocery marketplace using Alexa and AWS Lambda.
- **Steps taken:** Built an Alexa custom-skill handler, product and meal intents, a Lambda configuration, and Firestore adapter.
- **Expected:** A voice interface operating against Sokonis inventory and shopping data.
- **Actual:** Source implementation exists; the cross-system integration needs deployment and production-data verification.
- **Severity:** Important.
- **Workaround:** Separate voice handler, application logic, and Firestore adapter into independent modules.
- **Suggestion:** Provide complete Alexa-to-Firebase reference examples including secure account linking.

## 2. Natural-language grocery workflows
- **Task:** Interpret product names and ingredients, with future support for shopping lists and multi-step conversations.
- **Steps taken:** Developed bounded product search, meal-suggestion logic and validation.
- **Expected:** Context-aware grocery assistance across different user requests.
- **Actual:** Basic pathways were developed; regional language handling, multi-turn context and live personalized interactions remain unverified.
- **Severity:** Important.
- **Workaround:** Start with discrete intents and deterministic sample inventory.
- **Suggestion:** Publish sample workflows for quantities, substitutions, budgets and Kenyan grocery terms.

## 3. Cross-cloud data access
- **Task:** Connect AWS-hosted logic with Firebase Firestore.
- **Steps taken:** Implemented a Firebase Admin SDK storage adapter and an authenticated API example.
- **Expected:** Consistent authorized access to product and shopping-list data.
- **Actual:** Adapter has not been validated against the live Sokonis database schema and identity configuration.
- **Severity:** Important.
- **Workaround:** Keep adapter independent of business logic, with a demo-mode storage implementation.
- **Suggestion:** Supply practical least-privilege guidance and schema migration examples for AWS/Firebase integrations.

## 4. Validation before live AWS deployment
- **Task:** Test integration code without connecting production resources.
- **Steps taken:** Added Node.js unit tests, GitHub Actions and an AWS SAM deployment template.
- **Expected:** Repeatable tests before staging and live deployment.
- **Actual:** Three initial local tests passed. Live Lambda, Alexa endpoint, Bedrock inference and CI results still need independent verification.
- **Severity:** Moderate.
- **Workaround:** Isolated testable business logic and used sample product data.
- **Suggestion:** Include local Alexa simulation tools and validation examples for AWS service configuration.

## 5. Publishing without exposing production systems
- **Task:** Share reusable source code while keeping the original Sokonis application private.
- **Steps taken:** Created a separate public MIT-licensed repository with code, deployment template and documentation.
- **Expected:** Open-source integration materials usable without private keys or customer records.
- **Actual:** Public contribution published; production connection remains a distinct future step.
- **Severity:** Minor.
- **Workaround:** Use a separate repository and environment-based configuration.
- **Suggestion:** Provide more examples of safe public integration projects for existing private apps.

## Summary
The principal engineering challenge was separating conversational intent handling from commerce data access without compromising maintainability or account security. Future work includes AWS deployment, real database schema alignment, authenticated account linking, and full Alexa+ compliance testing.

**Status:** This describes implemented source and work still outstanding, rather than inventing errors from services that have not been tested.
