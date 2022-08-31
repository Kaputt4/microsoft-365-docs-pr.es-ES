---
title: Configuración de notificaciones por correo electrónico para el equipo de seguridad
description: Configure notificaciones por correo electrónico para informar al equipo de seguridad sobre alertas y vulnerabilidades en Defender for Business.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- M365-security-compliance
- m365solution-mdb-setup
- highpri
ms.openlocfilehash: 31f3d1d11331ccb6fc800c0dabdcc41e19abe295
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480655"
---
# <a name="set-up-email-notifications"></a>Configuración de notificaciones por correo electrónico

Puede configurar notificaciones por correo electrónico para el equipo de seguridad. A continuación, a medida que se generan alertas o se detectan nuevas vulnerabilidades, se notificará automáticamente a las personas del equipo de seguridad. 

## <a name="what-to-do"></a>Qué hacer

1. [Obtener información sobre los tipos de notificaciones por correo electrónico](#types-of-email-notifications).
2. [Ver y editar la configuración de notificaciones por correo electrónico](#view-and-edit-email-notifications).
3. [Continúe con los pasos siguientes](#next-steps).

## <a name="types-of-email-notifications"></a>Tipos de notificaciones por correo electrónico

Al configurar notificaciones por correo electrónico, puede elegir entre dos tipos, como se describe en la tabla siguiente:

| Tipo de notificación  | Descripción  |
|---------|---------|
| Vulnerabilidades  | Cada vez que se detectan nuevas vulnerabilidades de seguridad o eventos de vulnerabilidad, los destinatarios reciben un correo electrónico. |
| Alertas & vulnerabilidades  | Cuando se generan alertas porque se detectan amenazas en los dispositivos o cuando se detectan nuevas vulnerabilidades o eventos de vulnerabilidad, los destinatarios reciben un correo electrónico. |

> [!TIP]
> **Email notificaciones no son la única manera en que el equipo de seguridad puede averiguar sobre nuevas alertas o vulnerabilidades**.
> 
> Email notificaciones son una manera cómoda de ayudar a mantener informado a su equipo de seguridad, en tiempo real. ¡Pero hay otros! Por ejemplo, cada vez que el equipo de seguridad inicie sesión en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), verá tarjetas que resaltan nuevas amenazas, alertas y vulnerabilidades. Defender for Business está diseñado para resaltar la información importante que le importa al equipo de seguridad en cuanto inician sesión.
> 
> El equipo de seguridad también puede elegir **Incidentes** en el panel de navegación para ver información. Para más información, consulte [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md).

## <a name="view-and-edit-email-notifications"></a>Visualización y edición de notificaciones por correo electrónico

Para ver o editar la configuración de notificaciones por correo electrónico de su empresa, siga estos pasos:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, seleccione **Configuración** y, a continuación, seleccione **Puntos de conexión**. A continuación, en **General**, seleccione **Email notificaciones**. 

3. Revise la información de las pestañas **Alertas** y **vulnerabilidades** .

   - Si no ve ningún elemento en la pestaña **Alertas** , puede crear una regla para que los usuarios reciban una notificación cuando se generen alertas. Para obtener ayuda con esta tarea, consulte [Creación de reglas para notificaciones de alertas](../defender-endpoint/configure-email-notifications.md).

   - Si no ve ningún elemento en la pestaña **Vulnerabilidades** , puede crear una regla para que las personas reciban notificaciones cada vez que se detecte una nueva vulnerabilidad. Para obtener ayuda con esta tarea, consulte [Creación de reglas para eventos de vulnerabilidad](../defender-endpoint/configure-vulnerability-email-notifications.md).

   - Si tiene reglas creadas, seleccione una regla para editarla. También puede eliminar una regla. 

> [!IMPORTANT]
> Al configurar notificaciones por correo electrónico en Defender para empresas, debe asignar las reglas de notificación a usuarios específicos. Defender for Business no usa [el control de acceso basado en rol, como hace Defender para punto de conexión](../defender-endpoint/rbac.md). Además, las notificaciones por correo electrónico no se pueden aplicar a grupos de dispositivos en Defender para empresas. 

## <a name="next-steps"></a>Pasos siguientes

Continúe con:

- [Paso 4: Incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md)
