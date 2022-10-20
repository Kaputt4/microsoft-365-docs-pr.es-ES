---
title: Rotar o alternar una Clave de cliente o una clave de disponibilidad
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- purview-compliance
- tier1
description: Obtenga información sobre cómo revertir las claves raíz del cliente almacenadas en Azure कि भल्ट que se usan con la clave de cliente. Los servicios incluyen archivos Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams.
ms.openlocfilehash: 22071e7e7c7168da2117cd9e7d0abcb07f9e211e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68647791"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rotar o alternar una Clave de cliente o una clave de disponibilidad

> [!CAUTION]
> Implemente solo una clave de cifrado que use con clave de cliente cuando los requisitos de seguridad o cumplimiento determinen que debe revertir la clave. Además, no elimine las claves que estén o estén asociadas a directivas. Al deshacer las claves, habrá contenido cifrado con las claves anteriores. Por ejemplo, aunque los buzones activos se volverán a cifrar con frecuencia, los buzones inactivos, desconectados y deshabilitados todavía se pueden cifrar con las claves anteriores. SharePoint Online realiza una copia de seguridad del contenido con fines de restauración y recuperación, por lo que es posible que todavía haya contenido archivado mediante claves anteriores.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="about-rolling-the-availability-key"></a>Acerca de cómo revertir la clave de disponibilidad

Microsoft no expone el control directo de la clave de disponibilidad a los clientes. Por ejemplo, solo puede revertir (girar) las claves que posee en Azure कि भल्ट. Microsoft 365 implementa las claves de disponibilidad en una programación definida internamente. No hay ningún acuerdo de nivel de servicio (SLA) orientado al cliente para estos lanzamientos de claves. Microsoft 365 gira la clave de disponibilidad mediante el código de servicio de Microsoft 365 en un proceso automatizado no manual. Los administradores de Microsoft pueden iniciar el proceso de lanzamiento. La clave se enrolla mediante mecanismos automatizados sin acceso directo al almacén de claves. El acceso al almacén secreto de clave de disponibilidad no se aprovisiona a los administradores de Microsoft. La rotación de claves de disponibilidad aprovecha el mismo mecanismo usado para generar inicialmente la clave. Para obtener más información sobre la clave de disponibilidad, consulte [Descripción de la clave de disponibilidad](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Exchange Online y Skype Empresarial claves de disponibilidad pueden ser efectivamente enrolladas por los clientes que crean un nuevo DEP, ya que se genera una clave de disponibilidad única para cada DEP que cree. Las claves de disponibilidad para archivos de SharePoint Online, OneDrive para la Empresa y Teams existen en el nivel de bosque y se comparten entre dep y clientes, lo que significa que la reversión solo se produce en una programación definida internamente por Microsoft. Para mitigar el riesgo de no revertir la clave de disponibilidad cada vez que se crea un nuevo DEP, SharePoint, OneDrive y Teams implementan la clave intermedia del inquilino (TIK), la clave encapsulada por las claves raíz del cliente y la clave de disponibilidad, cada vez que se crea un nuevo DEP.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Solicitar una nueva versión de cada clave raíz existente que quiera revertir

Al lanzar una clave, se solicita una nueva versión de una clave existente. Para solicitar una nueva versión de una clave existente, use el mismo cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), con la misma sintaxis que usó para crear la clave en primer lugar. Una vez que haya terminado de revertir cualquier clave asociada a una directiva de cifrado de datos (DEP), ejecute otro cmdlet para asegurarse de que clave de cliente comienza a usar la nueva clave. Realice este paso en cada कि भल्ट de Azure (AKV).

Por ejemplo:

1. Inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, consulte [Inicio de sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Add-AzKeyVaultKey como se muestra en el ejemplo siguiente:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   En este ejemplo, dado que existe una clave denominada **Contoso-CK-EX-NA-VaultA1-Key001** en el almacén **Contoso-CK-EX-NA-VaultA1** , el cmdlet crea una nueva versión de la clave. Esta operación conserva las versiones de clave anteriores en el historial de versiones de la clave. Necesita la versión de clave anterior para descifrar los datos que sigue cifrando. Una vez completada la puesta en marcha de cualquier clave asociada a un DEP, ejecute un cmdlet adicional para asegurarse de que clave de cliente comienza a usar la nueva clave. En las secciones siguientes se describen los cmdlets con más detalle.
  
## <a name="update-the-keys-for-multi-workload-deps"></a>Actualización de las claves para los DEP de varias cargas de trabajo

Al implementar cualquiera de las claves de Azure कि भल्ट asociadas a un DEP usado con varias cargas de trabajo, debe actualizar el DEP para que apunte a la nueva clave. Este proceso no gira la clave de disponibilidad.

Para indicar a Customer Key que use la nueva clave para cifrar varias cargas de trabajo, complete estos pasos:

1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global o administrador de cumplimiento en su organización, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ejecute el cmdlet Set-M365DataAtRestEncryptionPolicy.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

Donde *PolicyName* es el nombre o identificador único de la directiva. Por ejemplo, Contoso_Global.

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>Actualización de las claves de los DEP de Exchange Online

Al implementar cualquiera de las claves de Azure कि भल्ट asociadas a un DEP usado con Exchange Online y Skype Empresarial, debe actualizar el DEP para que apunte a la nueva clave. Esto no gira la clave de disponibilidad.

Para indicar a Customer Key que use la nueva clave para cifrar los buzones de correo, ejecute el cmdlet Set-DataEncryptionPolicy como se indica a continuación:

1. Ejecute el cmdlet Set-DataEncryptionPolicy en Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. Para comprobar el valor de la propiedad DataEncryptionPolicyID del buzón, siga los pasos descritos en [Determinar el DEP asignado a un buzón](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). El valor de esta propiedad cambia una vez que el servicio aplica la clave actualizada.
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Actualización de las claves para archivos de SharePoint Online, OneDrive para la Empresa y Teams

SharePoint Online solo le permite lanzar una clave a la vez. Si desea revertir ambas claves en un almacén de claves, espere a que se complete la primera operación. Microsoft recomienda escalonar las operaciones para evitar este problema. Al implementar cualquiera de las claves de Azure कि भल्ट asociadas a un DEP usado con SharePoint Online y OneDrive para la Empresa, debe actualizar el DEP para que apunte a la nueva clave. Esto no gira la clave de disponibilidad.

1. Ejecute el cmdlet Update-SPODataEncryptionPolicy de la siguiente manera:
  
   ```powershell
   Update-SPODataEncryptionPolicy  <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Aunque este cmdlet inicia la operación de sustitución de claves para SharePoint Online y OneDrive para la Empresa, la acción no se completa inmediatamente.

2. Para ver el progreso de la operación de sustitución de claves, ejecute el cmdlet Get-SPODataEncryptionPolicy de la siguiente manera:

   ```powershell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Configuración de la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)
