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
description: 'Resumen: comprenda qué ha cambiado para pasar de Microsoft Cloud Alemania (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688627"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Qué ha cambiado para la migración a los servicios de Office 365 en las nuevas regiones del centro de datos alemán

Las migraciones de inquilinos están diseñadas para tener un efecto mínimo en los administradores y usuarios. Sin embargo, hay consideraciones para cada carga de trabajo. Revise las siguientes secciones para comprender mejor la experiencia de migración de las cargas de trabajo.

A continuación se encuentran las principales diferencias entre los servicios de Microsoft Cloud Deutschland y Office 365 en las nuevas regiones del centro de datos alemán.

| Categoría | Microsoft Cloud Deutschland (Microsoft Cloud Deutschland) | Los servicios de Office 365 en las nuevas regiones del centro de datos alemán. |
|:-------|:-----|:-------|
| Servicios de Microsoft 365 disponibles para suscripción con un solo espacio empresarial de Office 365 | 15 servicios | 29 servicios <br><br> Para obtener más información, vea ¿Cuál es la disponibilidad del servicio entre las distintas ofertas de servicios en la nube [de Office 365?](ms-cloud-germany-transition.md#serv-avail) |
| Características nuevas | No hay disponibles características nuevas | Las nuevas características estarán disponibles de forma coherente con los servicios de Office 365. |
| Administrador de datos | Sí | No |
| Colaboración entre espacios empresariales con los espacios empresariales globales de Office 365 | No | Sí |
| Residencia de datos de clientes | Los datos de los clientes se almacenarán únicamente en centros de datos alemanes. | Microsoft almacenará los siguientes datos de cliente en reposo exclusivamente en Alemania: <ul><li> Contenido del buzón de Exchange Online (cuerpo del correo electrónico, entradas de calendario y contenido de datos adjuntos de correo electrónico) </li><li> Contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio, y archivos cargados en OneDrive para la Empresa </li></ul> |
| Términos aplicables | [Términos de Online Services](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con este [complemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Términos de Online Services](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Lo que no cambia:

- El dominio inicial del inquilino (por ejemplo) con el identificador de inquilino (GUID) y los dominios personalizados `contoso.onmicrosoft.de` persistirán después de la migración. 

- Las solicitudes de autenticación para los recursos que se migran a los servicios de Office 365 las concede el servicio de autenticación de Azure de servicios de Office 365 ( `login.microsoftonline.com` ). Durante la migración, los recursos que permanecen en Office 365 Germany se autentican mediante el servicio existente de Germany Azure ( `login.microsoftonline.de` ).

Consideraciones a tener en cuenta:

- Para las cuentas de dominio administradas, después de copiar el inquilino inicial de Azure Active Directory (Azure AD) se ha completado (que es el primer paso de la migración de Azure AD al servicio de Azure AD de servicios de Office 365), los cambios de contraseña, los cambios de autoservicio de restablecimiento de contraseña (SSPR) y los restablecimientos de contraseña por parte de los administradores deben realizarse desde los portales de servicio de Office 365. Las solicitudes para actualizar contraseñas desde el servicio de Alemania no se realiza correctamente en este momento, porque el inquilino de Azure AD se ha migrado a los servicios de Office 365. Los restablecimientos de contraseñas de dominio federado no se ven afectados, porque se completan en el directorio local.

- Los inicios de sesión de Azure se presentan en el portal donde el usuario intenta obtener acceso. Los registros de auditoría solo están disponibles desde el punto de conexión de servicios de Office 365 después de la transición. Antes de la migración hasta la finalización de la migración, debe guardar los registros de inicio de sesión y auditoría desde el portal de Microsoft Cloud Deutschland.

- Los restablecimientos de contraseña, los cambios de contraseña, el restablecimiento de contraseña por parte de un administrador de organizaciones administradas (que no usan servicios de federación de Active Directory) deben realizarse a través del portal de servicios de Office 365. Se producirá un error en los intentos de los usuarios que acceden a los portales de Microsoft Cloud Deutschland para restablecer contraseñas.

- Las solicitudes de interesados (DSR) del Reglamento general de protección de datos (RGPD) se ejecutan desde el portal de administración de Azure de servicios de Office 365 para solicitudes futuras. Los datos de diagnóstico heredados o que no son de cliente que residen en Microsoft Cloud Deutschland se eliminan en 30 días o antes.

## <a name="subscriptions--licenses"></a>Suscripciones & licencias

- Las suscripciones de Office 365 y Dynamics de Microsoft Cloud Deutschland se trasladan a la región alemana con la reubicación de Azure AD. A continuación, la organización se actualiza para reflejar las nuevas suscripciones de servicios de Office 365. Durante el breve proceso de transferencia de suscripción, se bloquean los cambios en las suscripciones.

- A medida que el inquilino se pasa a los servicios de Office 365, sus suscripciones y licencias específicas de Alemania se estandarizan con las nuevas ofertas de servicios de Office 365. Las suscripciones de servicios de Office 365 correspondientes se compran para las suscripciones transferidas de Alemania. A los usuarios con licencias de Alemania se les asignarán licencias de servicios de Office 365. Una vez completadas, las suscripciones heredadas de Alemania se cancelan y se quitan del inquilino actual de servicios de Office 365.

- Después de la migración de las cargas de trabajo individuales, las funciones adicionales están disponibles a través de los servicios de Office 365 (como Microsoft Planner y Microsoft Flow) debido a las nuevas suscripciones de servicios de Office 365. Si es apropiado para su organización, el inquilino o el administrador de licencias puede deshabilitar nuevos planes de servicio mientras planea la administración de cambios para introducir los nuevos servicios. Para obtener instrucciones sobre cómo deshabilitar los planes de servicio asignados a las licencias de los usuarios, vea Deshabilitar el acceso a los servicios de [Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)al asignar licencias de usuario.

## <a name="exchange-online"></a>Exchange Online

- Las direcciones URL de recursos de Exchange se transición del extremo de Alemania heredado al punto de conexión de servicios de `outlook.office.de` Office 365 `outlook.office365.com` después de la migración. Los usuarios pueden tener acceso a su buzón migrado mediante la dirección URL heredada hasta que se complete la migración. Los clientes deben realizar la transición de usuarios a la nueva dirección URL tan pronto como sea posible después de que comience la migración de Exchange para evitar que afecten a la retirada del entorno de Alemania. Las direcciones URL de servicios de Office 365 para los servicios de Outlook solo están disponibles después de que comience la migración de Exchange.

- Los buzones se migran como un proceso back-end. Los usuarios de su organización pueden estar en Microsoft Cloud Deutschland o en la región alemana durante la transición y forman parte de la misma organización de Exchange (en la misma lista global de direcciones).

- Los usuarios de Outlook Web App que tienen acceso al servicio mediante una dirección URL en la que su buzón no reside verán un mensaje de autenticación adicional. Por ejemplo, si el buzón del usuario está en los servicios de Office 365 y la conexión de Outlook Web App del usuario usa el extremo heredado , el usuario primero se autenticará en y, a continuación, en `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` . Una vez completada la migración, el usuario puede tener acceso a la nueva dirección URL ( ) y solo verá la solicitud de inicio de sesión única `https://outlook.office365.com` y esperada. 

## <a name="office-services"></a>Servicios de Office

Los servicios de Office Online son accesibles `office.de` a través de antes y durante la transición. Una vez que los buzones de los usuarios se han pasado a los servicios de Office 365, los usuarios deben empezar a usar las direcciones URL de servicios de Office 365. A medida que las cargas de trabajo posteriores migren a los servicios de Office 365, su interfaz del portal de office.com empezará a funcionar.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Las características back-end de Exchange Online Protection (EOP) se copian en la nueva región de Alemania.
- Los usuarios del Centro de seguridad y cumplimiento de Office 365 deben realizar la transición al uso de direcciones URL globales, como `https://protection.office.com` parte de la migración.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

Los clientes existentes de Skype Empresarial Online pasarán a Microsoft Teams. Para obtener más información, vea [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 Video se retirará el 1 de marzo de 2021 y Office 365 Video no será compatible una vez completada la migración de SharePoint Online a las nuevas regiones del centro de datos alemán. El contenido de Office 365 Video se migrará como parte de la migración de SharePoint Online. Sin embargo, los vídeos de Office 365 Video no se reproducirán en la interfaz de usuario de vídeo de Office 365 después de la migración de SharePoint. Obtenga más información sobre la escala de tiempo de migración [en Office 365 Video transition to Microsoft Stream (classic) overview](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Paso siguiente

[Comprender las acciones y los impactos de las fases de migración](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)

Pasar por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
