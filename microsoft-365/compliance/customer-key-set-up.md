---
title: Configuración de la clave de cliente
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
description: En este artículo se describen los pasos para crear y configurar los recursos de Azure necesarios y, a continuación, se proporcionan los pasos para configurar la clave de cliente.
ms.openlocfilehash: 4d6c82efc996d0d10b619bf152ffbfb3d27b9d5f
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68641829"
---
# <a name="set-up-customer-key"></a>Configuración de la clave de cliente

Con La clave de cliente, puede controlar las claves de cifrado de su organización y, a continuación, configurar Microsoft 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft. En otras palabras, La clave de cliente permite a los clientes agregar una capa de cifrado que les pertenece, con sus claves.

Configure Azure para poder usar la clave de cliente. En este artículo se describen los pasos que debe seguir para crear y configurar los recursos de Azure necesarios y, a continuación, se proporcionan los pasos para configurar la clave de cliente. Después de configurar Azure, se determina qué directiva y, por lo tanto, qué claves se van a asignar para cifrar los datos en varias cargas de trabajo de Microsoft 365 de la organización. Para obtener más información sobre la clave de cliente o para obtener información general, consulte [Cifrado de servicio con clave de cliente de Microsoft Purview](customer-key-overview.md).
  
> [!IMPORTANT]
> Se recomienda encarecidamente seguir los procedimientos recomendados de este artículo. Se denominan **TIP** e **IMPORTANTE**. Clave de cliente proporciona control sobre las claves de cifrado raíz cuyo ámbito puede ser tan grande como toda la organización. Esto significa que los errores cometidos con estas claves pueden tener un gran impacto y pueden dar lugar a interrupciones del servicio o pérdida irrevocable de los datos.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-set-up-customer-key"></a>Antes de configurar la clave de cliente

Antes de empezar, asegúrese de que tiene las suscripciones de Azure y las licencias M365/O365 adecuadas para su organización. Debe usar suscripciones de Azure de pago. Las suscripciones que obtuvo a través de Gratis, Evaluación, Patrocinios, Suscripciones de MSDN y las que se encuentran en Soporte técnico heredado no son aptas.

> [!IMPORTANT]
> Las licencias válidas de M365/O365 que ofrecen la clave de cliente M365 son:
>
> - Office 365 E5
> - Microsoft 365 E5
> - Cumplimiento de Microsoft 365 E5
> - SKU de Microsoft 365 E5 Information Protection & Governance
> - Seguridad y cumplimiento de Microsoft 365 para FLW

Se seguirán admitiendo las licencias de Cumplimiento avanzado de Office 365 existentes.

Para comprender los conceptos y procedimientos de este artículo, revise la documentación [de Azure कि भल्ट](/azure/key-vault/). Además, familiarícese con los términos usados en Azure, por ejemplo, [inquilino de Azure AD](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant).
  
Si necesita más soporte técnico que la documentación, póngase en contacto con Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) o con un asociado de Microsoft para obtener ayuda. Para proporcionar comentarios sobre la clave del cliente, incluida la documentación, envíe sus ideas, sugerencias y perspectivas a customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Introducción a los pasos para configurar la clave de cliente

Para configurar la clave de cliente, complete estas tareas en el orden indicado. El resto de este artículo proporciona instrucciones detalladas para cada tarea o vínculos a más información para cada paso del proceso.
  
**En Azure y Microsoft FastTrack:**
  
Completará la mayoría de estas tareas mediante la conexión remota a Azure PowerShell. Para obtener mejores resultados, use la versión 4.4.0 o posterior de Azure PowerShell.
  
- [Creación de dos nuevas suscripciones de Azure](#create-two-new-azure-subscriptions)

- [Enviar una solicitud para activar la clave de cliente para Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

- [Registro de suscripciones de Azure para usar un período de retención obligatorio](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  Este proceso de registro tardará cinco días laborables en completarse.
- [Póngase en contacto con el alias de Microsoft correspondiente para continuar con el proceso.](#contact-the-corresponding-microsoft-alias-to-proceed-with-the-process)

- [Creación de una कि भल्ट premium de Azure en cada suscripción](#create-a-premium-azure-key-vault-in-each-subscription)

- [Asignación de permisos a cada almacén de claves](#assign-permissions-to-each-key-vault)

- [Asegúrese de que la eliminación temporal está habilitada en los almacenes de claves.](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [Agregue una clave a cada almacén de claves mediante la creación o importación de una clave](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Comprobación de la fecha de expiración de las claves](#verify-expiration-date-of-your-keys)

- [Comprobación del nivel de recuperación de las claves](#check-the-recovery-level-of-your-keys)

- [Copia de seguridad de Azure कि भल्ट](#back-up-azure-key-vault)

- [Obtención del URI para cada clave de azure कि भल्ट](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Completar tareas en Azure कि भल्ट y Microsoft FastTrack para la clave de cliente

Complete estas tareas en Azure कि भल्ट. Deberá completar estos pasos para todos los DEP que use con la clave de cliente.
  
### <a name="create-two-new-azure-subscriptions"></a>Creación de dos nuevas suscripciones de Azure

La clave de cliente requiere dos suscripciones de Azure. Como procedimiento recomendado, Microsoft recomienda crear nuevas suscripciones de Azure para usarlas con la clave de cliente. Las claves de Azure कि भल्ट solo se pueden autorizar para aplicaciones en el mismo inquilino de Azure Active Directory (Microsoft Azure Active Directory), debe crear las nuevas suscripciones con el mismo inquilino de Azure AD que se usa con la organización donde se asignarán los DEP. Por ejemplo, usar la cuenta profesional o educativa que tenga privilegios de administrador global en su organización. Para obtener pasos detallados, consulte [Registrarse en Azure como organización](/azure/active-directory/fundamentals/sign-up-organization).
  
> [!IMPORTANT]
> La clave de cliente requiere dos claves para cada directiva de cifrado de datos (DEP). Para ello, debe crear dos suscripciones de Azure. Como procedimiento recomendado, Microsoft recomienda que tenga miembros independientes de su organización que configuren una clave en cada suscripción. Solo debe usar estas suscripciones de Azure para administrar claves de cifrado para Office 365. Esto protege su organización en caso de que uno de los operadores elimine accidentalmente, intencionada o malintencionadamente o de otro modo no coincida con las claves de las que son responsables.

No hay ningún límite práctico para el número de suscripciones de Azure que puede crear para su organización. Si sigue estos procedimientos recomendados, se minimizará el impacto del error humano y, al mismo tiempo, se ayudarán a administrar los recursos utilizados por la clave de cliente.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Enviar una solicitud para activar la clave de cliente para Office 365

Una vez que haya creado las dos nuevas suscripciones de Azure, deberá enviar la solicitud de oferta de clave de cliente adecuada en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/). Las selecciones que realice en el formulario de oferta sobre las designaciones autorizadas dentro de su organización son críticas y necesarias para completar el registro de clave de cliente. Los responsables de esos roles seleccionados de su organización garantizan la autenticidad de cualquier solicitud de revocación y destrucción de todas las claves usadas con una directiva de cifrado de datos de clave de cliente. Tendrá que realizar este paso una vez por cada tipo de DEP de clave de cliente que quiera usar para su organización.

**El equipo de FastTrack no proporciona asistencia con la clave de cliente. Office 365 simplemente usa el portal de FastTrack para permitirle enviar el formulario y ayudarnos a realizar un seguimiento de las ofertas pertinentes para la clave de cliente. Una vez que haya enviado la solicitud de FastTrack, póngase en contacto con el equipo de incorporación de la clave de cliente correspondiente para iniciar el proceso de incorporación.**
  
Para enviar una oferta para activar la clave de cliente, complete estos pasos:
  
1. Con una cuenta profesional o educativa que tenga permisos de administrador global en su organización, inicie sesión en el [portal de Microsoft FastTrack](https://fasttrack.microsoft.com/).

2. Una vez que haya iniciado sesión, seleccione el dominio adecuado.

3. En el dominio seleccionado, elija **Implementar** en la barra de navegación superior y revise la lista de ofertas disponibles.

4. Elija la tarjeta de información de la oferta que se aplica a usted:

   - **Varias cargas de trabajo de Microsoft 365:** Elija la **oferta Solicitud de ayuda de clave de cifrado para Microsoft 365** .

   - **Exchange Online y Skype Empresarial:** elija la **ayuda Solicitar clave de cifrado para la oferta de Exchange**.

   - **Archivos de SharePoint Online, OneDrive y Teams:** Elija la **ayuda solicitar clave de cifrado para SharePoint y OneDrive para la Empresa** oferta.

5. Una vez que haya revisado los detalles de la oferta, elija **Continuar al paso 2**.

6. Rellene todos los detalles aplicables y la información solicitada en el formulario de oferta. Preste especial atención a las selecciones para las que los responsables de su organización quiera autorizar la aprobación de la destrucción permanente e irreversible de claves de cifrado y datos. Una vez que haya completado el formulario, elija **Enviar**.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registro de suscripciones de Azure para usar un período de retención obligatorio

La pérdida temporal o permanente de claves de cifrado raíz puede ser perjudicial o incluso catastrófica para el funcionamiento del servicio y puede dar lugar a la pérdida de datos. Por este motivo, los recursos utilizados con la clave de cliente requieren una protección segura. Todos los recursos de Azure que se usan con clave de cliente ofrecen mecanismos de protección más allá de la configuración predeterminada. Puede etiquetar o registrar suscripciones de Azure durante un *período de retención obligatorio*. Un período de retención obligatorio impide la cancelación inmediata e irrevocable de la suscripción de Azure. Los pasos necesarios para registrar las suscripciones de Azure durante un período de retención obligatorio requieren la colaboración con el equipo de Microsoft 365. Anteriormente, a veces se hacía referencia al período de retención obligatorio como "No cancelar". Este proceso tardará cinco días laborables en completarse.
  
> [!IMPORTANT]
> Antes de ponerse en contacto con el equipo de Microsoft 365, debe realizar los pasos siguientes para **cada** suscripción de Azure que use con la clave de cliente. Asegúrese de que tiene instalado el módulo [az de Azure PowerShell](/powershell/azure/new-azureps-module-az) antes de empezar.

1. Inicie sesión con Azure PowerShell. Para obtener instrucciones, consulte [Inicio de sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet Register-AzProviderFeature para registrar las suscripciones y usar un período de retención obligatorio. Complete esta acción para **cada** suscripción.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

### <a name="contact-the-corresponding-microsoft-alias-to-proceed-with-the-process"></a>Póngase en contacto con el alias de Microsoft correspondiente para continuar con el proceso.

>[!NOTE]
> Antes de ponerse en contacto con el alias de Microsoft correspondiente, compruebe que ha completado las solicitudes de FastTrack para la clave de cliente M365.

- Para habilitar la clave de cliente para asignar DEP a buzones de Exchange Online individuales, póngase en contacto con [exock@microsoft.com](mailto:exock@microsoft.com).

- Para habilitar la clave de cliente para asignar DEP para cifrar SharePoint Online y OneDrive para la Empresa contenido (incluidos los archivos de Teams) para todos los usuarios del inquilino, póngase en contacto con [spock@microsoft.com](mailto:spock@microsoft.com).

- Para habilitar la clave de cliente para asignar DEP para cifrar el contenido en varias cargas de trabajo de Microsoft 365 (Exchange Online, Teams, Microsoft Purview Information Protection) para todos los usuarios del inquilino, póngase en contacto con [m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com).

- Incluya la siguiente información en su correo electrónico:

     **Asunto**: Clave de cliente para \<*Your tenant's fully qualified domain name*\>

     **Cuerpo**: incluya los identificadores de solicitud y los identificadores de suscripción de FastTrack para **cada uno** de los servicios de clave de cliente a los que desea incorporarse. Estos identificadores de suscripción son los que desea completar el período de retención obligatorio y la salida de Get-AzProviderFeature para cada suscripción.

El Acuerdo de Nivel de Servicio (SLA) para la finalización de este proceso es de cinco días laborables una vez que Se ha notificado (y comprobado) a Microsoft que ha registrado sus suscripciones para usar un período de retención obligatorio.

### <a name="verify-the-status-of-each-your-azure-subscriptions"></a>Comprobación del estado de cada una de las suscripciones de Azure

Una vez que reciba una notificación de Microsoft de que el registro se ha completado, compruebe el estado del registro mediante la ejecución del comando Get-AzProviderFeature como se indica a continuación. Si se comprueba, el comando Get-AzProviderFeature devuelve un valor de **Registrado** para la propiedad **Estado de registro** . Complete este paso para **cada** suscripción.

   ```powershell
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

> [!TIP]
> Antes de continuar, asegúrese de que "RegistrationState" está establecido en "Registrado" como la imagen siguiente.
>
> ![Período de retención obligatorio](../media/MandatoryRetentionPeriod.png)

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Creación de una कि भल्ट premium de Azure en cada suscripción

Los pasos para crear un almacén de claves se documentan en [Introducción a Azure कि भल्ट](/azure/key-vault/general/overview), que le guía a través de la instalación y el inicio de Azure PowerShell, la conexión a la suscripción de Azure, la creación de un grupo de recursos y la creación de un almacén de claves en ese grupo de recursos.
  
Al crear un almacén de claves, debe elegir una SKU: Estándar o Premium. La SKU estándar permite que las claves de Azure कि भल्ट estén protegidas con software (no hay ninguna protección de claves del Módulo de seguridad de hardware (HSM) y la SKU Premium permite el uso de HSM para la protección de claves de कि भल्ट. Clave de cliente acepta almacenes de claves que usan cualquiera de las SKU, aunque Microsoft recomienda encarecidamente que use solo la SKU Premium. El costo de las operaciones con claves de cualquier tipo es el mismo, por lo que la única diferencia en el costo es el costo por mes para cada clave protegida por HSM. Consulte [कि भल्ट precios](https://azure.microsoft.com/pricing/details/key-vault/) para obtener más información.
  
> [!IMPORTANT]
> Use los almacenes de claves de SKU Premium y las claves protegidas por HSM para los datos de producción, y use solo almacenes de claves y claves de SKU estándar con fines de prueba y validación.
  
Para cada servicio de Microsoft 365 con el que usará la clave de cliente, cree un almacén de claves en cada una de las dos suscripciones de Azure que ha creado. Por ejemplo, para permitir que la clave de cliente use DEP para escenarios de Exchange Online, SharePoint Online y cargas de trabajo múltiples, creará tres pares de almacenes de claves.
  
Use una convención de nomenclatura para almacenes de claves que refleje el uso previsto del DEP con el que asociará los almacenes. Consulte la sección Procedimientos recomendados a continuación para obtener recomendaciones de convención de nomenclatura.
  
Cree un conjunto de almacenes separado y emparejado para cada directiva de cifrado de datos. Para Exchange Online, el ámbito de una directiva de cifrado de datos lo elige usted al asignar la directiva al buzón. Un buzón solo puede tener asignada una directiva y puede crear hasta 50 directivas. El ámbito de una directiva de SharePoint Online incluye todos los datos de una organización en una ubicación geográfica o *geográfica*. El ámbito de una directiva de varias cargas de trabajo incluye todos los datos de las cargas de trabajo admitidas para todos los usuarios.

La creación de almacenes de claves también requiere la creación de grupos de recursos de Azure, ya que los almacenes de claves necesitan capacidad de almacenamiento (aunque pequeña) y कि भल्ट registro, si está habilitado, también genera datos almacenados. Como procedimiento recomendado, Microsoft recomienda usar administradores independientes para administrar cada grupo de recursos, con la administración alineada con el conjunto de administradores que administrarán todos los recursos relacionados con la clave de cliente.
  
### <a name="assign-permissions-to-each-key-vault"></a>Asignación de permisos a cada almacén de claves

Tendrá que definir tres conjuntos de permisos independientes para cada almacén de claves, en función de la implementación. Por ejemplo, tendrá que definir un conjunto de permisos para cada uno de los siguientes elementos:
  
- **Administradores del almacén de claves** que realizan la administración diaria del almacén de claves para su organización. Estas tareas incluyen copia de seguridad, creación, obtención, importación, lista y restauración.

  > [!IMPORTANT]
  > El conjunto de permisos asignados a los administradores del almacén de claves no incluye el permiso para eliminar claves. Esto es intencionado y una práctica importante. Normalmente no se realiza la eliminación de claves de cifrado, ya que al hacerlo se destruyen de forma permanente los datos. Como procedimiento recomendado, no conceda este permiso a los administradores del almacén de claves de forma predeterminada. En su lugar, reserve esto para los colaboradores del almacén de claves y asígnelo solo a un administrador a corto plazo una vez que se comprendan claramente las consecuencias.
  
  Para asignar estos permisos a un usuario de la organización, inicie sesión en su suscripción de Azure con Azure PowerShell. Para obtener instrucciones, consulte [Inicio de sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

  - Ejecute el cmdlet Set-AzKeyVaultAccessPolicy para asignar los permisos necesarios.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Por ejemplo:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Colaboradores de Key Vault** que pueden cambiar los permisos en el propio कि भल्ट de Azure. Tendrá que cambiar estos permisos a medida que los empleados se vayan o se unan a su equipo. En la rara situación en la que los administradores del almacén de claves necesitan legítimamente permiso para eliminar o restaurar una clave, también tendrá que cambiar los permisos. A este conjunto de colaboradores del almacén de claves se le debe conceder el rol **Colaborador** en el almacén de claves. Puede asignar este rol mediante Azure Resource Manager. Para obtener pasos detallados, consulte [Uso de Role-Based Access Control para administrar el acceso a los recursos de la suscripción de Azure](/azure/active-directory/role-based-access-control-configure). El administrador que crea una suscripción tiene este acceso implícitamente y la capacidad de asignar otros administradores al rol Colaborador.

- **Permisos para aplicaciones de Microsoft 365** para cada almacén de claves que use para clave de cliente, debe proporcionar wrapKey, unwrapKey y obtener permisos a la entidad de servicio de Microsoft 365 correspondiente.

  Para conceder permiso a la entidad de servicio de Microsoft 365, ejecute el cmdlet **Set-AzKeyVaultAccessPolicy** mediante la sintaxis siguiente:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Donde:
   - *el nombre del almacén* de claves es el nombre del almacén de claves que ha creado.
   - Para Exchange Online y Skype Empresarial, reemplace *Office 365 appID* por`00000002-0000-0ff1-ce00-000000000000`
   - Para los archivos de SharePoint Online, OneDrive para la Empresa y Teams, reemplace *Office 365 appID* por`00000003-0000-0ff1-ce00-000000000000`
   - Para la directiva de varias cargas de trabajo (Exchange, Teams, Microsoft Purview Information Protection) que se aplica a todos los usuarios del inquilino, reemplace *Office 365 appID* por`c066d759-24ae-40e7-a56f-027002b5d3e4`

  Ejemplo: Establecer permisos para Exchange Online y Skype Empresarial:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Ejemplo: Establecer permisos para archivos de SharePoint Online, OneDrive para la Empresa y Teams:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

  Confirme que *get, wrapKey y unwrapKey* se conceden a **cada** almacén de claves mediante la ejecución del cmdlet *Get-AzKeyVault* .

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```  

> [!Tip]
> Antes de continuar, asegúrese de que los permisos están configurados correctamente para el almacén de claves; los *permisos para claves* **devolverán wrapKey, unwrapKey, get**.
> Asegúrese de corregir los permisos para el servicio correcto al que se va a incorporar. El *nombre para mostrar* de cada servicio se muestra a continuación:  
  >
  > - Exchange Online y Skype Empresarial: *Office 365 Exchange Online*
  > - Archivos de SharePoint Online, OneDrive y Teams: *Office 365 SharePoint Online*
  > - Varias cargas de trabajo de Microsoft 365: *M365DataAtRestEncryption*
  >  
  > Por ejemplo, el fragmento de código siguiente es un ejemplo de cómo asegurarse de que los permisos están configurados para M365DataAtRestEncryption. El siguiente cmdlet con un almacén denominado *mmcexchangevault* mostrará los campos siguientes.
  >
  > ```powershell
  >   Get-AzKeyVault -VaultName mmcexchangevault | fl
  >   ```  
  >
  >
  > ![Cifrado de cifrado para Exchange Online clave de cliente.](../media/KeyVaultPermissions.png)

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>Asegúrese de que la eliminación temporal está habilitada en los almacenes de claves.

Cuando puede recuperar rápidamente las claves, es menos probable que experimente una interrupción prolongada del servicio debido a claves eliminadas accidental o malintencionadamente. Habilite esta configuración, denominada Eliminación temporal, para poder usar las claves con la clave de cliente. Habilitar la eliminación temporal permite recuperar claves o almacenes en un plazo de 90 días después de la eliminación sin tener que restaurarlas desde la copia de seguridad.
  
Para habilitar la eliminación temporal en los almacenes de claves, complete estos pasos:
  
1. Inicie sesión en la suscripción de Azure con Windows PowerShell. Para obtener instrucciones, consulte [Inicio de sesión con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Ejecute el cmdlet [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) . En este ejemplo, *el nombre del almacén* es el nombre del almacén de claves para el que va a habilitar la eliminación temporal:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Confirme que la eliminación temporal está configurada para el almacén de claves mediante la ejecución del cmdlet **Get-AzKeyVault** . Si la eliminación temporal está configurada correctamente para el almacén de claves, la propiedad *Eliminación temporal habilitada* devuelve un valor de **True**:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

> [!TIP]
> Antes de continuar, asegúrese de que la opción "Eliminación temporal habilitada". se establece en "True" como la imagen siguiente.
>
> <img src="../media/SoftDeleteEnabled.png" alt="SoftDelete" width="400"/>

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Agregue una clave a cada almacén de claves mediante la creación o importación de una clave

Hay dos maneras de agregar claves a una कि भल्ट de Azure; puede crear una clave directamente en कि भल्ट o puede importar una clave. La creación de una clave directamente en कि भल्ट es menos complicada, pero la importación de una clave proporciona control total sobre cómo se genera la clave. Use las claves RSA. Azure कि भल्ट no admite el ajuste y desencapsulado con teclas de curva elípticas.

Para obtener instrucciones para agregar una clave a cada almacén, consulte [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey).

 Para obtener pasos detallados para crear una clave local e importarla en el almacén de claves, consulte [Cómo generar y transferir claves protegidas por HSM para Azure कि भल्ट](/azure/key-vault/keys/hsm-protected-keys). Use las instrucciones de Azure para crear una clave en cada almacén de claves.

### <a name="verify-expiration-date-of-your-keys"></a>Comprobación de la fecha de expiración de las claves

Para comprobar que no se ha establecido una fecha de expiración para las claves, ejecute el cmdlet [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) como se indica a continuación:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

La clave de cliente no puede usar una clave expirada. Las operaciones que se intenten con una clave expirada producirán un error y, posiblemente, provocarán una interrupción del servicio. Se recomienda encarecidamente que las claves usadas con clave de cliente no tengan una fecha de expiración. Una fecha de expiración, una vez establecida, no se puede quitar, pero se puede cambiar a otra fecha. Si se debe usar una clave que tenga establecida una fecha de expiración, cambie el valor de expiración a 12/31/9999. Las claves con una fecha de expiración establecida en una fecha distinta del 12/31/9999 no superarán la validación de Microsoft 365.
  
Para cambiar una fecha de expiración establecida en cualquier valor distinto del 12/31/9999, ejecute el cmdlet [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) de la siguiente manera:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> No establezca fechas de expiración en las claves de cifrado que use con clave de cliente.  

### <a name="check-the-recovery-level-of-your-keys"></a>Comprobación del nivel de recuperación de las claves

Microsoft 365 requiere que la suscripción de Azure कि भल्ट esté establecida en No cancelar y que las claves usadas por clave de cliente tengan habilitada la eliminación temporal. Puede confirmar la configuración de las suscripciones examinando el nivel de recuperación en las claves.
  
Para comprobar el nivel de recuperación de una clave, en Azure PowerShell, ejecute el cmdlet Get-AzKeyVaultKey de la siguiente manera:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

> [!Tip]
> Antes de continuar, si la propiedad *Nivel de recuperación* devuelve algo distinto de un valor de **Recoverable+ProtectedSubscription**, asegúrese de que ha registrado la característica *MandatoryRetentionPeriodEnabled* en la suscripción y de que tiene habilitada la eliminación temporal en cada uno de los almacenes de claves.
>
>    <img src="../media/RecoveryLevel.png" alt="drawing" width="500"/>

### <a name="back-up-azure-key-vault"></a>Copia de seguridad de Azure कि भल्ट

Inmediatamente después de la creación o cualquier cambio en una clave, realice una copia de seguridad y almacene copias de la copia de seguridad, tanto en línea como sin conexión.
Para crear una copia de seguridad de una clave de Azure कि भल्ट, ejecute el cmdlet [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey).

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Obtención del URI para cada clave de azure कि भल्ट

Una vez que haya configurado los almacenes de claves y agregado las claves, ejecute el siguiente comando para obtener el URI de la clave en cada almacén de claves. Usará estos URI al crear y asignar cada DEP más adelante, por lo que debe guardar esta información en un lugar seguro. Ejecute este comando una vez para cada almacén de claves.
  
En Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya completado los pasos de este artículo, estará listo para crear y asignar DEP. Para obtener instrucciones, consulte [Administrar clave de cliente](customer-key-manage.md).

## <a name="related-articles"></a>Artículos relacionados

- [Cifrado de servicio con clave de cliente](customer-key-overview.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Cifrado de servicio](office-365-service-encryption.md)
