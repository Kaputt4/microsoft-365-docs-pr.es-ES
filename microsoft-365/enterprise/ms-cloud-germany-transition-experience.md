---
title: Qué ha cambiado para la migración a los servicios de Office 365 en las nuevas regiones del centro de datos alemán
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Summary: Understand what has changed for moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.'
ms.openlocfilehash: cadad596011bbcde02b61f01e949c93a5a62a1c3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923831"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Qué ha cambiado para la migración a los servicios de Office 365 en las nuevas regiones del centro de datos alemán

Las migraciones de inquilinos están diseñadas para tener un efecto mínimo en los administradores y usuarios. Sin embargo, hay consideraciones para cada carga de trabajo. Revise las siguientes secciones para comprender mejor la experiencia de migración de las cargas de trabajo.

Las siguientes son las principales diferencias entre los servicios de Microsoft Cloud Deutschland y Office 365 en las nuevas regiones del centro de datos alemán.

| Categoría | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | Los servicios de Office 365 en las nuevas regiones del centro de datos alemán. |
|:-------|:-----|:-------|
| Servicios de Microsoft 365 disponibles para suscripción con un solo espacio empresarial de Office 365 | 15 servicios | 29 servicios <br><br> Para obtener más información, vea ¿Cuál es la disponibilidad del servicio entre las distintas ofertas de servicios en la nube [de Office 365?](ms-cloud-germany-transition.md#serv-avail). |
| Características nuevas | No hay disponibles características nuevas | Las nuevas características estarán disponibles de forma coherente con los servicios de Office 365. |
| Administrador de datos | Sí | No |
| Colaboración entre espacios empresariales con los espacios empresariales globales de Office 365 | No | Sí |
| Residencia de datos de clientes | Los datos de los clientes se almacenarán únicamente en centros de datos alemanes. | Microsoft almacenará los siguientes datos de cliente en reposo exclusivamente en Alemania: <ul><li> Contenido del buzón de Exchange Online (cuerpo del correo electrónico, entradas de calendario y contenido de datos adjuntos de correo electrónico) </li><li> Contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio y archivos cargados en OneDrive para la Empresa </li></ul> |
| Términos aplicables | [Términos de Servicios en línea](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con este [complemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Términos de Online Services](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Lo que no está cambiando:

- El dominio inicial del inquilino (como ) con identificador de inquilino (GUID) y dominios personalizados `contoso.onmicrosoft.de` persistirá después de la migración. 

- Las solicitudes de autenticación de los recursos que se migran a los servicios de Office 365 se conceden mediante el servicio de autenticación de Azure services de Office 365 ( `login.microsoftonline.com` ). Durante la migración, los recursos que permanecen en Office 365 Germany se autentican mediante el servicio de Azure de Alemania existente ( `login.microsoftonline.de` ).

Consideraciones a tener en cuenta:

- Para las cuentas de dominio administrado, después de copiar el inquilino inicial de Azure Active Directory (Azure AD) se ha completado (que es el primer paso de la migración de Azure AD al servicio de Azure AD de servicios de Office 365), los cambios de contraseña, los cambios de restablecimiento de contraseñas de autoservicio (SSPR) y los restablecimientos de contraseña por parte de los administradores deben realizarse desde los portales de servicio de Office 365. Las solicitudes para actualizar las contraseñas del servicio de Alemania no se pueden actualizar correctamente en este momento, ya que el inquilino de Azure AD se ha migrado a los servicios de Office 365. Los restablecimientos de las contraseñas de dominio federado no se ven afectados, ya que se completan en el directorio local.

- Los inicios de sesión de Azure se presentan en el portal al que el usuario intenta acceder. Los registros de auditoría solo están disponibles desde el punto de conexión de servicios de Office 365 después de la transición. Antes de la migración hasta la finalización de la migración, debe guardar los registros de inicio de sesión y auditoría desde el portal de Microsoft Cloud Deutschland.

- Los restablecimientos de contraseña, los cambios de contraseña, el restablecimiento de contraseñas por parte de un administrador de organizaciones administradas (que no usan servicios de federación de Active Directory) deben realizarse a través del portal de servicios de Office 365. Los intentos de los usuarios que tienen acceso a los portales de Microsoft Cloud Deutschland para restablecer contraseñas producirán un error.

- Las solicitudes de interesados (DSR) del Reglamento general de protección de datos (RGPD) se ejecutan desde el portal de administración de Azure de servicios de Office 365 para futuras solicitudes. Los datos de diagnóstico heredados o que no son del cliente que residen en Microsoft Cloud Deutschland se eliminan en o antes de 30 días.

## <a name="subscriptions--licenses"></a>Suscripciones & licencias

- Las suscripciones de Office 365 y Dynamics de Microsoft Cloud Deutschland se transiciónn a la región alemana con la reubicación de Azure AD. A continuación, la organización se actualiza para reflejar las nuevas suscripciones de servicios de Office 365. Durante el breve proceso de transferencia de suscripción, se bloquean los cambios en las suscripciones.

- A medida que el inquilino se pasa a los servicios de Office 365, sus suscripciones y licencias específicas de Alemania se estandarizan con nuevas ofertas de servicios de Office 365. Las suscripciones de servicios de Office 365 correspondientes se compran para las suscripciones transferidas de Alemania. A los usuarios con licencias de Alemania se les asignarán licencias de servicios de Office 365. Una vez completadas, las suscripciones heredadas de Alemania se cancelan y quitan del inquilino actual de servicios de Office 365.

- Después de la migración de las cargas de trabajo individuales, las funciones adicionales están disponibles a través de los servicios de Office 365 (como Microsoft Planner y Microsoft Flow) debido a las nuevas suscripciones de servicios de Office 365. Si es apropiado para su organización, el inquilino o el administrador de licencias pueden deshabilitar los nuevos planes de servicio mientras planea la administración de cambios para introducir los nuevos servicios. Para obtener instrucciones sobre cómo deshabilitar los planes de servicio asignados a las licencias de los usuarios, vea [Disable access to Microsoft 365 services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange en línea

- Las direcciones URL de recursos de Exchange se transiciónn del extremo de Alemania heredado al punto de conexión de servicios de `outlook.office.de` Office 365 `outlook.office365.com` después de la migración. Los usuarios pueden tener acceso a su buzón migrado mediante la dirección URL heredada hasta que se complete la migración. Los clientes deben realizar la transición de usuarios a la nueva dirección URL tan pronto como sea posible después de que la migración de Exchange comience a evitar que afecte a la retirada del entorno de Alemania. Las direcciones URL de servicios de Office 365 para los servicios de Outlook solo estarán disponibles después de que comience la migración de Exchange.

- Los buzones se migran como un proceso back-end. Los usuarios de la organización pueden estar en Microsoft Cloud Deutschland o en la región alemana durante la transición y formar parte de la misma organización de Exchange (en la misma lista global de direcciones).

- Los usuarios de Outlook Web App que tienen acceso al servicio mediante una dirección URL donde no reside su buzón de correo verán un mensaje de autenticación adicional. Por ejemplo, si el buzón del usuario está en los servicios de Office 365 y la conexión de Outlook Web App del usuario usa el extremo heredado, el usuario primero se autenticará en y, a continuación, en `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` . Una vez completada la migración, el usuario puede obtener acceso a la nueva dirección URL ( ), y solo verá la solicitud de inicio de sesión única `https://outlook.office365.com` y esperada. 

## <a name="office-services"></a>Servicios de Office

Los servicios de Office Online son accesibles a través `office.de` de antes y durante la transición. Después de que los buzones de los usuarios se transiciónn a los servicios de Office 365, los usuarios deben empezar a usar direcciones URL de servicios de Office 365. A medida que las cargas de trabajo posteriores migren a los servicios de Office 365, su interfaz desde el portal office.com empezará a funcionar.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Las características back-end de Exchange Online Protection (EOP) se copian en la nueva región de Alemania.
- Los usuarios del Centro de seguridad y cumplimiento de Office 365 deben realizar la transición al uso de direcciones URL `https://protection.office.com` globales, como parte de la migración.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

Los clientes existentes de Skype Empresarial Online pasarán a Microsoft Teams. Para obtener más información, vea [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video se retirará el 1 de marzo de 2021 y Office 365 Video no se admite una vez completada la migración de SharePoint Online a las nuevas regiones del centro de datos alemán. El contenido de Office 365 Video se migrará como parte de la migración de SharePoint Online. Sin embargo, los vídeos de Office 365 Video no se reproducirán en la interfaz de usuario de vídeo de Office 365 después de la migración de SharePoint. Obtenga más información sobre la escala de tiempo de migración en la transición de vídeo de [Office 365 a Microsoft Stream (clásico).](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Paso siguiente

[Comprender las acciones y los impactos de las fases de migración](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Información del programa de migración de Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introducción a su actualización de Microsoft Teams](/microsoftteams/upgrade-start-here)