---
title: Obtener notificaciones de incidentes por correo electrónico en Microsoft 365 Defender
description: Obtenga información sobre cómo crear reglas para obtener notificaciones por correo electrónico para incidentes en Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents, analyze, response
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 600ff555762112222769fde0372716f4a89a12b9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717676"
---
# <a name="get-incident-notifications-by-email"></a>Obtener notificaciones de incidentes por correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Puede configurar Microsoft 365 Defender para notificar a su personal con un correo electrónico sobre nuevos incidentes o actualizaciones de incidentes existentes. Puede elegir obtener notificaciones en función de:

- Gravedad del incidente.
- Grupo de dispositivos.
- Solo en la primera actualización por incidente.

La notificación por correo electrónico contiene detalles importantes sobre el incidente, como el nombre del incidente, la gravedad y las categorías, entre otras. También puede ir directamente al incidente e iniciar el análisis de inmediato. Para obtener más información, vea [Investigar incidentes](investigate-incidents.md).

Puede agregar o quitar destinatarios en las notificaciones de correo electrónico. Los nuevos destinatarios reciben notificaciones sobre incidentes después de agregarse. 

>[!NOTE]
>Necesita el permiso "Administrar la configuración de seguridad" para configurar las opciones de notificación de correo electrónico. Si ha elegido usar la administración de permisos básicos, los usuarios con roles de administrador de seguridad o administrador global pueden configurar las notificaciones de correo electrónico por usted. <br> <br>
Del mismo modo, si tu organización usa el control de acceso basado en roles (RBAC), solo puedes crear, editar, eliminar y recibir notificaciones en función de los grupos de dispositivos que puedas administrar.

## <a name="create-a-rule-for-email-notifications"></a>Crear una regla para notificaciones por correo electrónico

Siga estos pasos para crear una nueva regla y personalizar la configuración de notificaciones por correo electrónico.

1. En el panel de navegación, **seleccione Configuración > Microsoft 365 Defender > notificaciones de correo electrónico de incidentes**.
2. Seleccione **Agregar elemento**.
3. En la **página Conceptos básicos,** escriba el nombre de la regla y una descripción y, a continuación, **seleccione Siguiente**.
4. En la **página Configuración de** notificaciones, configure:
    - **Gravedad de alerta**: elija los niveles de gravedad de alerta que desencadenarán una notificación de incidente. Por ejemplo, si solo desea que se le informe sobre incidentes de alta gravedad, seleccione **Alto**.
    - **Ámbito del grupo de dispositivos**: puede especificar todos los grupos de dispositivos o seleccionarlos en la lista de grupos de dispositivos del inquilino.
    - **Notificar solo la primera aparición por incidente**: seleccione si desea una notificación solo en la primera alerta que coincida con las demás selecciones. Las actualizaciones o alertas posteriores relacionadas con el incidente no enviarán notificaciones adicionales.
    - **Incluir el nombre de la organización en el correo electrónico**: seleccione si desea que el nombre de la organización aparezca en la notificación por correo electrónico.
    - **Incluir vínculo del portal específico del inquilino**: seleccione si desea agregar un vínculo con el identificador de inquilino en la notificación de correo electrónico para acceder a un inquilino de Microsoft 365 específico.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Configuración de notificaciones para notificaciones de correo electrónico de incidentes.":::

5. Seleccione **Siguiente**. En la **página Destinatarios,** agregue las direcciones de correo electrónico que recibirán las notificaciones de incidentes. Seleccione **Agregar después** de escribir cada nueva dirección de correo electrónico. Para probar las notificaciones y asegurarse de que los destinatarios las reciben en las bandejas de entrada, seleccione **Enviar correo electrónico de prueba.** 
6. Seleccione **Siguiente**. En la **página Revisar regla,** revise la configuración de la regla y, a continuación, **seleccione Crear regla**. Los destinatarios empezarán a recibir notificaciones de incidentes a través del correo electrónico en función de la configuración.

Para editar una regla existente, selecciónelo en la lista de reglas. En el panel con el nombre de regla, seleccione **Editar** regla y realice los cambios en las páginas **Conceptos** básicos, Configuración de **notificación** y **Destinatarios.**

Para eliminar una regla, selecciónelo en la lista de reglas. En el panel con el nombre de regla, seleccione **Eliminar**.

## <a name="see-also"></a>Vea también
- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Investigar incidentes](investigate-incidents.md)
