---
title: Paso 4. Migración de su Microsoft 365 para inquilinos empresariales
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migre Windows dispositivos, Office aplicaciones cliente y Office servidores para sus Microsoft 365 inquilinos.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929149"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 4. Migración de su Microsoft 365 para inquilinos empresariales

La mayoría de las organizaciones empresariales tienen un entorno heterogéneo que incluye varias versiones de sistemas operativos, software cliente y software de servidor. Microsoft 365 para empresas incluye las versiones más seguras de los componentes clave de su infraestructura de TI. También incluye características de productividad diseñadas para aprovechar las tecnologías en la nube.

Para maximizar el valor empresarial de la Microsoft 365 de productos integrados para empresas, comience a planear e implementar una estrategia para migrar estas versiones:

| From | To |
|:-------|:-----|
| Windows 7 y Windows 8.1 | Windows 10 Enterprise |
| Office de cliente instalados en los dispositivos del trabajador | Aplicaciones de Microsoft 365 para empresas |
| Office de servidor instalados en servidores locales | Sus servicios basados en la nube equivalentes en Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrar a Windows 10

Cada Microsoft 365 licencia de empresa incluye una licencia para Windows 10 Enterprise. Para migrar los dispositivos que se Windows 7 o Windows 8.1, puede realizar una actualización local. La compatibilidad finalizó Windows 7 de enero *de 2020.* 

Para obtener métodos adicionales de Windows 10 Enterprise más allá de una actualización local, [vea Windows 10 escenarios de implementación](/windows/deployment/windows-10-deployment-scenarios). También puede [planear la implementación de Windows 10](/windows/deployment/planning/) por su cuenta.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrar a Aplicaciones Microsoft 365 para empresas

Microsoft 365 para empresas incluye Aplicaciones Microsoft 365 para empresas, una versión de los productos cliente de Office (Word, PowerPoint, Excel y Outlook) que se instala y actualiza desde la nube de Microsoft. Para obtener más información, vea [Acerca de Aplicaciones Microsoft 365 para empresas](/deployoffice/about-microsoft-365-apps).

En lugar de mantener los equipos actuales para Office 2019 o versiones anteriores, siga estos pasos:

1. Obtener y asignar una Microsoft 365 licencia de usuario para los usuarios.
2. Desinstale Office 2013 o Office 2016 en sus equipos.
3. Instale Aplicaciones Microsoft 365 para empresas, ya sea individualmente o durante un lanzamiento de IT. Para más información, consulte la [Guía de implementación para Aplicaciones de Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones Microsoft 365 para empresas instala actualizaciones de seguridad y actualizaciones de nuevas características automáticamente y puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migración de servidores y datos locales a Microsoft 365

Microsoft 365 para empresas incluye versiones basadas en la nube de servicios de servidor de Office que usan algunas de las mismas herramientas que las versiones locales de software de servidor Office, como exploradores web y el cliente Outlook. Estos servicios basados en la nube se actualizan automáticamente para la seguridad y las nuevas características. Después de la migración, el departamento de TI puede ahorrar el tiempo necesario para mantener y actualizar los servidores locales.

Use los siguientes recursos para obtener información acerca de la migración de usuarios y datos para cargas de trabajo Microsoft 365 específicas:

- [Mover buzones de correo de la Exchange Server local a Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migrar SharePoint datos de SharePoint Server a SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migrar Skype Empresarial Online a Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Realizar la transición en toda la organización

Para obtener una mejor imagen de cómo mover toda la organización a los productos y servicios de Microsoft 365 para empresas, descargue este póster de transición:

[![Imagen que muestra el póster Transición a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Este póster de dos páginas es una forma rápida de hacer un inventario de la infraestructura existente. Úselo para obtener instrucciones para pasar a un producto o servicio en Microsoft 365 para la empresa. Muestra productos Windows y Office y otros elementos de infraestructura y seguridad, como la administración de dispositivos, la protección de identidades y amenazas, y la protección y cumplimiento de la información.

## <a name="results-of-step-4"></a>Resultados del paso 4

Para la migración de su Microsoft 365 inquilino, ha determinado:

- Qué dispositivos se Windows 7 o Windows 8.1 y el plan para actualizarlos a Windows 10 Enterprise.
- Qué dispositivos ejecutan las Office cliente y el plan para actualizarlas a Microsoft 365 aplicaciones empresariales.
- Qué servicios de servidor Office local deben migrarse a su Microsoft 365 equivalente y el plan para migrarlos y sus datos.

Este es un ejemplo de un inquilino con una migración completada de servidores locales.

![Ejemplo de un inquilino con una migración completada de servidores locales](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

En esta ilustración, la organización tiene:

- Migró sus buzones de correo Exchange Server locales a Exchange Online.
- Migró sus datos y sitios SharePoint servidor local a SharePoint en Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Mantenimiento continuo para la migración

De forma continua, es posible que deba:

- Según el estado de la migración Exchange buzón de correo, continúe implementando la transición a Exchange Online a la organización.
- En función del estado de la migración SharePoint sitio local, continúe implementando la transición a SharePoint en Microsoft 365 a la organización.

## <a name="next-step"></a>Paso siguiente

[![Paso 5. Implementar la administración de dispositivos y aplicaciones](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Continúe con [la administración de dispositivos y aplicaciones](tenant-management-device-management.md) para implementar la administración de dispositivos y aplicaciones.