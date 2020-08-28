---
title: Aplicaciones de Microsoft 365 para empresas
description: Cómo implementar aplicaciones de Microsoft 365, cómo se actualizan y cómo se administra la configuración
keywords: historial de cambios
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: b3843da0d35d78486ed22af6d057930ee4ad5bc9
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "47295273"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

## <a name="initial-deployment"></a>Implementación inicial

Microsoft Managed Desktop garantiza que Microsoft 365 apps for Enterprise (64-bit) se instalen como parte de la imagen en todos los [dispositivos de programa](../service-description/device-list.md). Todas las aplicaciones siguientes deben estar presentes en el dispositivo cuando se entreguen:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype Empresarial
- OneNote

Este enfoque minimiza el impacto en la red y garantiza que los usuarios puedan ser productivos tan pronto como reciban el dispositivo. A continuación, implementamos directivas adicionales en los dispositivos administrados para configurar las aplicaciones que se usarán.

> [!NOTE]
> Microsoft Teams se implementa por separado de las aplicaciones de Microsoft 365 para empresas y no se incluye en la imagen básica. 

### <a name="available-deployment-to-users"></a>Implementación disponible para los usuarios

Si un usuario no tiene aplicaciones de Microsoft 365 en su dispositivo por algún motivo, puede usar un paquete para devolver el dispositivo a su estado esperado. Agregue el usuario al grupo APP **Workplace-Office-Office365_Install moderno** y las aplicaciones estarán disponibles en el portal de la empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Microsoft 365 apps for Enterprise (32 bits)

Microsoft Managed Desktop no es compatible con la implementación de la versión 32 de M365 de aplicaciones para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Actualizaciones para aplicaciones de Microsoft 365

Las aplicaciones de Microsoft 365 están configuradas para actualizarse en el [canal mensual](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)de la empresa. Este procedimiento proporciona a los usuarios nuevas características de Office cada mes, pero solo recibirán una actualización por mes en un programa de entrega predecible. Las actualizaciones se publican el segundo martes del mes; estas actualizaciones pueden incluir actualizaciones de características, seguridad y calidad. Estas actualizaciones se producen automáticamente y se extraen directamente de la red CDN de Office para ese canal específico.

El escritorio administrado de Microsoft Escalona cada versión para identificar cualquier posible problema en el entorno. Completamos la implementación 28 días después de la publicación del grupo de productos de aplicación 365 de Microsoft. Microsoft Managed Desktop programa las versiones de actualización a diferentes grupos para dejar tiempo para la validación y las pruebas de la siguiente manera: 

- Prueba: 0 días
- Primero: 0 días
- Rápido: 7 días
- Amplia gama: 21 días

Microsoft Managed Desktop establece una [fecha límite de actualización](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) de siete días para los dispositivos. Una vez que la actualización está disponible, debe instalarse en un plazo de siete días. Se [notifica](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) a los usuarios que se necesitan actualizaciones en varias ubicaciones: la aplicación, en la bandeja del sistema 12 horas antes de la fecha límite, recibe una advertencia de 15 minutos antes de la fecha límite. Todas las aplicaciones de Microsoft 365 deben estar cerradas para que se pueda completar la actualización.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar o revertir una actualización

Si tiene que pausar o revertir la actualización de la aplicación de Microsoft 365 por cualquier motivo, archivo una [solicitud de soporte de administrador](../working-with-managed-desktop/admin-support.md) mediante Microsoft Managed Desktop portal.

Durante una versión, Microsoft Managed Desktop supervisa las tasas de error de todas las aplicaciones de Microsoft 365. Si se observa una diferencia importante en cuanto a la calidad entre la nueva versión y su antecesor, es posible que se ponga en contacto con usted a través del portal de administración de escritorio administrado de Microsoft. En función de la gravedad, se le preguntará si desea pausar el lanzamiento o informarle de que hemos tomado medidas para mitigar un problema. 

### <a name="delivery-optimization"></a>Optimización de entrega

La optimización de entrega es una tecnología de distribución de punto a punto disponible en Windows 10. Permite que los dispositivos compartan contenido, como actualizaciones, que los dispositivos han descargado de Microsoft a través de Internet. Esto puede ayudar a reducir el ancho de banda de red porque un dispositivo puede obtener partes de la actualización desde otro dispositivo en su red local en lugar de tener que descargar la actualización completamente desde Microsoft.

La [optimización de entrega](https://docs.microsoft.com/deployoffice/delivery-optimization) está habilitada de forma predeterminada en los dispositivos que ejecutan las ediciones de Windows 10 Enterprise o Windows 10 Education. 

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrada por el escritorio administrado por Microsoft

Microsoft administra algunas opciones como parte del servicio. El escritorio administrado de Microsoft no administra una línea de base de seguridad de Office, pero puede establecer una usted mismo siguiendo las instrucciones de la sección [configuración que se va a administrar](#settings-you-manage) .

### <a name="update-settings"></a>Actualizar configuración

Microsoft Managed Desktop mantiene todas las [configuraciones de actualización](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) para los dispositivos administrados y debe modificar esta configuración.

### <a name="set-updates-to-occur-automatically"></a>Establecer actualizaciones para que se realicen automáticamente

**Valor predeterminado**: habilitado

Esta directiva está configurada para garantizar que todos los dispositivos de Office se puedan mantener actualizados desde la nube. 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a>Establecer una fecha límite cuando se deben aplicar las actualizaciones

**Valor predeterminado**: 7 días

La directiva **UpdateDeadline** se usa para configurar el período de gracia que los usuarios tienen antes de que se aplique una actualización en el dispositivo. Esta directiva de fecha límite también desencadena [notificaciones](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) al usuario para informarles de los cambios necesarios en el dispositivo.  

### <a name="defer-updates-on-a-device-for-a-period"></a>Aplazar las actualizaciones en un dispositivo durante un período

Esta Directiva se configura de forma diferente para cada grupo de dispositivos de administración de actualizaciones y es necesario para que Microsoft Managed Desktop cumpla sus objetivos de actualización:  

- Prueba: 0 días
- Primero: 0 días
- Rápido 7 días
- Amplia gama: 21 días

### <a name="update-notifications-settings"></a>Actualizar la configuración de notificaciones

**Valor predeterminado**: false

La configuración "ocultar notificaciones de actualización" se establece en **false** en dispositivos de escritorio administrados por Microsoft para proporcionar la mejor experiencia de actualización a los usuarios mediante la [notificación](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) cuando se necesitan actualizaciones.

### <a name="specify-a-location-to-look-for-updates"></a>Especificar una ubicación para buscar actualizaciones

**Valor predeterminado**: canal de empresa mensual

Se utiliza una combinación de las directivas **UpdatePath** y **UpdateChannel** para obtener la programación de actualizaciones. Estas directivas se establecen para garantizar que todos los dispositivos de Office reciban actualizaciones directamente desde la red CDN para el canal de empresa mensual.

### <a name="specify-the-target-version-of-microsoft-365-apps"></a>Especificar la versión de destino de las aplicaciones de Microsoft 365

La Directiva de versión de destino a veces la usa el escritorio administrado por Microsoft para revertir o anclar una versión específica de Office. 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a>Ocultar la opción para habilitar o deshabilitar las actualizaciones automáticas de Office

**Valor predeterminado**: habilitado

Esta configuración es necesaria para que Microsoft Managed Desktop cumpla sus objetivos de actualización para las aplicaciones de Microsoft 365. 

### <a name="first-run-settings"></a>Configuración de primera ejecución 

Hay varias configuraciones que afectan al comportamiento la primera vez que se ejecuta Office.

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a>Aceptar los términos de licencia en nombre del usuario final

**Valor predeterminado**: deshabilitado

La primera vez que un usuario abra una aplicación de Microsoft 365, se le pedirá que acepte los términos de licencia. Si desea aceptar los términos de licencia en nombre de sus usuarios, archivo una solicitud de servicio con el equipo de operaciones de escritorio administradas de Microsoft que solicita que esta configuración esté habilitada. 

### <a name="suppress-outlook-mobile-check-box"></a>Casilla de verificación suprimir Outlook Mobile

**Valor predeterminado**: deshabilitado

La primera vez que un usuario abre Outlook, se le pedirá que instale Outlook Mobile. Si no desea que los usuarios vean esa casilla, archivo una solicitud de servicio con el equipo de operaciones de escritorio administradas de Microsoft que solicita que esta configuración esté habilitada para los dispositivos. 

## <a name="other-settings"></a>Otras opciones de configuración

Hay otras opciones de configuración de la aplicación Microsoft 365 que Microsoft Managed Desktop puede configurar de forma opcional en su nombre. 

### <a name="disable-personal-onedrive"></a>Deshabilitar OneDrive personal

**Valor predeterminado**: deshabilitado

A algunas organizaciones les preocupa que los usuarios tengan acceso a archivos corporativos y personales en sus dispositivos. Puede archivar una solicitud de servicio con el equipo de operaciones de escritorio administrado por Microsoft que solicita que esta configuración esté habilitada. 

## <a name="settings-you-manage"></a>Configuración que administra

Hay muchas otras directivas que el escritorio administrado de Microsoft todavía no ha establecido como parte de nuestro servicio. Puede configurarlos mediante Microsoft Intune, que usa el servicio de [directivas de nube de Office](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) . Para ello, siga estos pasos:

1.  Inicie sesión en el centro de administración de Microsoft Endpoint Manager.
2.  Seleccione **aplicaciones > directivas para las aplicaciones de Office > crear**
3.  En la página crear configuración de **Directiva** , haga lo siguiente:
    - Escriba un nombre.
    - Proporcione una descripción (opcional).
    - En **asignaciones**, elija si esta Directiva se aplica a todos los usuarios de las aplicaciones de Microsoft 365 para empresas o solo a los usuarios que tengan acceso anónimo a los documentos con Office para la Web.
    - Seleccione el grupo de seguridad basado en AAD que se asigna a la configuración de la Directiva. Cada configuración de directiva solo se puede asignar a un grupo y cada grupo solo puede tener asignada una configuración de directiva.
    - Configure las opciones de directiva que se incluirán en la configuración de la Directiva. Puede buscar en el nombre de la configuración de directiva para encontrar la configuración de directiva que desea configurar. También puede filtrar en la aplicación, si la Directiva es una línea base de seguridad recomendada y si la Directiva se ha configurado. La columna plataforma indica si la Directiva se aplica a Microsoft 365 apps for Enterprise para dispositivos Windows, Office para la web o todo.
4.  Después de realizar las selecciones, elija **crear**.

> [!NOTE]
> Las directivas de configuración de Office solo admiten la implementación basada en el usuario
