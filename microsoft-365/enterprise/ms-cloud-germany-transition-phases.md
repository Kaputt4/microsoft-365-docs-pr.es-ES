---
title: Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland (general)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
ms.openlocfilehash: 98a547a9af772e880465f75d9a3b01b1795639e1
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711957"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland (general)

Las migraciones de inquilinos de Microsoft Cloud Deutschland (MCD) a la región "Alemania" de los servicios globales de Office 365 de Microsoft se ejecutan como un conjunto de fases y sus acciones configuradas para cada carga de trabajo. Esta figura muestra las nueve fases de migración a los nuevos centros de datos alemanes.

![Las nueve fases de migración a los nuevos centros de datos de Alemania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

El proceso de migración se completará durante varias semanas en función del tamaño general y la complejidad de la organización. Mientras la migración está en curso, los usuarios y administradores pueden seguir usando los servicios con cambios notables detallados en esta documentación. El gráfico y la tabla definen fases y pasos durante la migración.

|Paso|Duración|Responsable|Descripción|
|:--------|:--------|:--------|:--------|
|Opt-In|Horas|Clientes|Opte por la organización en la migración.|
|Pre-Work|Días|Clientes|Complete el trabajo necesario para preparar usuarios, estaciones de trabajo y red para la migración.|
|Azure Active Directory (Azure AD)|De 1 a 2 días|Microsoft|Migre la organización de Azure AD a todo el mundo.|
|Azure|Semanas|Clientes|Crear nuevas suscripciones de Azure a nivel mundial y servicios de Azure de transición.|
|Suscripción & de licencias|De 1 a 2 días|Microsoft|Compre suscripciones mundiales, cancele las suscripciones de Microsoft Cloud Deutschland y las licencias de usuario de transición.|
|SharePoint y OneDrive|Más de 15 días|Microsoft|Migre el contenido de SharePoint y OneDrive para la Empresa, conservando sharepoint.de direcciones URL.|
|Exchange en línea|Más de 15 días|Microsoft|Migrar el contenido de Exchange Online y la transición a direcciones URL de todo el mundo.|
|Seguridad y cumplimiento|De 1 a 2 días|Microsoft|Seguridad de transición & de cumplimiento y contenido.|
|Skype Empresarial|De 1 a 2 días|Microsoft|Transición de Skype Empresarial a Microsoft Teams.|
|Power BI & Dynamics 365|Más de 15 días|Microsoft|Migrar contenido de Power BI y Dynamics 365.|
|Finalizar Azure AD|De 1 a 2 días|Microsoft|Completar el recorte de inquilinos a todo el mundo.|
|Clean-Up|De 1 a 2 días|Clientes|Limpie las conexiones heredadas a Microsoft Cloud Deutschland, como los reinicios de cliente de Office, Azure AD Connect y Servicios de federación de Active Directory (AD FS).|

Las fases y sus acciones garantizan que los datos y experiencias críticos se migren a los servicios globales de Office 365. Después de agregar el espacio empresarial a la cola de migración, cada carga de trabajo se completará como un conjunto de pasos que se ejecutan en el servicio back-end. Algunas cargas de trabajo pueden requerir acciones del administrador (o usuario) o la migración puede afectar al uso de las fases que se ejecutan y se analizan en ¿Cómo se organiza la [migración?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Las secciones siguientes contienen acciones y efectos para las cargas de trabajo a medida que avanzan a través de varias fases de la migración. Revise las tablas y determine qué acciones o efectos son aplicables a su organización. Asegúrese de que está preparado para ejecutar los pasos en las fases correspondientes según sea necesario. Si no se completan los pasos necesarios, se puede producir una interrupción del servicio y puede retrasar la finalización de la migración a los servicios de Office 365.

## <a name="opt-in"></a>Opt-In

**Se aplica a**: Todos los clientes con un inquilino de Office 365 hospedado en Microsoft Cloud Deutschland (MCD)

| Pasos | Descripción | Impacto |
|:-------|:-----|:-------|
| No podemos migrar inquilinos de Office 365 hospedados en mcd sin consentimiento. | Microsoft obtiene el derecho de migrar de dos maneras, lo que permite a Microsoft organizar la transición de datos y servicios a la instancia de servicios globales de Office 365. <ol><li>El administrador de inquilinos de Office 365 opta por la migración controlada por Microsoft. </li><li> Los clientes renuevan cualquier suscripción en su inquilino de MCD Office 365 después del 1 de mayo de 2020. Notificaremos a estos clientes sobre el derecho de migración cada mes, esperaremos 30 días para dar a los clientes la oportunidad de cancelar y, a continuación, participaremos directamente.</li></ol> | <ul><li>El espacio empresarial se marca como consentido para la migración y el Centro de administración muestra la confirmación. </li><li>La confirmación se publica en el Centro de mensajes del inquilino de Office 365. La configuración del servicio continúa desde los puntos de conexión de Microsoft Cloud Deutschland. </li><li>El administrador de inquilinos debe supervisar el Centro de mensajes de Office 365 para obtener actualizaciones sobre el estado de la fase de migración. </li></ul>|

## <a name="subscription-phase-3"></a>Suscripción (fase 3)

**Se aplica a**: Todos los clientes con un inquilino de Office 365 hospedado en Microsoft Cloud Deutschland (MCD)

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Las suscripciones se transfieren y las licencias se reasignan. | Las suscripciones de servicios globales de Office 365 correspondientes se adquieren en la instancia global de Office 365 para las suscripciones transferidas de Microsoft Cloud Deutschland. A los usuarios con licencias de Microsoft Cloud Deutschland asignadas se les asignarán licencias en la instancia global de Office 365. Las suscripciones heredadas de Microsoft Cloud Deutschland se quitan del inquilino de servicios de Office 365 al finalizar.| <ul><li>Los cambios en las suscripciones existentes se bloquearán (por ejemplo, no habrá nuevas compras de suscripción ni cambios en el recuento de puestos) durante esta fase.</li><li>Se bloquearán los cambios de asignación de licencias.</li><li>La suscripción de Microsoft Cloud Deutschland se migrará a la suscripción de servicios globales de Office 365 correspondiente. Microsoft define la oferta de servicios globales de Office 365 de esa suscripción (también conocida como _asignación de ofertas)._</li><li>El número de características (planes de servicio) ofrecidos por los servicios de Office 365 puede ser mayor que en la oferta original de Microsoft Cloud Deutschland. Las licencias de usuario de los servicios de Office 365 se asignarán de forma equivalente a características similares de Microsoft Cloud Deutschland (planes de servicio). Las licencias de usuario de todos los usuarios se asignarán automáticamente a las nuevas características. El administrador debe realizar una acción explícita para deshabilitar esas licencias, si es necesario. </li><li>Cuando se complete la migración de suscripción, los servicios de Office 365 y las suscripciones de Microsoft Cloud Deutschland estarán visibles en el Portal de administración de Office 365, con el estado de las suscripciones de Microsoft Cloud Deutschland como _desaprovisionadas._ </li><li>Los usuarios se reasignarán licencias vinculadas a las nuevas suscripciones de servicios de Office 365. Cualquier proceso de cliente que tenga dependencias en suscripciones MCD o GUID de SKU se romperá y deberá revisarse con la oferta de servicios de Office 365. </li><li>Las nuevas suscripciones en los servicios de Office 365 se comprarán con el nuevo plazo (mensual/trimestral/anual) y el cliente recibirá un reembolso prorrateado por el saldo sin usar de la suscripción de Microsoft Cloud Deutschland. </li><li>Los inquilinos de Microsoft Cloud Deutschland asociados no se migrarán. Los clientes de CSP se migrarán a los servicios de Office 365 en el nuevo inquilino de servicios de Office 365 del mismo partner. Después de la migración de clientes, el partner solo puede administrar este cliente desde el inquilino de servicios de Office 365. </li><li>La funcionalidad adicional está disponible (por ejemplo, Microsoft Planner y Microsoft Flow), a menos que esté deshabilitada por el administrador del espacio empresarial. Para obtener información sobre cómo deshabilitar los planes de servicio asignados a las licencias de los usuarios, vea [Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fase 4)

**Se aplica a**: Todos los clientes que usan SharePoint Online

| Pasos | Descripción | Impacto |
|:-------|:-----|:-------|
| SharePoint y OneDrive se transiciónn | SharePoint Online y OneDrive para la Empresa se migran de Microsoft Cloud Deutschland a los servicios globales de Office 365 en esta fase.<br><ul><li>Las direcciones URL existentes de Microsoft Cloud Deutschland se conservan (por ejemplo, `contoso.sharepoint.de` ).</li><li>Los sitios existentes se conservan.</li><li>Los tokens de autenticación del lado cliente emitidos por el Servicio de tokens de seguridad (STS) en la instancia de servicios globales de Microsoft Cloud Deutschland u Office 365 son válidos durante la transición.</li></ul>|<ul><li>El contenido será de solo lectura durante dos breves períodos durante la migración. Durante este tiempo, espere un banner "no puede editar contenido" en SharePoint.</li><li>El índice de búsqueda no se conservará y puede tardar hasta 10 días en volver a crearse.</li><li>El contenido de SharePoint Online y OneDrive para la Empresa será de solo lectura durante dos breves períodos durante la migración. Los usuarios verán un banner "no se puede editar contenido" brevemente durante este tiempo.</li><li>Una vez completada la migración de SharePoint Online, es posible que los resultados de la búsqueda del contenido de SharePoint Online y OneDrive para la Empresa no estén disponibles mientras se recompile el índice. Durante este período, es posible que las consultas de búsqueda no devuelvan resultados completos. Las características que dependen de índices de búsqueda, como SharePoint Online News, pueden verse afectadas al volver a indizar.</li></ul>|
||||

Consideraciones adicionales:

- Si su organización todavía usa flujos de trabajo de SharePoint 2010, ya no funcionarán después del 31 de diciembre de 2021. Los flujos de trabajo de SharePoint 2013 seguirán siendo compatibles, aunque desactivados de forma predeterminada para los nuevos inquilinos a partir del 1 de noviembre de 2020. Una vez completada la migración al servicio de SharePoint Online, se recomienda pasar a Power Automate u otras soluciones compatibles.

- Los clientes de Microsoft Cloud Deutschland cuya instancia de SharePoint Online aún no se ha migrado necesitan permanecer en el módulo de PowerShell de SharePoint Online/Microsoft.SharePointOnline.CSOM versión 16.0.20616.12000 o posterior. De lo contrario, las conexiones a SharePoint Online a través de PowerShell o el modelo de objetos del lado cliente producirán un error.

- Los clientes de Microsoft Cloud Deutschland cuya instancia de SharePoint Online se migra deben actualizar el módulo de PowerShell de SharePoint Online/Microsoft.SharePointOnline.CSOM a la versión 16.0.20717.12000 o posterior. De lo contrario, las conexiones a SharePoint Online a través de PowerShell o el modelo de objetos del lado cliente producirán un error.

## <a name="exchange-online-phase-5"></a>Exchange Online (fase 5)

**Se aplica a:** Todos los clientes que usan Exchange Online

Si usa Exchange Online híbrido: los administradores híbridos de Exchange Online deben ejecutar el Asistente para configuración híbrida  **(HCW)** varias veces como parte de esta transición. Vea los [pasos de migración avanzados de pretrabajo para Exchange](ms-cloud-germany-transition-add-experience.md#exchange-online-before-phase-5)

Como se describe en el trabajo previo de [migración,](ms-cloud-germany-transition-add-pre-work.md#exchange-online)antes de que comience la fase 5 del paso de **migración,** los clientes híbridos de Exchange Online deben ejecutar la versión más reciente del Asistente para la configuración híbrida de Exchange (HCW) en modo "Office 365 Germany" para preparar la configuración local para la migración a los servicios globales de Office 365.

Una vez completada la fase de migración **5** (cuando se publica el aviso del Centro de mensajes), debe ejecutar el HCW de nuevo con la configuración de Office 365 Worldwide para apuntar los sistemas locales a los servicios globales de Office 365. Es posible que se requieran actualizaciones adicionales de DNS si usa dominios personalizados.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Los buzones de Exchange Online se mueven de Microsoft Cloud Deutschland a los servicios globales de Office 365.| La configuración de Exchange Online agrega la nueva región alemana local a la organización de transición. La región servicios globales de Office 365 se establece como predeterminada, lo que permite al servicio de equilibrio de carga interno redistribuir buzones a la región predeterminada adecuada en los servicios de Office 365. En esta transición, los usuarios de ambos lados (servicios MCD o Global) están en la misma organización y pueden usar cualquier extremo de dirección URL. |<ul><li>Transición de usuarios y servicios de las direcciones URL de MCD heredadas (outlook.office.de) a las nuevas direcciones URL de servicios de Office 365 ( `https://outlook.office365.com` ).</li><li>Los usuarios pueden seguir teniendo acceso al servicio a través de direcciones URL mcd heredadas durante la migración, pero deben dejar de usar las direcciones URL heredadas al finalizar la migración.</li><li>Los usuarios deben pasar a usar el portal de Office mundial para las características de Office Online (Calendario, Correo, Personas). La navegación a los servicios que aún no se han migrado a los servicios de Office 365 no funcionará hasta que se migren. </li><li>Outlook Web App no proporcionará la experiencia de carpetas públicas durante la migración. </li></ul>|
| Actualizar la configuración de DNS personalizada para detección automática| La configuración dns administrada por el cliente para la detección automática que actualmente apunta a Microsoft Cloud Deutschland debe actualizarse para hacer referencia al extremo global de Office 365 al finalizar la fase de Exchange Online (fase 5). <br> Las entradas DNS existentes con CNAME que apuntan a autodiscover-outlook.office.de deben actualizarse para que apunten a autodiscover.outlook.com. |  Las solicitudes de disponibilidad y las llamadas de detección de servicio a través de detección automática apuntan directamente a los servicios de Office 365. Los clientes que no realizan estas actualizaciones dns pueden experimentar problemas de servicio de detección automática cuando se completa la migración. |
||||

Consideraciones adicionales:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` solo funcionará después del recorte del espacio empresarial en la fase 9. Los vínculos producirán mensajes de error de "algo salió mal" hasta ese momento.

- Se pedirá a los usuarios de Outlook Web App que tienen acceso a un buzón compartido en el otro entorno (por ejemplo, un usuario del entorno MCD tiene acceso a un buzón compartido en el entorno global) para que se autentiquen por segunda vez. El usuario debe autenticarse primero y tener acceso a su buzón en y, a continuación, abrir el buzón `outlook.office.de` compartido que se encuentra en `outlook.office365.com` . Necesitarán autenticarse una segunda vez al obtener acceso a los recursos compartidos hospedados en el otro servicio.

- Para los clientes de Microsoft Cloud Deutschland existentes o los que están en transición, cuando se agrega un buzón compartido a Outlook mediante Archivo **> Información >** Agregar cuenta, es posible que se fallen los permisos del calendario (el cliente de Outlook intenta usar la API de Rest `https://outlook.office.de/api/v2.0/Me/Calendars` ).) Los clientes que quieran agregar una cuenta para ver permisos de calendario pueden agregar la clave del Registro como se describe en Cambios de experiencia de usuario para compartir un calendario en [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantizar que esta acción se realice correctamente. Esta clave del Registro se puede implementar en toda la organización mediante la directiva de grupo.

- Durante la fase de migración, el uso de los cmdlets de PowerShell **New-migrationEndpoint**, **Set-MigrationEndpoint** y **Test-MigrationsServerAvailability** puede provocar errores (error en el proxy). Esto sucede cuando el buzón de arbitraje ha migrado a todo el mundo, pero el buzón de administración no lo ha hecho o viceversa. Para resolver esto, al crear la sesión de PowerShell del inquilino, use el buzón de arbitraje como sugerencia de enrutamiento en **ConnectionUri**. Por ejemplo:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Para obtener más información sobre las diferencias de las organizaciones en la migración y después de migrar los recursos de Exchange Online, revise la información de la experiencia del cliente durante la migración a los servicios de [Office 365](ms-cloud-germany-transition-experience.md)en las nuevas regiones del centro de datos alemán.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Protección y seguridad y cumplimiento de Exchange Online (fase 6)

**Se aplica a:** Todos los clientes que usan Exchange Online<br>

Las características back-end de Exchange Online Protection (EOP) se copian en la nueva región "Alemania".

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Migración del enrutamiento de Exchange Online y detalles de mensajes históricos. | Exchange Online habilita el enrutamiento desde hosts externos a Office 365. Los registros MX externos se transiciónn para enrutar al servicio EOP. Se migran la configuración del espacio empresarial y los detalles históricos. |<ul><li>Las entradas DNS administradas por Microsoft se actualizan de Office 365 Germany EOP a los servicios de Office 365.</li><li>Los clientes deben esperar 30 días después de la escritura dual de EOP para la migración de EOP. De lo contrario, puede haber pérdida de datos.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype Empresarial Online (fase 7)

**Se aplica a:** Todos los clientes que usan SharePoint Online

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Migración de Skype Empresarial a Teams. | Los clientes existentes de Skype Empresarial se migran a los servicios globales de Office 365 en Europa y, a continuación, se transiciónn a Microsoft Teams en la región "Alemania" de servicios de Office 365. |<ul><li>Los usuarios no podrán iniciar sesión en Skype Empresarial en la fecha de migración. Diez días antes de la migración, publicaremos en el Centro de administración para que sepa cuándo se llevará a cabo la migración y, de nuevo, cuando iniciemos la migración.</li><li> Se migra la configuración de la directiva. </li><li>Los usuarios se migrarán a Teams y ya no tendrán Skype Empresarial después de la migración. </li><li>Los usuarios deben tener instalado el cliente de escritorio de Teams. La instalación se realizará durante los 10 días mediante la directiva en la infraestructura de Skype Empresarial, pero si esto falla, los usuarios seguirán teniendo que descargar el cliente o conectarse con un explorador compatible. </li><li>Los contactos y reuniones se migrarán a Teams.</li><li>Los usuarios no podrán iniciar sesión en Skype Empresarial entre transiciones de servicio de tiempo a servicios de Office 365 y no hasta que se completen las entradas dns del cliente. </li><li>Los contactos y las reuniones existentes seguirán funcionando como reuniones de Skype Empresarial. </li><li>PowerShell se usará para administrar la configuración y las directivas para el inquilino y los usuarios. Al conectarse a una sesión de PowerShell, agregue lo siguiente: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (fase 8)

**Se aplica a:** Todos los clientes que usan Microsoft Dynamics 365

Los clientes con Dynamics 365 requieren una participación adicional para migrar las organizaciones de Dynamics de la organización de forma independiente.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Recursos de Microsoft Dynamics | Microsoft Engineering o Microsoft FastTrack contratarán a los clientes con Microsoft Dynamics para realizar la transición de Microsoft Dynamics 365 a la instancia de servicios globales de Office 365.* |<ul><li>Después de la migración, el administrador valida la organización. <</li><li>El administrador modifica los flujos de trabajo según sea necesario. </li><li>El administrador borra el modo AdminOnly según corresponda.</li><li>El administrador cambia el tipo de organización de _Espacio aislado_, según corresponda</li><li>Notificar a los usuarios finales de la nueva dirección URL para obtener acceso a la instancia (org).</li><li>Actualice las conexiones entrantes a la nueva dirección URL del extremo. </li><li>El servicio Dynamics no estará disponible para los usuarios durante la transición. </li><li>Los usuarios deben validar el estado de la organización y las características después de la migración de cada organización.</li></ul>|
|||||

\* (i) Los clientes con Microsoft Dynamics 365 deben tomar medidas en este escenario de migración según se define en el proceso de migración proporcionado. (ii) Si el cliente no toma medidas, Microsoft no podrá completar la migración. (iii) Cuando Microsoft no puede completar la migración debido a la inacción del cliente, la suscripción del cliente expirará el 29 de octubre de 2021.

## <a name="power-bi-phase-8-of-9"></a>Power BI (fase 8 de 9)

**Se aplica a:** Todos los clientes que usan Microsoft Power BI (PBI)

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Migración de recursos de Power BI | Microsoft Engineering o Microsoft FastTrack contratarán a los clientes con Microsoft Power BI (PBI) después de desencadenar manualmente una herramienta de migración de PBI existente para realizar la transición de Power BI a la instancia de servicios globales de Office 365.\*\* |<ul><li>Los siguientes elementos de Power BI _no se_ transiciónrán y tendrán que volver a crearse: <</li><li>Conjuntos de datos en tiempo real (por ejemplo, conjuntos de datos de streaming o inserción). </li><li>Configuración de puerta de enlace de datos local de Power BI y origen de datos. </li><li>Los informes creados sobre los conjuntos de datos en tiempo real no estarán disponibles después de la migración y deben volver a crearse. </li><li>Los servicios de Power BI no estarán disponibles para los usuarios durante la transición. La indisponibilidad del servicio no debe ser superior a 24 horas.</li><li>Los usuarios tendrán que volver a configurar los orígenes de datos y sus puertas de enlace de datos locales con el servicio Power BI después de la migración.  Hasta que lo hagan, los usuarios no podrán usar estos orígenes de datos para realizar actualizaciones programadas o consultas directas en estos orígenes de datos. </li><li>Las capacidades y las áreas de trabajo premium no se pueden migrar. Los clientes deben eliminar todas las capacidades antes de la migración y volver a crearlas después de la migración. Vuelva a mover las áreas de trabajo a las capacidades deseadas.</li></ul>  |
||||

\*\* (i) Los clientes con Microsoft Power BI deben tomar medidas en este escenario de migración, tal como se define en el proceso de migración proporcionado. (ii) Si el cliente no toma medidas, Microsoft no podrá completar la migración. (iii) Cuando Microsoft no puede completar la migración debido a la inacción del cliente, la suscripción del cliente expirará el 29 de octubre de 2021.

## <a name="office-apps"></a>Aplicaciones de Office

**Se aplica a:** Todos los clientes que usan aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, ...)

Los inquilinos de Office 365 que transiciónn a la región "Alemania" requieren que todos los usuarios cierren, cierren sesión desde Office 365 y vuelvan a iniciar sesión para todas las aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, etc.) y el cliente de OneDrive para la Empresa después de que la migración de inquilinos haya alcanzado la fase 9. Al iniciar sesión, permite a los servicios de Office obtener nuevos tokens de autenticación del servicio global de Azure AD.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Clientes, Office Online durante el traslado de cliente de Office, Azure AD ultima el ámbito del espacio empresarial para apuntar a los servicios de Office 365. | Este cambio de configuración permite a los clientes de Office actualizar y apuntar a los extremos de servicios de Office 365. | <ul><li>Notificar a los usuarios que cierren _todas_ las aplicaciones de Office y vuelvan a iniciar sesión (o forzar a los clientes a reiniciarse y a los usuarios a iniciar sesión) para permitir que los clientes de Office puedan recoger el cambio. </li><li>Notifique a los usuarios  y al personal del servicio de atención al cliente que los usuarios pueden ver un banner de Office que les pida que reactiven las aplicaciones de Office en un plazo de 72 horas desde el recorte. </li><li>Todas las aplicaciones de Office en máquinas personales deben cerrarse y los usuarios deben cerrar sesión y volver a iniciar sesión. En la barra de activación amarilla, inicie sesión para reactivarse con los servicios de Office 365.</li><li>Las máquinas compartidas requerirán acciones similares a las máquinas personales y no requerirán un procedimiento especial. </li><li>En dispositivos móviles, los usuarios deben cerrar sesión en las aplicaciones, cerrarlas y, a continuación, iniciar sesión de nuevo. </li></ul>|
||||

## <a name="office-services"></a>Servicios de Office

El servicio más reciente usado (MRU) en Office es un recorte del MCD a los servicios globales de Office 365, no una migración. Solo los vínculos DE MRU del lado servicios globales de Office 365 estarán visibles después de la migración desde el portal Office.com web. Los vínculos MRU de MCD no son visibles como vínculos de MRU en los servicios globales de Office 365. En los servicios globales de Office 365, los vínculos de MRU solo son accesibles después de que la migración de inquilinos haya alcanzado la fase 9.

## <a name="next-step"></a>Paso siguiente

[Realizar trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
