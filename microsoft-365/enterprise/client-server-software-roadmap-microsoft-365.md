---
title: Guía básica de software de cliente y servidor para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Use esta guía básica para configurar software de cliente y servidor para Microsoft 365.
ms.openlocfilehash: ee101b3ba148f1075939d56904dc9d2ecf14e1b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905205"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a>Guía básica de software de cliente y servidor para Microsoft 365

La mayoría de las organizaciones empresariales tienen un entorno heterogéneo que incluye varias versiones de sistemas operativos, software cliente y software de servidor. Microsoft 365 para Empresas incluye las versiones más seguras de los componentes clave de su infraestructura de TI. También incluye características de productividad diseñadas para aprovechar las tecnologías en la nube.

Para maximizar el valor empresarial del conjunto de productos integrado de Microsoft 365 para empresas, comience a planear e implementar una estrategia para migrar las versiones de:

- El cliente de Office instalado en los equipos en Aplicaciones de Microsoft 365 para empresas.
- Los servidores de Office instalados en los servidores en sus servicios equivalentes en Microsoft 365.
- Windows 7 y Windows 8.1 en tus dispositivos a Windows 10 Enterprise.

>[!Note]
>La compatibilidad con Windows 7 finalizó *el 14 de enero de 2020*. Para obtener más información, vea los detalles de fin [de soporte técnico](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020).
>

A medida que realiza estas migraciones con el tiempo, su organización se acerca más a la visión del [lugar de trabajo moderno.](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/) Este entorno seguro e integrado puede ayudarle a desbloquear el trabajo en equipo y la creatividad en su organización. Microsoft 365 para empresas le permite y le habilita en todo el camino.

## <a name="migration-for-office-client-products"></a>Migración de productos cliente de Office

Las organizaciones grandes y pequeñas suelen usar una combinación de versiones anteriores de productos cliente de Office, como Word, Excel y PowerPoint. Estas versiones anteriores:

- Se puede [actualizar con](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) las últimas actualizaciones de seguridad y correcciones de soporte técnico. Pero el proceso a veces es manual y puede que no se escala en toda la organización.
- No están optimizados para usar las tecnologías en la nube de Microsoft que le ayudan a transformar digitalmente su negocio.
- No proporciones las características más recientes.

Microsoft 365 para empresas incluye Aplicaciones de Microsoft 365 para empresas. Esta versión de los productos cliente de Office está disponible con una licencia de Microsoft 365 para empresas. Se instala y actualiza desde la nube de Microsoft. Aplicaciones de Microsoft 365 para empresas incluye actualizaciones de seguridad y las características más recientes. Para obtener más información, vea [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).

### <a name="office-2007"></a>Office 2007

Para las versiones de Office en la versión de Office 2007, el final de la compatibilidad ya ha pasado. Para obtener más información, vea [Office 2007 end-of-support roadmap](/deployoffice/office-2007-end-support-roadmap).

En lugar de actualizar los equipos que ejecutan Office 2007 a Office 2010, Office 2013 u Office 2016, considere la posibilidad de seguir los siguientes pasos:

1. Obtener y asignar una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2007 en sus equipos.
3. Instale Aplicaciones de Microsoft 365 para empresas, ya sea individualmente o durante un lanzamiento de TI. Para obtener más información, vea [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones de Microsoft 365 para empresas instala actualizaciones automáticamente. Puede aprovechar los servicios basados en la nube para mejorar la seguridad y la productividad.

### <a name="office-2010"></a>Office 2010

Para las versiones de Office en la versión de Office 2010, la compatibilidad finalizó el 13 de octubre de *2020*. Para obtener más información, vea [Office 2010 end-of-support roadmap](/deployoffice/office-2010-end-support-roadmap).

Es posible que considere la posibilidad de actualizar los equipos que ejecutan Office 2010 a Office 2013 u Office 2016. Sin embargo, ambas versiones deben actualizarse manualmente. Por lo tanto, considere la posibilidad de seguir los pasos siguientes en su lugar:

1. Obtener y asignar una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2010 en sus equipos.
3. Instale Aplicaciones de Microsoft 365 para empresas, ya sea individualmente o durante un lanzamiento de TI. Para obtener más información, vea [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones de Microsoft 365 para empresas instala automáticamente las actualizaciones de seguridad y las nuevas actualizaciones de características. Puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.

### <a name="office-2013-and-office-2016"></a>Office 2013 y Office 2016

Vea la guía básica de fin [de soporte técnico de Office 2013](/lifecycle/products/microsoft-office-2013). Todavía no se ha determinado el final de la compatibilidad con Office 2016. En estas versiones, como Office 2010, debe instalar [actualizaciones de seguridad.](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) Es posible que esta tarea no se escale bien, según el tamaño de la organización.

En lugar de mantener los equipos actualizados con las actualizaciones de seguridad más recientes para Office 2013 u Office 2016, o actualizar los equipos de Office 2013 a Office 2016, considere la posibilidad de seguir los siguientes pasos:

1. Obtener y asignar una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2013 u Office 2016 en sus equipos.
3. Instale Aplicaciones de Microsoft 365 para empresas, ya sea individualmente o durante un lanzamiento de TI. Para obtener más información, vea [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones de Microsoft 365 para empresas instala automáticamente actualizaciones de seguridad y actualizaciones de nuevas características. Puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.

## <a name="migration-for-office-server-products"></a>Migración de productos de servidor de Office

Las organizaciones grandes y pequeñas suelen usar una combinación de versiones anteriores de los productos de servidor de Office, como Exchange Server y SharePoint Server. Estas versiones anteriores:

- Debe actualizarse con las últimas actualizaciones de seguridad y correcciones de soporte técnico. En algunos casos, estas actualizaciones se lanzan mensualmente.
- No están optimizados para usar las tecnologías en la nube de Microsoft que le ayudan a transformar digitalmente su negocio.
- No incluyas nuevas aplicaciones de productividad, como Microsoft Teams.
- No incluya las características de seguridad más recientes, como Exchange y Defender para Office 365.

Microsoft 365 para Enterprise incluye versiones basadas en la nube de servicios de servidor de Office que usan algunas de las mismas herramientas que las versiones locales del software de servidor de Office, como exploradores web y el cliente de Outlook. Estos servicios se actualizan automáticamente por motivos de seguridad. Por lo tanto, el personal de IT ahorra el tiempo necesario para mantener y actualizar los servidores locales. Estos servicios también ofrecen nuevas mejoras de características que no están presentes en el software del servidor de Office.

Use los siguientes recursos para obtener información sobre la migración de usuarios y datos para cargas de trabajo específicas de Microsoft 365:

- [Mover buzones de correo de Exchange Server local a Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migrar datos de SharePoint desde SharePoint Server a SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migrar Skype Empresarial Online a Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

### <a name="office-2007-server-products"></a>Productos de servidor de Office 2007

Para los productos de servidor de la versión de Office 2007, el final de la compatibilidad ya ha pasado. Vea estos artículos para obtener más información:

- [Guía básica de fin de soporte técnico de Exchange 2007](exchange-2007-end-of-support.md)
- [Guía básica de fin de soporte técnico de SharePoint Server 2007](sharepoint-2007-end-of-support.md)
- [Guía básica de fin de soporte técnico de Project Server 2007](project-server-2007-end-of-support.md)
- [Guía básica de fin de soporte técnico de Office Communications Server](/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server plan de fin de soporte técnico de 2007](pps-2007-end-of-support.md)

En lugar de actualizar los productos de servidor en la versión de Office 2007 con productos de servidor en las versiones de Office 2010, Office 2013 u Office 2016, considere la posibilidad de seguir los pasos siguientes:

1. Migre los datos de los servidores de Office 2007 a Microsoft 365. Para obtener más información o ayuda, contrate a un partner de Microsoft.
2. Roll out the new functionality and work processes to your users.
3. Cuando ya no necesite los servidores locales que ejecuten productos de servidor de Office 2007, desconéctelos.

### <a name="office-2010-server-products"></a>Productos de servidor de Office 2010

La compatibilidad [Exchange Server 2010](exchange-2010-end-of-support.md) finalizó el *13 de octubre de 2020*.

El soporte técnico para [SharePoint Server 2010](upgrade-from-sharepoint-2010.md) finalizará el *13 de abril de 2021*.

En lugar de actualizar estos productos de servidor en la versión de Office 2010 con productos de servidor en las versiones de Office 2013 u Office 2016, considere la posibilidad de seguir los siguientes pasos:

1. Migre los datos de los servidores de Office 2010 a Microsoft 365. Para obtener más información, [consulte FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contrate a un partner de Microsoft.
2. Roll out the new functionality and work processes to your users.
3. Cuando ya no necesite los servidores locales que ejecuten productos de servidor de Office 2010, desconsódalos.

### <a name="office-2013-server-products"></a>Productos de servidor de Office 2013

Para los productos de servidor de la versión de Office 2013, no se ha determinado el final de la compatibilidad. En lugar de actualizar los productos de servidor en la versión de Office 2013 con productos de servidor en la versión de Office 2016, considere la posibilidad de seguir los pasos siguientes:

1. Migre los datos de los servidores de Office 2013 a Microsoft 365. Para obtener más información, [consulte FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contrate a un partner de Microsoft.
2. Roll out the new functionality and work processes to your users.
3. Cuando ya no necesite los servidores locales que ejecuten productos de servidor de Office 2013, desconéctelos.

### <a name="office-2016-server-products"></a>Productos de servidor de Office 2016

Para los productos de servidor de la versión de Office 2016, no se ha determinado el final de la compatibilidad. Para aprovechar el servicio basado en la nube y las mejoras para transformar digitalmente su negocio, considere la posibilidad de seguir los pasos siguientes:

1. Migre los datos de los servidores de Office 2016 a Microsoft 365. Para obtener más información, [consulte FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contrate a un partner de Microsoft.
2. Roll out the new functionality and work processes to your users.
3. Cuando ya no necesite los servidores locales que ejecuten productos de servidor de Office 2016, desconsódalos.

## <a name="migration-for-windows-7-and-81"></a>Migración para Windows 7 y 8.1

El soporte técnico finalizó para Windows 7 *el 14 de enero de 2020*. Para migrar los dispositivos que ejecutan Windows 7 o Windows 8.1, puedes realizar una actualización local.

Para obtener más métodos, [vea escenarios](/windows/deployment/windows-10-deployment-scenarios) de implementación de Windows 10. También puede [planear la implementación de Windows 10](/windows/deployment/planning/) por su cuenta.

## <a name="office-2010-clients-and-servers-and-windows-7"></a>Clientes y servidores de Office 2010 y Windows 7

Este es un resumen visual de las opciones de actualización, migración y movimiento a la nube para clientes y servidores de Office 2010 y Windows 7:

[![Imagen que muestra las opciones para el final de la compatibilidad con los clientes y servidores de Office 2010 y Windows 7.](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este póster de una página es una forma rápida de comprender las rutas de acceso que puede seguir para administrar el fin de la compatibilidad con productos de cliente y servidor de Office 2010 y Windows 7. Las rutas de acceso preferidas se admiten en Microsoft 365 para Enterprise.

Puede descargar [este póster e](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) imprimirlo en tamaño de letra, tamaño legal o tamaño de tabloide (11 x 17).

## <a name="transition-your-entire-organization"></a>Realizar la transición en toda la organización

Para obtener una mejor imagen de cómo mover toda la organización a los productos y servicios de Microsoft 365 para Empresas, descargue este póster de transición:

[![Imagen que muestra el póster Transición a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Este póster de dos páginas es una forma rápida de hacer un inventario de la infraestructura existente. Úselo para obtener instrucciones para pasar a un producto o servicio en Microsoft 365 para Empresas. Muestra productos de Windows y Office y otros elementos de infraestructura y seguridad, como la administración de dispositivos, la protección de identidades y amenazas, y la protección de información y cumplimiento.

## <a name="how-microsoft-migrated-to-microsoft-365-for-enterprise"></a>Cómo migró Microsoft a Microsoft 365 para empresas

Vea cómo los expertos de TI de Microsoft migraron la compañía a Microsoft 365 para empresas:

- [Implementación y actualización de aplicaciones de Microsoft 365 para empresas](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft migra 150.000 buzones a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint en la nube: Obtenga información sobre cómo Microsoft llevó a cabo su propia migración](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Implementar Windows 10 en Microsoft como una actualización local](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementación de Windows 10: sugerencias y trucos de Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)