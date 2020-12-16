---
title: Qué ha cambiado para la migración a Office 365 Services en las nuevas regiones del centro de datos en alemán
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
description: 'Resumen: comprenda qué ha cambiado para cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.'
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688627"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Qué ha cambiado para la migración a Office 365 Services en las nuevas regiones del centro de datos en alemán

Las migraciones de inquilinos están diseñadas para tener un efecto mínimo en los administradores y los usuarios. Sin embargo, hay consideraciones para cada carga de trabajo. Revise las siguientes secciones para conocer mejor la experiencia de migración de las cargas de trabajo.

A continuación se enumeran las principales diferencias entre los servicios de Microsoft Cloud Alemania y Office 365 en las nuevas regiones del centro de administración de Office en alemán.

| Categoría | Microsoft Cloud Alemania (Microsoft Cloud Alemania) | Los servicios de Office 365 en las nuevas regiones del centro de datos alemán. |
|:-------|:-----|:-------|
| Servicios de Microsoft 365 disponibles para suscripción con un solo espacio empresarial de Office 365 | 15 servicios | 29 servicios <br><br> Para obtener más información, consulte [¿cuál es la disponibilidad del servicio entre las distintas ofertas del servicio de nube de Office 365?](ms-cloud-germany-transition.md#serv-avail). |
| Características nuevas | No hay disponibles características nuevas | Las nuevas características estarán disponibles de forma coherente con los servicios de Office 365. |
| Administrador de datos | Sí | No |
| Colaboración entre espacios empresariales con los espacios empresariales globales de Office 365 | No | Sí |
| Residencia de datos de clientes | Los datos de los clientes se almacenarán exclusivamente en los centros de datos alemanes. | Microsoft almacenará los siguientes datos de cliente en reposo exclusivamente en Alemania: <ul><li> Contenido del buzón de correo de Exchange Online (cuerpo del correo electrónico, entradas del calendario y contenido de los datos adjuntos de correo electrónico) </li><li> El contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio y los archivos cargados en OneDrive para la empresa </li></ul> |
| Términos aplicables | [Términos de servicios en línea](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) con este [suplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Términos de Online Services](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

Qué no está cambiando:

- El dominio inicial del inquilino (como `contoso.onmicrosoft.de` ) con el identificador de inquilino (GUID) y los dominios personalizados se conservarán después de la migración. 

- Las solicitudes de autenticación para los recursos que se migran a los servicios de Office 365 se conceden mediante el servicio de autenticación de Azure de servicios de Office 365 ( `login.microsoftonline.com` ). Durante la migración, los recursos que permanecen en Office 365 Germany se autentican mediante el servicio de Microsoft Alemania existente ( `login.microsoftonline.de` ).

Consideraciones a tener en cuenta:

- Para las cuentas de dominio administrado, tras completar la copia del inquilino inicial de Azure Active Directory (Azure AD) (que es el primer paso de la migración de Azure AD al servicio Office 365 Services Azure AD), los cambios de contraseña, los cambios de restablecimiento de contraseña de autoservicio (SSPR) y los administradores de contraseñas se deben realizar desde los portales del servicio Office 365. Las solicitudes de actualización de contraseñas del servicio Alemania no se realizarán correctamente en este momento, ya que el inquilino de Azure AD se ha migrado a los servicios de Office 365. Los restablecimientos de contraseñas de dominio federado no se ven afectados porque se completan en el directorio local.

- Los inicios de sesión de Azure se presentan en el portal donde el usuario intenta tener acceso. Los registros de auditoría solo están disponibles desde el punto de conexión de servicios de Office 365 después de la transición. Antes de realizar la migración a la finalización de la migración, debe guardar los registros de auditoría y de inicio de sesión del portal de Microsoft Cloud Alemania.

- Los restablecimientos de contraseñas, los cambios de contraseña y el restablecimiento de contraseña por parte de un administrador de organizaciones administradas (que no usan los servicios de Federación de Active Directory) deben realizarse a través del portal de servicios de Office 365. Se producirá un error en los intentos de los usuarios que accedan a Microsoft Cloud Alemania portales para restablecer contraseñas.

- Reglamento General de protección de datos (RGPD) las solicitudes de interesados de datos (interesado) se ejecutan desde el portal de administración de Azure de servicios de Office 365 para solicitudes futuras. Los datos de diagnóstico heredados o no del cliente que residan en la nube de Microsoft Alemania se eliminan en o antes de 30 días.

## <a name="subscriptions--licenses"></a>Suscripciones & licencias

- Las suscripciones de Office 365 y Dynamics de la nube de Microsoft Alemania pasan a la región alemana con la reubicación de Azure AD. A continuación, la organización se actualiza para reflejar las nuevas suscripciones a los servicios de Office 365. Durante el proceso breve de transferencia de suscripción, los cambios en las suscripciones se bloquean.

- A medida que el inquilino se pasa a los servicios de Office 365, sus suscripciones y licencias específicas de Alemania están estandarizadas con las nuevas ofertas de servicios de Office 365. Se compran las suscripciones de Office 365 Services correspondientes para las suscripciones de Alemania transferidas. A los usuarios que tienen licencias de Alemania se les asignan licencias de servicios de Office 365. Una vez finalizadas, las suscripciones de Alemania heredadas se cancelan y se quitan del inquilino actual de Office 365 Services.

- Después de la migración de las cargas de trabajo individuales, la funcionalidad adicional está disponible a través de los servicios de Office 365 (como Microsoft Planner y Microsoft Flow) debido a las nuevas suscripciones de Office 365 Services. Si es adecuado para su organización, el administrador de inquilinos o licencias puede deshabilitar los nuevos planes de servicio a medida que planea que la administración de cambios presente los nuevos servicios. Para obtener instrucciones sobre cómo deshabilitar los planes de servicio asignados a las licencias de los usuarios, vea [deshabilitar el acceso a los servicios de Microsoft 365 mientras se asignan licencias de usuario](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange en línea

- Las direcciones URL de recursos de Exchange pasan desde el extremo de Alemania heredado `outlook.office.de` hasta el punto de conexión de servicios de Office 365 `outlook.office365.com` después de la migración. Los usuarios pueden tener acceso a su buzón migrado usando la dirección URL heredada hasta que finalice la migración. Los clientes deben realizar la transición de los usuarios a la nueva dirección URL lo antes posible después de comenzar la migración de Exchange para evitar que afecte al retiro del entorno de Alemania. Las direcciones URL de servicios de Office 365 para servicios de Outlook están disponibles solo después de iniciar la migración de Exchange.

- Los buzones se migran como un proceso de back-end. Los usuarios de la organización pueden estar en Microsoft Cloud Alemania o en la región alemana durante la transición y forman parte de la misma organización de Exchange (en la misma lista global de direcciones).

- Los usuarios de Outlook Web App que tienen acceso al servicio con una dirección URL en la que no reside el buzón verán un mensaje de autenticación adicional. Por ejemplo, si el buzón del usuario se encuentra en los servicios de Office 365 y la conexión de Outlook Web App del usuario usa el extremo heredado `outlook.office.de` , el usuario se autenticará primero `login.microsoftonline.de` y, a continuación, en `login.microsoftonline.com` . Una vez completada la migración, el usuario puede acceder a la nueva dirección URL ( `https://outlook.office365.com` ) y verá solo la solicitud de inicio de sesión esperada única. 

## <a name="office-services"></a>Servicios de Office

Se puede obtener acceso a los servicios de Office online a través de `office.de` antes y durante la transición. Después de migrar los buzones de los usuarios a los servicios de Office 365, los usuarios deben empezar a usar las direcciones URL de servicios de Office 365. A medida que las cargas de trabajo posteriores migren a los servicios de Office 365, la interfaz del portal de office.com empezará a funcionar.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- Las características back-end de Exchange Online Protection (EOP) se copian en la nueva región de Alemania.
- Los usuarios del centro de seguridad y cumplimiento de Office 365 necesitan realizar la transición al uso de direcciones URL globales, `https://protection.office.com` como parte de la migración.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

Los clientes existentes de Skype Empresarial Online pasarán a Microsoft Teams. Para obtener más información, consulte [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Office 365 Video

Office 365 vídeo se está retirando el 1 de marzo de 2021 y no se admitirá el vídeo de Office 365 después de la migración de SharePoint Online a las nuevas regiones del centro de proceso de seguridad en alemán. El contenido del vídeo de Office 365 se migrará como parte de la migración de SharePoint Online. Sin embargo, los vídeos en Office 365 vídeo no se reproducen en la interfaz de usuario de vídeo de Office 365 después de la migración de SharePoint. Obtenga más información sobre la escala de tiempo de migración en [Office 365 video Transition to Microsoft Stream (Classic) Overview](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Paso siguiente

[Descripción de las acciones y los efectos de las fases de migración](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)

Desplazarse por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
