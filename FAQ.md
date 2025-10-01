# Frequently Asked Questions (FAQ)

## General Questions

### What is the Business Process Catalog (BPC) template?

The BPC template is a customized Azure DevOps process template designed to help organizations document, manage, and track their business processes. It extends the standard Agile process with specialized work item types and fields for process management.

### Who should use this template?

This template is ideal for:
- Business Process Management teams
- Process improvement initiatives
- Organizations implementing ISO standards
- Compliance and audit teams
- Operations teams documenting workflows
- Any organization wanting to catalog their business processes

### What version of Azure DevOps does this work with?

The template works with:
- Azure DevOps Services (cloud)
- Azure DevOps Server 2019 and later
- Team Foundation Server 2018 (with limitations)

## Installation Questions

### Do I need special permissions to import the template?

Yes, you need to be a member of the **Project Collection Administrators** group in your Azure DevOps organization.

### Can I use this template on Azure DevOps Server (on-premises)?

Yes, the Process Migrator tool supports both Azure DevOps Services and Azure DevOps Server 2019+.

### What if I don't have .NET Framework 4.7.2?

The Process Migrator tool requires .NET Framework 4.7.2 or higher. You can download it from:
https://dotnet.microsoft.com/download/dotnet-framework

### Can I import this template multiple times?

Yes, you can import it with different names (e.g., "BPC v1", "BPC Custom") for testing or different use cases.

## Customization Questions

### Can I modify the template after importing?

Yes! You can customize the template through:
1. Azure DevOps UI (Organization Settings → Process)
2. Export, modify, and re-import using Process Migrator

### Can I add my own custom fields?

Absolutely. You can add as many custom fields as needed through the Process customization interface or by modifying the exported JSON files.

### Can I remove work item types I don't need?

You cannot delete work item types, but you can:
- Disable them (they won't appear in the UI)
- Hide them from certain projects
- Simply not use them

### Will customizations affect existing projects?

No. Changes to the process template only affect new projects or projects you explicitly update to use the new version.

## Usage Questions

### How do I create a hierarchy of processes?

Use the parent-child linking feature:
1. Create a main "Business Process" work item
2. Create "Process Step" work items
3. Link the steps as children of the main process

### Can I track process versions?

Yes, several approaches:
1. Use the built-in "History" tab on work items
2. Add a custom "Version" field
3. Clone processes and mark old versions as "Deprecated"

### How do I set up process review reminders?

1. Add "Next Review Date" field to your processes
2. Create a query to find processes due for review
3. Set up alerts on the query
4. Use Azure DevOps automation rules to send notifications

### Can I integrate with other systems?

Yes, through:
- Azure DevOps REST API
- Power Automate connectors
- Custom integrations using the API
- Export to Excel/CSV for external use

## Process Migrator Questions

### What does Process Migrator actually do?

Process Migrator is a command-line tool that:
- Exports process templates from Azure DevOps
- Imports process templates to Azure DevOps
- Allows offline editing of process definitions

### Where can I get help with Process Migrator?

- GitHub Repository: https://github.com/microsoft/process-migrator
- Wiki: https://github.com/microsoft/process-migrator/wiki
- Issues: https://github.com/microsoft/process-migrator/issues

### Can I use Process Migrator for migration between organizations?

Yes, that's one of its primary use cases. Export from one organization and import to another.

### Does Process Migrator migrate work items?

No. Process Migrator only handles process template definitions. For work item migration, use:
- Azure DevOps migration tools
- Excel import/export
- Third-party migration tools

## Troubleshooting Questions

### Why can't I see my custom process in the project creation dropdown?

Possible causes:
1. Process import failed (check for error messages)
2. You're not looking in the "Advanced" section during project creation
3. Process is disabled
4. Browser cache issues (try refreshing)

### Why am I getting authentication errors with Process Migrator?

Solutions:
1. Ensure you have the correct organization URL
2. Check you have proper permissions
3. Try generating a Personal Access Token (PAT) with full access
4. Verify your PAT hasn't expired

### Can I undo a process import?

You can:
- Create a new process with your old settings
- Switch projects to use a different process
- You cannot delete a process being used by projects

### What if the configuration.json doesn't import correctly?

The configuration.json in this repository is a **reference template**, not a direct import file. To use Process Migrator:
1. Export an existing process first
2. Use that export's structure
3. Modify it based on the configuration.json
4. Re-import the modified export

## Best Practices Questions

### How many processes should I document?

Start small:
- Phase 1: 5-10 critical processes
- Phase 2: 20-30 important processes
- Phase 3: Expand based on value delivered

### How often should I review processes?

Recommended frequencies:
- Critical processes: Quarterly
- Important processes: Semi-annually
- Standard processes: Annually

### Should I document every detail?

No. Focus on:
- Key steps and decision points
- Critical dependencies
- Compliance requirements
- Common issues and resolutions

### How do I get team adoption?

1. Start with a pilot team
2. Show quick wins
3. Make it easy to use
4. Integrate with existing workflows
5. Provide training and support
6. Celebrate successes

## Technical Questions

### Can I export my customized template to share with others?

Yes! Use Process Migrator to export your customized template, then share the exported files.

### Does this work with GitHub Projects?

No, this is specifically for Azure DevOps. GitHub Projects uses a different system.

### Can I use this with Azure Boards only?

Yes, you can use just Azure Boards without other Azure DevOps services.

### Are there any costs?

The BPC template itself is free. Azure DevOps costs depend on:
- Number of users (first 5 are free)
- Required features
- Storage needs

See Azure DevOps pricing: https://azure.microsoft.com/pricing/details/devops/

## Support Questions

### Where can I get help?

1. This repository's GitHub Issues
2. Azure DevOps community forums
3. Stack Overflow (tag: azure-devops)
4. Microsoft documentation

### How do I report a bug?

Open an issue on GitHub with:
- Clear description
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if relevant

### Can I request new features?

Yes! Open an issue with the "enhancement" label and describe your idea.

### Is there paid support available?

This is a community template. For Azure DevOps support:
- Microsoft Support (for enterprise customers)
- Azure DevOps consulting partners
- Community forums

## Contributing Questions

### Can I contribute to this template?

Yes! We welcome contributions. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### What kind of contributions are helpful?

- Documentation improvements
- Bug fixes
- New features
- Industry-specific customizations
- Translation to other languages
- Sample processes and examples

### Do I need to know programming to contribute?

Not necessarily! You can contribute:
- Documentation
- Examples
- Feedback and suggestions
- Testing and bug reports

---

## Still Have Questions?

If your question isn't answered here:
1. Check the [README.md](README.md)
2. Review the [QUICKSTART.md](QUICKSTART.md)
3. Search existing GitHub Issues
4. Open a new issue with your question

We're here to help! 🚀
