# CI CD Pipeline
## Architecture

Devleoper -> GitHub <- Jenkins - Uses Gradle, Pushes the Artifact to AWS Code Artifact

## CI Setup
Jenkins
 1. Checkout SCM
 2. Build the code (Compile)
 3. Test (Run any unit test)
 4. Create Artifact
 5. Push Artifiact

## CD Setup
1. Pull the Artifact
2. Deploy to Elastic Bean Stalk
