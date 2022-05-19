---
title: Configuración de notificaciones de alertas en Microsoft Defender para punto de conexión
description: Puede usar Microsoft Defender para punto de conexión para configurar las opciones de notificación por correo electrónico para las alertas de seguridad, en función de la gravedad y otros criterios.
keywords: notificaciones por correo electrónico, configurar notificaciones de alertas, Microsoft Defender para punto de conexión, Microsoft Defender para punto de conexión notificaciones, Microsoft Defender para punto de conexión alertas, Windows Enterprise, Windows Education
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fde5ce238a44b6722770338378ae33c54a38a450
ms.sourcegitcommit: 60970cf8a2cb451011c423d797dfb77925394f89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "65587498"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>Configuración de notificaciones de alertas en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-emailconfig-abovefoldlink)

Puede configurar Defender para punto de conexión para enviar notificaciones por correo electrónico a destinatarios especificados para nuevas alertas. Esta característica le permite identificar a un grupo de personas que se informarán inmediatamente y que pueden actuar sobre alertas en función de su gravedad.

Si usa [Defender para empresas](../defender-business/mdb-overview.md), puede configurar notificaciones por correo electrónico para usuarios específicos (no roles o grupos).

> [!NOTE]
> Solo los usuarios con permisos de "Administrar configuración de seguridad" pueden configurar las notificaciones por correo electrónico. Si ha elegido usar la administración básica de permisos, los usuarios con roles administrador de seguridad o administrador global pueden configurar las notificaciones por correo electrónico.

Puede establecer los niveles de gravedad de alerta que desencadenan las notificaciones. También puede agregar o quitar destinatarios de la notificación por correo electrónico. Los nuevos destinatarios reciben una notificación sobre las alertas desencadenadas después de agregarse. Para obtener más información sobre las alertas, consulte [Visualización y organización de la cola de alertas](alerts-queue.md).

Si usa el control de acceso basado en rol (RBAC), los destinatarios solo recibirán notificaciones basadas en los grupos de dispositivos configurados en la regla de notificación. Los usuarios con el permiso adecuado solo pueden crear, editar o eliminar notificaciones limitadas a su ámbito de administración del grupo de dispositivos. Solo los usuarios asignados al rol Administrador global pueden administrar las reglas de notificación configuradas para todos los grupos de dispositivos.

La notificación por correo electrónico incluye información básica sobre la alerta y un vínculo al portal donde puede realizar una investigación adicional.

## <a name="create-rules-for-alert-notifications"></a>Creación de reglas para notificaciones de alertas
Puede crear reglas que determinen los dispositivos y la gravedad de las alertas para enviar notificaciones por correo electrónico a los destinatarios de las notificaciones y .

1. En el panel de navegación, seleccione **Configuración** \> **Notificaciones de correo electrónico** **general** \> **de puntos** \> de conexión.

2. Haga clic en **Agregar elemento**.

3. Especifique la información general:
    - **Nombre de regla** : especifique un nombre para la regla de notificación.
    - **Incluir nombre de la organización** : especifique el nombre del cliente que aparece en la notificación por correo electrónico.
    - **Incluir vínculo de portal específico del inquilino** : agrega un vínculo con el identificador de inquilino para permitir el acceso a un inquilino específico.
    - **Incluir información del dispositivo** : incluye el nombre del dispositivo en el cuerpo de la alerta de correo electrónico.

        > [!NOTE]
        > Es posible que los servidores de correo de destinatarios que no estén en la ubicación geográfica que ha seleccionado para los datos de Defender para punto de conexión procesen esta información.

    - **Dispositivos**: elija si desea notificar a los destinatarios las alertas en todos los dispositivos (solo Administrador global rol) o en los grupos de dispositivos seleccionados. Para obtener más información, consulte [Creación y administración de grupos de dispositivos](machine-groups.md). (Si usa [Defender para empresas](../defender-business/mdb-overview.md), los grupos de dispositivos no se aplican).
    - **Gravedad de alerta** : elija el nivel de gravedad de la alerta.

4. Haga clic en **Siguiente**.

5. Escriba la dirección de correo electrónico del destinatario y haga clic en **Agregar destinatario**. Puedes agregar varias direcciones de correo electrónico.

6. Compruebe que los destinatarios de correo electrónico pueden recibir las notificaciones por correo electrónico seleccionando **Enviar correo electrónico de prueba**.

7. Haga clic en **Guardar regla de notificación**.

## <a name="edit-a-notification-rule"></a>Edición de una regla de notificación

1. Seleccione la regla de notificación que desea editar.

2. Actualice la información de la pestaña General y Destinatario.

3. Haga clic en **Guardar regla de notificación**.

## <a name="delete-notification-rule"></a>Eliminar regla de notificación

1. Seleccione la regla de notificación que desea eliminar.

2. Haga clic en **Eliminar**.

## <a name="troubleshoot-email-notifications-for-alerts"></a>Solución de problemas de notificaciones por correo electrónico para alertas

En esta sección se enumeran varios problemas que puede encontrar al usar notificaciones por correo electrónico para las alertas.

**Problema:** Los destinatarios previstos informan de que no reciben las notificaciones.

**Solución:** Asegúrese de que los filtros de correo electrónico no bloqueen las notificaciones:

1. Compruebe que las notificaciones de correo electrónico de Defender para punto de conexión no se envían a la carpeta Correo no deseado. Marcarlos como No basura.
2. Compruebe que el producto de seguridad de correo electrónico no bloquea las notificaciones por correo electrónico de Defender para punto de conexión.
3. Compruebe las reglas de la aplicación de correo electrónico que podrían estar detectando y moviendo las notificaciones de correo electrónico de Defender para punto de conexión.

## <a name="related-topics"></a>Temas relacionados

- [Actualización de la configuración de retención de datos](data-retention-settings.md)
- [Configurar funciones avanzadas](advanced-features.md)
- [Configuración de notificaciones por correo electrónico de vulnerabilidad en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
