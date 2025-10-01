# Quick Start Guide

This guide will help you quickly get started with the Business Process Catalog template.

## Prerequisites Checklist

Before you begin, make sure you have:

- [ ] Azure DevOps organization with admin access
- [ ] Process Migrator tool downloaded and extracted
- [ ] .NET Framework 4.7.2 or higher installed
- [ ] This BPC repository downloaded or cloned

## 5-Minute Setup

### 1. Download Process Migrator

```bash
# Download from: https://github.com/microsoft/process-migrator/releases
# Extract to a folder, e.g., C:\Tools\ProcessMigrator
```

### 2. Open Command Prompt or PowerShell

Navigate to the Process Migrator directory:

```bash
cd C:\Tools\ProcessMigrator
```

### 3. Authenticate with Azure DevOps

The tool will prompt for credentials when you run it. Make sure you have:
- Your Azure DevOps organization URL: `https://dev.azure.com/YourOrganization`
- Appropriate permissions (Project Collection Administrator)

### 4. Import the Template

**Note**: The current configuration.json is a reference template. For actual import with Process Migrator, you'll need to export a base process first and then customize it.

#### Option A: Create Custom Process via UI (Recommended for Beginners)

1. Go to `https://dev.azure.com/YourOrganization/_settings/process`
2. Click "Create inherited process"
3. Select "Agile" as the parent process
4. Name it "Business Process Catalog"
5. Customize using the configuration.json as a guide

#### Option B: Use Process Migrator (Advanced)

First, export an existing process to get the correct format:

```bash
process-migrator.exe export -n "Agile" -a "https://dev.azure.com/YourOrg"
```

This will create a folder with the process template. You can then modify it based on the configuration.json provided in this repository.

### 5. Create Your First Project

1. Go to Azure DevOps
2. Click "New Project"
3. Name your project (e.g., "Process Management")
4. Under "Advanced" → "Work item process", select "Business Process Catalog"
5. Click "Create"

### 6. Start Documenting Processes

1. Go to Boards → Work Items
2. Click "New Work Item"
3. Select "Business Process" from the dropdown
4. Fill in the details:
   - Title: Name of your process
   - Process Owner: Who owns this process
   - Process Category: Select the appropriate category
   - Description: Detailed description of the process

## What's Next?

- **Customize Fields**: Add more custom fields specific to your organization
- **Define Workflows**: Set up specific workflow states for your processes
- **Create Queries**: Build queries to filter and organize your processes
- **Set Up Dashboards**: Create visual dashboards to track process management

## Common First Tasks

### Task 1: Add Your First Business Process

```
Title: Customer Onboarding Process
Process Owner: Sales Team
Process Category: Sales
Priority: High
Description: Complete process for onboarding new customers
```

### Task 2: Add Process Steps

Create "Process Step" work items and link them to your Business Process:
- Step 1: Gather customer information
- Step 2: Set up customer account
- Step 3: Schedule onboarding meeting
- Step 4: Provide training materials

### Task 3: Link Documentation

Create "Process Document" work items for related documentation:
- Customer Onboarding Checklist
- Account Setup Guide
- Training Materials Repository

## Need Help?

- Review the main [README.md](README.md) for detailed instructions
- Check [CUSTOMIZATION.md](CUSTOMIZATION.md) for customization options
- Visit the [Process Migrator Wiki](https://github.com/microsoft/process-migrator/wiki)

## Tips for Success

1. **Start Small**: Begin with 3-5 key processes
2. **Iterate**: Refine your template based on team feedback
3. **Document**: Keep process documentation up to date
4. **Review Regularly**: Schedule periodic process reviews
5. **Engage Stakeholders**: Get buy-in from process owners early

Happy Process Management! 🚀
