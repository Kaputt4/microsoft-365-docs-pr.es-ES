---
title: notificaciones de Microsoft Defender for Identity en Microsoft 365 Defender
description: Obtenga información sobre cómo establecer notificaciones de Microsoft Defender for Identity en Microsoft 365 Defender.
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 7015e87d79a01888a1315de597eecd39263e5d66
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682313"
---
# <a name="defender-for-identity-notifications-in-microsoft-365-defender"></a>Notificaciones de Defender for Identity en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo trabajar con [las notificaciones de Microsoft Defender for Identity](/defender-for-identity) en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

> [!IMPORTANT]
> Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y nuevas.

## <a name="health-issues-notifications"></a>Notificaciones de problemas de mantenimiento

En Microsoft 365 Defender, puede agregar destinatarios para notificaciones por correo electrónico de problemas de mantenimiento en Defender for Identity.

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a **Configuración** y, a continuación, **Identidades**.

  :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades de la columna Nombre" lightbox="../../media/defender-identity/settings-identities.png":::


1. Seleccione **Notificaciones de problemas de mantenimiento**.

1. Escriba la dirección de correo electrónico del destinatario. Seleccione **Agregar**.

   :::image type="content" source="../../media/defender-identity/health-email-recipient.png" alt-text="Elemento de submenú Problemas de mantenimiento" lightbox="../../media/defender-identity/health-email-recipient.png":::

1. Cuando Defender for Identity detecta un problema de mantenimiento, los destinatarios recibirán una notificación por correo electrónico con los detalles.

   :::image type="content" source="../../media/defender-identity/health-email.png" alt-text="Correo electrónico del problema de mantenimiento" lightbox="../../media/defender-identity/health-email.png":::

    > [!NOTE]
    > El correo electrónico proporciona dos vínculos para obtener más detalles sobre el problema. Puede ir al **Centro de salud de MDI** o al nuevo **Centro de salud en M365D**.

## <a name="alert-notifications"></a>Notificaciones de alertas

En Microsoft 365 Defender, puede agregar destinatarios para las notificaciones por correo electrónico de las alertas detectadas.

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a **Configuración** y, a continuación, **Identidades**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción Identidades" lightbox="../../media/defender-identity/settings-identities.png":::

1. Seleccione **Notificaciones de alertas**.

1. Escriba la dirección de correo electrónico del destinatario. Seleccione **Agregar**.

   :::image type="content" source="../../media/defender-identity/alert-email-recipient.png" alt-text="Elemento de submenú Notificaciones de alertas" lightbox="../../media/defender-identity/alert-email-recipient.png":::

## <a name="syslog-notifications"></a>Notificaciones de Syslog

Defender for Identity puede notificarle cuando detecte actividades sospechosas mediante el envío de alertas de seguridad y estado al servidor syslog a través de un sensor designado.

> [!NOTE]
> Para obtener información sobre cómo integrar Defender for Identity con Microsoft Sentinel, consulte [Microsoft 365 Defender integración con Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a **Configuración** y, a continuación, **Identidades**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Opción de Identidades en la columna Nombre" lightbox="../../media/defender-identity/settings-identities.png":::

1. Seleccione **Notificaciones de Syslog**.

1. Para habilitar la notificación de Syslog, establezca el botón de alternancia del **servicio syslog** **en la posición activa** .

   :::image type="content" source="../../media/defender-identity/syslog-service.png" alt-text="La opción de servicio syslog que se puede activar" lightbox="../../media/defender-identity/syslog-service.png":::

1. Seleccione **Configurar servicio**. Se abrirá un panel donde puede especificar los detalles del servicio syslog.

   :::image type="content" source="../../media/defender-identity/syslog-sensor.png" alt-text="Página en la que se escriben los detalles del servicio Syslog" lightbox="../../media/defender-identity/syslog-sensor.png":::

1. Escriba los detalles siguientes:

    - **Sensor** : en la lista desplegable, elija el sensor que enviará las alertas.
    - **Punto de conexión de servicio** y **puerto** : escriba la dirección IP o el nombre de dominio completo (FQDN) para el servidor syslog y especifique el número de puerto. Solo puede configurar un punto de conexión de Syslog.
    - **Transporte** : seleccione el protocolo **de transporte** (TCP o UDP).
    - **Formato** : seleccione el formato (RFC 3164 o RFC 5424).

1. Seleccione **Enviar notificación SIEM de prueba** y compruebe que el mensaje se recibe en la solución de infraestructura de Syslog.

1. Haga clic en **Guardar**.

1. Una vez que haya configurado el **servicio Syslog**, puede elegir qué tipos de notificaciones (alertas o problemas de estado) se enviarán al servidor de Syslog.

   :::image type="content" source="../../media/defender-identity/syslog-configured.png" alt-text="La opción de configuración del servicio Syslog está activada" lightbox="../../media/defender-identity/syslog-configured.png":::

## <a name="see-also"></a>Vea también

- [Administración de alertas de seguridad de Defender for Identity](manage-security-alerts.md)
