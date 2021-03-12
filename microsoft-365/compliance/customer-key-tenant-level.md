---
title: Clave de cliente para Microsoft 365 en el nivel de espacio empresarial (versión preliminar pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Obtenga información sobre cómo configurar la clave de cliente para todos los datos de su inquilino de Microsoft 365.
ms.openlocfilehash: 7ffa9a8148a8ae699711b62da48cd2c856d48cac
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727483"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Introducción a la clave de cliente de Microsoft 365 en el nivel de inquilino (versión preliminar pública)

Con las claves que proporcione, puede crear una directiva de cifrado de datos (DEP) y asignarla al inquilino. El DEP cifra los datos en todo el espacio empresarial para estas cargas de trabajo:

- Mensajes de chat de Teams (chats 1:1, chats de grupo, chats de reunión y conversaciones de canal)
- Mensajes multimedia de Teams (imágenes, fragmentos de código, mensajes de vídeo, mensajes de audio, imágenes wiki)
- Grabaciones de llamadas y reuniones de Teams almacenadas en el almacenamiento de Teams
- Notificaciones de chat de Teams
- Sugerencias de chat de Teams por Cortana
- Mensajes de estado de Teams
- Información de usuario y señal para Exchange Online
- Buzones de Exchange Online que no están cifrados ya en el nivel de aplicación

Para Microsoft Teams, la clave de cliente en el nivel de inquilino cifra los nuevos datos desde el momento en que se asigna el DEP al inquilino. La vista previa pública no admite el cifrado de datos anteriores. Para Exchange Online, la clave de cliente cifra todos los datos nuevos y existentes.

Puede crear varios DEP por inquilino, pero solo puede asignar un DEP en cualquier momento. Al asignar el DEP, el cifrado comienza automáticamente, pero puede tardar algún tiempo en completarse según el tamaño del espacio empresarial.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Las directivas de nivel de inquilino agregan un control más amplio a la clave de cliente para Microsoft 365

Si ya tiene la clave de cliente configurada para Exchange Online y Sharepoint Online, aquí se muestra cómo encaja la nueva versión preliminar pública de nivel de inquilino.

La directiva de cifrado de nivel de inquilino que crea cifra todos los datos de las cargas de trabajo de Microsoft Teams y Exchange Online en Microsoft 365. Sin embargo, para Exchange Online, si ya ha asignado DEP de clave de cliente a buzones individuales, la directiva de nivel de inquilino no invalidará esos DEP. La directiva de nivel de inquilino solo cifrará los buzones a los que aún no se haya asignado un DEP de clave de cliente de nivel de buzón.

Por ejemplo, los archivos de Microsoft Teams y algunas grabaciones de llamadas y reuniones de Teams que se guardan en OneDrive para la Empresa y SharePoint están cifrados por un DEP de SharePoint Online. Un solo DEP de SharePoint Online cifra el contenido dentro de una única ubicación geográfica.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurar clave de cliente en el nivel de inquilino (versión preliminar pública)

Estos pasos son similares pero no idénticos a los pasos para configurar la clave de cliente en el nivel de aplicación. Solo debe usar esta vista previa pública con datos de prueba en inquilinos de prueba. No use esta versión con datos de producción o en el entorno de producción. Si ya tiene una implementación de producción de clave de cliente, siga estos pasos para configurar la clave de cliente en el nivel de inquilino en un entorno de prueba.

Para completar la mayoría de estas tareas, conéctese de forma remota a Azure PowerShell. Para obtener los mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.

Antes de empezar, asegúrese de lo siguiente:

- Deberá usar una cuenta profesional o educativa que tenga el rol de administrador de cumplimiento para configurar la clave de cliente en el nivel de inquilino.
- Asegúrese de que tiene las licencias adecuadas para su organización. Use una suscripción de Azure de pago facturada con un Contrato Enterprise o un proveedor de servicios en la nube. Las suscripciones de Azure compradas con planes de pago o con una tarjeta de crédito no son compatibles con la clave de cliente. A partir del 1 de abril de 2020, la clave de cliente en Office 365 se ofrece en Office 365 E5, M365 E5, M365 E5 Compliance y M365 E5 Information Protection & Governance SKU. La SKU de cumplimiento avanzado de Office 365 ya no está disponible para adquirir nuevas licencias. Las licencias de cumplimiento avanzado de Office 365 existentes seguirán siendo compatibles. Aunque el servicio se puede habilitar con un mínimo de una licencia en el inquilino que tenga la licencia adecuada, debe asegurarse de que todos los usuarios que se benefician del servicio tengan las licencias adecuadas.

### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure

Clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda que los miembros independientes de la organización configuren una clave en cada suscripción. Solo use estas suscripciones de Azure para administrar claves de cifrado para Microsoft 365. Esto protege a la organización en caso de que uno de los operadores elimine accidentalmente, intencionada o malintencionadamente las claves de las que son responsables.

No hay ningún límite práctico en el número de suscripciones de Azure que puede crear para su organización. Seguir este procedimiento recomendado ayuda a minimizar el impacto del error humano al mismo tiempo que ayuda a administrar los recursos usados por la clave de cliente.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar suscripciones de Azure para usar un período de retención obligatorio

La pérdida temporal o permanente de claves de cifrado raíz puede ser perjudicial o incluso catastrófica para la operación del servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección sólida. Todos los recursos de Azure que se usan con clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Las suscripciones de Azure se pueden etiquetar o registrar de forma que se evite la cancelación inmediata e irrevocable. Esto se conoce como registro para un período de retención obligatorio. Los pasos necesarios para registrar suscripciones de Azure durante un período de retención obligatorio requieren colaboración con Microsoft. Este proceso puede tardar hasta cinco días laborables. Anteriormente, esto a veces se denominaba "No cancelar".
  
Antes de ponerse en contacto con el equipo de Microsoft 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente. Asegúrese de que tiene instalado el módulo [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) antes de empezar.

1. Inicie sesión con Azure PowerShell. Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Register-AzProviderFeature para registrar las suscripciones para usar un período de retención obligatorio. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Póngase en contacto con Microsoft para que el proceso se haya finalizado [en m365ck@microsoft.com](mailto:m365ck@microsoft.com). Incluya lo siguiente en el correo electrónico:

   **Asunto**: Clave de cliente para \<*Your tenant's fully-qualified domain name*\>

   **Cuerpo:** identificadores de suscripción para los que desea finalizar el período de retención obligatorio.
   El resultado de Get-AzProviderFeature para cada suscripción.

   El Contrato de nivel de servicio (SLA) para la finalización de este proceso es de cinco días laborables después de que Microsoft haya sido notificado (y comprobado) de que ha registrado sus suscripciones para usar un período de retención obligatorio.

4. Una vez que reciba la notificación de Microsoft de que el registro se ha completado, compruebe el estado del registro ejecutando el Get-AzProviderFeature siguiente. Si se comprueba, Get-AzProviderFeature comando devuelve un valor **de Registered** para la propiedad **Registration State.** Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para completar el proceso, ejecute el Register-AzResourceProvider comando. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Crear un Almacén de claves de Azure premium en cada suscripción

Los pasos para crear un almacén de claves se documentan en Introducción a [Azure Key Vault,](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)que le guía a través de la instalación y el inicio de Azure PowerShell, la conexión a la suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese grupo de recursos.
  
Al crear un almacén de claves, debe elegir una SKU: Standard o Premium. La SKU estándar permite proteger las claves de Azure Key Vault con software (no hay protección de claves del Módulo de seguridad de hardware (HSM) y la SKU premium permite el uso de HSM para proteger las claves del almacén de claves. Clave de cliente acepta almacenes de claves que usan cualquiera de las SKU, aunque Microsoft recomienda encarecidamente que use solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia en el costo es el costo por mes de cada clave protegida por HSM. Consulta [Precios de Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) para obtener más información.
  
> [!IMPORTANT]
> Use los almacenes de claves sku premium y las claves protegidas por HSM para los datos de producción y solo use las claves y almacenes de claves de SKU estándar con fines de prueba y validación.

Use un prefijo común para los almacenes de claves e incluya una abreviatura del uso y el ámbito del almacén de claves y las claves. Por ejemplo, para el servicio Contoso donde se ubicarán los almacenes en Norteamérica, un posible par de nombres es Contoso-O365-NA-VaultA1 y Contoso-O365-NA-VaultA2. Los nombres de almacén son cadenas únicas globalmente en Azure, por lo que es posible que deba probar las variaciones de los nombres deseados en caso de que otros clientes de Azure ya resonan los nombres deseados. Una vez configurado, los nombres de almacén no se pueden cambiar, por lo que lo más recomendado es tener un plan escrito para la instalación y usar una segunda persona para comprobar que el plan se ejecuta correctamente.

Si es posible, cree los almacenes en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad entre dominios de error de servicio. Por lo tanto, los pares regionales se pueden pensar como la región de copia de seguridad del otro. Esto significa que un recurso de Azure que se coloca en una región obtiene automáticamente tolerancia a errores a través de la región emparejada. Por este motivo, elegir regiones para dos almacenes usados en una directiva de cifrado de datos en la que las regiones están emparejadas significa que solo se usa un total de dos regiones de disponibilidad. La mayoría de las zonas geográficas solo tienen dos regiones, por lo que aún no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para los dos almacenes usados con una directiva de cifrado de datos. Esto se beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, vea Continuidad empresarial y recuperación ante [desastres (BCDR): Regiones emparejadas](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) de Azure para obtener una lista actual de pares regionales.

### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada almacén de claves

Para cada almacén de claves, deberá definir tres conjuntos de permisos independientes para la clave de cliente, según la implementación. Por ejemplo, deberá definir un conjunto de permisos para cada una de las siguientes opciones:
  
- **Administradores del almacén de** claves que realizarán la administración diaria del almacén de claves para su organización. Estas tareas incluyen copia de seguridad, crear, obtener, importar, enumerar y restaurar.

  > [!IMPORTANT]
  > El conjunto de permisos asignados a los administradores del almacén de claves no incluye el permiso para eliminar claves. Esto es intencionado y una práctica importante. Normalmente, la eliminación de claves de cifrado no se realiza, ya que al hacerlo se destruyen datos de forma permanente. Como procedimiento recomendado, no conceda este permiso a los administradores del almacén de claves de forma predeterminada. En su lugar, reserve esto para los colaboradores del almacén de claves y asígnelo solo a un administrador a corto plazo una vez que se comprenda claramente las consecuencias.
  
  Para asignar estos permisos a un usuario de la organización, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Ejecute el cmdlet Set-AzKeyVaultAccessPolicy para asignar los permisos necesarios.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por ejemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores del almacén de** claves que pueden cambiar los permisos en el propio Almacén de claves de Azure. Deberá cambiar estos permisos a medida que los empleados se vayan o se unan a su equipo, o en la rara situación en la que los administradores del almacén de claves necesitan permiso legítimamente para eliminar o restaurar una clave. Este conjunto de colaboradores del almacén de claves debe tener el rol Colaborador en el almacén de claves. Puede asignar este rol con Azure Resource Manager. Para obtener instrucciones detalladas, consulte [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) para administrar el acceso a los recursos de suscripción de Azure. El administrador que crea una suscripción tiene este acceso de forma predeterminada y la capacidad de asignar otros administradores al rol Colaborador.

- Servicio de cifrado de datos en reposo de **Microsoft 365** que realiza el trabajo de clave de cliente en el nivel de inquilino. Para conceder permiso a Microsoft 365, ejecute el cmdlet **Set-AzKeyVaultAccessPolicy** con la siguiente sintaxis:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Donde:

  - *nombre del almacén* es el nombre del almacén de claves que creó.

  Ejemplo: para el servicio de cifrado de datos de Microsoft 365 en reposo, reemplace  *AppID de Microsoft 365* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación suave en los almacenes de claves

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio extendida debido a claves eliminadas accidentalmente o malintencionadas. Habilite esta configuración, denominada Eliminación suave, antes de poder usar las claves con clave de cliente. Habilitar la eliminación suave permite recuperar claves o almacenes dentro de los 90 días posteriores a la eliminación sin tener que restaurarlas a partir de la copia de seguridad.
  
Para habilitar la eliminación suave en los almacenes de claves, siga estos pasos:
  
1. Inicie sesión en su suscripción de Azure con Windows PowerShell. Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet [Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) En este ejemplo, *el nombre del almacén* es el nombre del almacén de claves para el que está habilitando la eliminación suave:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Para confirmar que la eliminación suave está configurada para el almacén de claves, ejecute el cmdlet **Get-AzKeyVault.** Si la eliminación suave está configurada correctamente para el almacén de claves, la propiedad _Soft Delete Enabled_ devuelve un valor de **True**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Agregar una clave a cada almacén de claves mediante la creación o importación de una clave

Hay dos formas de agregar claves a un Almacén de claves de Azure; puede crear una clave directamente en Key Vault o puede importar una clave. La creación de una clave directamente en Key Vault es el método menos complicado, mientras que la importación de una clave proporciona un control total sobre cómo se genera la clave. Use las claves RSA. Azure Key Vault no admite ajustar y desenvolver con claves de curva elípticas.
  
Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) de la siguiente manera:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Donde:

- *nombre del* almacén es el nombre del almacén de claves en el que desea crear la clave.

- *nombre de* clave es el nombre que desea dar a la nueva clave.

  > [!TIP]
  > Asigne nombres a las claves con una convención de nomenclatura similar como se describió anteriormente para los almacenes de claves. De este modo, en las herramientas que solo muestran el nombre de la clave, la cadena se describe a sí misma.
  
Si desea proteger la clave con un HSM, asegúrese de especificar **HSM** como el valor del parámetro _Destination,_ de lo contrario, especifique **Software**.

Por ejemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Comprobar el nivel de recuperación de las claves

Microsoft 365 requiere que la suscripción a Azure Key Vault esté establecida en No cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación suave. Para confirmar esto, busque el nivel de recuperación de las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzKeyVaultKey de la siguiente manera:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Si la propiedad _Nivel_ de recuperación devuelve algo distinto de un valor de **Recoverable+ProtectedSubscription**, deberá revisar este artículo y asegurarse de que ha seguido todos los pasos para colocar la suscripción en la lista No cancelar y que ha habilitado la "eliminación suave" en cada uno de los almacenes de claves. A continuación, envíe una captura de pantalla del resultado del correo electrónico `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` a m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Copia de seguridad de Azure Key Vault

Inmediatamente después de la creación o cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. No conecte copias sin conexión a ninguna red. En su lugar, guárdalos en una instalación de almacenamiento física segura o comercial. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda acceder si se produce un desastre. Los blobs de copia de seguridad son el único medio para restaurar el material de clave en caso de que una clave del almacén de claves se destruya permanentemente o se represente de otro modo inoperable. Las claves externas a Azure Key Vault y que se importaron a Azure Key Vault no califican como copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existen con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para operaciones de restauración con clave de cliente. Por lo tanto, es esencial que realice una copia de seguridad de Azure Key Vault una vez que se cargue o cree una clave.
  
Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) de la siguiente manera:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Asegúrese de que el archivo de salida usa el sufijo `.backup` .
  
El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar en la suscripción de Azure desde la que se ha realizado la copia de seguridad.
  
Por ejemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar las opciones de configuración de Azure Key Vault

Realizar la validación antes de usar claves en un DEP es opcional, pero muy recomendable. En concreto, si usa pasos para configurar las claves y almacenes distintos de los descritos en este tema, debe validar el estado de los recursos de Azure Key Vault antes de configurar la clave de cliente.
  
Para comprobar que las claves tienen habilitadas las operaciones get, wrapKey y unwrapKey:
  
Ejecute el cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

En el resultado, busque la directiva de Access y el identificador de aplicación (GUID) de Microsoft 365 según corresponda. Las tres operaciones, get, wrapKey y unwrapKey, deben mostrarse en Permisos para claves.
  
Si la configuración de la directiva de acceso es incorrecta, ejecute el cmdlet Set-AzKeyVaultAccessPolicy de la siguiente manera:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Ejemplo: para el servicio de cifrado de datos de Microsoft 365 en reposo, reemplace  *AppID de Microsoft 365* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

La clave de cliente no puede usar una clave expirada y las operaciones que se intentan con una clave expirada producirán un error y posiblemente provocarán una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha diferente. Si se debe usar una clave que tenga un conjunto de fechas de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha que no sea 12/31/9999 no superarán la validación de Microsoft 365.
  
Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto del 12/31/9999, ejecute el cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) de la siguiente manera:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el URI de cada clave de Azure Key Vault

Una vez que haya completado todos los pasos de Azure para configurar los almacenes de claves y agregar las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de claves. Deberá usar estos URI al crear y asignar cada DEP más adelante, por lo que guarde esta información en un lugar seguro. Recuerde ejecutar este comando una vez para cada almacén de claves.
  
En Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Configurar la directiva de cifrado de clave de cliente para el inquilino

Debe tener asignados permisos antes de poder ejecutar estos cmdlets. Aunque en este artículo se enumeran todos los parámetros de los cmdlets, es posible que no tenga acceso a algunos parámetros si no están incluidos en los permisos asignados. Para obtener los permisos necesarios para ejecutar cualquier cmdlet o parámetro en su organización, consulte [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Crear directiva

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

Descripción: habilite al administrador de cumplimiento para crear una nueva directiva de cifrado de datos (DEP) con dos claves raíz de AKV. Una vez creada, se puede asignar una directiva mediante Set-M365DataAtRestEncryptionPolicyAssignment cmdlet. Tras la primera asignación de claves o después de girar las teclas, las nuevas claves pueden tardar hasta 24 horas en tener efecto. Si el nuevo DEP tarda más de 24 horas en tener efecto, póngase en contacto con Microsoft.

Ejemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parámetros:

| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
|Nombre|Nombre descriptivo de la directiva de cifrado de datos|N|
|AzureKeyIDs|Especifica dos valores uri de las claves de Azure Key Vault, separadas por una coma, para asociar con la directiva de cifrado de datos|N|
|Descripción|Descripción de la directiva de cifrado de datos|N|

### <a name="assign-policy"></a>Asignar directiva

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “<Default_PolicyName or Default_PolicyID>”
```

Descripción: este cmdlet se usa para configurar la directiva de cifrado de datos predeterminada. Esta directiva se usará para cifrar los datos en todas las cargas de trabajo de soporte técnico. 

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “Default_PolicyName”
```

Parámetros:

| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
-DataEncryptionPolicy|Especifica la directiva de cifrado de datos que debe asignarse; especifique el nombre de la directiva o el identificador de directiva.|N|

### <a name="modify-or-refresh-policy"></a>Modificar o actualizar directiva

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descripción: el cmdlet se puede usar para modificar o actualizar una directiva existente. También se puede usar para habilitar o deshabilitar una directiva. Tras la primera asignación de claves o después de girar las teclas, las nuevas claves pueden tardar hasta 24 horas en tener efecto. Si el nuevo DEP tarda más de 24 horas en tener efecto, póngase en contacto con Microsoft.

Ejemplos:

Deshabilitar una directiva de cifrado de datos.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Actualice una directiva de cifrado de datos.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parámetros:

| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
|-Identidad|Especifica la directiva de cifrado de datos que desea modificar.|N|
|-Refresh|Use el modificador Refresh para actualizar la directiva de cifrado de datos después de girar cualquiera de las claves asociadas en el Almacén de claves de Azure. No es necesario especificar un valor con este modificador.|v|
|-Enabled|El parámetro Enabled habilita o deshabilita la directiva de cifrado de datos. Antes de deshabilitar una directiva, debe desasignla del espacio empresarial. Los valores admitidos son:</br > $true: la directiva está habilitada</br > $true: la directiva está habilitada. Es el valor predeterminado.
|v|
|-Name|El parámetro Name especifica el nombre único de la directiva de cifrado de datos.|v|
|-Description|El parámetro Description especifica una descripción opcional para la directiva de cifrado de datos.|v|

### <a name="get-policy-details"></a>Obtener detalles de la directiva

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descripción: este cmdlet enumera todas las directivas de cifrado M365DataAtRest que se crean para el inquilino o detalles sobre una directiva específica.

Ejemplos:

En este ejemplo se devuelve una lista resumida de directivas de cifrado M365DatAtRest de la organización.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

En este ejemplo se devuelve información detallada para la directiva de cifrado de datos denominada "Directiva de NAM".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parámetros:

| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
|-Identidad|Especifica la directiva de cifrado de datos para la que desea enumerar los detalles.|v|

### <a name="get-policy-assignment-info"></a>Obtener información de asignación de directivas

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Descripción: este cmdlet enumera la directiva que está asignada actualmente al inquilino.

## <a name="offboarding-from-customer-key"></a>Offboarding from Customer Key

Si necesita volver a las claves administradas por Microsoft, puede hacerlo. Cuando se desaborde, los datos se vuelve a cifrar con el cifrado predeterminado admitido por cada carga de trabajo individual. Por ejemplo, Exchange Online admite el cifrado predeterminado mediante claves administradas por Microsoft.

Si decidió retirar el espacio empresarial de la clave de cliente en el nivel de inquilino, envíe una solicitud a Microsoft por correo electrónico para "deshabilitar" el servicio del inquilino en [m365ck@microsoft.com](mailto:m365ck@microsoft.com).

> [!IMPORTANT]
> El offboarding no es lo mismo que una purga de datos. Una purga de datos elimina de forma permanente los datos de la organización de Microsoft 365, pero la eliminación de datos no se realiza. No puede realizar una purga de datos para una directiva de nivel de inquilino. Para obtener información acerca de la ruta de depuración de datos, vea Revocar las claves e iniciar el proceso de ruta [de depuración de datos.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

## <a name="about-the-availability-key"></a>Acerca de la clave de disponibilidad

Para obtener información acerca de la clave de disponibilidad, vea [Learn about the availability key](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Rotación de teclas

Para obtener información sobre la rotación o la rotación de claves usadas con la clave de cliente, vea [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md). Cuando actualice el DEP para usar la nueva versión de las claves, ejecutará el cmdlet Set-M365DataAtRestEncryptionPolicy como se describió anteriormente en este artículo.

## <a name="related-articles"></a>Artículos relacionados:

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Obtenga información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Cifrado de servicio](office-365-service-encryption.md)
