---
title: Administrar alertas de Microsoft Defender para puntos de conexión
description: Cambie el estado de las alertas, cree reglas de supresión para ocultar alertas, enviar comentarios y revisar el historial de cambios de alertas individuales con el menú Administrar alerta.
keywords: administrar alertas, administrar, alertas, estado, nuevo, en curso, resuelto, resolver alertas, suprimir, supresión, reglas, contexto, historial, comentarios, cambios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187006"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Administrar alertas de Microsoft Defender para puntos de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender for Endpoint le notifica posibles eventos malintencionados, atributos e información contextual a través de alertas. En el panel de operaciones de seguridad se muestra un resumen de las alertas nuevas y se puede obtener acceso a todas las alertas de la cola **De alertas.**

Puedes administrar alertas seleccionando una alerta en  la cola de alertas **o** en la pestaña Alertas de la página Dispositivo de un dispositivo individual.

Al seleccionar una alerta en cualquiera de esos lugares, se muestra el panel **de administración de alertas**.

![Imagen del panel de administración de alertas y la cola de alertas](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>Vincular a otro incidente
Puede crear un nuevo incidente a partir de la alerta o vínculo a un incidente existente. 

## <a name="assign-alerts"></a>Asignar alertas
Si aún no se ha asignado una alerta, puedes seleccionar **Asignarme** para asignarte la alerta.


## <a name="suppress-alerts"></a>Suprimir alertas
Es posible que haya escenarios en los que necesite suprimir las alertas para que no aparezcan en el Centro de seguridad de Microsoft Defender. Defender for Endpoint te permite crear reglas de supresión para alertas específicas que se sabe que son inocuas, como herramientas o procesos conocidos de la organización.

Las reglas de supresión se pueden crear a partir de una alerta existente. Se pueden deshabilitar y volver a habilitar si es necesario.

Cuando se crea una regla de supresión, tendrá efecto desde el punto en que se crea la regla. La regla no afectará a las alertas existentes ya en la cola, antes de la creación de la regla. La regla solo se aplicará en alertas que cumplan las condiciones establecidas después de crear la regla.

Hay dos contextos para una regla de supresión entre las que puede elegir:

- **Suprimir alerta en este dispositivo**
- **Suprimir alerta en mi organización**

El contexto de la regla te permite adaptar lo que se ve en el portal y asegurarte de que solo se desencien alertas de seguridad reales en el portal.

Puede usar los ejemplos de la tabla siguiente para ayudarle a elegir el contexto de una regla de supresión:

| **Context**                           | **Definición**                                                                                                                                              | **Escenarios de ejemplo**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Suprimir alerta en este dispositivo**    | Las alertas con el mismo título de alerta y en ese dispositivo específico solo se suprimirán. <br /><br />El resto de alertas de ese dispositivo no se suprimirán. | <ul><li>Un investigador de seguridad está investigando un script malintencionado que se ha usado para atacar otros dispositivos de la organización.</li><li>Un desarrollador crea regularmente scripts de PowerShell para su equipo.</li></ul> |
| **Suprimir alerta en mi organización** | Las alertas con el mismo título de alerta en cualquier dispositivo se suprimirán.                                                                                         | <ul><li>Todos los usuarios de la organización usan una herramienta administrativa benigna.</li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>Suprimir una alerta y crear una nueva regla de supresión:
Cree reglas personalizadas para controlar cuándo se suprimen o resuelven las alertas. Puede controlar el contexto para cuando se suprime una alerta especificando el título de la alerta, el indicador de compromiso y las condiciones. Después de especificar el contexto, podrá configurar la acción y el ámbito en la alerta. 

1. Seleccione la alerta que desea suprimir. Esto muestra el panel **administración de alertas.**

2.  Seleccione **Crear una regla de supresión**.

    Puede crear una condición de supresión con estos atributos. Se aplica un operador AND entre cada condición, por lo que la supresión se produce solo si se cumplen todas las condiciones.
    
    * Archivo SHA1
    * Nombre de archivo: comodín admitido
    * Ruta de acceso de carpeta: comodín compatible
    * Dirección IP
    * DIRECCIÓN URL: comodín compatible
    * Línea de comandos: comodín compatible

3. Seleccione el **IOC desencadenante**.
    
4. Especifique la acción y el ámbito en la alerta. <br>
   Puede resolver automáticamente una alerta u ocultarla del portal. Las alertas que se resuelven automáticamente aparecerán en la sección resuelta de la cola de alertas, la página de alertas y la escala de tiempo del dispositivo y aparecerán como resueltas en Defender para las API de extremo. <br><br> Las alertas marcadas como ocultas se suprimirán de todo el sistema, tanto en las alertas asociadas del dispositivo como desde el panel y no se transmitirán a través de las API de Defender para puntos de conexión.


5. Escriba un nombre de regla y un comentario.

6. Haga clic en **Guardar**.

#### <a name="view-the-list-of-suppression-rules"></a>Ver la lista de reglas de supresión

1. En el panel de navegación, seleccione **Configuración**  >  **supresión de alertas**.

2. La lista de reglas de supresión muestra todas las reglas que los usuarios de la organización han creado.

Para obtener más información sobre la administración de reglas de supresión, vea [Administrar reglas de supresión](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>Cambiar el estado de una alerta

Puede clasificar las alertas (como **Nuevo**, **En curso** o **Resuelto)** cambiando su estado a medida que avanza la investigación. Esto te ayuda a organizar y administrar cómo tu equipo puede responder a las alertas.

Por ejemplo, un jefe de equipo puede revisar todas las **alertas** Nuevas y decidir asignarlas a la cola **En** curso para un análisis posterior.

Como alternativa, el jefe de equipo  puede asignar la alerta a la cola Resuelto si sabe que la alerta es benigna, procedente de un dispositivo que es irrelevante (por ejemplo, uno que pertenece a un administrador de seguridad) o que se trata a través de una alerta anterior.



## <a name="alert-classification"></a>Clasificación de alertas
Puede elegir no establecer una clasificación o especificar si una alerta es una alerta verdadera o una alerta falsa. Es importante proporcionar la clasificación de verdadero positivo/falso positivo. Esta clasificación se usa para supervisar la calidad de las alertas y hacer que las alertas sea más precisa. El campo "determinación" define fidelidad adicional para una clasificación "verdadero positivo". 

## <a name="add-comments-and-view-the-history-of-an-alert"></a>Agregar comentarios y ver el historial de una alerta
Puede agregar comentarios y ver eventos históricos sobre una alerta para ver los cambios anteriores realizados en la alerta.

Cada vez que se realiza un cambio o comentario en una alerta, se registra en la **sección Comentarios e** historial.

Los comentarios agregados aparecen al instante en el panel.


## <a name="related-topics"></a>Temas relacionados
- [Administrar reglas de supresión](manage-suppression-rules.md)
- [Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender](alerts-queue.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigar una cuenta de usuario en Microsoft Defender para endpoint](investigate-user.md)
