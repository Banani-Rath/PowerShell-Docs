---
external help file: PSITPro5_Core.xml
online version: http://go.microsoft.com/fwlink/p/?linkid=289609
schema: 2.0.0
---

# Remove-PSSnapin
## SYNOPSIS
Removes Windows PowerShell snap-ins from the current session.

## SYNTAX

```
Remove-PSSnapin [-Name] <String[]> [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The Remove-PSSnapin cmdlet removes a Windows PowerShell snap-in from the current session.
You can use it to remove snap-ins that you have added to Windows PowerShell You cannot use this cmdlet to remove the snap-ins that are installed with Windows PowerShell.

After you remove a snap-in from the current session, the snap-in is still loaded, but the cmdlets and providers in the snap-in are no longer available in the session.

## EXAMPLES

### Example 1: Remove a snap-in
```
PS C:\>remove-pssnapin -Name Microsoft.Exchange
```

This command removes the Microsoft.Exchange snap-in from the current session.
When the command is complete, the cmdlets and providers that the snap-in supported are not available in the session.

### Example 2: Remove snap-ins by using names with the pipeline
```
PS C:\>Get-PSSnapIn smp* | Remove-PSSnapIn
```

This command removes the Windows PowerShell snap-ins that have names that start with smp from the current session.

The command uses the Get-PSSnapin cmdlet to get objects that represent the snap-ins.
The pipeline operator (|) sends the results to the Remove-PSSnapin cmdlet, which removes them from the session.
The providers and cmdlets that this snap-in supports are no longer available in the session.

When you pipe objects to Remove-PSSnapin, the names of the objects are associated with the Name parameter, which accepts objects from the pipeline that have a Name property.

### Example 3: Remove snap-ins by using names
```
PS C:\>Remove-PSSnapin -Name *event*
```

This command removes all Windows PowerShell snap-ins that have names that include event.

## PARAMETERS

### -Name
Specifies the names of Windows PowerShell snap-ins to remove from the current session.
Wildcard characters (*) are permitted.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object that represents the snap-in.
By default, this cmdlet does not generate any output.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### System.Management.Automation.PSSnapInInfo
You can pipe a snap-in object to this cmdlet.

## OUTPUTS

### None, System.Management.Automation.PSSnapInInfo
This cmdlet generates a System.Management.Automation.PSSnapInInfo object that represents the snap-in, if you specify the PassThru parameter.
By default, Remove-PSSnapin does not generate any output.

## NOTES
Remove-PSSnapin does not check the version of Windows PowerShell before removing a snap-in from the session.
If a snap-in cannot be removed, a warning appears and the command fails.

Remove-PSSnapin affects only the current session.
If you have added an Add-PSSnapin command to your Windows PowerShell profile, you should delete the command to remove the snap-in from future sessions.
For instructions, type Get-Help about_Profiles.

## RELATED LINKS

[Add-PSSnapin](4125e0dc-d3c1-494f-87e1-4918df7d0f84)

[Get-PSSnapin](f2561ac4-9ef9-4b8b-95ca-8bfc5f51784d)

[about_Profiles](c555334d-3000-4fc4-a076-1486c3ed27ec)
