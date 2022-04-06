---
title: Notificaciones de Identidad de Microsoft Defender en Microsoft 365 Defender
description: Obtén información sobre cómo establecer notificaciones de Microsoft Defender para identidad en Microsoft 365 Defender.
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: 89ed7ae50bf89c28bde81ea02e8905d0056ede53
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470931"
---
# <a name="defender-for-identity-notifications-in-microsoft-365-defender"></a>Notificaciones de Defender for Identity en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo trabajar con [Microsoft Defender para notificaciones](/defender-for-identity) de identidad en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

> [!IMPORTANT]
> Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="health-issues-notifications"></a>Notificaciones de problemas de estado

En Microsoft 365 Defender, puedes agregar destinatarios para notificaciones por correo electrónico de problemas de estado en Defender for Identity.

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a Configuración y, a **continuación**, **Identities**.

  :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades de la columna Nombre" lightbox="../../media/defender-identity/settings-identities.png":::


1. Seleccione **Notificaciones de problemas de estado**.

1. Escriba la dirección de correo electrónico del destinatario. Seleccione **Agregar**.

   :::image type="content" source="../../media/defender-identity/health-email-recipient.png" alt-text="El elemento de submenú Problemas de mantenimiento emite notificaciones" lightbox="../../media/defender-identity/health-email-recipient.png":::

1. Cuando Defender for Identity detecte un problema de estado, los destinatarios recibirán una notificación por correo electrónico con los detalles.

   :::image type="content" source="../../media/defender-identity/health-email.png" alt-text="El correo electrónico del problema de estado" lightbox="../../media/defender-identity/health-email.png":::

    > [!NOTE]
    > El correo electrónico proporciona dos vínculos para obtener más detalles sobre el problema. Puede ir al Centro de salud **MDI** o al nuevo centro de **mantenimiento de M365D**.

## <a name="alert-notifications"></a>Notificaciones de alerta

En Microsoft 365 Defender, puede agregar destinatarios para notificaciones por correo electrónico de alertas detectadas.

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a Configuración y, a **continuación**, **Identities**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades" lightbox="../../media/defender-identity/settings-identities.png":::

1. Seleccione **Notificaciones de alerta.**

1. Escriba la dirección de correo electrónico del destinatario. Seleccione **Agregar**.

   :::image type="content" source="../../media/defender-identity/alert-email-recipient.png" alt-text="El elemento de submenú Notificaciones de alerta" lightbox="../../media/defender-identity/alert-email-recipient.png":::

## <a name="syslog-notifications"></a>Notificaciones de Syslog

Defender for Identity puede notificarte cuando detecta actividades sospechosas enviando alertas de seguridad y estado a tu servidor de Syslog a través de un sensor designado.

> [!NOTE]
> Para obtener información sobre cómo integrar Defender for Identity con Microsoft Sentinel, consulte [Microsoft 365 Defender integración con Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a Configuración y, a **continuación**, **Identities**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción de Identidades en la columna Nombre" lightbox="../../media/defender-identity/settings-identities.png":::

1. Seleccione **Notificaciones de Syslog**.

1. Para habilitar la notificación de syslog, establece la alternancia **del servicio de Syslog** en **la posición** activa.

   :::image type="content" source="../../media/defender-identity/syslog-service.png" alt-text="La opción de servicio de Syslog que se puede desactivar" lightbox="../../media/defender-identity/syslog-service.png":::

1. Seleccione **Configurar servicio**. Se abrirá un panel donde puede especificar los detalles del servicio de syslog.

   :::image type="content" source="../../media/defender-identity/syslog-sensor.png" alt-text="La página en la que se escriben los detalles del servicio de Syslog" lightbox="../../media/defender-identity/syslog-sensor.png":::

1. Escriba los siguientes detalles:

    - **Sensor** : en la lista desplegable, elija el sensor que enviará las alertas.
    - **Punto de conexión** de servicio y **puerto** : escriba la dirección IP o el nombre de dominio completo (FQDN) del servidor de syslog y especifique el número de puerto. Solo puede configurar un extremo de Syslog.
    - **Transporte** : seleccione el **protocolo** de transporte (TCP o UDP).
    - **Formato** : seleccione el formato (RFC 3164 o RFC 5424).

1. Seleccione **Enviar notificación SIEM de prueba** y compruebe que el mensaje se recibe en la solución de infraestructura de Syslog.

1. Haga clic en **Guardar**.

1. Una vez configurado el servicio **de Syslog**, puede elegir qué tipos de notificaciones (alertas o problemas de estado) enviar a su servidor de Syslog.

   :::image type="content" source="../../media/defender-identity/syslog-configured.png" alt-text="La opción de servicio de Syslog está activada" lightbox="../../media/defender-identity/syslog-configured.png":::

## <a name="see-also"></a>Vea también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
