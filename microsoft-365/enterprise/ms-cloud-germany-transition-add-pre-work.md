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
ms.openlocfilehash: 5110c6bd86d5df35a7ceccb4abfedf059cb826d0
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826181"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Trabajo previo para la migración desde Microsoft Cloud Deutschland

Use estos vínculos para obtener acceso a los pasos previos al trabajo relevantes para su organización:

- Para todos los clientes que usan Office 365 en Microsoft Cloud Deutschland, siga [estos pasos.](#applies-to-everyone)
- Si usa Exchange Online o Exchange híbrido, realice [este paso](#exchange-online).
- Si usa SharePoint Online, realice [este paso](#sharepoint-online).
- Si usa una solución de administración de dispositivos móviles (MDM) de terceros, realice [este paso](#mobile).
- Si usa aplicaciones de servicio de terceros o de línea de negocio (LOB) integradas con Office 365, realice [este paso](#line-of-business-apps).
- Si también usa servicios de Azure más allá de los incluidos con su suscripción a Office 365, realice [este paso](#microsoft-azure).
- Si también usa Dynamics 365, realice [este paso](#dynamics365).
- Si también usa Power BI, realice [este paso](#power-bi).
- Para los cambios de DNS, realice [este paso](#dns).
- Si usa identidad federada, siga [estos pasos.](#federated-identity)

## <a name="applies-to-everyone"></a>Se aplica a todos los usuarios

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Prepárese para notificar a los usuarios sobre el reinicio y el inicio de sesión en y fuera de sus clientes después de la migración. | Las licencias de cliente de Office pasarán de Microsoft Cloud Deutschland a los servicios de Office 365 en la migración. Los clientes recogen una nueva licencia válida después de iniciar sesión en los clientes de Office. | Los productos de Office de los usuarios necesitan actualizar las licencias de los servicios de Office 365. Si las licencias no se actualizan, los productos de Office pueden experimentar errores de validación de licencias. |
| Garantizar la conectividad de red con direcciones IP y direcciones URL de servicios de [Office 365.](https://aka.ms/o365urls) | Todos los clientes y servicios hospedados por el cliente que se usan para obtener acceso al servicio de Office 365 deben tener acceso a los extremos de servicios globales de Office 365. <br>En caso de que usted o sus asociados de colaboración tengan reglas de firewall que impidan el acceso a las direcciones URL y direcciones IP enumeradas en las direcciones URL de servicios de [Office 365](https://aka.ms/o365urls) y las direcciones IP, deben cambiar las reglas de firewall para permitir el acceso a los puntos de conexión de servicio global de Office 365| Pueden producirse errores en el servicio o el software cliente si no se realiza antes de la fase 4  |
| Cancelar cualquier suscripción de prueba. | Las suscripciones de prueba no se migrarán y bloquearán la transferencia de suscripciones de pago. | Los servicios de prueba expiran y no funcionan si los usuarios acceden después de la cancelación. |
| Analice las diferencias en las características de licencia entre Microsoft Cloud Deutschland y Office 365 Services. | Los servicios de Office 365 incluyen características y servicios adicionales que no están disponibles en el Microsoft Cloud Deutschland actual. Durante la transferencia de suscripción, las nuevas características estarán disponibles para los usuarios. | <ul><li> Analice las distintas características proporcionadas por las licencias de Microsoft Cloud Deutschland y Office 365 Services. Comience con la descripción del servicio de la [plataforma office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). </li><li> Determine si las nuevas características de los servicios de Office 365 deben deshabilitarse inicialmente para limitar los efectos en los usuarios o en la administración de cambios de usuario y modificar las asignaciones de licencias de usuario según sea necesario. </li><li>Prepare a los usuarios y al personal de servicio de ayuda para los nuevos servicios y características proporcionados por los servicios de Office 365. |
| Cree directivas de retención en toda [la](https://docs.microsoft.com/microsoft-365/compliance/retention) organización para protegerse de la eliminación involuntaria de contenido durante la migración.  |<ul><li>Para asegurarse de que los usuarios finales no eliminan accidentalmente el contenido durante la migración, los clientes pueden optar por habilitar una directiva de retención en toda la organización. </li><li>Aunque la retención no es necesaria, dado que las retenciones realizadas en cualquier momento durante la migración deben funcionar según lo esperado, tener una directiva de retención es un mecanismo de seguridad de copia de seguridad. Al mismo tiempo, es posible que todos los clientes no utilicen una directiva de retención, especialmente aquellos que están preocupados por la conservación.</li></ul>| Aplicar la directiva de retención tal como se describe [en Obtenga información sobre las directivas de retención y las etiquetas de retención.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Los errores del servicio o del software cliente pueden producirse si esto no se realiza antes de la fase 4 de 9. </li></ul>|
| Corregir los excesos de licencia | En determinadas circunstancias, los clientes pueden consumir más servicios de los que se compran. Esta condición se conoce como exceso de licencia. Microsoft no puede migrar clientes en una condición de exceso de licencia de Microsoft Cloud Deutschland a las regiones del centro de datos alemán. Para garantizar el acceso continuo al servicio y a los datos, cada usuario asignado requiere una licencia. | Todos los clientes | Los clientes deben evaluar y resolver la condición de exceso de licencias a través de la compra de licencias adicionales o mediante la desasignación de licencias de los usuarios. |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>Servicios de federación de Active Directory (ADFS)

**Se aplica a**: Los clientes que usan AD FS localmente para autenticar a los usuarios que se conectan a Microsoft Office 365

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| [Copia de seguridad de la granja de servidores de Servicios de federación de Active Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) para escenarios de recuperación ante desastres. | Los clientes necesitan hacer una copia de seguridad de la granja de AD FS de forma adecuada para garantizar que las confianzas de los usuarios de confianza en las redes & los puntos de conexión de Alemania se puedan restaurar sin tocar el URI del emisor de los dominios. Microsoft recomienda usar la restauración rápida de AD FS para una copia de seguridad de la granja de servidores y la restauración correspondiente, si es necesario. | Acción requerida. La inacción provocará un impacto en el servicio durante la migración si se produce un error en la granja de servidores de AD FS del cliente. Para obtener más información, consulte [Pasos de migración de ADFS](https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |
||||

## <a name="exchange-online"></a>Exchange en línea

**Se aplica a**: Clientes de Exchange Online que han habilitado el espacio de direcciones de disponibilidad y calendario para compartir.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Notificar a los asociados externos de la próxima transición a los servicios de Office 365. | Las configuraciones de espacio de direcciones de disponibilidad permiten compartir información de disponibilidad con Office 365. | Si no lo hace, puede producirse un error en el servicio o el cliente en una fase posterior de la migración de clientes. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Configuración híbrida de Exchange Online

**Se aplica a**: Clientes de Exchange Online con una configuración híbrida de Exchange activa

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Actualice a la versión más reciente del Asistente para configuración híbrida (HCW) en cualquier momento antes de que el inquilino entre en la fase de migración 5. Puede iniciar esta actividad inmediatamente después de recibir la notificación del centro de mensajes de que su migración de inquilino de Office 365 ha comenzado.<br><br> Los clientes híbridos de Microsoft Cloud Deutschland Exchange Online deben desinstalar las versiones anteriores de HCW y, a continuación, instalar y ejecutar la última versión (17.0.5378.0 o posterior) de [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . |<ul><li>La versión más reciente del HCW incluye actualizaciones necesarias para admitir a los clientes que están haciendo la transición de Microsoft Cloud Deutschland a Office 365 Services.</li><li> Las actualizaciones incluyen cambios en la configuración del certificado local para el conector de envío y el conector de recepción.</li><li> Los administradores de Exchange deben volver a instalar el HCW en cualquier momento antes de que comience la fase 5 de 9 (migración de Exchange).<br>Al ejecutar el HCW antes de la fase 5, seleccione "Office 365 Germany" en la segunda página del HCW en _Office 365 Exchange Online_ en el cuadro de lista debajo de Mi organización de Office _365_ está hospedado por</li><li>**NOTA:** Una vez completada la migración de inquilino de Office 365, se quitará y se volverá a instalar el HCW, esta vez con la configuración "Office 365 Worldwide" en la 2ª página del HCW para completar la configuración híbrida con el servicio global de Exchange Online.</li></ul>|Si no se ejecuta el HCW antes de la fase 5 (migración de Exchange), se puede producir un error en el servicio o en el cliente. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**Se aplica a**: Clientes que usan SharePoint 2013 localmente


| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Limitar flujos de trabajo de SharePoint 2013, usarlos durante la migración de SharePoint Online. | Reduzca los flujos de trabajo de SharePoint 2013 y complete los flujos de trabajo en el vuelo antes de las transiciones. | La inacción puede provocar confusión del usuario y llamadas al servicio de ayuda. |
||||

## <a name="skype-for-business-online"></a>Skype Empresarial Online

**Se aplica a**: Clientes de Skype Empresarial Online

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Implementar el cliente de escritorio de Teams para los usuarios que tienen acceso a Skype Empresarial en Alemania. | La migración mueve usuarios de Skype Empresarial a Microsoft Teams para colaboración, llamadas y chat. Implemente el cliente de escritorio de Microsoft Teams o asegúrese de que hay disponible un explorador compatible. | La inacción provocará la indisponibilidad de los servicios de colaboración de Microsoft Teams. |
| Revise y prepare los cambios dns relacionados con la migración. | Cambios de zona DNS propiedad del cliente para Skype Empresarial Online. |<ul><li>Se recomienda actualizar el tiempo de vida (TTL) para los registros DNS de dominio propiedad del cliente a 5 minutos para acelerar la actualización de los registros DNS. Sin embargo, el recorte administrado por Microsoft asociado a este cambio dns puede producirse en cualquier momento dentro de la ventana de cambio de 24 horas proporcionada. </li><li>La interrupción del servicio es posible en el futuro. Los usuarios no podrán iniciar sesión en Skype Empresarial y se redirigirán a la experiencia migrada de Teams en los servicios de Office 365. </li></ul>|
| Prepare el aprendizaje y la preparación del usuario final y de administración para la transición a Microsoft Teams. | Tenga éxito en la transición de Skype a Teams planeando la comunicación y preparación del usuario. | <ul><li>Los clientes deben tener en cuenta los nuevos servicios y cómo usarlos una vez que sus servicios se transiciónn a los servicios de Office 365. </li><li>Después de que se realicen cambios dns tanto para los dominios de vanidad del cliente como para el dominio inicial, los usuarios iniciarían sesión en Skype Empresarial y verían que ahora se migran a Teams. Esto también descargaría el cliente de escritorio para Teams en segundo plano. </li></ul>|
||||

## <a name="mobile"></a>Móvil

Si usas una solución de administración de dispositivos móviles (MDM) de terceros:

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Prepare la formación de usuario final y administración sobre los usuarios que quitan y agregan de nuevo su cuenta a Microsoft Outlook para iOS y Android. | Las cuentas de Microsoft Outlook para iOS y Android configuradas con buzones en Microsoft Cloud Deutschland pueden tener que quitarse y agregarse de nuevo a Outlook para sincronizar correctamente la nueva configuración de servicios de Office 365. | Microsoft Outlook para clientes de iOS y Android | Es posible que los buzones de Outlook configurados anteriormente para Microsoft Cloud Deutschland no retome la nueva configuración de Servicios de Office 365, lo que provoca errores y un rendimiento degradado de otras experiencias de usuario. Se recomienda a los administradores de TI que proporcionen documentación que indique de forma proactiva a los usuarios que quiten y vuelvan a agregar sus cuentas a Microsoft Outlook para iOS y Android si se producen problemas con el inicio de sesión o la sincronización del correo después de la migración. |
| Determine si es necesaria una reconfiguración después de la migración. | Las soluciones de administración de dispositivos móviles (MDM) pueden dirigirse a `outlook.de` puntos de conexión. En esta transición a Servicios de Office 365, los perfiles de cliente deben actualizarse a la dirección URL de servicios de Office 365, `outlook.office365.com` . | Clientes de Exchange Online y MDM | Los clientes pueden seguir funcionando mientras se puede obtener acceso al punto de conexión, pero producirán un error si los puntos de conexión `outlook.de` de Microsoft Cloud Deutschland ya no están disponibles. |
|||||

## <a name="line-of-business-apps"></a>Aplicaciones de línea de negocio

Si usa un servicio de terceros o aplicaciones de línea de negocio (LOB) integradas con Office 365: 

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Determine si es necesaria una reconfiguración después de la migración. | Los servicios y aplicaciones de terceros que se integran con Office 365 pueden codificarse para esperar direcciones IP y direcciones URL de Microsoft Cloud Deutschland. | Acción necesaria. La inacción puede provocar errores en el servicio o el software cliente. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Se aplica a**: Clientes que usan Microsoft Dynamics

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Para las suscripciones de espacio aislado de Dynamics 365, asegúrese de descargar el entorno de producción de la instancia de Dynamics SQL desde su suscripción a Dynamics 365 en Microsoft Cloud Deutschland. La copia de seguridad de producción más reciente debe restaurarse en el espacio aislado antes de la migración de espacio aislado. | La migración de Dynamics 365 requiere que los clientes se aseguren de que el entorno de espacio aislado se actualice con la base de datos de producción más reciente. | El equipo de FastTrack ayudará a los clientes a realizar ejecuciones secas para validar la actualización de versión de 8.x a 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Se aplica a**: Clientes de Power BI 

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Eliminación de objetos de suscripciones de Power BI que no se migrarán de Power BI Microsoft Cloud Deutschland a los servicios de Office 365. | La migración de los servicios de Power BI requerirá una acción del cliente para eliminar determinados artefactos, como conjuntos de datos y paneles. | <ul><li>Los administradores pueden tener que quitar los siguientes elementos de su suscripción: </li><li>Real-Time conjuntos de datos (por ejemplo, conjuntos de datos de streaming o inserción) </li><li>Configuración y origen de datos de Power BI local </li></ul>|
||||

## <a name="dns"></a>DNS

**Se aplica a**: Clientes que usan el cliente de escritorio de Office (Aplicaciones de Microsoft 365, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Quite MSOID, CName del DNS propiedad del cliente si existe en cualquier momento antes del corte de Azure Active Directory (Azure AD). Se puede establecer un TTL de 5 minutos para que el cambio pueda tener efecto rápidamente.

## <a name="federated-identity"></a>Identidad federada

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Agregue un identificador de inicio de sesión único (SSO) a una confianza de usuario de confianza existente y deshabilite las actualizaciones automáticas de metadatos de AD FS. | Un identificador debe agregarse a la confianza de usuario de confianza de AD FS antes de iniciar la migración. Para evitar la eliminación accidental del identificador de usuario de confianza, deshabilite la actualización automática para las actualizaciones de metadatos. <br><br> Ejecute este comando como una sola línea de comandos en el servidor de AD FS: <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| Organizaciones de autenticación federada | Acción requerida. La inacción antes de la fase 4 de 9 (SharePoint) provocará un impacto en el servicio durante la migración.  |
| Generar confianza de usuario de confianza para puntos de conexión globales de Azure AD. | Los clientes deben crear manualmente una confianza de usuario de confianza (RPT) para los puntos de conexión [globales.](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) Para ello, agrega un nuevo RPT a través de la GUI aprovechando la dirección URL de metadatos de federación global y, a continuación, usando las reglas de notificación de [RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) de Azure AD (en la Ayuda de AD FS) para generar las reglas de notificación e importarlas al RPT. | Organizaciones de autenticación federada | Acción requerida. La inacción provocará un impacto en el servicio durante la migración. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

Si usa la misma partición de identidad de Azure Active Directory para Office 365 y Microsoft Azure en la instancia de Microsoft Cloud Deutschland, asegúrese de prepararse para la migración controlada por el cliente de los servicios de Microsoft Azure.
La migración de los servicios de Microsoft Azure no debe iniciarse antes de que el inquilino de Office 365 haya alcanzado la fase de migración 3 y debe completarse antes de que se complete la fase 8 de migración.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Determine qué servicios de Azure están en uso y prepárese para la migración futura desde Alemania al inquilino de servicios de Office 365 trabajando con sus asociados. Siga los pasos descritos en el libro de [reproducción de migración de Azure](https://docs.microsoft.com/azure/germany/germany-migration-main). |<ul><li>La migración de recursos de Azure es una responsabilidad del cliente y requiere un esfuerzo manual siguiendo los pasos prescritos. Comprender qué servicios se usan en la organización es clave para la migración correcta de los servicios de Azure. </li><li> Los clientes de Office 365 Germany que tienen suscripciones de Azure bajo la misma partición de identidad (organización) deben seguir el orden prescrito por Microsoft cuando puedan iniciar la migración de suscripción y servicios.</li></ul>|<ul><li>Los clientes pueden tener varias suscripciones de Azure, cada suscripción que contenga infraestructura, servicios y componentes de plataforma. </li><li> Los administradores deben identificar suscripciones y partes interesadas para garantizar que la migración y validación rápidas sea posible como parte de este evento de migración. </li><li>Si no se completa correctamente la migración de estas suscripciones y los componentes de Azure dentro de la escala de tiempo prescrita, se afectará la finalización de la transición de Office y Azure AD a los servicios de Office 365 y puede provocar la pérdida de datos. </li><li> Una notificación del Centro de mensajes señalará el punto en el que puede comenzar la migración dirigida por el cliente. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

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

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
