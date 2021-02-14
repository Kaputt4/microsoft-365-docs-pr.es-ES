---
title: Rotar o alternar una Clave de cliente o una clave de disponibilidad
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo deshacer las claves raíz del cliente almacenadas en Azure Key Vault que se usan con la clave de cliente. Los servicios incluyen archivos de Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633647"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rotar o alternar una Clave de cliente o una clave de disponibilidad

> [!CAUTION]
> Roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key. Además, no elimine ninguna clave que esté o esté asociada a directivas. Al deshacer las claves, habrá contenido cifrado con las claves anteriores. Por ejemplo, aunque los buzones activos se volverán a cifrar con frecuencia, inactivos, desconectados y deshabilitados, los buzones pueden seguir cifrados con las claves anteriores. SharePoint Online realiza una copia de seguridad del contenido con fines de restauración y recuperación, por lo que es posible que aún haya contenido archivado con claves anteriores.

## <a name="about-rolling-the-availability-key"></a>Acerca de cómo implementar la clave de disponibilidad

Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede girar las claves que posee en Azure Key Vault. Microsoft 365 rolls the availability keys on an internally-defined schedule. No hay ningún contrato de nivel de servicio (SLA) orientado al cliente para estos lanzamientos de claves. Microsoft 365 gira la clave de disponibilidad mediante el código de servicio de Microsoft 365 en un proceso automatizado y no manual. Los administradores de Microsoft pueden iniciar el proceso de implementación. La clave se usa mediante mecanismos automatizados sin acceso directo al almacén de claves. El acceso al almacén secreto de clave de disponibilidad no está aprovisionado para los administradores de Microsoft. La implementación de la clave de disponibilidad aprovecha el mismo mecanismo usado inicialmente para generar la clave. Para obtener más información acerca de la clave de disponibilidad, vea [Comprender la clave de disponibilidad.](customer-key-availability-key-understand.md)

> [!IMPORTANT]
> Las claves de disponibilidad de Exchange Online y Skype Empresarial las pueden implementar eficazmente los clientes que crean un nuevo DEP, ya que se genera una clave de disponibilidad única para cada DEP que cree. Las claves de disponibilidad para los archivos de SharePoint Online, OneDrive para la Empresa y Teams existen en el nivel de bosque y se comparten entre los dep y los clientes, lo que significa que la implementación solo se produce en una programación definida internamente por Microsoft. Para mitigar el riesgo de no implementar la clave de disponibilidad cada vez que se crea un nuevo DEP, SharePoint, OneDrive y Teams lanzan la clave intermedia de inquilino (TIK), la clave encapsulada por las claves raíz del cliente y la clave de disponibilidad, cada vez que se crea un nuevo DEP.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Solicitar una nueva versión de cada clave raíz existente que quieras roll

Cuando se lanza una clave, se solicita una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, usa el mismo cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), con la misma sintaxis que usó para crear la clave en primer lugar. Cuando haya terminado de implementar cualquier clave asociada con una directiva de cifrado de datos (DEP), ejecute otro cmdlet para asegurarse de que la clave de cliente empiece a usar la nueva clave. Realice este paso en cada Azure Key Vault (AKV).

Por ejemplo:

1. Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, [vea Iniciar sesión con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Ejecute el cmdlet Add-AzKeyVaultKey como se muestra en el siguiente ejemplo:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   En este ejemplo, dado que existe una clave llamada **Contoso-O365EX-NA-VaultA1-Key001** en el almacén **Contoso-O365EX-NA-VaultA1,** el cmdlet crea una nueva versión de la clave. Esta operación conserva las versiones de clave anteriores en el historial de versiones de la clave. Necesita la versión de clave anterior para descifrar los datos que aún cifra. Una vez que haya terminado de implementar cualquier clave asociada con un DEP, ejecute un cmdlet adicional para asegurarse de que la clave de cliente empiece a usar la nueva clave. En las secciones siguientes se describen los cmdlets con más detalle.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Actualizar la clave de cliente para Exchange Online y Skype Empresarial

Al implementar cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con Exchange Online y Skype Empresarial, debe actualizar el DEP para que apunte a la nueva clave. Esto no gira la clave de disponibilidad.

Para indicar a la clave de cliente que use la nueva clave para cifrar buzones, ejecute el cmdlet Set-DataEncryptionPolicy de la siguiente manera:

1. Ejecute el cmdlet Set-DataEncryptionPolicy en Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   En un plazo de 72 horas, los buzones activos asociados con este DEP se cifran con la nueva clave.

2. Para comprobar el valor de la propiedad DataEncryptionPolicyID para el buzón, siga los pasos descritos en [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). El valor de esta propiedad cambia una vez que el servicio aplica la clave actualizada.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Actualizar la clave de cliente para los archivos de SharePoint Online, OneDrive para la Empresa y Teams

SharePoint Online solo le permite deshacer una clave a la vez. Si desea deshacer ambas claves en un almacén de claves, espere a que se complete la primera operación. Microsoft recomienda escalonar las operaciones para evitar este problema. Al implementar cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con SharePoint Online y OneDrive para la Empresa, debe actualizar el DEP para que apunte a la nueva clave. Esto no gira la clave de disponibilidad.

1. Ejecute el cmdlet Update-SPODataEncryptionPolicy de la siguiente manera:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Aunque este cmdlet inicia la operación de lanzamiento de claves para SharePoint Online y OneDrive para la Empresa, la acción no se completa inmediatamente.

2. Para ver el progreso de la operación de succión de claves, ejecute el cmdlet Get-SPODataEncryptionPolicy siguiente:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente para Office 365](customer-key-overview.md)

- [Configurar Clave de cliente de Office 365](customer-key-set-up.md)

- [Administrar Clave de cliente de Office 365](customer-key-manage.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)
