---
page_type: sample
languages:
- json
products:
- azure-policy
description: "An Azure policy definition that enforces a naming convention on Azure virtual machines."
urlFragment: "update-this-to-unique-url-stub"
---

# Enforce Azure virtual machine names based on a naming convention

This Azure policy governs the naming convention for virtual machines within the specified scope. The policy was developed to support a 3 tier application in 2 locations that all reside in the same resource group. Ideally, this policy would be assigned to a resource group when the resource group is created.

## Deployment Options

### Azure Portal

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/)
[![Deploy to Azure Gov](https://aka.ms/deploytoazuregovbutton)](https://portal.azure.us/?#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/)

### Azure PowerShell

````powershell

$definition = New-AzPolicyDefinition `
    -Name 'Naming_VirtualMachine_Deny' `
    -DisplayName 'Naming_VirtualMachine_Deny' `
    -Description 'This policy governs the naming convention for virtual machines.' `
    -Policy '' `
    -Parameter '' `
    -Mode 'All' `
    -Metadata '{"category":"Governance"}'

New-AzPolicyAssignment `
    -Name '<Assignment Name>' `
    -Scope '<Scope>' `
    -Application '<Application>' `
    -Environment '<Environment Abbreviation>' `
    -DataCenterCountry '<Data Center Country>' `
    -DataCenterLocation '<Primary Location Abbreviation>' `
    -PolicyDefinition $definition

````

### Azure CLI

````cli

az policy definition create \
    --name 'Naming_VirtualMachine_Deny' \
    --display-name 'Naming_VirtualMachine_Deny' \
    --description 'This policy governs the naming convention for virtual machines.' \
    --rules '' \
    --params '' \
    --mode All

az policy assignment create \
    --name <Assignment Name> \
    --scope <scope> \
    --policy "Naming_VirtualMachine_Deny"

````
