## 🧾 Workflow Name: Maven Build and Publish

## 🕹️ Triggers:

Runs automatically when you push to the main branch

Can also be started manually from the Actions tab (workflow_dispatch)

## ⚙️ Job: build

Runs your CI/CD pipeline on Ubuntu.

## Steps performed:

Checkout code
→ Pulls your project files from the repository so Maven can access them.

Build with Maven
→ Executes mvn clean package, which:

Cleans previous builds

Compiles the source code

Runs tests

Packages the project (e.g., generates .jar or .war file in target/)

Publish to GitHub Packages
→ Executes mvn deploy -s settings.xml, which:

Uses credentials stored in GitHub Secrets (USERNAME and TOKEN)

Deploys (uploads) the built artifact to GitHub Packages, your Maven package repository.

Verify JAR
→ Lists the contents of the target/ directory to confirm the JAR/WAR was created successfully.

## 💡 In short:

This workflow automatically:

Checks out your code → builds it with Maven → publishes the generated package to GitHub Packages → and verifies the artifact.

It acts as both a CI (build/test) and CD (publish) workflow.
