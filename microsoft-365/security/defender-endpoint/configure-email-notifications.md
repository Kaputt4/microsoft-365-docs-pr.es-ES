---
title: Configurar notificaciones de alertas en Microsoft Defender para endpoint
description: Puedes usar Microsoft Defender para Endpoint para configurar las opciones de notificación de correo electrónico para alertas de seguridad, según la gravedad y otros criterios.
keywords: notificaciones de correo electrónico, configurar notificaciones de alertas, Microsoft Defender para endpoint, Microsoft Defender para notificaciones de puntos de conexión, alertas de Microsoft Defender para endpoints, windows 10 enterprise, windows 10 education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9a7ad1241ce73bb9b68e173faa9433c7326e14e5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286938"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Configurar notificaciones de alertas en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

Puede configurar Defender for Endpoint para enviar notificaciones por correo electrónico a destinatarios especificados para nuevas alertas. Esta característica le permite identificar un grupo de personas que se informarán inmediatamente y pueden actuar en alertas en función de su gravedad.

> [!NOTE]
> Solo los usuarios con permisos de "Administrar configuración de seguridad" pueden configurar las notificaciones de correo electrónico. Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones de correo electrónico.

Puede establecer los niveles de gravedad de alerta que desencadenan las notificaciones. También puede agregar o quitar destinatarios de la notificación de correo electrónico. Los nuevos destinatarios reciben notificaciones sobre las alertas desencadenadas después de agregarse. Para obtener más información acerca de las alertas, vea [Ver y organizar la cola de alertas](alerts-queue.md).

Si usas el control de acceso basado en roles (RBAC), los destinatarios solo recibirán notificaciones en función de los grupos de dispositivos configurados en la regla de notificación.
Los usuarios con el permiso adecuado solo pueden crear, editar o eliminar notificaciones limitadas al ámbito de administración de grupos de dispositivos.
Solo los usuarios asignados al rol de administrador global pueden administrar las reglas de notificación configuradas para todos los grupos de dispositivos.

La notificación por correo electrónico incluye información básica sobre la alerta y un vínculo al portal donde puede realizar más investigaciones.

## <a name="create-rules-for-alert-notifications"></a>Crear reglas para notificaciones de alertas
Puede crear reglas que determinen los dispositivos y las gravedades de alerta para enviar notificaciones por correo electrónico y los destinatarios de las notificaciones.


1. En el panel de navegación, **seleccione Configuración** notificaciones de  >  **correo electrónico**.

2. Haga clic **en Agregar elemento**.

3. Especifique la información general:
    - **Nombre de regla:** especifique un nombre para la regla de notificación.
    - **Incluir nombre de organización:** especifique el nombre del cliente que aparece en la notificación por correo electrónico.
    - **Incluir vínculo de portal específico del inquilino:** agrega un vínculo con el identificador de inquilino para permitir el acceso a un inquilino específico.
    - **Incluir información del dispositivo:** incluye el nombre del dispositivo en el cuerpo de la alerta de correo electrónico.

        > [!NOTE]
        > Es posible que los servidores de correo de destinatarios procese esta información que no se encuentra en la ubicación geográfica seleccionada para los datos del extremo de Defender.

    - **Dispositivos:** elige si se notifica a los destinatarios alertas en todos los dispositivos (solo rol de administrador global) o en grupos de dispositivos seleccionados. Para obtener más información, consulta [Crear y administrar grupos de dispositivos.](machine-groups.md)
    - **Gravedad de alerta:** elija el nivel de gravedad de la alerta.

4. Haga clic en **Siguiente**.

5. Escriba la dirección de correo electrónico del destinatario y, a continuación, haga clic **en Agregar destinatario.** Puedes agregar varias direcciones de correo electrónico.

6. Compruebe que los destinatarios de correo electrónico pueden recibir las notificaciones de correo electrónico **seleccionando Enviar correo electrónico de prueba**.

7. Haga clic **en Guardar regla de notificación**.

## <a name="edit-a-notification-rule"></a>Editar una regla de notificación

1. Seleccione la regla de notificación que desea editar.

2. Actualice la información de las pestañas General y Destinatario.

3. Haga clic **en Guardar regla de notificación**.

## <a name="delete-notification-rule"></a>Eliminar regla de notificación

1. Seleccione la regla de notificación que desea eliminar.

2. Haga clic en **Eliminar**.

## <a name="troubleshoot-email-notifications-for-alerts"></a>Solucionar problemas de notificaciones de correo electrónico para alertas

En esta sección se enumeran varios problemas que puede encontrar al usar notificaciones por correo electrónico para alertas.

**Problema:** Los destinatarios previstos informan de que no reciben las notificaciones.

**Solución:** Asegúrese de que los filtros de correo electrónico no bloqueen las notificaciones:

1. Compruebe que las notificaciones de correo electrónico de Defender for Endpoint no se envíen a la carpeta Correo no deseado. Marcalos como No deseado.
2. Compruebe que el producto de seguridad de correo electrónico no está bloqueando las notificaciones de correo electrónico de Defender para endpoint.
3. Comprueba las reglas de la aplicación de correo electrónico que podrían estar capturando y moviendo las notificaciones de correo electrónico de Defender para puntos de conexión.

## <a name="related-topics"></a>Temas relacionados

- [Actualizar la configuración de retención de datos](data-retention-settings.md)
- [Configurar funciones avanzadas](advanced-features.md)
