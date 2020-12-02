---
title: Información previa al trabajo adicional para la migración desde la nube de Microsoft Alemania
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Resumen: información previa al trabajo al cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.'
ms.openlocfilehash: 41953aa9d91faa91bd983fbbc8d93baf08c172ed
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551715"
---
# <a name="additional-pre-work-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información previa al trabajo adicional para la migración desde la nube de Microsoft Alemania

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Asegúrese de que la conectividad de red con [las direcciones IP y los URL de servicios de Office 365](https://aka.ms/o365urls). | Todos los clientes y servicios hospedados por el cliente que se usan para tener acceso al servicio de Office 365 deben poder acceder a los puntos de conexión de servicios de Office 365. | Todos los clientes de transición y clientes con acceso de red restringido al Alemania en la nube de Microsoft. | Acción necesaria. La inacción puede dar lugar a errores en el software del cliente o del servicio. |
| Revise y prepare los cambios de DNS relacionados con la migración. | El cliente prepara las entradas DNS para Exchange Online y Exchange Online Protection (registro MX, etc.). | Clientes de Exchange Online | Se trata de una acción recomendada. Ninguna acción significa que el correo electrónico de los clientes migrados puede enrutar a través de Microsoft Cloud Alemania hasta que se deshabiliten los servicios de Alemania de Microsoft Cloud. |
| Revise y prepare los cambios de DNS relacionados con la migración. | Cambios en las zonas DNS de propiedad del cliente para Skype empresarial online. | Clientes de Skype empresarial online | -Se recomienda actualizar el período de vida (TTL) de los registros DNS de los dominios de los clientes a 5 minutos para acelerar la actualización de los registros DNS. Sin embargo, la transferencia administrada por Microsoft asociada con este cambio de DNS puede producirse en cualquier momento dentro del período de tiempo de cambio de 24 horas proporcionado. <br><br> -Es posible que se interrumpa el servicio en el futuro. Los usuarios no podrán iniciar sesión en Skype empresarial y se redirigirán a la experiencia de los equipos migrados en los servicios de Office 365. |
| Preparar el aprendizaje para usuarios finales y la administración y preparación para la transición a Microsoft Teams. | Tener éxito en la transición de Skype a teams mediante la planeación de la comunicación y preparación de los usuarios. | Clientes de Skype empresarial online | -Los clientes necesitan conocer los nuevos servicios y cómo usar una vez que los servicios pasan a los servicios de Office 365. <br><br> -Una vez que se hayan realizado los cambios en los dominios de clientes y el dominio inicial, los usuarios iniciarían sesión en Skype empresarial y verán que ahora se migran a teams. Esto también descargaría el cliente de escritorio para Teams en segundo plano. |
| Prepare el aprendizaje del usuario final y la administración sobre los usuarios para quitar y volver a agregar su cuenta a Microsoft Outlook para iOS y Android. | Las cuentas de Microsoft Outlook para iOS y Android configuradas con buzones en Microsoft Cloud Alemania pueden tener que quitarse y agregarse de nuevo a Outlook para poder sincronizar correctamente la nueva configuración de los servicios de Office 365. | Microsoft Outlook para clientes de iOS y Android | Los buzones de Outlook configurados anteriormente para Microsoft Cloud Alemania pueden no escoger la nueva configuración de servicios de Office 365, lo que provoca errores y disminuye el rendimiento de otras experiencias de usuario. Se recomienda a los administradores de ti que proporcionen documentación que indique de forma proactiva a los usuarios que quiten y vuelvan a agregar sus cuentas a Microsoft Outlook para iOS y Android en caso de que se produzcan problemas con el inicio de sesión o la sincronización de correo después de la migración. |
| Prepárese para notificar a los usuarios sobre el reinicio y la sesión en y hacia los clientes después de la migración. | Las licencias de cliente de Office pasarán de Alemania de Microsoft Cloud a Office 365 Services en la migración. Los clientes recogen una nueva licencia válida después de cerrar la sesión de y en los clientes de Office. | Clientes de Microsoft 365 apps |  Los productos de Office de los usuarios necesitan actualizar las licencias de los servicios de Office 365. Si las licencias no se actualizan, los productos de Office pueden experimentar errores de validación de licencia. |
| Cancelar las suscripciones de prueba. | No se migrarán las suscripciones de prueba y se bloqueará la transferencia de suscripciones de pago. | Todos los clientes | Los servicios de prueba han expirado y no funcionan si los usuarios tienen acceso a ellos después de la cancelación. |
| Implementar el cliente de escritorio de Microsoft Teams para los usuarios que tienen acceso a Skype empresarial en Alemania. | La migración mueve a los usuarios a Microsoft Teams para colaboración, llamadas y chat. Puede implementar el cliente de escritorio de Microsoft Teams o asegurarse de que haya un explorador compatible disponible. | Clientes de Skype empresarial | La inacción dará como resultado la no disponibilidad de los servicios de colaboración de Microsoft Teams. |
| Analizar las diferencias de las características de licencia entre Microsoft Cloud Alemania y los servicios de Office 365. | Los servicios de Office 365 incluyen características y servicios adicionales que no están disponibles en el Alemania actual de la nube de Microsoft. Durante la transferencia de la suscripción, las nuevas características estarán disponibles para los usuarios. | Todos los clientes | -Analizar las distintas características proporcionadas por las licencias de los servicios de Microsoft Cloud Alemania y Office 365. Comience con la [Descripción del servicio de la plataforma 365 de Office](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> -Determine si las nuevas características de servicios de Office 365 deben deshabilitarse inicialmente para limitar los efectos en los usuarios o en la administración de cambios de usuario y modificar las asignaciones de licencia de usuario según sea necesario. <br><br> -Preparar a los usuarios y al personal del servicio de asistencia para obtener nuevos servicios y características proporcionados por los servicios de Office 365. |
| Crear [directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention) de toda la organización para proteger contra la eliminación inadvertida del contenido durante la migración.  | -Para garantizar que los usuarios finales no eliminen accidentalmente el contenido durante la migración, los clientes pueden elegir habilitar una directiva de retención para toda la organización. <br><br> -Aunque la retención no es necesaria, dado que las suspensiones realizadas en cualquier momento durante la migración deben funcionar según lo esperado, tener una directiva de retención es un mecanismo de seguridad de copia de seguridad. Al mismo tiempo, es posible que una directiva de retención no la usen todos los clientes, en especial aquellos que se preocupan de la preservación. | Clientes de Office | Aplique la Directiva de retención tal como se describe en [información sobre directivas de retención y etiquetas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies). |
| [Copia de seguridad de la granja de servicios de Federación de Active Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) para escenarios de recuperación ante desastres. | Los clientes necesitan realizar una copia de seguridad de la granja de AD FS correctamente para asegurarse de que las relaciones de confianza para usuario autenticado con los puntos de conexión de & Alemania globales se puedan restaurar sin tocar el URI del emisor de los dominios. Microsoft recomienda usar la restauración rápida de AD FS para realizar una copia de seguridad de la granja de servidores y la restauración correspondiente, si es necesario. | Organizaciones de autenticación federada | Acción necesaria. La inacción dará como resultado un impacto en el servicio durante la migración si se produce un error en la granja de AD FS del cliente. |


## <a name="exchange-online"></a>Exchange en línea

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Notifique a los socios externos de la próxima transición a los servicios de Office 365. | La configuración del espacio de direcciones de disponibilidad permite el uso compartido de información de disponibilidad con Office 365. | Clientes de Exchange online que han habilitado el espacio de direcciones de calendario y disponibilidad compartido. | Acción necesaria.  Si no lo hace, podrían producirse errores de servicio o de cliente en una fase posterior de la migración de clientes. |
|||||

Si tiene Exchange híbrido:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Desinstalar versiones anteriores del asistente de configuración híbrida (HCW) y, a continuación, instalar y ejecutar la versión más reciente, 17.0.5378.0, desde [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | La versión más reciente del HCW incluye las actualizaciones necesarias para admitir a los clientes que están cambiando de Alemania en la nube de Microsoft a Office 365 Services. <br><br> Las actualizaciones incluyen cambios en la configuración de certificados locales para el conector de envío y el conector de recepción. | Clientes de Exchange online que ejecutan implementación híbrida | Acción necesaria. Si no lo hace, podrían producirse errores en el servicio o en el cliente. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

Si tiene SharePoint 2013:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Limite los flujos de trabajo de SharePoint 2013, use durante la migración de SharePoint Online. | Reduzca los flujos de trabajo de SharePoint 2013 y complete los flujos de trabajo en vuelo antes de las transiciones. | Clientes de SharePoint Online | La inacción puede dar lugar a confusión del usuario y llamadas al servicio de asistencia. |
|||||

<!--
[Reference:  If Pre-Work][ SharePoint 2013 ]
--> 

## <a name="mobile"></a>Móvil

Si está usando una solución de administración de dispositivos móviles (MDM) de terceros:

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine si es necesaria una reconfiguración después de la migración. | Las soluciones MDM pueden tener extremos de destino `outlook.de` . En esta transición a los servicios de Office 365, los perfiles de cliente deben actualizarse a la dirección URL de los servicios de Office 365 `outlook.office365.com` . | Clientes de Exchange Online y MDM | Los clientes pueden seguir funcionando mientras `outlook.de` se tiene acceso al punto de conexión, pero se producirán un error si los puntos de conexión de Microsoft Cloud Alemania ya no están disponibles. |
|||||

<!--
[Reference:  If Pre-Work][ Mobile]
-->             

## <a name="line-of-business-apps"></a>Aplicaciones de línea de negocio

Si está usando un servicio de terceros o aplicaciones de línea de negocio (LOB) integradas con Office 365: 

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine si es necesaria una reconfiguración después de la migración. | Los servicios y aplicaciones de terceros que se integran con Office 365 pueden codificarse para esperar direcciones IP y URL de Microsoft Cloud Alemania. | Todos los clientes | Acción necesaria. La inacción puede dar lugar a errores en el software del cliente o del servicio. |
|||||

<!--
[Reference:  If Pre-Work][ LOB]
--> 

## <a name="azure"></a>Azure 

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Trabaje con sus asociados para determinar qué servicios de Azure se están usando y preparar la migración futura de Alemania al inquilino de Office 365 Services. Siga los pasos descritos en la [Guía de migración de Azure](https://docs.microsoft.com/azure/germany/germany-migration-main). | La migración de los recursos de Azure es una responsabilidad del cliente y requiere un esfuerzo manual tras los pasos recomendados. Comprender qué servicios están en uso en la organización es clave para la migración correcta de los servicios de Azure. <br><br> Office 365 Germany los clientes que tienen suscripciones de Azure en la misma partición de identidad (organización) deben seguir el orden indicado por Microsoft cuando puedan comenzar la migración de la suscripción y de los servicios. | Clientes de Azure | -Los clientes pueden tener varias suscripciones de Azure, cada una de las cuales contiene la infraestructura, los servicios y los componentes de la plataforma. <br><br> -Los administradores deben identificar las suscripciones y las partes interesadas para garantizar que la migración y la validación de mensajes son posibles como parte de este evento de migración. <br><br> Si no completa correctamente la migración de estas suscripciones y de los componentes de Azure en la escala de tiempo indicada, afectará a la finalización de la transición de Office y Azure AD a los servicios de Office 365 y puede provocar la pérdida de datos.  <br><br> -Una notificación del centro de mensajes indicará el punto en el que puede comenzar la migración dirigida a los clientes. |
|||||

<!--
[Reference:  If Azure Pre-Work][ Azure]
-->  

## <a name="dynamics-365"></a>Dynamics 365

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Para las suscripciones de espacio aislado de Dynamics 365, asegúrese de descargar el entorno de producción de la instancia de Dynamics SQL desde la suscripción a Dynamics 365 en la nube de Microsoft Alemania. La última copia de seguridad de producción debe restaurarse en el espacio aislado antes de la migración de espacio aislado. | La migración de Dynamics 365 requiere que los clientes garanticen que el entorno de espacio aislado se actualice con la base de datos de producción más reciente. | Clientes de Microsoft Dynamics | El equipo de FastTrack ayudará a los clientes en la realización de ejecuciones secas para validar la actualización de la versión de 8. x a 9.1. x. |
|||||

<!--
[Reference: Prework][Dynamics]
-->             

## <a name="power-bi"></a>Power BI

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Eliminación de objetos de suscripciones de Power BI que no se migrarán de Power BI Microsoft Cloud Alemania a Office 365 Services. | La migración de los servicios de Power BI requerirá la acción del cliente para eliminar ciertos artefactos, como datasets y paneles. | Clientes de Power BI | Es posible que los administradores tengan que quitar los siguientes elementos de su suscripción: <br> -Real-Time conjuntos de valores (por ejemplo, conjuntos de bits streaming o push) <br> -Configuración y origen de datos de puerta de enlace de datos local de Power BI |
|||||

<!--
[Reference: Prework][Power BI]
--> 

## <a name="dns"></a>DNS

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Revise y prepare el cambio de DNS si el DNS actual tiene una entrada CName de MSOID. | Cambios en la zona DNS de propiedad del cliente | Clientes de servicios de cliente de Office | Actualice el período de vida (TTL) de los registros DNS de propiedad del cliente a 5 minutos si existe un CName de MSOID. |
|||||

<!--
[Reference: Prework][DNS]
-->             

## <a name="federated-identity"></a>Identidad federada

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Generar la relación de confianza para usuario autenticado para los puntos de conexión globales de Azure AD. | Los clientes deben crear manualmente una relación de confianza para usuario autenticado (RPT) en los extremos [globales](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) . Para ello, se agrega un nuevo RPT mediante GUI aprovechando la dirección URL de metadatos de Federación global y, a continuación, se usan [las reglas de notificación de Azure ad RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (en la ayuda de AD FS) para generar las reglas de notificación e importarlas en la RPT. | Organizaciones de autenticación federada | Acción necesaria. La inacción dará como resultado un impacto en el servicio durante la migración. |
|||||

<!--
[Reference: Prework][Federation]
-->  

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Desplazarse por la transición:

- [Impacto y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [servicios](ms-cloud-germany-transition-add-general.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
