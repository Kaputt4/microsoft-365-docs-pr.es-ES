---
title: Plan de desarrollo de software de cliente y servidor para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-subscription-management
ms.custom: it-pro
description: Use este mapa de ruta para configurar el software de cliente y servidor para Microsoft 365.
ms.openlocfilehash: c42f02f20c9f16dd19f60d051c7f4a4aa5316bf2
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090847"
---
# <a name="client-and-server-software-roadmap-for-microsoft-365"></a>Plan de desarrollo de software de cliente y servidor para Microsoft 365

La mayoría de las organizaciones empresariales tienen un entorno heterogéneo que incluye varias versiones de sistemas operativos, software cliente y software de servidor. Microsoft 365 para Enterprise incluye las versiones más seguras de los componentes clave de la infraestructura de TI. También incluye características de productividad diseñadas para aprovechar las tecnologías en la nube.

Para maximizar el valor empresarial de la Microsoft 365 para Enterprise conjunto integrado de productos, empiece a planear e implementar una estrategia para migrar versiones de:

- El cliente Office instalado en los equipos para Aplicaciones Microsoft 365 para empresas.
- Los servidores Office instalados en los servidores en sus servicios equivalentes en Microsoft 365.
- Windows 7 y Windows 8.1 en los dispositivos para Windows 10 Enterprise.

>[!Note]
>El soporte técnico para Windows 7 finalizó el *14 de enero de 2020*. Para obtener más información, consulte los [detalles del final del soporte](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020) técnico.
>

A medida que realiza estas migraciones con el tiempo, su organización se acerca a la visión del [área de trabajo moderna](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/). Este entorno seguro e integrado puede ayudarle a desbloquear el trabajo en equipo y la creatividad en su organización. Microsoft 365 para Enterprise le permite y le permite en todo el camino.

## <a name="migration-for-office-client-products"></a>Migración para productos cliente de Office

Las organizaciones grandes y pequeñas suelen usar una combinación de versiones anteriores de Office productos cliente, como Word, Excel y PowerPoint. Estas versiones anteriores:

- Se puede [actualizar](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5) con las últimas actualizaciones de seguridad y correcciones de soporte técnico. Pero el proceso a veces es manual y es posible que no se escale en toda la organización.
- No están optimizados para usar las tecnologías en la nube de Microsoft que le ayudan a transformar digitalmente su negocio.
- No proporcione las características más recientes.

Microsoft 365 para Enterprise incluye Aplicaciones Microsoft 365 para empresas. Esta versión de los productos cliente de Office está disponible con una Microsoft 365 para Enterprise licencia. Se instala y actualiza desde la nube de Microsoft. Aplicaciones de Microsoft 365 para empresas incluye actualizaciones de seguridad y las características más recientes. Para obtener más información, consulte [Acerca de Aplicaciones Microsoft 365 para empresas](/deployoffice/about-microsoft-365-apps).

### <a name="office-2007"></a>Office 2007

Para las versiones de Office en la versión de Office 2007, ya se ha superado el final de la compatibilidad. Para obtener más información, consulte [Office hoja de ruta de fin de soporte técnico de 2007](/deployoffice/office-2007-end-support-roadmap).

En lugar de actualizar los equipos que ejecutan Office 2007 a Office 2010, Office 2013 o Office 2016, considere la posibilidad de realizar los pasos siguientes:

1. Obtenga y asigne una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2007 en sus equipos.
3. Instale Aplicaciones Microsoft 365 para empresas, ya sea de forma individual o durante un lanzamiento de TI. Para más información, consulte la [Guía de implementación para Aplicaciones de Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones Microsoft 365 para empresas instala actualizaciones automáticamente. Puede aprovechar los servicios basados en la nube para mejorar la seguridad y la productividad.

### <a name="office-2010"></a>Office 2010

Para las versiones de Office en la versión de Office 2010, la compatibilidad finalizó el *13 de octubre de 2020*. Para obtener más información, consulte [Office hoja de ruta de fin de soporte técnico de 2010](/deployoffice/office-2010-end-support-roadmap).

Puede considerar la posibilidad de actualizar los equipos que ejecutan Office 2010 a Office 2013 o Office 2016. Sin embargo, ambas versiones deben actualizarse manualmente. Por lo tanto, considere la posibilidad de realizar los pasos siguientes en su lugar:

1. Obtenga y asigne una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2010 en sus equipos.
3. Instale Aplicaciones Microsoft 365 para empresas, ya sea de forma individual o durante un lanzamiento de TI. Para más información, consulte la [Guía de implementación para Aplicaciones de Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones Microsoft 365 para empresas instala automáticamente las actualizaciones de seguridad y las nuevas actualizaciones de características. Puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.

### <a name="office-2013-and-office-2016"></a>Office 2013 y Office 2016

Consulte la [hoja de ruta de fin de soporte técnico para Office 2013](/lifecycle/products/microsoft-office-2013). Todavía no se ha determinado el final de la compatibilidad con Office 2016. En estas versiones, como Office 2010, debe [instalar actualizaciones de seguridad](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5). Es posible que esta tarea no se escale bien, en función del tamaño de la organización.

En lugar de mantener los equipos actualizados con las actualizaciones de seguridad más recientes para Office 2013 o Office 2016, o actualizar los equipos de Office 2013 a Office 2016, considere la posibilidad de realizar los pasos siguientes:

1. Obtenga y asigne una licencia de Microsoft 365 para los usuarios.
2. Desinstale Office 2013 o Office 2016 en sus equipos.
3. Instale Aplicaciones Microsoft 365 para empresas, ya sea de forma individual o durante un lanzamiento de TI. Para más información, consulte la [Guía de implementación para Aplicaciones de Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps).

Aplicaciones Microsoft 365 para empresas instala actualizaciones de seguridad y nuevas actualizaciones de características automáticamente. Puede aprovechar los servicios basados en la nube en Microsoft 365 para mejorar la seguridad y la productividad.

## <a name="migration-for-office-server-products"></a>Migración para Office productos de servidor

Las organizaciones grandes y pequeñas suelen usar una combinación de versiones anteriores de los productos de servidor de Office, como Exchange Server y SharePoint Server. Estas versiones anteriores:

- Tienen que actualizarse con las correcciones de soporte técnico y actualizaciones de seguridad más recientes. En algunos casos, estas actualizaciones se publican de forma mensual.
- No están optimizados para usar las tecnologías en la nube de Microsoft que le ayudan a transformar digitalmente su negocio.
- No incluya nuevas aplicaciones de productividad, como Microsoft Teams.
- No incluya las características de seguridad más recientes, como Exchange y Defender para Office 365.

Microsoft 365 para Enterprise incluye versiones basadas en la nube de Office servicios de servidor que usan algunas de las mismas herramientas que las versiones locales de Office software de servidor, como exploradores web y el cliente Outlook. Estos servicios se actualizan automáticamente para la seguridad. Por lo tanto, el personal de TI ahorra el tiempo necesario para mantener y actualizar los servidores locales. Estos servicios también ofrecen nuevas mejoras de características que no están presentes en Office software de servidor.

Use los siguientes recursos para obtener información sobre cómo migrar usuarios y datos para cargas de trabajo de Microsoft 365 específicas:

- [Mover buzones de correo de Exchange Server locales a Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migración de datos de SharePoint de SharePoint Server a SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migración de Skype Empresarial en línea a Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

### <a name="office-2007-server-products"></a>productos de servidor de Office 2007

En el caso de los productos de servidor de la versión Office 2007, ya se ha superado el final de la compatibilidad. Consulte estos artículos para obtener más información:

- [Exchange hoja de ruta de fin de soporte técnico de 2007](exchange-2007-end-of-support.md)
- [SharePoint Server 2007 hoja de ruta de fin de soporte técnico](sharepoint-2007-end-of-support.md)
- [Project Server 2007 hoja de ruta de fin de soporte técnico](project-server-2007-end-of-support.md)
- [Office hoja de ruta de fin de soporte técnico de Communications Server](/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server hoja de ruta de fin de soporte técnico de 2007](pps-2007-end-of-support.md)

En lugar de actualizar los productos de servidor en la versión Office 2007 con productos de servidor en las versiones de Office 2010, Office 2013 o Office 2016, considere la posibilidad de realizar los pasos siguientes:

1. Migre los datos de los servidores de Office 2007 a Microsoft 365. Para obtener más información o ayuda, contrate a un partner de Microsoft.
2. Implemente la nueva funcionalidad y los procesos de trabajo para los usuarios.
3. Cuando ya no necesite los servidores locales que ejecutan Office productos de servidor de 2007, desconéctelos.

### <a name="office-2010-server-products"></a>productos de servidor de Office 2010

El soporte técnico para [Exchange Server 2010](exchange-2010-end-of-support.md) finalizó el *13 de octubre de 2020*.

El soporte técnico para [SharePoint Server 2010](upgrade-from-sharepoint-2010.md) finalizará el *13 de abril de 2021*.

En lugar de actualizar estos productos de servidor en la versión de Office 2010 con productos de servidor en las versiones de Office 2013 o Office 2016, considere la posibilidad de realizar los pasos siguientes:

1. Migre los datos de los servidores de Office 2010 a Microsoft 365. Para obtener más información, consulte [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contratar a un asociado de Microsoft.
2. Implemente la nueva funcionalidad y los procesos de trabajo para los usuarios.
3. Cuando ya no necesite los servidores locales que ejecutan Office productos de servidor de 2010, desconéctelos.

### <a name="office-2013-server-products"></a>productos de servidor de Office 2013

En el caso de los productos de servidor de la versión Office 2013, no se ha determinado el final del soporte técnico. En lugar de actualizar los productos de servidor en la versión Office 2013 con productos de servidor en la versión Office 2016, considere la posibilidad de realizar los pasos siguientes:

1. Migre los datos de los servidores de Office 2013 a Microsoft 365. Para obtener más información, consulte [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contratar a un asociado de Microsoft.
2. Implemente la nueva funcionalidad y los procesos de trabajo para los usuarios.
3. Cuando ya no necesite los servidores locales que ejecutan Office productos de servidor de 2013, desconéctelos.

### <a name="office-2016-server-products"></a>productos de servidor de Office 2016

En el caso de los productos de servidor de la versión Office 2016, no se ha determinado el final del soporte técnico. Para aprovechar las ventajas del servicio basado en la nube y las mejoras para transformar digitalmente su negocio, considere la posibilidad de realizar los pasos siguientes:

1. Migre los datos de los servidores de Office 2016 a Microsoft 365. Para obtener más información, consulte [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365) o contratar a un asociado de Microsoft.
2. Implemente la nueva funcionalidad y los procesos de trabajo para los usuarios.
3. Cuando ya no necesite los servidores locales que ejecutan Office productos de servidor de 2016, desconéctelos.

## <a name="migration-for-windows-7-and-81"></a>Migración para Windows 7 y 8.1

El soporte técnico finalizó para el Windows 7 el *14 de enero de 2020*. Para migrar los dispositivos que ejecutan Windows 7 o Windows 8.1, puede realizar una actualización local.

Para obtener métodos adicionales, vea [Escenarios de implementación de Windows 10](/windows/deployment/windows-10-deployment-scenarios). También puede [planear la implementación de Windows 10](/windows/deployment/planning/) por su cuenta.

## <a name="office-2010-clients-and-servers-and-windows-7"></a>Office servidores y clientes de 2010 y Windows 7

Este es un resumen visual de las opciones de actualización, migración y traslado a la nube para Office 2010 clientes y servidores y Windows 7:

[![Imagen que muestra las opciones para el final de la compatibilidad con los clientes y servidores de Office 2010 y Windows 7.](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Este póster de una página es una manera rápida de comprender las rutas de acceso que puede tomar para administrar el final de la compatibilidad con los productos de cliente y servidor de Office 2010 y Windows 7. Las rutas de acceso preferidas se admiten en Microsoft 365 para Enterprise.

Puede [descargar este póster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) e imprimirlo en tamaño de letra, tamaño legal o tamaño tabloide (11 x 17).

## <a name="transition-your-entire-organization"></a>Realizar la transición en toda la organización

Para obtener una mejor idea de cómo mover toda la organización a los productos y servicios de Microsoft 365 para Enterprise, descargue este póster de transición:

[![Imagen que muestra el póster Transición a Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Este póster de dos páginas es una forma rápida de hacer un inventario de la infraestructura existente. Úselo para obtener instrucciones para pasar a un producto o servicio en Microsoft 365 para Enterprise. Muestra Windows y Office productos y otros elementos de infraestructura y seguridad, como la administración de dispositivos, la protección de identidades y amenazas, y la protección de la información y el cumplimiento.

## <a name="how-microsoft-migrated-to-microsoft-365-for-enterprise"></a>Cómo migró Microsoft a Microsoft 365 para Enterprise

Vea cómo los expertos de TI de Microsoft migraron la empresa a Microsoft 365 para Enterprise:

- [Implementación y actualización de Aplicaciones Microsoft 365 para empresas](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft migra 150.000 buzones a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [SharePoint en la nube: Obtenga información sobre cómo Microsoft llevó a cabo su propia migración](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [Implementar Windows 10 en Microsoft como una actualización local](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows 10 implementación: Sugerencias y trucos de TI de Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)