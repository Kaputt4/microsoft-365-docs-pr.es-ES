---
title: Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: 23ccc30bab5d1045e4716cd637899e20362fc597
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846945"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán

> [!NOTE]
> Este artículo solo se aplica a los clientes de Alemania en la nube de Microsoft elegida.

En agosto de 2018, Microsoft anunció nuestra intención de ofrecer la nube completa de Microsoft (Azure, Office 365, Dynamics 365 y Power Platform) desde nuevas regiones de la nube en Alemania para permitir una mejor transformación digital de nuestros clientes. En agosto de 2019, anunciamos que estamos en proceso de abrir las nuevas regiones en la nube en Alemania. Desde entonces, hemos anunciado la disponibilidad de Azure, Office 365, Dynamics 365 y la plataforma de energía.

Las nuevas regiones están diseñadas para satisfacer las necesidades en constante evolución de los clientes alemanes con una mayor flexibilidad, los últimos servicios en la nube inteligente y la conectividad completa con nuestra red en la nube de servicios de Microsoft 365, así como la residencia de datos de clientes en Alemania.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Cómo migrar a las nuevas regiones alemanas

Los clientes de Microsoft Cloud Alemania ahora pueden empezar a migrar su compromiso con el cliente de Office 365, Dynamics 365 y la plataforma de energía. El primer paso consiste en [participar en una migración dirigida por Microsoft](https://aka.ms/office365germanymoveoptin) a las nuevas regiones del centro de datos alemán.

Para las organizaciones que optan por el enfoque dirigido por Microsoft, se espera que las migraciones comiencen a principios de 2021 y que se completarán antes del 29 de octubre de 2021. Como resultado de la migración, los datos básicos del cliente y las suscripciones se mueven a las nuevas regiones alemanas.

En este artículo se proporciona información general sobre el enfoque dirigido por Microsoft para la migración, la claridad sobre las experiencias de los usuarios y los administradores durante y después de la migración, y las acciones que pueden ser necesarias para los clientes en función de las cargas de trabajo que use.

Los siguientes servicios se migrarán como parte del enfoque liderado por Microsoft:

- Azure Active Directory (Azure AD)
- Exchange en línea
- Exchange Online Protection
- SharePoint Online
- OneDrive para la Empresa

- Skype empresarial online\*\*
- Grupos de Office 365
- Dynamics 365/plataforma de alimentación\*\*\*

\*\*Durante la migración desde la nube de Microsoft Alemania a las regiones del centro de administración de la organización alemana, los clientes de Skype empresarial online existentes cambiarán a Microsoft Teams. Para obtener más información, consulte [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

\*\*\*Los requisitos previos y el impacto de la migración para estos servicios se describen en el artículo [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin) .

Office 365 Video se retirará el 1 de marzo de 2021. Si decide migrar su espacio empresarial de Office 365 a las nuevas regiones del centro de datos alemán, Office 365 Video no se admitirá una vez completada la migración de SharePoint Online. Haga clic [aquí](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) para obtener más información.

## <a name="how-is-the-migration-organized"></a>¿Cómo se organiza la migración?

Esta figura representa los diversos componentes de Office 365 y Dynamics 365 en la migración a los nuevos centros de recursos alemanes.

![Componentes de Office 365 y Dynamics 365 en la migración a los nuevos centros de recursos de Alemania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

La migración se ejecuta en fases que se inician al [participar en la migración](https://aka.ms/office365germanymoveoptin). La mayoría de las fases de migración se ejecutan como operaciones de servicio back-end con una interacción mínima del cliente necesaria y se ejecutan una fase después de la otra. El inicio de las tareas dirigidas a clientes adicionales y el estado general de la migración se comunicarán a través del centro de mensajes del centro de administración de Microsoft 365 durante el proceso de migración. Un ejemplo de tareas pueden incluir actualizaciones de DNS administradas por el cliente, reconfiguración de la configuración híbrida para clientes híbridos de Exchange o migración de Azure.

La migración no comienza inmediatamente cuando se produce la suscripción. La organización se agrega a la lista de inquilinos programados para la migración posterior. Puede comenzar las fases previas al trabajo ahora, ya que son esenciales para garantizar una migración y un uso correctos tras la finalización.

Una semana antes del inicio de la migración de inquilino, recibirá un aviso en el servicio de centro de mensajes como una advertencia final de que deben completarse todos los requisitos previos.

La migración se moverá del espacio empresarial de Azure ad desde el servicio de Azure AD soberano de Alemania a la instancia de servicios de Office 365 de Azure AD en la región de la UE.

La siguiente fase es la migración del espacio empresarial&#39;las suscripciones y licencias de usuario de productos específicos de Alemania.

Una vez completados todos los pasos, incluida la migración de clientes de Azure, el inquilino se finaliza en el servicio de Office 365 Services y la migración se marca como completado. En este momento, se le proporcionará la actualización final del centro de mensajes. El inquilino ahora no es una organización de Office 365 completamente global.

Se le notificará el progreso de la migración con las publicaciones del centro de mensajes. Las publicaciones se producirán en hitos específicos y proporcionarán instrucciones sobre el progreso de un paso, así como información importante para que los clientes actúen en función de los requisitos del proceso. Las notificaciones del centro de mensajes se proporcionan en los siguientes hitos:

- Inicio de la migración (5 días laborables antes de que comience la migración de Azure AD)
- Migración de Azure AD completada
- Migración de suscripción y licencias completada
- Migración de SharePoint completada
- Migración de Exchange completada
- Skype empresarial completado
- Total de dinámicas
- Power BI completada
- Se completó la última transferencia de servicios

## <a name="moving-to-the-new-german-regions"></a>Pasar a las nuevas regiones alemanas

Los clientes existentes de Microsoft Cloud Germany (Microsoft Cloud Alemania) ahora pueden empezar a migrar su compromiso con el cliente de Office 365, Dynamics 365 y la plataforma de energía. El primer paso consiste en [participar en una migración dirigida por Microsoft](https://aka.ms/office365germanymoveoptin) a las nuevas regiones del centro de datos alemán. Al renovar la suscripción, puede optar automáticamente a una migración asistida por Microsoft. Microsoft notificará a los administradores de inquilinos de cliente con el correo electrónico y en el centro de mensajes del centro de administración de Microsoft 365 cuando esto ha sucedido. Sin embargo, si prefiere iniciar el proceso ahora, puede [participar](https://aka.ms/office365germanymoveoptin) directamente en el centro de administración de Microsoft 365 en la actualidad. Se espera que las migraciones comiencen a principios de 2021 y que se completarán antes del 29 de octubre de 2021. 

Como resultado de la migración, los datos básicos del cliente y las suscripciones se mueven a las nuevas regiones alemanas.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Cómo preparar la migración a los servicios de Office 365 en las nuevas regiones del centro de datos alemán.

El primer paso es notificar a Microsoft para que tenga su permiso para migrar la suscripción y los datos de Alemania de Microsoft Cloud a Office 365 Services en las nuevas regiones del centro de datos en alemán. Para obtener instrucciones, consulte el [proceso de suscripción](https://aka.ms/office365germanymoveoptin) y tenga en cuenta lo siguiente:

- Todos los clientes de migración necesitan comprobar la conectividad a las [direcciones IP y URL](urls-and-ip-address-ranges.md)de Office 365 Services Office 365, que incluyen las nuevas regiones del centro de recursos alemanes. La inacción puede dar lugar a un error de servicio o de cliente.
- Debe revisar la descripción del servicio de la plataforma de Office 365 para comprender las características y servicios que estarán disponibles para su organización, siguiendo la migración a la región alemana.
- No se migrarán las suscripciones de prueba y se bloqueará la migración de todas las suscripciones pagadas. Debe cancelar cualquier prueba o convertir a suscripciones de pago antes de que se inicie la migración.

## <a name="where-do-i-go-from-here"></a>¿A dónde ir desde aquí?

Revise la siguiente sección de preguntas más frecuentes.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="is-migration-required"></a>¿Es la migración obligatoria?

Microsoft ofrece la migración de inquilinos de Office 365 desde la nube de Alemania a los servicios de 365 de Microsoft en las nuevas regiones del centro de administración de Office sin costo adicional. Aunque le recomendamos encarecidamente que opte por migrar a las nuevas regiones del centro de administración de la seguridad alemana, seguiremos proporcionando las actualizaciones de seguridad necesarias para la región de Microsoft Cloud Alemania.

Servicios de Office 365 en las nuevas regiones del centro de recursos alemanes:

- Ofertas competitivas para [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) y [Power BI](https://powerbi.microsoft.com/pricing/).
- Están conectados a la red global de Microsoft&#39;s, que ofrecen cientos de sitios perimetrales de red, ubicaciones de emparejamiento y puntos de salida para ofrecer una experiencia de usuario sólida en cualquier lugar del mundo.
- Asistencia para que pueda cumplir los requisitos de residencia de datos de clientes locales en Alemania.
- Ofrezca nuestra oferta de nube global completa con las últimas versiones de nuestros servicios y nuevas funciones, como Microsoft Teams y multi-geo en Office 365. Comparar productos por región para [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) y [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Funcionalidad completa, una seguridad de nivel empresarial y una amplia variedad de características para ayudar a los clientes a cumplir los requisitos de cumplimiento normativo.
- Acceso a través de los contratos de servicios en línea existentes.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>¿Cuál es la disponibilidad del servicio entre las diferentes ofertas de servicios en la nube de Office 365?

Los siguientes 15 servicios están disponibles en la oferta de servicios en la nube de Microsoft Cloud Alemania. No estamos agregando nuevos servicios a Microsoft Cloud Alemania.

1. Exchange Online
2. Caja de seguridad del cliente (Exchange Online)
3. Grupos (grupos modernos)
4. Perfil de Delve
5. Exchange Online Protection
6. Microsoft Defender para Office 365
7. eDiscovery avanzado
8. Control avanzado de datos
9. SharePoint Online
10. Caja de seguridad del cliente (SharePoint Online)
11. OneDrive para la Empresa
12. Skype Empresarial Online
13. Word Online, Excel Online, PowerPoint, OneNote y Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Actualmente, hay 29 servicios disponibles como parte de los servicios de Office 365 en las nuevas regiones del centro de datos alemán. Las nuevas características y servicios estarán disponibles consecuentemente con los servicios globales de Office 365 de manera continua.

1. Exchange Online
2. Caja de seguridad del cliente de Exchange Online
3. Grupos de Microsoft 365
4. Perfil de Delve
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Microsoft Defender para Office 365
9. eDiscovery avanzado
10. Administración de seguridad avanzada
11. Information Rights Management
12. Control avanzado de datos
13. SharePoint Online
14. Caja de seguridad del cliente para SharePoint Online
15. OneDrive para la Empresa
16. Microsoft Stream
17. Skype empresarial (se migrará a Microsoft Teams durante la migración)
18. PBX en la nube
19. Conferencias RTC
20. Llamadas RTC
21. Microsoft Teams
22. Informes de uso e informes de administración
23. Word Online, Excel Online, PowerPoint, OneNote y Visio Online
24. Planner
25. Sway
26. Aplicaciones de Microsoft 365
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune y Rights Management Service)
29. Yammer Online

### <a name="when-will-migration-happen"></a>¿Cuándo se producirá la migración?

**Azure**

Si solo es cliente de Azure, puede empezar a [migrar](https://docs.microsoft.com/azure/germany/germany-migration-main) los recursos de Azure a otra región de hoy. Si tiene Azure con Office 365, Dynamics 365 o Power BI, siga los pasos que se indican a continuación.

**Office 365**

[Participe](https://aka.ms/office365germanymoveoptin) hoy en la migración liderada por Microsoft. Cuando esté listo para iniciar la migración, le informaremos a través del centro de mensajes en el centro de administración de Microsoft 365.

**Dynamics 365 y Power BI**

Suscripción a la migración controlada por Microsoft para la [contratación de clientes de Dynamics 365](https://aka.ms/D365ceOptIn) y [Power BI](https://aka.ms/PBIOptIn) en la actualidad. Cuando esté listo para empezar la migración, le informaremos en el Centro de mensajes del Centro de administración de Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>¿El precio cambiará para los servicios de Office 365 que uso?

Sí. El precio de Microsoft&#39;s global Cloud Regions (incluidas las nuevas regiones del centro de recursos) suele ser inferior.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Durante la migración de la suscripción, ¿qué SKU y licencias se aplicarán a la organización y a los usuarios?

Durante la migración de Microsoft Cloud Alemania a los servicios de Office 365, las SKU específicas del servicio de Alemania se reemplazan con versiones globales del mismo SKU o de una SKU similar. Para la mayoría de los casos, el SKU en los servicios de Office 365 es el mismo, pero hay pocos sustituciones donde la SKU en Alemania ya no está disponible en los servicios de Office 365. Si desea actualizar la SKU asignada a su organización una vez completada la migración, póngase en contacto con el vendedor para agregar o modificar los servicios asignados.

| Microsoft Cloud Alemania-producto SKU (DE) | Microsoft Cloud global-producto SKU (WW) |
| --- | --- |
| Caja \_ de caja de cliente de (liquidación \_ de) | Caja de caja del cliente (caja de LIQUIDAción) |
| Dynamics 365 Enterprise Edition-almacenamiento de bases de datos adicional \_ de (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-almacenamiento de bases de datos adicional (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition: adicional que no es de producción instancia \_ de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition: instancia adicional que no es de producción (CRMTESTINSTANCE) |
| Dynamics 365 para Customer Service Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Customer \_ Service \_ de) | Dynamics 365 para Customer Service Enterprise Edition ( \_ servicio de \_ atención al cliente de DYN365 Enterprise \_ ) |
| Dynamics 365 for sales Enterprise Edition \_ de (DYN365 \_ Enterprise \_ sales \_ de) | Dynamics 365 for sales Enterprise Edition (DYN365 \_ Enterprise \_ sales) |
| Dynamics 365 para miembros del equipo Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Team \_ Integrations \_ de) | Dynamics 365 para miembros del equipo Enterprise Edition ( \_ miembros del equipo de DYN365 Enterprise \_ \_ ) |
| Dynamics 365 plan 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 plan 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| Servicios de ECAL (EOA, EOP, DLP) \_ de (ECAL \_ Services \_ de) | Servicios de ECAL (EOA, EOP, DLP) ( \_ servicios de ECAL) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (plan 1) \_ de (EXCHANGESTANDARD \_ de) | Exchange Online (plan 1) (EXCHANGESTANDARD) |
| Exchange Online (plan 2) \_ de (EXCHANGEENTERPRISE \_ de) | Exchange Online (plan 2) (EXCHANGEENTERPRISE) |
| Archivado de Exchange Online para Exchange Online \_ de (EXCHANGEARCHIVE \_ addon \_ de) | Archivado de Exchange Online para Exchange Online ( \_ addon EXCHANGEARCHIVE) |
| Archivado de Exchange Online para Exchange Server \_ de (EXCHANGEARCHIVE \_ de) | Archivado de Exchange Online para Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Aspectos básicos de Exchange Online ( \_ \_ aspectos básicos de Exchange) |
| Exchange Online quiosco \_ de (EXCHANGEDESKLESS \_ de) | Quiosco de Exchange Online (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ de (EOP \_ Enterprise \_ de) | Exchange Online Protection (EOP \_ Enterprise) |
| Microsoft 365 Business Standard (O365 \_ empresa \_ Premium) | Microsoft 365 Business Standard (O365 \_ empresa \_ Premium) |
| Microsoft Dynamics CRM Online instancia \_ de (CRMINSTANCE \_ de) | Instancia de Microsoft Dynamics CRM Online (CRMINSTANCE) |
| Office 365 a1 para profesores \_ de (STANDARDWOFFPACK \_ profesores \_ de) | Office 365 a1 para profesores (STANDARDWOFFPACK \_ profesores) |
| Office 365 a1 para estudiantes \_ de (STANDARDWOFFPACK \_ Student \_ de) | Office 365 a1 para estudiantes (STANDARDWOFFPACK \_ Student) |
| Office 365 Advanced Compliance \_ de (EQUIVIO \_ Analytics \_ de) | Cumplimiento de Microsoft 365 E5 (cumplimiento de protección de la información \_ \_ ) |
|Microsoft defender para Office 365 (plan 1) \_ de (ATP \_ Enterprise \_ de) |Microsoft defender para Office 365 (plan 1) (ATP \_ Enterprise) |
| Office 365 Business Essentials \_ de (O365 \_ Business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ empresa \_ Essentials) |
| Office 365 empresa Premium \_ de (O365 \_ empresa \_ Premium \_ de) | Microsoft 365 Business Standard (O365 \_ empresa \_ Premium) |
| Office 365 Business \_ de (O365 \_ empresa \_ de) | Microsoft 365 apps for Business (O365 \_ Business) |
| Office 365 E1 \_ de (STANDARDPACK \_ de) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 sin ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 sin ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 extra File Storage \_ de (SHAREPOINTSTORAGE \_ de) | Office 365 extra File Storage (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus para profesores \_ de (OFFICESUBSCRIPTION \_ profesores \_ de) | Office 365 ProPlus para profesores ( \_ profesores OFFICESUBSCRIPTION) |
| Office 365 ProPlus para estudiantes de \_ (OFFICESUBSCRIPTION \_ Student \_ de) | Office 365 ProPlus para estudiantes (OFFICESUBSCRIPTION \_ Student) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive para la empresa (plan 1) \_ de (WACONEDRIVESTANDARD \_ de) | OneDrive para la empresa (plan 1) (WACONEDRIVESTANDARD) |
| OneDrive para la empresa (plan 2) \_ de (WACONEDRIVEENTERPRISE \_ de) | OneDrive para la empresa (plan 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro para profesores \_ de (Power \_ BI \_ Pro \_ docente \_ de) | Power BI Pro para profesores (profesor de POWER \_ BI \_ Pro \_ ) |
| Power BI Pro \_ de (Power \_ BI \_ Pro \_ de) | Power BI Pro (POWER \_ BI \_ Pro) |
| Project online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project online Essentials (PROJECTESSENTIALS) |
| Project online Premium \_ de (PROJECTPREMIUM \_ de) | Project online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project Online Professional (PROJECTPROFESSIONAL) |
| Plan de proyecto 3 \_ de (PROJECTPROFESSIONAL \_ de) | Plan de proyecto 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (plan 1) \_ de (SHAREPOINTSTANDARD \_ de) | SharePoint Online (plan 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (plan 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (plan 2) (SHAREPOINTENTERPRISE) |
| Skype empresarial online (plan 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype empresarial online (plan 1) \_ de (MCOIMP \_ de) | Skype empresarial online (plan 1) (MCOIMP) |
| Skype empresarial online (plan 2) \_ de (MCOSTANDARD \_ de) | Skype empresarial online (plan 2) (MCOSTANDARD) |
| Skype empresarial Plus CAL \_ de (MCOPLUSCAL \_ de) | Skype empresarial Plus CAL (MCOPLUSCAL) |
| Visio online plan 1 para profesores \_ de (VISIOONLINE \_ PLAN1 \_ FAC \_ de) | Visio online plan 1 para profesores (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio online plan 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio online plan 1 (VISIOONLINE \_ PLAN1) |
| Visio online plan 2 para profesores \_ de (VISIOCLIENT \_ profesores \_ de) | Visio online plan 2 para profesores (VISIOCLIENT \_ profesores) |
| Visio online plan 2 \_ de (VISIOCLIENT \_ de) | Visio online plan 2 (VISIOCLIENT) |
| Visio plan 1 \_ de (VISIOONLINE \_ PLAN1 \_ de) | Visio plan 1 (VISIOONLINE \_ PLAN1) |
| Visio plan 2 \_ de (VISIOCLIENT \_ de) | Visio plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>¿Cómo puedo obtener ayuda de Microsoft para migrar a una nueva región o hacer preguntas a soporte técnico?

Si tiene alguna pregunta, puede ponerse en contacto con nosotros o con su partner:

- Para Azure, puede enviar [nuevas solicitudes de soporte técnico](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) en Azure Portal.
- Para Office 365, puede enviar preguntas mediante el &quot; vínculo ¿necesita ayuda? &quot; del [centro de administración de Microsoft 365](https://portal.office.de/).
- Si es un cliente de la contratación del cliente de Dynamics 365 y de Power BI, y también tiene Office 365, puede enviar preguntas mediante el &quot; vínculo ¿necesita ayuda? &quot; del [centro de administración de Microsoft 365](https://portal.office.de/). Las opciones de soporte de Dynamics 365 Customer Engagement se encuentran [aquí](https://docs.microsoft.com/dynamics365/get-started/support/). Las opciones de soporte técnico de Power BI se encuentran [aquí](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Más información

La información adicional acerca de la migración a las nuevas regiones del centro de datos en alemán estará disponible. Marque esta página para que pueda proteger y mantener actualizada.

- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](https://aka.ms/office365germanymoveoptin)
- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Direcciones URL e intervalos de direcciones IP de Office 365](https://aka.ms/o365endpoints)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
