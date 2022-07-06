---
title: Eliminación de un tipo de información confidencial personalizada mediante PowerShell
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
description: Obtenga información sobre cómo quitar un tipo de información confidencial personalizado mediante PowerShell
ms.openlocfilehash: ba29c2f20133b94d87c14f527d454980c41373c9
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66621697"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Eliminación de un tipo de información confidencial personalizada mediante PowerShell

En Security & Compliance PowerShell, hay dos métodos para quitar tipos de información confidencial personalizados:

- **Quitar tipos de información confidencial personalizados individuales**: use el método documentado en [Modificar un tipo de información confidencial personalizada mediante PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell). Exporte el paquete de reglas personalizado que contiene el tipo de información confidencial personalizada, quite el tipo de información confidencial del archivo XML e importe de nuevo el archivo XML actualizado en el paquete de reglas personalizado existente.

- **Quitar un paquete de reglas personalizado y todos los tipos de información confidencial que contiene**: este método se documenta en esta sección.

> [!NOTE]
> Antes de quitar un tipo personalizado de información confidencial, asegúrese de que ninguna de las directivas DLP o reglas de flujo del correo de Exchange (también conocidas como reglas de transporte) hagan referencia al tipo de información confidencial.

1. [PowerShell de cumplimiento de & de seguridad](/powershell/exchange/exchange-online-powershell)

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

- [Información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

- [Funciones de tipo de información confidencial](sit-functions.md)
