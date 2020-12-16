---
title: Acciones y impacto de las fases de migración para la migración de Microsoft Cloud Alemania (general)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 'Resumen: comprenda las acciones de fases de migración y los efectos de cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de administración de información en alemán.'
ms.openlocfilehash: 4a032ab88704cfb46b3f451d939a784d222cbb40
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688634"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Acciones y impacto de las fases de migración para la migración de Microsoft Cloud Alemania (general)

Las migraciones de inquilinos desde Microsoft Cloud Alemania a la región de Alemania de los servicios de Office 365 de Microsoft se ejecutan como un conjunto de acciones configuradas para cada carga de trabajo. Estas acciones garantizan que los datos y la experiencia críticos se migren a los servicios de Office 365. Una vez agregado el inquilino a la cola de migración, cada carga de trabajo se completará como un conjunto de pasos que se ejecutan en el servicio back-end. Algunas cargas de trabajo pueden requerir acciones del administrador (o del usuario), o la migración puede afectar al uso de las fases que se ejecutan y se explican en [¿cómo se organiza la migración?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Las secciones siguientes contienen acciones y efectos para las cargas de trabajo a medida que avanzan en varias fases de la migración. Revise las tablas y determine qué acciones o efectos se aplican a su organización. Asegúrese de que está preparado para ejecutar los pasos en las fases respectivas según sea necesario. Si no se completan los pasos necesarios, es posible que se produzca una interrupción del servicio y que se retrase la finalización de la migración a los servicios de Office 365.

## <a name="exchange-online"></a>Exchange en línea

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| La nueva región de Alemania se agrega a la configuración de la organización existente y los buzones se mueven a los servicios de Office 365. | La configuración de Exchange Online agrega la nueva región alemana go-local a la organización de transición. Esta región de servicios de Office 365 está configurada como predeterminada, lo que permite que el servicio de equilibrio de carga interno redistribuya los buzones de correo a la región predeterminada adecuada en los servicios de Office 365. En esta transición, los usuarios de cada lado (los servicios de Alemania o Office 365) están en la misma organización y pueden usar cualquier punto de conexión de dirección URL. | Exchange en línea | -Transición de los usuarios y servicios de las direcciones URL de Alemania a direcciones URL de servicios de Office 365 ( `https://outlook.office365.com` ). <br><br> -Los usuarios seguirán accediendo al servicio a través de direcciones URL heredadas de Alemania durante la migración. No es necesario realizar ninguna acción inmediata. <br><br> -Los usuarios deben empezar a usar el portal de office.com para las características de Office Online (calendario, correo, personas). La navegación a los servicios que todavía no se han migrado a los servicios de Office 365 no funcionará hasta que se migren. <br><br> -Outlook Web App no proporcionará la experiencia de carpeta pública durante la migración. |
|||||

Consideraciones adicionales:

- `myaccount.msft.com` solo funcionará después del traslado de Office 365. Los vínculos producirán mensajes de error "se ha producido un problema" hasta esa fecha.

- Los usuarios de Outlook Web App que tienen acceso a un buzón compartido en el otro entorno (por ejemplo, un usuario del entorno de Alemania accede a un buzón compartido en el entorno global) se les pedirá que se autentiquen una segunda vez. En primer lugar, el usuario debe autenticar y obtener acceso a su buzón en y, `outlook.office.de` a continuación, abrir el buzón compartido que se encuentra en `outlook.office365.com` . Deberán autenticarse una segunda vez cuando obtengan acceso a los recursos compartidos que se hospedan en el otro servicio.

- Para los clientes de Microsoft Cloud Alemania o los que están en transición, cuando se agrega un buzón compartido a Outlook mediante el **> de archivos > agregar cuenta**, se puede producir un error al ver los permisos del calendario (el cliente de Outlook intenta usar la API de REST `https://outlook.office.de/api/v2.0/Me/Calendars` ). Los clientes que quieran agregar una cuenta para ver permisos de calendario pueden agregar la clave del registro como se describe en [cambios en la experiencia del usuario para compartir un calendario en Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para asegurarse de que esta acción se realice correctamente. Esta clave del registro se puede implementar en toda la organización mediante la Directiva de grupo.

- Durante la fase de migración, el uso de los cmdlets de PowerShell **New-migrationendpoint**, **set-migrationendpoint** y **Test-MigrationsServerAvailability** puede dar como resultado errores (error en el proxy). Esto ocurre cuando el buzón de correo de arbitraje ha migrado a todo el mundo pero el buzón de administrador no lo ha hecho o viceversa. Para resolver esto, al crear la sesión de PowerShell de inquilino, use el buzón de correo de arbitraje como la sugerencia de enrutamiento en el **ConnectionUri**. Por ejemplo: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Si está usando Exchange Online híbrido:

    - Debe volver a ejecutar el Asistente para la configuración híbrida (HCW) para actualizar la configuración local con el Alemania en la nube de Microsoft antes de la transición y volver a ejecutar el HCW tras la limpieza con los servicios de Office 365. Si usa dominios personalizados, es posible que se requieran actualizaciones DNS adicionales.

Para obtener más información acerca de las diferencias para las organizaciones en la migración y después de migrar los recursos de Exchange Online, revise la información de la [experiencia del cliente durante la migración a Office 365 Services en las nuevas regiones del centro de](ms-cloud-germany-transition-experience.md)datos en alemán.

## <a name="exchange-online-protection"></a>Exchange Online Protection

Las características back-end de Exchange Online Protection (EOP) se copian en la nueva región de Alemania. 

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Migración del enrutamiento y los detalles del mensaje histórico de Exchange Online. | Exchange Online permite el enrutamiento desde hosts externos a Office 365. Los registros MX externos se transfieren a la ruta al servicio de EOP. La configuración del espacio empresarial y los detalles históricos se migran. | Clientes de Exchange Online | -Las entradas de DNS administradas por Microsoft se actualizan desde EOP de Office 365 Germany a Office 365 Services. <br><br> -Los clientes deben esperar 30 días después de la migración de EOP dual Write para la migración de EOP. De lo contrario, es posible que se pierdan datos. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Se realiza la transición de SharePoint y OneDrive. | SharePoint y OneDrive se migran desde Microsoft Cloud Alemania a los servicios de Office 365 en esta fase. Se conservan las URL de Alemania de Microsoft Cloud existentes (por ejemplo, `contoso.sharepoint.de` ). Los tokens emitidos por Microsoft Cloud Alemania u Office 365 Services son válidos durante la transición. | Clientes de SharePoint | -El contenido será de solo lectura durante dos breves períodos durante la migración. Durante este tiempo, se espera un banner "no se puede editar el contenido" en SharePoint. <br><br> -El índice de búsqueda no se conservará y puede tardar hasta 10 días en volver a compilarse. <br><br> -SharePoint/el contenido de OneDrive será de solo lectura durante dos breves períodos durante la migración. Durante este tiempo, los usuarios verán un banner "no se puede editar el contenido" brevemente. <br><br> -Es posible que el índice de búsqueda no esté disponible mientras se vuelve a generar el índice. Durante este período, es posible que las consultas de búsqueda no devuelvan resultados completos. <br><br> -Se conservan los sitios existentes. |
|||||

Consideraciones adicionales:

- Cuando finalice la migración de SharePoint Online a la región alemana, se volverán a crear los índices de datos. Las características que dependen de los índices de búsqueda pueden verse afectadas mientras se completa la reindización.

- Si su organización sigue utilizando flujos de trabajo de SharePoint 2010, dejarán de funcionar después del 31 de diciembre de 2021. Los flujos de trabajo de SharePoint 2013 seguirán siendo compatibles, aunque están desactivados de forma predeterminada para los nuevos inquilinos a partir del 1 de noviembre de 2020. Una vez finalizada la migración al servicio de SharePoint Online, le recomendamos que se mueva a Power Automate u otras soluciones compatibles.

- Una vez finalizada la migración de OneDrive a la región alemana, los índices de datos se vuelven a generar. Las características que dependen de los índices de búsqueda pueden verse afectadas mientras el reindizado está en curso.


## <a name="skype-for-business-online"></a>Skype Empresarial Online

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Migración de Skype empresarial a Microsoft Teams. | Los clientes existentes de Skype empresarial se migran a los servicios de Office 365 en Europa y, a continuación, se pasan a Microsoft Teams en la región de Alemania de los servicios de Office 365. | Clientes de Skype empresarial | -Los usuarios no podrán iniciar sesión en Skype empresarial en la fecha de migración. Diez días antes de la migración, notificaremos a los usuarios finales a través de la banda en el cliente de Skype empresarial que se van a actualizar a Microsoft Teams. También publicaremos en el centro de administración que estos cambios ocurrirán después de los 10 días. <br><br> -Se migra la configuración de la Directiva. <br><br> -Los usuarios se migrarán a teams y ya no tendrán Skype empresarial después de la migración. <br><br> -Los usuarios deben tener instalado el cliente de escritorio de Microsoft Teams. La instalación se llevará a cabo durante los diez días a través de la Directiva de la infraestructura de Skype empresarial, pero si se produce un error, los usuarios aún tendrán que descargar el cliente o conectarse con un explorador compatible. <br><br> -Los contactos y las reuniones se migrarán a teams. <br><br> -Los usuarios no podrán iniciar sesión en Skype empresarial entre las transiciones del servicio de tiempo a los servicios de Office 365 y no hasta que se completen las entradas de DNS del cliente. <br><br> -Los contactos y las reuniones existentes seguirán funcionando como reuniones de Skype empresarial. |
|||||

## <a name="office-services"></a>Servicios de Office

El servicio de Office usado más recientemente (MRU) es un traslado desde el servicio Alemania a Office 365 Services, no una migración. Solo los vínculos MRU del lado de servicios de Office 365 estarán visibles después de la migración desde el portal Office.com. Los vínculos MRU del servicio Alemania no se ven como vínculos MRU en los servicios de Office 365. En Office 365, los vínculos MRU solo son accesibles después de que se complete la migración de inquilinos.

## <a name="subscription"></a>Suscripción

| Pasos (s) | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| No podemos migrar clientes sin consentimiento. | Microsoft tiene el derecho de migrar de una de estas dos maneras, lo que permite a Microsoft organizar la transición de datos y servicios a la instancia de servicios de Office 365. <br> El administrador opta por la migración controlada por Microsoft. <br> Los clientes renuevan las suscripciones en el inquilino Alemania de la nube de Microsoft después del 1 de mayo de 2020. Notificaremos estos clientes de la migración todos los meses a la derecha, esperar 30 días para ofrecer a los clientes la oportunidad de cancelar y, a continuación, optar directamente por el seguimiento en ICM. | Todos los clientes de Office | -Tenant está marcado como Consent para la migración y el centro de administración muestra la confirmación. <br><br> -La confirmación se publica en el inquilino del centro de mensajes de la nube Germany. La configuración del servicio sigue desde los extremos de Alemania en la nube de Microsoft. <br><br> -Supervisar el centro de mensajes para obtener actualizaciones del estado de fase de migración. |
| Se transfieren las suscripciones y se reasignan las licencias. | Una vez que se pasa el inquilino a Office 365 Services, se compran las suscripciones de servicios de Office 365 correspondientes para las suscripciones de Alemania en la nube de Microsoft transferidas. A los usuarios con licencias de Microsoft Cloud Alemania asignadas se les asignará licencias de servicios de Office 365. Las suscripciones heredadas de la nube de Microsoft Alemania se quitan del inquilino de Office 365 Services al finalizar. | Todos los clientes de Office | -Se bloquearán los cambios en las suscripciones existentes (por ejemplo, no hay cambios de suscripción nuevos o de recuento de asientos) durante esta fase. <br><br> -Los cambios de asignación de licencia se bloquearán. <br><br> -La suscripción de Microsoft Cloud Alemania se migrará a la suscripción a Office 365 Services correspondiente. La oferta de servicios de Office 365 de esa suscripción la define Microsoft (también denominada _asignación de ofertas_). <br><br> -El número de características (planes de servicio) que ofrecen los servicios de Office 365 puede ser mayor que en la oferta original de Microsoft Cloud Alemania. Las licencias de usuario de los servicios 365 de Office se asignarán equivalentes a características de Microsoft Cloud Alemania similares (planes de servicio). Las licencias de usuario de todos los usuarios se asignarán automáticamente a las nuevas características. El administrador tiene que realizar una acción explícita para deshabilitar esas licencias, si es necesario. <br><br> -Cuando se haya completado la migración de la suscripción, las suscripciones a los servicios de Office 365 y a Alemania estarán visibles en el portal de administración de Office 365, con el estado de las suscripciones de Alemania como _desaprovisionado_. <br><br> -Se volverán a asignar licencias a los usuarios vinculados a las nuevas suscripciones de Office 365 Services. Los procesos de los clientes que tengan dependencias en las suscripciones de Alemania o los GUID de SKU se romperán y deberán revisarse con la oferta de servicios de Office 365. <br><br> -Las nuevas suscripciones de los servicios de Office 365 se comprarán con el nuevo término (mensual/trimestral o anual) y el cliente recibirá una restitución prorrateada del saldo no usado de la suscripción de Microsoft Cloud Alemania. <br><br> -Partner Microsoft Cloud Alemania no se migrarán los inquilinos. Los clientes de CSP se migrarán a los servicios de Office 365 en el nuevo inquilino de Office 365 Services del mismo socio. Después de la migración de clientes, el asociado puede administrar a este cliente solo desde el inquilino de Office 365 Services. <br><br> -Hay disponible funcionalidad adicional (por ejemplo, Microsoft Planner y Microsoft Flow), a menos que la administración del espacio empresarial la deshabilite. Para obtener información acerca de cómo deshabilitar los planes de servicio asignados a las licencias de los usuarios, vea [deshabilitar el acceso a los servicios de Microsoft 365 mientras se asignan licencias de usuario](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Paso siguiente

[Realizar tareas previas adicionales](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Desplazarse por la transición:

- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
