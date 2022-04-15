---
title: Configuración de notificaciones por correo electrónico para el equipo de seguridad
description: Configurar notificaciones por correo electrónico para informar a los usuarios sobre alertas y vulnerabilidades con Microsoft Defender para Empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: a65634a5827e60d710cec56ca10835c73053cb10
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862860"
---
# <a name="set-up-email-notifications"></a>Configuración de notificaciones por correo electrónico

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

Puede configurar notificaciones por correo electrónico para el equipo de seguridad. A continuación, a medida que se generan alertas o se detectan nuevas vulnerabilidades, se notificará automáticamente a las personas del equipo de seguridad. 

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los tipos de notificaciones por correo electrónico](#types-of-email-notifications).

2. [Ver y editar la configuración de notificaciones por correo electrónico](#view-and-edit-email-notifications).

3. [Continúe con los pasos siguientes](#next-steps).


>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="types-of-email-notifications"></a>Tipos de notificaciones por correo electrónico

Al configurar notificaciones por correo electrónico, puede elegir entre dos tipos, como se describe en la tabla siguiente:

| Tipo de notificación  | Descripción  |
|---------|---------|
| Vulnerabilidades  | Cada vez que se detectan nuevas vulnerabilidades de seguridad o eventos de vulnerabilidad, los destinatarios reciben un correo electrónico. |
| Alertas & vulnerabilidades  | Cuando se generan alertas porque se detectan amenazas en los dispositivos o cuando se detectan nuevas vulnerabilidades o eventos de vulnerabilidad, los destinatarios reciben un correo electrónico. |

> [!TIP]
> **Las notificaciones por correo electrónico no son la única manera en que el equipo de seguridad puede averiguar sobre nuevas alertas o vulnerabilidades**.
> 
> Las notificaciones por correo electrónico son una manera cómoda de ayudar a mantener informado a su equipo de seguridad, en tiempo real. ¡Pero hay otros! Por ejemplo, cada vez que el equipo de seguridad inicie sesión en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), verá tarjetas que resaltan nuevas amenazas, alertas y vulnerabilidades. Defender for Business está diseñado para resaltar la información importante que le importa al equipo de seguridad en cuanto inician sesión.
> 
> El equipo de seguridad también puede elegir **Incidentes** en el panel de navegación para ver información. Para más información, consulte [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md).

## <a name="view-and-edit-email-notifications"></a>Visualización y edición de notificaciones por correo electrónico

Para ver o editar la configuración de notificaciones por correo electrónico de su empresa, siga estos pasos:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, seleccione **Configuración** y, a continuación, seleccione **Puntos de conexión**. A continuación, en **General**, seleccione **Notificaciones por correo electrónico**. 

3. Revise la información de las pestañas **Alertas** y **vulnerabilidades** .

   - Si no ve ningún elemento en la pestaña **Alertas** , puede crear una regla para que los usuarios reciban una notificación cuando se generen alertas. Para obtener ayuda con esta tarea, consulte [Creación de reglas para notificaciones de alertas](../defender-endpoint/configure-email-notifications.md).

   - Si no ve ningún elemento en la pestaña **Vulnerabilidades** , puede crear una regla para que las personas reciban notificaciones cada vez que se detecte una nueva vulnerabilidad. Para obtener ayuda con esta tarea, consulte [Creación de reglas para eventos de vulnerabilidad](../defender-endpoint/configure-vulnerability-email-notifications.md).

   - Si tiene reglas creadas, seleccione una regla para editarla. También puede eliminar una regla. 

## <a name="next-steps"></a>Siguientes pasos

Continúe con:

- [Paso 4: Incorporación de dispositivos a Microsoft Defender para Empresas](mdb-onboard-devices.md)
