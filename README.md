# Deploying a Python Azure Function

This repository contains a **Python-based Azure Function App** for automated tasks, with a GitHub Actions workflow for continuous deployment.

---

## Purpose

Automatically deploy the Azure Function to Azure whenever code is pushed to the `main` branch, using GitHub Actions.

---

## Technologies Used

- Python 3.11  
- Azure Functions  
- GitHub Actions  
- Oryx Build System  
- Azure Publish Profile (for GitHub authentication)

---

## Deployment with GitHub Actions

### File:
`.github/workflows/deploy.yml`

### Triggered:
- Automatically on `push` to the `main` branch  
- Manually via GitHub’s **Actions** tab

### Workflow steps:

1. Check out the repository code  
2. Set up Python 3.11  
3. Deploy to Azure using Oryx (which installs all dependencies listed in `requirements.txt`)

---

## Required Secret

You must add the following GitHub secret to enable deployment:

| Secret name | Description |
|-------------|-------------|
| `AZUREAPPSERVICE_PUBLISHPROFILE_xxxxxxxxxxx` | The publish profile from Azure (contents of `.PublishSettings` file) |

To obtain the publish profile:
1. Go to Azure Portal  
2. Open your Function App  
3. Navigate to "Deployment Center"  
4. Click "Get publish profile" and copy the content into your GitHub repository 

---

## Expected Behavior

Each time code is pushed to the `main` branch:

- Dependencies (like `requests`, `pandas`, etc.) are installed automatically  
- The code is deployed to the specified Azure Function App  
- The function is made immediately available in production

---

## Example Use Case

An HTTP-triggered Azure Function that:
- Compares accounting Excel files  
- Generates a ZIP file of results  
- Uploads it to SharePoint or another storage system

---

## Contact

Feel free to open an issue or pull request for questions or improvements.