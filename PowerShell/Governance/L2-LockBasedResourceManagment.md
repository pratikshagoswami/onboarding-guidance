
# TODO: Randy to add header info by EOD 9/29

######################################## ABOVE #####################

# Lock resources with Azure Resource Manager

https://azure.microsoft.com/en-us/documentation/articles/resource-group-lock-resources/ 


As an administrator, you may need to lock a subscription, resource group, or resource to prevent other users in your organization from accidentally deleting or modifying critical resources.
You can set the lock level to CanNotDelete or ReadOnly.

You can set locks at resource, resource group, or subscription . 
Resource inherits the lock from the parent. For example, you could lock the resource group to apply a lock to all its resources.

# Creating a lock with Azure PowerShell


# Putting a Lock on a subscription Level 

New-AzureRmResourceLock -LockLevel CanNotDelete -LockName SubcriptionLevelLock -LockNotes "Subcription Level Lock" -Scope /subscriptions/6b6a59a6-e367-4913-bea7-34b6862095bf/ -Verbose -Debug

# Putting a Lock on a Resource Group 

New-AzureRmResourceLock -LockLevel CanNotDelete -LockName LockResourceGroup -LockNotes "Cannot Delete Resource Group" -ResourceGroupName monitorstrg -verbose -debug 

# Putting a Lock on Resource Level

New-AzureRmResourceLock -LockLevel CanNotDelete -LockName LockonStorage -LockNotes "Cannot Delete storage Resource" -ResourceName mystorageaccount -ResourceType Microsoft.Storage/storageAccounts -ResourceGroupName exampleresourcegroup