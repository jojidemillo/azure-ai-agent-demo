## 🔧 Azure Setup Instructions

### 1. Azure AI Foundry Project Setup
1. Create an Azure AI Foundry project in the Azure portal
2. Note your project endpoint URL  
3. Ensure you have appropriate permissions

### 2. Azure App Registration (Service Principal)
1. Go to **Azure Portal** → **Azure Active Directory** → **App registrations**
2. Create **New registration** with a descriptive name
3. Copy these values for the notebook configuration:
   - **Application (client) ID** → `AZURE_CLIENT_ID`
   - **Directory (tenant) ID** → `AZURE_TENANT_ID`
4. Create a **client secret** → `AZURE_CLIENT_SECRET`

### 3. Grant Required Permissions
**Critical Step:** Your App Registration needs proper permissions on the AI Foundry project:

1. **Navigate to your Azure AI Foundry project** in the Azure portal
2. **Go to Access control (IAM)** in the left sidebar
3. **Click "Add" → "Add role assignment"**
4. **Assign these roles** to your App Registration:
   - **Cognitive Services Data Contributor** ← **Required for AI Agents**
   - **AI Developer** (if available in your subscription)
   - **Reader** (for basic access)

**Without these permissions, agent creation will fail with authentication errors.**

### 4. Configure the Notebook
Open `azure_ai_agent.ipynb` and replace the placeholder values in the configuration section:

```python
# Replace these with your actual values  
os.environ["AZURE_CLIENT_ID"] = "your-actual-client-id"        
os.environ["AZURE_TENANT_ID"] = "your-actual-tenant-id"          
os.environ["AZURE_CLIENT_SECRET"] = "your-actual-client-secret"      
project_endpoint = "https://your-resource.services.ai.azure.com/api/projects/your-project"
```

⚠️ **Security Note:** These are placeholder values in the template. Replace them with your actual Azure credentials. Never commit real credentials to version control!

# Azure AI Agent Demo - Complete Educational Template

🤖 A comprehensive Jupyter notebook template demonstrating how to create and use Azure AI Agents with custom functions.

## 🎯 What You'll Learn

By working through this template, you will understand:
- How to create and configure Azure AI Agents
- How to implement custom functions for AI agents  
- How conversation threads work in AI agent systems
- Best practices for resource management and cleanup
- Real-world scenarios and use cases for AI agents

## 🚀 Quick Start

### **Cloud Environments (Recommended)**

#### **Azure ML Studio:**
1. Upload `azure_ai_agent.ipynb` to your Azure ML workspace
2. Install dependencies: `!pip install azure-ai-projects azure-identity`
3. Replace credential placeholders with your Azure values
4. Run the notebook step by step

#### **Google Colab:**
1. Upload `azure_ai_agent.ipynb` to Google Colab
2. Install dependencies: `!pip install azure-ai-projects azure-identity`
3. Replace credential placeholders with your Azure values
4. Run the notebook step by step

### **Local Development**

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/azure-ai-agent-demo.git
   cd azure-ai-agent-demo
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   pip install jupyter notebook  # If not already installed
   ```

3. **Open the notebook**
   ```bash
   jupyter notebook azure_ai_agent.ipynb
   ```

4. **Replace credential placeholders** with your Azure values

5. **Run the demo scenarios** step by step

## 📋 Prerequisites

### Azure Requirements
- **Azure subscription** with access to Azure AI Foundry
- **Azure AI Foundry project** created in Azure portal
- **App Registration** (Service Principal) with appropriate permissions

### Development Environment
- **Python 3.8+**
- **Jupyter Notebook** environment (for local development)
- **Git** (for cloning the repository)

## 📦 Installation & Dependencies

### **Requirements**
This template has minimal dependencies that work across all environments:

```
azure-ai-projects>=1.0.0
azure-identity>=1.15.0
```

### **Installation Methods**

#### **Cloud Environments (Azure ML, Google Colab)**
The notebook includes installation commands:
```python
# Run this cell in the notebook
!pip install azure-ai-projects azure-identity
```

#### **Local Development**
```bash
pip install -r requirements.txt
pip install jupyter notebook  # If not already installed
```

#### **Conda Users**
```bash
conda install pip
pip install azure-ai-projects azure-identity
```

## 📁 Repository Files

- **`azure_ai_agent.ipynb`** - Main educational notebook with complete demo
- **`requirements.txt`** - Minimal dependencies for all environments  
- **`.gitignore`** - Protects against accidental credential uploads
- **`README.md`** - This documentation

## 🛡️ Security & Best Practices

### Template Safety
- ✅ All credentials in the notebook are **placeholder values**
- ✅ `.gitignore` prevents accidental credential uploads
- ✅ Clear instructions on what to replace

### For Users of This Template  
- ⚠️ **Never commit real credentials** to any repository
- ✅ Use environment variables or Azure Key Vault in production
- ✅ Always run the cleanup function to avoid unnecessary Azure charges
- ✅ Monitor usage in Azure Cost Management

## 🏗️ Customization

### Adding New Functions
1. Define your function with proper type hints and docstrings
2. Add it to the `agent_functions` list
3. Update the `execute_function_call()` handler
4. Test with the interactive lab

### Changing AI Models
Modify the `AGENT_MODEL` variable to use different models:
- `gpt-4o` - Latest model, best performance
- `gpt-4` - Reliable, excellent quality
- `gpt-4-turbo` - Faster processing
- `gpt-35-turbo` - Cost-effective option

## 💡 Best Practices

### Security
- ⚠️ **Never commit real credentials** to version control
- ✅ Use environment variables or Azure Key Vault in production
- ✅ Set up proper IAM permissions for your service principal

### Cost Management
- ✅ Always run the cleanup function when done testing
- ✅ Monitor usage in Azure Cost Management
- ✅ Use lower-cost models for development and testing

### Development
- ✅ Test functions individually before chaining them
- ✅ Handle errors gracefully in custom functions
- ✅ Add proper logging for production deployments

## 🔍 Troubleshooting

### Common Issues

**Authentication Errors**
- ✅ Verify your App Registration credentials are correct
- ✅ Confirm the App Registration has proper permissions on the AI Foundry project
- ✅ Check that your service principal has "Cognitive Services Data Contributor" role
- ✅ Ensure your Azure AI Foundry project is accessible

**Agent Creation Failures**
- ✅ Verify "Cognitive Services Data Contributor" role is assigned
- ✅ Confirm your project endpoint URL is correct
- ✅ Verify the selected model is available in your region
- ✅ Check Azure service status if experiencing outages

## 📚 Additional Resources

- [Azure AI Foundry Documentation](https://docs.microsoft.com/azure/ai-services/)
- [Azure AI Python SDK Reference](https://docs.microsoft.com/python/api/overview/azure/ai/)
- [Azure App Registration Guide](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)
- [Azure Cost Management](https://docs.microsoft.com/azure/cost-management/)

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Important Notes

- This is an **educational template** with mock functions
- Replace mock functions with real APIs for production use
- Always clean up Azure resources to avoid unexpected charges
- Monitor your Azure spending when experimenting

---

**Happy AI Agent building! 🚀**

For questions or support, please open an issue in this repository.
