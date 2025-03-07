---
title: User-defined functions in Bicep
description: Describes how to define and use user-defined functions in Bicep.
ms.topic: conceptual
ms.custom: devx-track-bicep
ms.date: 08/30/2023
---

# User-defined functions in Bicep (Preview)

Within your Bicep file, you can create your own functions. These functions are available for use in your Bicep files. User-defined functions are separate from the [standard Bicep functions](./bicep-functions.md) that are automatically available within your Bicep files. Create your own functions when you have complicated expressions that are used repeatedly in your Bicep files.

[Bicep version 0.20 or newer](./install.md) is required to use this feature.

## Enable the preview feature

To enable this preview, modify your project's [bicepconfig.json](./bicep-config.md) file to include the following JSON:

```json
{
  "experimentalFeaturesEnabled": {
    "userDefinedFunctions": true
  }
}
```

## Define the function

Use the `func` statement to define user-defined functions.

```bicep
func <user-defined-function-name> (<argument-name> <data-type>, <argument-name> <data-type>, ...) <function-data-type> => <expression>
```

## Examples

The following examples show how to define and use user-defined functions:

```bicep
func buildUrl(https bool, hostname string, path string) string => '${https ? 'https' : 'http'}://${hostname}${empty(path) ? '' : '/${path}'}'

func sayHelloString(name string) string => 'Hi ${name}!'

func sayHelloObject(name string) object => {
  hello: 'Hi ${name}!'
}

func nameArray(name string) array => [
  name
]

func addNameArray(name string) array => [
  'Mary'
  'Bob'
  name
]

output azureUrl string = buildUrl(true, 'microsoft.com', 'azure')
output greetingArray array = map(['Evie', 'Casper'], name => sayHelloString(name))
output greetingObject object = sayHelloObject('John')
output nameArray array = nameArray('John')
output addNameArray array = addNameArray('John')

```

The outputs from the preceding examples are:


| Name | Type | Value |
| ---- | ---- | ----- |
| azureUrl | String | https://microsoft.com/azure |
| greetingArray | Array | ["Hi Evie!","Hi Casper!"] |
| greetingObject | Object | {"hello":"Hi John!"} |
| nameArray | Array | ["John"] |
| addNameArray | Array | ["Mary","Bob","John"] |

## Limitations

When defining a user function, there are some restrictions:

* The function can't access variables.
* The function can only use parameters that are defined in the function.
* The function can't call other user-defined functions.
* The function can't use the [reference](bicep-functions-resource.md#reference) function or any of the [list](bicep-functions-resource.md#list) functions.
* Parameters for the function can't have default values.

## Next steps

* To learn about the Bicep file structure and syntax, see [Understand the structure and syntax of Bicep files](./file.md).
* For a list of the available Bicep functions, see [Bicep functions](./bicep-functions.md).
