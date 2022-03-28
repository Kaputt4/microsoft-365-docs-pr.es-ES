---
title: Pruebe Microsoft 365 Defender capacidades de respuesta a incidentes en un entorno piloto
description: Pruebe las capacidades de respuesta a incidentes Microsoft 365 Defender priorizar y administrar incidentes, automatizar investigaciones y usar la búsqueda avanzada en la detección de amenazas.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, Microsoft 365 Defender de evaluación, Microsoft 365 Defender  pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0ad2fc9a1566e7816b3ff806b7d07ac29347cc89
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754768"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Pruebe Microsoft 365 Defender capacidades de respuesta a incidentes en un entorno piloto

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 2 de 2](eval-defender-investigate-respond.md) en el proceso de realizar una investigación y respuesta de un incidente en Microsoft 365 Defender un entorno piloto. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-investigate-respond.md) .

Una vez que haya realizado una respuesta [a incidentes para un ataque simulado](eval-defender-investigate-respond-simulate-attack.md), estas son algunas Microsoft 365 Defender capacidades para explorar:

|Funcionalidad |Descripción |
|:-------|:-----|
| [Priorización de incidentes](#prioritize-incidents) | Use el filtrado y ordenación de la cola de incidentes para determinar qué incidentes se deben solucionar a continuación. |
| [Administración de incidentes](#manage-incidents) | Modifique las propiedades de incidentes para garantizar la asignación correcta, agregar etiquetas y comentarios y resolver un incidente. |
| [Investigación y respuesta automatizadas](#examine-automated-investigation-and-response-with-the-action-center) | Use las capacidades de investigación y respuesta automatizadas (AIR) para ayudar a su equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz. El Centro de acciones es una experiencia de "panel único de cristal" para las tareas de incidentes y alertas, como la aprobación de acciones de corrección pendientes. |
| [Búsqueda avanzada de amenazas](#use-advanced-hunting) | Use consultas para inspeccionar proactivamente los eventos de la red y localizar indicadores y entidades de amenazas. También se usa la búsqueda avanzada durante la investigación y la corrección de un incidente. |


## <a name="prioritize-incidents"></a>Priorizar incidentes

Puede acceder a la cola de incidentes desde **Incidentes & alertas > incidentes** en el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender incidentes</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La sección Alertas de & incidentes en el portal Microsoft 365 Defender web" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::


La **sección Incidentes y alertas** más recientes muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

Para examinar la lista de incidentes y priorizar su importancia para la asignación e investigación, puede: 

- Configure columnas personalizables (seleccione **Elegir** columnas) para darle visibilidad a las diferentes características del incidente o las entidades afectadas. Esto le ayuda a tomar una decisión fundamentada con respecto a la priorización de incidentes para su análisis.

- Use el filtrado para centrarse en un escenario o amenaza específicos. La aplicación de filtros en la cola de incidentes puede ayudar a determinar qué incidentes requieren atención inmediata. 

En la cola de incidentes predeterminada, seleccione **Filtros** para ver un panel **Filtros** , desde el que puede especificar un conjunto específico de incidentes. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Panel Filtros de la sección Alertas de & incidentes en el portal Microsoft 365 Defender web" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

Para obtener más información, consulte [Priorizar incidentes](incident-queue.md).

## <a name="manage-incidents"></a>Administrar incidentes

Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="El panel Administrar incidentes de la sección Incidentes & alertas en el portal de Microsoft 365 Defender incidentes" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

Puede mostrar este panel desde el vínculo **Administrar incidentes** en:

- Panel de propiedades de un incidente en la cola de incidentes.
- **Página de** resumen de un incidente.

Estas son las formas en que puede administrar sus incidentes:

- Editar el nombre del incidente

  Cambie el nombre asignado automáticamente en función de los procedimientos recomendados del equipo de seguridad.
  
- Agregar etiquetas de incidente

  Agregue etiquetas que el equipo de seguridad usa para clasificar incidentes, que se pueden filtrar más adelante.
  
- Asignar el incidente

  Asígnelo a un nombre de cuenta de usuario, que se puede filtrar más adelante.
  
- Resolver un incidente

  Cierre el incidente después de que se haya corregido.
  
- Establecer su clasificación y determinación

  Clasificar y seleccionar el tipo de amenaza al resolver un incidente.
  
- Agregar comentarios

  Use comentarios para el progreso, las notas u otra información basada en los procedimientos recomendados del equipo de seguridad. El historial de comentarios completo está disponible en la **opción Comentarios e** historial de la página de detalles de un incidente.

Para obtener más información, vea [Administrar incidentes](manage-incidents.md).

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>Examinar la investigación automatizada y la respuesta con el Centro de acción

En función de cómo se configuren las capacidades automatizadas de investigación y respuesta para su organización, las acciones de corrección se toman automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. Todas las acciones, ya sean pendientes o completadas, se enumeran en el Centro de [acciones, que](m365d-action-center.md) enumera las acciones de corrección pendientes y completadas para los dispositivos, el correo electrónico & contenido de colaboración y las identidades en una ubicación.

Por ejemplo:

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="El Centro de acciones unificadas en el portal de Microsoft 365 Defender web" lightbox="../../media/m3d-action-center-unified.png":::

En el Centro de acciones, puede seleccionar acciones pendientes y, a continuación, aprobarlas o rechazarlas en el panel desplegable. Por ejemplo:

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Panel que muestra las opciones para aprobar o rechazar una acción en el portal de Microsoft 365 Defender web" lightbox="../../media/air-actioncenter-itemselected.png":::


Aprobar (o rechazar) acciones pendientes tan pronto como sea posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.

Para obtener más información, vea [Automated investigation and response](m365d-autoir.md) y [Action Center](m365d-action-center.md).

## <a name="use-advanced-hunting"></a>Usar la búsqueda avanzada

> [!NOTE]
> Antes de ayudarle a través de la simulación de búsqueda avanzada, vea el siguiente vídeo para comprender los conceptos avanzados de búsqueda, vea dónde puede encontrarlo en el portal y sepa cómo puede ayudarle en sus operaciones de seguridad.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


Si la simulación de ataque de [PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) sin archivos opcional era un ataque real que ya había alcanzado la fase de acceso a credenciales, puede usar la búsqueda avanzada en cualquier momento de la investigación para buscar proactivamente en eventos y registros de la red con lo que ya sabe de las alertas generadas y las entidades afectadas. 

Por ejemplo, en función de la información de la alerta de reconocimiento de direcciones IP y de usuario [(SMB](eval-defender-investigate-respond-simulate-attack.md#alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity) ), `IdentityDirectoryEvents` puede usar la tabla para buscar todos los eventos de enumeración de sesiones SMB o encontrar más actividades de detección en otros protocolos de Microsoft Defender `IdentityQueryEvents` para datos de identidad mediante la tabla.


### <a name="hunting-environment-requirements"></a>Requisitos del entorno de búsqueda

Hay un único buzón interno y un dispositivo necesarios para esta simulación. También necesitará una cuenta de correo electrónico externa para enviar el mensaje de prueba.

1. Compruebe que el inquilino ha [habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).
2. Identificar un buzón de destino que se usará para recibir correo electrónico.

   - Microsoft Defender debe supervisar este buzón Office 365

   - El dispositivo del requisito 3 debe tener acceso a este buzón

3. Configurar un dispositivo de prueba:

    a. Asegúrese de que usa Windows 10 versión 1903 o posterior.

    b. Une el dispositivo de prueba al dominio de prueba.

    c. [Active Antivirus de Windows Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Si tiene problemas para habilitar Antivirus de Windows Defender, consulte [este tema de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

    d. [Incorporación a Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Ejecutar la simulación

1. Desde una cuenta de correo electrónico externa, envíe un correo electrónico al buzón identificado en el paso 2 de la sección de requisitos del entorno de búsqueda. Incluya datos adjuntos que se permitirán a través de las directivas de filtro de correo electrónico existentes. Este archivo no necesita ser malintencionado ni ejecutable. Los tipos de archivo <i> sugeridos.pdf</i>, <i>.exe</i> (si está permitido) o un tipo de documento Office como un archivo de Word.

2. Abra el correo electrónico enviado desde el dispositivo configurado como se define en el paso 3 de la sección de requisitos del entorno de búsqueda. Abra los datos adjuntos o guarde el archivo en el dispositivo.

#### <a name="go-hunting"></a>Ir a buscar

1. Abra el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender web</a>.

2. En el panel de navegación, seleccione **Buscar > Búsqueda avanzada**.

3. Cree una consulta que comience recopilando eventos de correo electrónico.

   1. Seleccione **Nuevo > consulta**.

   1. En los **grupos de** correo electrónico en **Búsqueda avanzada**, haga doble clic en **EmailEvents**. Debería verlo en la ventana de consulta.

      ```console
      EmailEvents
      ```

   1. Cambie el período de tiempo de la consulta a las últimas 24 horas. Suponiendo que el correo electrónico que envió al realizar la simulación anterior fue en las últimas 24 horas, cambie el período de tiempo según sea necesario.

   1. Seleccione **Ejecutar consulta**. Es posible que tenga resultados diferentes en función del entorno piloto.

      > [!NOTE]
      > Consulta el siguiente paso para filtrar opciones para limitar la devolución de datos.

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-1.png" alt-text="La página Búsqueda avanzada en el portal Microsoft 365 Defender búsqueda avanzada" lightbox="../../media/advanced-hunting-incident-response-try-1.png":::

        > [!NOTE]
        > La búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede optar por ver los datos en otros tipos de formato, como gráficos.

   1. Vea los resultados y vea si puede identificar el correo electrónico que abrió. El mensaje puede tardar hasta dos horas en aparecer en la búsqueda avanzada. Para restringir los resultados, puede agregar la condición **where** a la consulta para buscar solo correos electrónicos que tengan "yahoo.com" como senderMailFromDomain. Por ejemplo:

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Haga clic en las filas resultantes de la consulta para poder inspeccionar el registro.

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-2.png" alt-text="Sección Inspeccionar registro de la página Búsqueda avanzada en el portal Microsoft 365 Defender búsqueda" lightbox="../../media/advanced-hunting-incident-response-try-2.png":::

4. Ahora que ha comprobado que puede ver el correo electrónico, agregue un filtro para los datos adjuntos. Céntrate en todos los correos electrónicos con datos adjuntos en el entorno. Para esta simulación, céntrate en los correos electrónicos entrantes, no en los que se envían desde el entorno. Quite los filtros que haya agregado para buscar el mensaje y agregar "| donde **AttachmentCount > 0** y **EmailDirection** == **"Inbound""**

   La siguiente consulta le mostrará el resultado con una lista más corta que la consulta inicial para todos los eventos de correo electrónico:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. A continuación, incluya la información sobre los datos adjuntos (como: nombre de archivo, hashes) en el conjunto de resultados. Para ello, únase a la **tabla EmailAttachmentInfo** . Los campos comunes que se usan para unirse, en este caso son **NetworkMessageId** y **RecipientObjectId**.

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

7. Las funciones son un tipo especial de unión, lo que te permite extraer más datos de TI sobre un archivo como su prevalencia, la información del firmante y el emisor, etc. Para obtener más detalles sobre el archivo, use el **enriquecimiento de la función FileProfile(** ):

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

Una vez que haya creado una consulta que identifique la información que le gustaría recibir alerta  sobre si se producirían en el futuro, puede crear una detección personalizada a partir de la consulta.

Las detecciones personalizadas ejecutarán la consulta según la frecuencia que establezca y los resultados de las consultas crearán alertas de seguridad, en función de los activos afectados que elija. Estas alertas se correlacionarán con incidentes y se pueden triager como cualquier otra alerta de seguridad generada por uno de los productos.

1. En la página de consulta, quite las líneas 7 y 8 que se agregaron en el paso 7 de las instrucciones Ir a buscar y haga clic en **Crear regla de detección**.

   :::image type="content" source="../../media/advanced-hunting-incident-response-try-3.png" alt-text="La sección Edición de consultas de la página Búsqueda avanzada en el portal Microsoft 365 Defender búsqueda" lightbox="../../media/advanced-hunting-incident-response-try-3.png":::

   > [!NOTE]
   > Si hace clic en **Crear regla de detección** y tiene errores de sintaxis en la consulta, la regla de detección no se guardará. Compruebe doblemente la consulta para asegurarse de que no hay errores.

2. Rellene los campos requeridos con la información que permitirá al equipo de seguridad comprender la alerta, por qué se generó y qué acciones espera que lleve a cabo.

   :::image type="content" source="../../media/mtp/fig23.png" alt-text="La página Detalles de la alerta en el portal Microsoft 365 Defender alerta" lightbox="../../media/mtp/fig23.png":::

   Asegúrese de rellenar los campos con claridad para ayudar a dar al siguiente usuario una decisión fundamentada sobre esta alerta de regla de detección

3. Seleccione las entidades que se verán afectadas en esta alerta. En este caso, seleccione **Dispositivo** y **buzón**.

   :::image type="content" source="../../media/mtp/fig24.png" alt-text="Página de detalles de entidades afectadas en el portal de Microsoft 365 Defender web" lightbox="../../media/mtp/fig24.png":::

4. Determine qué acciones deben tener lugar si se desencadena la alerta. En este caso, ejecute un examen antivirus, aunque se podrían realizar otras acciones.

   :::image type="content" source="../../media/mtp/fig25.png" alt-text="La página Acciones del portal de Microsoft 365 Defender web" lightbox="../../media/mtp/fig25.png":::

5. Seleccione el ámbito de la regla de alerta. Dado que esta consulta implica dispositivos, los grupos de dispositivos son relevantes en esta detección personalizada según el contexto de Microsoft Defender para endpoint. Al crear una detección personalizada que no incluya dispositivos como entidades afectadas, el ámbito no se aplica.

   :::image type="content" source="../../media/mtp/fig26.png" alt-text="La página Ámbito del portal Microsoft 365 Defender web" lightbox="../../media/mtp/fig26.png":::


   Para este piloto, es posible que quieras limitar esta regla a un subconjunto de dispositivos de prueba en el entorno de producción.

6. Seleccione **Crear**. A continuación, **seleccione Reglas de detección personalizadas** en el panel de navegación.

   :::image type="content" source="../../media/mtp/fig27a.png" alt-text="La opción Reglas de detección personalizadas en el portal Microsoft 365 Defender de detección" lightbox="../../media/mtp/fig27a.png":::

   :::image type="content" source="../../media/mtp/fig27b.png" alt-text="La página que muestra las reglas de detección y los detalles de ejecución en el portal Microsoft 365 Defender búsqueda" lightbox="../../media/mtp/fig27b.png":::

   En esta página, puede seleccionar la regla de detección, que abrirá una página de detalles.

   :::image type="content" source="../../media/mtp/fig28.png" alt-text="La página que muestra los detalles de las alertas desencadenadas en el portal Microsoft 365 Defender datos" lightbox="../../media/mtp/fig28.png":::


### <a name="expert-training-on-advanced-hunting"></a>Formación de expertos sobre la búsqueda avanzada

**El seguimiento del adversario es** una serie de difusión por web para nuevos analistas de seguridad y expertos en amenazas. Le guía a través de los conceptos básicos de la búsqueda avanzada hasta la creación de sus propias consultas sofisticadas. 

Consulta [Obtener formación de expertos sobre la búsqueda avanzada](advanced-hunting-expert-training.md) para empezar.

### <a name="navigation-you-may-need"></a>Navegación que puede necesitar

[Crear el entorno Microsoft 365 Defender evaluación](eval-create-eval-environment.md)
