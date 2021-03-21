---
title: Configurar clave de cliente en el nivel de aplicación
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
description: Obtenga información sobre cómo configurar la clave de cliente para archivos de Microsoft 365 para Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams.
ms.openlocfilehash: a7a0c807b8778960d423d6b7d8afc20430ba89ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922724"
---
# <a name="set-up-customer-key-at-the-application-level"></a>Configurar clave de cliente en el nivel de aplicación

Con clave de cliente, controla las claves de cifrado de su organización y, a continuación, configura Microsoft 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft. En otras palabras, la clave de cliente permite a los clientes agregar una capa de cifrado que les pertenece, con sus claves. Los datos en reposo incluyen datos de Exchange Online y Skype Empresarial que se almacenan en buzones y archivos en SharePoint Online y OneDrive para la Empresa.

Debe configurar Azure para poder usar la clave de cliente para Office 365. En este artículo se describen los pasos que debe seguir para crear y configurar los recursos de Azure necesarios y, a continuación, proporciona los pasos para configurar la clave de cliente en Office 365. Después de completar la instalación de Azure, determina qué directiva y, por lo tanto, qué claves asignar a buzones y archivos de la organización. Los buzones y archivos a los que no asigne una directiva usarán directivas de cifrado controladas y administradas por Microsoft. Para obtener más información acerca de la clave de cliente o para obtener información general, vea Cifrado de servicio con clave de cliente [en Office 365](customer-key-overview.md).
  
> [!IMPORTANT]
> Le recomendamos encarecidamente que siga los procedimientos recomendados de este artículo. Estos se denominan **TIP** e **IMPORTANT**. Clave de cliente le proporciona control sobre las claves de cifrado raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que los errores que se cometen con estas claves pueden tener un impacto general y pueden provocar interrupciones del servicio o pérdida irrevocable de los datos.
  
## <a name="before-you-set-up-customer-key"></a>Antes de configurar la clave de cliente

Antes de empezar, asegúrese de que tiene las licencias adecuadas para su organización. Use una suscripción de Azure de pago facturada con un Contrato Enterprise o un proveedor de servicios en la nube. Las suscripciones de Azure compradas con planes de pago o con una tarjeta de crédito no son compatibles con la clave de cliente. A partir del 1 de abril de 2020, la clave de cliente en Office 365 se ofrece en Office 365 E5, M365 E5, M365 E5 Compliance y M365 E5 Information Protection & Governance SKU. La SKU de cumplimiento avanzado de Office 365 ya no está disponible para adquirir nuevas licencias. Las licencias de cumplimiento avanzado de Office 365 existentes seguirán siendo compatibles.

Para comprender los conceptos y procedimientos de este artículo, revise la [documentación de Azure Key Vault.](/azure/key-vault/) Además, familiarícese con los términos usados en Azure, por ejemplo, [inquilino de Azure AD](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).

FastTrack solo se usa para recopilar la información de configuración de inquilino y servicio necesaria que se usa para registrar la clave de cliente. Las ofertas de clave de cliente se publican a través de FastTrack para que sea conveniente que usted y nuestros partners envíen la información necesaria con el mismo método. FastTrack también facilita el archivo de los datos que proporciona en la oferta.
  
Si necesita más soporte más allá de la documentación, póngase en contacto con Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) o un partner de Microsoft para obtener ayuda. Para proporcionar comentarios sobre la clave de cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Introducción a los pasos para configurar la clave de cliente

Para configurar la clave de cliente, complete estas tareas en el orden indicado. El resto de este artículo proporciona instrucciones detalladas para cada tarea o vínculos a más información para cada paso del proceso.
  
**En Azure y Microsoft FastTrack:**
  
Para completar la mayoría de estas tareas, conéctese de forma remota a Azure PowerShell. Para obtener los mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.
  
- [Crear dos nuevas suscripciones de Azure](#create-two-new-azure-subscriptions)

- [Registrar suscripciones de Azure para usar un período de retención obligatorio](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  El registro puede tardar de uno a cinco días laborables.

- [Enviar una solicitud para activar la clave de cliente para Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

Una vez creadas las dos nuevas suscripciones de Azure, deberá enviar la solicitud de oferta de clave de cliente adecuada completando un formulario web hospedado en el portal de Microsoft FastTrack. **El equipo de FastTrack no proporciona asistencia con la clave de cliente. Office simplemente usa el portal de FastTrack** para permitirle enviar el formulario y ayudarnos a realizar un seguimiento de las ofertas relevantes para la clave de cliente.

- [Crear un Almacén de claves de Azure premium en cada suscripción](#create-a-premium-azure-key-vault-in-each-subscription)

- [Asignar permisos a cada almacén de claves](#assign-permissions-to-each-key-vault)

- [Habilitar y, a continuación, confirmar la eliminación suave en los almacenes de claves](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Agregar una clave a cada almacén de claves mediante la creación o importación de una clave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Comprobar el nivel de recuperación de las claves](#check-the-recovery-level-of-your-keys)

- [Copia de seguridad de Azure Key Vault](#back-up-azure-key-vault)

- [Validar las opciones de configuración de Azure Key Vault](#validate-azure-key-vault-configuration-settings)

- [Obtener el URI de cada clave de Azure Key Vault](#obtain-the-uri-for-each-azure-key-vault-key)

**En Office 365:**
  
Exchange Online y Skype Empresarial:
  
- [Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype Empresarial](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Asignar un DEP a un buzón](#assign-a-dep-to-a-mailbox)

- [Validar el cifrado de buzones](#validate-mailbox-encryption)

SharePoint Online y OneDrive para la Empresa:
  
- [Crear una directiva de cifrado de datos (DEP) para cada geo de SharePoint Online y OneDrive para la Empresa](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Validar el cifrado de archivos para archivos de SharePoint Online, OneDrive para la Empresa y Teams](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completar tareas en Azure Key Vault y Microsoft FastTrack para clave de cliente

Complete estas tareas en Azure Key Vault. Deberá completar estos pasos independientemente de si tiene la intención de configurar la clave de cliente para Exchange Online y Skype Empresarial o para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, o para todos los servicios admitidos en Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Crear dos nuevas suscripciones de Azure

La clave de cliente requiere dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda crear nuevas suscripciones de Azure para usarlas con la clave de cliente. Las claves de Azure Key Vault solo pueden autorizarse para aplicaciones en el mismo inquilino de Azure Active Directory (Microsoft Azure Active Directory), debe crear las nuevas suscripciones con el mismo inquilino de Azure AD usado con su organización donde se asignarán los DEP. Por ejemplo, usar su cuenta profesional o educativa que tenga privilegios de administrador global en su organización. Para obtener pasos detallados, consulte [Registrarse en Azure como organización.](/azure/active-directory/fundamentals/sign-up-organization)
  
> [!IMPORTANT]
> Clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como práctica recomendada, Microsoft recomienda que los miembros independientes de la organización configuren una clave en cada suscripción. Solo debe usar estas suscripciones de Azure para administrar claves de cifrado para Office 365. Esto protege a la organización en caso de que uno de los operadores elimine accidentalmente, intencionada o malintencionadamente las claves de las que son responsables.
>

No hay ningún límite práctico en el número de suscripciones de Azure que puede crear para su organización. Seguir estos procedimientos recomendados minimizará el impacto del error humano y ayudará a administrar los recursos usados por la clave de cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar una solicitud para activar la clave de cliente para Office 365

Una vez completados los pasos de Azure, deberá enviar una solicitud de oferta en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Una vez que haya enviado una solicitud a través del portal web de FastTrack, Microsoft comprueba los datos de configuración de Azure Key Vault y la información de contacto que proporcionó. Las selecciones que realice en el formulario de oferta sobre los responsables autorizados de su organización son fundamentales y necesarias para completar el registro de clave de cliente. Los responsables de su organización garantizan la autenticidad de cualquier solicitud para revocar y destruir todas las claves usadas con una directiva de cifrado de datos de clave de cliente. Deberá realizar este paso una vez para activar la clave de cliente para la cobertura de Exchange Online y Skype Empresarial y una segunda vez para activar la clave de cliente para SharePoint Online y OneDrive para la Empresa.
  
Para enviar una oferta para activar la clave de cliente, siga estos pasos:
  
1. Con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).

2. Una vez que haya iniciado sesión, vaya al **Panel**.

3. Elija **Implementar** en la barra de navegación **O seleccione** **Ver** todos los recursos de implementación en la **tarjeta** de información Implementar y revise la lista de ofertas actuales.

4. Elija la tarjeta de información de la oferta que se aplica a usted:

   - **Exchange Online y Skype Empresarial:** Elija la **ayuda de clave de cifrado de solicitud para la oferta de Exchange** Online.

   - **Archivos de SharePoint Online, OneDrive y Teams:** Elija la **ayuda de la clave de cifrado de solicitud para Sharepoint y la oferta de OneDrive.**

5. Una vez que haya revisado los detalles de la oferta, elija **Continuar al paso 2**.

6. Rellene todos los detalles aplicables y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones para las que los responsables de su organización desea autorizar para aprobar la destrucción permanente e irreversible de claves y datos de cifrado. Una vez completado el formulario, elija **Enviar**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrar suscripciones de Azure para usar un período de retención obligatorio

La pérdida temporal o permanente de claves de cifrado raíz puede ser perjudicial o incluso catastrófica para la operación del servicio y puede provocar la pérdida de datos. Por este motivo, los recursos usados con la clave de cliente requieren una protección sólida. Todos los recursos de Azure que se usan con clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Puede etiquetar o registrar suscripciones de Azure durante *un período de retención obligatorio.* Un período de retención obligatorio impide la cancelación inmediata e irrevocable de la suscripción de Azure. Los pasos necesarios para registrar suscripciones de Azure durante un período de retención obligatorio requieren colaboración con el equipo de Microsoft 365. Este proceso puede tardar de uno a cinco días laborables. Anteriormente, el período de retención obligatorio a veces se denominaba "No cancelar".
  
Antes de ponerse en contacto con el equipo de Microsoft 365, debe realizar los siguientes pasos para cada suscripción de Azure que use con la clave de cliente. Asegúrese de que tiene instalado el módulo [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) antes de empezar.
  
1. Inicie sesión con Azure PowerShell. Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Register-AzProviderFeature para registrar las suscripciones para usar un período de retención obligatorio. Complete esta acción para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Póngase en contacto con Microsoft para completar el proceso. Para el equipo de SharePoint y OneDrive para la Empresa, póngase en [contacto con spock@microsoft.com](mailto:spock@microsoft.com). Para Exchange Online y Skype Empresarial, póngase en [contacto con exock@microsoft.com](mailto:exock@microsoft.com). Incluya la siguiente información en su correo electrónico:

   **Asunto**: Clave de cliente para \<*Your tenant's fully qualified domain name*\>

   **Cuerpo:** incluya los identificadores de suscripción para los que desea completar el período de retención obligatorio y el resultado de Get-AzProviderFeature para cada suscripción.

   El Contrato de nivel de servicio (SLA) para la finalización de este proceso es de cinco días laborables después de que Microsoft haya sido notificado (y comprobado) de que ha registrado sus suscripciones para usar un período de retención obligatorio.

4. Una vez que reciba la notificación de Microsoft de que el registro se ha completado, compruebe el estado del registro ejecutando el Get-AzProviderFeature siguiente. Si se comprueba, Get-AzProviderFeature comando devuelve un valor **de Registered** para la propiedad **Registration State.** Complete este paso para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Para completar el proceso, ejecute el Register-AzResourceProvider comando. Complete este paso para cada suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Crear un Almacén de claves de Azure premium en cada suscripción

Los pasos para crear un almacén de claves se documentan en Introducción a [Azure Key Vault,](/azure/key-vault/general/overview)que le guía a través de la instalación y el inicio de Azure PowerShell, la conexión a la suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese grupo de recursos.
  
Al crear un almacén de claves, debe elegir una SKU: Standard o Premium. La SKU estándar permite proteger las claves de Azure Key Vault con software (no hay protección de claves del Módulo de seguridad de hardware (HSM) y la SKU Premium permite el uso de HSM para proteger las claves de Key Vault. Clave de cliente acepta almacenes de claves que usan cualquiera de las SKU, aunque Microsoft recomienda encarecidamente que use solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia en el costo es el costo por mes de cada clave protegida por HSM. Consulta [Precios de Key Vault](https://azure.microsoft.com/pricing/details/key-vault/) para obtener más información.
  
> [!IMPORTANT]
> Use los almacenes de claves sku premium y las claves protegidas por HSM para los datos de producción y solo use las claves y almacenes de claves de SKU estándar con fines de prueba y validación.
  
Para cada servicio de Microsoft 365 con el que usará la clave de cliente, cree un almacén de claves en cada una de las dos suscripciones de Azure que creó. Por ejemplo, solo para Exchange Online y Skype Empresarial o SharePoint Online y OneDrive para la Empresa, solo creará un par de almacenes. Para habilitar la clave de cliente para Exchange Online y SharePoint Online, creará dos pares de almacenes de claves.
  
Use una convención de nomenclatura para almacenes de claves que refleje el uso previsto del DEP con el que asociará los almacenes. Vea la sección Procedimientos recomendados a continuación para obtener recomendaciones de convención de nomenclatura.
  
Cree un conjunto independiente y emparejado de almacenes para cada directiva de cifrado de datos. Para Exchange Online, el ámbito de una directiva de cifrado de datos lo elige cuando asigna la directiva al buzón. Un buzón solo puede tener asignada una directiva y puede crear hasta 50 directivas. El ámbito de una directiva de SharePoint Online incluye todos los datos de una organización en una ubicación geográfica o _geo_.

La creación de almacenes de claves también requiere la creación de grupos de recursos de Azure, ya que los almacenes de claves necesitan capacidad de almacenamiento (aunque pequeño) y el registro de Key Vault, si está habilitado, también genera datos almacenados. Como práctica recomendada, Microsoft recomienda usar administradores independientes para administrar cada grupo de recursos, con la administración alineada con el conjunto de administradores que administrarán todos los recursos relacionados con la clave de cliente.
  
> [!IMPORTANT]
> Para maximizar la disponibilidad, los almacenes de claves deben estar en regiones cercanas al servicio de Microsoft 365. Por ejemplo, si su organización de Exchange Online está en Norteamérica, coloque los almacenes de claves en Norteamérica. Si la organización de Exchange Online está en Europa, coloque los almacenes de claves en Europa.
> 
> Use un prefijo común para los almacenes de claves e incluya una abreviatura del uso y el ámbito del almacén de claves y las claves (por ejemplo, para el servicio de SharePoint contoso donde se ubicarán los almacenes en Norteamérica, un posible par de nombres es Contoso-O365SP-NA-VaultA1 y Contoso-O365SP-NA-VaultA2. Los nombres de almacén son cadenas únicas globalmente en Azure, por lo que es posible que deba probar las variaciones de los nombres deseados en caso de que otros clientes de Azure ya resonan los nombres deseados. A partir de julio de 2017 no se pueden cambiar los nombres de los almacenes, por lo que una práctica recomendada es tener un plan escrito para la configuración y usar una segunda persona para comprobar que el plan se ejecuta correctamente.
> 
> Si es posible, cree los almacenes en regiones no emparejadas. Las regiones de Azure emparejadas proporcionan alta disponibilidad entre dominios de error de servicio. Por lo tanto, los pares regionales se pueden pensar como la región de copia de seguridad del otro. Esto significa que un recurso de Azure que se coloca en una región obtiene automáticamente tolerancia a errores a través de la región emparejada. Por este motivo, elegir regiones para dos almacenes usados en una directiva de cifrado de datos en la que las regiones están emparejadas significa que solo se usa un total de dos regiones de disponibilidad. La mayoría de las zonas geográficas solo tienen dos regiones, por lo que aún no es posible seleccionar regiones no emparejadas. Si es posible, elija dos regiones no emparejadas para los dos almacenes usados con una directiva de cifrado de datos. Esto se beneficia de un total de cuatro regiones de disponibilidad. Para obtener más información, vea Continuidad empresarial y recuperación ante [desastres (BCDR): Regiones emparejadas](/azure/best-practices-availability-paired-regions) de Azure para obtener una lista actual de pares regionales.
  
### <a name="assign-permissions-to-each-key-vault"></a>Asignar permisos a cada almacén de claves

Deberá definir tres conjuntos de permisos independientes para cada almacén de claves, según la implementación. Por ejemplo, deberá definir un conjunto de permisos para cada una de las siguientes opciones:
  
- **Administradores del almacén de claves** que hacen la administración diaria del almacén de claves para su organización. Estas tareas incluyen copia de seguridad, crear, obtener, importar, enumerar y restaurar.

  > [!IMPORTANT]
  > El conjunto de permisos asignados a los administradores del almacén de claves no incluye el permiso para eliminar claves. Esto es intencionado y una práctica importante. Normalmente, la eliminación de claves de cifrado no se realiza, ya que al hacerlo se destruyen datos de forma permanente. Como procedimiento recomendado, no conceda este permiso a los administradores del almacén de claves de forma predeterminada. En su lugar, reserve esto para los colaboradores del almacén de claves y asígnelo solo a un administrador a corto plazo una vez que se comprenda claramente las consecuencias.
  
  Para asignar estos permisos a un usuario de la organización, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

- Ejecute el cmdlet Set-AzKeyVaultAccessPolicy para asignar los permisos necesarios.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por ejemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores del almacén de** claves que pueden cambiar los permisos en el propio Almacén de claves de Azure. Deberá cambiar estos permisos a medida que los empleados se vayan o se unan a su equipo. En la rara situación en la que los administradores del almacén de claves necesitan permiso para eliminar o restaurar una clave, también necesitará cambiar los permisos. Este conjunto de colaboradores del almacén de claves debe tener el rol **Colaborador** en el almacén de claves. Puede asignar este rol con Azure Resource Manager. Para obtener instrucciones detalladas, consulte Use Role-Based Access Control para administrar el acceso a los recursos de [suscripción de Azure.](/azure/active-directory/role-based-access-control-configure) El administrador que crea una suscripción tiene este acceso implícitamente y la capacidad de asignar otros administradores al rol Colaborador.

- Si tiene previsto usar la clave de cliente con Exchange Online y Skype Empresarial, debe conceder permiso a Microsoft 365 para usar el almacén de claves en nombre de Exchange Online y Skype Empresarial. Del mismo modo, si desea usar la clave de cliente con SharePoint Online y OneDrive para la Empresa, debe agregar permisos para que Microsoft 365 use el almacén de claves en nombre de SharePoint Online y OneDrive para la Empresa. Para conceder permiso a Microsoft 365, ejecute el cmdlet **Set-AzKeyVaultAccessPolicy** con la siguiente sintaxis:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Donde:

    - *nombre del almacén* es el nombre del almacén de claves que creó.

    - Para Exchange Online y Skype Empresarial, reemplace  *Office 365 appID* por `00000002-0000-0ff1-ce00-000000000000`

    - For SharePoint Online, OneDrive for Business, and Teams files, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`

  Ejemplo: Configuración de permisos para Exchange Online y Skype Empresarial:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Ejemplo: Configuración de permisos para archivos de SharePoint Online, OneDrive para la Empresa y Teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Habilitar y, a continuación, confirmar la eliminación suave en los almacenes de claves

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción del servicio extendida debido a claves eliminadas accidentalmente o malintencionadas. Debe habilitar esta configuración, denominada Eliminación suave, antes de poder usar las claves con la clave de cliente. Habilitar la eliminación suave permite recuperar claves o almacenes dentro de los 90 días posteriores a la eliminación sin tener que restaurarlas a partir de la copia de seguridad.
  
Para habilitar la eliminación suave en los almacenes de claves, siga estos pasos:
  
1. Inicie sesión en su suscripción de Azure con Windows PowerShell. Para obtener instrucciones, vea [Iniciar sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet [Get-AzKeyVault.](/powershell/module/az.keyvault/get-azkeyvault) En este ejemplo, *el nombre del almacén* es el nombre del almacén de claves para el que está habilitando la eliminación suave:

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
  
Para crear una clave directamente en el almacén de claves, ejecute el cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) de la siguiente manera:
  
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

Para importar una clave directamente en el almacén de claves, debe tener un módulo de seguridad de hardware nCipher nShield.
  
Algunas organizaciones prefieren este enfoque para establecer la procedencia de sus claves y, a continuación, este método también proporciona las siguientes atestaciones:
  
- El conjunto de herramientas usado para la importación incluye la certificación de nCipher de que la clave de exchange de claves (KEK) que se usa para cifrar la clave que genera no es exportable y se genera dentro de un HSM original que fue fabricado por nCipher.

- El conjunto de herramientas incluye la certificación de nCipher de que el mundo de seguridad de Azure Key Vault también se generó en un HSM original fabricado por nCipher. Esta atestación demuestra que Microsoft también usa hardware original de nCipher.

Consulte con el grupo de seguridad para determinar si las atestaciones anteriores son necesarias. Para obtener pasos detallados para crear una clave local e importarla en el almacén de claves, vea How [to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys). Use las instrucciones de Azure para crear una clave en cada almacén de claves.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Comprobar el nivel de recuperación de las claves

Microsoft 365 requiere que la suscripción a Azure Key Vault esté establecida en No cancelar y que las claves usadas por la clave de cliente tengan habilitada la eliminación suave. Puedes confirmar la configuración de suscripciones mirando el nivel de recuperación de las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzKeyVaultKey de la siguiente manera:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Si la propiedad _Nivel_ de recuperación devuelve algo distinto de un valor de **Recoverable+ProtectedSubscription**, asegúrese de que ha puesto la suscripción en la lista No cancelar y de que tiene habilitada la eliminación suave en cada uno de los almacenes de claves.
  
### <a name="back-up-azure-key-vault"></a>Copia de seguridad de Azure Key Vault

Inmediatamente después de la creación o cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión. Las copias sin conexión no deben conectarse a ninguna red, como en una instalación de almacenamiento física segura o comercial. Al menos una copia de la copia de seguridad debe almacenarse en una ubicación a la que se pueda acceder en caso de desastre. Los blobs de copia de seguridad son el único medio para restaurar el material de clave en caso de que una clave del almacén de claves se destruya permanentemente o se represente de otro modo inoperable. Las claves externas a Azure Key Vault y que se importaron a Azure Key Vault no califican como copia de seguridad porque los metadatos necesarios para que la clave de cliente use la clave no existen con la clave externa. Solo se puede usar una copia de seguridad tomada de Azure Key Vault para operaciones de restauración con clave de cliente. Por lo tanto, debe crear una copia de seguridad de Azure Key Vault después de cargar o crear una clave.
  
Para crear una copia de seguridad de una clave de Azure Key Vault, ejecute el cmdlet [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) de la siguiente manera:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Asegúrese de que el archivo de salida usa el sufijo `.backup` .
  
El archivo de salida resultante de este cmdlet está cifrado y no se puede usar fuera de Azure Key Vault. La copia de seguridad solo se puede restaurar en la suscripción de Azure desde la que se ha realizado la copia de seguridad.
  
> [!TIP]
> Para el archivo de salida, elija una combinación del nombre del almacén y el nombre de la clave. Esto hará que el nombre de archivo se describa por sí mismo. También se asegurará de que los nombres de archivo de copia de seguridad no entren en colisión.
  
Por ejemplo:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Validar las opciones de configuración de Azure Key Vault

Validar antes de usar claves en un DEP es opcional, pero muy recomendable. Si usa pasos para configurar las claves y almacenes distintos de los descritos en este artículo, valide el estado de los recursos de Azure Key Vault antes de configurar la clave de cliente.
  
Para comprobar que las claves tienen `get` , y las operaciones `wrapKey` `unwrapKey` habilitadas:
  
Ejecute el cmdlet [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

En el resultado, busque la directiva de access y la identidad de Exchange Online (GUID) o la identidad de SharePoint Online (GUID) según corresponda. Los tres permisos anteriores deben mostrarse en Permisos a claves.
  
Si la configuración de la directiva de acceso es incorrecta, ejecute el cmdlet Set-AzKeyVaultAccessPolicy de la siguiente manera:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Por ejemplo, para Exchange Online y Skype Empresarial:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Por ejemplo, para SharePoint Online y OneDrive para la Empresa:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) de la siguiente manera:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

La clave de cliente no puede usar una clave expirada. Las operaciones que se intentan con una clave expirada producirán un error y, posiblemente, provocarán una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con la clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a una fecha diferente. Si se debe usar una clave que tenga un conjunto de fechas de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha que no sea 12/31/9999 no pasarán la validación de Microsoft 365.
  
Para cambiar una fecha de expiración que se haya establecido en cualquier valor distinto del 12/31/9999, ejecute el cmdlet [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) de la siguiente manera:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> No establezca las fechas de expiración en las claves de cifrado que use con la clave de cliente.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtener el URI de cada clave de Azure Key Vault

Una vez que haya configurado los almacenes de claves y agregado las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de claves. Tendrás que usar estos URI al crear y asignar cada DEP más adelante, así que guarda esta información en un lugar seguro. Ejecute este comando una vez para cada almacén de claves.
  
En Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: configurar la clave de cliente para Exchange Online y Skype Empresarial

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault. Consulte [Completar tareas en Azure Key Vault y Microsoft FastTrack para obtener información.](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)
  
Para configurar la clave de cliente para Exchange Online y Skype Empresarial, debe completar estos pasos conectándose de forma remota a Exchange Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Crear una directiva de cifrado de datos (DEP) para su uso con Exchange Online y Skype Empresarial

Un DEP está asociado con un conjunto de claves almacenadas en Azure Key Vault. Se asigna un DEP a un buzón en Microsoft 365. Microsoft 365 usará las claves identificadas en la directiva para cifrar el buzón. Para crear el DEP, necesita los URI de Key Vault que obtuvo anteriormente. Consulte [Obtener el URI de cada clave de Azure Key Vault para](#obtain-the-uri-for-each-azure-key-vault-key) obtener instrucciones.
  
¡Recuerda! Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes. Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear el DEP, siga estos pasos:
  
1. En el equipo local, con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana Windows PowerShell usuario.

2. Para crear un DEP, use New-DataEncryptionPolicy cmdlet escribiendo el siguiente comando.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Donde:

   - *PolicyName* es el nombre que desea usar para la directiva. Los nombres no pueden contener espacios. Por ejemplo, USA_mailboxes.

   - *Descripción de* la directiva es una descripción fácil de usar de la directiva que le ayudará a recordar para qué es la directiva. Puede incluir espacios en la descripción. Por ejemplo, "Clave raíz para buzones de correo en Estados Unidos y sus territorios".

   - *KeyVaultURI1* es el URI de la primera clave de la directiva. Por ejemplo, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* es el URI de la segunda clave de la directiva. Por ejemplo, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Separe los dos URI por una coma y un espacio.

   Ejemplo:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Asignar un DEP a un buzón

Asigne el DEP a un buzón mediante el cmdlet Set-Mailbox. Una vez que asigne la directiva, Microsoft 365 puede cifrar el buzón con la clave identificada en el DEP.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailboxIdParameter* especifica un buzón de usuario. Para obtener más información acerca del cmdlet Set-Mailbox, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).

En entornos híbridos, puede asignar un DEP a los datos de buzones locales que se sincronizan con el inquilino de Exchange Online. Para asignar un DEP a estos datos de buzones sincronizados, usará el cmdlet Set-MailUser correo. Para obtener más información acerca de los datos de buzones en el entorno híbrido, vea buzones locales con Outlook para iOS y Android con [autenticación moderna híbrida.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Donde *MailUserIdParameter* especifica un usuario de correo (también conocido como usuario habilitado para correo). Para obtener más información acerca del cmdlet Set-MailUser, vea [Set-MailUser](/powershell/module/exchange/set-mailuser).
  
### <a name="validate-mailbox-encryption"></a>Validar el cifrado de buzones

Cifrar un buzón puede tardar algún tiempo. Para la asignación de directivas por primera vez, el buzón también debe moverse completamente de una base de datos a otra para que el servicio pueda cifrar el buzón. Se recomienda esperar 72 horas antes de intentar validar el cifrado después de cambiar un DEP o la primera vez que asigne un DEP a un buzón.
  
Use el cmdlet Get-MailboxStatistics para determinar si un buzón está cifrado.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

La propiedad IsEncrypted devuelve un valor **de true** si el buzón está cifrado y un valor de **false** si el buzón no está cifrado. El tiempo para completar los movimientos de buzones depende del número de buzones a los que asigne un DEP por primera vez y del tamaño de los buzones. Si los buzones no se han cifrado después de una semana desde el momento en que asignó el DEP, póngase en contacto con Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: configurar la clave de cliente para archivos de SharePoint Online, OneDrive para la Empresa y Teams

Antes de empezar, asegúrese de que ha completado las tareas necesarias para configurar Azure Key Vault. Consulte [Completar tareas en Azure Key Vault y Microsoft FastTrack para obtener información.](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key)
  
Para configurar los archivos clave de cliente para SharePoint Online, OneDrive para la Empresa y Teams, realice estos pasos conectándose de forma remota a SharePoint Online con Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Crear una directiva de cifrado de datos (DEP) para cada geo de SharePoint Online y OneDrive para la Empresa

Asocie un DEP con un conjunto de claves almacenadas en Azure Key Vault. Se aplica un DEP a todos los datos en una ubicación geográfica, también denominada geo. Si usa la característica multigeográfica de Office 365, puede crear un DEP por geo con la capacidad de usar diferentes claves por geo. Si no está usando multige-geo, puede crear un DEP en su organización para usarlo con archivos de SharePoint Online, OneDrive para la Empresa y Teams. Microsoft 365 usa las claves identificadas en el DEP para cifrar los datos en esa ubicación geográfica. Para crear el DEP, necesita los URI de Key Vault que obtuvo anteriormente. Consulte [Obtener el URI de cada clave de Azure Key Vault para](#obtain-the-uri-for-each-azure-key-vault-key) obtener instrucciones.
  
¡Recuerda! Al crear un DEP, se especifican dos claves en dos almacenes de claves de Azure diferentes. Cree estas claves en dos regiones de Azure independientes para garantizar la redundancia geográfica.
  
Para crear un DEP, debe conectarse de forma remota a SharePoint Online mediante Windows PowerShell.
  
1. En el equipo local, con una cuenta laboral o educativa que tenga permisos de administrador global en su organización, Conéctese a [PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).

2. En el Shell de administración de Microsoft SharePoint Online, ejecute el cmdlet Register-SPODataEncryptionPolicy de la siguiente manera:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Ejemplo:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Al registrar el DEP, el cifrado comienza en los datos de la geo. El cifrado puede tardar algo de tiempo. Para obtener más información sobre el uso de este parámetro, [vea Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).

### <a name="validate-file-encryption"></a>Validar cifrado de archivos

 Para validar el cifrado de archivos de SharePoint Online, OneDrive para la Empresa y Teams, conéctese a PowerShell de [SharePoint Online](/powershell/exchange/connect-to-exchange-online-powershell)y, a continuación, use el cmdlet Get-SPODataEncryptionPolicy para comprobar el estado del inquilino. La _propiedad State_ devuelve un valor de **registrado** si el cifrado de clave de cliente está habilitado y todos los archivos de todos los sitios se han cifrado. Si el cifrado aún está en curso, este cmdlet devuelve un valor de **registro**.

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Obtenga información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Cifrado de servicio](office-365-service-encryption.md)