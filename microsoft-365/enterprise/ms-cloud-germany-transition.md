---
title: Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán
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
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Resumen: comprender la migración de Microsoft Cloud Alemania (Microsoft Cloud Deutschland) a los servicios de Office 365 en las nuevas regiones del centro de datos alemán'
ms.openlocfilehash: 18df7c43e21fb186dee56dabc29a67654f0f6882
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923773"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán

> [!NOTE]
> Este artículo solo se aplica a los clientes elegibles de Microsoft Cloud Deutschland.

En agosto de 2018, Microsoft anunció nuestra intención de entregar la nube completa de Microsoft (Azure, Office 365, Dynamics 365 y Power Platform) de nuevas regiones en la nube en Alemania para permitir mejor la transformación digital de nuestros clientes. En agosto de 2019, anunciamos que estamos en proceso de abrir las nuevas regiones en la nube en Alemania. Desde entonces hemos anunciado la disponibilidad de Azure, Office 365, Dynamics 365 y Power Platform.

Las nuevas regiones están diseñadas para satisfacer las necesidades cambiantes de los clientes alemanes con mayor flexibilidad, los servicios en la nube inteligente más recientes y la conectividad completa a nuestra red en la nube de servicios de Microsoft 365, así como a la residencia de datos de clientes en Alemania.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Cómo migrar a las nuevas regiones de centros de datos alemanes

Los clientes existentes de Microsoft Cloud Deutschland ahora pueden empezar a migrar sus clientes de Office 365, Dynamics 365 Customer Engagement y Power Platform. El primer paso consiste en [participar en una migración dirigida por Microsoft](./ms-cloud-germany-migration-opt-in.md) a las nuevas regiones del centro de datos alemán.

Para las organizaciones que optan por el enfoque basado en Microsoft, se espera que las migraciones comiencen a principios de 2021 y se completen antes del 29 de octubre de 2021. Como resultado de la migración, los datos básicos del cliente y las suscripciones se mueven a las nuevas regiones alemanas.

En este artículo se proporciona información general sobre el enfoque basado en Microsoft para la migración, la claridad de las experiencias de usuarios y administradores durante y después de la migración y las acciones que pueden ser necesarias para los clientes en función de las cargas de trabajo que use.

Los siguientes servicios se migrarán como parte del enfoque liderado por Microsoft:

- Azure Active Directory (Azure AD)
- Exchange en línea
- Exchange Online Protection
- SharePoint Online
- OneDrive para la Empresa

- Skype Empresarial Online\*\*
- Grupos de Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Durante la migración de Microsoft Cloud Deutschland a las regiones del centro de datos alemán, los clientes existentes de Skype Empresarial Online pasarán a Microsoft Teams. Para obtener más información, consulte [Introducción a su actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).

\*\*\*Los requisitos previos y el impacto de la migración para estos servicios se describen en el [artículo de Dynamics 365 Customer engagement.](/dynamics365/get-started/migrate-data-german-region)

Office 365 Video se retirará el 1 de marzo de 2021. Si decide migrar su espacio empresarial de Office 365 a las nuevas regiones del centro de datos alemán, Office 365 Video no se admitirá una vez completada la migración de SharePoint Online. Para obtener más información, vea [Escala de tiempo de Microsoft Cloud Deutschland](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="how-is-the-migration-organized"></a>¿Cómo se organiza la migración?

Esta figura muestra las nueve fases de migración a los nuevos centros de datos alemanes.

![Las nueve fases de migración a los nuevos centros de datos de Alemania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Estas fases comienzan cuando [se opta por la migración.](./ms-cloud-germany-migration-opt-in.md) La mayoría de las fases de migración se ejecutan como operaciones de servicio back-end con una interacción mínima del cliente necesaria y se ejecutan una fase tras otra. El inicio de tareas adicionales dirigidas por el cliente y el estado general de migración se comunicarán a través del Centro de mensajes del Centro de administración de Microsoft 365 durante el proceso de migración. Ejemplo de tareas puede incluir actualizaciones dns administradas por el cliente, reconfiguración de la configuración híbrida para clientes híbridos de Exchange o migración de Azure.

La migración no comienza inmediatamente cuando se produce la suscripción. La organización se agrega a la lista de inquilinos que están programados para la migración posterior. Ahora puede comenzar las fases previas al trabajo, ya que son fundamentales para garantizar una migración y un uso correctos al finalizar:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)

Una semana antes del inicio de la migración de inquilino, recibirá un aviso en el servicio del Centro de mensajes como una advertencia final de que todos los requisitos previos deben completarse.

La migración se moverá del inquilino de Azure AD desde el servicio de Azure AD de Alemania soberana a la instancia de servicios de Office 365 de Azure AD en la región de la UE.

La siguiente fase es la migración de las suscripciones&#39;inquilino y las licencias de usuario de productos específicos de Alemania a productos globales.

Una vez completados todos los pasos, incluida la migración de Azure del cliente, el inquilino finaliza en el servicio de servicios de Office 365 y la migración se marca completa. En este momento, se le proporciona la actualización final del Centro de mensajes. El inquilino es ahora una organización totalmente global de Office 365.

Se le notificará el progreso de la migración con las publicaciones del Centro de mensajes. Las publicaciones se producirán en hitos específicos y proporcionarán instrucciones sobre el progreso de un paso, así como información importante para que los clientes actúen en función de los requisitos del proceso. Las notificaciones del centro de mensajes se proporcionan en los siguientes hitos:

- Inicio de la migración (5 días laborables antes de que comience la migración de Azure AD)
- Migración de Azure AD completada
- Suscripción y migración de licencias completada
- Migración de SharePoint completada
- Migración de Exchange completada
- Skype Empresarial completado
- Dynamics complete
- Power BI completado
- Final cutover of services is complete

## <a name="moving-to-the-new-german-datacenter-regions"></a>Mover a las nuevas regiones del centro de datos alemán

Los clientes existentes de Microsoft Cloud Deutschland ahora pueden comenzar a migrar sus servicios de Office 365, Dynamics 365 Customer Engagement y Power Platform. El primer paso consiste en [participar en una migración dirigida por Microsoft](./ms-cloud-germany-migration-opt-in.md) a las nuevas regiones del centro de datos alemán. Al renovar la suscripción, opta automáticamente por una migración asistida por Microsoft. Microsoft notificará a los administradores de inquilinos del cliente con correo electrónico y en el Centro de mensajes del Centro de administración de Microsoft 365 cuando esto haya ocurrido. Sin embargo, si prefiere iniciar el [](./ms-cloud-germany-migration-opt-in.md) proceso ahora, puede participar directamente en el Centro de administración de Microsoft 365 hoy mismo. Se espera que las migraciones comiencen a principios de 2021 y que se completen el 29 de octubre de 2021. 

Como resultado de la migración, los datos principales del cliente y las suscripciones se mueven a las nuevas regiones del centro de datos alemán.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Cómo preparar la migración a los servicios de Office 365 en las nuevas regiones del centro de datos alemán.

El primer paso es notificar a Microsoft para que tenga permiso para migrar la suscripción y los datos de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán. Consulte el proceso [de suscripción](./ms-cloud-germany-migration-opt-in.md) para obtener instrucciones y tenga en cuenta que:

- Todos los clientes que migran deben comprobar la conectividad a las direcciones URL y direcciones IP de [Office 365 Services Office 365,](urls-and-ip-address-ranges.md)que incluyen las nuevas regiones del centro de datos alemán. La inacción puede provocar errores en el servicio y en el cliente.
- Revise la lista de [actividades previas al](ms-cloud-germany-transition-add-pre-work.md) trabajo para asegurarse de que su organización está informada y preparada para los cambios.
- Debe revisar la descripción del servicio de plataforma de Office 365 para comprender qué características y servicios estarán disponibles para su organización después de la migración a la región alemana.
- Las suscripciones de prueba no se migrarán y bloquearán la migración de todas las suscripciones de pago. Debe cancelar las pruebas o convertir a suscripciones de pago antes de que comience la migración.

## <a name="where-do-i-go-from-here"></a>¿A dónde voy desde aquí?

Revise la siguiente sección De preguntas más frecuentes.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="is-migration-required"></a>¿Es la migración obligatoria?

Microsoft ofrece la migración de inquilinos de Office 365 de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán sin costo adicional. Aunque recomendamos encarecidamente que opte por migrar a las nuevas regiones de centros de datos alemanes, seguiremos proporcionando las actualizaciones de seguridad necesarias para la región de Microsoft Cloud Deutschland.

Servicios de Office 365 en las nuevas regiones del centro de datos alemán:

- Ofertas competitivas para [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) y [Power BI](https://powerbi.microsoft.com/pricing/).
- Están conectados a la red global de Microsoft&#39;, que ofrece cientos de sitios perimetrales de red, ubicaciones de emparejamiento y puntos de salida para ofrecer una experiencia de usuario sólida en cualquier parte del mundo.
- Asistencia para que pueda cumplir los requisitos de residencia de datos de clientes locales en Alemania.
- Ofrezca nuestra oferta de nube global con las últimas versiones de nuestros servicios y nuevas capacidades, incluidas Microsoft Teams y Multi-Geo en Office 365. Comparar productos por región para [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) y [Dynamics 365](/dynamics365/get-started/availability).
- Funcionalidad completa, una seguridad de nivel empresarial y una amplia variedad de características para ayudar a los clientes a cumplir los requisitos de cumplimiento normativo.
- Acceso a través de los contratos de servicios en línea existentes.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>¿Cuál es la disponibilidad del servicio entre las diferentes ofertas de servicios en la nube de Office 365?
<h2 id="serv-avail"></h2>

Los siguientes 15 servicios están disponibles en la oferta de servicios en la nube de Microsoft Cloud Deutschland. No vamos a agregar nuevos servicios a Microsoft Cloud Deutschland.

1. Exchange Online
2. Caja de seguridad del cliente (Exchange Online)
3. Grupos (grupos modernos)
4. Perfil de Delve
5. Exchange Online Protection
6. Defender para Office 365
7. eDiscovery avanzado
8. Control avanzado de datos
9. SharePoint Online
10. Caja de seguridad del cliente (SharePoint Online)
11. OneDrive para la Empresa
12. Skype Empresarial Online
13. Word Online, Excel Online, PowerPoint, OneNote y Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Actualmente hay 39 servicios disponibles como parte de los servicios de Office 365 en las nuevas regiones del centro de datos alemán. Las nuevas características y servicios estarán disponibles consecuentemente con los servicios globales de Office 365 de manera continua.

1. Exchange Online
2. Caja de seguridad del cliente para Exchange Online
3. Grupos de Microsoft 365
4. Perfil de Delve
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Defender para Office 365
9. eDiscovery avanzado
10. Administración de seguridad avanzada
11. Protección de información para Office 365 
12. Control avanzado de datos
13. SharePoint Online
14. Caja de seguridad del cliente para SharePoint Online
15. OneDrive para la Empresa
16. Microsoft Stream
17. Skype Empresarial (migrará a Microsoft Teams durante la migración)
18. PBX en la nube
19. Conferencias RTC
20. Llamadas RTC
21. Microsoft Teams
22. Informes de uso e informes de administración
23. Office para la web
24. Planner
25. Sway
26. Aplicaciones de Microsoft 365
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune y Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate para Office 365
32. Agentes virtuales de Power para Office 365
33. PowerApps para Office 365
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Listas

### <a name="when-will-migration-happen"></a>¿Cuándo se producirá la migración?

**Azure**

Si solo es cliente de Azure, puede empezar a migrar [los recursos](/azure/germany/germany-migration-main) de Azure a otra región hoy mismo. 

Si tiene Azure con Office 365, Dynamics 365 o Power BI, debe seguir el proceso de migración para garantizar la migración correcta de AzureAD antes de comenzar la migración autodescrída de Azure. Debe completar la migración de Azure antes del cierre del servicio para mantener las cargas de trabajo de Azure con azureAD y la organización de Office 365.

**Office 365**

[Participe](./ms-cloud-germany-migration-opt-in.md) hoy en la migración liderada por Microsoft. Cuando estemos listos para iniciar la migración, le informaremos a través del Centro de mensajes del Centro de administración de Microsoft 365.

**Dynamics 365 y Power BI**

Opt-in to the Microsoft-driven migration for [Dynamics 365 Customer Engagement](/dynamics365/get-started/migrate-data-german-region) and Power [BI](/power-bi/admin/service-admin-migrate-data-germany) today. Cuando esté listo para empezar la migración, le informaremos en el Centro de mensajes del Centro de administración de Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>¿Cambiará el precio de los servicios de Office 365 que use?

Sí. Los precios en las&#39;de nube global de Microsoft (incluidas las nuevas regiones del centro de datos) suelen ser más bajos.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Durante la migración de suscripción, ¿qué SKU y licencias se aplicarán a mi organización y a los usuarios?

Durante la migración de Microsoft Cloud Deutschland a los servicios de Office 365, las SKU específicas del servicio de Alemania se reemplazan por versiones globales de la misma SKU o similar. En la mayoría de los casos, la SKU de los servicios de Office 365 es la misma, pero hay pocos reemplazos en los que la SKU en Alemania ya no está disponible en los servicios de Office 365. Si desea actualizar la SKU asignada a su organización una vez completada la migración, póngase en contacto con el vendedor para agregar o modificar los servicios asignados.

| Microsoft Cloud Deutschland: SKU de producto (DE) | Microsoft Cloud Global: SKU de producto (WW) |
| --- | --- |
| Caja de seguridad \_ de cliente DE (LOCKBOX \_ DE) | Caja de seguridad del cliente (LOCKBOX) |
| Dynamics 365 Enterprise Edition: De almacenamiento de base de datos \_ adicional (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition: almacenamiento de bases de datos adicional (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition: instancia no de producción \_ adicional DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition: instancia adicional que no es de producción (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| Servicios ECAL (EOA, EOP, DLP) \_ DE (ECAL \_ SERVICES \_ DE) | Servicios ECAL (EOA, EOP, DLP) (SERVICIOS \_ ECAL) |
| Enterprise Mobility + Security E3 \_ DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (Plan 1) \_ DE (EXCHANGESTANDARD \_ DE) | Exchange Online (plan 1) (EXCHANGESTANDARD) |
| Exchange Online (Plan 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (plan 2) (EXCHANGEENTERPRISE) |
| Archivado de Exchange Online para Exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Archivado de Exchange Online exchange online (COMPLEMENTO \_ EXCHANGEARCHIVE) |
| Archivado de Exchange Online para Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | Archivado de Exchange Online para Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| Quiosco de Exchange Online DE \_ (EXCHANGEDESKLESS \_ DE) | Quiosco de Exchange Online (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ EMPRESA \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ EMPRESA \_ PREMIUM) |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online (CRMINSTANCE) |
| Office 365 A1 para \_ profesorES DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 para profesores (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 para estudiantes \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 para estudiantes (STANDARDWOFFPACK \_ STUDENT) |
| De cumplimiento avanzado de Office 365 \_ (EQUIVIO \_ ANALYTICS \_ DE) | Cumplimiento de Microsoft 365 E5 (CUMPLIMIENTO \_ DE PROTECCIÓN DE LA \_ INFORMACIÓN) |
|Microsoft Defender para Office 365 (Plan 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender para Office 365 (Plan 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Empresa Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Empresa Premium \_ DE (O365 \_ EMPRESA PREMIUM \_ \_ DE) | Microsoft 365 Business Standard (O365 \_ EMPRESA \_ PREMIUM) |
| Office 365 Empresa \_ DE (O365 \_ BUSINESS \_ DE) | Aplicaciones de Microsoft 365 para empresas (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 sin ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 sin ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Almacenamiento adicional de archivos de Office 365 (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus para Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus para profesores (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus para estudiantes \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus para estudiantes (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive para la Empresa (Plan 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | OneDrive para la Empresa (Plan 1) (WACONEDRIVESTANDARD) |
| OneDrive para la Empresa (Plan 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive para la Empresa (Plan 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro para \_ profesorES DE (POWER \_ BI PRO \_ \_ FACULTY \_ DE) | Power BI Pro para profesores (POWER \_ BI \_ PRO \_ FACULTY) |
| Power BI Pro \_ DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| Plan de proyecto 3 \_ DE (PROJECTPROFESSIONAL \_ DE) | Plan 3 de Project (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (Plan 1) \_ DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (plan 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (Plan 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (plan 2) (SHAREPOINTENTERPRISE) |
| Skype Empresarial Online (Plan 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype Empresarial Online (Plan 1) \_ DE (MCOIMP \_ DE) | Skype Empresarial Online (Plan 1) (MCOIMP) |
| Skype Empresarial Online (Plan 2) \_ DE (MCOSTANDARD \_ DE) | Skype Empresarial Online (Plan 2) (MCOSTANDARD) |
| Skype Empresarial Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype Empresarial Más CAL (MCOPLUSCAL) |
| Plan 1 de Visio Online para \_ profesores DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Plan 1 de Visio Online para profesores (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Plan 1 de Visio Online (VISIOONLINE \_ PLAN1) |
| Plan 2 de Visio Online para \_ profesorES DE (VISIOCLIENT \_ FACULTY \_ DE) | Plan 2 de Visio Online para profesores (VISIOCLIENT \_ FACULTY) |
| Visio Online Plan 2 \_ DE (VISIOCLIENT \_ DE) | Plan 2 de Visio Online (VISIOCLIENT) |
| Visio Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Plan 1 de Visio (VISIOONLINE \_ PLAN1) |
| Visio Plan 2 \_ DE (VISIOCLIENT \_ DE) | Plan 2 de Visio (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>¿Cómo puedo obtener ayuda de Microsoft para migrar a una nueva región o hacer preguntas a soporte técnico?

Si tiene preguntas, puede ponerse en contacto con nosotros o con su partner:

- Para Azure, puede enviar [nuevas solicitudes de soporte técnico](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) en Azure Portal.
- Para Office 365, puede enviar preguntas mediante el vínculo ¿Necesita ayuda? del Centro de administración de &quot; &quot; Microsoft [365](https://portal.office.de/).
- Si es cliente de Dynamics 365 Customer Engagement y Power BI y también tiene Office 365, puede enviar preguntas mediante el vínculo ¿Necesita ayuda? del Centro de administración de &quot; &quot; Microsoft [365](https://portal.office.de/). Las opciones de soporte de Dynamics 365 Customer Engagement se encuentran [aquí](/dynamics365/get-started/support/). Las opciones de soporte técnico de Power BI se encuentran [aquí](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>Mi cliente ya tiene un inquilino M365 en la nube global de Microsoft además de un inquilino de Microsoft Cloud Deutschland. ¿Estos dos inquilinos se pueden combinar en uno como parte de la migración?

No, no hay ninguna funcionalidad de combinación de inquilinos. Los inquilinos seguirán siendo independientes y únicos, ya que cada inquilino tiene su propio espacio de nombres y su identificador único. Microsoft migrará un inquilino de Microsoft Cloud Deutschland a la nube global si lo desea o, de lo contrario, el cliente puede cancelarla y abandonarla.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>¿Qué acciones deben realizar la mayoría de los usuarios finales como parte de la migración?
La migración está diseñada para tener un impacto mínimo para los usuarios finales o los clientes.
- Asegúrese de que las aplicaciones de Office ejecutan las versiones más recientes disponibles. 
- Los clientes que usan Skype Empresarial pasarán a Teams como parte de la migración y es posible que deba [descargar e instalar Teams](/deployoffice/teams-install) en dispositivos.
- Es posible que los usuarios finales deba cerrar sesión en las aplicaciones de Office y volver a iniciar sesión una vez completada la migración. 
- Los clientes que ejecutan el cliente de Sincronización de OneDrive deben cerrar sesión de su estación de trabajo e iniciar sesión de nuevo para permitir que el cliente de Sincronización de OneDrive inicie sesión en el servicio global de Azure Active Directory.
- Tenga en cuenta las nuevas direcciones URL globales una vez completada la migración, en particular Outlook Web Access (ejemplo: use outlook.office365.com). Los clientes de SharePoint Online seguirán conectándose correctamente al espacio de nombres MCD mediante la dirección URL existente (ejemplo: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>¿Qué clientes se ven afectados por la migración de Azure Active Directory? 

Todos los clientes de Office365 dependen de Azure Active Directory para autenticar y almacenar los componentes de servicio críticos necesarios para el funcionamiento de los servicios hospedados por Microsoft. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>¿Cuáles son los impactos de la migración de Azure Active Directory?

La migración inicial de Azure Active Directory en la fase inicial no tiene ningún impacto en la experiencia del cliente. Después de la fase de migración final, todos los servicios del inquilino del cliente están totalmente en el servicio global. Después de esta fase final, es posible que el servicio Azure Active Directory de Microsoft Cloud Deutschland ya no acepte solicitudes de autorización ni proporcione tokens de acceso a los servicios de Office.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>¿Qué significa garantizar la conectividad de red con direcciones IP y direcciones URL de servicios de [Office 365?](./urls-and-ip-address-ranges.md)

En este artículo se describen las direcciones URL y direcciones IP necesarias para el correcto funcionamiento del servicio global con el fin de garantizar una buena experiencia del cliente. En casos relativamente raros, algunos clientes intentan configurar la seguridad perimetral de la red de tal manera que se minimicen los flujos de tráfico y se haya restringido el acceso a los servicios a aquellos solo como parte de los intervalos IP de servicio de Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>¿Cómo puedo administrar los cambios dns para Exchange Online para que el correo siga fluyendo?

Los intervalos IP administrados por Microsoft y las zonas DNS se transiciónn durante y como parte de la migración al servicio global. 

Las zonas DNS administradas por el cliente, como los registros MX de dominio personalizados, son responsabilidad del cliente, sin embargo, para simplificar esta migración, el registro MX administrado por el cliente apunta a un extremo de servicio de Office 365 en la zona office.de y Microsoft administra automáticamente la migración de este extremo de servicio.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>¿Cómo puedo administrar los cambios dns para Skype Empresarial? 
 
Todos los clientes de Skype Empresarial pasarán a Microsoft Teams. La transición de las zonas DNS de Skype del cliente no es necesaria en la migración a Teams. Los clientes podrán iniciar sesión en Teams inmediatamente con todas las funciones después de la migración.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>¿Funcionará Outlook para iOS y Android después de la migración? 

Sí. La recomendación de Microsoft es que todos los clientes ejecuten las últimas versiones disponibles de clientes de Office, incluidos los clientes de Outlook para iOS y Android. Una vez completada la migración al servicio global de Office 365, todos los clientes de Office tendrán que cerrar sesión y volver a iniciar sesión para obtener un nuevo token de acceso de Azure Active Directory del servicio global. 



## <a name="next-step"></a>Paso siguiente

[Participar en la migración](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Más información

Introducción:

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