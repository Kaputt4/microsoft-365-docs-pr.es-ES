---
title: 'Paso 2: Preparación de los directorios y la red'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo evaluar la preparación de los directorios y redes en el entorno.
ms.openlocfilehash: 78087b7e0c1cb7031954d3a9ac4188b59879db20
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679019"
---
# <a name="step-2-directory-and-network-readiness"></a>Paso 2: Preparación de los directorios y la red

Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Microsoft 365 Apps for enterprise. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Paso 2: Preparación de los directorios y la red</strong></p>
<p>Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>La preparación de los directorios y la red es el segundo paso del ciclo de proceso de implementación recomendado, que se centra en Azure Active Directory y optimizar la red. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorio](https://aka.ms/HowToShift).
>

Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.

With your shift to Windows 10 and Microsoft 365 Apps for enterprise you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Microsoft 365 Apps for enterprise, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.

En este artículo veremos las herramientas y opciones para preparar los servicios de directorio y los usuarios y permisos de dispositivo, listos para la implementación de Windows 10 y Aplicaciones de Microsoft 365 para empresas.

## <a name="adding-azure-active-directory"></a>Agregar acceso a Azure Active Directory

Si su organización ya usa Office 365, Exchange Online, Microsoft Intune u otros servicios de Microsoft Online, la buena noticia es que ya usa Azure Active Directory. Si es así, solo tiene que asegurarse de que los usuarios de destino para la implementación de escritorio estén en su Azure Active Directory y que tienen licencias asignadas.

Si actualmente no usa Azure Active Directory, hay [numerosos recursos](https://docs.microsoft.com/azure/active-directory/) para ayudarle a configurarlo. También pueden optar a la asistencia personalizada a través de Microsoft FastTrack, como parte de su licencia. Puede consultar más información acerca de Microsoft FastTrack [aquí](https://fasttrack.microsoft.com).

Una vez que tenga Azure Active Directory, los usuarios pueden iniciar sesión y activar sus aplicaciones de Aplicaciones de Microsoft 365 para empresas y usted puede utilizar Microsoft Intune o Windows Autopilot para la implementación automatizada de las aplicaciones y la directiva.

## <a name="network-readiness"></a>Preparación de la red

Debe tener en cuenta los requisitos de ancho de banda al planear las implementaciones. Hay tres componentes principales en una implementación que tendrán un impacto en la red: la creación de imágenes de equipos, las actualizaciones de software y la personalización de usuario. Combinadas, pueden representar más de 20 GB por equipo para la migración inicial y a menudo 1 GB o más al mes por equipo para mantenerse al día.

Empecemos explorando los requisitos de cada uno de estos tres componentes principales:

### <a name="pc-imaging"></a>Creación de imágenes de equipo

Para las imágenes de Windows sin ninguna personalización debería prever que normalmente se usarán 3 GB por equipo, mientras que para imágenes personalizadas con aplicaciones deberá permitir 6 GB o más. También deberá tener en cuenta los paquetes de controladores; que pueden ir de unos cuantos megabytes por equipo, hasta 1 GB.

### <a name="software-updates"></a>Actualizaciones de software

Debe planear el ancho de banda de red para las actualizaciones de software. Windows 10 y Aplicaciones de Microsoft 365 para empresas usan un nuevo modelo de mantenimiento que ofrece actualizaciones mensuales y semestrales. Si no conoce este modelo, puede obtener más información acerca de cómo funciona [aquí](https://docs.microsoft.com/windows/deployment/update/waas-overview).

The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Enterprise Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Enterprise Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.

### <a name="user-personalization"></a>Personalización de usuario

The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.

## <a name="limiting-bandwidth"></a>Limitar el ancho de banda

One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.

[Acerca de BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

Si usa la rama actual de Microsoft Endpoint Configuration Manager, también puede configurar los puntos de distribución habilitados para BITS o habilitar la multidifusión con WDS.

Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.

Afortunadamente, hay nuevas herramientas que facilitan la administración del impacto de la red de una implementación de escritorio a gran escala, como LEDBAT para optimizar el uso de ancho de banda disponible y las opciones de punto a punto (P2P) para mover el tráfico de implementación fuera del centro de la red y hacia el perímetro.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Aprovechamiento del ancho de banda

Low Extra Delay Background Transport (LEDBAT), compatible con Windows Server 2019 y la rama actual de Microsoft Endpoint Configuration Manager, están diseñados para optimizar el tráfico de red en clientes de Windows.

[10 características principales de red en Windows Server 2019: \#9 LEDBAT: Latency Optimized Background Transport](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Opciones de punto a punto

Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.

**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in Configuration Manager), which lets clients share already downloaded content with each other.

**Caché del mismo nivel** Los clientes admitidos por Configuration Manager también pueden hacer uso de Caché del mismo nivel. Esto permite equipos que están disponibles de forma fiable en la red hospedar orígenes para la distribución de contenido. No se recomienda que habilite esto en todos su equipos, use solo dispositivos con conexiones de red confiables como hosts (por ejemplo, equipos de escritorio, minitorres o equipos de torre). La Caché del mismo nivel puede incluso usarse para tareas de implementación que se ejecutan en fases de Windows PE durante la instalación.

Nota: Windows BranchCache y Caché del mismo nivel son complementarias y pueden funcionar juntas en el mismo entorno.

[Windows BranchCache frente a caché del mismo nivel](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Optimización de entrega** La Optimización de entrega es otra tecnología de almacenamiento en caché de punto a punto que proporciona controles de red para las implementaciones. Use la Optimización de entrega de Windows 10 para actualizar aplicaciones UWP integradas, instalar aplicaciones desde Microsoft Store y actualizaciones de software con actualizaciones rápidas. Ha estado disponible desde las primeras versiones de Windows 10, aunque solo se ha integrado recientemente con la rama actual de Microsoft Endpoint Configuration Manager. Desde Windows 10 versión 1803 nuevas opciones de configuración le permiten establecer límites de ancho de banda para actualizaciones en segundo plano y trabajos en primer plano como instalar una aplicación desde la Microsoft Store. Optimización de entrega de Windows ahora también es compatible con Aplicaciones de Microsoft 365 para empresas durante actualizaciones del cliente, disponible en todas los canales de actualización de cliente compatibles. La compatibilidad con la Optimización de entrega de Windows durante la instalación inicial del cliente estará disponible próximamente.  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Consideraciones adicionales para las Aplicaciones de Microsoft 365 para empresas**

Además de aprovechar la optimización de entrega, hay tres elementos que le ayudarán a reducir la carga de red debido a las implementaciones de Aplicaciones de Microsoft 365 para empresas.

**Binary Delta Compression** Microsoft 365 Apps for enterprise uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Microsoft 365 Apps for enterprise to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.

[Descargar actualizaciones de Aplicaciones de Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Archivos de datos de Outlook** Outlook está configurado con frecuencia para almacenar en caché todo el buzón de los usuarios de forma local para su uso sin conexión. En cualquier implementación de Windows, excepto en una actualización local, esto requiere que los archivos de datos de Outlook de los usuario se reconstruyan tras la actualización. Este es un proceso automatizado, pero con los límites de buzón de Outlook que normalmente se establecen en un máximo de 100 GB, volver a almacenar en caché todo el buzón local para todos los usuarios implica una gran cantidad de transferencia de datos. Para reducir la carga de red puede que quiera considerar el uso de directivas de grupo para reducir la configuración "Correo para mantener sin conexión". En Aplicaciones de Microsoft 365 para empresas para empresas u Office 2016 el valor predeterminado de Outlook se establece en 12 meses. Para reducir el impacto en la red considere la posibilidad configurar el almacenamiento en memoria caché para que dure de 1 a 6 meses. Cambiar esta configuración no afecta el tamaño del buzón en línea y se puede buscar todo el buzón a través de Outlook cuando tenga conexión.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**Archivos de OneDrive a petición y Mover a carpeta conocida** OneDrive es una manera excelente de sincronizar y proteger los archivos de usuario de equipos y otros dispositivos en la nube. Con Mover a carpeta conocida, puede aplicar la sincronización de archivos desde las carpetas Escritorio, Documentos e Imágenes del usuario a OneDrive, de forma que esos archivos estén disponible al iniciar sesión en un nuevo dispositivo un equipo con una nueva imagen. No obstante, debe recordar que a causa del gran tamaño y el número de archivos que se conservan en las ubicaciones de Escritorio, Documentos e Imágenes, se recomienda que planee la implementación de directivas para habilitar y exigir OneDrive en sus equipos. Una opción es usar los controles de red de directivas de grupo para limitar el ancho de banda que usa el servicio de sincronización de OneDrive.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Configuración de Mover carpeta conocida](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[Archivos de OneDrive a petición](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Si aún no ha implementado OneDrive, el cambio de Windows 7 a Windows 10 es una oportunidad perfecta para habilitar OneDrive y se integra perfectamente con Aplicaciones de Microsoft 365 para empresas. Considere iniciar esta implementación mientras prepara las aplicaciones y dispositivos. Esto impulsará la sincronización de archivos antes de que empiece a mover imágenes de Windows e implementar aplicaciones a través de la red.

## <a name="next-step"></a>Paso siguiente 

## <a name="step-3-office-and-lob-app-delivery"></a>[Paso 3: Entrega de aplicaciones de Office y de LOB](https://aka.ms/mdd3)

## <a name="previous-step"></a>Paso anterior:

## <a name="step-1-device-and-app-readiness"></a>[Paso 1: Preparación de dispositivos y aplicaciones](https://aka.ms/mdd1)

## <a name="feedback"></a>Comentarios

We'd love to hear your thoughts. Choose the type you'd like to provide:

Inicie sesión para proporcionar comentarios sobre el producto.

Our new feedback system is built on GitHub Issues. Read about this change in our blog post.
