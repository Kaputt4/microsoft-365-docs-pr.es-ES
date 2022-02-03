---
title: Aplicaciones de Microsoft 365 para empresas
description: Cómo implementar Aplicaciones Microsoft 365, cómo se actualizan y cómo se administra la configuración
keywords: historial de cambios
ms.service: m365-md
ms.sitesec: library
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 19ad7cfa3459b67b41a9d85994f960255aeeeb02
ms.sourcegitcommit: babc2dad1c0e08a9237dbe4956ffd21c0214db83
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62346049"
---
# <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

## <a name="initial-deployment"></a>Implementación inicial

Microsoft Managed Desktop garantiza que Aplicaciones Microsoft 365 para empresas (64 bits) se instalen como parte de la imagen en todos los [dispositivos del programa](../service-description/device-list.md). Todas las aplicaciones siguientes deben estar presentes en el dispositivo cuando se entregue:

- Word
- Excel
- PowerPoint
- Outlook
- Publisher
- Access
- Skype Empresarial
- OneNote

Este enfoque minimiza el impacto en la red y garantiza que los usuarios puedan ser productivos tan pronto como reciban su dispositivo. A continuación, implementamos más directivas en dispositivos administrados para configurar las aplicaciones para su uso.

> [!NOTE]
> Microsoft Teams se implementa independientemente de Aplicaciones Microsoft 365 para empresas y no se incluye en la imagen base.

### <a name="available-deployment-to-users"></a>Implementación disponible para los usuarios

Si un usuario no tiene Aplicaciones Microsoft 365 en su dispositivo por cualquier motivo, puedes usar un paquete para devolver el dispositivo al estado esperado. Agrega al usuario al grupo **Modern Workplace-Office-Office365_Install y** las aplicaciones estarán disponibles en el Portal de empresa.

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a>Aplicaciones Microsoft 365 para empresas (32 bits)

Microsoft Managed Desktop no admite la implementación de la versión de 32 bits de Aplicaciones Microsoft 365 para empresas.

## <a name="updates-to-microsoft-365-apps"></a>Actualizaciones de Aplicaciones Microsoft 365

Aplicaciones Microsoft 365 se establecen para actualizarse en el Canal [de Enterprise mensual](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview). Esta práctica proporciona a los usuarios nuevas características Office cada mes, pero solo recibirán una actualización al mes en una programación de lanzamiento predecible. Las actualizaciones se lanzan el segundo martes del mes; estas actualizaciones pueden incluir actualizaciones de características, seguridad y calidad. Estas actualizaciones se producen automáticamente y se sacan directamente del Office CDN para ese canal específico.

Microsoft Managed Desktop escalona cada versión para identificar posibles problemas en el entorno. Completamos el lanzamiento 28 días después de la versión del grupo de productos Microsoft 365 app. Microsoft Managed Desktop programa las versiones de actualización a diferentes grupos para dar tiempo a la validación y las pruebas de la siguiente manera:

- Prueba: cero días
- Primero: cero días
- Rápido: tres días
- Amplia: siete días

Microsoft Managed Desktop establece una fecha límite de actualización de siete [días](/deployoffice/configure-update-settings-microsoft-365-apps) para dispositivos. Una vez que la actualización está disponible, debe instalarse en un plazo de siete días. Se notifica [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) a los usuarios que las actualizaciones son necesarias en varias ubicaciones: la aplicación, en la bandeja del sistema 12 horas antes de la fecha límite, y reciben una advertencia de 15 minutos antes de la fecha límite. Todos los Aplicaciones Microsoft 365 deben cerrarse para que se complete la actualización.

### <a name="pausing-or-rolling-back-an-update"></a>Pausar o revertir una actualización

Si necesita pausar o revertir la actualización Microsoft 365 aplicación por cualquier motivo, abra una solicitud de soporte técnico para [administradores a](../working-with-managed-desktop/admin-support.md) través del portal de Escritorio administrado de Microsoft.

Durante una versión, Microsoft Managed Desktop supervisa las tasas de error de todos los Aplicaciones Microsoft 365. Si vemos una diferencia significativa en la calidad entre la nueva versión y la versión anterior, podríamos ponerse en contacto con usted a través del portal de administración de escritorio administrado de Microsoft.

Dependiendo de la gravedad, haremos lo siguiente:

- Pregunte si desea pausar la versión o
- Le informamos de que hemos tomado medidas para mitigar un problema.

### <a name="delivery-optimization"></a>Optimización de entrega

Optimización de distribución es una tecnología de distribución punto a punto disponible en Windows 10. Permite a los dispositivos compartir contenido, como las actualizaciones, que los dispositivos descargaron de Microsoft a través de Internet. Us Delivery Optimization puede ayudar a reducir el ancho de banda de red, ya que un dispositivo puede obtener partes de la actualización de otro dispositivo en su red local en su lugar descargar la actualización completamente de Microsoft.

[Optimización de](/deployoffice/delivery-optimization) entrega está habilitada de forma predeterminada en dispositivos que ejecutan Windows 10 Enterprise o Windows 10 Education ediciones.

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrado por Microsoft Managed Desktop

Microsoft administra algunas opciones de configuración como parte del servicio. Microsoft Managed Desktop no administra una línea base Office seguridad. Sin embargo, puede establecer uno usted mismo siguiendo las instrucciones de la [sección Configuración administrar](#settings-you-manage).

### <a name="update-settings"></a>Actualizar configuración

Microsoft Managed Desktop mantiene toda la configuración [de actualización para](/deployoffice/configure-update-settings-microsoft-365-apps) dispositivos administrados y debe modificar esta configuración.

| Setting | Valor predeterminado | Descripción |
| ------ | ------ | ------ |
| Establecer actualizaciones para que se produzcan automáticamente | Habilitado | Esta directiva se configura para garantizar que todos los Office se puedan mantener actualizados desde la nube. |
| Establecer una fecha límite cuando se deben aplicar las actualizaciones | Siete días | La **directiva UpdateDeadline** se usa para configurar el período de gracia que tienen los usuarios antes de que se aplique una actualización en el dispositivo. Esta directiva de fecha límite también desencadena [notificaciones](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) al usuario para informarle de los cambios necesarios en su dispositivo. |
| Aplazar actualizaciones en un dispositivo durante un período | Ver descripción | Esta directiva se configura de forma diferente para cada grupo de dispositivos de administración de actualizaciones. Es necesario que Microsoft Managed Desktop cumpla sus objetivos de actualización: <ul> <li> Prueba: cero días </li> <li>Primero: cero días</li><li>Ayunar siete días</li><li>Ancho: 21 días</li></ul> |
| Actualizar la configuración de notificación | Falso | La configuración "ocultar notificaciones de actualización" se establece en **False** en dispositivos de Escritorio administrado de Microsoft para proporcionar la mejor experiencia de [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) actualización para los usuarios notificándolos cuando se necesitan actualizaciones.|
| Especificar una ubicación para buscar actualizaciones | Canal empresarial mensual | Se usa una combinación de **las directivas UpdatePath** y **UpdateChannel** según sea necesario para lograr la programación de actualización. Estas directivas se establecen para garantizar que todos los dispositivos Office reciban actualizaciones directamente desde el CDN del canal de Enterprise mensual.|
| Especifique la versión de destino de Aplicaciones Microsoft 365 | Ver descripción | La directiva versión de destino a veces la usa Microsoft Managed Desktop para revertir o anclar una versión específica de Office.|
| Ocultar la opción para habilitar o deshabilitar Office actualizaciones automáticas | Habilitado | Esta configuración es necesaria para que Microsoft Managed Desktop cumpla sus objetivos de actualización para Microsoft 365 aplicaciones. |
| Configuración de la primera ejecución | Ver descripción | Hay varias opciones de configuración que afectan al comportamiento la primera vez que Office se ejecuta. |
| Aceptar los términos de licencia en nombre del usuario final | Deshabilitado | La primera vez que un usuario abre una Microsoft 365, se le pedirá que acepte los términos de licencia. Si desea aceptar los términos de licencia en nombre de los usuarios, presente una solicitud de soporte técnico al equipo de Operaciones de escritorio administrado de Microsoft y pida que esta configuración esté habilitada. |
| Suprimir Outlook móvil | Deshabilitado | La primera vez que un usuario Outlook, se le pedirá que instale Outlook Móvil. Si no desea que los usuarios vean esa casilla, presente una solicitud de soporte técnico con el equipo de Operaciones de escritorio administrado de Microsoft y solicite que esta configuración esté habilitada para los dispositivos. |

## <a name="other-settings"></a>Otras opciones de configuración

Hay otras opciones Microsoft 365 aplicación que Microsoft Managed Desktop puede configurar opcionalmente en su nombre.

| Setting | Valor predeterminado | Descripción |
| ------ | ------ | ------ |
| Deshabilitar las OneDrive | Deshabilitado | Algunas organizaciones están preocupadas por que los usuarios tengan acceso a archivos corporativos y personales en sus dispositivos. Puede presentar una solicitud de soporte técnico con el equipo de Operaciones de escritorio administrado de Microsoft y solicitar que esta configuración esté habilitada. |

## <a name="settings-you-manage"></a>Configuración administrar

Hay muchas otras directivas que Microsoft Managed Desktop aún no establece como parte de nuestro servicio. Puede configurar estas directivas mediante Microsoft Intune, que usa el [Office de directivas en la](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) nube. Para establecer estas directivas, siga estos pasos:

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager.
1. Seleccione **Aplicaciones**.
1. Selecciona **Directivas para Office y** luego selecciona **Crear**.
1. En la **página Crear configuración** de directiva, haga lo siguiente:
    - Escriba un nombre.
    - Proporcione una descripción opcional.
    - En **asignaciones**, elija si esta directiva se aplica a todos los usuarios de Aplicaciones Microsoft 365 para empresas, o simplemente a los usuarios que acceden de forma anónima a documentos mediante Office para la Web.
    - Seleccione el **AAD de seguridad basado en la** directiva que está asignado a la configuración de directiva. Cada configuración de directiva solo se puede asignar a un grupo. Solo se puede asignar una configuración de directiva a cada grupo.
    - Configure las opciones de directiva para que se incluyan en la configuración de directiva. Puede buscar en el nombre de configuración de directiva para buscar la configuración de directiva que desea configurar. También puede filtrar si la directiva es una línea base de seguridad recomendada y si la directiva se ha configurado. La columna de plataforma indica si la directiva se aplica a Aplicaciones Microsoft 365 para empresas para Windows dispositivos, Office para la Web o todos.
1. Después de realizar las selecciones, seleccione **Crear**.

> [!NOTE]
> Office de configuración solo admiten la implementación basada en usuarios
