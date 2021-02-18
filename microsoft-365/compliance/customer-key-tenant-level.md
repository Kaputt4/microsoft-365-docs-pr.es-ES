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
ms.openlocfilehash: 60704f77e17222de790cb397653a2275144d770e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288151"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Introducción a la clave de cliente de Microsoft 365 en el nivel de inquilino (versión preliminar pública)

Con las claves que proporcione, puede crear una directiva de cifrado de datos (DEP) y asignarla al inquilino. El DEP cifra los datos en todo el espacio empresarial para estas cargas de trabajo:

- Mensajes de chat de Teams (chats de 1:1, chats de grupo, chats de reuniones y conversaciones de canal)
- Mensajes multimedia de Teams (imágenes, fragmentos de código, mensajes de vídeos, mensajes de audio, imágenes wiki)
- Grabaciones de llamadas y reuniones de Teams almacenadas en el almacenamiento de Teams
- Notificaciones de chat de Teams
- Sugerencias de chat de Teams de Cortana
- Mensajes de estado de Teams
- Información de usuario y señal para Exchange Online

Para Microsoft Teams, la clave de cliente en el nivel de inquilino cifra nuevos datos desde el momento en que se asigna el DEP al inquilino. La versión preliminar pública no admite el cifrado de datos anteriores. Para Exchange Online, la clave de cliente cifra todos los datos nuevos y existentes.

Puede crear varios DEP por inquilino, pero solo puede asignar un DEP en cualquier momento. Cuando asigna el DEP, el cifrado comienza automáticamente, pero puede tardar algún tiempo en completarse según el tamaño de su espacio empresarial.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Las directivas de nivel de inquilino agregan un control más amplio a la clave de cliente para Microsoft 365

Si ya tiene la clave de cliente configurada para Exchange Online y Sharepoint Online, esta es la forma en que se ajusta la nueva versión preliminar pública de nivel de inquilino.

La directiva de cifrado de nivel de inquilino que cree cifra todos los datos de las cargas de trabajo de Microsoft Teams y Exchange Online en Microsoft 365. Esta directiva no interfiere con los DEP ajustados que ya creaste en la clave de cliente.

Ejemplos:

Los archivos de Microsoft Teams y algunas grabaciones de reuniones y llamadas de Teams que se guardan en OneDrive para la Empresa y SharePoint se cifran mediante un DEP de SharePoint Online. Un solo DEP de SharePoint Online cifra el contenido dentro de una única ubicación geográfica.

Para Exchange Online, puede crear un DEP que cifre uno o más buzones de usuario con la clave de cliente. Al crear una directiva de nivel de inquilino, esa directiva no cifrará los buzones cifrados. Sin embargo, la clave de nivel de inquilino cifrará los buzones que aún no se ven afectados por un DEP.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Configurar la clave de cliente en el nivel de inquilino (versión preliminar pública)

Estos pasos son similares, pero no idénticos, a los pasos para configurar la clave de cliente en el nivel de aplicación. Solo debe usar esta versión preliminar pública con datos de prueba en espacios empresariales de prueba. No use esta versión con datos de producción o en su entorno de producción. Si ya tiene una implementación de producción de clave de cliente, siga estos pasos para configurar la clave de cliente en el nivel de inquilino en un entorno de prueba.

You'll complete most of these tasks by remotely connecting to Azure PowerShell. Para obtener mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.

Antes de empezar, asegúrese de lo siguiente:

- Deberá usar una cuenta profesional o educativa que tenga el rol de administrador de cumplimiento para configurar la clave de cliente en el nivel de inquilino.
- Asegúrese de que tiene las licencias adecuadas para su organización. Use una suscripción de Azure facturada y de pago con un proveedor Contrato Enterprise o un proveedor de servicios en la nube. Las suscripciones de Azure adquiridas con planes de Pago a medida que vaya o con una tarjeta de crédito no se admiten para la clave de cliente. A partir del 1 de abril de 2020, la clave de cliente en Office 365 se ofrece en Office 365 E5, M365 E5, cumplimiento de M365 E5 y M365 E5 Information Protection & GOVERNANCE SKU. Sku de cumplimiento avanzado de Office 365 ya no está disponible para adquirir nuevas licencias. Las licencias de Cumplimiento avanzado de Office 365 existentes seguirán siendo compatibles. Aunque el servicio se puede habilitar con un mínimo de una licencia en el espacio empresarial que tenga la licencia adecuada, debe asegurarse de que todos los usuarios que se benefician del servicio tengan las licencias adecuadas.

### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure

La clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda tener miembros independientes de la organización que configuren una clave en cada suscripción. Use solo estas suscripciones de Azure para administrar claves de cifrado para Microsoft 365. Esto protege la organización en caso de que uno de los operadores elimine o desajuste las claves de las que son responsables de forma accidental, intencionada o malintencionada.

No hay ningún límite práctico para el número de suscripciones de Azure que puede crear para su organización. Siguiendo este procedimiento recomendado, se ayuda a minimizar el impacto de errores humanos y a administrar los recursos usados por la clave de cliente.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar suscripciones de Azure para usar un período de retención obligatorio

La pérdida temporal o permanente de claves de cifrado raíz puede ser perjudicial o incluso catastrófica para la operación de servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección sólida. Todos los recursos de Azure que se usan con la clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Las suscripciones de Azure se pueden etiquetar o registrar de forma que se evite la cancelación inmediata e irrevocable. Esto se conoce como registro durante un período de retención obligatorio. Los pasos necesarios para registrar suscripciones de Azure durante un período de retención obligatorio requieren la colaboración con Microsoft. Este proceso puede tardar hasta cinco días laborables. Anteriormente, esto se denominaba a veces "No cancelar".
  
Antes de ponerse en contacto con el equipo de Microsoft 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente. Asegúrese de tener instalado el [módulo Az de Azure PowerShell](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) antes de empezar.

1. Inicie sesión con Azure PowerShell. Para obtener instrucciones, [vea Iniciar sesión con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Ejecute el cmdlet Register-AzProviderFeature para registrar las suscripciones y usar un período de retención obligatorio. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Póngase en contacto con Microsoft para que el proceso se haya finalizado [en m365ck@microsoft.com](mailto:m365ck@microsoft.com). Incluya lo siguiente en el correo electrónico:

   **Asunto:** clave de cliente para \<*Your tenant's fully-qualified domain name*\>

   **Cuerpo:** identificadores de suscripción para los que desea finalizar el período de retención obligatorio.
   El resultado de Get-AzProviderFeature para cada suscripción.

   El Contrato de nivel de servicio (SLA) para la finalización de este proceso es de cinco días laborables una vez que Se haya notificado (y comprobado) a Microsoft que ha registrado sus suscripciones para usar un período de retención obligatorio.

4. Una vez que reciba la notificación de Microsoft de que el registro se ha completado, ejecute el Get-AzProviderFeature comando como se muestra a continuación. Si se comprueba, Get-AzProviderFeature comando devuelve un valor **de Registered** para la propiedad **Registration State.** Realice esta acción para cada suscripción.

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

Los pasos para crear un almacén de claves se documentan en Introducción a [Azure Key Vault,](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)que le guiará a través de la instalación y el inicio de Azure PowerShell, la conexión a su suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese grupo de recursos.
  
Al crear un almacén de claves, debes elegir una SKU: Standard o Premium. La SKU estándar permite proteger las claves de Azure Key Vault con software (no hay protección de claves del Módulo de seguridad de hardware ( OEM) y la SKU premium permite el uso de HSMs para la protección de claves del almacén de claves. Clave de cliente acepta almacenes de claves que usan cualquier SKU, aunque Microsoft recomienda encarecidamente usar solo la SKU Premium. El costo de las operaciones con claves de cualquiera de los tipos es el mismo, por lo que la única diferencia en el costo es el costo por mes de cada clave protegida con HSM. Consulte los [precios del Almacén de claves](https://azure.microsoft.com/pricing/details/key-vault/) para obtener más información.
  
> [!IMPORTANT]
> Usa los almacenes de claves de SKU premium y las claves protegidas por HSM para los datos de producción, y solo usa las claves y almacenes de claves de SKU estándar con fines de prueba y validación.

Use un prefijo común para almacenes de claves e incluya una abreviatura del uso y el ámbito del almacén de claves y las claves. Por ejemplo, para el servicio Contoso donde se ubicarán las cámaras en Norteamérica, un posible par de nombres es Contoso-O365-NA-VaultA1 y Contoso-O365-NA-VaultA2. Los nombres de las cámaras son cadenas únicas globalmente en Azure, por lo que es posible que deba probar las variaciones de los nombres deseados en caso de que otros clientes de Azure ya reclamaran los nombres deseados. Una vez configurado, los nombres de las cámaras no se pueden cambiar, por lo que el procedimiento recomendado es tener un plan escrito para la instalación y usar una segunda persona para comprobar que el plan se ejecuta correctamente.

Si es posible, cree las cámaras en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad entre dominios de error de servicio. Por lo tanto, los pares regionales se pueden pensar como la región de copia de seguridad del otro. Esto significa que un recurso de Azure que se coloca en una región obtiene automáticamente tolerancia a errores a través de la región emparejada. Por este motivo, elegir regiones para dos almacenes usados en una directiva de cifrado de datos en la que las regiones están emparejadas significa que solo están en uso un total de dos regiones de disponibilidad. La mayoría de las regiones geográficas solo tienen dos regiones, por lo que aún no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para los dos almacenes usados con una directiva de cifrado de datos. Esto se beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, consulte Continuidad empresarial y recuperación ante [desastres (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista actual de pares regionales.

### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada almacén de claves

Para cada almacén de claves, deberá definir tres conjuntos de permisos independientes para la clave de cliente, en función de su implementación. Por ejemplo, tendrá que definir un conjunto de permisos para cada uno de los siguientes:
  
- **Administradores del almacén de** claves que realizarán la administración diaria del almacén de claves de su organización. Estas tareas incluyen copia de seguridad, creación, obtener, importar, enumerar y restaurar.

  > [!IMPORTANT]
  > El conjunto de permisos asignados a los administradores del almacén de claves no incluye el permiso para eliminar claves. Esto es intencionado y una práctica importante. La eliminación de claves de cifrado no suele realizarse, ya que al hacerlo se destruyen los datos de forma permanente. Como procedimiento recomendado, no conceda este permiso de forma predeterminada a los administradores del almacén de claves. En su lugar, reserve esto para los colaboradores del almacén de claves y asígnelo solo a un administrador a corto plazo una vez que comprenda claramente las consecuencias.
  
  Para asignar estos permisos a un usuario de su organización, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, [vea Iniciar sesión con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

   Ejecute el cmdlet Set-AzKeyVaultAccessPolicy para asignar los permisos necesarios.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por ejemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores del almacén de** claves que pueden cambiar los permisos en el propio Almacén de claves de Azure. Tendrá que cambiar estos permisos a medida que los empleados abandonan o se unen a su equipo, o en la rara situación en la que los administradores del almacén de claves necesitan legítimamente permiso para eliminar o restaurar una clave. A este conjunto de colaboradores del almacén de claves se le debe conceder el rol colaborador en el almacén de claves. Puede asignar este rol mediante el Administrador de recursos de Azure. Para conocer los pasos detallados, consulte [Usar Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) para administrar el acceso a los recursos de suscripción de Azure. El administrador que crea una suscripción tiene este acceso de forma predeterminada y la capacidad de asignar otros administradores al rol colaborador.

- Servicio de cifrado de datos en reposo de **Microsoft 365** que realiza el trabajo de clave de cliente en el nivel de inquilino. Para conceder permiso a Microsoft 365, ejecute el cmdlet **Set-AzKeyVaultAccessPolicy** con la siguiente sintaxis:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Donde:

  - *nombre del almacén* es el nombre del almacén de claves que creó.

  Ejemplo: para el servicio cifrado de datos en reposo de Microsoft 365, reemplace el appID de  *Microsoft 365* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación de forma flexible en los almacenes de claves

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio extendida debido a claves eliminadas accidentalmente o malintencionadamente. Habilita esta configuración, denominada Eliminación de forma automática, antes de poder usar las claves con la clave de cliente. Habilitar la eliminación de software permite recuperar claves o almacenes en un plazo de 90 días desde la eliminación sin tener que restaurarlas a partir de la copia de seguridad.
  
Para habilitar la eliminación soft en los almacenes de claves, siga estos pasos:
  
1. Inicie sesión en su suscripción de Azure con Windows PowerShell. Para obtener instrucciones, [vea Iniciar sesión con Azure PowerShell.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Ejecuta el cmdlet [Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) En este ejemplo, el *nombre de la* cámara es el nombre del almacén de claves para el que está habilitando la eliminación de forma flexible:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Para confirmar que la eliminación soft está configurada para el almacén de claves, ejecute el cmdlet **Get-AzKeyVault.** Si la eliminación soft está configurada correctamente para el almacén de claves, la propiedad _Habilitada para_ eliminación soft devuelve un valor **true:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Agregar una clave a cada almacén de claves mediante la creación o importación de una clave

Hay dos formas de agregar claves a un Almacén de claves de Azure; puede crear una clave directamente en el Almacén de claves o puede importar una clave. La creación de una clave directamente en el Almacén de claves es el método menos complicado, mientras que la importación de una clave proporciona control total sobre cómo se genera la clave. Use las claves RSA. Azure Key Vault no admite el ajuste ni el desencapsulado con teclas de curva elíptica.
  
Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) de la siguiente manera:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Donde:

- *el nombre* del almacén de claves es el nombre del almacén de claves en el que desea crear la clave.

- *nombre de* clave es el nombre que desea dar a la nueva clave.

  > [!TIP]
  > Las claves de nombre usan una convención de nomenclatura similar como se describió anteriormente para almacenes de claves. De este modo, en las herramientas que muestran solo el nombre de la clave, la cadena es autodescripta.
  
Si desea proteger la clave con un RELA, asegúrese de especificar **HSM** como el valor del parámetro _Destination;_ de lo contrario, especifique **Software**.

Por ejemplo,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Comprobar el nivel de recuperación de las claves

Microsoft 365 requiere que la suscripción a Azure Key Vault esté establecida en No cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación de forma automática. Para confirmar esto, mira el nivel de recuperación de las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzKeyVaultKey como se muestra a continuación:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Si  la propiedad Nivel de recuperación devuelve algo que no sea un valor de **Recoverable+ProtectedSubscription**, deberá revisar este artículo y asegurarse de que ha seguido todos los pasos para colocar la suscripción en la lista No cancelar y que habilitó la "eliminación soft" en cada uno de los almacenes de claves. A continuación, envíe una captura de pantalla del resultado en el correo `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` electrónico a m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Copia de seguridad de Azure Key Vault

Inmediatamente después de la creación o de cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. No conecte copias sin conexión a ninguna red. En su lugar, guárdalos en una instalación de almacenamiento comercial o segura física. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda tener acceso si se produce un desastre. Los blobs de copia de seguridad son el único medio de restaurar material de clave en caso de que una clave del almacén de claves se destruya permanentemente o se represente de otro modo inoperable. Las claves que son externas a Azure Key Vault y que se importaron a Azure Key Vault no se califican como una copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existen con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para operaciones de restauración con clave de cliente. Por lo tanto, es esencial que realice una copia de seguridad de Azure Key Vault una vez que se cargue o cree una clave.
  
Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) de la siguiente manera:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Asegúrese de que el archivo de salida usa el sufijo `.backup` .
  
El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar en la suscripción de Azure desde la que se tomó la copia de seguridad.
  
Por ejemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar las opciones de configuración de Azure Key Vault

Realizar la validación antes de usar claves en un DEP es opcional, pero muy recomendable. En particular, si usa pasos para configurar las claves y almacenes distintos de los descritos en este tema, debe validar el estado de los recursos de Azure Key Vault antes de configurar la clave de cliente.
  
Para comprobar que las claves tienen habilitadas las operaciones get, wrapKey y unwrapKey:
  
Ejecute el cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

En el resultado, busque la directiva de acceso y el identificador de aplicación (GUID) de Microsoft 365 según corresponda. Las tres operaciones, get, wrapKey y unwrapKey, deben mostrarse en Permisos para claves.
  
Si la configuración de la directiva de acceso es incorrecta, ejecute Set-AzKeyVaultAccessPolicy cmdlet de la siguiente manera:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Ejemplo: para el servicio cifrado de datos en reposo de Microsoft 365, reemplace el appID de  *Microsoft 365* por `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

La clave de cliente no puede usar una clave expirada y las operaciones intentadas con una clave expirada producirán un error y, posiblemente, provocarán una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha diferente. Si se debe usar una clave que tenga una fecha de expiración establecida, cambie el valor de expiración a 31/12/9999. Las claves con una fecha de expiración establecida en una fecha que no sea 31/12/9999 no superarán la validación de Microsoft 365.
  
Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto del 31/12/9999, ejecute el cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) de la siguiente manera:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el URI para cada clave de Azure Key Vault

Una vez que haya completado todos los pasos de Azure para configurar los almacenes de claves y agregar las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de claves. Deberás usar estos URI al crear y asignar cada DEP más adelante, así que guarda esta información en un lugar seguro. Recuerde ejecutar este comando una vez para cada almacén de claves.
  
En Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Configurar la directiva de cifrado de clave de cliente para el inquilino

Deberá tener asignados permisos antes de poder ejecutar estos cmdlets. Aunque en este artículo se enumeran todos los parámetros de los cmdlets, es posible que no tenga acceso a algunos parámetros si no están incluidos en los permisos que se le han asignado. Para obtener los permisos necesarios para ejecutar cualquier cmdlet o parámetro en su organización, consulte [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).

### <a name="create-policy"></a>Crear directiva

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

Descripción: habilite al administrador de cumplimiento para crear una nueva directiva de cifrado de datos (DEP) con dos claves raíz de AKV. Una vez creada, se puede asignar una directiva mediante Set-M365DataAtRestEncryptionPolicy cmdlet. Tras la primera asignación de teclas o después de girar las teclas, las nuevas teclas pueden tardar hasta 24 horas en tener efecto. Si el nuevo DEP tarda más de 24 horas en tener efecto, póngase en contacto con Microsoft.

Ejemplo:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parámetros:

| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
|Nombre|Nombre descriptivo de la directiva de cifrado de datos|N|
|AzureKeyIDs|Especifica dos valores uri de las claves de Azure Key Vault, separadas por comas, para asociar con la directiva de cifrado de datos|N|
|Descripción|Descripción de la directiva de cifrado de datos|N|

### <a name="assign-policy"></a>Asignar directiva

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

Descripción: este cmdlet se usa para configurar la directiva de cifrado de datos predeterminada. Esta directiva se usará para cifrar datos en todas las cargas de trabajo de soporte técnico. 

Ejemplo:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

Parámetros:
| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
-Policy|Especifica la directiva de cifrado de datos que debe asignarse; especifique el nombre de la directiva o el identificador de directiva.|N|

### <a name="modify-or-refresh-policy"></a>Modificar o actualizar directiva

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Descripción: el cmdlet se puede usar para modificar o actualizar una directiva existente. También se puede usar para habilitar o deshabilitar una directiva. Tras la primera asignación de teclas o después de girar las teclas, las nuevas teclas pueden tardar hasta 24 horas en tener efecto. Si el nuevo DEP tarda más de 24 horas en tener efecto, póngase en contacto con Microsoft.

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
| Nombre | Descripción | Opcional (Y/N) |
|----------|----------|---------|
|-Identidad|Especifica la directiva de cifrado de datos que desea modificar.|N|
|-Refresh|Use el modificador Refresh para actualizar la directiva de cifrado de datos después de girar cualquiera de las claves asociadas en azure Key Vault. No es necesario especificar un valor con este modificador.|v|
|-Enabled|El parámetro Enabled habilita o deshabilita la directiva de cifrado de datos. Antes de deshabilitar una directiva, debe desasignla del espacio empresarial. Los valores válidos son:</br > $true: la directiva está habilitada</br > $true: la directiva está habilitada. Es el valor predeterminado.
|v|
|-Name|El parámetro Name especifica el nombre único de la directiva de cifrado de datos.|v
|-Description|El parámetro Description especifica una descripción opcional para la directiva de cifrado de datos.|v|

### <a name="get-policy-details"></a>Obtener detalles de la directiva

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Descripción: este cmdlet enumera todas las directivas de cifrado M365DataAtRest que se crean para el inquilino o detalles sobre una directiva específica.

Ejemplos:

En este ejemplo se devuelve una lista resumida de directivas de cifrado M365DatAtRest de la organización.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

En este ejemplo se devuelve información detallada de la directiva de cifrado de datos denominada "NAM Policy".

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

Descripción: este cmdlet enumera la directiva asignada actualmente al inquilino.

## <a name="offboarding-from-customer-key"></a>Salida de la clave de cliente

Si necesita volver a las claves administradas por Microsoft, puede hacerlo. Al quitar la carga de trabajo, los datos se cifran de nuevo mediante el cifrado predeterminado admitido por cada carga de trabajo individual. Por ejemplo, Exchange Online admite el cifrado predeterminado mediante claves administradas por Microsoft.

Si decidió retirar su inquilino de la clave de cliente en el nivel de inquilino, puede comunicarse con Microsoft con una solicitud por correo electrónico para "deshabilitar" el servicio para el inquilino en [m365ck@microsoft.com](mailto:m365ck@microsoft.com).

> [!IMPORTANT]
> La eliminación no es lo mismo que una purga de datos. Una purga de datos criptográficos elimina permanentemente los datos de su organización de Microsoft 365, no lo hace la eliminación. No puede realizar una purga de datos para una directiva de nivel de inquilino. Para obtener información acerca de la ruta de depuración de datos, vea [Revocar las claves e iniciar el proceso de ruta de depuración de datos.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

## <a name="about-the-availability-key"></a>Acerca de la clave de disponibilidad

Para obtener información acerca de la clave de disponibilidad, [vea Más información sobre la clave de disponibilidad.](customer-key-availability-key-understand.md)

## <a name="key-rotation"></a>Rotación de teclas

Para obtener información sobre la rotación o la rotación de claves usadas con la clave de cliente, vea Roll [o rotate a Customer Key or an availability key](customer-key-availability-key-roll.md). Cuando actualice el DEP para que use la nueva versión de las claves, ejecutará el cmdlet Set-M365DataAtRestEncryptionPolicy como se describió anteriormente en este artículo.

## <a name="related-articles"></a>Artículos relacionados:

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Cifrado de servicio](office-365-service-encryption.md)
