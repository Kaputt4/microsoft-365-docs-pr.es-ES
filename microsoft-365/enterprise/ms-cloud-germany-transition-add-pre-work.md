---
title: Trabajo previo para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: 'Resumen: Pre-work when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.'
ms.openlocfilehash: fb352c17d9868cf5c42034e198be63b6e0543dbb
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445607"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Trabajo previo para la migración desde Microsoft Cloud Deutschland

Use estos vínculos para obtener acceso a los pasos previos al trabajo relevantes para su organización:

- Para **todos los clientes** que usan Office 365 en Microsoft Cloud Deutschland, siga estos [pasos.](#general-tenant-migration-considerations)
- Para **los cambios de DNS,** realice este [paso](#dns).
- Si usa los Servicios de federación **de Active Directory** localmente, siga estos [pasos.](#active-directory-federation-services-ad-fs)
- Si usa **SharePoint Online,** realice [este paso](#sharepoint-online).
- Si usa Exchange **Online** o **Exchange híbrido,** realice [este paso](#exchange-online).
- Si está usando Skype Empresarial **Online,** realice [este paso](#skype-for-business-online)
- Si usa una solución de administración de dispositivos móviles (MDM) de terceros, realice [este paso](#mobile-device-management).
- Si usa servicios  de terceros o aplicaciones de línea de negocio **(LOB)** integradas con Office 365, realice [este paso](#line-of-business-apps).
- Si también usa **Dynamics 365,** realice [este paso](#dynamics365).
- Si también usa **Power BI,** realice [este paso](#power-bi).
- Si también usa servicios **de Azure** con su suscripción a Office 365, realice [este paso](#microsoft-azure).

## <a name="general-tenant-migration-considerations"></a>Consideraciones generales de migración de inquilinos

**Se aplica a:** Todos los clientes que usan Office 365 en la instancia de Microsoft Deutschland Cloud

Los identificadores de inquilino e usuario de Office 365 se conservan durante la migración. Las llamadas de servicio de Azure AD se redirigen desde Microsoft Cloud Deutschland a los servicios globales de Office 365 y son transparentes para los servicios de Office 365.

- Las solicitudes de interesados (DSR) del Reglamento general de protección de datos (RGPD) se ejecutan desde el portal de administración de Azure para futuras solicitudes. Los datos de diagnóstico heredados o que no son del cliente que residen en Microsoft Cloud Deutschland se eliminan en o antes de que transcurren 30 días.
- Las solicitudes de autenticación multifactor (MFA) que usan Microsoft Authenticator se muestran como objectid de usuario (GUID) mientras el inquilino se copia en los servicios de Office 365. Las solicitudes MFA se realizarán según lo esperado a pesar de este comportamiento de presentación.  Las cuentas de Microsoft Authenticator que se activaron mediante puntos de conexión de servicios de Office 365 mostrarán el nombre principal de usuario (UPN).  Las cuentas agregadas mediante puntos de conexión de Microsoft Cloud Deutschland mostrarán el ObjectID del usuario, pero funcionarán con puntos de conexión de servicios de Microsoft Cloud Deutschland y Office 365.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Prepárese para notificar a los usuarios sobre el reinicio y el inicio de sesión en y fuera de sus clientes después de la migración. | Las licencias de cliente de Office pasarán de Microsoft Cloud Deutschland a los servicios de Office 365 en la migración. Los clientes recogen una nueva licencia válida después de iniciar sesión en los clientes de Office. | Los productos de Office de los usuarios necesitan actualizar las licencias de los servicios de Office 365. Si las licencias no se actualizan, los productos de Office pueden experimentar errores de validación de licencias. |
| Garantizar la conectividad de red con direcciones IP y direcciones URL de servicios de [Office 365.](https://aka.ms/o365urls) | Todos los clientes y servicios hospedados por el cliente que se usan para obtener acceso al servicio de Office 365 deben tener acceso a los extremos de servicios globales de Office 365. <br>En caso de que usted o sus asociados de colaboración tengan reglas de firewall que impidan el acceso a las direcciones URL y direcciones IP enumeradas en las direcciones URL de servicios de [Office 365](https://aka.ms/o365urls) y las direcciones IP deben cambiar las reglas de firewall para permitir el acceso a los extremos de servicio global de Office 365| Pueden producirse errores en el servicio o el software cliente si no se realiza antes de la fase 4  |
| Cancelar cualquier suscripción de prueba. | Las suscripciones de prueba no se migrarán y bloquearán la transferencia de suscripciones de pago. | Los servicios de prueba expiran y no funcionan si los usuarios acceden después de la cancelación. |
| Analice las diferencias en las características de licencia entre Microsoft Cloud Deutschland y los Servicios globales de Office 365. | Los servicios de Office 365 incluyen características y servicios adicionales que no están disponibles en el Microsoft Cloud Deutschland actual. Durante la transferencia de suscripción, las nuevas características estarán disponibles para los usuarios. | <ul><li> Analice las distintas características proporcionadas por las licencias de Microsoft Cloud Deutschland y Servicios globales de Office 365. Comience con la descripción del servicio de la [plataforma office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). </li><li> Determine si las nuevas características de los servicios de Office 365 deben deshabilitarse inicialmente para limitar los efectos en los usuarios o en la administración de cambios de usuario y modificar las asignaciones de licencias de usuario según sea necesario. </li><li>Prepare a los usuarios y al personal de servicio de ayuda para los nuevos servicios y características proporcionados por los servicios de Office 365. |
| Cree directivas de retención en toda [la](https://docs.microsoft.com/microsoft-365/compliance/retention) organización para protegerse de la eliminación involuntaria de contenido durante la migración.  |<ul><li>Para asegurarse de que los usuarios finales no eliminan accidentalmente el contenido durante la migración, los clientes pueden optar por habilitar una directiva de retención en toda la organización. </li><li>Aunque la retención no es necesaria, dado que las retenciones realizadas en cualquier momento durante la migración deben funcionar según lo esperado, tener una directiva de retención es un mecanismo de seguridad de copia de seguridad. Al mismo tiempo, es posible que todos los clientes no utilicen una directiva de retención, especialmente aquellos que están preocupados por la conservación.</li></ul>| Aplicar la directiva de retención tal como se describe [en Obtenga información sobre las directivas de retención y las etiquetas de retención.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Los errores del servicio o del software cliente pueden producirse si esto no se realiza antes de la fase 4 de 9. </li></ul>|
|||||

## <a name="dns"></a>DNS

<!-- before phase 9 -->

**Se aplica a**: Clientes que establecen un CNAME _msoid_ personalizado en su propio dominio DNS

Si se configura, _el Msoid_ CNAME solo afecta a los clientes que usan el cliente de escritorio de Office (Aplicaciones de Microsoft 365, Office 365 ProPlus, Office 2019, 2016, ...).

En caso de que haya establecido un CNAME DNS denominado _msoid_ en uno o varios espacios de nombres DNS de su propiedad, debe quitar el CNAME hasta el final de la fase 8 como máximo. Puede quitar el _msoid_ CNAME en cualquier momento antes del final de la fase 8.

Para comprobar si ha establecido un CNAME en el espacio de nombres DNS, siga los pasos siguientes y reemplace _contoso.com_ por su propio nombre de dominio:

```console
nslookup -querytype=CNMAE msoid.contoso.com
```

Si la línea de comandos devuelve un registro DNS, quite _el Msoid_ CNAME del dominio.

## <a name="active-directory-federation-services-ad-fs"></a>Servicios de federación de Active Directory (ADFS)

<!-- before phase 4 -->

**Se aplica a**: Los clientes que usan AD FS localmente para autenticar a los usuarios que se conectan a Microsoft Office 365<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 4

Leer y aplicar los pasos [de migración de ADFS](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Se aplica a**: Clientes que usan SharePoint 2013 local<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 4

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Limitar flujos de trabajo de SharePoint 2013, usarlos durante la migración de SharePoint Online. | Reduzca los flujos de trabajo de SharePoint 2013 y complete los flujos de trabajo en el vuelo antes de las transiciones. | La inacción puede provocar confusión del usuario y llamadas al servicio de ayuda. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Se aplica a**: Clientes de Exchange Online que han habilitado el espacio de direcciones de disponibilidad y calendario para compartir<br>
**Cuando se aplica:** cualquier momento antes del final de la fase 9

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Notificar a los asociados externos de la próxima transición a los servicios de Office 365. | Las configuraciones de espacio de direcciones de disponibilidad permiten compartir información de disponibilidad con Office 365. | Si no lo hace, puede producirse un error en el servicio o el cliente en una fase posterior de la migración de clientes. |
||||

### <a name="exchange-online-hybrid-configuration"></a>Configuración híbrida de Exchange Online

**Se aplica a:** Todos los clientes que usan una configuración híbrida de Exchange activa con servidores de Exchange locales<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 5

Los clientes empresariales con una implementación híbrida de Exchange Online y una instalación local Exchange Server el Asistente para la configuración híbrida (HCW) para mantener y establecer la configuración híbrida. Al realizar la transición de Microsoft Cloud Deutschland a la región de Office 365 Germany, el administrador debe volver a ejecutar la compilación más reciente de HCW en modo "Office 365 Germany" antes de que comience la migración de Exchange (fase 5). A continuación, vuelva a ejecutar el HCW en modo "Office 365 Worldwide" al finalizar la fase 5 para finalizar la implementación local con la configuración de la región de Office 365 Germany.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| (Fase previa 5): volver a ejecutar HCW con la configuración de Office 365 Germany <br><br> <i>Puede iniciar esta actividad inmediatamente después de recibir la notificación del centro de mensajes de que su migración de inquilino de Office 365 ha comenzado (fase 1).</i>| Desinstalar y volver a ejecutar HCW (17.0.5378.0 o posterior) desde antes de la fase 5 garantizará que la configuración local esté preparada para enviar y recibir correo con usuarios y usuarios de Microsoft Cloud Deutschland que se migran a la región de [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Alemania. <p><li> En hcw, para el cuadro de lista debajo de **Mi organización de Office 365** está hospedado por , seleccione Office **365 Alemania.** | Si no se completa esta tarea antes de que comience la fase 5 [Migración de Exchange], pueden producirse NDR para el correo enrutado entre la implementación local de Exchange y Office 365.  
| (Post-Stage 5): vuelva a ejecutar HCW con la configuración de Office 365 Worldwide <br><br> <i>Puede iniciar esta actividad después de recibir la notificación del centro de mensajes de que se ha completado la migración de Exchange (fase 5).</i>| Al desinstalar y volver a ejecutar HCW desde después de la fase 5, se restablecerá la configuración local para la configuración híbrida con [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) solo Office 365 global. <p><li> En el cuadro de lista debajo **de Mi organización de Office 365** está hospedado por , seleccione Office **365 Worldwide**. | Si no se completa esta tarea antes de la fase 9 [Migración completada], es posible que los NDR para el correo enrutado entre la implementación local de Exchange y Office 365.  
| Establecer AuthServer local que señale al servicio de token de seguridad global (STS) para la autenticación | Esto garantiza que las solicitudes de autenticación para las solicitudes de disponibilidad de Exchange de los usuarios en estado de migración destinadas al entorno local híbrido se autentican para obtener acceso al servicio local. Del mismo modo, esto garantizará la autenticación de solicitudes desde locales a puntos de conexión de servicios globales de Office 365. | Una vez completada la migración de Azure AD (fase 2), el administrador de la topología local de Exchange (híbrida) debe agregar un nuevo extremo de servicio de autenticación para los servicios globales de Office 365. Con este comando de Exchange PowerShell, reemplace por el identificador de inquilino de su organización que se encuentra en `<TenantID>` Azure Portal en Azure Active Directory.<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> Si no se completa esta tarea, es posible que las solicitudes híbridas de disponibilidad no proporcionen información a los usuarios de buzones que se han migrado de Microsoft Cloud Deutschland a los servicios de Office 365.  |
||||

## <a name="skype-for-business-online"></a>Skype Empresarial Online

<!-- before phase 7 -->

**Se aplica a**: Clientes de Skype Empresarial Online<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 7

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Implementar el cliente de escritorio de Teams para los usuarios que tienen acceso a Skype Empresarial en Alemania. | La migración mueve usuarios de Skype Empresarial a Microsoft Teams para colaboración, llamadas y chat. Implemente el cliente de escritorio de Microsoft Teams o asegúrese de que hay disponible un explorador compatible. | La inacción provocará la indisponibilidad de los servicios de colaboración de Microsoft Teams. |
| Revise y prepare los cambios dns relacionados con la migración. | Cambios de zona DNS propiedad del cliente para Skype Empresarial Online. |<ul><li>Se recomienda actualizar el tiempo de vida (TTL) para los registros DNS de dominio propiedad del cliente a 5 minutos para acelerar la actualización de los registros DNS. Sin embargo, el recorte administrado por Microsoft asociado a este cambio dns puede producirse en cualquier momento dentro de la ventana de cambio de 24 horas proporcionada. </li><li>La interrupción del servicio es posible en el futuro. Los usuarios no podrán iniciar sesión en Skype Empresarial y se redirigirán a la experiencia migrada de Teams en los servicios de Office 365. </li></ul>|
| Prepare el aprendizaje y la preparación del usuario final y de administración para la transición a Microsoft Teams. | Tenga éxito en la transición de Skype a Teams planeando la comunicación y preparación del usuario. | <ul><li>Los clientes deben tener en cuenta los nuevos servicios y cómo usarlos una vez que sus servicios se transiciónn a los servicios de Office 365. </li><li>Después de que se realicen cambios dns tanto para los dominios de vanidad del cliente como para el dominio inicial, los usuarios iniciarían sesión en Skype Empresarial y verían que ahora se migran a Teams. Esto también descargaría el cliente de escritorio para Teams en segundo plano. </li></ul>|
||||

## <a name="mobile-device-management"></a>Administración de dispositivos móviles

<!-- before phase 5 -->
**Se aplica a:** Clientes que usan una solución de administración de dispositivos móviles (MDM) de terceros<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 5

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Prepare la formación de usuario final y administración sobre los usuarios que quitan y agregan de nuevo su cuenta a Microsoft Outlook para iOS y Android. | Las cuentas de Microsoft Outlook para iOS y Android configuradas con buzones en Microsoft Cloud Deutschland pueden tener que quitarse y agregarse de nuevo a Outlook para sincronizar correctamente la nueva configuración de servicios de Office 365. | Microsoft Outlook para clientes de iOS y Android | Es posible que los buzones de Outlook configurados anteriormente para Microsoft Cloud Deutschland no retome la nueva configuración de Servicios de Office 365, lo que provoca errores y un rendimiento degradado de otras experiencias de usuario. Se recomienda a los administradores de TI que proporcionen documentación que indique de forma proactiva a los usuarios que quiten y vuelvan a agregar sus cuentas a Microsoft Outlook para iOS y Android si se producen problemas con el inicio de sesión o la sincronización del correo después de la migración. |
| Determine si es necesaria una reconfiguración después de la migración. | Las soluciones de administración de dispositivos móviles (MDM) pueden dirigirse a `outlook.de` puntos de conexión. En esta transición a Servicios de Office 365, los perfiles de cliente deben actualizarse a la dirección URL de servicios de Office 365, `outlook.office365.com` . | Clientes de Exchange Online y MDM | Los clientes pueden seguir funcionando mientras se puede obtener acceso al punto de conexión, pero producirán un error si los puntos de conexión `outlook.de` de Microsoft Cloud Deutschland ya no están disponibles. |
|||||

## <a name="line-of-business-apps"></a>Aplicaciones de línea de negocio

**Se aplica a:** Clientes que usan aplicaciones de línea de negocio (LOB) con puntos de conexión proporcionados por Microsoft Cloud Deutschland<br>
**Cuando se aplica:** después de la finalización de la fase 2 y antes del final de la fase 9

Si usa un servicio de terceros o aplicaciones de línea de negocio (LOB) integradas con Office 365, debe resolver las dependencias de los puntos de conexión proporcionados por la instancia de Microsoft Cloud Deutschland. Por ejemplo, si las aplicaciones de LOB se conectan a `https://graph.microsoft.de/` , debes cambiar el punto de conexión a `https://graph.microsoft.com/` . Los extremos del servicio global Microsoft Office 365 están disponibles para el inquilino después de la fase 2.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Determine si es necesaria una reconfiguración después de la migración. | Los servicios y aplicaciones de terceros que se integran con Office 365 pueden codificarse para esperar direcciones IP y direcciones URL de Microsoft Cloud Deutschland. | Acción necesaria. La inacción puede provocar errores en el servicio o el software cliente. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Se aplica a**: Clientes que usan Microsoft Dynamics 365

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Para las suscripciones de espacio aislado de Dynamics 365, asegúrese de descargar el entorno de producción de la instancia de Dynamics SQL desde su suscripción a Dynamics 365 en Microsoft Cloud Deutschland. La copia de seguridad de producción más reciente debe restaurarse en el espacio aislado antes de la migración de espacio aislado. | La migración de Dynamics 365 requiere que los clientes se aseguren de que el entorno de espacio aislado se actualice con la base de datos de producción más reciente. | El equipo de FastTrack ayudará a los clientes a realizar ejecuciones secas para validar la actualización de versión de 8.x a 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Se aplica a**: Clientes que usan Power BI

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Eliminación de objetos de suscripciones de Power BI que no se migrarán de Power BI Microsoft Cloud Deutschland a los servicios de Office 365. | La migración de los servicios de Power BI requerirá una acción del cliente para eliminar determinados artefactos, como conjuntos de datos y paneles. | <ul><li>Los administradores pueden tener que quitar los siguientes elementos de su suscripción: </li><li>Real-Time conjuntos de datos (por ejemplo, conjuntos de datos de streaming o inserción) </li><li>Configuración y origen de datos de Power BI local </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Si usa la misma partición de identidad de Azure Active Directory para Office 365 y Microsoft Azure en la instancia de Microsoft Cloud Deutschland, asegúrese de prepararse para la migración controlada por el cliente de los servicios de Microsoft Azure.

> [!NOTE]
> La migración de los servicios de Microsoft Azure no debe iniciarse antes de que el inquilino de Office 365 haya alcanzado la fase de migración 3 y debe completarse antes de que se complete la fase 8 de migración.

Los clientes que usan recursos de Office 365 y Azure (por ejemplo, redes, proceso y almacenamiento) realizarán la migración de recursos a la instancia de servicios de Office 365. Esta migración es responsabilidad del cliente. Las publicaciones del Centro de mensajes marcarán el inicio. La migración debe completarse antes de finalizar la organización de Azure AD en el entorno de servicios de Office 365. Para las migraciones de Azure, consulte el libro de reproducción de migración de Azure, Información general sobre las instrucciones [de migración para Azure Germany](https://docs.microsoft.com/azure/germany/germany-migration-main).

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Determine qué servicios de Azure están en uso y prepárese para la migración futura desde Alemania al inquilino de servicios de Office 365 trabajando con sus asociados. Siga los pasos descritos en el libro de [reproducción de migración de Azure](/azure/germany/germany-migration-main). |<ul><li>La migración de recursos de Azure es una responsabilidad del cliente y requiere un esfuerzo manual siguiendo los pasos prescritos. Comprender qué servicios se usan en la organización es clave para la migración correcta de los servicios de Azure. </li><li> Los clientes de Office 365 Germany que tienen suscripciones de Azure bajo la misma partición de identidad (organización) deben seguir el orden prescrito por Microsoft cuando puedan iniciar la migración de suscripción y servicios.</li></ul>|<ul><li>Los clientes pueden tener varias suscripciones de Azure, cada suscripción que contenga infraestructura, servicios y componentes de plataforma. </li><li> Los administradores deben identificar suscripciones y partes interesadas para garantizar que la migración y validación rápidas sea posible como parte de este evento de migración. </li><li>Si no se completa correctamente la migración de estas suscripciones y los componentes de Azure dentro de la escala de tiempo prescrita, se afectará la finalización de la transición de Office y Azure AD a los servicios de Office 365 y puede provocar la pérdida de datos. </li><li> Una notificación del Centro de mensajes señalará el punto en el que puede comenzar la migración dirigida por el cliente. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Información del programa de migración de Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introducción a su actualización de Microsoft Teams](/microsoftteams/upgrade-start-here)
