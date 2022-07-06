---
title: Creación de un aviso de suspensión legal
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use la herramienta de comunicaciones en un caso de exhibición de documentos electrónicos (Premium) para enviar, recopilar y realizar un seguimiento de las notificaciones de suspensión legal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97630c75c05412e22afa17daaa1897f8627adf1
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634685"
---
# <a name="create-a-legal-hold-notice"></a>Creación de un aviso de suspensión legal

Mediante las comunicaciones de custodios de eDiscovery (Premium), las organizaciones pueden administrar su flujo de trabajo en torno a la comunicación con los custodios. A través de la herramienta de comunicaciones, los equipos legales pueden enviar, recopilar y realizar un seguimiento sistemático de las notificaciones de suspensión legal. El proceso de creación flexible también permite a los equipos personalizar el flujo de trabajo de notificación de suspensión y el contenido de los avisos enviados a los custodios.

![Página Comunicaciones.](../media/CommunicationPage.PNG)

En el artículo se describen los pasos del flujo de trabajo de notificación de suspensión.

## <a name="step-1-specify-communication-details"></a>Paso 1: Especificar detalles de comunicación

El primer paso es especificar los detalles adecuados para los avisos de suspensión legal u otras comunicaciones de custodio.

![Página Comunicación de nombre.](../media/NameCommunication.PNG)

1. En el portal de cumplimiento Microsoft Purview, vaya a **eDiscovery > Advanced** para mostrar la lista de casos de su organización.

2. Seleccione un caso, haga clic en la pestaña **Comunicaciones** y, a continuación, haga clic en **Nueva comunicación**.

3. En la página **Comunicación de nombre** , especifique la siguiente configuración de comunicación.

    - **Nombre**: este es el nombre de la comunicación.

    - **Oficial emisor**: en la lista desplegable se muestran los usuarios de la organización que se pueden seleccionar como responsable de emisión de la comunicación. Cada comunicación enviada a los custodios se enviará en nombre del oficial emisor seleccionado. La lista de usuarios de la lista desplegable está formada por los miembros del caso y los responsables emisores de toda la organización. Estos oficiales emisores los agrega un administrador de exhibición de documentos electrónicos y están disponibles en todos los casos de exhibición de documentos electrónicos (Premium) de su organización. Para obtener más información, consulte [Administración de oficiales emisores](advanced-ediscovery-issuing-officers.md).

    - **Seleccionar plantilla de comunicación**: la lista desplegable muestra las plantillas de la biblioteca de comunicaciones en la página de configuración de eDiscovery (Premium). Si selecciona una plantilla, se mostrará en Definir **contenido del portal** como punto de partida para el texto de la notificación que va a crear. Si no selecciona una plantilla, tendrá que crear el aviso usted mismo desde cero. Para obtener más información sobre las plantillas de comunicación, vea [Administrar plantillas de comunicaciones de custodio.](advanced-ediscovery-communications-library.md)

4. Haga clic en **Siguiente**.

## <a name="step-2-define-the-portal-content"></a>Paso 2: Definir el contenido del portal

A continuación, puede crear y agregar el contenido del aviso de suspensión. En la página **Definir contenido del portal** del Asistente **para crear comunicaciones** , especifique el contenido del aviso de suspensión. Este contenido se anexará automáticamente a los avisos de emisión, reedición, recordatorio y escalación. Además, este contenido aparecerá en el Portal de cumplimiento del custodio. Si seleccionó una plantilla de la biblioteca de comunicaciones, se mostrará y proporcionará un punto de partida para el aviso que va a crear.

![Página Contenido del portal.](../media/PortalContent.PNG)

Para crear el contenido del portal:

1. Escriba (o corte y pegue desde otro documento) el aviso de suspensión en el cuadro de texto del contenido del portal. Si seleccionó una plantilla de comunicaciones en la página del asistente anterior, se muestra la plantilla. Puede editar el contenido de la plantilla según sea necesario.

2. Inserte variables de combinación en el aviso para personalizar el aviso y compartir el Portal de cumplimiento de custodios.

3. Haga clic en **Siguiente**.

  > [!TIP]
  > Para más información sobre cómo personalizar el contenido y el formato del contenido del portal, consulte [Uso del Editor de comunicaciones](using-communications-editor.md).

## <a name="step-3-set-the-required-notifications"></a>Paso 3: Establecer las notificaciones necesarias

Después de definir el contenido del aviso de suspensión, puede configurar los flujos de trabajo en torno al envío y la administración del proceso de notificación. Las notificaciones son mensajes de correo electrónico que se envían para notificar y realizar un seguimiento con los custodios. Cada custodio agregado a la comunicación recibirá la misma notificación.

Para configurar y enviar un aviso de suspensión, debe incluir las notificaciones de emisión, reejeje y versión.

### <a name="issuance-notification"></a>Notificación de emisión

Una vez creada la comunicación, el responsable de emisión especificado inicia la **notificación de emisión** . La notificación de emisión es la primera comunicación enviada al custodio para informarle sobre sus obligaciones de conservación.

Para crear una notificación de emisión:

1. En el icono **Emisión** , haga clic en **Editar**.

2. Si es necesario, agregue más miembros del caso o personal a los campos **Cc** y **CCO** . Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.

3. Especifique el **asunto** para el aviso (obligatorio).

4. Especifique el contenido o las instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de emisión.

5. Haga clic en **Guardar**.

### <a name="re-issuance-notification"></a>Re-Issuance notificación

A medida que avanza el caso, es posible que los custodios deban conservar datos adicionales o menos de los indicados anteriormente. Después de actualizar el contenido del portal, se envía la notificación de reemitimiento y alerta a los custodios sobre los cambios en sus obligaciones de conservación.

Para crear una notificación de reemitimiento:

1. En el icono **Volver a emitir** , haga clic en **Editar**.

2. Si es necesario, agregue más miembros del caso o personal a los campos **Cc** y **CCO** . Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.

3. Especifique el **asunto** para el aviso (obligatorio).

4. Especifique el contenido o las instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de reemitimiento.

5. Haga clic en **Guardar**.

> [!NOTE]
> Si se modifica el contenido del portal (en la página **Definir contenido del portal** del Asistente para **editar comunicaciones** ), la notificación de nueva emisión se enviará automáticamente a todos los custodios asignados al aviso. Una vez enviada la notificación, se pedirá a los custodios que vuelvan a confirmar su notificación de suspensión. Si ha configurado flujos de trabajo de recordatorio o escalación, también se volverán a iniciar. Para obtener más información sobre qué otros eventos de administración de casos desencadenan comunicaciones, vea [Eventos que desencadenan notificaciones](#events-that-trigger-notifications).

### <a name="release-notification"></a>Notificación de versión

Una vez resuelto un asunto o si un custodio ya no está sujeto a conservación del contenido, puede liberar al custodio de un caso. Si el custodio recibió previamente un aviso de suspensión, la notificación de liberación se puede usar para alertar a los custodios de que han sido liberados de su obligación.

Para crear una notificación de versión:

1. En el icono **Versión** , haga clic en **Editar**.

2. Si es necesario, agregue más miembros del caso o personal a los campos **Cc** y **CCO** . Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.

3. Especifique el **asunto** para el aviso (obligatorio).

4. Especifique el contenido o las instrucciones adicionales que desea proporcionar al custodio (obligatorio).

5. Haga clic en **Guardar** y vaya al paso siguiente.

## <a name="optional-step-4-set-the-optional-notifications"></a>(Opcional) Paso 4: Establecer las notificaciones opcionales

Opcionalmente, puede simplificar el flujo de trabajo para realizar un seguimiento con custodios que no responden mediante la creación y programación de notificaciones automatizadas de recordatorio y escalación.

![Página Recordatorio/Escalación.](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Reminders

Después de enviar una notificación de suspensión, puede realizar un seguimiento con los custodios que no responden definiendo un flujo de trabajo de recordatorio.

Para programar recordatorios:

1. En el icono **Recordatorio** , haga clic en **Editar**.

2. Habilite el flujo de trabajo **Recordatorio** activando el botón de alternancia **Estado** (obligatorio).

3. Especifique el **intervalo de recordatorio (en días)** (obligatorio). Este es el número de días que hay que esperar antes de enviar las primeras notificaciones de recordatorio y de seguimiento. Por ejemplo, si establece el intervalo de recordatorio en siete días, el primer aviso se enviará siete días después de que se emitiera inicialmente la notificación de suspensión. Todos los recordatorios posteriores también se enviarían cada siete días.

4. Especifique el **número de avisos** (obligatorio). Este campo especifica cuántos recordatorios se enviarán a los custodios que no respondan. Por ejemplo, si establece el número de recordatorios en 3, un custodio recibiría un máximo de tres avisos. Después de que un custodio confirme la notificación de suspensión, los avisos ya no se enviarán a ese usuario.

5. Especifique el **asunto** para el aviso (obligatorio).

6. Especifique el contenido o las instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso.

7. Haga clic en **Guardar** y vaya al paso siguiente.

### <a name="escalations"></a>Escalamientos

En algunas situaciones, es posible que necesite formas adicionales de hacer un seguimiento con los custodios que no responden. Si un custodio no confirma una notificación de suspensión después de recibir el número especificado de avisos, el equipo legal puede especificar un flujo de trabajo para enviar automáticamente un aviso de escalación al custodio y a su administrador.

Para programar escalaciones:

1. En el icono **Escalación** , haga clic en **Editar**.

2. Habilite el flujo **de trabajo de escalación** activando el botón de alternancia **Estado** .

3. Especifique el **intervalo de escalación (en días)** (obligatorio).

4. Especifique el **número de escalaciones** (obligatorio). Este campo especifica cuántas escalaciones se van a enviar a los custodios que no responden. Por ejemplo, si establece el número de escalaciones en 3, se enviará un aviso de escalación al custodio y a su administrador un máximo de tres veces. Después de que un custodio confirme la notificación de suspensión, ya no se enviarán escalaciones.

5. Especifique el **asunto** para el aviso (obligatorio).

6. Especifique el contenido o las instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de escalación.

7. Haga clic en **Guardar** y vaya al paso siguiente.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Paso 5: Asignar custodios para recibir notificaciones

Después de finalizar el contenido de las notificaciones, seleccione los custodios a los que desea enviar notificaciones.

![Seleccione la página Custodios.](../media/SelectCustodians.PNG)

Para agregar custodios:

1. Asigne custodios a la comunicación haciendo clic en la casilla situada junto a su nombre.

    Una vez creada la comunicación, el flujo de trabajo de notificación se aplicará automáticamente a los custodios seleccionados.

2. Haga clic en **Siguiente** para revisar la configuración y los detalles de la comunicación.

> [!NOTE]
> Solo puede agregar custodios que se hayan agregado al caso y que no hayan enviado otra notificación dentro del caso.

## <a name="step-6-review-settings"></a>Paso 6: Revisar la configuración

Después de revisar la configuración y hacer clic en **Enviar** para completar la comunicación, el sistema iniciará automáticamente el flujo de trabajo de comunicación enviando el aviso de emisión.

## <a name="events-that-trigger-notifications"></a>Eventos que desencadenan notificaciones

En la tabla siguiente se describen los eventos del proceso de administración de casos que se desencadenan cuando se envían los distintos tipos de notificaciones a los custodios.

|Tipo de comunicación|Trigger |
|:---------|:---------|
|Avisos de emisión|La creación inicial de la notificación. También puede volver a enviar manualmente una notificación de suspensión. |
|Avisos de reemitimiento|Actualizar el contenido del portal en la página **Definir contenido del portal** en el Asistente para **editar comunicaciones** .|
|Avisos de versión|El custodio queda libre del caso.|
|Reminders|Intervalo y número de avisos configurados para el aviso.|
|Escalamientos|Intervalo y número de avisos configurados para la escalación.|
|||
