# Customization Guide

This guide explains how to customize the Business Process Catalog template to meet your organization's specific needs.

## Understanding the Template Structure

The Business Process Catalog template consists of:

1. **Work Item Types**: Define the types of items you can create
2. **Fields**: Custom fields for capturing process information
3. **States**: Workflow states for process lifecycle
4. **Rules**: Automation rules for work item behavior

## Customizing via Azure DevOps UI

The easiest way to customize is through the Azure DevOps web interface.

### Accessing Process Customization

1. Navigate to: `https://dev.azure.com/YourOrganization/_settings/process`
2. Find your "Business Process Catalog" process
3. Click on it to start customizing

### Adding Custom Fields

1. Click on a work item type (e.g., "Business Process")
2. Click "New field"
3. Configure the field:
   - **Name**: Display name for the field
   - **Type**: String, Integer, DateTime, Boolean, etc.
   - **Description**: Help text for users
   - **Required**: Whether the field must be filled

#### Example Custom Fields

```
Field Name: SOP Document Link
Type: String
Description: Link to the Standard Operating Procedure document
Required: No

Field Name: Estimated Annual Cost
Type: Decimal
Description: Estimated annual cost of maintaining this process
Required: No

Field Name: Automation Level
Type: Picklist
Options: Manual, Semi-Automated, Fully Automated
Description: Current automation level of the process
Required: No
```

### Adding Work Item Types

1. In your process, click "New work item type"
2. Enter details:
   - **Name**: The name of your work item type
   - **Icon**: Choose an icon
   - **Color**: Pick a color
   - **Description**: Brief description

#### Suggested Additional Work Item Types

- **Process Improvement**: Track improvements to existing processes
- **Process Audit**: Document audit findings
- **Process Risk**: Identify and manage process-related risks
- **Process Metric**: Track KPIs for processes

### Customizing Workflow States

1. Click on a work item type
2. Go to "States" tab
3. Add, remove, or modify states:
   - **Draft**: Initial state for new processes
   - **In Review**: Process under review
   - **Approved**: Process approved but not yet active
   - **Active**: Process is active and being used
   - **Under Revision**: Process being updated
   - **Deprecated**: Process no longer in use

#### State Categories

Map your states to categories:
- **Proposed**: Draft, New
- **InProgress**: In Review, Under Revision
- **Resolved**: Approved, Active
- **Removed**: Deprecated, Archived

### Adding Rules

Rules automate work item behavior. Examples:

1. **Auto-assign Process Owner**:
   - When: Work item is created
   - Then: Set "Assigned To" to the Process Owner field value

2. **Set Review Date**:
   - When: State changes to "Active"
   - Then: Set "Next Review Date" to 365 days from today

3. **Require Approval**:
   - When: State changes to "Active"
   - Then: Require field "Approved By" to be filled

## Customizing via Process Migrator

For advanced customizations, use the Process Migrator tool.

### Step 1: Export Current Process

```bash
process-migrator.exe export -n "Business Process Catalog" -a "https://dev.azure.com/YourOrg"
```

This creates a folder with JSON files representing your process.

### Step 2: Modify JSON Files

The export creates several files:

- **ProcessConfiguration.json**: Main configuration
- **WorkItemTypes/*.json**: Work item type definitions
- **States.json**: State definitions
- **Rules.json**: Business rules

Edit these files to make your changes.

### Step 3: Re-import Modified Process

```bash
process-migrator.exe import -n "Custom BPC" -f "path\to\ProcessConfiguration.json" -a "https://dev.azure.com/YourOrg"
```

## Common Customization Scenarios

### Scenario 1: Industry-Specific Categories

Modify the "Process Category" field to include industry-specific categories:

**Healthcare**:
- Patient Care
- Clinical Operations
- Billing & Coding
- Compliance & Regulatory
- Quality Assurance

**Financial Services**:
- Trading Operations
- Risk Management
- Compliance
- Customer Onboarding
- Regulatory Reporting

**Manufacturing**:
- Production
- Quality Control
- Supply Chain
- Maintenance
- Safety

### Scenario 2: Compliance Fields

Add fields for compliance tracking:

```
Field: Regulatory Framework
Type: Picklist
Options: SOX, HIPAA, GDPR, ISO 9001, PCI DSS

Field: Control ID
Type: String
Description: Reference to internal control framework

Field: Audit Frequency
Type: Picklist
Options: Monthly, Quarterly, Semi-Annually, Annually
```

### Scenario 3: Process Metrics

Add fields to track process performance:

```
Field: Cycle Time (days)
Type: Integer
Description: Average time to complete the process

Field: Error Rate (%)
Type: Decimal
Description: Percentage of errors in process execution

Field: Cost per Transaction
Type: Decimal
Description: Average cost per process execution
```

### Scenario 4: Integration Fields

Add fields for system integration:

```
Field: Source System
Type: String
Description: Primary system where this process executes

Field: Integration Points
Type: String (Multi-line)
Description: Systems that integrate with this process

Field: API Endpoints
Type: String (Multi-line)
Description: API endpoints used by this process
```

## Best Practices

### Field Design

1. **Keep it Simple**: Only add fields that will actually be used
2. **Use Picklists**: For fields with limited options, use picklists instead of free text
3. **Add Help Text**: Always include descriptions to guide users
4. **Consider Required vs Optional**: Don't make too many fields required

### Work Item Types

1. **Maintain Hierarchy**: Use parent-child relationships effectively
2. **Limit Types**: Don't create too many work item types (5-7 is usually sufficient)
3. **Clear Naming**: Use clear, consistent names

### Workflow States

1. **Keep it Linear**: Avoid complex state transitions
2. **3-7 States**: Most workflows work well with 3-7 states
3. **Clear Transitions**: Make it obvious how to move between states

### Rules

1. **Test Thoroughly**: Rules can have unintended consequences
2. **Document Rules**: Keep track of what rules you've implemented
3. **Review Regularly**: Rules may need adjustment as processes evolve

## Testing Customizations

Always test customizations in a non-production project:

1. Create a test project using your customized process
2. Create sample work items
3. Test all workflow transitions
4. Verify rules work as expected
5. Get feedback from a small group before rolling out widely

## Version Control for Customizations

Keep track of your customizations:

1. Export your process regularly
2. Store exports in version control (Git)
3. Document changes in a CHANGELOG
4. Tag major versions

## Rollback Procedures

If a customization causes issues:

1. Export a backup before making changes
2. Create a new process with the backup if needed
3. You cannot delete a process being used by projects, but you can disable work item types

## Getting Help

- **Azure DevOps Documentation**: [Customize a process](https://docs.microsoft.com/en-us/azure/devops/organizations/settings/work/customize-process)
- **Process Migrator**: [GitHub Issues](https://github.com/microsoft/process-migrator/issues)
- **Community**: Azure DevOps Community forums

## Examples Repository

Check the `/examples` folder (if available) for:
- Sample customizations
- Industry-specific templates
- Integration examples

---

Remember: Start with the basic template and customize incrementally based on actual usage and feedback from your team.
