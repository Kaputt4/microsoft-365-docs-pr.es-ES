---
title: Crear un aviso de retención legal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Usa la herramienta Comunicaciones en un Advanced eDiscovery caso para enviar, recopilar y realizar un seguimiento de las notificaciones de retención legal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840565"
---
# <a name="create-a-legal-hold-notice"></a>Crear un aviso de retención legal

Con Advanced eDiscovery de custodia, las organizaciones pueden administrar su flujo de trabajo en torno a la comunicación con los custodios. A través de la herramienta comunicaciones, los equipos legales pueden enviar, recopilar y realizar un seguimiento sistemático de las notificaciones de retención legal. El proceso de creación flexible también permite a los equipos personalizar el flujo de trabajo de notificación de retención y el contenido de los avisos enviados a los custodios.

![Página comunicaciones](../media/CommunicationPage.PNG)

En el artículo se describen los pasos del flujo de trabajo de notificación de retención.

## <a name="step-1-specify-communication-details"></a>Paso 1: Especificar detalles de comunicación

El primer paso es especificar los detalles adecuados para los avisos de retención legal u otras comunicaciones de custodia.

![Página de comunicación de nombres](../media/NameCommunication.PNG)

1. En el Centro de seguridad & cumplimiento, vaya a **eDiscovery > Advanced eDiscovery** para mostrar la lista de casos de su organización.

2. Seleccione un caso, haga clic en la **pestaña** Comunicaciones y, a continuación, haga clic **en Nueva comunicación.**

3. En la **página Comunicación de** nombre, especifique los siguientes detalles de comunicación (obligatorios).

    - **Nombre:** este es el nombre de la comunicación.

    - **Oficial emisor:** la lista desplegable muestra una lista de miembros de casos. Para obtener más información sobre cómo agregar nuevos miembros a un caso, vea [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case). Cada aviso enviado a los custodios se enviará en nombre del oficial emisor especificado.

> [!NOTE]
> El oficial emisor debe tener un **buzón activo** para aparecer en la lista desplegable Oficial emisor


4. Haga clic en **Siguiente**.

## <a name="step-2-define-the-portal-content"></a>Paso 2: Definir el contenido del portal

A continuación, puede crear y agregar el contenido del aviso de retención. En la **página Definir contenido del portal** del Asistente para crear **comunicación,** especifique el contenido del aviso de retención. Este contenido se anexará automáticamente a los avisos de emisión, reedición, aviso y escalación. Además, este contenido aparecerá en el Portal de cumplimiento del custodio. 

![Página de contenido del portal](../media/PortalContent.PNG)

Para crear el contenido del portal:

1. Escriba (o corte y pegue desde otro documento) el aviso de retención en el cuadro de texto del contenido del portal. 

2. Inserte variables de combinación en el aviso para personalizar el aviso y compartir el Portal de cumplimiento de custodia.

3. Haga clic en **Siguiente**.

  >[!Tip]
  >Para obtener más información sobre cómo personalizar el contenido y el formato del contenido del portal, vea [Use the Communications Editor](using-communications-editor.md).

## <a name="step-3-set-the-required-notifications"></a>Paso 3: Establecer las notificaciones necesarias

Después de definir el contenido del aviso de retención, puede configurar los flujos de trabajo en torno al envío y administración del proceso de notificación. Las notificaciones son mensajes de correo electrónico que se envían para notificar y hacer un seguimiento con los custodios. Todos los custodios agregados a la comunicación recibirán la misma notificación. 

Para configurar y enviar un aviso de retención, debe incluir las notificaciones Emisión, Re-emisión y Lanzamiento.

### <a name="issuance-notification"></a>Notificación de emisión 

Una vez creada la comunicación, **el** oficial emisor especificado inicia la notificación de emisión. La notificación de emisión es la primera comunicación enviada al custodio para informarle sobre sus obligaciones de conservación. 

Para crear una notificación de emisión:

1. En el icono **Emisión,** haga clic **en Editar**.

2. Si es necesario, agregue miembros o personal de casos adicionales a los **campos Cc** y **CCO.** Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.

3. Especifique el **asunto** para el aviso (obligatorio).

4. Especifique el contenido o instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de emisión. 

5. Haga clic en **Guardar**.

### <a name="re-issuance-notification"></a>Re-Issuance notificación

A medida que avanza el caso, es posible que los custodios deban conservar datos adicionales o inferiores a los que se instruyeron anteriormente. Después de actualizar el contenido del portal, se envía la notificación de nueva emisión y se alerta a los custodios sobre cualquier cambio en sus obligaciones de conservación.

Para crear una notificación de nueva emisión:

1. En el **icono Reissue,** haga clic en **Editar**.

2. Si es necesario, agregue miembros o personal de casos adicionales a los **campos Cc** y **CCO.** Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.

3. Especifique el **asunto** para el aviso (obligatorio).

4. Especifique el contenido o instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de ree emisión.

5. Haga clic en **Guardar**.

> [!NOTE]
> Si se modifica el contenido del portal (en la página Definir contenido del **portal** en el Asistente para editar comunicaciones), la notificación de nueva emisión se enviará automáticamente a todos los custodios asignados al aviso.  Después de enviar la notificación, se pedirá a los custodios que vuelvan a confirmar su notificación de retención. Si ha configurado flujos de trabajo de aviso o de escalación, estos también se volverán a iniciar. Para obtener más información acerca de qué otros eventos de administración de casos desencadenan comunicaciones, vea [Eventos que desencadenan notificaciones](#events-that-trigger-notifications).

### <a name="release-notification"></a>Notificación de lanzamiento

Una vez resuelto un asunto o si un custodio ya no está sujeto a la conservación del contenido, puede liberar al custodio de un caso. Si el custodio recibió previamente un aviso de retención, la notificación de liberación puede usarse para alertar a los custodios de que han sido liberados de su obligación.

Para crear una notificación de lanzamiento: 

1. En el **icono Versión,** haga clic **en Editar**.

2. Si es necesario, agregue miembros o personal de casos adicionales a los **campos Cc** y **CCO.** Para agregar varios usuarios a estos campos, separe las direcciones de correo electrónico con un punto y coma.

3. Especifique el **asunto** para el aviso (obligatorio).

4. Especifique el contenido o instrucciones adicionales que desea proporcionar al custodio (obligatorio).

5. Haga **clic en** Guardar y vaya al paso siguiente.

## <a name="optional-step-4-set-the-optional-notifications"></a>(Opcional) Paso 4: Establecer las notificaciones opcionales

Opcionalmente, puede simplificar el flujo de trabajo para realizar un seguimiento con custodios no responsables mediante la creación y programación de notificaciones automatizadas de avisos y escalamiento.

![Página aviso/escalación](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Reminders

Después de enviar una notificación de retención, puede realizar un seguimiento con los custodios no responsables definiendo un flujo de trabajo de aviso.

Para programar avisos:

1. En el **icono Aviso,** haga clic **en Editar**.

2. Habilite el **flujo de trabajo** Aviso activando el botón de **alternancia** Estado (obligatorio).

3. Especifique el **intervalo de aviso (en días)** (obligatorio). Este es el número de días que hay que esperar antes de enviar las primeras notificaciones de aviso y seguimiento. Por ejemplo, si establece el intervalo de aviso en siete días, el primer aviso se enviará siete días después de que se emitió inicialmente la notificación de retención. Todos los avisos posteriores también se enviarían cada siete días.

4. Especifique el **número de avisos** (obligatorio). Este campo especifica cuántos avisos enviar a los custodios no responsables. Por ejemplo, si establece el número de avisos en 3, un custodio recibiría un máximo de tres avisos. Después de que un custodio reconozca la notificación de retención, los avisos ya no se enviarán a ese usuario.

5. Especifique el **asunto** para el aviso (obligatorio). 

6. Especifique el contenido o instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de aviso.

7. Haga **clic en** Guardar y vaya al paso siguiente.

### <a name="escalations"></a>Escalaciones

En algunas situaciones, es posible que necesite formas adicionales de hacer un seguimiento con los custodios no responsables. Si un custodio no reconoce una notificación de retención después de recibir el número especificado de avisos, el equipo legal puede especificar un flujo de trabajo para enviar automáticamente un aviso de escalamiento al custodio y a su administrador.

Para programar escalaciones:

1. En el icono **Escalación,** haga clic **en Editar**.

2. Habilite el **flujo de trabajo escalación** activando el **botón de alternancia** Estado.

3. Especifique el **intervalo de escalación (en días)** (obligatorio).

4. Especifique el **número de escalaciones** (obligatorio). Este campo especifica cuántas escalaciones se enviarán a los custodios no responsables. Por ejemplo, si establece el número de escalaciones en 3, se enviará un aviso de escalación al custodio y a su administrador un máximo de tres veces. Después de que un custodio reconozca la notificación de retención, las escalaciones ya no se enviarán.

5. Especifique el **asunto** para el aviso (obligatorio). 

6. Especifique el contenido o instrucciones adicionales que desea proporcionar al custodio (obligatorio). El contenido del portal que definió en el paso 2 se agrega al final del aviso de escalado.

7. Haga **clic en** Guardar y vaya al paso siguiente.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Paso 5: Asignar custodios para recibir notificaciones

Después de finalizar el contenido de las notificaciones, seleccione los custodios a los que desea enviar notificaciones. 

![Seleccionar página de custodios](../media/SelectCustodians.PNG)

Para agregar custodios:

1. Para asignar custodios a la comunicación, haga clic en la casilla situada junto a su nombre.

    Una vez creada la comunicación, el flujo de trabajo de notificación se aplicará automáticamente a los custodios seleccionados.

2. Haga **clic en Siguiente** para revisar la configuración y los detalles de la comunicación.

>[!NOTE]
>Solo puede agregar custodios que se hayan agregado al caso y que no hayan recibido otra notificación dentro del caso.

## <a name="step-6-review-settings"></a>Paso 6: Revisar la configuración

Después de revisar la configuración y hacer **clic** en Enviar para completar la comunicación, el sistema iniciará automáticamente el flujo de trabajo de comunicación enviando el aviso de emisión.

## <a name="events-that-trigger-notifications"></a>Eventos que desencadenan notificaciones

En la tabla siguiente se describen los eventos del proceso de administración de casos que se desencadenan cuando se envían los distintos tipos de notificaciones a los custodios.

|Tipo de comunicación|Trigger |
|:---------|:---------|
|Avisos de emisión|La creación inicial de la notificación. También puede reenviar manualmente una notificación de retención. |
|Avisos de ree emisión|Actualizar el contenido del portal en la **página Definir contenido del portal** en el Asistente para editar **comunicaciones.**|
|Avisos de lanzamiento|El custodio se libera del caso.|
|Reminders|Intervalo y número de avisos configurados para el aviso.|
|Escalaciones|Intervalo y número de avisos configurados para la escalación.|
|||
