---
title: Administrar alertas de Microsoft Defender para punto de conexión
description: Cambie el estado de las alertas, cree reglas de supresión para ocultar alertas, envíe comentarios y revise el historial de cambios de alertas individuales con el menú Administrar alerta.
keywords: administrar alertas, administrar, alertas, estado, nuevo, en curso, resuelto, resolver alertas, suprimir, supresión, reglas, contexto, historial, comentarios, cambios
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 72d35555d3853aad102d2e4fee1a665c9abb04cd
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521233"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Administrar alertas de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender for Endpoint le notifica posibles eventos malintencionados, atributos e información contextual a través de alertas. En el **panel Operaciones de seguridad** se muestra un resumen de las nuevas alertas y puede acceder a todas las alertas de la **cola alertas**.

Para administrar las alertas, seleccione una alerta en la **cola Alertas** o en la pestaña **Alertas** de la página Dispositivo de un dispositivo individual.

Al seleccionar una alerta en cualquiera de esos lugares, aparece el **panel Administración de alertas**.

:::image type="content" source="images/atp-alerts-selected.png" alt-text="El panel Administración de alertas y la cola de alertas" lightbox="images/atp-alerts-selected.png":::

Vea este vídeo para obtener información sobre cómo usar la nueva página de alertas de Microsoft Defender para punto de conexión.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4yiO5]

## <a name="link-to-another-incident"></a>Vínculo a otro incidente

Puede crear un nuevo incidente a partir de la alerta o vincularlo a un incidente existente.

## <a name="assign-alerts"></a>Asignación de alertas

Si aún no se ha asignado una alerta, puede seleccionar **Asignarme para asignarla** usted mismo.

## <a name="suppress-alerts"></a>Suprimir alertas

Puede haber escenarios en los que tenga que suprimir la aparición de alertas en Microsoft 365 Defender. Defender para punto de conexión le permite crear reglas de supresión para alertas específicas que se sabe que son inofensas, como herramientas conocidas o procesos de su organización.

Las reglas de supresión se pueden crear a partir de una alerta existente. Se pueden deshabilitar y volver a habilitar si es necesario.

Cuando se crea una regla de supresión, surtirá efecto desde el punto en que se crea la regla. La regla no afectará a las alertas existentes ya en la cola, antes de la creación de la regla. La regla solo se aplicará en las alertas que cumplan las condiciones establecidas después de crear la regla.

Hay dos contextos para una regla de supresión entre los que puede elegir:

- **Suprimir alerta en este dispositivo**
- **Suprimir alerta en mi organización**

El contexto de la regla le permite adaptar lo que aparece en el portal y asegurarse de que solo se exponen alertas de seguridad reales en el portal.

Puede usar los ejemplos de la tabla siguiente para ayudarle a elegir el contexto de una regla de supresión:

|Contexto|Definición|Escenarios de ejemplo|
|---|---|---|
|**Suprimir alerta en este dispositivo**|Las alertas con el mismo título de alerta y en ese dispositivo específico solo se suprimirán. <p> Todas las demás alertas de ese dispositivo no se suprimirán.|<ul><li>Un investigador de seguridad está investigando un script malintencionado que se ha usado para atacar a otros dispositivos de su organización.</li><li>Un desarrollador crea periódicamente scripts de PowerShell para su equipo.</li></ul>|
|**Suprimir alerta en mi organización**|Se suprimirán las alertas con el mismo título de alerta en cualquier dispositivo.|<ul><li>Todos los usuarios de la organización usan una herramienta administrativa benigna.</li></ul>|

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>Suprimir una alerta y crear una nueva regla de supresión

Cree reglas personalizadas para controlar cuándo se suprimen o resuelven las alertas. Puede controlar el contexto para cuando se suprime una alerta especificando el título de la alerta, el indicador de riesgo y las condiciones. Después de especificar el contexto, podrá configurar la acción y el ámbito en la alerta.

1. Seleccione la alerta que desea suprimir. Esto abre el panel **Administración de alertas** .

2. Seleccione **Crear una regla de supresión**.

    Puede crear una condición de supresión mediante estos atributos. Se aplica un operador AND entre cada condición, por lo que la supresión solo se produce si se cumplen todas las condiciones.

    - Archivo SHA1
    - Nombre de archivo: comodín admitido
    - Ruta de acceso de carpeta: comodín admitido
    - Dirección IP
    - DIRECCIÓN URL: comodín admitido
    - Línea de comandos: comodín admitido

3. Seleccione **la opción Desencadenar IOC**.

4. Especifique la acción y el ámbito en la alerta.

   Puede resolver automáticamente una alerta u ocultarla en el portal. Las alertas que se resuelven automáticamente aparecerán en la sección resuelta de la cola de alertas, la página de alertas y la escala de tiempo del dispositivo y aparecerán como resueltas en las API de Defender para punto de conexión.

   Las alertas marcadas como ocultas se suprimirán de todo el sistema, tanto en las alertas asociadas del dispositivo como desde el panel y no se transmitirán a través de las API de Defender para punto de conexión.

5. Escriba un nombre de regla y un comentario.

6. Haga clic en **Guardar**.

#### <a name="view-the-list-of-suppression-rules"></a>Ver la lista de reglas de supresión

1. En el panel de navegación, seleccione **Configuración Supresión** \> **de alertas**.

2. La lista de reglas de supresión muestra todas las reglas que los usuarios de su organización han creado.

Para obtener más información sobre la administración de reglas de supresión, consulte [Administración de reglas de supresión](manage-suppression-rules.md).

## <a name="change-the-status-of-an-alert"></a>Cambiar el estado de una alerta

Puede clasificar las alertas (como **Nuevas**, **En curso** o **Resueltas**) cambiando su estado a medida que avanza la investigación. Esto le ayuda a organizar y administrar cómo su equipo puede responder a las alertas.

Por ejemplo, un responsable del equipo puede revisar todas las alertas **nuevas** y decidir asignarlas a la cola **En curso** para su análisis posterior.

Como alternativa, el responsable del equipo podría asignar la alerta a la cola **Resuelta** si sabe que la alerta es benigna, que procede de un dispositivo que no es relevante (por ejemplo, una que pertenece a un administrador de seguridad) o que se trata a través de una alerta anterior.

## <a name="alert-classification"></a>Clasificación de alerta

Puede elegir no establecer una clasificación o especificar si una alerta es una alerta verdadera o una alerta falsa. Es importante proporcionar la clasificación de verdadero positivo o falso positivo. Esta clasificación se usa para supervisar la calidad de las alertas y hacer que las alertas sean más precisas. El campo "determinación" define una fidelidad adicional para una clasificación "verdaderamente positiva".

## <a name="add-comments-and-view-the-history-of-an-alert"></a>Agregar comentarios y ver el historial de una alerta

Puede agregar comentarios y ver eventos históricos sobre una alerta para ver los cambios anteriores realizados en la alerta.

Cada vez que se realiza un cambio o comentario en una alerta, se registra en la sección **Comentarios e historial** .

Los comentarios agregados aparecen al instante en el panel.

## <a name="related-topics"></a>Temas relacionados

- [Administrar reglas de supresión](manage-suppression-rules.md)
- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigación de un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión](investigate-user.md)
