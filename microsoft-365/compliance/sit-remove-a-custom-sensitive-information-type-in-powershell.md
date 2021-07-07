---
title: Quitar un tipo de información confidencial personalizada con PowerShell
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
description: Obtenga información sobre cómo quitar un tipo de información confidencial personalizada con PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322955"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Quitar un tipo de información confidencial personalizada con PowerShell



En PowerShell del Centro de cumplimiento, hay dos métodos para quitar los tipos personalizados de información confidencial:

- **Quitar tipos de información confidencial** personalizados individuales: use el método documentado en Modificar un tipo de información confidencial personalizado con [PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell). Exporte el paquete de reglas personalizado que contiene el tipo de información confidencial personalizada, quite el tipo de información confidencial del archivo XML e importe el archivo XML actualizado de nuevo al paquete de reglas personalizado existente.

- **Quitar un paquete de reglas personalizado y todos los tipos de información confidencial que contiene**: este método se documenta en esta sección.

> [!NOTE]
> Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.

1. [Conectar con el Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/exchange-online-powershell)

2. Para quitar un paquete de reglas personalizado, use el cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Puede usar el valor de nombre (en cualquier idioma) o el valor (GUID) `RulePack id` para identificar el paquete de reglas.

   En este ejemplo se quita el paquete de reglas denominado "Paquete de reglas personalizado de Id. de empleado".

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Para obtener información detallada sobre la sintaxis y los parámetros, vea [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).

3. Para comprobar que ha quitado correctamente un nuevo tipo personalizado de información confidencial, siga uno de los pasos siguientes:

   - Ejecute el cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) y compruebe que ya no se muestra el paquete de reglas en la lista:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Ejecute el cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para comprobar que ya no aparecen los tipos de información confidencial en el paquete de reglas que ha quitado:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Para los tipos personalizados de información confidencial, el valor de propiedad de Publisher no será Microsoft Corporation, sino otro.

   - Reemplace \<Name\> con el valor de Nombre del tipo de información confidencial (por ejemplo, Id. de empleado) y ejecute el cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para comprobar que el tipo de información confidencial ya no aparece:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Más información

- [Obtenga más información acerca de la prevención de pérdida de datos](dlp-learn-about-dlp.md)

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

- [Qué buscan las funciones de DLP](what-the-dlp-functions-look-for.md)
