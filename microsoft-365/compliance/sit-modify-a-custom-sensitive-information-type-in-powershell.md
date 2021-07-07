---
title: Modificar un tipo de información confidencial personalizada con PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo modificar una información confidencial personalizada con PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322958"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Modificar un tipo de información confidencial personalizada con PowerShell

Crear un tipo personalizado de información confidencial en PowerShell del Centro de cumplimiento requiere lo siguiente:

1. Exporte el paquete de reglas existente que contiene el tipo de información confidencial a un archivo XML (o, si lo tiene, use el archivo XML existente).

2. Modifique el tipo personalizado de información confidencial en el archivo XML exportado.

3. Importe el archivo XML actualizado en el paquete de reglas existentes.

Para conectarse a PowerShell del Centro de cumplimiento, vea [Conectarse a PowerShell del Centro de cumplimiento](/powershell/exchange/exchange-online-powershell).

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Paso 1: exportar el paquete de reglas existentes a un archivo XML

> [!NOTE]
> Si tiene una copia del archivo XML (si, por ejemplo, lo acaba de crear y de importar), puede saltar al paso siguiente para modificar el archivo XML.

1. Si aún no lo sabe, ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) para buscar el nombre del paquete de reglas personalizado:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > El paquete de reglas integradas que contiene los tipos de información confidencial integrados se denomina paquete de reglas de Microsoft. El paquete de reglas que contiene los tipos de información confidencial personalizados que creó en la interfaz de usuario del Centro de cumplimiento se llama Microsoft.SCCManaged.CustomRulePack.

2. Use el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) para almacenar el paquete de reglas personalizadas en una variable:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Por ejemplo, si el paquete de reglas se llama "Paquete de reglas personalizado de Id. de empleado", ejecute el cmdlet siguiente:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Use el cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) para exportar el paquete de reglas personalizado a un archivo XML:

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   En este ejemplo se exporta el paquete de reglas para el archivo denominado ExportedRulePackage.xml en la carpeta C:\Mis documentos.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Paso 2: modificar el tipo de información confidencial en el archivo XML exportado

Anteriormente en este tema se describen los tipos de información confidencial en el archivo XML y otros elementos del archivo.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Paso 3: importar el archivo XML actualizado en el paquete de reglas existentes

Para importar el archivo XML actualizado en el paquete de reglas existentes, use el cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).


## <a name="more-information"></a>Más información

- [Obtenga más información acerca de la prevención de pérdida de datos](dlp-learn-about-dlp.md)

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

- [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md)
