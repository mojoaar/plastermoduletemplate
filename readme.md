<p align="center">
<a href="https://github.com/mojoaar/plastermoduletemplate"><img src="https://img.shields.io/github/last-commit/mojoaar/plastermoduletemplate"></a>
<a href="https://github.com/mojoaar/plastermoduletemplate"><img src="https://img.shields.io/github/contributors/mojoaar/plastermoduletemplate"></a>
</p>
<p align="center">
<a href="https://twitter.com/mojoaar"><img src="https://img.shields.io/twitter/follow/mojoaar?style=social"></a>
</p>

# PlasterModuleTemplate

A Plaster template for automating the scaffolding of a new PowerShell module.

Plaster GitHub repository: https://github.com/PowerShellOrg/Plaster

## Example: Create new manifest

`$manifestProperties = @{
    Path         = 'C:\tmp\PlasterManifest\PlasterManifest.xml'
    TemplateName = 'ScriptModuleTemplate'
    TemplateType = 'Project'
    Title        = 'New PowerShell Module'
    Author       = 'Morten Johansen'
    Description  = 'Scaffolds the files required for a PowerShell script module'
    Tags         = 'PowerShell, Module, ModuleManifest'
}

$Folder = Split-Path -Path $manifestProperties.Path -Parent
if (-not(Test-Path -Path $Folder -PathType Container)) {
    New-Item -Path $Folder -ItemType Directory | Out-Null
}

New-PlasterManifest @manifestProperties`

## Example: Use the new manifest

`Invoke-Plaster -TemplatePath C:\tmp\PlasterManifest\ -DestinationPath C:\tmp\AwesomeModule -Verbose`