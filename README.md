# 🤖 Azure AI Agent Demo - Complete Educational Template

A comprehensive Jupyter notebook template demonstrating how to create and use Azure AI Agents with custom functions, developed through collaboration with Claude AI.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Azure AI](https://img.shields.io/badge/Azure-AI%20Foundry-blue.svg)](https://azure.microsoft.com/en-us/products/ai-services/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

## 🎯 What You'll Learn

By working through this template, you will understand:
- ✅ How to create and configure Azure AI Agents
- ✅ How to implement custom functions for AI agents  
- ✅ How conversation threads work in AI agent systems
- ✅ Best practices for resource management and cleanup
- ✅ Real-world scenarios and use cases for AI agents
- ✅ Enterprise security patterns and cost optimization

## 🌟 Key Features

- 🔒 **Template Safety** - All credentials are placeholder values
- 📚 **Step-by-Step Education** - Complete learning guide with explanations
- 🧪 **Interactive Testing** - Live scenarios you can experiment with
- 💰 **Cost Management** - Built-in cleanup and optimization guidance
- 🚀 **Cross-Platform** - Works on Azure ML, Google Colab, and local environments
- 🔧 **Production Ready** - Enterprise security patterns and best practices

## 🔧 Azure Setup Instructions

### 1. Azure AI Foundry Project Setup
1. Create an Azure AI Foundry project in the Azure portal
2. Note your project endpoint URL  
3. Ensure you have appropriate permissions

### 2. Azure App Registration (Service Principal)
1. Go to **Azure Portal** → **Microsoft Entra ID** → **App registrations**
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
   git clone https://github.com/jojidemillo/azure-ai-agent-demo.git
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

## 📁 Repository Structure

```
azure-ai-agent-demo/
├── azure_ai_agent.ipynb    # Main educational notebook with complete demo
├── requirements.txt        # Minimal dependencies for all environments  
├── .gitignore             # Protects against accidental credential uploads
├── README.md              # This documentation
└── LICENSE                # MIT License
```

## 🎮 Demo Scenarios

The notebook includes three progressive scenarios that demonstrate real-world capabilities using **mock functions** (no real API calls):

### **Scenario 1: Weather Report Email**
Learn multi-step function chaining as the agent:
- Fetches **mock weather data** for a specified location
- Composes a **simulated email** (prints to console)
- Demonstrates parameter extraction from natural language

### **Scenario 2: Time and Calculations**
Explore parallel function execution:
- Retrieves **actual current time** and date
- Performs **real mathematical calculations**
- Shows how agents handle multiple independent requests

### **Scenario 3: Complex Business Process**
Experience enterprise-level workflow automation:
- Aggregates **mock data** from multiple sources
- Generates **simulated business reports**
- **Simulates email delivery** via console output

### **Interactive Testing Lab**
Experiment with your own scenarios using the built-in testing framework with mock functions.

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

### Custom Instructions
Update the `AGENT_INSTRUCTIONS` variable to customize agent behavior and personality.

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

### Security Best Practices
- ⚠️ **Never commit real credentials** to version control
- ✅ Use environment variables or Azure Key Vault in production
- ✅ Set up proper IAM permissions for your service principal
- ✅ Regular security audits and credential rotation

### Cost Management
- ✅ Always run the cleanup function when done testing
- ✅ Monitor usage in Azure Cost Management
- ✅ Use lower-cost models for development and testing
- ✅ Set up spending alerts to avoid unexpected charges

### Development Best Practices
- ✅ Test functions individually before chaining them
- ✅ Handle errors gracefully in custom functions
- ✅ Add proper logging for production deployments
- ✅ Use version control for your customizations

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

**Function Call Issues**
- ✅ Ensure function signatures have proper type hints
- ✅ Verify function docstrings are clear and descriptive
- ✅ Check that all required parameters are provided
- ✅ Review error logs in the notebook output

**Notebook Issues**
- ✅ Restart kernel and run cells in order
- ✅ Verify all dependencies are installed correctly
- ✅ Check Python version compatibility (3.8+)
- ✅ Clear output and restart if experiencing memory issues

## 🎓 Educational Use

This repository is designed as an educational template for learning Azure AI Agents. Feel free to:
- Fork and customize for your own learning
- Use as a reference for your projects
- Adapt the patterns for your specific use cases
- Share with others who are learning AI agent development

## 📚 Additional Resources

- [Azure AI Foundry Documentation](https://docs.microsoft.com/azure/ai-services/)
- [Azure AI Python SDK Reference](https://docs.microsoft.com/python/api/overview/azure/ai/)
- [Azure App Registration Guide](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)
- [Azure Cost Management](https://docs.microsoft.com/azure/cost-management/)
- [Azure AI Agent Service Documentation](https://docs.microsoft.com/azure/ai-services/agents/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Acknowledgments

- **Azure AI Team** for the excellent Agent Service platform
- **Claude AI** for collaboration in creating this educational resource
- **Open Source Community** for inspiration and best practices

## ⚠️ Important Notes

- This is an **educational template** with **mock functions**
- **Functions are not real API calls** - they return hardcoded data for demonstration
- Replace mock functions with real APIs for production use
- Always clean up Azure resources to avoid unexpected charges
- Monitor your Azure spending when experimenting
- This project demonstrates AI-AI collaboration in development

## 🆘 Getting Help

- **Documentation**: Check the notebook comments for detailed explanations
- **Azure Issues**: Contact Azure support for platform-specific problems
- **Learning Resources**: See the Additional Resources section above

*This is an educational template - please use it as a reference for your own learning and development.*

---

**🚀 Ready to build intelligent AI agents? Clone this repository and start your journey into enterprise AI automation!**

**Happy AI Agent building!** 🤖✨

---

*Created through collaboration between human expertise and Claude AI, demonstrating the power of AI-assisted development.*