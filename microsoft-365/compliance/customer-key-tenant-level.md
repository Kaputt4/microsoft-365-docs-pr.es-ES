---
title: Clave de cliente de Microsoft 365 en el nivel de inquilino (vista previa pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
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
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712534"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Información general sobre la clave de cliente para Microsoft 365 en el nivel de espacio empresarial (vista previa pública)

Con las claves que proporcione, puede crear una directiva de cifrado de datos (DEP) y asignarla al inquilino. DEP cifra los datos en el inquilino para estas cargas de trabajo:

- Mensajes de chat de Microsoft Teams (1:1 chats, grupos chats, chats de reuniones y conversaciones de canal)
- Mensajes multimedia de Microsoft Teams (imágenes, fragmentos de código, vídeos, imágenes de wiki)
- Grabaciones de reuniones y llamadas de Microsoft Teams almacenadas en el almacenamiento de Teams
- Notificaciones de chat de Microsoft Teams
- Sugerencias de chat de Microsoft Teams por Cortana
- Mensajes de estado de Teams
- Información de usuario y señal para Exchange Online

Para Microsoft Teams, la clave de cliente en el nivel de inquilino cifra los nuevos datos desde el momento en que se asigna la DEP al inquilino. La versión preliminar pública no admite el cifrado de datos pasados. Para Exchange Online, la clave de cliente cifra todos los datos nuevos y existentes.

Puede crear varios DEPs por inquilino, pero solo puede asignar un DEP en cualquier momento. Cuando se asigna la DEP, el cifrado comienza automáticamente, pero puede tardar algún tiempo en completarse en función del tamaño del espacio empresarial.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Las directivas de nivel de inquilino agregan un control más amplio a la clave de cliente de Microsoft 365

Si ya tiene la clave de cliente configurada para Exchange Online y SharePoint Online, esta es la forma en que se ajusta la nueva vista previa pública en el nivel de inquilino.

La Directiva de cifrado de nivel de inquilino que cree cifra todos los datos de las cargas de trabajo de Microsoft Teams y Exchange online en Microsoft 365. Esta Directiva no interfiere con la DEPs optimizada que ya ha creado en la clave de cliente.

Ejemplos:

Los archivos de Microsoft Teams y algunas de las grabaciones de llamadas y reuniones de Microsoft teams que se guardan en OneDrive para la empresa y SharePoint se cifran mediante una DEP de SharePoint Online. Un solo DEP de SharePoint Online cifra contenido dentro de una sola geo. DEP en el nivel de inquilino cifrará los datos cifrados de nuevo con la nueva Directiva.

Para Exchange Online, puede crear un DEP que cifre uno o más buzones de usuario con la clave de cliente. Al crear una directiva de nivel de inquilino, esa Directiva no cifrará los buzones de correo cifrados. Sin embargo, la clave de nivel de inquilino cifrará los buzones que ya no están afectados por un DEP.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurar la clave de cliente en el nivel de inquilino (vista previa pública)

Estos pasos son similares, pero no idénticos, a los pasos para configurar la clave de cliente en el nivel de aplicación. Solo debe usar esta vista previa pública con datos de prueba en los inquilinos de prueba. No use esta versión con datos de producción o en su entorno de producción. Si ya tiene una implementación de producción de la clave de cliente, siga estos pasos para configurar la clave de cliente en el nivel de inquilino en un entorno de prueba.

Completará la mayoría de estas tareas conectándose de forma remota a Azure PowerShell. Para obtener los mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.

Antes de empezar, asegúrese de lo siguiente:

- Deberá usar una cuenta profesional o educativa que tenga el rol de administrador de cumplimiento para configurar la clave de cliente en el nivel de inquilino.
- Asegúrese de que dispone de la licencia adecuada para su organización. Use una suscripción de Azure facturada y pagada mediante un contrato Enterprise o un proveedor de servicios en la nube. Las suscripciones de Azure adquiridas mediante planes de pago a cuenta o con una tarjeta de crédito no se admiten para la clave de cliente. A partir del 1 de abril de 2020, la clave de cliente de Office 365 se ofrece en Office 365 E5, M365 E5, M365 E5 Compliance y M365 E5 Information Protection & las SKU de gobierno. Office 365 Advanced Compliance SKU ya no está disponible para adquirir nuevas licencias. Las licencias de cumplimiento de Office 365 avanzadas existentes seguirán siendo compatibles. Aunque el servicio se puede habilitar con un mínimo de una licencia en el inquilino con la licencia adecuada, debe asegurarse de que todos los usuarios que se beneficien del servicio tengan las licencias adecuadas. Necesitará una de las siguientes licencias:

### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure

La clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como procedimiento recomendado, Microsoft recomienda que los miembros de la organización se configuren como una clave en cada suscripción. Use estas suscripciones de Azure solo para administrar claves de cifrado para Microsoft 365. Esto protege a su organización en caso de que uno de sus operadores elimine accidentalmente, de forma intencionada, o de una mala administración de las claves de las que es responsable.

No hay ningún límite práctico en el número de suscripciones de Azure que puede crear para su organización. Seguir este procedimiento recomendado ayuda a minimizar el impacto de los errores humanos mientras ayuda a administrar los recursos usados por la clave de cliente.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar suscripciones de Azure para usar un período de retención obligatorio

La pérdida temporal o permanente de las claves de cifrado raíz puede ser perjudicial o incluso catastrófica para el funcionamiento del servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección segura. Todos los recursos de Azure que se usan con la clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Las suscripciones de Azure se pueden etiquetar o registrar de manera que se evite la cancelación inmediata y irrevocable. Esto se conoce como registro de un período de retención obligatorio. Los pasos necesarios para registrar las suscripciones de Azure durante un período de retención obligatorio requieren la colaboración con Microsoft. Este proceso puede tardar hasta cinco días hábiles. Anteriormente, a veces se hacía referencia a esto como "no cancelar".
  
Antes de ponerse en contacto con el equipo de Microsoft 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente. Asegúrese de que tiene instalado el módulo de [Azure PowerShell AZ](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) antes de empezar.

1. Inicie sesión con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Register-AzProviderFeature para registrar sus suscripciones y usar un período de retención obligatorio. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Póngase en contacto con Microsoft para finalizar el proceso en [m365ck@microsoft.com](mailto:m365ck@microsoft.com). Incluya lo siguiente en su correo electrónico:

   **Asunto**: clave de cliente de \<*Your tenant's fully-qualified domain name*\>

   **Cuerpo**: identificadores de suscripción para los que desea finalizar el período de retención obligatorio.
   El resultado de Get-AzProviderFeature para cada suscripción.

   El contrato de nivel de servicio (SLA) para completar este proceso es cinco días hábiles después de que Microsoft haya notificado (y comprobado) que ha registrado sus suscripciones para usar un período de retención obligatorio.

4. Una vez que reciba la notificación de Microsoft de que se ha completado el registro, compruebe el estado del registro; para ello, ejecute el comando Get-AzProviderFeature de la siguiente manera. Si se comprueba, el comando Get-AzProviderFeature devuelve un valor de **registrado** para la propiedad de **Estado de registro** . Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para completar el proceso, ejecute el comando Register-AzResourceProvider. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Crear un almacén de claves Premium de Azure en cada suscripción

Los pasos para crear un almacén de claves se documentan en [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que le guiará a través de la instalación y el inicio de Azure PowerShell, la conexión a su suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese grupo de recursos.
  
Al crear un almacén de claves, debe elegir una SKU: estándar o Premium. La SKU estándar permite que las claves de Azure Key Vault estén protegidas con software (no hay protección de clave de módulo de seguridad de hardware (HSM) y la SKU Premium permite usar los HSM para proteger las claves de la bóveda clave. La clave de cliente acepta almacenes clave que usan una SKU, pero Microsoft recomienda encarecidamente usar solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia de costo es el costo cada mes para cada clave protegida por HSM. Consulte [tarifas clave](https://azure.microsoft.com/pricing/details/key-vault/) de la bóveda para obtener más información.
  
> [!IMPORTANT]
> Use los almacenes clave de SKU Premium y las claves protegidas por HSM para los datos de producción y use únicamente las claves y los almacenes de claves de SKU estándar para fines de prueba y validación.

Use un prefijo común para los depósitos clave e incluya una abreviatura del uso y el alcance de las claves y el almacén de claves. Por ejemplo, para el servicio de Contoso donde los almacenes se ubicarán en Norteamérica, un posible par de nombres es contoso-O365-NA-VaultA1 y contoso-O365-NA-VaultA2. Los nombres de almacén son cadenas únicas de forma global dentro de Azure, por lo que es posible que deba probar variantes de sus nombres deseados en caso de que otros clientes de Azure ya hayan reclamado los nombres deseados. Una vez configurados, los nombres de almacén no se pueden cambiar, por lo que el procedimiento recomendado es tener un plan escrito para la configuración y usar una segunda persona para comprobar que el plan se ejecuta correctamente.

Si es posible, cree sus depósitos en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad en todos los dominios de error de servicio. Por lo tanto, los pares regionales pueden considerarse como una región de copia de seguridad de cada uno. Esto significa que un recurso de Azure que se coloca en una región está obteniendo automáticamente la tolerancia a errores a través de la región emparejada. Por este motivo, la elección de regiones para dos almacenes usados en una directiva de cifrado de datos en la que las regiones están emparejadas significa que solo se usa un total de dos regiones de disponibilidad. La mayoría de las zonas geográficas solo tienen dos regiones, por lo que todavía no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para las dos Vaults que se usan con una directiva de cifrado de datos. Esto beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, vea [continuidad empresarial y recuperación ante desastres (BCDR): regiones emparejadas de Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista actual de pares regionales.

### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada almacén clave

Para cada almacén de claves, tendrá que definir tres conjuntos de permisos distintos para la clave de cliente, según la implementación. Por ejemplo, tendrá que definir un conjunto de permisos para cada uno de los siguientes elementos:
  
- **Administradores de la bóveda clave** que realizarán la administración cotidiana de su almacén clave para su organización. Estas tareas incluyen copia de seguridad, crear, obtener, importar, enumerar y restaurar.

  > [!IMPORTANT]
  > El conjunto de permisos asignado a los administradores de la bóveda de claves no incluye el permiso para eliminar claves. Esto es intencionado y es un ejercicio importante. La eliminación de claves de cifrado no suele realizarse, ya que al hacerlo se destruyen los datos de forma permanente. Como procedimiento recomendado, no conceda este permiso a los administradores de la bóveda clave de forma predeterminada. En su lugar, Reserve esto para los colaboradores clave de la bóveda y asígnelo solo a un administrador a corto plazo una vez que comprenda claramente las consecuencias.
  
  Para asignar estos permisos a un usuario de su organización, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Ejecute el cmdlet Set-AzKeyVaultAccessPolicy para asignar los permisos necesarios.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por ejemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Contribute de Key Vault** que puede cambiar los permisos en el propio almacén de claves de Azure. Deberá cambiar estos permisos a medida que los empleados abandonen o se unan a su equipo, o en la situación poco frecuente de que los administradores de la bóveda clave necesiten de forma legítima permiso para eliminar o restaurar una clave. Este conjunto de colaboradores clave del almacén debe tener concedido el rol colaborador en su almacén de claves. Puede asignar este rol mediante el administrador de recursos de Azure. Para conocer los pasos detallados, consulte [Use Role-Based control de acceso](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) para administrar el acceso a los recursos de suscripción de Azure. El administrador que crea una suscripción tiene este acceso de forma predeterminada y la capacidad de asignar otros administradores al rol colaborador.

- **Servicio de cifrado de datos en REST de Microsoft 365** que realiza el trabajo de la clave de cliente en el nivel de inquilino. Para conceder permiso a Microsoft 365, ejecute el cmdlet **set-AzKeyVaultAccessPolicy** con la siguiente sintaxis:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Donde:

  - el *nombre del almacén* es el nombre del almacén de claves que ha creado.

  Ejemplo: para el servicio de cifrado de datos en reposo de Microsoft 365, reemplace  *Microsoft 365 appID* con `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio prolongada debido a claves eliminadas accidental o malintencionadamente. Habilite esta configuración, que se conoce como eliminación temporal, antes de que pueda usar las claves con la clave de cliente. La habilitación de la eliminación temporal permite recuperar claves o depósitos en un plazo de 90 días de eliminación sin tener que restaurarlos a partir de la copia de seguridad.
  
Para habilitar la eliminación temporal en los almacenes clave, siga estos pasos:
  
1. Inicie sesión en su suscripción de Azure con Windows PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) . En este ejemplo, el *nombre del almacén* es el nombre del almacén de claves para el que se va a habilitar la eliminación temporal:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirme que la eliminación de software está configurada para el almacén de claves mediante la ejecución del cmdlet **Get-AzKeyVault** . Si la eliminación temporal está configurada correctamente para el almacén de claves, la propiedad _eliminación temporal habilitada_ devuelve un valor **true**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Agregar una clave a cada depósito clave creando o importando una clave

Hay dos formas de agregar claves a un almacén de claves de Azure; puede crear una clave directamente en el almacén de claves, o puede importar una clave. La creación de una clave directamente en el almacén de claves es el método menos complicado, mientras que la importación de una clave proporciona un control total sobre la forma en que se genera la clave. Usar las claves RSA. Azure Key Vault no admite el ajuste y desajuste de claves de curva elíptica.
  
Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) de la siguiente manera:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Donde:

- *nombre del almacén* es el nombre del almacén de clave en el que desea crear la clave.

- *nombre de clave* es el nombre que desea asignar a la nueva clave.

  > [!TIP]
  > Denomine claves con una Convención de nomenclatura similar, como se ha descrito anteriormente para los almacenes de claves. De este modo, en las herramientas que solo muestran el nombre de la clave, la cadena es autodescriptivo.
  
Si piensa proteger la clave con un HSM, asegúrese de especificar **HSM** como el valor del parámetro _Destination_ ; de lo contrario, especifique el **software**.

Por ejemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Comprobar el nivel de recuperación de las claves

Microsoft 365 requiere que la suscripción de Azure Key Vault esté definida como no cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación temporal. Para confirmarlo, consulte el nivel de recuperación de las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzKeyVaultKey de la siguiente manera:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Si la propiedad _nivel de recuperación_ devuelve cualquier cosa que no sea un valor **recuperable + ProtectedSubscription**, tendrá que revisar este artículo y asegurarse de que ha seguido todos los pasos para poner la suscripción en la lista no cancelar y que ha habilitado la eliminación temporal en cada una de las cajas fuertes de clave. A continuación, envíe una captura de pantalla del resultado de `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` en correo electrónico a m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Copia de seguridad de Azure Key Vault

Inmediatamente después de la creación o de cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. No conecte las copias sin conexión a ninguna red. En su lugar, almacénelos en un servicio físico seguro o de almacenamiento comercial. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda tener acceso si se produce un desastre. Los blobs de copia de seguridad son los únicos medios de restaurar el material clave en caso de que una clave de almacén clave se destruya de forma permanente o no pueda ser procesada de forma inservible. Las claves externas a Azure Key Vault y que se importaron a Azure Key Vault no se califican como una copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existe con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para las operaciones de restauración con la clave de cliente. Por lo tanto, es esencial que realice una copia de seguridad de Azure Key Vault una vez que se haya cargado o creado una clave.
  
Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) de la siguiente manera:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Asegúrese de que el archivo de salida Use el sufijo `.backup` .
  
El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar a la suscripción de Azure desde la que se realizó la copia de seguridad.
  
Por ejemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar las opciones de configuración de Azure Key Vault

La validación antes de usar claves en un DEP es opcional, pero se recomienda encarecidamente. En particular, si usa los pasos para configurar las claves y los almacenes distintos de los que se describen en este tema, debe validar el estado de los recursos de Azure Key Vault antes de configurar la clave de cliente.
  
Para comprobar que las claves tienen las operaciones GET, wrapKey y unwrapKey habilitadas:
  
Ejecute el cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

En el resultado, busque la Directiva de acceso y el identificador de aplicación (GUID) de 365 según corresponda. Las tres operaciones, get, wrapKey y unwrapKey, deben mostrarse en permisos a claves.
  
Si la configuración de la Directiva de acceso no es correcta, ejecute el cmdlet Set-AzKeyVaultAccessPolicy de la siguiente manera:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Ejemplo: para el servicio de cifrado de datos en reposo de Microsoft 365, reemplace  *Microsoft 365 appID* con `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

La clave de cliente no puede usar una clave expirada y las operaciones que se intenten con una clave expirada producirán un error y, posiblemente, se producirá una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha distinta. Si se debe usar una clave que tenga establecida una fecha de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha distinta a 12/31/9999 no pasarán la validación 365 de Microsoft.
  
Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto de 12/31/9999, ejecute el cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) de la siguiente manera:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el URI para cada clave de Azure Key Vault

Una vez que haya completado todos los pasos de Azure para configurar los almacenes clave y haya agregado las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de clave. Tendrá que usar estos URI cuando cree y asigne cada DEP más adelante, por lo que debe guardar esta información en un lugar seguro. Recuerde ejecutar este comando una vez para cada almacén de clave.
  
En Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Configurar la Directiva de cifrado de clave de cliente para el espacio empresarial

Debe tener permisos asignados para poder ejecutar estos cmdlets. Aunque en este artículo se enumeran todos los parámetros para los cmdlets, es posible que no tenga acceso a algunos parámetros si no están incluidos en los permisos que tiene asignados. Para obtener los permisos necesarios para ejecutar cualquier cmdlet o parámetro en su organización, consulte [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Crear directiva

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

Descripción: habilite el administrador de cumplimiento para crear una nueva Directiva de cifrado de datos (DEP) con dos claves raíz de AKV. Una vez creada, se puede asignar una Directiva mediante Set-M365DataAtRestEncryptionPolicy cmdlet. La primera vez que se asignan claves o cuando se giran las claves, puede que las nuevas claves surtan efecto hasta 24 horas. Si el nuevo DEP tarda más de 24 horas en surtir efecto, póngase en contacto con Microsoft.

Ejemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parámetros:

| Nombre | Descripción | Opcional (s/N) |
|--|--|--|
|Name|Nombre descriptivo de la Directiva de cifrado de datos|N|
|AzureKeyIDs|Especifica dos valores de URI de las claves de Azure Key Vault, separados por una coma, para asociar con la Directiva de cifrado de datos|N|
|Descripción|Descripción de la Directiva de cifrado de datos|N|

### <a name="assign-policy"></a>Asignar directiva

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

Descripción: este cmdlet se usa para configurar una directiva de cifrado de datos predeterminada. Esta Directiva se usará para cifrar datos a través de todas las cargas de trabajo de soporte. 

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

Parámetros:
| Nombre | Descripción | Opcional (s/N) |
|--|--|--|
: Directiva|Especifica la Directiva de cifrado de datos que se debe asignar; Especifique el nombre de la Directiva o el identificador de la Directiva.|N|

### <a name="modify-or-refresh-policy"></a>Modificar o actualizar la Directiva

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descripción: el cmdlet se puede usar para modificar o actualizar una directiva existente. También se puede usar para habilitar o deshabilitar una directiva. La primera vez que se asignan claves o cuando se giran las claves, puede que las nuevas claves surtan efecto hasta 24 horas. Si el nuevo DEP tarda más de 24 horas en surtir efecto, póngase en contacto con Microsoft.

Ejemplos:

Deshabilitar una directiva de cifrado de datos.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Actualizar una directiva de cifrado de datos.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parámetros:
| Nombre | Descripción | Opcional (s/N) |
|--|--|--|
|-Identity|Especifica la Directiva de cifrado de datos que desea modificar.|N|
|-Refresh|Use el modificador de actualización para actualizar la Directiva de cifrado de datos después de girar cualquiera de las claves asociadas en el almacén de claves de Azure. No es necesario especificar un valor con este modificador.|v|
|Habilitado para|El parámetro Enabled habilita o deshabilita la Directiva de cifrado de datos. Antes de deshabilitar una directiva, debe desasignarla de su espacio empresarial. Los valores válidos son:</br > $true: la Directiva está habilitada</br > $true: la directiva está habilitada. Es el valor predeterminado.
|v|
|-Name|El parámetro name especifica el nombre único de la Directiva de cifrado de datos.|v
|-Description|El parámetro Description especifica una descripción opcional para la Directiva de cifrado de datos.|v|

### <a name="get-policy-details"></a>Obtener detalles de la Directiva

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descripción: este cmdlet muestra una lista de todas las directivas de cifrado de M365DataAtRest que se crean para el inquilino o información detallada sobre una directiva específica.

Ejemplos:

En este ejemplo se devuelve una lista resumida de las directivas de cifrado de M365DatAtRest en la organización.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

En este ejemplo se devuelve información detallada sobre la Directiva de cifrado de datos denominada "Directiva de NAM".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parámetros:

| Nombre | Descripción | Opcional (s/N) |
|--|--|--|
|-Identity|Especifica la Directiva de cifrado de datos para la que desea enumerar los detalles.|v|

### <a name="get-policy-assignment-info"></a>Obtener información de asignación de Directiva

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Descripción: este cmdlet muestra la Directiva que está asignada actualmente al inquilino.

## <a name="offboarding-from-customer-key"></a>Descarga de la clave de cliente

Si necesita volver a las claves administradas por Microsoft, puede hacerlo. Al desincorpora, los datos se vuelven a cifrar con el cifrado predeterminado que admite cada carga de trabajo individual. Por ejemplo, Exchange Online admite el cifrado predeterminado mediante claves administradas por Microsoft.

Si decidió desincorpora su espacio empresarial de la clave de cliente en el nivel de inquilino, póngase en contacto con Microsoft con una solicitud a través del correo electrónico para "Deshabilitar" el servicio del inquilino en [m365ck@microsoft.com](mailto:m365ck@microsoft.com).

> [!IMPORTANT]
> La descarga no es lo mismo que una depuración de datos. La descifrado de datos elimina de forma permanente los datos de su organización de Microsoft 365, no se admite la descarga. No se puede realizar una depuración de datos para una directiva de nivel de inquilino. Para obtener información acerca de la ruta de purga de datos, consulte [revocar claves e iniciar el proceso de ruta de purga de datos](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

## <a name="about-the-availability-key"></a>Acerca de la clave de disponibilidad

Para obtener información acerca de la clave de disponibilidad, consulte [información sobre la clave de disponibilidad](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Rotación de clave

Para obtener información acerca de las teclas de rotación o desplazamiento usadas con la clave de cliente, consulte [Roll or Rotate a Customer Key o a Availability Key](customer-key-availability-key-roll.md). Al actualizar la DEP para usar la nueva versión de las claves, deberá ejecutar el cmdlet Set-M365DataAtRestEncryptionPolicy como se describió anteriormente en este artículo.

## <a name="related-articles"></a>Artículos relacionados:

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Obtener información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Cifrado de servicio](office-365-service-encryption.md)
