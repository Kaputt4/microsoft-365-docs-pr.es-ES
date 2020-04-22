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
description: Obtenga información sobre cómo revertir las claves raíz del cliente almacenadas en Azure Key Vault que se usan con la clave de cliente. Los servicios incluyen los archivos de Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y Microsoft Teams.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633647"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rotar o alternar una Clave de cliente o una clave de disponibilidad

> [!CAUTION]
> Haga solo una clave de cifrado que use con la clave de cliente cuando sus requisitos de seguridad o cumplimiento determinen que debe revertir la clave. Además, no elimine las claves que estén asociadas a directivas. Al revertir las claves, habrá contenido cifrado con las claves anteriores. Por ejemplo, los buzones activos se volverán a cifrar con frecuencia, los buzones inactivos, desconectados y deshabilitados pueden seguir cifrados con las claves anteriores. SharePoint Online realiza una copia de seguridad del contenido para restauración y recuperación, por lo que es posible que todavía haya contenido archivado con claves antiguas.

## <a name="about-rolling-the-availability-key"></a>Sobre cómo se gira la clave de disponibilidad

Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede girar (girar) las claves que posee en el almacén de claves de Azure. Microsoft 365 aplica las claves de disponibilidad según una programación definida internamente. No hay ningún contrato de nivel de servicio (SLA) dirigido a los clientes para estos lanzamientos clave. Microsoft 365 gira la clave de disponibilidad con el código de servicio de Microsoft 365 en un proceso automatizado y no manual. Los administradores de Microsoft pueden iniciar el proceso de lanzamiento. La clave se propaga mediante mecanismos automatizados sin acceso directo al almacén de claves. El acceso al almacén secreto de clave de disponibilidad no se aprovisiona para los administradores de Microsoft. La tecla de disponibilidad "Rolling" aprovecha el mismo mecanismo que se usa para generar la clave inicialmente. Para obtener más información acerca de la clave de disponibilidad, vea [comprender la clave de disponibilidad](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Las claves de disponibilidad de Skype empresarial y Exchange Online las pueden realizar de forma eficaz los clientes que creen una nueva DEP, ya que se genera una clave de disponibilidad única para cada DEP que cree. Las claves de disponibilidad para SharePoint Online, OneDrive para la empresa y los archivos de Microsoft Teams existen en el nivel de bosque y se comparten entre DEPs y clientes, lo que significa que solo se produce en una programación definida internamente por Microsoft. Para mitigar el riesgo de no poner la clave de disponibilidad cada vez que se crea una nueva DEP, SharePoint, OneDrive y Teams colocan la clave intermedia del inquilino (TIK), la clave que se ajusta mediante las claves raíz del cliente y la clave de disponibilidad, cada vez que se crea un nuevo DEP.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Solicite una nueva versión de cada clave raíz existente que desee revertir

Cuando se gira una clave, se solicita una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, use el mismo cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), con la misma sintaxis que usó para crear la clave en primer lugar. Una vez que haya terminado de revertir cualquier clave asociada con una directiva de cifrado de datos (DEP), deberá ejecutar otro cmdlet para asegurarse de que la clave de cliente comienza a usar la nueva clave. Realice este paso en cada Azure Key Vault (AKV).

Por ejemplo:

1. Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Add-AzKeyVaultKey como se muestra en el siguiente ejemplo:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   En este ejemplo, dado que existe una clave llamada **contoso-O365EX-na-VaultA1-Key001** en el almacén **contoso-O365EX-na-VaultA1** , el cmdlet crea una nueva versión de la clave. Esta operación conserva las versiones anteriores de la clave en el historial de versiones de la clave. Necesita la versión de clave anterior para descifrar los datos que sigue cifrando. Una vez que haya terminado de revertir cualquier clave asociada con una DEP, ejecute un cmdlet adicional para asegurarse de que la clave de cliente comienza a usar la nueva clave. En las secciones siguientes se describen los cmdlets con más detalle.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Actualizar la clave de cliente de Exchange Online y Skype empresarial

Cuando se revierte cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con Exchange Online y Skype empresarial, debe actualizar el DEP para que apunte a la nueva clave. Esto no gira la clave de disponibilidad.

Para indicar a la clave de cliente que use la nueva clave para cifrar buzones, ejecute el cmdlet Set-DataEncryptionPolicy de la siguiente manera:

1. Ejecute el cmdlet Set-DataEncryptionPolicy en Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   En un plazo de 72 horas, los buzones activos asociados a este DEP se cifran con la nueva clave.

2. Para comprobar el valor de la propiedad DataEncryptionPolicyID del buzón de correo, siga los pasos descritos en [determinar el DEP asignado a un buzón de correo](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). El valor de esta propiedad cambia una vez que el servicio aplica la clave actualizada.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Actualizar la clave de cliente para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams

SharePoint Online solo le permite revertir una tecla cada vez. Si desea desplegar ambas claves en un depósito de claves, espere a que se complete la primera operación. Microsoft recomienda escalonar las operaciones para evitar este problema. Cuando se revierte cualquiera de las claves de Azure Key Vault asociadas con un DEP usado con SharePoint Online y OneDrive para la empresa, debe actualizar el DEP para que apunte a la nueva clave. Esto no gira la clave de disponibilidad.

1. Ejecute el cmdlet Update-SPODataEncryptionPolicy de la siguiente manera:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Aunque este cmdlet inicia la operación de desplazamiento de claves para SharePoint Online y OneDrive para la empresa, la acción no se completa inmediatamente.

2. Para ver el progreso de la operación de desplazamiento de claves, ejecute el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicios con clave de cliente de Office 365](customer-key-overview.md)

- [Configurar Clave de cliente de Office 365](customer-key-set-up.md)

- [Administrar Clave de cliente de Office 365](customer-key-manage.md)

- [Obtener información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)
