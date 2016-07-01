---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=517143
schema: 2.0.0
---

# Unregister-PackageSource
## SYNOPSIS
Removes a registered package source.

## SYNTAX

### SourceBySearch
```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>]
```

### SourceByInputObject
```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm]
```

### NuGet:SourceByInputObject
```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate]
```

### NuGet:SourceBySearch
```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate]
```

### PowerShellGet:SourceByInputObject
```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-PackageManagementProvider <String>] [-Type <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
```

### PowerShellGet:SourceBySearch
```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-PackageManagementProvider <String>] [-Type <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
```

## DESCRIPTION
The Unregister-PackageSource cmdlet removes a registered package source.
Package sources are always managed by a package provider.

## EXAMPLES

### Example 1: Unregister a package source for the NuGet provider
```
PS C:\>Unregister-PackageSource -Source "myRep" -Location "http://contoso/nuget/MyRepository/api/v3" -Provider "nugget"
```

This command unregisters a package source named Features for the NuGet provider.
You are prompted to confirm that you want to unregister the package because the Force parameter is not specified,

### Example 2: Unregister a package source by piping a PackageSource object
```
PS C:\>$a = Get-PackageSource -Name "myRep" -Location "http://contoso/nuget/Features/api/v3"
PS C:\>Unregister-PackageSource -InputObject $a -Force
```

This command unregisters a package source named Features for the NuGet provider by saving the results of a Get-PackageSource command to a variable, and then using the variable as input to Unregister-PackageSource.
The Force parameter ensures that you are not prompted to confirm that you want to unregister the package.

## PARAMETERS

### -Credential
Specifies a user account that has rights to unregister a package source for a specified package provider.
Specify a user name, such as "User01", or "Domain\User01", or specify a PSCredential object, such as one generated by the Get-Credential cmdlet.
The simplest way to specify a PSCredential object is to save the results of a Get-Credential cmdlet as a variable.
When you add this parameter and specify a user name, you are prompted to provide a password after you run the command.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceBootstrap
Indicates that this cmdlet forces Package Management to automatically install the package provider for the specified package source.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies a package source by using the package source's object, which is shown in the results of the Get-PackageSource cmdlet.

```yaml
Type: PackageSource[]
Parameter Sets: SourceByInputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Location
Specifies the location to which a package source points.
The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.

```yaml
Type: String
Parameter Sets: SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider
Specifies the Package Management provider.

```yaml
Type: String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName
Specifies the provider name.

```yaml
Type: String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Programs, msi, msu, PowerShellGet, nuget, chocolatey

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishLocation
Specifies the publish location.

```yaml
Type: String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptPublishLocation
Specifies the script publish location.

```yaml
Type: String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptSourceLocation
Specifies the script source location.

```yaml
Type: String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Specifies the friendly name of the package source.

```yaml
Type: String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of package source.

```yaml
Type: String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases: 
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigFile
{{Fill ConfigFile Description}}

```yaml
Type: String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipValidate
{{Fill SkipValidate Description}}

```yaml
Type: SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases: 

Required: False
Position: Named
Default value: 
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[about_PackageManagement]()

[Get-PackageSource]()

[Register-PackageSource]()

[Set-PackageSource]()
