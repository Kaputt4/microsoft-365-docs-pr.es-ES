---
title: 'Introducción: Implementación de escritorios modernos'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Introducción al proceso de implementación de escritorios modernos
ms.openlocfilehash: bb5c1433554e984676884fd2bac4fa5120c76996
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871571"
---
# <a name="getting-started---modern-desktop-deployment"></a>Introducción: Implementación de escritorios modernos

La nube está cambiando la manera de administrar los equipos PC y Microsoft Intelligent Cloud proporciona información para ayudar a los profesionales de TI a cambiar a un escritorio moderno. Esta serie está diseñada para ayudarle a planificar y realizar el cambio a un escritorio moderno con Windows 10 y Office 365 ProPlus.

<img src="media/getting-started-media/getting-started-media-1.png" alt="Desktop Deployment Wheel" style="background-color: #fff;" />

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="130" width="130" /></td>
<td><p><strong>Introducción: Orientaciones sobre personas, procesos y tecnología</strong></p>
<p>Descubra las ventajas de un escritorio moderno, cambios y consideraciones clave frente a implementaciones anteriores, y los procedimientos recomendados para garantizar un transición sin problemas a Windows 10 y Office 365 ProPlus.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>En esta serie explicaremos las mejores formas de usar herramientas existentes y le presentaremos tecnologías, servicios y métodos nuevos que puede aplicar gracias a la nube. Para ver el proceso de implementación de escritorio completo, visite el [Centro de implementación de escritorios modernos](https://aka.ms/HowToShift).
>

Bienvenido al Centro de implementación de escritorios modernos, el lugar principal donde aprenderá cómo planificar y realizar el cambio a un escritorio moderno. Esto le permitirá aprovechar las ventajas de un espacio de trabajo seguro con lo último en tecnología de productividad, trabajo en equipo y colaboración.

Si lleva tiempo sin implementar ningún entorno de escritorio, la buena noticia es que se ha mejorado gran parte del proceso de implementación. Los retos del pasado, como la compatibilidad de aplicaciones ya no son un problema hoy en día y las herramientas e información que proporciona la nube le permitirán avanzar con confianza, más rápido y de forma más eficiente que antes.

En esta introducción vamos a explicar lo que ha cambiado y realizaremos un recorrido por el ciclo de implementación de escritorio. Esto le servirá de guía durante los pasos recomendados para su cambio a Windows 10 y Office 365 ProPlus, proporcionándole detalles sobre cómo aprovechar las herramientas y procesos existentes mientras adopta la tecnología y los enfoques de administración moderna.

## <a name="why-upgrade"></a>¿Por qué actualizarse?

Combinados, Windows 10 y Microsoft Intelligence Cloud mejoran su capacidad para proporcionar el espacio de trabajo más potente, enriquecido y seguro para sus usuarios y le permite simplificar su infraestructura de soporte.

Uno de los inquilinos clave de las prácticas de administración modernas es contar con dispositivos que siempre estén actualizados. Durante esta serie, comprobará las nuevas capacidades que le ayudarán a pasar a Windows 10 y Office 365 ProPlus y verá cómo estar al día de las versiones semianuales de ambos.

[Windows 10 para el profesional de TI](https://www.microsoft.com/es-ES/itpro/windows-10)

## <a name="what-has-changed"></a>¿Qué ha cambiado?

Comencemos echando un vistazo a lo que ha cambiado y mejorado desde su última implementación de escritorio. Si lleva tiempo sin cambiar de entorno de escritorio, es probable que siga usando Windows 7 y Office 2010 o 2013. En ese caso, verá que hay algunas cosas que han evolucionado desde su última actualización importante. Aquí describimos algunos de los cambios principales:

**Administración de identidades y acceso** El escritorio moderno, con su conectividad a los servicios de productividad, seguridad y administración, tiene como núcleo un servicio nuevo de administración de identidad y acceso: Azure Active Directory. Esto permite un inicio de sesión único y conectividad segura a través de sus servicios en la nube, lo que significa que necesitará contar con Azure AD. Esto le permitirá aprovechar los servicios de Microsoft 365 como Office 365, Intune o Windows Autopilot.

[Microsoft 365](https://www.microsoft.com/es-ES/microsoft-365/default.aspx)

**Proteger el entorno previo al inicio** El firmware UEFI de 64 bits sustituye a la BIOS. Esto no solo acelera el tiempo de inicio, también es necesario para habilitar muchas de las capacidades de seguridad modernas de Windows 10. Windows 10 puede ejecutarse en la BIOS, pero recomendamos encarecidamente UEFI. Si aún no ha cambiado de BIOS a UEFI y 64 bits, ahora es el momento. Hay herramientas que le ayudarán a realizar este cambio tanto durante una actualización de Windows 10 como al terminarla.

[Pasar de BIOS a UEFI con MBR2GPT](https://technet.microsoft.com/es-ES/windows/mt782786.aspx)

**Administración de dispositivos en la nube** Servicios como Microsoft Intune le permiten administrar sus dispositivos con Windows 10 igual que con otros dispositivos móviles, desde un mismo sitio. Lo que hace único a Microsoft Intune es la habilidad de coadministrar sus dispositivos con System Center Configuration Manager. Puede usar System Center Configuration Manager para cambiar a Windows 10 y, a continuación, añadir Microsoft Intune. Juntos, System Center Configuration Manager se convierte en una ventaja inteligente para su organización, conectada a la nube inteligente de Microsoft. Esto le permite administrar los dispositivos de sus usuarios de forma segura estén donde estén, tanto si están conectados a su organización como a la nube pública.

[Administración conjunta para dispositivos con Windows 10](https://docs.microsoft.com/es-ES/sccm/core/clients/manage/co-management-overview)

**Servicio de implementación en la nube** Los equipos PC que compre incluyen un nuevo servicio de nube que le ayudará a implementar dispositivos Microsoft 365. Recibe el nombre de servicio de entregas de Windows Autopilot. AutoPilot está integrado con su hardware y los nuevos equipos se registran en AutoPilot. Esto permite enviar el nuevo equipo directamente al usuario final. Al iniciar el equipo por primera vez, se configura con rapidez según la configuración deseada y personalizada para seguir las necesidades específicas del usuario.

[Windows Autopilot](https://www.microsoft.com/es-ES/windowsforbusiness/windows-autopilot)

**Hacer clic y ejecutar implementaciones** Al aprovisionar aplicaciones de escritorio de Office, Office 365 ProPlus es la opción preferida. Esto le otorga acceso a las innovaciones más modernas en Office conforme son desarrolladas, por lo que no tendrá que esperar años hasta obtener algo nuevo. También usará un sistema de instalación denominado Hacer clic y ejecutar (Click-to-Run).

Hacer clic y ejecutar es muy diferente de los antiguos paquetes basados en MSI. Es más rápido, más ligero y usa transmisión de programas para permitir a los usuarios tenerlo todo listo en apenas unos minutos, además de actualizarse en segundo plano. No se preocupe, sigue siendo una copia local de Office y puede seguir usando sus herramientas de implementación existentes (como System Center Configuration Manager) para aprovisionar y configurar las aplicaciones.

[Guía de implementación de Office 365 ProPlus](https://docs.microsoft.com/es-ES/DeployOffice/deployment-guide-for-office-365-proplus)

**Actualizaciones semestrales** Una vez que se haya pasado a Windows 10 y Office 365 ProPlus, las actualizaciones con nuevas características se realizarán de forma semestral. Pero con Microsoft y su capacidad de proporcionar información de la nube para ayudarle, podrá aplicar estas actualizaciones con rapidez y seguridad a cientos o miles de dispositivos. Como una actualización local, las actualizaciones de características conservan las aplicaciones, los datos y la configuración de la versión anterior.

## <a name="the-deployment-process-wheel"></a>El ciclo de proceso de implementación

Antes de empezar, querrá crear un plan de alto nivel y convencer a los patrocinadores necesarios. Nuestro ciclo de proceso de desarrollo describe los pasos críticos para ayudarle a identificar a los miembros y los recursos centrales del equipo que debe administrar en las siguientes áreas de implementación.

**[Paso 1: Preparación de dispositivos y aplicaciones](https://aka.ms/mdd1)** Para poder realizar una implementación con éxito debe saber antes con qué cuenta. Esto significa realizar un inventario de sus dispositivos y aplicaciones y verificar su compatibilidad.

Para ayudarle con esto, cuenta con herramientas disponibles en nuestro servicio en la nube, Windows Analytics. Windows Analytics le permite consultar la información de compatibilidad y telemetría recopilada de cientos de millones de PC para valorar las aplicaciones y controladores que se ejecutan en su dispositivo, lo que le permite establecer el estado de preparación del estado de su escritorio. Incluso puede exportar una lista de "PC listos para la implementación" de Windows Analytics a System Center Configuration Manager si lo usa, lo que le permite implementar colecciones basadas en datos de los equipos PC de destino en cuanto están disponibles.

[Empezar con Upgrade Readiness](https://docs.microsoft.com/es-ES/windows/deployment/upgrade/upgrade-readiness-get-started)

**[Paso 2: Preparación de los directorios y la red](https://aka.ms/mdd2)** A continuación, si aún no lo ha hecho, querrá implementar Azure Active Directory para la administración de acceso e identidad. También deberá preparar su red para el movimiento de imágenes de sistema, paquetes de aplicaciones, archivos de usuario y actualizaciones. Esto significa una gran cantidad de datos adicionales que su red debe poder gestionar sin que afecte al trabajo diario de su organización. Tenemos una amplia gama de optimizaciones disponibles, desde la aceleración de la banda ancha y las opciones de punto a punto, al aprovechamiento de banda ancha dinámica y diferencial.

[Windows BranchCache frente a caché del mismo nivel](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**[Paso 3: Entrega de aplicaciones de Office y de línea de negocio](https://aka.ms/mdd3)** Mientras Windows sigue siendo compatible con instalaciones basadas en MSI, ahora también lo es con nuevos mecanismos de instalación, optimizados para la implementación automatizada y las actualizaciones continuas. Los clientes de Office 365 ProPlus y Windows 2019 utilizan la tecnología Hacer clic y ejecutar, por lo que puede que desee tener a su disposición una variedad de aplicaciones UWP, y puede que cada vez necesite implementar más aplicaciones de terceros y de línea de negocio desarrolladas externamente que usan las nuevas aplicaciones basadas en MSIX. Este paso asegura que las aplicaciones estén listas para implementaciones automatizadas y que usted esté preparado para el éxito tanto si sus aplicaciones se instalan con Hacer clic y ejecutar, MSIX, MSI tradicional, como si se trata de aplicaciones UWP implementadas de una Microsoft Store de negocios que ha establecido.

[MSIX Intro](https://blogs.msdn.microsoft.com/sgern/2018/06/15/msix-intro/)

**[Paso 4: Migración de los archivos y la configuración del usuario](https://aka.ms/mdd4)** Este es un paso crítico en cualquier sustitución de PC o ciclo de actualización: tiene que asegurarse de que los archivos, datos y configuración de los usuarios se trasladan con éxito y se preservan durante la migración. Este paso cubre las opciones disponibles para migraciones manuales o automatizadas, incluyendo opciones conocidas y nuevas.

Al igual que en actualizaciones anteriores, la Herramienta de migración de estado de usuario sigue siendo valiosa en este proceso y es una parte integral de las migraciones preparadas con System Center Configuration Manager o el kit de Microsoft Deployment. Pero, en ocasiones, trasladar todos estos datos durante una migración puede formar cuello de botella para el equipo PC sustituto debido a las físicas involucradas en la transferencia de cientos de gigabytes por PC en dos ocasiones: primero, desde el escritorio existente y luego de vuelta al escritorio nuevo. Una nueva opción activada por OneDrive se trata de Movimiento de carpeta conocida cuyo objetivo es sincronizar, documentos de usuario, fotografías y archivos de fondo. A escala, en la nube, por delante de los pagos.

[Redirigir y mover las carpetas conocidas de Windows a OneDrive](https://docs.microsoft.com/es-ES/onedrive/redirect-known-folders)

**[Paso 5: Seguridad y cumplimiento](https://aka.ms/mdd5)** El área de seguridad y cumplimiento tiene muchas ventajas a la hora de trasladarse a Windows 10 y Office 365 ProPlus. Es importante que se familiarice con las nuevas características integradas y las compare con lo que ya tiene. Por ejemplo, las nuevas capacidades de Windows 10 con seguridad basada en virtualización pueden evitar el robo de credenciales, proteger contra vulnerabilidades del navegador y la ejecución de código malicioso al aislar los procesos principales y secretos del sistema operativo. Además, los servicios de la nube como Advanced Threat Protection proporcionan una plataforma unificada para fortalecimiento de la seguridad, detección de incursiones, investigación y respuesta. Advanced Threat Protection también puede protegerle contra archivos adjuntos de correo, hipervínculos poco seguros y mucho más.

[Microsoft Security](https://www.microsoft.com/es-ES/security/default.aspx)

**[Paso 6: Implementación del sistema operativo y actualizaciones de características](https://aka.ms/mdd6)** Con todo preparado, el siguiente paso consiste en implementar las imágenes del sistema operativo. Gran parte del trabajo puede realizarse con la infraestructura y las secuencias de tareas de System Center Configuration Manager. La estrategia recomendada consiste en realizar un despliegue por fases, primero con la implementación en un "grupo preferente" de su organización que disponga del mismo conjunto representativo de hardware y aplicaciones. Después, puede usar los datos de esos dispositivos y usuarios para realizar la implementación en más PC.

[Introducción a la implementación de un sistema operativo en System Center Configuration Manager](https://docs.microsoft.com/es-ES/sccm/osd/understand/introduction-to-operating-system-deployment)

**[Paso 7: Windows y Office como servicio](https://aka.ms/mdd7)** Esto representa un cambio importante en la forma en la que mantiene el escritorio. Con este movimiento de Windows 10 (-y Office 365 ProPlus) puede pasar a administrar Windows (y Office) como un servicio. En vez de un enorme intercambio de tecnología cada pocos años, seguirá aportando nuevas capacidades, experiencias y protección al usuario. Las actualizaciones importantes semestrales se implementarán en otoño y primavera de cada año, mientras que las actualizaciones de calidad contendrán seguridad, confianza y corrección de errores. Aunque puede desplegar clientes de Office 2019, recomendamos que se pase a Office ProPlus. Sigue un plan de servicio parecido para Windows, por lo que sus usuarios recibirán aplicaciones para las aplicaciones de Office con regularidad.

![](media/getting-started-media/getting-started-media-2.png)

[Información general sobre Windows como servicio](https://docs.microsoft.com/es-ES/windows/deployment/update/waas-overview)

**[Paso 8: Comunicación con los usuarios y aprendizaje](https://aka.ms/mdd8)** Este último paso es crítico para impulsar el uso de nuevas capacidades para mejorar el trabajo en equipo, las comunicaciones, la seguridad y demás. Antes de que la implementación principal se lleve a usuarios fuera del grupo inicial, le recomendamos iniciar las comunicaciones de usuario y la formación. Esto ayudará a impulsar los cambios deseados en el uso que realicen los usuarios de las nuevas capacidades de Office, Windows y otras aplicaciones y servicios de línea de negocios. Para apoyarle, proporcionamos formación gratuita en línea a través de Microsoft FastTrack. Además, hemos publicado una muestra gratuita de planes de comunicación y líneas de tiempo junto a plantillas de correo, sociales y de intranet para ayudarle con su despliegue de Windows 10. Además, como organización de Microsoft 365 o de Office 365, su organización puede recurrir al soporte directo.

## <a name="next-step"></a>Paso siguiente

Ahora conoce las novedades y le hemos mostrado nuestro proceso de implementación recomendado. Con esta introducción como guía y las herramientas disponibles para realizar el cambio a un escritorio moderno, pongámonos manos a la obra.

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[Paso 1: Preparación de dispositivos y aplicaciones](https://aka.ms/mdd1)

