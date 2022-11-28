# Azure APIM APIOPs

```bash
# Create dev & prod resource group
rgDevId=$(az group create --name rg-apim-apiops-dev --location canadacentral --query id -o tsv)
rgProdId=$(az group create --name rg-apim-apiops-prod --location canadacentral --query id -o tsv)

# Create an Azure AD Service Principal 
az ad sp create-for-rbac --name "apiopslab-dev" --role contributor --scopes $rgDevId --sdk-auth
az ad sp create-for-rbac --name "apiopslab-prod" --role contributor --scopes $rgProdId --sdk-auth