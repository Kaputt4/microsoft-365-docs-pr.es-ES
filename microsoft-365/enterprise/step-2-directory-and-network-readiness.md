---
title: 'Paso 2: Preparación de los directorios y la red'
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
ms.openlocfilehash: 505099607b6c4744af29d00ff04e2535a2c0848e
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982731"
---
# <a name="step-2-directory-and-network-readiness"></a>Paso 2: Preparación de los directorios y la red

Asegúrese de que su directorio y la red están configurados y listos para admitir su cambio a Windows 10 y Office 365 ProPlus. Esto requerirá que los Servicios de Azure Active Directory estén instalados para los usuarios y su red debe tener la capacidad de gestionar tanto su tráfico regular como el movimiento potencial de una gran cantidad de datos mientras se actualizan los equipos y se restauran los archivos, la configuración y las aplicaciones de los usuarios.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Paso 2: Preparación de los directorios y la red</strong></p>
<p>Los servicios conectados en la nube en Office 365 ProPlus y las nuevas opciones de implementación, como Windows Autopilot, requieren Azure Active Directory. También es importante que planifique los aspectos relacionados con la red y la conectividad para mover imágenes, aplicaciones, controladores y archivos relacionados de Windows al equipo. Obtenga información sobre cómo las nuevas herramientas y opciones de implementación reducen y simplifican el tráfico de red.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>La preparación de los directorios y la red es el segundo paso del ciclo de proceso de implementación recomendado, que se centra en Azure Active Directory y optimizar la red. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorio](https://aka.ms/HowToShift).
>

La preparación de los directorios y la red es fundamental para asegurar una implementación sin problemas de sistemas operativos y escritorios. Como con cualquier implementación automatizada, es importante asegurar que se puedan alcanzar los recursos compartidos de archivos y la red necesitará poder admitir la transferencia de archivos muy grandes, posiblemente a cientos o incluso miles de PC al mismo tiempo.

Con su cambio a Windows 10 y Office 365 ProPlus, también deberá asegurarse de que la identidad basada en la nube está establecida con Azure Active Directory. Esto es clave no solo para la activación de Office 365 ProPlus, también le permitirá aprovecharse de soluciones de aprovisionamiento modernas como Windows Autopilot.

En este artículo veremos las herramientas y opciones para preparar los servicios de directorio y los usuarios y permisos de dispositivo, listos para la implementación de Windows 10 y Office 365 ProPlus.

## <a name="adding-azure-active-directory"></a>Agregar acceso a Azure Active Directory

Si su organización ya usa Office 365, Exchange Online, Microsoft Intune u otros servicios de Microsoft Online, la buena noticia es que ya usa Azure Active Directory. Si es así, solo tiene que asegurarse de que los usuarios de destino para la implementación de escritorio estén en su Azure Active Directory y que tienen licencias asignadas.

Si actualmente no usa Azure Active Directory, hay [numerosos recursos](https://docs.microsoft.com/es-ES/azure/active-directory/) para ayudarle a configurarlo. También pueden optar a la asistencia personalizada a través de Microsoft FastTrack, como parte de su licencia de Office 365. Puede consultar más información acerca de Microsoft FasTrack [aquí](https://fasttrack.microsoft.com).

Una vez que tenga Azure Active Directory, los usuarios pueden iniciar sesión y activar sus aplicaciones de Office 365 ProPlus y usted puede utilizar Microsoft Intune o Windows Autopilot para la implementación automatizada de las aplicaciones y la directiva.

## <a name="network-readiness"></a>Preparación de la red

Debe tener en cuenta los requisitos de ancho de banda al planear las implementaciones. Hay tres componentes principales en una implementación que tendrán un impacto en la red: la creación de imágenes de equipos, las actualizaciones de software y la personalización de usuario. Combinadas, pueden representar más de 20 GB por equipo para la migración inicial y a menudo 1 GB o más al mes por equipo para mantenerse al día.

Empecemos explorando los requisitos de cada uno de estos tres componentes principales:

### <a name="pc-imaging"></a>Creación de imágenes de equipo

Para las imágenes de Windows sin ninguna personalización debería prever que normalmente se usarán 3 GB por equipo, mientras que para imágenes personalizadas con aplicaciones deberá permitir 6 GB o más. También deberá tener en cuenta los paquetes de controladores; que pueden ir de unos cuantos megabytes por equipo, hasta 1 GB.

### <a name="software-updates"></a>Actualizaciones de software

Debe planear el ancho de banda de red para las actualizaciones de software. Windows 10 y Office 365 ProPlus usan el nuevo modelo de mantenimiento que ofrece actualizaciones mensuales y semestrales. Si no conoce este modelo, puede obtener más información acerca de cómo funciona [aquí](https://docs.microsoft.com/es-ES/windows/deployment/update/waas-overview).

El nuevo modelo de mantenimiento incluye actualizaciones de características para Windows dos veces al año, actualizaciones de canal semianuales de Office y actualizaciones de calidad mensuales. Las actualizaciones de características suelen tener un tamaño de 2 a 4 GB y las actualizaciones de canal semianuales de Office son 300 o 400 MB cada una. En cuanto a las actualizaciones mensuales de calidad, pueden ir desde unos cientos megabytes hasta un gigabyte. Esto se debe a que las actualizaciones mensuales son acumulables, de modo que el tamaño aumenta a lo largo de la vida del mantenimiento para cada versión de Windows 10. Dicho esto, hay herramientas que pueden ayudarle a reducir la cantidad de datos que deben pasar por la red para implementar actualizaciones. Trataremos esto con más detalle más adelante.

### <a name="user-personalization"></a>Personalización de usuario

El tercer componente considerar es la personalización de usuario. Aquí debe planificar el ancho de banda de red para dar cabida a la restauración de sus aplicaciones, la configuración y los archivos de usuario como parte del proceso de actualización o la sustitución del equipo. Juntos, estos elementos suelen superan 20 GB por equipo. Para algunos usuarios puede superar 100GB.

## <a name="limiting-bandwidth"></a>Limitar el ancho de banda

Una forma de limitar el impacto del tráfico relacionado con la implementación en la red es limitarlo con la función BITS (servicio de transferencia inteligente en segundo plano) de los clientes. BITS usa una tasa de bits adaptativa (ABR) para ajustar el ancho de banda disponible para la implementación; puede configurarse en los clientes que usan la directiva de grupo.

[Acerca de BITS](https://docs.microsoft.com/es-ES/windows/desktop/bits/about-bits)

Si usa la rama actual de System Center Configuration Manager, también puede configurar los puntos de distribución habilitados para BITS o habilitar la multidifusión con WDS.

La limitación del tráfico específico significa que el tráfico de red normal se ve menos afectado al descargar las actualizaciones y las aplicaciones de equipos. Pero reservar un porcentaje específico de ancho de banda para estas tareas ayuda a asegurar que la productividad no se ve afectada por la implementación de Windows u Office y los procesos pueden seguir ejecutándose. Puede empeorar el tiempo de inactividad relacionado con la implementación, con usuarios que no pueden acceder a sus equipos mientras se ejecuta la implementación.

Afortunadamente, hay nuevas herramientas que facilitan la administración del impacto de la red de una implementación de escritorio a gran escala, como LEDBAT para optimizar el uso de ancho de banda disponible y las opciones de punto a punto (P2P) para mover el tráfico de implementación fuera del centro de la red y hacia el perímetro.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Aprovechamiento del ancho de banda

Low Extra Delay Background Transport (LEDBAT), compatible con Windows Server 2019 y la rama actual de System Center Configuration Manager, está diseñado para optimizar el tráfico de red en clientes de Windows.

[10 características principales de red en Windows Server 2019: \#9 LEDBAT: Latency Optimized Background Transport](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

A diferencia de la limitación tradicional, LEDBAT puede usar todo el ancho de banda de la red disponible como tarea en segundo plano, cediendo ancho de banda cuando sea necesario. Al contrario que BITS no hay retraso, todo es automatizado: no se requiere ajuste manual o planificación y todo se configura en el lado del servidor. Esto permite potencialmente mejorar el rendimiento.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Opciones de punto a punto

Las opciones de punto a punto se usan cada vez más en migraciones de Windows 10 para imágenes de equipo, actualizaciones de software y personalización de usuarios. Tienen un gran valor al facilitar actualizaciones de compilación a compilación tras la implementación inicial de Windows 10. A continuación, cubriremos varios ejemplos para ayudar a trasladar tráfico relacionado con Windows 10 y Office lejos del centro de la red, lo que reducirá la necesidad de la limitación tradicional y permitirá a los equipos encontrar los archivos de actualización que necesitan en otros puntos de su red local, en vez de descargarlos de un único punto de distribución en Internet.

**Windows BranchCache** puede ayudarle a descargar contenido en entornos de distribución sin saturar la red. Cuenta con dos opciones: Modo de caché hospedada, que le permite utilizar servidores locales para almacenar caché y modo de caché distribuida (un modo compatible con System Center Configuration Manager), que permite a los clientes compartir el contenido descargado entre ellos.

**Caché del mismo nivel** Los clientes compatibles con System Center Configuration Manager también pueden hacer uso de Caché del mismo nivel. Esto permite equipos que están disponibles de forma fiable en la red hospedar orígenes para la distribución de contenido. No se recomienda que habilite esto en todos su equipos, use solo dispositivos con conexiones de red confiables como hosts (por ejemplo, equipos de escritorio, minitorres o equipos de torre). La Caché del mismo nivel puede incluso usarse para tareas de implementación que se ejecutan en fases de Windows PE durante la instalación.

Nota: Windows BranchCache y Caché del mismo nivel son complementarias y pueden funcionar juntas en el mismo entorno.

[Windows BranchCache frente a caché del mismo nivel](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Optimización de entrega** La Optimización de entrega es otra tecnología de almacenamiento en caché de punto a punto que proporciona controles de red para las implementaciones. Use la Optimización de entrega de Windows 10 para actualizar aplicaciones UWP integradas, instalar aplicaciones desde Microsoft Store y actualizaciones de software con actualizaciones rápidas. Ha estado disponible desde las primeras versiones de Windows 10, aunque solo se ha integrado recientemente con la rama actual de System Center Configuration Manager. Desde Windows 10 versión 1803 nuevas opciones de configuración le permiten establecer límites de ancho de banda para actualizaciones en segundo plano y trabajos en primer plano como instalar una aplicación desde la Microsoft Store. Optimización de entrega de Windows ahora también es compatible con Office 365 ProPlus durante actualizaciones del cliente, disponible en todas los canales de actualización de cliente de Office 365 compatibles. La compatibilidad con la Optimización de entrega de Windows durante la instalación inicial del cliente de Office 365 estará disponible próximamente.  

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Consideraciones adicionales para Office 365 ProPlus**

Además de aprovechar la optimización de entrega, hay tres elementos que le ayudarán a reducir la carga de red debido a las implementaciones de Office 365 ProPlus.

**La compresión binaria de delta** Office 365 ProPlus utiliza compresión binaria de delta para reducir el ancho de banda consumido por actualizaciones de software al actualizar desde la versión más reciente de Office 365 ProPlus hasta la siguiente versión. Pero solo al quitar los cambios a nivel binario de la versión anterior, el impacto de las actualizaciones acumulativas se ha minimizado. Esto tiene el potencial de ahorrar cientos de megas de datos por equipo cada mes. Para poder usar esta función, sin embargo, no puede saltarse ninguna versión. Si lo hace, deberá descargar la actualización acumulativa completa.

[Descargar actualizaciones de Office 365](https://docs.microsoft.com/es-ES/deployoffice/overview-of-the-update-process-for-office-365-proplus#download-the-updates-for-office-365-proplus)

**Archivos de datos de Outlook** Outlook está configurado con frecuencia para almacenar en caché todo el buzón de los usuarios de forma local para su uso sin conexión. En cualquier implementación de Windows, excepto en una actualización local, esto requiere que los archivos de datos de Outlook de los usuario se reconstruyan tras la actualización. Este es un proceso automatizado, pero con los límites de buzón de Outlook que normalmente se establecen en un máximo de 100 GB, volver a almacenar en caché todo el buzón local para todos los usuarios implica una gran cantidad de transferencia de datos. Para reducir la carga de red puede que quiera considerar el uso de directivas de grupo para reducir la configuración "Correo para mantener sin conexión". En Office 365 ProPlus u Office 2016 el valor predeterminado de Outlook se establece en 12 meses. Para reducir el impacto en la red considere la posibilidad configurar el almacenamiento en memoria caché para que dure de 1 a 6 meses. Cambiar esta configuración no afecta el tamaño del buzón en línea y se puede buscar todo el buzón a través de Outlook cuando tenga conexión.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**Archivos de OneDrive a petición y Mover a carpeta conocida** OneDrive es una manera excelente de sincronizar y proteger los archivos de usuario de equipos y otros dispositivos en la nube. Con Mover a carpeta conocida, puede aplicar la sincronización de archivos desde las carpetas Escritorio, Documentos e Imágenes del usuario a OneDrive, de forma que esos archivos estén disponible al iniciar sesión en un nuevo dispositivo un equipo con una nueva imagen. No obstante, debe recordar que a causa del gran tamaño y el número de archivos que se conservan en las ubicaciones de Escritorio, Documentos e Imágenes, se recomienda que planee la implementación de directivas para habilitar y exigir OneDrive en sus equipos. Una opción es usar los controles de red de directivas de grupo para limitar el ancho de banda que usa el servicio de sincronización de OneDrive.

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Configuración de Mover carpeta conocida](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[Archivos de OneDrive a petición](https://www.microsoft.com/es-ES/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Si aún no ha implementado OneDrive, el cambio de Windows 7 a Windows 10 es una oportunidad perfecta para habilitar OneDrive y se integra perfectamente con Office 365 ProPlus. Considere iniciar esta implementación mientras prepara las aplicaciones y dispositivos. Esto impulsará la sincronización de archivos antes de que empiece a mover imágenes de Windows e implementar aplicaciones a través de la red.

## <a name="next-step"></a>Paso siguiente 

## <a name="step-3-office-and-lob-app-deliveryhttpsakamsmdd3"></a>[Paso 3: Entrega de aplicaciones de Office y de LOB](https://aka.ms/mdd3)

## <a name="previous-step"></a>Paso anterior:

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[Paso 1: Preparación de dispositivos y aplicaciones](https://aka.ms/mdd1)

## <a name="feedback"></a>Comentarios

Estaremos encantados de escuchar su opinión. Elija el tipo que le gustaría ofrecer:

Inicie sesión para proporcionar comentarios sobre el producto.

El nuevo sistema comentarios está integrado en GitHub problemas. Obtenga información sobre este cambio en la entrada de blog.
