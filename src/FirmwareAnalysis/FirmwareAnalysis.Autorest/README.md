<!-- region Generated -->
# Az.FirmwareAnalysis
This directory contains the PowerShell module for the FirmwareAnalysis service.

---
## Info
- Modifiable: yes
- Generated: all
- Committed: yes
- Packaged: yes

---
## Detail
This module was primarily generated via [AutoRest](https://github.com/Azure/autorest) using the [PowerShell](https://github.com/Azure/autorest.powershell) extension.

## Module Requirements
- [Az.Accounts module](https://www.powershellgallery.com/packages/Az.Accounts/), version 2.7.5 or greater

## Authentication
AutoRest does not generate authentication code for the module. Authentication is handled via Az.Accounts by altering the HTTP payload before it is sent.

## Development
For information on how to develop for `Az.FirmwareAnalysis`, see [how-to.md](how-to.md).
<!-- endregion -->

### AutoRest Configuration

> see https://aka.ms/autorest

```yaml
# pin the swagger version by using the commit id instead of branch name
commit: 09f3dd2d269324277e8909230e1dc4c1f274cb3a
require:
# readme.azure.noprofile.md is the common configuration file
  - $(this-folder)/../../readme.azure.noprofile.md
  #- $(repo)/specification/fist/resource-manager/readme.md

# - /swagger/fist/resource-manager/readme.md
# If the swagger has not been put in the repo, you may uncomment the following line and refer to it locally
# - (this-folder)/relative-path-to-your-local-readme.md

input-file:
  - $(repo)/specification/fist/resource-manager/Microsoft.IoTFirmwareDefense/preview/2025-04-01-preview/iotfirmwaredefense.json

try-require: 
  - /swagger/fist/resource-manager/readme.powershell.md

# For new RP, the version is 0.1.0
module-version: 0.1.0
# Normally, title is the service name
title: FirmwareAnalysis
subject-prefix: $(service-name)

# The next three configurations are exclusive to v3, and in v4, they are activated by default. If you are still using v3, please uncomment them.
# identity-correction-for-post: true
# resourcegroup-append: true
# nested-object-to-string: true

directive:
  # Following are common directives which are normally required in all the RPs
  # 1. Remove the unexpanded parameter set
  # 2. For New-* cmdlets, ViaIdentity is not required
  # Following two directives are v4 specific
  - where:
      variant: ^(Create|Update)(?!.*?Expanded|JsonFilePath|JsonString)
    remove: true
  - where:
      variant: ^CreateViaIdentity.*$
    remove: true
  # Follow directive is v3 specific. If you are using v3, uncomment following directive and comments out two directives above
  #- where:
  #    variant: ^Create$|^CreateViaIdentity$|^CreateViaIdentityExpanded$|^Update$|^UpdateViaIdentity$
  #  remove: true

  # Remove the set-* cmdlet
  - where:
      verb: Set
    remove: true

  - where:
      verb: New
      subject: FirmwareDownloadUrl
    remove: true

  - where:
      verb: Get
      subject: Summary
      variant: List
    remove: true

  - where:
      verb: New
      subject: FirmwareFilesystemDownloadUrl
    remove: true

  - where:
      parameter-name: Id
      verb: New
      subject: Firmware
    set:
      default:
        name: Id
        description: Gets the Id from the current context.
        script: 'New-Guid'
```
