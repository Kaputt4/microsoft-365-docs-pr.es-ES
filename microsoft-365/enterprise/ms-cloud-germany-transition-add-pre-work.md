---
title: Trabajo previo para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
description: 'Resumen: trabajo previo al pasar de Microsoft Cloud Alemania (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921571"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Trabajo previo para la migración desde Microsoft Cloud Deutschland


Use estos vínculos para obtener acceso a los pasos de trabajo previo relevantes para su organización:

- Para todas las suscripciones, siga [estos pasos.](#applies-to-everyone)
- Si usa Exchange Online o Exchange híbrido, realice [este paso.](#exchange-online)
- Si usa SharePoint Online, realice [este paso.](#sharepoint-online)
- Si usa una solución de administración de dispositivos móviles (MDM) de terceros, realice [este paso.](#mobile)
- Si usa aplicaciones de servicio de terceros o de línea de negocio (LOB) integradas con Office 365, realice [este paso.](#line-of-business-apps)
- Si también usa servicios de Azure más allá de los incluidos con su suscripción a Office 365, realice [este paso.](#azure)
- Si también usa Dynamics 365, realice [este paso.](#dynamics365)
- Si también usa Power BI, realice [este paso.](#power-bi)
- Para los cambios de DNS, realice [este paso.](#dns)
- Si usa la identidad federada, siga [estos pasos.](#federated-identity)

## <a name="applies-to-everyone"></a>Se aplica a todos los usuarios

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Asegúrese de la conectividad de red a direcciones IP y URL de servicios [de Office 365.](https://aka.ms/o365urls) | Todos los clientes y servicios hospedados por el cliente que se usan para acceder al servicio de Office 365 deben poder acceder a los puntos de conexión de servicios de Office 365. | Todos los clientes de transición y los clientes con acceso a la red restringidos a Microsoft Cloud Deutschland. | Acción necesaria. La inacción puede provocar errores en el servicio o el software cliente. |
| Revisar y preparar los cambios de DNS relacionados con la migración. | El cliente prepara entradas DNS para Exchange Online y Exchange Online Protection (registro MX, etc.). | Clientes de Exchange Online | Se trata de una acción recomendada. Ninguna acción significa que el correo electrónico de los clientes migrados puede enrutar a través de Microsoft Cloud Deutschland hasta que los servicios de Microsoft Cloud Deutschland estén deshabilitados. |
| Revisar y preparar los cambios de DNS relacionados con la migración. | Cambios en la zona DNS propiedad del cliente para Skype Empresarial Online. | Clientes de Skype Empresarial Online | - Se recomienda actualizar el período de vida (TTL) de los registros DNS de dominio propiedad del cliente a 5 minutos para acelerar la actualización de los registros DNS. Sin embargo, la cutover administrada por Microsoft asociada a este cambio de DNS puede producirse en cualquier momento dentro de la ventana de cambio de 24 horas proporcionada. <br><br> - La interrupción del servicio es posible en el futuro. Los usuarios no podrán iniciar sesión en Skype Empresarial y se les redirigirá a la experiencia migrada de Teams en los servicios de Office 365. |
| Preparar la formación y preparación del usuario final y administración para la transición a Microsoft Teams. | Para realizar la transición de Skype a Teams, planee la comunicación y la preparación de los usuarios. | Clientes de Skype Empresarial Online | - Los clientes deben conocer los nuevos servicios y cómo usarlos una vez que sus servicios se han pasado a los servicios de Office 365. <br><br> - Después de que se realicen cambios de DNS para los dominios de vanidad del cliente y el dominio inicial, los usuarios iniciarían sesión en Skype Empresarial y verían que ahora se migran a Teams. Esto también descargaría el cliente de escritorio para Teams en segundo plano. |
| Prepare el aprendizaje para el usuario final y la administración acerca de los usuarios que quitan y agregan su cuenta a Microsoft Outlook para iOS y Android. | Es posible que las cuentas de Microsoft Outlook para iOS y Android configuradas con buzones en Microsoft Cloud Deutschland deba quitarse y agregarse de nuevo a Outlook para sincronizar correctamente la nueva configuración de servicios de Office 365. | Microsoft Outlook para clientes de iOS y Android | Es posible que los buzones de Outlook configurados anteriormente para Microsoft Cloud Deutschland no retome la nueva configuración de servicios de Office 365, lo que provoca errores y degrada el rendimiento de otras experiencias de usuario. Se recomienda a los administradores de TI proporcionar documentación que indique de forma proactiva a los usuarios que quiten y vuelvan a agregar sus cuentas a Microsoft Outlook para iOS y Android si se producen problemas con el inicio de sesión o la sincronización del correo después de la migración. |
| Prepárese para notificar a los usuarios sobre el reinicio y el inicio de sesión en y fuera de sus clientes después de la migración. | Las licencias de cliente de Office pasarán de Microsoft Cloud Deutschland a los servicios de Office 365 durante la migración. Los clientes recogen una nueva licencia válida después de iniciar sesión en los clientes de Office. | Clientes de Aplicaciones de Microsoft 365 |  Los productos de Office de los usuarios necesitan actualizar las licencias de los servicios de Office 365. Si no se actualizan las licencias, los productos de Office pueden experimentar errores de validación de licencia. |
| Cancela las suscripciones de prueba. | Las suscripciones de prueba no se migrarán y bloquearán la transferencia de suscripciones de pago. | Todos los clientes | Los servicios de prueba expiran y no funcionan si los usuarios acceden después de la cancelación. |
| Implemente el cliente de escritorio de Teams para los usuarios que tienen acceso a Skype Empresarial en Alemania. | La migración mueve a los usuarios a Teams para colaborar, llamar y chatear. Implemente el cliente de escritorio de Teams o asegúrese de que hay disponible un explorador compatible. | Clientes de Skype Empresarial | La inacción provocará la falta de disponibilidad de los servicios de colaboración de Teams. |
| Analizar las diferencias en las características de licencia entre Microsoft Cloud Deutschland y los Servicios de Office 365. | Los servicios de Office 365 incluyen características y servicios adicionales que no están disponibles en la nube de Microsoft Deutschland actual. Durante la transferencia de suscripción, las nuevas características estarán disponibles para los usuarios. | Todos los clientes | - Analice las distintas características proporcionadas por las licencias de Microsoft Cloud Deutschland y los Servicios de Office 365. Comience con la descripción del servicio de la [plataforma de Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) <br><br> - Determine si se deben deshabilitar inicialmente las nuevas características de los servicios de Office 365 para limitar los efectos en los usuarios o en la administración de cambios de usuario, y modificar las asignaciones de licencias de usuario según sea necesario. <br><br> - Prepare a los usuarios y al personal de servicio de ayuda para los nuevos servicios y características proporcionados por los servicios de Office 365. |
| Cree directivas de retención en toda [la](https://docs.microsoft.com/microsoft-365/compliance/retention) organización para protegerse de la eliminación involuntaria de contenido durante la migración.  | - Para asegurarse de que los usuarios finales no eliminan accidentalmente el contenido durante la migración, los clientes pueden optar por habilitar una directiva de retención en toda la organización. <br><br> - Aunque la retención no es necesaria, dado que las retenciones realizadas en cualquier momento durante la migración deben funcionar según lo esperado, tener una directiva de retención es un mecanismo de seguridad de copia de seguridad. Al mismo tiempo, es posible que todos los clientes no puedan usar una directiva de retención, especialmente aquellos a los que les preocupa la conservación. | Clientes de Office | Aplique la directiva de retención tal como se describe [en Más información sobre las directivas de retención y las etiquetas de retención.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) |
| Copia de seguridad de la granja de servicios de federación [de Active Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) para escenarios de recuperación ante desastres. | Los clientes necesitan hacer una copia de seguridad de la granja de AD FS correctamente para garantizar que las confianzas de usuario de confianza en los puntos de conexión globales de & Germany se pueden restaurar sin tocar el URI del emisor de los dominios. Microsoft recomienda usar la restauración rápida de AD FS para realizar una copia de seguridad de la granja de servidores y la restauración correspondiente, si es necesario. | Organizaciones de autenticación federada | Acción requerida. La inacción provocará un impacto en el servicio durante la migración si se produce un error en la granja de AD FS del cliente. |


## <a name="exchange-online"></a>Exchange Online

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Notificar a los socios externos de la próxima transición a los servicios de Office 365. | Las configuraciones de espacio de direcciones de disponibilidad permiten compartir información de disponibilidad con Office 365. | Clientes de Exchange Online que han habilitado el uso compartido del calendario y el espacio de direcciones de disponibilidad. | Acción necesaria.  Si no lo hace, puede producirse un error en el servicio o en el cliente en una fase posterior de la migración de clientes. |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>Para Exchange híbrido

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Desinstale las versiones anteriores del Asistente para la configuración híbrida (HCW) y, a continuación, instale y ejecute la versión más reciente, 17.0.5378.0, desde [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | La versión más reciente del HCW incluye las actualizaciones necesarias para dar soporte a los clientes que están haciendo la transición de Microsoft Cloud Deutschland a los Servicios de Office 365. <br><br> Las actualizaciones incluyen cambios en la configuración del certificado local para el conector de envío y el conector de recepción. | Clientes de Exchange Online que ejecutan una implementación híbrida | Acción necesaria. Si no lo hace, puede producirse un error en el servicio o en el cliente. |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

Si tiene SharePoint 2013:

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Limitar los flujos de trabajo de SharePoint 2013, usarlos durante la migración de SharePoint Online. | Reduzca los flujos de trabajo de SharePoint 2013 y complete los flujos de trabajo en ejecución antes de realizar las transiciones. | Clientes de SharePoint Online | La inacción puede causar confusión en el usuario y llamadas al servicio de ayuda. |
|||||

## <a name="mobile"></a>Móvil

Si usas una solución de administración de dispositivos móviles (MDM) de terceros:

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine si se requiere una reconfiguración después de la migración. | Las soluciones MDM pueden dirigirse a `outlook.de` puntos de conexión. En esta transición a Servicios de Office 365, los perfiles de cliente deben actualizarse a la dirección URL de servicios de Office 365. `outlook.office365.com` | Clientes de Exchange Online y MDM | Los clientes pueden seguir funcionando mientras el punto de conexión es accesible, pero producirán un error si los puntos de conexión `outlook.de` de Microsoft Cloud Deutschland ya no están disponibles. |
|||||

## <a name="line-of-business-apps"></a>Aplicaciones de línea de negocio

Si usa un servicio de terceros o aplicaciones de línea de negocio (LOB) integradas con Office 365: 

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Determinar si se requiere una reconfiguración después de la migración. | Los servicios y las aplicaciones de terceros que se integran con Office 365 pueden codificarse para esperar direcciones IP y DIRECCIONES URL de Microsoft Cloud Deutschland. | Todos los clientes | Acción necesaria. La inacción puede provocar errores en el servicio o el software cliente. |
|||||

## <a name="azure"></a>Azure 

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine qué servicios de Azure están en uso y prepárese para la migración futura de Alemania al inquilino de servicios de Office 365 trabajando con sus partners. Siga los pasos descritos en el libro de [reproducción de migración de Azure.](https://docs.microsoft.com/azure/germany/germany-migration-main) | La migración de recursos de Azure es una responsabilidad del cliente y requiere un esfuerzo manual siguiendo los pasos indicados. Comprender qué servicios están en uso en la organización es clave para una migración correcta de los servicios de Azure. <br><br> Los clientes de Office 365 Germany que tienen suscripciones de Azure con la misma partición de identidad (organización) deben seguir el orden que microsoft les ha indicado cuando puedan iniciar la migración de suscripción y servicios. | Clientes de Azure | - Los clientes pueden tener varias suscripciones de Azure, cada suscripción que contenga componentes de infraestructura, servicios y plataforma. <br><br> - Los administradores deben identificar las suscripciones y las partes interesadas para garantizar que la migración y la validación rápidas son posibles como parte de este evento de migración. <br><br> Si no se completa correctamente la migración de estas suscripciones y los componentes de Azure dentro de la escala de tiempo indicada, la finalización de la transición de Office y Azure AD a los servicios de Office 365 puede provocar la pérdida de datos.  <br><br> - Una notificación del centro de mensajes señalará el punto en el que puede comenzar la migración dirigida por el cliente. |
|||||

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

## <a name="dynamics-365"></a>Dynamics 365

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Para las suscripciones de espacio aislado de Dynamics 365, asegúrese de descargar el entorno de producción de la instancia de Dynamics SQL desde su suscripción a Dynamics 365 en Microsoft Cloud Deutschland. La copia de seguridad de producción más reciente debe restaurarse en el espacio aislado antes de la migración de espacio aislado. | La migración de Dynamics 365 requiere que los clientes se aseguren de que el entorno de espacio aislado se actualice con la base de datos de producción más reciente. | Clientes de Microsoft Dynamics | El equipo de FastTrack ayudará a los clientes a realizar ejecuciones en buen estado para validar la actualización de la versión de 8.x a 9.1.x. |
|||||

## <a name="power-bi"></a>Power BI

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Eliminación de objetos de suscripciones de Power BI que no se migrarán de Power BI Microsoft Cloud Deutschland a los servicios de Office 365. | La migración de los servicios de Power BI requerirá una acción del cliente para eliminar ciertos artefactos, como conjuntos de datos y paneles. | Clientes de Power BI | Es posible que los administradores deban quitar los siguientes elementos de su suscripción: <br> - Real-Time conjuntos de datos (por ejemplo, conjuntos de datos de transmisión por secuencias o inserción) <br> - Origen de datos y configuración de Puerta de enlace de datos local de Power BI |
|||||

## <a name="dns"></a>DNS

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Quite MSOID, CName del DNS propiedad del cliente si existe en cualquier momento antes del corte de Azure AD. Se puede establecer un TTL de 5 minutos para que el cambio pueda tener efecto rápidamente. | Cambios en la zona DNS propiedad del cliente | Clientes de servicios cliente de Office | 
|||||

## <a name="federated-identity"></a>Identidad federada

| Pasos | Description | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Agregue un identificador de inicio de sesión único (SSO) a una relación de confianza para usuario autenticado existente y deshabilite las actualizaciones automáticas de metadatos de AD FS. | Se debe agregar un identificador a la confianza de usuario de confianza de AD FS antes de iniciar la migración. Para evitar la eliminación accidental del identificador de usuario de confianza, deshabilite la actualización automática para las actualizaciones de metadatos. <br><br> Ejecute este comando en el servidor de AD FS: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Organizaciones de autenticación federada | Acción requerida. La inacción provocará un impacto en el servicio durante la migración.  |
| Generar confianza de usuario de confianza para los puntos de conexión globales de Azure AD. | Los clientes necesitan crear manualmente una relación de confianza para usuario de confianza (RPT) para los [puntos de conexión](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) globales. Para ello, agrega una nueva RPT a través de la GUI aprovechando la dirección URL de metadatos de federación global y, a continuación, usando las reglas de notificación de [RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) de Azure AD (en la Ayuda de AD FS) para generar las reglas de notificación e importarlas a la RPT. | Organizaciones de autenticación federada | Acción requerida. La inacción provocará un impacto en el servicio durante la migración. |
|||||

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
