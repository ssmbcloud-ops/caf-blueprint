

## Create Blueprint
Import-AzBlueprintWithArtifact -Name caf-demo -InputPath . -ManagementGroupId nepeters-internal -Force
$bp = Get-AzBlueprint -Name caf-demo -ManagementGroupId nepeters-internal
Publish-AzBlueprint -Blueprint $bp -Version 1

## Assign Blueprint with Assignment File
New-AzBlueprintAssignment -Name caf-demo -Blueprint $bp -AssignmentFile ./assign.json -SubscriptionId bb63e160-80c7-4e6c-a4e6-e5f23787c83c

## Assign Blueprint without Assignment File
$params = @{
    Policy_CostCenter_Tag = 'test123'
    Policy_Allowed_Locations = 'test123'
    Policy_Resource_Types_DENY = 'test123'
    Policy_Allowed_StorageAccount_SKUs = 'test123'
    Policy_Allowed_VM_SKUs = 'test123'
    LogAnalytics_DataRetention = 'test123'
    LogAnalytics_Location = 'test123'
}