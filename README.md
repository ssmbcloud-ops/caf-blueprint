## Create Blueprint
Import-AzBlueprintWithArtifact -Name caf-demo -InputPath . -ManagementGroupId nepeters-internal -Force
$bp = Get-AzBlueprint -Name caf-demo -ManagementGroupId nepeters-internal
Publish-AzBlueprint -Blueprint $bp -Version 1

## Assign Blueprint
New-AzBlueprintAssignment -Name caf-demo -Blueprint $bp -AssignmentFile ./assign.json -SubscriptionId bb63e160-80c7-4e6c-a4e6-e5f23787c83c



