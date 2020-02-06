---
title: Configurar la clave de cliente de Office 365
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
description: Obtenga información sobre cómo configurar la clave de cliente de Office 365 para Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y archivos de Microsoft Teams.
ms.openlocfilehash: a57fb5ee7eea1746a50ec0fb1e2c3e84495b4f2c
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804871"
---
# <a name="set-up-customer-key-for-office-365"></a>Configurar la clave de cliente de Office 365

Con la clave de cliente, puede controlar las claves de cifrado de la organización y, después, configurar Office 365 para usarlas y cifrar los datos en reposo en los centros de datos de Microsoft. Es decir, la clave de cliente permite a los clientes agregar una capa de cifrado que les pertenece, con sus claves. Los datos en reposo incluyen datos de Exchange Online y Skype Empresarial que se almacenan en buzones y archivos en SharePoint Online y OneDrive para la Empresa.

Debe configurar Azure antes de poder usar la clave de cliente de Office 365. En este tema se describen los pasos que debe seguir para crear y configurar los recursos necesarios de Azure y, a continuación, se proporcionan los pasos para configurar la clave de cliente en Office 365. Una vez completada la configuración de Azure, determine qué directivas y, por lo tanto, qué claves asignar a los buzones de correo y los archivos de su organización. Los buzones de correo y los archivos para los que no se asigna una directiva usarán directivas de cifrado controladas y administradas por Microsoft. Para obtener más información acerca de la clave de cliente o para obtener información general, consulte [Service Encryption with Customer key in Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> Se recomienda encarecidamente seguir los procedimientos recomendados de este tema. Se les llama como **Tip** e **Important**. La clave de cliente le da control sobre las claves de cifrado raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que los errores realizados con estas claves pueden tener un gran impacto y pueden dar lugar a interrupciones en el servicio o la pérdida irrevocable de los datos.
  
## <a name="before-you-set-up-customer-key"></a>Antes de configurar la clave de cliente

Antes de empezar, asegúrese de que dispone de la licencia adecuada para su organización. La clave de cliente en Office 365 se ofrece en Office 365 E5 o en la SKU de cumplimiento avanzada. Para comprender los conceptos y procedimientos de este tema, revise la documentación de [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) . Además, familiarícese con los términos que se usan en Azure, por ejemplo, [tenant](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)).

FastTrack solo se usa para recopilar la información de configuración de servicio y el inquilino necesario que se usa para registrar la clave de cliente. Las ofertas de clave de cliente se publican a través de FastTrack para que sea conveniente para usted y para nuestros partners enviar la información necesaria con el mismo método. FastTrack también facilita el archivado de los datos facilitados en la oferta.
  
Si necesita más información sobre la documentación, póngase en contacto con los servicios de consultoría de Microsoft (MCS), el servicio de ingeniería de campo (PFE) de Premier o un socio de Microsoft para obtener ayuda. Para proporcionar comentarios sobre la clave de cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Información general sobre los pasos para configurar la clave de cliente

Para configurar la clave de cliente, complete estas tareas en el orden indicado. En el resto de este artículo se proporcionan instrucciones detalladas para cada tarea o vínculos a más información para cada paso del proceso.
  
**En Azure y Microsoft FastTrack:**
  
Completará la mayoría de estas tareas conectándose de forma remota a Azure PowerShell. Para obtener los mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.
  
- [Crear dos nuevas suscripciones de Azure](#create-two-new-azure-subscriptions)

- [Registrar suscripciones de Azure para usar un período de retención obligatorio](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  El registro puede tardar de uno a cinco días hábiles.

- [Enviar una solicitud para activar la clave de cliente de Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Una vez que haya creado las dos nuevas suscripciones de Azure, deberá enviar la solicitud de oferta de la clave de cliente correspondiente completando un formulario web hospedado en el portal de Microsoft FastTrack. **El equipo de FastTrack no proporciona asistencia con la clave de cliente. Office simplemente usa el portal de FastTrack para permitirle enviar el formulario y ayudar a hacer un seguimiento de las ofertas relevantes para la clave de cliente**.

- [Crear un almacén de claves Premium de Azure en cada suscripción](#create-a-premium-azure-key-vault-in-each-subscription)

- [Asignar permisos a cada almacén clave](#assign-permissions-to-each-key-vault)

- [Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Agregar una clave a cada depósito clave creando o importando una clave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Comprobar el nivel de recuperación de las claves](#check-the-recovery-level-of-your-keys)

- [Copia de seguridad de Azure Key Vault](#back-up-azure-key-vault)

- [Validar las opciones de configuración de Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Obtener el URI para cada clave de Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)

**En Office 365:**
  
Exchange Online y Skype empresarial:
  
- [Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype empresarial](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Asignar una DEP a un buzón](#assign-a-dep-to-a-mailbox)

- [Validar el cifrado de buzones](#validate-mailbox-encryption)

SharePoint Online y OneDrive para la empresa:
  
- [Crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Validar el cifrado de archivos para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completar las tareas en Azure Key Vault y Microsoft FastTrack para la clave de cliente

Complete estas tareas en Azure Key Vault. Deberá completar estos pasos independientemente de si desea configurar la clave de cliente para los archivos de Exchange Online y Skype empresarial o para SharePoint Online, OneDrive para la empresa y Teams, o para todos los servicios admitidos en Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure

La clave de cliente requiere dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda crear nuevas suscripciones de Azure para usarlas con la clave de cliente. Las claves de Azure Key Vault solo se pueden autorizar para aplicaciones en el mismo inquilino de Azure Active Directory (AAD), debe crear las nuevas suscripciones con el mismo inquilino de Azure AD que se usa con la organización de Office 365 donde se asignará la DEPs. Por ejemplo, con su cuenta profesional o educativa con privilegios de administrador global en su organización de Office 365. Para obtener los pasos detallados, consulte [registrarse para Azure como organización](https://azure.microsoft.com/documentation/articles/sign-up-organization/).
  
> [!IMPORTANT]
> La clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como procedimiento recomendado, Microsoft recomienda que los miembros de la organización se configuren como una clave en cada suscripción. Además, estas suscripciones de Azure solo deben usarse para administrar claves de cifrado para Office 365. Esto protege a su organización en caso de que uno de sus operadores elimine accidentalmente, de forma intencionada, o de una mala administración de las claves de las que es responsable. <br/> Le recomendamos que configure nuevas suscripciones de Azure que solo se usan para administrar recursos de Azure Key Vault para usarlas con la clave de cliente. No hay ningún límite práctico en el número de suscripciones de Azure que puede crear para su organización. Siga estos procedimientos recomendados para minimizar el impacto de los errores humanos mientras ayuda a administrar los recursos usados por la clave de cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar una solicitud para activar la clave de cliente de Office 365

Una vez que haya completado los pasos de Azure, tendrá que enviar una solicitud de oferta en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Una vez que haya enviado una solicitud a través del portal web FastTrack, Microsoft comprueba los datos de configuración de Azure Key Vault y la información de contacto que ha proporcionado. Las selecciones que realice en el formulario de oferta en relación con los agentes autorizados de su organización son críticas y necesarias para completar el registro de la clave de cliente. Los agentes de la organización que seleccione en el formulario se usarán para garantizar la autenticidad de cualquier solicitud de revocar y destruir todas las claves utilizadas con una directiva de clave de cifrado de datos de cliente. Deberá realizar este paso una vez para activar la cobertura del cliente para la cobertura de Exchange Online y Skype empresarial, y una segunda vez para activar la clave de cliente de SharePoint Online y OneDrive para la empresa.
  
Para enviar una oferta para activar la clave de cliente, siga estos pasos:
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).

2. Una vez que haya iniciado sesión, vaya al **Panel**.

3. Elija **ofertas**y revise la lista de ofertas actuales.

4. Elija más **información** para la oferta que se le aplique:

   - **Exchange Online y Skype empresarial:** Elija más **información** en la **clave de cliente de la oferta de Exchange** .

   - **Archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams:** Elija más **información** sobre la oferta de **clave de cliente para SharePoint y OneDrive para la empresa** .

5. En la página Detalles de la **oferta** , elija **crear solicitud**.

6. Rellene todos los detalles aplicables y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones de los funcionarios de su organización a los que desea conceder autorización para aprobar la destrucción permanente e irreversible de claves de cifrado y datos. Una vez que haya completado el formulario, elija **Enviar**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar suscripciones de Azure para usar un período de retención obligatorio

La pérdida temporal o permanente de las claves de cifrado raíz puede ser muy disruptiva o incluso catastróficas para el funcionamiento del servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección segura. Todos los recursos de Azure que se usan con la clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Las suscripciones de Azure se pueden etiquetar o registrar de manera que se evite la cancelación inmediata y irrevocable. Esto se conoce como registro de un período de retención obligatorio. Los pasos necesarios para registrar las suscripciones de Azure durante un período de retención obligatorio requieren la colaboración con el equipo de Office 365. Este proceso puede tardar de uno a cinco días laborables. Anteriormente, a veces se hacía referencia a esto como "no cancelar".
  
Antes de ponerse en contacto con el equipo de Office 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente. Asegúrese de que tiene instalado el módulo de Azure PowerShell AZ antes de continuar (https://docs.microsoft.com/powershell/azure/new-azureps-module-az.
  
1. Inicie sesión con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Register-AzProviderFeature para registrar sus suscripciones para usar un período de retención obligatorio. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

3. Póngase en contacto con Microsoft para finalizar el proceso. Para el equipo de SharePoint y OneDrive para la empresa, póngase en contacto con [Spock@microsoft.com](mailto:spock@microsoft.com). Para Exchange Online y Skype empresarial, póngase en contacto con [exock@microsoft.com](mailto:exock@microsoft.com). Incluya lo siguiente en su correo electrónico:

   **Asunto**: clave del cliente \<para *el nombre de dominio completo del espacio empresarial*\>

   **Cuerpo**: identificadores de suscripción para los que desea finalizar el período de retención obligatorio.
   El resultado de Get-AzProviderFeature para cada suscripción.

   El contrato de nivel de servicio (SLA) para completar este proceso es cinco días hábiles después de que Microsoft haya notificado (y comprobado) que ha registrado sus suscripciones para usar un período de retención obligatorio.

4. Una vez que reciba la notificación de Microsoft de que se ha completado el registro, compruebe el estado del registro ejecutando el cmdlet Get-AzProviderFeature de la siguiente manera. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Después de comprobar que la propiedad de **Estado de registro** del cmdlet Get-AzProviderFeature devuelve un valor de **registrado**, ejecute el siguiente comando para completar el proceso. Realice esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace "Microsoft.KeyVault"
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Crear un almacén de claves Premium de Azure en cada suscripción

Los pasos para crear un almacén de claves se documentan en [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), que le guiará a través de la instalación y el inicio de Azure PowerShell, la conexión a su suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese grupo de recursos.
  
Al crear un almacén de claves, debe elegir una SKU: estándar o Premium. La SKU estándar permite que las claves de Azure Key Vault estén protegidas con software (no hay protección de clave de módulo de seguridad de hardware (HSM) y la SKU Premium permite usar los HSM para proteger las claves de la bóveda clave. La clave de cliente acepta almacenes clave que usan una SKU, pero Microsoft recomienda encarecidamente usar solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia de costo es el costo cada mes para cada clave protegida por HSM. Consulte [tarifas clave](https://azure.microsoft.com/pricing/details/key-vault/) de la bóveda para obtener más información.
  
> [!IMPORTANT]
> Use los almacenes clave de SKU Premium y las claves protegidas por HSM para los datos de producción y use únicamente las claves y los almacenes de claves de SKU estándar para fines de prueba y validación.
  
Para cada servicio de Office 365 con el que va a usar la clave de cliente, cree un almacén de claves en cada una de las dos suscripciones de Azure que ha creado. Por ejemplo, solo para Exchange Online y Skype empresarial, o SharePoint Online y OneDrive para la empresa, solo se creará un par de depósitos. Para habilitar la clave de cliente para Exchange Online y SharePoint Online, deberá crear dos pares de depósitos clave.
  
Use una Convención de nomenclatura para los depósitos clave que refleje el uso previsto de la Directiva de cifrado de datos con la que va a asociar los almacenes. Consulte la sección procedimientos recomendados a continuación para conocer las recomendaciones de Convención de nomenclatura.
  
Cree un conjunto independiente y emparejado de depósitos para cada directiva de cifrado de datos. Para Exchange Online, el ámbito de una directiva de cifrado de datos se elige cuando se asigna la Directiva al buzón. Un buzón puede tener solo una directiva asignada y puede crear hasta 50 directivas. Para SharePoint Online el ámbito de una Directiva son todos los datos de una organización en una ubicación geográfica o _geográfica_.

La creación de almacenes clave también requiere la creación de grupos de recursos de Azure, ya que las bóvedas clave necesitan capacidad de almacenamiento (aunque muy pequeña) y el registro de la bóveda clave, si está habilitado, también genera datos almacenados. Como procedimiento recomendado, Microsoft recomienda el uso de administradores independientes para administrar cada grupo de recursos, con la administración alineada con el conjunto de administradores que administrarán todos los recursos de clave de cliente relacionados.
  
> [!IMPORTANT]
> Para maximizar la disponibilidad, los depósitos clave deben estar en regiones próximos a su servicio de Office 365. Por ejemplo, si su organización de Exchange Online está en Norteamérica, ubique sus depósitos clave en Norteamérica. Si su organización de Exchange Online está en Europa, ubique los depósitos clave en Europa.<br/>Use un prefijo común para los depósitos clave e incluya una abreviatura del uso y el alcance de las claves y el almacén de claves (por ejemplo, para el servicio de SharePoint de Contoso donde los almacenes se ubicarán en Norteamérica, un posible par de nombres es contoso-O365SP-NA-VaultA1 y Contoso-O365SP-NA-VaultA2. Los nombres de almacén son cadenas únicas de forma global dentro de Azure, por lo que es posible que deba probar variantes de sus nombres deseados en caso de que otros clientes de Azure ya hayan reclamado los nombres deseados. A partir de julio 2017 los nombres de almacén no se pueden cambiar, por lo que un procedimiento recomendado es tener un plan escrito para la configuración y usar una segunda persona para comprobar que el plan se ejecuta correctamente.<br/>Si es posible, cree sus depósitos en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad en todos los dominios de error de servicio. Por lo tanto, los pares regionales pueden considerarse como una región de copia de seguridad de cada uno. Esto significa que un recurso de Azure que se coloca en una región está obteniendo automáticamente la tolerancia a errores a través de la región emparejada. Por este motivo, la elección de regiones para dos almacenes usados en una directiva de cifrado de datos en la que las regiones están emparejadas significa que solo se usa un total de dos regiones de disponibilidad. La mayoría de las zonas geográficas solo tienen dos regiones, por lo que todavía no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para las dos Vaults que se usan con una directiva de cifrado de datos. Esto beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, vea [continuidad empresarial y recuperación ante desastres (BCDR): regiones emparejadas de Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) para obtener una lista actual de pares regionales.
  
### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada almacén clave

Para cada almacén de claves, tendrá que definir tres conjuntos de permisos distintos para la clave de cliente, según la implementación. Por ejemplo, tendrá que definir un conjunto de permisos para cada uno de los siguientes elementos:
  
- **Administradores de la bóveda clave** que realizarán la administración cotidiana de su almacén clave para su organización. Estas tareas incluyen copia de seguridad, crear, obtener, importar, enumerar y restaurar.

  > [!IMPORTANT]
  > El conjunto de permisos asignado a los administradores de la bóveda de claves no incluye el permiso para eliminar claves. Esto es intencionado y es un ejercicio importante. La eliminación de claves de cifrado no suele realizarse, ya que al hacerlo se destruyen los datos de forma permanente. Como procedimiento recomendado, no conceda este permiso a los administradores de la bóveda clave de forma predeterminada. En su lugar, Reserve esto para los colaboradores clave de la bóveda y asígnelo solo a un administrador a corto plazo una vez que comprenda claramente las consecuencias.
  
  Para asignar estos permisos a un usuario de su organización de Office 365, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [iniciar sesión con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

- Ejecute el cmdlet Set-AzKeyVaultAccessPolicy para asignar los permisos necesarios.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por ejemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Contribute de Key Vault** que puede cambiar los permisos en el propio almacén de claves de Azure. Tendrá que cambiar estos permisos a medida que los empleados abandonen o se unan a su equipo, o en la situación extremadamente inusual de que los administradores de la bóveda clave necesiten de forma legítima permiso para eliminar o restaurar una clave. Este conjunto de colaboradores clave del almacén debe tener concedido el rol **colaborador** en su almacén de claves. Puede asignar este rol mediante el administrador de recursos de Azure. Para obtener los pasos detallados, consulte [usar el control de acceso basado en roles para administrar el acceso a los recursos de suscripción de Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). El administrador que crea una suscripción tiene este acceso de forma implícita, así como la capacidad de asignar otros administradores al rol colaborador.

- Si tiene previsto usar la clave de cliente con Exchange Online y Skype empresarial, debe conceder permiso a Office 365 para usar el almacén de claves en nombre de Exchange Online y Skype empresarial. Del mismo modo, si tiene previsto usar la clave de cliente con SharePoint Online y OneDrive para la empresa, necesitará agregar el permiso para que la oficina 365 use el almacén de claves en nombre de SharePoint Online y OneDrive para la empresa. Para conceder permiso a Office 365, ejecute el cmdlet **set-AzKeyVaultAccessPolicy** con la siguiente sintaxis: 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Donde:

    - el *nombre del almacén* es el nombre del almacén de claves que ha creado.

    - Para Exchange Online y Skype empresarial, reemplace *Office 365 appID* por`00000002-0000-0ff1-ce00-000000000000`

    - Para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, reemplace *Office 365 appID* por`00000003-0000-0ff1-ce00-000000000000`

  Ejemplo: establecer permisos para Exchange Online y Skype empresarial:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Ejemplo: establecer permisos para los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación de software en los depósitos clave

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio prolongada debido a claves eliminadas accidental o malintencionadamente. Debe habilitar esta configuración, que se conoce como eliminación temporal, para poder usar las claves con la clave de cliente. La habilitación de la eliminación temporal permite recuperar claves o depósitos en un plazo de 90 días de eliminación sin tener que restaurarlos a partir de la copia de seguridad.
  
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

Hay dos formas de agregar claves a un almacén de claves de Azure; puede crear una clave directamente en el almacén de claves, o puede importar una clave. La creación de una clave directamente en el almacén de claves es el método menos complicado, mientras que la importación de una clave proporciona un control total sobre la forma en que se genera la clave.
  
Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) de la siguiente manera:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Donde:

- *nombre del almacén* es el nombre del almacén de clave en el que desea crear la clave.

- *nombre de clave* es el nombre que desea asignar a la nueva clave.

  > [!TIP]
  > Denomine claves con una Convención de nomenclatura similar, como se ha descrito anteriormente para los almacenes de claves. De este modo, en las herramientas que solo muestran el nombre de la clave, la cadena es autodescriptivo.
  
- Si piensa proteger la clave con un HSM, asegúrese de especificar **HSM** como el valor del parámetro _Destination_ ; de lo contrario, especifique el **software**.

For example,
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

Para importar una clave directamente en el almacén de claves, debe tener un módulo de seguridad de hardware de Thales nShield.
  
Algunas organizaciones prefieren este enfoque para establecer la procedencia de sus claves y este método también ofrece lo siguiente:
  
- El conjunto de herramientas usado para la importación incluye atestación de Thales de que la clave de intercambio de claves (KEK) que se usa para cifrar la clave que se genera no es exportable y se genera dentro de un HSM genuino fabricado por Thales.

- El conjunto de herramientas incluye la atestación de Thales que el mundo de seguridad de la clave de Azure Key Vault también se generó en un HSM auténtico fabricado por Thales. Esta atestación le demuestra que Microsoft también usa hardware de Thales genuino.

Consulte a su grupo de seguridad para determinar si se requieren las atestaciones anteriores. Para obtener instrucciones detalladas para crear una clave local e importarla en el almacén de claves, consulte [How to generate HSM-Protected Keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use las instrucciones de Azure para crear una clave en cada almacén de clave.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Comprobar el nivel de recuperación de las claves

Office 365 requiere que la suscripción de Azure Key Vault esté definida como no cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación temporal. Para confirmarlo, consulte el nivel de recuperación de las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzKeyVaultKey de la siguiente manera:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Si la propiedad _nivel de recuperación_ devuelve cualquier cosa que no sea un valor **recuperable + ProtectedSubscription**, tendrá que revisar este tema y asegurarse de que ha seguido todos los pasos necesarios para poner la suscripción en la lista no cancelar y que tiene habilitada la eliminación temporal en cada uno de los almacenes clave.
  
### <a name="back-up-azure-key-vault"></a>Copia de seguridad de Azure Key Vault

Inmediatamente después de la creación o de cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. Las copias sin conexión no deben estar conectadas a ninguna red, como en un servicio de almacenamiento comercial o seguro físico. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda tener acceso en caso de desastre. Los blobs de copia de seguridad son los únicos medios de restaurar el material clave en caso de que una clave de almacén clave se destruya de forma permanente o no pueda ser procesada de forma inservible. Las claves externas a Azure Key Vault y que se importaron a Azure Key Vault no se califican como una copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existe con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para las operaciones de restauración con la clave de cliente. Por lo tanto, es fundamental realizar una copia de seguridad del almacén de claves de Azure una vez que se haya cargado o creado una clave.
  
Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) de la siguiente manera:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Asegúrese de que el archivo de salida Use `.backup`el sufijo.
  
El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar a la suscripción de Azure desde la que se realizó la copia de seguridad.
  
> [!TIP]
> Para el archivo de salida, elija una combinación del nombre de la caja fuerte y el nombre de la clave. Esto hará que el nombre de archivo se describa automáticamente. También se asegurará de que los nombres de archivo de copia de seguridad no entren en conflicto.
  
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

En el resultado, busque la Directiva de acceso y la identidad de Exchange Online (GUID) o la identidad de SharePoint Online (GUID) según corresponda. Los tres permisos anteriores deben mostrarse en permisos a claves.
  
Si la configuración de la Directiva de acceso no es correcta, ejecute el cmdlet Set-AzKeyVaultAccessPolicy de la siguiente manera:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por ejemplo, para Exchange Online y Skype empresarial:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por ejemplo, para SharePoint Online y OneDrive para la empresa:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

La clave de cliente no puede usar una clave expirada y las operaciones que se intentan con una clave expirada fallarán y, posiblemente, se producirá una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha distinta. Si se debe usar una clave que tenga establecida una fecha de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha distinta a 12/31/9999 no pasarán la validación de Office 365.
  
Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto de 12/31/9999, ejecute el cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) de la siguiente manera:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> No establezca fechas de expiración en las claves de cifrado que use con la clave de cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el URI para cada clave de Azure Key Vault

Una vez que haya completado todos los pasos de Azure para configurar los almacenes clave y haya agregado las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de clave. Tendrá que usar estos URI cuando cree y asigne cada DEP más adelante, por lo que debe guardar esta información en un lugar seguro. Recuerde ejecutar este comando una vez para cada almacén de clave.
  
En Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: configuración de la clave de cliente para Exchange Online y Skype empresarial

Antes de empezar, asegúrese de haber completado las tareas necesarias para configurar el almacén de claves de Azure. Vea la [clave de cliente completar tareas en Azure Key Vault y Microsoft FastTrack](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) para obtener información.
  
Para configurar la clave de cliente de Exchange Online y Skype empresarial, tendrá que realizar estos pasos conectándose de forma remota a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype empresarial

Un DEP está asociado a un conjunto de claves almacenadas en Azure Key Vault. Asigne un DEP a un buzón de correo en Office 365. Office 365 usará entonces las claves identificadas en la Directiva para cifrar el buzón. Para crear la DEP, necesita los URI de la bóveda de clave que obtuvo antes. Consulte [obtener el URI de cada clave de Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key) para obtener instrucciones.
  
Recuerde! Cuando se crea un DEP, se especifican dos claves que residen en dos depósitos de clave de Azure diferentes. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear la DEP, siga estos pasos:
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) abriendo Windows PowerShell y ejecutando el siguiente comando.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. En el cuadro de diálogo solicitud de credenciales para Windows PowerShell, escriba la información de su cuenta profesional o educativa, haga clic en **Aceptar**y, a continuación, escriba el siguiente comando.

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. Ejecute el comando siguiente.

   ```powershell
   Import-PSSession $Session
   ```

4. Para crear un DEP, use el cmdlet New-DataEncryptionPolicy; para ello, escriba el siguiente comando.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Donde:

   - *PolicyName* es el nombre que desea usar para la Directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes.

   - La descripción de la *Directiva* es una descripción de la Directiva que le ayudará a recordar qué es la Directiva. Puede incluir espacios en la descripción. Por ejemplo, "clave raíz para buzones de correo en Estados Unidos y sus zonas de ventas".

   - *KeyVaultURI1* es el URI para la primera clave de la Directiva. Por ejemplo, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.

   - *KeyVaultURI2* es el URI de la segunda clave de la Directiva. Por ejemplo, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separe los dos URI por una coma y un espacio.

   Ejemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>Asignar una DEP a un buzón

Asigne la DEP a un buzón mediante el cmdlet Set-Mailbox. Una vez asignada la Directiva, Office 365 puede cifrar el buzón con la clave designada en la DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailboxIdParameter* especifica un buzón. Para obtener más información acerca del cmdlet Set-Mailbox, consulte [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).
  
### <a name="validate-mailbox-encryption"></a>Validar el cifrado de buzones

El cifrado de un buzón puede tardar algún tiempo. Para la asignación de directivas primera vez, el buzón también debe moverse completamente de una base de datos a otra antes de que el servicio pueda cifrar el buzón. Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar una DEP o la primera vez que asigna un DEP a un buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor **true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado.

El tiempo para completar los movimientos de buzones depende del número de buzones a los que se asigna la DEP por primera vez, así como del tamaño de los buzones. Si los buzones no se han cifrado después de una semana desde el momento en que asignó la DEP, póngase en contacto con Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: configuración de la clave de cliente para SharePoint Online, OneDrive para la empresa y archivos de Microsoft Teams

Antes de empezar, asegúrese de haber completado las tareas necesarias para configurar el almacén de claves de Azure. Vea la [clave de cliente completar tareas en Azure Key Vault y Microsoft FastTrack](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) para obtener información.
  
Para configurar la clave de cliente para SharePoint Online, OneDrive para la empresa y los archivos de Teams, debe realizar estos pasos conectándose de forma remota a SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Crear una directiva de cifrado de datos (DEP) para cada geográfico de SharePoint Online y OneDrive para la empresa

Asocia un DEP con un conjunto de claves almacenadas en Azure Key Vault. Se aplica una DEP a todos los datos en una ubicación geográfica, también denominada geo. Si usa la característica multigeográfica de Office 365, puede crear un DEP por geográfico con la capacidad de usar diferentes claves por geográfico. Si no usa multigeográfico, puede crear un DEP en la organización de Office 365 para usarlo con los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams. Office 365 usa las claves identificadas en el DEP para cifrar los datos en esa geografía. Para crear la DEP, necesita los URI de la bóveda de clave que obtuvo antes. Consulte [obtener el URI de cada clave de Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key) para obtener instrucciones.
  
Recuerde! Cuando se crea un DEP, se especifican dos claves que residen en dos depósitos de clave de Azure diferentes. Asegúrese de que estas claves se encuentran en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.
  
1. En el equipo local, con una cuenta profesional o educativa que tenga permisos de administrador global en su organización de Office 365, [Conéctese a SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

2. En el shell de administración de Microsoft SharePoint Online, ejecute el cmdlet Register-SPODataEncryptionPolicy de la siguiente manera:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Cuando registra el DEP, el cifrado comienza en los datos de la geografía. Esto puede tardar algún tiempo.

### <a name="validate-file-encryption"></a>Validar el cifrado de archivos

 Para validar el cifrado de los archivos de SharePoint Online, OneDrive para la empresa y Microsoft Teams, [Conéctese a SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)y, a continuación, use el cmdlet Get-SPODataEncryptionPolicy para comprobar el estado del espacio empresarial. La propiedad _State_ devuelve un valor de **registrado** si el cifrado de clave de cliente está habilitado y todos los archivos de todos los sitios se han cifrado. Si el cifrado todavía está en curso, este cmdlet proporciona información sobre el porcentaje de sitios que se ha completado.

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicios con clave de cliente de Office 365](customer-key-overview.md)

- [Administrar la clave de cliente de Office 365](customer-key-manage.md)

- [Rollo o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Obtener información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Cifrado de servicio de Office 365](office-365-service-encryption.md)
