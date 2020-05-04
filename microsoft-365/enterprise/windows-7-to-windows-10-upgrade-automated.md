---
title: Actualizaciones automatizadas de Windows 7 a Windows 10
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 07/01/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Actualizaciones automatizadas de Windows 7 a Windows 10 para grandes empresas
ms.openlocfilehash: 575ffba84b2cd7b7cfe5267a35a9f36c75dbe306
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011556"
---
# <a name="windows-7-to-windows-10-automated-in-place-upgrades-for-large-organizations"></a>Actualizaciones locales automatizadas de Windows 7 a Windows 10 para grandes empresas

Desde el 14 de enero de 2020, ya no se proporcionan actualizaciones de seguridad ni soporte técnico para equipos PC que ejecutan Windows 7. Para pasar de Windows 7 a Windows 10 con varias opciones para implementar, una de las preguntas más frecuentes en la comunidad de TI es la manera más rápida de pasar de Windows 7 a Windows 10. La respuesta es llevar a cabo actualizaciones locales para equipos existentes para puede reducir el enfoque en varios aspectos del proceso de implementación de escritorio.

<center><img src="../media/windows-7-to-windows-10-upgrade-automated-media/windows-7-to-windows-10-upgrade-automated-media-1.png" alt="wheel" height="421" width="500" /></center>

Al usar las actualizaciones locales, se reduce considerablemente el ámbito de varios procesos de implementación de escritorio, especialmente:

  - **El empaquetado de aplicaciones** y reentrega de aplicaciones de línea de negocio necesarias: simplemente se realizan a partir del entorno de Windows 7.

  - **La migración de archivos** y la configuración de usuario básica: también se realizan a partir la instalación anterior cuando el mismo usuario conserva el dispositivo.

Las tareas atenuadas en el gráfico de la rueda del proceso de implementación anterior no son elementos que se pueden ignorar completamente, pero para ahorrar tiempo se presupone que llevará a cabo la configuración de seguridad y cambiará los procesos de actualización de software después de la implementación. Suponemos que la formación de usuarios para el componente de Windows se ha producido en gran medida en casa para los usuarios, ya que los equipos con Windows que se adquirieron de forma privada desde 2012, en la mayoría de los casos, no tenía Windows 7 precargado y desde el lanzamiento de Windows 10, en 2015, la mayoría de los sistemas domésticos de Windows 7 también se han actualizado a Windows 10.

## <a name="in-place-upgrade-reliability-safeguards-and-scale"></a>Confiabilidad, elementos de protección y escala de la actualización local

Las actualizaciones locales a Windows 10 son un método confiable para mover un dispositivo existente que ejecuta Windows 7 o posterior a Windows 10, sin requerir la migración de archivos o la reinstalación de aplicaciones. Después de una actualización local, los archivos, las opciones de configuración y las aplicaciones disponibles del usuario son coherentes con la instalación de Windows 7 anterior. Las actualizaciones también funcionan desde arquitecturas similares (de 32 bits a 32 bits o de 64 bits a 64 bits) y versiones similares de Windows (de Professional a Pro o de Enterprise a Enterprise).

De forma predeterminada, el proceso de actualización realiza una copia de seguridad de la instalación anterior de Windows como parte de la actualización, por lo que en caso de que se produzca un error de actualización o en caso de que una aplicación o un dispositivo no funcione correctamente después de la actualización, el equipo puede revertir a Windows 7. De forma predeterminada, los equipos actualizados tienen 10 días para que pueda revertir manualmente a Windows 7, si es necesario.

Las actualizaciones locales se pueden automatizar con herramientas de implementación de sistema operativo, como [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) o [Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit). En este artículo, se resaltan los métodos y las optimizaciones automatizadas, así como los vínculos a recursos relacionados para obtener ayuda adicional.

## <a name="upgrading-a-small-number-of-computers"></a>Actualizar un número reducido de equipos

Para un único equipo o un número reducido de equipos, el método manual para la actualización es generalmente la mejor opción en comparación con los métodos más automatizados. Puede encontrar el software y las licencias necesarios en [Microsoft Store](https://go.microsoft.com/fwlink/p/?LinkId=808282), en otros proveedores de software o en el [Centro de servicios de licencias por volumen](https://www.microsoft.com/licensing/servicecenter/default.aspx), si tiene licencias por volumen. Para obtener instrucciones detalladas sobre cómo actualizar un único equipo a Windows 10, así como las opciones de restauración posteriores a la actualización, vea la [Guía paso a paso de la actualización manual de Windows 7 a Windows 10](https://docs.microsoft.com/microsoft-365/enterprise/windows-7-to-windows-10-upgrade).

## <a name="how-to-upgrade-many-computers"></a>Cómo actualizar muchos equipos

Si administra decenas o miles de equipos, la mejor opción es llevar a cabo actualizaciones locales con la automatización de la secuencia de tareas con Microsoft Endpoint Configuration Manager o Microsoft Deployment Toolkit. Aunque el proceso es muy confiable en la mayoría de los casos, en función del número de equipos que se actualizan, aún tiene sentido contar con las pruebas y controles necesarios para asegurar el éxito a escala.

Esto quiere decir que puede omitir la preparación del directorio o las tareas asociadas con Azure Active Directory, Office, la entrega y empaquetado de aplicaciones de línea de negocio y la migración de los archivos de usuario, ya que estos aspectos se conservan como parte de la actualización y al menos se debe llevar adelante la seguridad. Todas estas áreas se pueden mejorar a lo largo del tiempo.

La opción de implementación de actualización se cubre en [Actualizaciones de características e implementación del sistema operativo](https://www.aka.ms/mdd6) y, aunque puede crear fácilmente soluciones con scripts que ejecuten el programa de instalación de Windows 10 de manera automatizada con mínima o ninguna interacción de administrador, una secuencia de tareas le proporcionará un control más granular para:

  - Realizar comprobaciones previas a la implementación,

  - Administrar el estado de cifrado de unidad antes de la actualización,

  - Desinstalar controladores y aplicaciones problemáticas conocidos antes de la actualización,

  - Instalar controladores y aplicaciones adicionales después de la actualización,

  - Administrar el estado de cifrado de unidad después de la actualización,

  - Restaurar un equipo a un estado anterior, donde se reinstalan las aplicaciones o los controladores desinstalados (en caso de que se produzca un error en la actualización),

  - Además de todo lo que necesite configurar para que esté todo listo

![](../media/windows-7-to-windows-10-upgrade-automated-media/windows-7-to-windows-10-upgrade-automated-media-2.png)

Las razones más comunes por las que las actualizaciones no se completan o no se pueden llevar a cabo son problemas relacionados con:

  - Controladores de dispositivos obsoletos

  - Cifrado de disco de <sup>terceros</sup>

  - Soluciones de código de bajo nivel, como antimalware, VPN o virtualización

Las plantillas de [Secuencia de tareas para actualización](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system) están integradas en la rama actual de Microsoft Endpoint Configuration Manager y han estado disponibles para varias versiones. En las versiones más recientes se han producido mejoras tecnológicas considerables para Configuration Manager que hacen que el proceso sea aún más eficaz para determinar la preparación de la compatibilidad de dispositivos y de Office, reducir el tráfico de red y configurar nuevas opciones como la copia de seguridad de OneDrive. Vea este [programa de Microsoft Mechanics](https://youtu.be/CYRnAmCD7ls) para obtener más información sobre las actualizaciones más recientes de la implementación de sistema operativo de Configuration Manager.

Si no usa Microsoft Endpoint Configuration Manager, puede usar Microsoft Deployment Toolkit para crear y ejecutar secuencias de tareas de implementación de actualización.

## <a name="pre-cache-task-sequence-upgrades"></a>Almacenar en caché previamente actualizaciones de secuencia de tareas

La [opción de almacenar en caché previamente](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system#configure-pre-cache-content) de la secuencia de tareas de implementación de Configuration Manager permite a los clientes descargar contenido de paquetes de actualización del sistema operativo relevante antes de que la secuencia de tareas actualice el mismo. Anteriormente, al iniciar la secuencia de tareas se iniciaba la descarga del contenido del paquete. El contenido almacenado en caché previamente también ofrece la opción de que el cliente solo pueda descargar el paquete de actualización del sistema operativo disponible y descargar el resto del contenido al que se hace referencia en cuanto reciba la implementación.

Almacenar en caché previamente secuencias de tareas combinadas con los exámenes de compatibilidad

Además de ahorrar tiempo para la descarga del paquete, puede almacenar en caché previamente el paquete de actualización y usar el programa de instalación de Windows para evaluar si la actualización local se realizará correctamente antes de ejecutar la actualización de Windows real. La siguiente sintaxis de línea de comandos puede usarse para ejecutar de forma silenciosa un examen de compatibilidad y averiguar si el programa de instalación de Windows considera que el dispositivo está listo para la actualización.

Luego, se enviarán los registros a la ruta de acceso del servidor definida y el programa de instalación de Windows no se mostrará al usuario y se cerrará sin la intervención del mismo.

Los resultados de los registros en sí serán:

1.  Si el programa de instalación no encuentra problemas de compatibilidad y parece que el equipo cumple todos los requisitos, devolverá MOSETUP\_E\_COMPAT\_SCANONLY (0xC1900210)

2.  Si el programa de instalación encuentra problemas de compatibilidad, como aplicaciones incompatibles, devolverá MOSETUP\_E\_COMPAT\_INSTALLREQ\_BLOCK (0xC1900208)

3.  Si el programa de instalación encuentra que el equipo no es apto para Windows 10, devolverá MOSETUP\_E\_COMPAT\_SYSREQ\_BLOCK (0xC1900200)

4.  Si el programa de instalación encuentra que el equipo no tiene suficiente espacio libre para la instalación, devolverá MOSETUP\_E\_INSTALLDISKSPACE\_BLOCK (0xC190020E)

Una vez que haya implementado las secuencias almacenadas en caché previamente con los exámenes de compatibilidad en un gran número de equipos de una colección, puede empezar a analizar los archivos de registro para la preparación del dispositivo. Al usar las salidas enumeradas anteriormente, \#1 (0xC1900210) puede accionarse como "listo para implementar" y \#4 (0xC190020E) puede accionarse liberando espacio en el disco. Aquí, deberá tener cuidado con el contenido que quiere eliminar, pero puede empezar con la Limpieza de actualizaciones de Windows, la Papelera de reciclaje y los Archivos temporales que, en muchos casos, le proporcionarán suficiente espacio para una correcta actualización. Puede ejecutar el examen de compatibilidad tan a menudo como sea necesario hasta que el equipo esté listo para la actualización local. Puede encontrar más información sobre las opciones de línea de comandos del programa de instalación de Windows en <https://aka.ms/setupswitches>

## <a name="desktop-deployment-center"></a>[Centro de implementación de escritorio](https://aka.ms/howtoshift)
