---
title: Pruebe Microsoft 365 Defender de respuesta a incidentes en un entorno piloto
description: Pruebe las capacidades de respuesta a incidentes en Microsoft 365 Defender priorizar y administrar incidentes, automatizar investigaciones y usar la búsqueda avanzada en la detección de amenazas.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, laboratorio de evaluación de Microsoft 365 Defender Microsoft 365 Defender, piloto, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
localization_priority: Normal
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: aaf30aa5f598fffc5f8f53fc92fef5571b3c851b0bd9e48ef3ca8b60ad9e5e43
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863323"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Pruebe Microsoft 365 Defender de respuesta a incidentes en un entorno piloto

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 2 de 2](eval-defender-investigate-respond.md) en el proceso de realizar una investigación y respuesta de un incidente en Microsoft 365 Defender un entorno piloto. Para obtener más información acerca de este proceso, vea el [artículo de introducción.](eval-defender-investigate-respond.md)

Una vez que haya realizado una respuesta [a incidentes para](eval-defender-investigate-respond-simulate-attack.md)un ataque simulado, estas son algunas Microsoft 365 Defender capacidades para explorar:

|Funcionalidad |Descripción |
|:-------|:-----|
| [Priorizar incidentes](#prioritize-incidents) | Use el filtrado y ordenación de la cola de incidentes para determinar qué incidentes se deben solucionar a continuación. |
| [Administrar incidentes](#manage-incidents) | Modifique las propiedades de incidentes para garantizar la asignación correcta, agregar etiquetas y comentarios y resolver un incidente. |
| [Investigación y respuesta automatizadas](#examine-automated-investigation-and-response-with-the-action-center) | Capacidades de investigación y respuesta automatizadas (AIR) que pueden ayudar a su equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz. El Centro de acciones es una experiencia de "panel único de cristal" para las tareas de incidentes y alertas, como la aprobación de acciones de corrección pendientes. |
| [Búsqueda avanzada de amenazas](#advanced-hunting) | Una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar proactivamente los eventos de la red y localizar indicadores y entidades de amenazas. También se usa la búsqueda avanzada durante la investigación y la corrección de un incidente. |


## <a name="prioritize-incidents"></a>Priorizar incidentes

You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)). Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Ejemplo de la cola de incidentes":::

La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

Para examinar la lista de incidentes y priorizar su importancia para la asignación e investigación, puede: 

- Configure columnas personalizables (seleccione **Elegir columnas**) para darle visibilidad a las distintas características del incidente o las entidades afectadas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.

- Use el filtrado para centrarse en un escenario o amenaza específicos. La aplicación de filtros en la cola de incidentes puede ayudar a determinar qué incidentes requieren atención inmediata. 

En la cola de incidentes predeterminada, seleccione **Filtros** para ver un panel **Filtros,** desde el que puede especificar un conjunto específico de incidentes. Aquí le mostramos un ejemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Ejemplo del panel de filtros de la cola de incidentes":::

Para obtener más información, vea [Priorizar incidentes](incident-queue.md).

## <a name="manage-incidents"></a>Administrar incidentes

Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Ejemplo del panel Administrar incidentes de un incidente":::

Puede mostrar este panel desde el vínculo **Administrar incidentes** en:

- Panel de propiedades de un incidente en la cola de incidentes.
- **Página de** resumen de un incidente.

Estas son las formas en que puede administrar sus incidentes:

- Editar el nombre del incidente

  Cambie el nombre asignado de formautomática en función de los procedimientos recomendados del equipo de seguridad.
  
- Agregar etiquetas de incidente

  Agregue etiquetas que el equipo de seguridad usa para clasificar incidentes, que se pueden filtrar más adelante.
  
- Asignar el incidente a usted mismo

  Asígnelo al nombre de la cuenta de usuario, que se puede filtrar más adelante.
  
- Resolver un incidente

  Cierre el incidente después de que se haya corregido.
  
- Establecer su clasificación y determinación

  Clasificar y seleccionar el tipo de amenaza al resolver un incidente.
  
- Agregar comentarios

  Use comentarios para el progreso, las notas u otra información basada en los procedimientos recomendados del equipo de seguridad. El historial de comentarios completo está disponible en la **opción Comentarios e** historial de la página de detalles de un incidente.

Para obtener más información, vea [Manage incidents](manage-incidents.md).

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>Examinar la investigación automatizada y la respuesta con el Centro de acción

En función de cómo se configuren las capacidades automatizadas de investigación y respuesta para su organización, las acciones de corrección se toman automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. Todas las acciones, ya sean pendientes o completadas, se enumeran en el Centro de [acciones,](m365d-action-center.md)que enumera las acciones de corrección pendientes y completadas para los dispositivos, el contenido de colaboración & correo electrónico y las identidades en una ubicación.

Por ejemplo:

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificado en Microsoft 365 Defender":::

En el Centro de acciones, puede seleccionar acciones pendientes y, a continuación, aprobarlas o rechazarlas en el panel desplegable. Por ejemplo:

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Aprobar o rechazar una acción":::

Aprobar (o rechazar) acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.

Para obtener más información, vea [Automated investigation and response](m365d-autoir.md) y Action [Center](m365d-action-center.md).

## <a name="advanced-hunting"></a>Búsqueda avanzada

> [!NOTE]
> Antes de ayudarle a través de la simulación de búsqueda avanzada, vea el siguiente vídeo para comprender los conceptos avanzados de búsqueda, vea dónde puede encontrarlo en el portal y sepa cómo puede ayudarle en sus operaciones de seguridad.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


Si la simulación de ataque de [PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) sin archivos opcional era un ataque real que ya había alcanzado la fase de acceso a credenciales, puede usar la búsqueda avanzada en cualquier momento de la investigación para buscar proactivamente en eventos y registros de la red con lo que ya sabe de las alertas generadas y las entidades afectadas. 

Por ejemplo, en función de la información de la alerta de reconocimiento de direcciones IP y de usuario [(SMB),](eval-defender-investigate-respond-simulate-attack.md#alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity) puede usar la tabla para buscar todos los eventos de enumeración de sesiones SMB o encontrar más actividades de detección en otros protocolos de Microsoft Defender para datos de identidad mediante la `IdentityDirectoryEvents` `IdentityQueryEvents` tabla.


### <a name="hunting-environment-requirements"></a>Requisitos del entorno de búsqueda

Hay un único buzón interno y un dispositivo necesarios para esta simulación. También necesitará una cuenta de correo electrónico externa para enviar el mensaje de prueba.

1. Compruebe que el espacio empresarial [ha habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).
2. Identificar un buzón de destino que se usará para recibir correo electrónico.

   - Microsoft Defender debe supervisar este buzón Office 365

   - El dispositivo del requisito 3 debe tener acceso a este buzón

3. Configurar un dispositivo de prueba:

    a. Asegúrese de que está usando Windows 10 versión 1903 o posterior.

    b. Une el dispositivo de prueba al dominio de prueba.

    c. [Active la Antivirus de Windows Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Si tiene problemas para habilitar Antivirus de Windows Defender, consulte [este tema de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).

    d. [Incorporación a Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Ejecutar la simulación

1. Desde una cuenta de correo electrónico externa, envíe un correo electrónico al buzón identificado en el paso 2 de la sección de requisitos del entorno de búsqueda. Incluya datos adjuntos que se permitirán a través de las directivas de filtro de correo electrónico existentes. Este archivo no necesita ser malintencionado ni ejecutable. Los tipos de archivo <i>sugeridos.pdf</i>, <i>.exe</i> (si está permitido) o un tipo de documento Office como un archivo de Word.

2. Abra el correo electrónico enviado desde el dispositivo configurado como se define en el paso 3 de la sección de requisitos del entorno de búsqueda. Abra los datos adjuntos o guarde el archivo en el dispositivo.

#### <a name="go-hunting"></a>Ir a buscar

1. Abra el [portal Microsoft 365 Defender](https://security.microsoft.com/).

2. En el panel de navegación, seleccione **Buscar > Búsqueda avanzada.**

3. Cree una consulta que comience recopilando eventos de correo electrónico.

   1. Seleccione **Consulta > Nuevo**.

   1. En los **grupos de** correo electrónico en **Búsqueda avanzada,** haga doble clic en **EmailEvents**. Debería verlo en la ventana de consulta.

      ```console
      EmailEvents
      ```

   1. Cambie el período de tiempo de la consulta a las últimas 24 horas. Suponiendo que el correo electrónico que envió al realizar la simulación anterior fue en las últimas 24 horas, cambie el período de tiempo según sea necesario.

   1. Seleccione **Ejecutar consulta**. Es posible que tenga resultados diferentes en función del entorno piloto.

      > [!NOTE]
      > Consulta el siguiente paso para filtrar opciones para limitar la devolución de datos.

      ![Ejemplo de los resultados avanzados de la consulta de búsqueda](../../media/mtp/fig19.png)

        > [!NOTE]
        > La búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede optar por ver los datos en otros tipos de formato, como gráficos.

   1. Vea los resultados y vea si puede identificar el correo electrónico que abrió. El mensaje puede tardar hasta dos horas en aparecer en la búsqueda avanzada. Para restringir los resultados, puede agregar la condición **where** a la consulta para buscar solo correos electrónicos que tengan "yahoo.com" como senderMailFromDomain. Aquí le mostramos un ejemplo.

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Haga clic en las filas resultantes de la consulta para poder inspeccionar el registro.

      ![Ejemplo del panel lateral del registro de inspección que se abre cuando se selecciona un resultado de búsqueda avanzada](../../media/mtp/fig21.png)

4. Ahora que ha comprobado que puede ver el correo electrónico, agregue un filtro para los datos adjuntos. Céntrate en todos los correos electrónicos con datos adjuntos en el entorno. Para esta simulación, céntrate en los correos electrónicos entrantes, no en los que se envían desde el entorno. Quite los filtros que haya agregado para buscar el mensaje y agregar "| donde **AttachmentCount > 0** y **EmailDirection**  ==  **"Inbound""**

   La siguiente consulta le mostrará el resultado con una lista más corta que la consulta inicial para todos los eventos de correo electrónico:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. A continuación, incluya la información sobre los datos adjuntos (como: nombre de archivo, hashes) en el conjunto de resultados. Para ello, únase a la **tabla EmailAttachmentInfo.** Los campos comunes que se usan para unirse, en este caso son **NetworkMessageId** y **RecipientObjectId**.

   La siguiente consulta también incluye una línea adicional "| **project-rename EmailTimestamp=Timestamp**" que le ayudará a identificar qué marca de tiempo estaba relacionada con el correo electrónico y las marcas de tiempo relacionadas con las acciones de archivo que agregará en el paso siguiente.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. A continuación, use el valor **SHA256** de la **tabla EmailAttachmentInfo** para buscar **DeviceFileEvents** (acciones de archivo que se han producido en el extremo) para ese hash. El campo común aquí será el hash SHA256 para los datos adjuntos.

   La tabla resultante ahora incluye detalles del punto de conexión (Microsoft Defender para endpoint), como el nombre del dispositivo, qué acción se hizo (en este caso, filtrada para incluir solo eventos FileCreated) y dónde se almacenaba el archivo. También se incluirá el nombre de cuenta asociado al proceso.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Ahora ha creado una consulta que identificará todos los correos electrónicos entrantes en los que el usuario abrió o guardó los datos adjuntos. También puede refinar esta consulta para filtrar para dominios de remitente específicos, tamaños de archivo, tipos de archivo, entre otros.

7. Las funciones son un tipo especial de unión, lo que te permite extraer más datos de TI sobre un archivo como su prevalencia, la información del firmante y el emisor, etc. Para obtener más detalles sobre el archivo, use el enriquecimiento de la función **FileProfile():**

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Crear una detección

Una vez que haya creado una consulta que  identifique la información que le gustaría recibir alerta sobre si se producirían en el futuro, puede crear una detección personalizada a partir de la consulta.

Las detecciones personalizadas ejecutarán la consulta según la frecuencia que establezca y los resultados de las consultas crearán alertas de seguridad, en función de los activos afectados que elija. Estas alertas se correlacionarán con incidentes y se pueden triager como cualquier otra alerta de seguridad generada por uno de los productos.

1. En la página de consulta, quite las líneas 7 y 8 que se agregaron en el paso 7 de las instrucciones Ir a buscar y haga clic en **Crear regla de detección.**

   ![Ejemplo de dónde puede hacer clic en Crear regla de detección en la página de búsqueda avanzada](../../media/mtp/fig22.png)

   > [!NOTE]
   > Si hace clic en **Crear regla de detección** y tiene errores de sintaxis en la consulta, la regla de detección no se guardará. Compruebe doblemente la consulta para asegurarse de que no hay errores.

2. Rellene los campos requeridos con la información que permitirá al equipo de seguridad comprender la alerta, por qué se generó y qué acciones espera que lleve a cabo.

   ![Ejemplo de la página crear regla de detección donde puede definir los detalles de la alerta](../../media/mtp/fig23.png)

   Asegúrese de rellenar los campos con claridad para ayudar a dar al siguiente usuario una decisión fundamentada sobre esta alerta de regla de detección

3. Seleccione las entidades que se verán afectadas en esta alerta. En este caso, seleccione **Dispositivo** y **buzón**.

   ![Ejemplo de la página crear regla de detección donde puede elegir los parámetros de las entidades afectadas](../../media/mtp/fig24.png)

4. Determine qué acciones deben tener lugar si se desencadena la alerta. En este caso, ejecute un examen antivirus, aunque se podrían realizar otras acciones.

   ![Ejemplo de la página crear regla de detección en la que puede ejecutar un examen antivirus cuando se desencadena una alerta para ayudar a solucionar amenazas](../../media/mtp/fig25.png)

5. Seleccione el ámbito de la regla de alerta. Dado que esta consulta implica dispositivos, los grupos de dispositivos son relevantes en esta detección personalizada según el contexto de Microsoft Defender para endpoint. Al crear una detección personalizada que no incluya dispositivos como entidades afectadas, el ámbito no se aplica.

   ![Ejemplo de la página crear regla de detección donde puede establecer el ámbito de la regla de alerta administra las expectativas de los resultados que verá](../../media/mtp/fig26.png)

   Para este piloto, es posible que quieras limitar esta regla a un subconjunto de dispositivos de prueba en el entorno de producción.

6. Seleccione **Crear**. A continuación, **seleccione Reglas de detección personalizadas** en el panel de navegación.

   ![Ejemplo de la opción Reglas de detección personalizadas en el menú](../../media/mtp/fig27a.png)

   ![Ejemplo de la página de reglas de detección que muestra los detalles de regla y ejecución](../../media/mtp/fig27b.png)

   En esta página, puede seleccionar la regla de detección, que abrirá una página de detalles.

   ![Ejemplo de la página de datos adjuntos de correo electrónico donde puede ver el estado de la ejecución de la regla, alertas y acciones desencadenadas, editar la detección, y así sucesivamente](../../media/mtp/fig28.png)

<!--

### Advanced hunting walk-through exercises

To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities, and create custom detections and remediation actions.

> [!NOTE]
> Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.

|Title|Description|Download MP4|Watch on YouTube|CSL file to use|
|---|---|---|---|---|
|Episode 1: KQL fundamentals|We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender. Learn about available advanced hunting data and basic KQL syntax and operators.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episode 1: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episode 2: Joins|We'll continue learning about data in advanced hunting and how to join tables together. Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episode 2: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episode 3: Summarizing, pivoting, and visualizing data|Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing. In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema. We turn our datasets into charts that can help improve analysis.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episode 3: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episode 4: Let's hunt! Applying KQL to incident tracking|Time to track some attacker activity! In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack. Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episode 4: CSL file in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

--> 

### <a name="expert-training-on-advanced-hunting"></a>Formación de expertos sobre la búsqueda avanzada

**El seguimiento del adversario es** una serie de difusión por web para nuevos analistas de seguridad y expertos en amenazas. Le guía a través de los conceptos básicos de la búsqueda avanzada hasta la creación de sus propias consultas sofisticadas. 

Consulta [Obtener formación de expertos sobre la búsqueda avanzada](advanced-hunting-expert-training.md) para empezar.

### <a name="navigation-you-may-need"></a>Navegación que puede necesitar

[Crear el entorno Microsoft 365 Defender evaluación](eval-create-eval-environment.md)
