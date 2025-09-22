# Google Cloud Setup Instructions

## Prerequisites
1. Install Google Cloud CLI: https://cloud.google.com/sdk/docs/install
2. Authenticate with your Google account

## Setup Commands (Run these in your terminal)

```bash
# Set your project
gcloud config set project ai-trip-planner-472817

# Enable required APIs
gcloud services enable aiplatform.googleapis.com
gcloud services enable cloudfunctions.googleapis.com
gcloud services enable storage.googleapis.com
gcloud services enable firestore.googleapis.com

# Authenticate for Application Default Credentials
gcloud auth application-default login

# Verify the setup
gcloud config list
gcloud services list --enabled
```

## Alternative: Service Account Key (for production)
If you prefer using a service account key file:

1. Go to: https://console.cloud.google.com/iam-admin/serviceaccounts?project=ai-trip-planner-472817
2. Create a new service account
3. Grant it "Vertex AI User" role
4. Create and download a JSON key
5. Set environment variable: GOOGLE_APPLICATION_CREDENTIALS=path/to/key.json

## Verification
After running the commands above, test with:
```bash
gcloud auth list
gcloud projects describe ai-trip-planner-472817
```