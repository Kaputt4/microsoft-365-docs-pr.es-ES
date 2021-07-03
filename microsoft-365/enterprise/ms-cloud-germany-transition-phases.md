---
title: Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Summary: Understand the migration phases actions and impacts of moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.'
ms.openlocfilehash: 2efb1ad941c06ed3273032eb8ce14d81dd2eb834
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286158"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland

Las migraciones de inquilinos de Microsoft Cloud Deutschland (MCD) a la región "Alemania" de los servicios globales de Office 365 de Microsoft se ejecutan como un conjunto de fases y sus acciones configuradas para cada carga de trabajo. Esta figura muestra las diez fases de migración a los nuevos centros de datos alemanes.

[![Las diez fases de migración a los nuevos centros de datos de Alemania ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)](../media/ms-cloud-germany-migration-opt-in/migration-organization.png#lightbox)

El proceso de migración se completará durante varias semanas en función del tamaño general y la complejidad de la organización. Mientras la migración está en curso, los usuarios y administradores pueden seguir usando los servicios con cambios notables detallados en esta documentación. El gráfico y la tabla definen fases y pasos durante la migración.

> [!NOTE]
> La migración de los servicios de Azure no forma parte de esta documentación. Para obtener esa información, consulte [Migration guidance for Azure Germany](/azure/germany/germany-migration-main).

<br>

****

|Pasos|Duración|Responsable|Descripción|
|---|---|---|---|
|Opt-In|Horas|Clientes|Opte por la organización en la migración.|
|Pre-Work|Días|Clientes|Complete el trabajo necesario para preparar usuarios, estaciones de trabajo y red para la migración.|
|Azure Active Directory (Azure AD)|De 1 a 2 días|Microsoft|Migre la organización de Azure AD a todo el mundo.|
|Azure|Semanas|Clientes|Crear nuevas suscripciones mundiales de Azure y [servicios de Azure de transición.](/azure/azure-resource-manager/management/move-resource-group-and-subscription)|
|Suscripción & de licencias|De 1 a 2 días|Microsoft|Compre suscripciones mundiales, cancele las suscripciones de Microsoft Cloud Deutschland y las licencias de usuario de transición.|
|SharePoint y OneDrive|Más de 15 días|Microsoft|Migre SharePoint y OneDrive para la Empresa contenido, conservando sharepoint.de direcciones URL.|
|Exchange Online|Más de 15 días|Microsoft|Migre Exchange Online contenido y la transición a direcciones URL de todo el mundo.|
|Seguridad y cumplimiento|De 1 a 2 días|Microsoft|Seguridad de transición & de cumplimiento y contenido.|
|Skype Empresarial|De 1 a 2 días|Microsoft|Transición de Skype Empresarial a Microsoft Teams.|
|Power BI & Dynamics 365|Más de 15 días|Microsoft|Migre Power BI y contenido de Dynamics 365.|
|Finalizar Azure AD|De 1 a 2 días|Microsoft|Completar el recorte de inquilinos a todo el mundo.|
|Clean-Up|De 1 a 2 días|Clientes|Limpie las conexiones heredadas a Microsoft Cloud Deutschland, como la confianza de usuario de confianza de usuario de confianza de servicios de federación de Active Directory (AD FS), azure AD Conectar y Office cliente.|
|Extremos deshabilitados|30 días|Microsoft|30 días después de finalizar Azure AD, el servicio Microsoft Cloud Deutschland Azure AD detendrá el acceso de puntos de conexión para la organización en transición. Las solicitudes de extremo, como la autenticación, producirán un error a partir de este momento en el servicio Microsoft Cloud Deutschland. Los clientes que ejecutan cargas de trabajo de Azure en la instancia vinculada Office 365 servicios de Microsoft Cloud Deutschland se trasladarán a la fase de migración final más adelante.|
|

Las fases y sus acciones garantizan que los datos críticos y las experiencias se migren a los servicios Office 365 global. Después de agregar el espacio empresarial a la cola de migración, cada carga de trabajo se completará como un conjunto de pasos que se ejecutan en el servicio back-end. Algunas cargas de trabajo pueden requerir acciones del administrador (o usuario) o la migración puede afectar al uso de las fases que se ejecutan y se analizan en ¿Cómo se organiza la [migración?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Las secciones siguientes contienen acciones y efectos para las cargas de trabajo a medida que avanzan a través de varias fases de la migración. Revise las tablas y determine qué acciones o efectos son aplicables a su organización. Asegúrese de que está preparado para ejecutar los pasos en las fases correspondientes según sea necesario. Si no se completan los pasos necesarios, se puede producir una interrupción del servicio y puede retrasar la finalización de la migración a los Office 365 servicios.

## <a name="phase-opt-in"></a>Fase: Opt-In

**Se** aplica a: todos los clientes con un inquilino de Office 365 hospedado en Microsoft Cloud Deutschland (MCD) Microsoft no puede migrar Office 365 inquilinos hospedados en mcd sin consentimiento.

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|**Tarea del cliente:** conceder el consentimiento para la migración|El cliente concede el consentimiento para la migración de modo que Microsoft obtiene el derecho de migrar y de organizar la transición de datos y servicios a la instancia de servicios Office 365 global. Hay dos formas: <ol><li>El Office 365 de inquilinos opta por la migración controlada por Microsoft.</li><li>Los clientes han renovado cualquier suscripción en su mcd Office 365 inquilino después del 1 de mayo de 2020. Microsoft notifica a estos clientes el derecho de migración cada mes, espera 30 días para dar a los clientes la oportunidad de cancelar y luego participar directamente.</li></ol>|<ul><li>El espacio empresarial se marca como consentido para la migración y el Centro de administración muestra la confirmación.</li><li>La confirmación se publica en el Centro de mensajes Office 365 inquilino. La configuración del servicio continúa desde los puntos de conexión de Microsoft Cloud Deutschland.</li></ul>
|**Administrador de inquilinos:** supervisar mensajes|El administrador de inquilinos debe supervisar el centro Office 365 mensajes para obtener actualizaciones sobre el estado de la fase de migración a partir de este momento.|El cliente puede ejecutar las tareas necesarias a tiempo.
|

## <a name="phase-1-before-the-migration-starts"></a>Fase 1: Antes de que se inicie la migración

Asegúrese de que está familiarizado con los pasos de preparación [de la migración que se aplican a todos los clientes](ms-cloud-germany-transition-add-pre-work.md).

En caso de que haya establecido un CNAME DNS denominado _msoid_ en uno o varios espacios de nombres DNS de su propiedad, debe quitar el CNAME hasta el final de la fase 8 como máximo. Puede quitar el _msoid_ CNAME en cualquier momento antes del final de la fase 8. Vea el [trabajo previo para DNS](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains).

En caso de que use el inicio de sesión único para Office 365 y Azure en la instancia de Microsoft Cloud Deutschland, debe preparar y programar la migración de la suscripción de Azure en consecuencia. Asegúrese de comprender el [trabajo previo para Microsoft Azure](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure).

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD Conectar con la federación de AD FS

**Se aplica a**: Clientes con federación de AD FS

**Cuando se aplica:** antes de que se inicie la fase 2

Si usa Servicios de federación de Active Directory (AD FS), asegúrese de realizar una copia de seguridad de la  configuración de [ADFS](ms-cloud-germany-transition-add-adfs.md) antes y después de agregar la confianza de usuario de confianza para el servicio global de Office 365 antes del comienzo de la fase 2.

## <a name="phase-2-azure-ad-migration"></a>Fase 2: Migración de Azure AD

En esta fase, Azure Active Directory se migrará a la nueva región del centro de datos y se activará. Los puntos de conexión de Azure AD antiguos seguirán estando disponibles.

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online Híbrido: modificar AuthServer local

**Se aplica a:** Todos los clientes que usan una configuración Exchange híbrida activa con Exchange servidores locales

**Cuando se aplica:** después de que finalice la fase 2

El AuthServer local debe apuntar al Servicio de tokens de seguridad (STS) global para la autenticación una vez completada la migración de Azure AD.
Esto garantiza que las solicitudes de autenticación Exchange solicitudes de disponibilidad de usuarios en estado de migración destinadas al entorno local híbrido se autentican para obtener acceso al servicio local. Del mismo modo, esto garantizará la autenticación de solicitudes desde locales a Office 365 de servicios globales.
Una vez completada la migración de Azure AD (fase 2), el administrador de la topología de Exchange local (híbrida) debe agregar un nuevo punto de conexión de servicio de autenticación para los servicios Office 365 global.

Con este comando de Exchange PowerShell, reemplace por el identificador de inquilino de su organización que se encuentra en `<TenantID>` Azure Portal en Azure Active Directory.

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

Si no se completa esta tarea, es posible que las solicitudes híbridas de disponibilidad no proporcionen información a los usuarios de buzones de correo que se han migrado de Microsoft Cloud Deutschland a Office 365 servicios.

## <a name="phase-3-subscription-transfer"></a>Fase 3: Transferencia de suscripción

**Se aplica a**: Todos los clientes con un inquilino Office 365 hospedado en Microsoft Cloud Deutschland (MCD)

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|Las suscripciones se transfieren|La suscripción de Microsoft Cloud Deutschland se migrará a la suscripción Office 365 de servicios globales correspondiente. <ul><li>Microsoft Office 365 la oferta de servicios globales de esa suscripción (también conocida como _asignación de ofertas)._</li><li> Las Office 365 de servicios globales se adquieren en la Office 365 Global para las suscripciones transferidas de Microsoft Cloud Deutschland.</li><li>Las suscripciones heredadas de Microsoft Cloud Deutschland se quitan del espacio empresarial Office 365 servicios al finalizar.</li></ul>|<ul><li>Los cambios en las suscripciones existentes se bloquearán (por ejemplo, no habrá nuevas compras de suscripción ni cambios en el recuento de puestos) durante esta fase.</li><li>Se bloquearán los cambios de asignación de licencias.</li><li>Cuando se complete la migración de suscripción, los servicios Office 365 y las suscripciones de Microsoft Cloud Deutschland estarán visibles en el portal de Office 365 Admin, con el estado de las suscripciones de Microsoft Cloud Deutschland como _desaprovisionadas._</li><li>Cualquier proceso de cliente que tenga dependencias en suscripciones de Microsoft Cloud Deutschland o GUID de SKU se romperá y deberá revisarse con la oferta de Office 365 servicios.</li><li>Las nuevas suscripciones de los servicios Office 365 se comprarán con el nuevo plazo (mensual/trimestral/anual) y el cliente recibirá un reembolso prorrateado por el saldo no utilizado de la suscripción a Microsoft Cloud Deutschland.</li></ul>|
|Las licencias se reasignan|A los usuarios con licencias de Microsoft Cloud Deutschland asignadas se les asignarán licencias en la Office 365 global.|<ul><li>Los usuarios se reasignarán licencias vinculadas a las nuevas Office 365 de servicios. Las licencias de usuario de todos los usuarios se asignarán automáticamente a las nuevas características.</li><li>El número de características (planes de servicio) ofrecidos por Office 365 servicios puede ser mayor que en la oferta original de Microsoft Cloud Deutschland. Las licencias de usuario en Office 365 servicios se asignarán de forma equivalente a características similares de Microsoft Cloud Deutschland (planes de servicio).</li></ul>|
|**Tarea de administración** Deshabilitar características|El administrador debe realizar una acción explícita para deshabilitar esas características, si es necesario.|<ul><li>Los usuarios ven nuevos servicios desconocidos en el portal</li><li>Hay funcionalidad adicional disponible (por ejemplo, Microsoft Planner y Microsoft Flow), a menos que esté deshabilitada por el administrador del espacio empresarial.</li></ul> <p> Para obtener información sobre cómo deshabilitar los planes de servicio asignados a las licencias de los usuarios, [vea Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</li></ul>|
|**Tarea de administración**|Revise cualquier proceso de cliente que tenga dependencias en suscripciones de Microsoft Cloud Deutschland o GUID de SKU con la oferta Office 365 servicios de desarrollo|Los procesos de cliente siguen funcionando.|
|

**Se aplica a**: Partners de Microsoft que usan el Office 365 partner portal

Entre la fase 2 y la 3, es posible que el Portal de partners no sea accesible. Durante este tiempo, es posible que el partner no pueda tener acceso a la información del inquilino en el Portal de partners. Dado que cada migración es diferente, la duración de la accesibilidad podría ser en horas.

La información adicional para proveedores de soluciones en la nube está disponible en [Migración de inquilinos de partners.](ms-cloud-germany-transition-add-csp.md#partner-tenant-migration)

## <a name="phase-4-sharepoint-online"></a>Fase 4: SharePoint Online

**Se aplica a**: Todos los clientes que usan SharePoint Online

En caso de que aún SharePoint flujos de trabajo de 2013, limite el uso de flujos de trabajo de SharePoint 2013 durante la migración SharePoint Online.

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|SharePoint y OneDrive se transiciónn|SharePoint Online y OneDrive para la Empresa se migran de Microsoft Cloud Deutschland a Office 365 global en esta fase. <ul><li>Las direcciones URL existentes de Microsoft Cloud Deutschland se conservan (por ejemplo, `contoso.sharepoint.de` ).</li><li>Los sitios existentes se conservan.</li><li>Los tokens de autenticación del lado cliente emitidos por el Servicio de tokens de seguridad (STS) en la instancia de servicios globales de Microsoft Cloud Deutschland o Office 365 son válidos durante la transición.</li></ul>|<ul><li>El contenido será de solo lectura durante dos breves períodos durante la migración. Durante este tiempo, espere un banner "no se puede editar contenido" en SharePoint.</li><li>El índice de búsqueda no se conservará y puede tardar hasta 10 días en volver a crearse.</li><li>SharePoint El contenido OneDrive para la Empresa y en línea será de solo lectura durante dos breves períodos durante la migración. Los usuarios verán un banner "no se puede editar contenido" brevemente durante este tiempo.</li><li>Una vez completada la migración de SharePoint Online, es posible que los resultados de la búsqueda de SharePoint Online y OneDrive para la Empresa contenido no estén disponibles mientras se recompile el índice. Durante este período, es posible que las consultas de búsqueda no devuelvan resultados completos. Las características que dependen de los índices de búsqueda, como SharePoint Online News, pueden verse afectadas al volver a indizar.</li><li>SharePoint flujos de trabajo de 2013 se romperán durante la migración y deben volver a publicarse después de la migración.</li></ul>|
|**Administrador de SPO:** volver a publicar SharePoint flujos de trabajo de 2013|Un administrador SharePoint Online vuelve a publicar los flujos SharePoint 2013 después de la migración.|Se trata de una acción necesaria. Si no lo hace, puede provocar confusión del usuario, llamadas al servicio de ayuda y disminución de la productividad.|
|**Usuario de PowerShell:** actualizar al nuevo módulo|Todos los usuarios del módulo de PowerShell de SharePoint Online deben actualizar el módulo/Microsoft.SharePointOnline.CSOM a la versión 16.0.20717.12000 o posterior después de completar la migración de SharePoint Online. La finalización se comunica en el centro de mensajes.|SharePoint En línea a través de PowerShell o el modelo de objetos del lado cliente ya no se producirán errores.|
|

Consideraciones adicionales:

- Si su organización sigue SharePoint flujos de trabajo de 2010, ya no funcionarán después del 31 de diciembre de 2021. SharePoint flujos de trabajo de 2013 seguirán siendo compatibles, aunque desactivados de forma predeterminada para los nuevos inquilinos a partir del 1 de noviembre de 2020. Una vez completada la migración SharePoint el servicio en línea, se recomienda pasar a Power Automate otras soluciones admitidas.
- Los clientes de Microsoft Cloud Deutschland cuya instancia de SharePoint SharePoint Online aún no se ha migrado deben permanecer en un módulo de PowerShell en línea/Microsoft.SharePointOnline.CSOM versión 16.0.20616.12000 o inferior. De lo contrario, las conexiones SharePoint Online a través de PowerShell o el modelo de objetos del lado cliente producirán un error.
- Durante esta fase, las direcciones IP detrás del SharePoint las direcciones URL cambiarán. Después de la transición a los servicios globales de Office 365, las direcciones de las direcciones URL de inquilino conservadas (por ejemplo, y ) se cambiarán a las direcciones URL e intervalos de direcciones IP de Microsoft 365 en todo el mundo `contoso.sharepoint.de` `contoso-my.sharepoint.de` [(SharePoint Online y OneDrive para la Empresa).](/microsoft-365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business)
- Aunque SharePoint y OneDrive servicios se transiciónn, Office Online puede que no funcione como se esperaba.

> [!NOTE]
> En caso de que use eDiscovery, asegúrese de que conoce la experiencia de migración de [exhibición de documentos electrónicos.](ms-cloud-germany-transition-add-scc.md)

## <a name="phase-5-exchange-online"></a>Fase 5: Exchange Online

A partir de la fase 5, Exchange Online buzones de correo se mueven de Microsoft Cloud Deutschland a Office 365 servicios globales.

La Office 365 global de servicios se establece como predeterminada, lo que permite al servicio de equilibrio de carga interno redistribuir buzones a la región predeterminada adecuada en Office 365 servicios. En esta transición, los usuarios de ambos lados (servicios MCD o Global) están en la misma organización y pueden usar cualquier extremo de dirección URL.

La nueva región "Alemania" se agrega a la configuración de la organización. Exchange Online configuración agrega la nueva región alemana local a la organización de transición.

- Transición de usuarios y servicios de las direcciones URL mcd heredadas ( ) a las `https://outlook.office.de` nuevas Office 365 de servicios ( `https://outlook.office365.com` ).
- Los servicios Exchange Online (Outlook Web Access y Exchange Admin Center) para la nueva región del centro de datos alemán estarán disponibles desde esta fase, no estarán disponibles antes.
- Los usuarios pueden seguir teniendo acceso al servicio a través de direcciones URL mcd heredadas durante la migración, pero deben dejar de usar las direcciones URL heredadas al finalizar la migración.
- Los usuarios deben pasar a usar el portal de Office para Office en línea (calendario, correo, personas). La navegación a los servicios que aún no se han migrado a Office 365 no funcionarán hasta que se migren.
- Esta limitación también se aplica a servicios en segundo plano como "Mi cuenta". Mi cuenta para servicios globales estará disponible después de finalizar la fase 9. Hasta este momento, los usuarios deben usar el portal mcd para administrar la configuración de su cuenta.
- El Outlook Web App no proporcionará la experiencia de carpetas públicas durante la migración.

Si desea modificar las fotos de usuario durante la fase 5, vea [Exchange Online PowerShell - Set-UserPhoto durante la fase 5](#exchange-online-powershell).

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>Registro DNS para detección automática en Exchange Online

**Se aplica a:** Clientes que usan Exchange Online con un dominio personalizado

La configuración dns administrada por el cliente para la detección automática que actualmente apunta a Microsoft Cloud Deutschland debe actualizarse para hacer referencia al extremo global de Office 365 al finalizar la fase Exchange Online (fase 5).

Las entradas DNS existentes con CNAME que apuntan a autodiscover-outlook.office.de deben actualizarse para que apunten a **autodiscover.outlook.com**.

Los clientes que no realicen estas actualizaciones de DNS al finalizar la fase de migración **9** pueden experimentar problemas de servicio cuando finalice la migración.

> [!NOTE]
> Los errores de validación en el Centro de administración para dominios personalizados para la entrada Detección automática se pueden omitir. Los servicios solo funcionarán correctamente cuando el registro CNAME se haya cambiado a autodiscover.outlook.com.

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell

**Se aplica a: Exchange Online** administradores con Exchange Online PowerShell

Durante la fase de migración, el uso de los cmdlets de PowerShell **New-MigrationEndpoint**, **Set-MigrationEndpoint** y **Test-MigrationsServerAvailability** puede provocar errores (error en el proxy). Esto sucede cuando el buzón de arbitraje ha migrado a todo el mundo, pero el buzón de administración no lo ha hecho o viceversa. Para resolver esto, al crear la sesión de PowerShell del inquilino, use el buzón de arbitraje como sugerencia de enrutamiento en **ConnectionUri**. Por ejemplo:

```powershell
New-PSSession
    -ConfigurationName Microsoft.Exchange
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

El uso del cmdlet **Set-UserPhoto** de PowerShell genera un error si se ha migrado un buzón de usuario pero no se ha migrado un buzón de administrador o viceversa. En esta situación, un administrador debe pasar el identificador de correo electrónico del usuario cuya foto debe cambiarse al crear la sesión de `ConnectionUri` PowerShell del inquilino:

```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>"
```

donde `<user_email>` es el marcador de posición del identificador de correo electrónico del buzón de usuario.

Consideraciones adicionales:

- Se pedirá a los usuarios de Outlook Web App que tienen acceso a un buzón compartido en el otro entorno (por ejemplo, un usuario del entorno MCD tiene acceso a un buzón compartido en el entorno global) para que se autentiquen por segunda vez. El usuario debe autenticarse primero y tener acceso a su buzón en y, a continuación, abrir el buzón `outlook.office.de` compartido que se encuentra en `outlook.office365.com` . Necesitarán autenticarse una segunda vez al obtener acceso a los recursos compartidos hospedados en el otro servicio.
- Para los clientes de Microsoft Cloud Deutschland existentes o aquellos en transición, cuando se agrega un buzón compartido a Outlook mediante archivo **> Información >** Agregar cuenta, es posible que se fallen los permisos del calendario (el cliente de Outlook intenta usar la API de Rest `https://outlook.office.de/api/v2.0/Me/Calendars` ). Los clientes que quieran agregar una cuenta para ver permisos de calendario pueden agregar la clave del Registro tal como se describe en Cambios de experiencia del usuario para compartir un calendario en [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantizar que esta acción se realice correctamente. Esta clave del Registro se puede implementar en toda la organización mediante la directiva de grupo.
- Todos los clientes que usan una configuración híbrida de Exchange activa no pueden mover buzones de correo de Exchange Server local a Exchange Online, ni a Microsoft Cloud Deutschland, ni a la nueva región del centro de datos en Alemania. Los clientes deben asegurarse de que los movimientos de buzones en curso se han completado antes de la fase 5 y se reanudarán después de completar esta fase.
- Ejecutar , un cmdlet de PowerShell, durante la migración de `Test-MigrationServerAvailabiilty` Exchange de Microsoft Cloud Deutschland a Office 365 servicios no funcionan. Sin embargo, funcionará correctamente una vez completada la migración.
- Si los clientes tienen problemas con las credenciales o la autorización después de migrar los buzones, vuelva a escribir las credenciales de administrador local en el extremo de migración ejecutando o estableciendo lo mismo mediante el Panel de control de Exchange `Set-MigrationEndpoint -Identity <endpointName> -Credential $(Get-Credential)` (ECP).
- Asegúrese de que todos los usuarios que usan protocolos heredados (POP3/IMAP4/SMTP) para sus dispositivos estén preparados para cambiar los puntos de conexión en su cliente después de que su buzón de Exchange se haya movido a la nueva región del centro de datos alemán, tal como se describe en los pasos previos a la migración [de Exchange Online](ms-cloud-germany-transition-add-pre-work.md#exchange-online).
- La programación Skype Empresarial reuniones en Outlook Web App ya no está disponible después de migrar el buzón. Si es necesario, los usuarios deben usar Outlook en su lugar.

Para obtener más información sobre las diferencias de las organizaciones en la migración y después de migrar los recursos de Exchange Online, revise la información de la experiencia del cliente durante la migración a los servicios [Office 365](ms-cloud-germany-transition-experience.md)en las nuevas regiones del centro de datos alemán.

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>Fase 6: Exchange Online Protection / Seguridad y cumplimiento

**Se aplica a:** Todos los clientes que usan Exchange Online

Las características de Exchange Online Protection back-end (EOP) se copian en la nueva región "Alemania". Exchange Online permite el enrutamiento de hosts externos a Office 365 y se migran detalles históricos del inquilino, que también incluye servicios back-end para características de seguridad y cumplimiento.

Los clientes que Exchange Online solo (no híbridos) no necesitan prestar atención en esta fase.

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online Implementaciones híbridas

**Se aplica a:** Todos los clientes que usan una configuración Exchange híbrida activa con Exchange servidores locales

Asegúrese de que [el Exchange se](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) haya aplicado antes de que comience la fase **5 del paso de migración.** Exchange Online los clientes híbridos deben ejecutar la versión más reciente del Asistente para configuración híbrida (HCW) de Exchange en modo "Office 365 Alemania" para preparar la configuración local para la migración Office 365 servicios globales.

**Acciones de administración:**

- Entre el inicio de la fase de migración 6 y la finalización de la fase de migración 9 (cuando se publica el aviso del Centro de mensajes), debe ejecutar el HCW de nuevo con la configuración de Office 365 Worldwide para apuntar los sistemas locales a los servicios globales de Office 365. Si no se completa esta tarea antes de la fase 9 [Migración completada], es posible que los NDR para el correo enrutado entre la implementación Exchange local y Office 365.
- Detenga o elimine los movimientos de buzones de correo de incorporación o de incorporación, es decir, no mueva buzones entre Exchange local y Exchange Online.  Esto garantiza que las solicitudes de movimiento del buzón no fallen con un error. Si no lo hace, puede producirse un error en el servicio o en Office cliente.
- Los Send-Connectors adicionales que se han creado además del conector creado por el HCW y que están destinados a Exchange Online deben actualizarse en esta fase inmediatamente después de ejecutar la ejecución de HCW, de lo contrario dejarán de funcionar. El dominio TLS debe actualizarse para estos conectores de envío. <br> Para actualizar el dominio TLS, use el siguiente comando de PowerShell en el entorno Exchange Server usuario:

```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online---transition-to-microsoft-teams"></a>Fase 7: Skype Empresarial Online: transición a Microsoft Teams

**Se aplica a:** Todos los clientes que usan Skype Empresarial Online

Revise los [pasos previos a la migración Skype Empresarial migración](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) en línea y asegúrese de completar todos los pasos.
En esta fase, Skype Empresarial se migrará a Microsoft Teams. Los Skype Empresarial existentes se migran Office 365 los servicios globales de Office 365 en Europa y, a continuación, se pasa a Microsoft Teams en la región "Alemania" de Office 365 servicios.

- Los usuarios no podrán iniciar sesión en la Skype Empresarial la fecha de migración. Diez días antes de la migración, el cliente recibirá un mensaje en el Centro de administración que anuncia cuándo se llevará a cabo la migración y de nuevo cuando comience la migración.
- Se migra la configuración de la directiva.
- Los usuarios se migrarán a Teams y ya no tendrán acceso a Skype Empresarial después de la migración.
- Los usuarios deben tener el Microsoft Teams de escritorio instalado. La instalación se realizará durante los 10 días mediante la directiva en la infraestructura de Skype Empresarial, pero si esto falla, los usuarios seguirán teniendo que descargar el cliente o conectarse con un explorador compatible.
- Los contactos y reuniones se migrarán a Microsoft Teams.
- Los usuarios no podrán iniciar sesión para iniciar sesión Skype Empresarial las transiciones de servicio de tiempo a Office 365 servicios y no hasta que se completen las entradas dns del cliente.
- Los contactos y las reuniones existentes seguirán funcionando como Skype Empresarial reuniones.

Cuando se ha configurado un dominio de vanidad para Skype Empresarial, las entradas DNS deben actualizarse. Consulte Dominios [en el Centro de administración de Microsoft 365](https://admin.microsoft.com/Adminportal/Home#/Domains) y aplique los cambios en la configuración de DNS.

Si tiene que conectarse a Skype Empresarial Online con PowerShell una vez completada la fase de migración 9, use el siguiente código de PowerShell para conectarse:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential
```

### <a name="known-limitations-until-finalizing-azure-ad-migration"></a>Limitaciones conocidas hasta finalizar la migración de Azure AD
Microsoft Teams está aprovechando las características de Azure AD. Aunque la migración de Azure AD no se ha completado, algunas características Microsoft Teams no están totalmente disponibles. Después de la fase 9, cuando se haya finalizado la migración de Azure AD, las siguientes características estarán totalmente disponibles:

- Las aplicaciones no se pueden administrar en el centro Microsoft Teams administración.
- Solo se pueden crear nuevos equipos en el Microsoft Teams a menos que el administrador de Teams haya limitado los permisos para que los usuarios creen nuevos equipos. No se pueden crear nuevos equipos en el centro Microsoft Teams administración.
- La versión web de Microsoft Teams no está disponible.

## <a name="phase-8-dynamics-365"></a>Fase 8: Dynamics 365

**Se aplica a:** Todos los clientes que usan Microsoft Dynamics 365

Asegúrese de que está familiarizado con el trabajo previo para el procedimiento de [instalación de Microsoft Dynamics 365.](ms-cloud-germany-transition-add-pre-work.md#dynamics-365)

Los clientes con Dynamics 365 requieren una participación adicional para migrar las organizaciones de Dynamics de la organización de forma independiente.

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|Recursos de Microsoft Dynamics|Microsoft Engineering o Microsoft FastTrack contratarán a los clientes con Microsoft Dynamics para realizar la transición de Microsoft Dynamics 365 a la Office 365 de servicios globales.\*|<ul><li>Después de la migración, el administrador valida la organización.</li><li>El administrador modifica los flujos de trabajo según sea necesario.</li><li>El administrador borra el modo AdminOnly según corresponda.</li><li>El administrador cambia el tipo de organización de _Espacio aislado_, según corresponda</li><li>Notificar a los usuarios finales de la nueva dirección URL para obtener acceso a la instancia (org).</li><li>Actualice las conexiones entrantes a la nueva dirección URL del extremo.</li><li>El servicio Dynamics no estará disponible para los usuarios durante la transición.</li><li>Los usuarios deben validar el estado de la organización y las características después de la migración de cada organización.</li></ul>|
|

\* (i) Los clientes con Microsoft Dynamics 365 deben tomar medidas en este escenario de migración según se define en el proceso de migración proporcionado. (ii) Si el cliente no toma medidas, Microsoft no podrá completar la migración. (iii) Cuando Microsoft no puede completar la migración debido a la inacción del cliente, la suscripción del cliente expirará el 29 de octubre de 2021.

## <a name="phase-8-power-bi"></a>Fase 8: Power BI

**Se aplica a:** Todos los clientes que usan Microsoft Power BI (PBI)

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|Migración de Power BI recursos|Microsoft Engineering o Microsoft FastTrack contratarán a los clientes con Microsoft Power BI (PBI) después de desencadenar manualmente una herramienta de migración de PBI existente para realizar la transición Power BI la instancia de servicios globales de Office 365.\*\*|<ul><li>Los siguientes Power BI no _se_ realizarán la transición y tendrán que volver a crearse: <</li><li>Conjuntos de datos en tiempo real (por ejemplo, conjuntos de datos de streaming o inserción).</li><li>Power BI configuración de puerta de enlace de datos local y origen de datos.</li><li>Los informes creados sobre los conjuntos de datos en tiempo real no estarán disponibles después de la migración y deben volver a crearse.</li><li>Power BI servicios no estarán disponibles para los usuarios durante la transición. La indisponibilidad del servicio no debe ser superior a 24 horas.</li><li>Los usuarios tendrán que volver a configurar los orígenes de datos y sus puertas de enlace de datos locales con el Power BI después de la migración.  Hasta que lo hagan, los usuarios no podrán usar estos orígenes de datos para realizar actualizaciones programadas o consultas directas en estos orígenes de datos.</li><li>Las capacidades y las áreas de trabajo premium no se pueden migrar. Los clientes deben eliminar todas las capacidades antes de la migración y volver a crearlas después de la migración. Vuelva a mover las áreas de trabajo a las capacidades deseadas.</li></ul>|
|

\*\*(i) Los clientes con Microsoft Power BI deben tomar medidas en este escenario de migración, tal como se define en el proceso de migración proporcionado. (ii) Si el cliente no toma medidas, Microsoft no podrá completar la migración. (iii) Cuando Microsoft no puede completar la migración debido a la inacción del cliente, la suscripción del cliente expirará el 29 de octubre de 2021.

## <a name="phase-9-office-apps"></a>Fase 9: Office aplicaciones

**Se aplica a:** Todos los clientes que usan Office de escritorio (Word, Excel, PowerPoint, Outlook, OneDrive ...)

En esta fase, todas las aplicaciones cliente y Office Online realizan el recorte de cliente. Azure AD ultima el ámbito del espacio empresarial para que apunte a los servicios Office 365 y los puntos de conexión relacionados.

Office 365 los inquilinos que se encuentran en la región "Alemania" requieren que todos los usuarios cierren, cierren sesión desde Office 365 y vuelvan a iniciar sesión para todas las aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, etc.) y un cliente OneDrive para la Empresa después de que la migración del espacio empresarial haya alcanzado la fase 9. Al iniciar sesión, permite a los Office obtener nuevos tokens de autenticación del servicio global de Azure AD.

En caso de que Office las aplicaciones de escritorio de Office no funcionen después de iniciar sesión e iniciar sesión desde las aplicaciones, se recomienda encarecidamente ejecutar la Herramienta de recorte de cliente [(OCCT)](https://github.com/microsoft/OCCT) de Office en el equipo afectado para solucionar el problema.

Si la Office herramienta de recorte de cliente [(OCCT)](https://github.com/microsoft/OCCT) se ha implementado y programado en clientes de Windows por adelantado, no es necesario el procedimiento de inicio de sesión o de salida.

La mejor experiencia del usuario se puede garantizar mediante el uso de aplicaciones Office recientes. Las empresas deben considerar el uso del canal de Enterprise mensual.

Asegúrese de que ha completado el [procedimiento de pretrabajo para dispositivos](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) móviles.

Consideraciones adicionales:

- Notificar a los usuarios que cierren todas las aplicaciones de Office y, a continuación, vuelvan a iniciar sesión (o forzar a los clientes a reiniciarse y a los usuarios a iniciar sesión) para permitir Office los clientes que puedan tomar el cambio.
- Notifique a los usuarios y al personal de servicio de ayuda que los usuarios pueden ver un banner de Office que les pida que reactiven las aplicaciones Office dentro de las 72 horas siguientes al recorte.
- Todas Office aplicaciones en máquinas personales deben cerrarse y los usuarios deben cerrar sesión y volver a iniciar sesión. En la barra de activación amarilla, inicie sesión para reactivarse en Office 365 servicios.
- Las máquinas compartidas requerirán acciones similares a las máquinas personales y no requerirán un procedimiento especial.
- En dispositivos móviles, los usuarios deben cerrar sesión en las aplicaciones, cerrarlas y, a continuación, iniciar sesión de nuevo.

## <a name="phase-9-line-of-business-apps"></a>Fase 9: Aplicaciones de línea de negocio

**Se aplica a:** Todos los clientes que usan aplicaciones de línea de negocio conectadas a Office 365

En caso de que tenga aplicaciones de línea de negocio, asegúrese de que ha completado el procedimiento de pretrabajo para aplicaciones de línea [de](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) negocio.

## <a name="phase-9--10-azure-ad-finalization"></a>Fase 9 & 10: Azure AD Finalization

**Se aplica a:** Todos los clientes

Cuando el inquilino Office 365 completa el paso final de la migración (Fase 9: Azure AD Finalization), todos los servicios se transiciónn a todo el mundo. Ninguna aplicación o usuario debe tener acceso a los recursos del inquilino en ninguno de los puntos de conexión de Microsoft Cloud Deutschland. Automáticamente, 30 días después de que finalice la finalización, el servicio Microsoft Cloud Deutschland Azure AD detendrá el acceso de puntos de conexión para el inquilino en transición. Las solicitudes de extremo, como la autenticación, producirán un error a partir de este momento en el servicio Microsoft Cloud Deutschland.

Microsoft Azure clientes deben realizar la transición de sus cargas de trabajo de Azure siguiendo los pasos descritos en el libro de juegos de migración de [Azure](/azure/germany/germany-migration-main) tan pronto como su inquilino complete la migración a todo el mundo (fase 9).

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|Actualizar puntos de conexión de usuario|Garantizar que todos los usuarios accedan al servicio con los extremos de Microsoft en todo el mundo adecuados|30 días después de finalizar la migración, los puntos de conexión de Microsoft Cloud Deutschland dejarán de cumplir las solicitudes; se producirá un error en el tráfico de cliente o aplicación.|
|Actualizar puntos de conexión de aplicaciones de Azure AD|Debe actualizar los puntos de conexión de autenticación, Azure Active Directory (Azure AD) (Azure AD) Graph y MS Graph para las aplicaciones a los del servicio de Microsoft Worldwide.|30 días después de finalizar la migración, los puntos de conexión de Microsoft Cloud Deutschland dejarán de cumplir las solicitudes; se producirá un error en el tráfico de cliente o aplicación.|
|Migrar cargas de trabajo de Azure|Los clientes de servicios de Azure deben aprovisionar nuevas suscripciones mundiales para los servicios de Azure y ejecutar la migración según el libro de [reproducción de migración de Azure](/azure/germany/germany-migration-main).|Cuando se haga la transición completa al servicio mundial (fase 10), los clientes ya no podrán acceder a las cargas de trabajo de Azure presentes en Microsoft Cloud Deutschland Azure Portal.|
|

**Se aplica a:** Clientes con dispositivos registrados o unidos de Azure AD

Una vez completada la fase 9, los dispositivos registrados y unidos de Azure AD deben conectarse a la instancia de Azure AD en transición en la nueva región del centro de datos alemán.
Es posible que los dispositivos que no se vuelvan a unir a Azure AD ya no funcionen al final de la fase 10. Para obtener instrucciones detalladas y más detalles, consulte [la información adicional acerca de los dispositivos](ms-cloud-germany-transition-add-devices.md).

### <a name="azure-ad-connect"></a>Azure AD Connect

**Se aplica a:** Todos los clientes sincronizan identidades con Azure AD connect

<br>

****

|Pasos|Descripción|Impacto|
|---|---|---|
|Actualice Azure AD Conectar.|Una vez completado el recorte a Azure AD, la organización usa completamente los servicios Office 365 y ya no está conectada a Microsoft Cloud Deutschland. En este momento, el cliente debe asegurarse de que el proceso de sincronización delta se ha finalizado y, después, cambiar el valor de cadena de `AzureInstance` 3 (Microsoft Cloud Deutschland) a 0 en la ruta de acceso del Registro `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` .|Cambie el valor de `AzureInstance` , la clave del Registro. Si no lo hace, los objetos no se sincronizarán después de que los puntos de conexión de Microsoft Cloud Deutschland ya no estén disponibles.|
|

## <a name="post-migration"></a>Después de la migración

Asegúrese de leer el artículo [actividades posteriores a la migración](ms-cloud-germany-transition-add-experience.md) y ejecutarlas en consecuencia.
