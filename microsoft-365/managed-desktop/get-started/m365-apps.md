---
title: Aplicaciones de Microsoft 365 para empresas
description: Cómo implementar Aplicaciones Microsoft 365, cómo se actualizan y cómo se administra la configuración
keywords: historial de cambios
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 45064584b622c313fee66c0699ab6495353342edad39948e8f8dabcd68911547
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53807197"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

## <a name="initial-deployment"></a>Implementación inicial

Escritorio administrado de Microsoft garantiza que Aplicaciones Microsoft 365 para empresas (64 bits) se instalen como parte de la imagen en todos los [dispositivos del programa](../service-description/device-list.md). Todas las aplicaciones siguientes deben estar presentes en el dispositivo cuando se entregue:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Acceso
- Skype Empresarial
- OneNote

Este enfoque minimiza el impacto en la red y garantiza que los usuarios puedan ser productivos tan pronto como reciban su dispositivo. A continuación, implementamos más directivas en dispositivos administrados para configurar las aplicaciones para su uso.

> [!NOTE]
> Microsoft Teams se implementa independientemente de Aplicaciones Microsoft 365 para empresas y no se incluye en la imagen base. 

### <a name="available-deployment-to-users"></a>Implementación disponible para los usuarios

Si un usuario no tiene Aplicaciones Microsoft 365 en su dispositivo por cualquier motivo, puedes usar un paquete para devolver el dispositivo a su estado esperado. Agrega al usuario al grupo **Modern Workplace-Office-Office365_Install y** las aplicaciones estarán disponibles en el Portal de empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Aplicaciones Microsoft 365 para empresas (32 bits)

Escritorio administrado de Microsoft no admite la implementación de la versión de 32 bits de M365 Apps para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Actualizaciones de Aplicaciones Microsoft 365

Aplicaciones Microsoft 365 se establecen para actualizarse en el canal [de Enterprise mensual](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Esta práctica proporciona a los usuarios nuevas características Office cada mes, pero solo recibirán una actualización al mes en una programación de lanzamiento predecible. Las actualizaciones se lanzan el segundo martes del mes; estas actualizaciones pueden incluir actualizaciones de características, seguridad y calidad. Estas actualizaciones se producen automáticamente y se sacan directamente del Office CDN para ese canal específico.

Escritorio administrado de Microsoft escalona cada versión para identificar posibles problemas en el entorno. Completamos el lanzamiento 28 días después de la versión del grupo de productos Microsoft 365 app. Escritorio administrado de Microsoft programa las versiones de actualización a diferentes grupos para permitir el tiempo de validación y pruebas de la siguiente manera: 

- Prueba: cero días
- Primero: cero días
- Rápido: 3 días
- Ancho: 7 días

Escritorio administrado de Microsoft establece una fecha límite de actualización de siete [días](/deployoffice/configure-update-settings-microsoft-365-apps) para dispositivos. Una vez que la actualización está disponible, debe instalarse en un plazo de siete días. Se [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) notifica a los usuarios que las actualizaciones son necesarias en varias ubicaciones: la aplicación, en la bandeja del sistema 12 horas antes de la fecha límite, y reciben una advertencia de 15 minutos antes de la fecha límite. Todos los Aplicaciones Microsoft 365 deben cerrarse para que se complete la actualización.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar o revertir una actualización

Si necesitas pausar o revertir la actualización Microsoft 365 la aplicación por cualquier motivo, haz una solicitud de soporte técnico para [administradores](../working-with-managed-desktop/admin-support.md) a través del portal Escritorio administrado de Microsoft web.

Durante una versión, Escritorio administrado de Microsoft las tasas de error de todos los Aplicaciones Microsoft 365. Si observamos una diferencia significativa en la calidad entre la nueva versión y su predecesora, podríamos ponerse en contacto con usted a través del portal de administración Escritorio administrado de Microsoft administración. Dependiendo de la gravedad, le preguntaremos si desea pausar la versión o le informaremos de que hemos tomado medidas para mitigar un problema. 

### <a name="delivery-optimization"></a>Optimización de distribución

Optimización de distribución es una tecnología de distribución punto a punto disponible en Windows 10. Permite a los dispositivos compartir contenido, como las actualizaciones, que los dispositivos han descargado de Microsoft a través de Internet. Su uso puede ayudar a reducir el ancho de banda de red porque un dispositivo puede obtener partes de la actualización de otro dispositivo en su red local en lugar de tener que descargar la actualización por completo de Microsoft.

[Optimización de](/deployoffice/delivery-optimization) entrega está habilitada de forma predeterminada en dispositivos que ejecutan Windows 10 Enterprise o Windows 10 Education ediciones. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrado por Escritorio administrado de Microsoft

Microsoft administra algunas opciones de configuración como parte del servicio. Escritorio administrado de Microsoft no administra una línea base de seguridad Office, pero puede establecerla usted mismo siguiendo las instrucciones de la [sección Configuración administrar.](#settings-you-manage)

### <a name="update-settings"></a>Actualizar configuración

Escritorio administrado de Microsoft mantiene toda la configuración [de actualización para](/deployoffice/configure-update-settings-microsoft-365-apps) dispositivos administrados y debe modificar esta configuración.

### <a name="set-updates-to-occur-automatically"></a>Establecer actualizaciones para que se produzcan automáticamente

**Valor predeterminado:** Habilitado

Esta directiva se configura para garantizar que todos los Office se puedan mantener actualizados desde la nube. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Establecer una fecha límite cuando deben aplicarse las actualizaciones

**Valor predeterminado:** 7 días

La **directiva UpdateDeadline** se usa para configurar el período de gracia que tienen los usuarios antes de que se aplique una actualización en el dispositivo. Esta directiva de fecha límite también desencadena [notificaciones](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) al usuario para informarle de los cambios necesarios en su dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Aplazar actualizaciones en un dispositivo durante un período

Esta directiva se configura de forma diferente para cada grupo de dispositivos de administración de actualizaciones y es necesaria para que Escritorio administrado de Microsoft cumpla sus objetivos de actualización:  

- Prueba: cero días
- Primero: cero días
- Rápido 7 días
- Ancho: 21 días

### <a name="update-notifications-settings"></a>Actualizar la configuración de notificaciones

**Valor predeterminado**: False

La configuración "ocultar notificaciones de actualización" se establece en **False** en Escritorio administrado de Microsoft dispositivos para proporcionar la mejor experiencia de actualización para los usuarios notificándolos cuando se requieren actualizaciones. [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)

### <a name="specify-a-location-to-look-for-updates"></a>Especificar una ubicación para buscar actualizaciones

**Valor predeterminado:** Canal de Enterprise mensual

Se usa una combinación de **las directivas UpdatePath** y **UpdateChannel** según sea necesario para lograr la programación de actualización. Estas directivas se establecen para garantizar que todos los dispositivos Office reciban actualizaciones directamente desde el CDN del canal de Enterprise mensual.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Especifique la versión de destino de Aplicaciones Microsoft 365

La directiva versión de destino a veces se usa Escritorio administrado de Microsoft para revertir o anclar una versión específica de Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ocultar la opción para habilitar o deshabilitar Office actualizaciones automáticas

**Valor predeterminado:** Habilitado

Esta configuración es necesaria para que Escritorio administrado de Microsoft sus objetivos de actualización para Microsoft 365 aplicaciones. 

### <a name="first-run-settings"></a>Configuración de la primera ejecución 

Hay varias opciones de configuración que afectan al comportamiento la primera vez que Office se ejecuta.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Aceptar los términos de licencia en nombre del usuario final

**Valor predeterminado**: Deshabilitado

La primera vez que un usuario abre una Microsoft 365, se le pedirá que acepte los términos de licencia. Si desea aceptar los términos de licencia en nombre de los usuarios, presente una solicitud de servicio al equipo de operaciones de Escritorio administrado de Microsoft solicitando que esta configuración esté habilitada. 

### <a name="suppress-outlook-mobile-check-box"></a>Suprimir Outlook casilla móvil

**Valor predeterminado**: Deshabilitado

La primera vez que se abre un Outlook se le pedirá que instale Outlook Móvil. Si no desea que los usuarios vean esa casilla, presente una solicitud de servicio al equipo de operaciones de Escritorio administrado de Microsoft solicitando que esta configuración esté habilitada para los dispositivos. 

## <a name="other-settings"></a>Otras opciones de configuración

Hay otras opciones Microsoft 365 de la aplicación que Escritorio administrado de Microsoft configurar opcionalmente en su nombre. 

### <a name="disable-personal-onedrive"></a>Deshabilitar personal OneDrive

**Valor predeterminado**: Deshabilitado

Algunas organizaciones están preocupadas por que los usuarios tengan acceso a archivos corporativos y personales en sus dispositivos. Puede presentar una solicitud de servicio con el equipo de Escritorio administrado de Microsoft operations que solicita que se habilite esta configuración. 

## <a name="settings-you-manage"></a>Configuración administrar

Hay muchas otras directivas que Escritorio administrado de Microsoft aún no se establecen como parte de nuestro servicio. Puede configurar estas directivas mediante el Microsoft Intune, que usa el [Office de directivas en la](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) nube. Para establecer estas directivas, siga estos pasos:

1. Inicie sesión en el centro Microsoft Endpoint Manager administración.
2. Selecciona **Aplicaciones > directivas para Office aplicaciones > Crear**
3. En la **página Crear configuración** de directiva, haga lo siguiente:
    - Escriba un nombre.
    - Proporcione una descripción (opcional).
    - En **las asignaciones,** elija si esta directiva se aplica a todos los usuarios de Aplicaciones Microsoft 365 para empresas, o simplemente a los usuarios que acceden de forma anónima a documentos mediante Office para la Web.
    - Seleccione el grupo de seguridad basado en AAD que está asignado a la configuración de directiva. Cada configuración de directiva solo se puede asignar a un grupo y solo se puede asignar una configuración de directiva a cada grupo.
    - Configure las opciones de directiva para que se incluyan en la configuración de directiva. Puede buscar en el nombre de configuración de directiva para buscar la configuración de directiva que desea configurar. También puede filtrar en la aplicación, en si la directiva es una línea base de seguridad recomendada y en si la directiva se ha configurado. La columna de plataforma indica si la directiva se aplica a Aplicaciones Microsoft 365 para empresas para Windows dispositivos, Office para la Web o todos.
4. Después de realizar las selecciones, elija **Crear**.

> [!NOTE]
> Office Las directivas de configuración solo admiten la implementación basada en usuarios
