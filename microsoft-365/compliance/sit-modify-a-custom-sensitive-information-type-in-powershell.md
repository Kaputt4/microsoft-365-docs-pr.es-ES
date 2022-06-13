---
title: Modificación de un tipo de información confidencial personalizada mediante PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo modificar una información confidencial personalizada mediante PowerShell.
ms.openlocfilehash: deb50679702cec69187392337511b4dde2d1ceb3
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014396"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Modificación de un tipo de información confidencial personalizada mediante PowerShell

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En PowerShell de cumplimiento de seguridad &, la modificación de un tipo de información confidencial personalizada requiere lo siguiente:

1. Exporte el paquete de reglas existente que contiene el tipo de información confidencial a un archivo XML (o, si lo tiene, use el archivo XML existente).

2. Modifique el tipo personalizado de información confidencial en el archivo XML exportado.

3. Importe el archivo XML actualizado en el paquete de reglas existentes.

Para conectarse a PowerShell de cumplimiento de & de seguridad, consulte [PowerShell de cumplimiento de & de seguridad](/powershell/exchange/exchange-online-powershell).

## <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Paso 1: exportar el paquete de reglas existentes a un archivo XML

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

3. Use la siguiente sintaxis para exportar el paquete de reglas personalizado a un archivo XML:

   ```powershell
   [System.IO.File]::WriteAllBytes('XMLFileAndPath', $rulepak.SerializedClassificationRuleCollection)
   ```

   En este ejemplo se exporta el paquete de reglas al archivo denominado ExportedRulePackage.xml en la carpeta C:\Mis documentos.

   ```powershell
   [System.IO.File]::WriteAllBytes('C:\My Documents\ExportedRulePackage.xml', $rulepak.SerializedClassificationRuleCollection)
   ```

## <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Paso 2: modificar el tipo de información confidencial en el archivo XML exportado

Anteriormente en este tema se describen los tipos de información confidencial en el archivo XML y otros elementos del archivo.

## <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Paso 3: importar el archivo XML actualizado en el paquete de reglas existentes

Para importar el archivo XML actualizado en el paquete de reglas existentes, use el cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([System.IO.File]::ReadAllBytes('C:\My Documents\External Sensitive Info Type Rule Collection.xml'))
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).

## <a name="more-information"></a>Más información

- [Información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Funciones de tipo de información confidencial](sit-functions.md)
