---
title: Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland (general)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: 'Resumen: comprenda las acciones y los impactos de las fases de migración de Microsoft Cloud Alemania (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 9dc2f4c0923f52bfc83a9177b595a6955a3afa8f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242739"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Fases de migración acciones e impactos para la migración desde Microsoft Cloud Deutschland (general)

Las migraciones de inquilinos de Microsoft Cloud Deutschland a la región de Alemania de los servicios de Office 365 de Microsoft se ejecutan como un conjunto de fases y sus acciones configuradas para cada carga de trabajo. En esta figura se muestran las nueve fases de migración a los nuevos centros de datos alemanes.

![Las nueve fases de migración a los nuevos centros de datos de Alemania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Las fases y sus acciones garantizan que los datos y experiencias críticos se migren a los servicios de Office 365. Después de agregar el inquilino a la cola de migración, cada carga de trabajo se completará como un conjunto de pasos que se ejecutan en el servicio back-end. Algunas cargas de trabajo pueden requerir acciones por parte del administrador (o usuario) o la migración puede afectar al uso de las fases que se ejecutan y se analizan en ¿Cómo se organiza la [migración?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Las secciones siguientes contienen acciones y efectos para las cargas de trabajo a medida que progresan a través de varias fases de la migración. Revise las tablas y determine qué acciones o efectos son aplicables a su organización. Asegúrese de que está preparado para ejecutar los pasos en las fases correspondientes según sea necesario. Si no se completan los pasos necesarios, se puede producir una interrupción del servicio y puede retrasar la finalización de la migración a los servicios de Office 365.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fase 4 de 9)

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Se ha transición de SharePoint y OneDrive. | SharePoint y OneDrive se migran de Microsoft Cloud Deutschland a los servicios de Office 365 en esta fase. Se conservan las direcciones URL existentes de Microsoft Cloud Deutschland (por ejemplo, `contoso.sharepoint.de` ). Los tokens emitidos por Microsoft Cloud Deutschland u servicios de Office 365 son válidos durante la transición. | Clientes de SharePoint | - El contenido será de solo lectura durante dos breves períodos durante la migración. Durante este tiempo, espere un banner "no se puede editar contenido" en SharePoint. <br><br> - El índice de búsqueda no se conservará y puede tardar hasta 10 días en volver a generarse. <br><br> - El contenido de SharePoint/OneDrive será de solo lectura durante dos breves períodos durante la migración. Los usuarios verán un banner "no se puede editar contenido" brevemente durante este tiempo. <br><br> - Es posible que el índice de búsqueda no esté disponible mientras se recompile el índice. Durante este período, es posible que las consultas de búsqueda no devuelvan resultados completos. <br><br> - Los sitios existentes se conservan. |
|||||

Consideraciones adicionales:

- Cuando finalice la migración de SharePoint Online a la región alemana, se volverán a crear los índices de datos. Las características que dependen de los índices de búsqueda pueden verse afectadas mientras se completa la reindexación.

- Si su organización aún usa flujos de trabajo de SharePoint 2010, ya no funcionarán después del 31 de diciembre de 2021. Los flujos de trabajo de SharePoint 2013 seguirán siendo compatibles, aunque desactivados de forma predeterminada para los nuevos inquilinos a partir del 1 de noviembre de 2020. Una vez completada la migración al servicio de SharePoint Online, se recomienda pasar a Power Automate u otras soluciones compatibles.

- Una vez completada la migración de OneDrive a la región alemana, se reconstruyen los índices de datos. Las características que dependen de índices de búsqueda pueden verse afectadas mientras la reindexación está en curso.

- Los clientes de Microsoft Cloud Deutschland cuya instancia de SharePoint Online aún no se ha migrado deben permanecer en el módulo de PowerShell de SharePoint Online/Microsoft.SharePointOnline.CSOM versión 16.0.20616.12000 o posterior. De lo contrario, se producirá un error en las conexiones a SharePoint Online a través de PowerShell o el modelo de objetos del lado cliente.

- Los clientes de Microsoft Cloud Deutschland cuya instancia de SharePoint Online se migra deben actualizar el módulo de PowerShell de SharePoint Online/Microsoft.SharePointOnline.CSOM a la versión 16.0.20717.12000 o posterior. De lo contrario, se producirá un error en las conexiones a SharePoint Online a través de PowerShell o el modelo de objetos del lado cliente.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 de 9)

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| La nueva región de Alemania se agrega a la configuración de la organización existente y los buzones se mueven a los servicios de Office 365. | La configuración de Exchange Online agrega la nueva región alemana go-local a la organización de transición. Esta región de servicios de Office 365 está establecida como predeterminada, lo que permite al servicio de equilibrio de carga interno redistribuir buzones a la región predeterminada adecuada en los servicios de Office 365. En esta transición, los usuarios de cualquier lado (servicios de Alemania u Office 365) están en la misma organización y pueden usar cualquier punto de conexión de dirección URL. | Exchange Online | - Realizar la transición de usuarios y servicios de las direcciones URL de Alemania a las direcciones URL de servicios de Office 365 ( `https://outlook.office365.com` ). <br><br> - Los usuarios seguirán teniendo acceso al servicio a través de direcciones URL heredadas de Alemania durante la migración. No se necesita ninguna acción inmediata. <br><br> - Los usuarios deben empezar a usar el portal office.com para las características de Office Online (calendario, correo, personas). La navegación a los servicios que aún no se han migrado a los servicios de Office 365 no funcionará hasta que se migre. <br><br> - Outlook Web App no proporcionará la experiencia de carpetas públicas durante la migración. |
|||||

Consideraciones adicionales:

- `myaccount.msft.com` solo funcionará después de la cutover de Office 365. Los vínculos producirán mensajes de error de "algo salió mal" hasta ese momento.

- Se pedirá a los usuarios de Outlook Web App que tienen acceso a un buzón compartido en el otro entorno (por ejemplo, un usuario del entorno de Alemania tiene acceso a un buzón compartido en el entorno global) para que se autentiquen por segunda vez. El usuario debe autenticarse primero y tener acceso a su buzón en y, a continuación, abrir el buzón `outlook.office.de` compartido que se encuentra en `outlook.office365.com` . Necesitarán autenticarse una segunda vez al obtener acceso a los recursos compartidos hospedados en el otro servicio.

- Para los clientes existentes de Microsoft Cloud Deutschland o los que están en transición, cuando se agrega un buzón compartido a Outlook mediante Archivo **> Información >** Agregar cuenta, es posible que se fallen los permisos de calendario (el cliente de Outlook intenta usar la API de `https://outlook.office.de/api/v2.0/Me/Calendars` Rest). Los clientes que quieran agregar una cuenta para ver los permisos de calendario pueden agregar la clave del Registro tal como se describe en Cambios en la experiencia del usuario para compartir un calendario en [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantizar que esta acción se realice correctamente. Esta clave del Registro se puede implementar en toda la organización mediante la directiva de grupo.

- Durante la fase de migración, el uso de los cmdlets de PowerShell **New-migrationEndpoint**, **Set-MigrationEndpoint** y **Test-MigrationsServerAvailability** puede provocar errores (error en el proxy). Esto sucede cuando el buzón de arbitraje se ha migrado a todo el mundo, pero el buzón de administración no lo ha hecho o viceversa. Para resolver esto, al crear la sesión de PowerShell del inquilino, use el buzón de arbitraje como sugerencia de enrutamiento en **ConnectionUri**. Por ejemplo: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Si usa Exchange Online híbrido:

    - Debe volver a ejecutar el Asistente para la configuración híbrida (HCW) para actualizar la configuración local con Microsoft Cloud Deutschland antes de la transición y volver a ejecutar el HCW tras la limpieza en los servicios de Office 365. Es posible que se requieran actualizaciones DNS adicionales si usa dominios personalizados.

Para obtener más información sobre las diferencias de las organizaciones en la migración y después de migrar los recursos de Exchange Online, revise la información de la experiencia del cliente durante la migración a los servicios de [Office 365](ms-cloud-germany-transition-experience.md)en las nuevas regiones del centro de datos alemán.

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (fase 6 de 9)

Las características back-end de Exchange Online Protection (EOP) se copian en la nueva región de Alemania. 

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Migración del enrutamiento de Exchange Online y detalles históricos de mensajes. | Exchange Online permite el enrutamiento desde hosts externos a Office 365. Los registros MX externos se transiciónn para enrutar al servicio EOP. Se migran la configuración del espacio empresarial y los detalles históricos. | Clientes de Exchange Online | - Las entradas DNS administradas por Microsoft se actualizan de Office 365 Germany EOP a los servicios de Office 365. <br><br> - Los clientes deben esperar 30 días después de la escritura dual de EOP para la migración de EOP. De lo contrario, puede haber una pérdida de datos. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype Empresarial Online (fase 7 de 9)

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Migración de Skype Empresarial a Teams. | Los clientes existentes de Skype Empresarial se migran a los servicios de Office 365 en Europa y, a continuación, se pasa a Microsoft Teams en la región de Alemania de los servicios de Office 365. | Clientes de Skype Empresarial | - Los usuarios no podrán iniciar sesión en Skype Empresarial en la fecha de migración. Diez días antes de la migración, publicaremos en el Centro de administración para que sepa cuándo se llevará a cabo la migración y de nuevo cuando se inicie la migración. <br><br> - Se migra la configuración de directiva. <br><br> - Los usuarios se migrarán a Teams y ya no tendrán Skype Empresarial después de la migración. <br><br> - Los usuarios deben tener instalado el cliente de escritorio de Teams. La instalación se realizará durante los 10 días mediante la directiva en la infraestructura de Skype Empresarial, pero si esto falla, los usuarios seguirán teniendo que descargar el cliente o conectarse con un explorador compatible. <br><br> - Los contactos y reuniones se migrarán a Teams. <br><br> - Los usuarios no podrán iniciar sesión en Skype Empresarial entre las transiciones de servicio a los servicios de Office 365 y no hasta que se completen las entradas DNS del cliente. <br><br> - Los contactos y las reuniones existentes seguirán funcionando como reuniones de Skype Empresarial. |
|||||


## <a name="office-apps-phase-8-of-9"></a>Aplicaciones de Office (fase 8 de 9)

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Clientes, Office Online durante la cutover del cliente de Office, Azure AD finaliza el ámbito de inquilino para apuntar a los servicios de Office 365. | Este cambio en la configuración permite a los clientes de Office actualizar y apuntar a los puntos de conexión de servicios de Office 365. | Todos los clientes de Office | - Notifique a los usuarios que cierren todas las aplicaciones de _Office_ y, a continuación, vuelvan a iniciar sesión (o fuercen a los clientes a reiniciarse y a los usuarios que inicien sesión) para permitir que los clientes de Office puedan retomar el cambio. <br><br> - Notifique a los  usuarios y al personal del servicio de ayuda que los usuarios pueden ver un banner de Office que les pide que reactiven las aplicaciones de Office en un plazo de 72 horas a partir de la escala. <br><br> - Todas las aplicaciones de Office en equipos personales deben cerrarse y los usuarios deben cerrar sesión y volver a iniciar sesión. En la barra de activación amarilla, inicie sesión para volver a activar los servicios de Office 365. <br><br> - Las máquinas compartidas requerirán acciones similares a las máquinas personales y no requerirán un procedimiento especial. <br><br> - En dispositivos móviles, los usuarios deben cerrar sesión en las aplicaciones, cerrarlas y volver a iniciarla. |
|||||


## <a name="office-services"></a>Servicios de Office

El servicio usado más recientemente (MRU) en Office es un traslado del servicio de Alemania a los servicios de Office 365, no una migración. Solo los vínculos de MRU del lado de servicios de Office 365 estarán visibles después de la migración desde Office.com portal. Los vínculos de MRU del servicio de Alemania no son visibles como vínculos de MRU en los servicios de Office 365. En Office 365, solo se puede obtener acceso a los vínculos de MRU una vez completada la migración del espacio empresarial.

## <a name="subscription"></a>Suscripción

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| No podemos migrar clientes sin consentimiento. | Microsoft obtiene el derecho de migrar de dos maneras, lo que permite a Microsoft organizar la transición de datos y servicios a la instancia de servicios de Office 365. <br> El administrador opta por la migración controlada por Microsoft. <br> Los clientes renuevan cualquier suscripción en su inquilino de Microsoft Cloud Deutschland después del 1 de mayo de 2020. Notificaremos a estos clientes el derecho de migración cada mes, esperaremos 30 días para dar a los clientes la oportunidad de cancelar y, a continuación, participaremos directamente en el seguimiento en el ICM. | Todos los clientes de Office | - El espacio empresarial se marca como consentido para la migración y el Centro de administración muestra la confirmación. <br><br> - El acuse de recibo se publica en el inquilino del Centro de mensajes de Cloud Germany. La configuración del servicio continúa desde los puntos de conexión de Microsoft Cloud Deutschland. <br><br> - Supervisar el Centro de mensajes para obtener actualizaciones sobre el estado de la fase de migración. |
| Las suscripciones se transfieren y las licencias se reasignan. | Después de realizar la transición del espacio empresarial a los servicios de Office 365, se adquieren las suscripciones de servicios de Office 365 correspondientes para las suscripciones transferidas de Microsoft Cloud Deutschland. A los usuarios con licencias de Microsoft Cloud Deutschland asignadas se les asignarán licencias de servicios de Office 365. Las suscripciones heredadas de Microsoft Cloud Deutschland se quitan del inquilino de servicios de Office 365 al finalizar. | Todos los clientes de Office | - Los cambios en las suscripciones existentes se bloquearán (por ejemplo, no habrá nuevas compras de suscripción ni cambios en el recuento de puestos) durante esta fase. <br><br> - Se bloquearán los cambios de asignación de licencias. <br><br> - La suscripción a Microsoft Cloud Deutschland se migrará a la suscripción de servicios de Office 365 correspondiente. Microsoft define la oferta de servicios de Office 365 de esa suscripción (también conocida como _asignación de ofertas)._ <br><br> - El número de características (planes de servicio) que ofrecen los servicios de Office 365 puede ser mayor que en la oferta original de Microsoft Cloud Deutschland. Las licencias de usuario en los servicios de Office 365 se asignarán de forma equivalente a características similares de Microsoft Cloud Deutschland (planes de servicio). Las licencias de usuario de todos los usuarios se asignarán automáticamente a las nuevas características. El administrador debe realizar una acción explícita para deshabilitar esas licencias, si es necesario. <br><br> - Cuando se complete la migración de la suscripción, tanto los servicios de Office 365 como las suscripciones de Alemania estarán visibles en el Portal de administración de Office 365, con el estado de las suscripciones de Alemania _como desaprovisionadas._ <br><br> - A los usuarios se les reasignarán licencias vinculadas a las nuevas suscripciones de servicios de Office 365. Los procesos de cliente que tengan dependencias en suscripciones de Alemania o GUID de SKU se romperán y deben revisarse con la oferta de servicios de Office 365. <br><br> - Las nuevas suscripciones en los servicios de Office 365 se comprarán con el nuevo plazo (mensual/trimestral/anual) y el cliente recibirá un reembolso prorrateado por el saldo sin usar de la suscripción a Microsoft Cloud Deutschland. <br><br> - Los inquilinos de Microsoft Cloud Deutschland asociados no se migrarán. Los clientes de CSP se migrarán a los servicios de Office 365 en el nuevo inquilino de servicios de Office 365 del mismo partner. Después de la migración del cliente, el partner puede administrar este cliente solo desde el inquilino de servicios de Office 365. <br><br> - Hay funcionalidad adicional disponible (por ejemplo, Microsoft Planner y Microsoft Flow), a menos que lo deshabilite el administrador de inquilinos. Para obtener información sobre cómo deshabilitar los planes de servicio que se asignan a las licencias de los usuarios, vea Deshabilitar el acceso a los servicios de [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)al asignar licencias de usuario.  |
|||||

## <a name="next-step"></a>Paso siguiente

[Realizar trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar por la transición:

- [Trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
