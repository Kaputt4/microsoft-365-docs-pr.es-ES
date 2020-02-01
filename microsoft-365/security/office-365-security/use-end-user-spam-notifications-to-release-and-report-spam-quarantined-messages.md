---
title: Usar notificaciones de correo no deseado para el usuario final para liberar y notificar mensajes de correo no deseado en cuarentena
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: 'Los usuarios que ven un mensaje de notificación de correo no deseado para el usuario final de su administrador sobre el correo electrónico en cuarentena pueden realizar estas acciones en los mensajes. '
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598087"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a>Usar notificaciones de correo no deseado para el usuario final para liberar y notificar mensajes de correo no deseado en cuarentena

Si su administrador habilita las notificaciones de correo no deseado del usuario final, recibirá un mensaje de notificación con los mensajes destinados al buzón que se identificaron como correo no deseado y en su lugar se colocaron en cuarentena. Este mensaje incluye la cantidad de mensajes marcados como correo no deseado y en cuarentena de la lista, y la fecha y hora (en hora universal coordinada [UTC]) del último mensaje de la lista. En esta lista, puede ver la siguiente información sobre cada mensaje:

- **Sender**: el nombre y la dirección de correo electrónico del remitente del mensaje en cuarentena.

- **Asunto**: el texto de la línea de asunto del mensaje en cuarentena.

- **Fecha**: la fecha y hora (en UTC) en que el mensaje se ha puesto en cuarentena.

- **Size**: el tamaño del mensaje en cuarentena, en kilobytes (KB).

Puede realizar las siguientes acciones en cada mensaje:

- **Liberar a bandeja de entrada**: al hacer clic en este vínculo, se envía el mensaje a la bandeja de entrada, donde puede verlo.

- **Informar como correo deseado**: al hacer clic en este vínculo, se envía una copia del mensaje a Microsoft para su análisis. El equipo de correo no deseado evalúa y analiza el mensaje, y, según de los resultados del análisis, ajusta las reglas de filtro de correo no deseado para permitir que el mensaje pase.

> [!NOTE]
> Los mensajes que están en cuarentena debido a una coincidencia de regla de flujo de correo (también conocida como una) no se incluyen en los mensajes de cuarentena de correo no deseado del usuario final. Solo se enumeran los mensajes en cuarentena de correo no deseado. <br/><br/>  Únicamente puede liberar un mensaje e identificarlo como un falso positivo (deseado) una vez.
