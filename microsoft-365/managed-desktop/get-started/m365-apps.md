---
title: Aplicaciones de Microsoft 365 para empresas
description: Cómo implementar Aplicaciones de Microsoft 365, cómo se actualizan y cómo se administra la configuración
keywords: historial de cambios
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840354"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

## <a name="initial-deployment"></a>Implementación inicial

Escritorio administrado de Microsoft garantiza que las Aplicaciones de Microsoft 365 para empresas (64 bits) estén instaladas como parte de la imagen en todos los dispositivos [del programa.](../service-description/device-list.md) Todas las aplicaciones siguientes deben estar presentes en el dispositivo cuando se entregue:

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
> Microsoft Teams se implementa independientemente de Aplicaciones de Microsoft 365 para empresas y no se incluye en la imagen base. 

### <a name="available-deployment-to-users"></a>Implementación disponible para los usuarios

Si un usuario no tiene Aplicaciones de Microsoft 365 en su dispositivo por cualquier motivo, puede usar un paquete para devolver el dispositivo a su estado esperado. Agregue el usuario al grupo **Modern Workplace-Office-Office365_Install** y las aplicaciones estarán disponibles en el Portal de empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Aplicaciones de Microsoft 365 para empresas (32 bits)

Escritorio administrado de Microsoft no admite la implementación de la versión de 32 bits de M365 Apps para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Actualizaciones de aplicaciones de Microsoft 365

Las Aplicaciones de Microsoft 365 están configuradas para actualizarse en el Canal [empresarial mensual.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview) Este procedimiento proporciona a los usuarios nuevas características de Office cada mes, pero recibirán solo una actualización al mes en una programación de lanzamiento predecible. Las actualizaciones se lanzan el segundo martes del mes; estas actualizaciones pueden incluir actualizaciones de características, seguridad y calidad. Estas actualizaciones se producen automáticamente y se extran directamente de la red CDN de Office para ese canal específico.

Escritorio administrado de Microsoft escalona cada versión para identificar posibles problemas en tu entorno. Completamos el lanzamiento 28 días después del lanzamiento del grupo de productos de aplicaciones de Microsoft 365. Escritorio administrado de Microsoft programa las versiones de actualización a diferentes grupos para permitir tiempo para la validación y las pruebas de la siguiente manera: 

- Prueba: cero días
- Primero: cero días
- Rápido: 7 días
- Amplia: 21 días

Escritorio administrado de Microsoft establece una fecha límite de actualización de siete [días](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) para los dispositivos. Una vez que la actualización esté disponible, debe instalarse en un plazo de siete días. Se [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) notifica a los usuarios que las actualizaciones son necesarias en varias ubicaciones: la aplicación, en la bandeja del sistema 12 horas antes de la fecha límite, y reciben una advertencia de 15 minutos antes de la fecha límite. Todas las Aplicaciones de Microsoft 365 deben cerrarse para que se complete la actualización.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar o revertir una actualización

Si necesita pausar o revertir la actualización de la aplicación [](../working-with-managed-desktop/admin-support.md) de Microsoft 365 por cualquier motivo, presentar una solicitud de soporte técnico para administradores a través del portal de Escritorio administrado de Microsoft.

Durante una versión, Escritorio administrado de Microsoft supervisa las tasas de error de todas las Aplicaciones de Microsoft 365. Si observamos una diferencia significativa en la calidad entre la nueva versión y su predecesora, es posible que nos comunicaremos con usted a través del portal de administración de escritorio administrado de Microsoft. Dependiendo de la gravedad, preguntaremos si desea pausar la versión o le informaremos de que hemos tomado medidas para mitigar un problema. 

### <a name="delivery-optimization"></a>Optimización de distribución

Optimización de distribución es una tecnología de distribución punto a punto disponible en Windows 10. Permite a los dispositivos compartir contenido, como las actualizaciones, que los dispositivos han descargado de Microsoft a través de Internet. Su uso puede ayudar a reducir el ancho de banda de red porque un dispositivo puede obtener partes de la actualización de otro dispositivo en su red local en lugar de tener que descargar la actualización completamente desde Microsoft.

[Optimización de](https://docs.microsoft.com/deployoffice/delivery-optimization) distribución está habilitada de forma predeterminada en dispositivos que ejecutan las ediciones Windows 10 Enterprise o Windows 10 Education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrada por Escritorio administrado de Microsoft

Microsoft administra algunas opciones de configuración como parte del servicio. Escritorio administrado de Microsoft no administra una línea base de seguridad de Office, pero puede establecer una usted mismo siguiendo las instrucciones de la sección [Configuración que administra.](#settings-you-manage)

### <a name="update-settings"></a>Actualizar configuración

Escritorio administrado de Microsoft mantiene toda la [configuración de actualización](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) para dispositivos administrados y debe modificar esta configuración.

### <a name="set-updates-to-occur-automatically"></a>Establecer actualizaciones para que se produzcan automáticamente

**Valor predeterminado:** Habilitado

Esta directiva se configura para garantizar que todos los dispositivos de Office se puedan mantener actualizados desde la nube. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Establecer una fecha límite cuando se deba aplicar las actualizaciones

**Valor predeterminado:** 7 días

La **directiva UpdateDeadline** se usa para configurar el período de gracia que tienen los usuarios antes de aplicar una actualización en el dispositivo. Esta directiva de fecha límite también desencadena [notificaciones](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) al usuario para informarle de los cambios necesarios en su dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Aplazar actualizaciones en un dispositivo durante un período de tiempo

Esta directiva se configura de forma diferente para cada grupo de dispositivos de administración de actualizaciones y es necesaria para que el Escritorio administrado de Microsoft cumpla sus objetivos de actualización:  

- Prueba: cero días
- Primero: cero días
- 7 días de rapidez
- Amplia: 21 días

### <a name="update-notifications-settings"></a>Actualizar la configuración de notificaciones

**Valor predeterminado:** False

La opción "ocultar notificaciones de actualización" se establece en **False** en los [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dispositivos de Escritorio administrado de Microsoft para proporcionar la mejor experiencia de actualización a los usuarios notificándolos cuando se necesitan actualizaciones.

### <a name="specify-a-location-to-look-for-updates"></a>Especificar una ubicación para buscar actualizaciones

**Valor predeterminado:** Canal empresarial mensual

Se usa una combinación **de las directivas UpdatePath** y **UpdateChannel** según sea necesario para lograr la programación de actualizaciones. Estas directivas se establecen para garantizar que todos los dispositivos de Office reciban actualizaciones directamente de la red CDN para el canal empresarial mensual.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Especificar la versión de destino de aplicaciones de Microsoft 365

A veces, el Escritorio administrado de Microsoft usa la directiva de versión de destino para revertir o anclar una versión específica de Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ocultar la opción para habilitar o deshabilitar las actualizaciones automáticas de Office

**Valor predeterminado:** Habilitado

Esta configuración es necesaria para que el Escritorio administrado de Microsoft cumpla sus objetivos de actualización para aplicaciones de Microsoft 365. 

### <a name="first-run-settings"></a>Configuración de la primera ejecución 

Hay varias opciones de configuración que afectan al comportamiento la primera vez que se ejecuta Office.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Aceptar los términos de licencia en nombre del usuario final

**Valor predeterminado:** Deshabilitado

La primera vez que un usuario abre una aplicación de Microsoft 365, se le pide que acepte los términos de licencia. Si desea aceptar los términos de licencia en nombre de los usuarios, presente una solicitud de servicio al equipo de operaciones de escritorio administrado de Microsoft solicitando que se habilite esta opción. 

### <a name="suppress-outlook-mobile-check-box"></a>Suprimir la casilla de verificación de Outlook Mobile

**Valor predeterminado:** Deshabilitado

La primera vez que un usuario abre Outlook se le pide que instale Outlook Mobile. Si no desea que los usuarios vean esa casilla, presente una solicitud de servicio al equipo de operaciones de escritorio administrado de Microsoft solicitando que esta configuración esté habilitada para sus dispositivos. 

## <a name="other-settings"></a>Otras opciones de configuración

Hay otras opciones de configuración de la aplicación de Microsoft 365 que el Escritorio administrado de Microsoft puede configurar opcionalmente en su nombre. 

### <a name="disable-personal-onedrive"></a>Deshabilitar OneDrive personal

**Valor predeterminado:** Deshabilitado

Algunas organizaciones están interesadas en que los usuarios tengan acceso a archivos corporativos y personales en sus dispositivos. Puede presentar una solicitud de servicio al equipo de operaciones de Escritorio administrado de Microsoft solicitando que esta configuración esté habilitada. 

## <a name="settings-you-manage"></a>Configuración que administra

Hay muchas otras directivas que el Escritorio administrado de Microsoft aún no establece como parte de nuestro servicio. Puede configurar estas directivas con Microsoft Intune, que usa el servicio de directivas [de nube de Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) Para establecer estas directivas, siga estos pasos:

1.  Inicia sesión en el Centro de administración de Microsoft Endpoint Manager.
2.  Seleccionar **aplicaciones > directivas para aplicaciones de Office > crear**
3.  En la **página Crear configuración** de directiva, haga lo siguiente:
    - Escriba un nombre.
    - Proporciona una descripción (opcional).
    - En **las** asignaciones, elija si esta directiva se aplica a todos los usuarios de Aplicaciones de Microsoft 365 para empresas o solo a los usuarios que acceden a documentos de forma anónima mediante Office para la Web.
    - Seleccione el grupo de seguridad basado en AAD asignado a la configuración de directiva. Cada configuración de directiva solo se puede asignar a un grupo y solo se puede asignar una configuración de directiva a cada grupo.
    - Configure las opciones de directiva que se incluirán en la configuración de directiva. Puede buscar en el nombre de la configuración de directiva para encontrar la configuración de directiva que desea configurar. También puede filtrar por la aplicación, por si la directiva es una línea base de seguridad recomendada y por si se ha configurado la directiva. La columna de plataforma indica si la directiva se aplica a Aplicaciones de Microsoft 365 para empresas para dispositivos Windows, Office para la Web o a todas.
4.  Después de realizar las selecciones, elija **Crear**.

> [!NOTE]
> Las directivas de configuración de Office solo admiten la implementación basada en usuarios
