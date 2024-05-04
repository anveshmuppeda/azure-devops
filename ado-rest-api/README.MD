#  
## 1. Create a YAML file:  
In your code repository, create a YAML file named azure-restapi-pipeline.yaml or any name you prefer.  

## Create pipeline json  
### Get repository ID  
```bash
REPO_ID=$(curl -s -X GET "https://dev.azure.com/$ORGANIZATION/$PROJECT/_apis/git/repositories/$REPOSITORY" -H "Authorization: Basic $PAT" | jq -r '.id')
```   

Create apipipeline.json file with the details of pipeline you want to create. 
Example:  
```json
{
    "folder": null,
    "name": "pipeline-made-by-api-2",
    "configuration": {
      "type": "yaml",
      "path": "/azure-rest-api-pipeline.yaml",
      "repository": {
        "id": "eba9d845-71ed-403a-a2ac-a5af2b0d8866",
        "name": "azure-devops-series",
        "type": "azureReposGit"
      }
    }
}
```  
Replace "name" with the name of your pipeline, "path" with the directory where your pipeline YAML definition exists, "repository/id" with the repository ID, and "repository/name" with the repository name.  


## Use Azure DevOps REST API:   
You'll need to use the Azure DevOps REST API to create the pipeline. Here's a simplified example using cURL:  

### Setting up environment variables   
```bash
# Replace placeholders with your actual values
ORGANIZATION="your-organization"
PROJECT="your-project"
REPOSITORY="your-repository"
PAT="your-personal-access-token"
```  

### Create pipeline  
```bash
curl --user ":$PAT" \
  --header "Content-Type: application/json" \
  --header "Accept: application/json" \
  "https://dev.azure.com/$ORGANIZATION/$PROJECT/_apis/pipelines?api-version=6.0-preview.1" \
  -d @apipipeline.json
```  

Using the above command the pipeline got created, login to azure devops and check the pipeline.  

### References  
1. https://learn.microsoft.com/en-us/rest/api/azure/devops/pipelines/pipelines/create?view=azure-devops-rest-6.1#createpipelineconfigurationparameters  
2. https://johnnyreilly.com/create-pipeline-with-azure-devops-api  


Or directly you can use below command to create pipeline.  
```bash
curl --user '':'MYPATTOKEN' \
  --header "Content-Type: application/json" \
  --header "Accept: application/json" \
  'https://dev.azure.com/amuppeda/azure-devops-series/_apis/pipelines?api-version=6.1-preview.1' \
  -d @apipipeline.json
```