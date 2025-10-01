# Business Process Catalog (BPC) Template for Azure DevOps

A comprehensive Business Process Catalog template designed for Azure DevOps that helps organizations document, manage, and track their business processes effectively.

> 📚 **Quick Links**: [Quick Start](QUICKSTART.md) | [Customization Guide](CUSTOMIZATION.md) | [FAQ](FAQ.md) | [Examples](examples/) | [Documentation Index](DOCS.md)

## Overview

This repository provides a ready-to-use Business Process Catalog template that can be imported into your Azure DevOps organization. The template includes custom work item types and fields specifically designed for cataloging and managing business processes.

## Features

- **Custom Work Item Types**: Pre-configured work items tailored for business process management
- **Process Hierarchy**: Structured approach to organize business processes
- **Easy Import**: Simple import process using Microsoft's Process Migrator tool
- **Customizable**: Fully customizable to meet your organization's specific needs

## Prerequisites

Before importing this template, ensure you have:

1. **Azure DevOps Organization**: An active Azure DevOps organization with administrative access
2. **Process Migrator Tool**: Download and install the Microsoft Process Migrator tool from:
   - GitHub: [https://github.com/microsoft/process-migrator](https://github.com/microsoft/process-migrator)
   - Latest Release: [Download Process Migrator](https://github.com/microsoft/process-migrator/releases)
3. **Permissions**: You need to be a member of the Project Collection Administrators group in Azure DevOps
4. **.NET Framework**: .NET Framework 4.7.2 or higher (required by Process Migrator)

## Installation Instructions

### Step 1: Download the Template

Clone or download this repository to your local machine:

```bash
git clone https://github.com/MVPJuanBravo/BPC.git
```

Or download as ZIP from the GitHub repository.

### Step 2: Install Process Migrator

1. Download the latest release of Process Migrator from [GitHub Releases](https://github.com/microsoft/process-migrator/releases)
2. Extract the downloaded ZIP file to a folder on your computer
3. Note the location of `process-migrator.exe`

### Step 3: Export Your Current Process (Optional)

If you want to base your customizations on an existing process:

```bash
process-migrator.exe export -n "YourProcessName" -a "https://dev.azure.com/YourOrg"
```

### Step 4: Prepare the BPC Template

The BPC template files are located in the root directory of this repository. Ensure all template files are accessible before proceeding.

### Step 5: Import the BPC Template

Use the Process Migrator to import the Business Process Catalog template into your Azure DevOps organization:

```bash
process-migrator.exe import -n "Business Process Catalog" -f "path\to\BPC\template.json" -a "https://dev.azure.com/YourOrg"
```

**Parameters:**
- `-n`: Name for your new process template
- `-f`: Path to the template JSON file
- `-a`: Your Azure DevOps organization URL

### Step 6: Create a Project Using the BPC Template

1. Go to your Azure DevOps organization
2. Click on **"New Project"**
3. Enter your project name and description
4. Under **"Advanced"**, select **"Business Process Catalog"** (or the name you used during import) as the work item process
5. Click **"Create"**

## Template Structure

The Business Process Catalog template includes:

- **Process Definition**: Core process template configuration
- **Work Item Types**: Custom work items for business processes
- **Fields**: Specialized fields for process documentation
- **Workflow States**: Defined states for process lifecycle management

## Usage

After importing the template and creating a project:

1. **Create Business Processes**: Use the custom work item types to document your business processes
2. **Organize Hierarchically**: Structure processes using parent-child relationships
3. **Track Changes**: Monitor process updates and changes over time
4. **Collaborate**: Use Azure DevOps boards to collaborate with your team on process improvements

## Customization

To customize the template:

1. Export your process after importing:
   ```bash
   process-migrator.exe export -n "Business Process Catalog" -a "https://dev.azure.com/YourOrg"
   ```

2. Modify the exported JSON files according to your needs

3. Re-import the customized template:
   ```bash
   process-migrator.exe import -n "Custom BPC" -f "path\to\modified\template.json" -a "https://dev.azure.com/YourOrg"
   ```

## Troubleshooting

### Common Issues

**Issue**: "Access denied" error during import
- **Solution**: Ensure you're a member of the Project Collection Administrators group

**Issue**: Process Migrator tool doesn't run
- **Solution**: Verify you have .NET Framework 4.7.2 or higher installed

**Issue**: Template import fails
- **Solution**: Check that all template files are present and properly formatted

### Getting Help

- **Process Migrator Documentation**: [Microsoft Process Migrator Wiki](https://github.com/microsoft/process-migrator/wiki)
- **Azure DevOps Process Customization**: [Microsoft Docs](https://docs.microsoft.com/en-us/azure/devops/organizations/settings/work/manage-process)

## Contributing

Contributions to improve the Business Process Catalog template are welcome! Please:

1. Fork this repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request with a clear description of improvements

## License

This template is provided as-is for use with Azure DevOps. Please refer to Microsoft's licensing terms for Azure DevOps and the Process Migrator tool.

## Support

For issues or questions:
- Open an issue in this repository
- Check the Process Migrator [GitHub Issues](https://github.com/microsoft/process-migrator/issues)

## Resources

- [Microsoft Process Migrator](https://github.com/microsoft/process-migrator)
- [Azure DevOps Documentation](https://docs.microsoft.com/en-us/azure/devops/)
- [Customize a Process](https://docs.microsoft.com/en-us/azure/devops/organizations/settings/work/customize-process)

---

**Version**: 1.0  
**Last Updated**: 2024  
**Maintained By**: MVPJuanBravo
