---
title: Pruebe Microsoft 365 Defender capacidades de respuesta a incidentes en un entorno piloto
description: Pruebe las funcionalidades de respuesta a incidentes en Microsoft 365 Defender para priorizar y administrar incidentes, automatizar las investigaciones y usar la búsqueda avanzada en la detección de amenazas.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, Microsoft 365 Defender laboratorio de evaluación, Microsoft 365 Defender  pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
- zerotrust-solution
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64e200acf8726a69e6f71784334345e5603b9677
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384544"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>Pruebe Microsoft 365 Defender capacidades de respuesta a incidentes en un entorno piloto

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 2 del 2](eval-defender-investigate-respond.md) en el proceso de realizar una investigación y respuesta de un incidente en Microsoft 365 Defender mediante un entorno piloto. Para obtener más información sobre este proceso, consulte el artículo [de información general](eval-defender-investigate-respond.md) .

Una vez que haya realizado una [respuesta a incidentes para un ataque simulado](eval-defender-investigate-respond-simulate-attack.md), estas son algunas funcionalidades de Microsoft 365 Defender para explorar:

|Funcionalidad |Descripción |
|:-------|:-----|
| [Priorización de incidentes](#prioritize-incidents) | Use el filtrado y la ordenación de la cola de incidentes para determinar qué incidentes abordar a continuación. |
| [Administración de incidentes](#manage-incidents) | Modifique las propiedades del incidente para garantizar la asignación correcta, agregar etiquetas y comentarios y resolver un incidente. |
| [Investigación y respuesta automatizadas](#examine-automated-investigation-and-response-with-the-action-center) | Use funcionalidades de investigación y respuesta automatizadas (AIR) para ayudar al equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz. El Centro de acciones es una experiencia de "un solo panel de cristal" para las tareas de incidentes y alertas, como la aprobación de acciones de corrección pendientes. |
| [Búsqueda avanzada de amenazas](#use-advanced-hunting) | Use consultas para inspeccionar eventos de forma proactiva en la red y localizar indicadores de amenazas y entidades. También se usa la búsqueda avanzada durante la investigación y corrección de un incidente. |


## <a name="prioritize-incidents"></a>Priorizar incidentes

Puede acceder a la cola de **incidentes desde las alertas de Incidentes & > Incidentes** en el inicio rápido del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La sección Alertas de & incidentes en el portal de Microsoft 365 Defender" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::


En la sección **Incidentes y alertas más recientes** se muestra un gráfico del número de alertas recibidas e incidentes creados en las últimas 24 horas.

Para examinar la lista de incidentes y priorizar su importancia para la asignación y la investigación, puede: 

- Configure columnas personalizables (seleccione **Elegir columnas**) para proporcionarle visibilidad sobre las distintas características del incidente o las entidades afectadas. Esto le ayuda a tomar una decisión informada con respecto a la priorización de incidentes para su análisis.

- Use el filtrado para centrarse en un escenario o una amenaza específicos. La aplicación de filtros en la cola de incidentes puede ayudar a determinar qué incidentes requieren atención inmediata. 

En la cola de incidentes predeterminada, seleccione **Filtros** para ver un panel **Filtros** , desde el que puede especificar un conjunto específico de incidentes. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="El panel Filtros de la sección Alertas de incidentes & en el portal de Microsoft 365 Defender" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

Para obtener más información, vea [Priorizar incidentes](incident-queue.md).

## <a name="manage-incidents"></a>Administrar incidentes

Puede administrar incidentes desde el panel **Administrar incidentes** para un incidente. Por ejemplo:

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="El panel Administrar incidentes de la sección Alertas de incidentes & del portal de Microsoft 365 Defender" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

Puede mostrar este panel desde el vínculo **Administrar incidente** en:

- Panel De propiedades de un incidente en la cola de incidentes.
- **Página resumen** de un incidente.

Estas son las maneras de administrar los incidentes:

- Editar el nombre del incidente

  Cambie el nombre asignado automáticamente en función de los procedimientos recomendados del equipo de seguridad.
  
- Agregar etiquetas de incidente

  Agregue etiquetas que el equipo de seguridad usa para clasificar los incidentes, que se pueden filtrar más adelante.
  
- Asignación del incidente

  Asígnelo a un nombre de cuenta de usuario, que se puede filtrar más adelante.
  
- Resolución de un incidente

  Cierre el incidente una vez corregido.
  
- Establecer su clasificación y determinación

  Clasifique y seleccione el tipo de amenaza al resolver un incidente.
  
- Agregar comentarios

  Use comentarios para el progreso, las notas u otra información en función de los procedimientos recomendados del equipo de seguridad. El historial de comentarios completo está disponible en la opción **Comentarios e historial** de la página de detalles de un incidente.

Para obtener más información, vea [Administrar incidentes](manage-incidents.md).

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>Examen de la investigación y respuesta automatizadas con el Centro de acciones

En función de cómo se configuren las funcionalidades automatizadas de investigación y respuesta para su organización, las acciones de corrección se realizan automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. Todas las acciones, ya sean pendientes o completadas, aparecen en el [Centro](m365d-action-center.md) de acciones, que muestra las acciones de corrección pendientes y completadas para los dispositivos, el correo electrónico & el contenido de colaboración y las identidades en una ubicación.

Por ejemplo:

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro de acciones unificadas en el portal de Microsoft 365 Defender" lightbox="../../media/m3d-action-center-unified.png":::

En el Centro de acciones, puede seleccionar acciones pendientes y, a continuación, aprobarlas o rechazarlas en el panel flotante. Por ejemplo:

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="Panel que muestra las opciones para aprobar o rechazar una acción en el portal de Microsoft 365 Defender" lightbox="../../media/air-actioncenter-itemselected.png":::


Apruebe (o rechace) las acciones pendientes lo antes posible para que las investigaciones automatizadas puedan continuar y completarse de forma oportuna.

Para obtener más información, consulte [Investigación y respuesta automatizadas](m365d-autoir.md) y [Centro de acción](m365d-action-center.md).

## <a name="use-advanced-hunting"></a>Uso de la búsqueda avanzada

> [!NOTE]
> Antes de guiarle por la simulación de búsqueda avanzada, vea el siguiente vídeo para comprender los conceptos avanzados de búsqueda, ver dónde puede encontrarlo en el portal y saber cómo puede ayudarle en sus operaciones de seguridad.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


Si la [simulación de ataque de PowerShell sin archivos opcional](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) era un ataque real que ya había alcanzado la fase de acceso a credenciales, puede usar la búsqueda avanzada en cualquier punto de la investigación para realizar búsquedas proactivas a través de eventos y registros en la red mediante lo que ya sabe de las alertas generadas y las entidades afectadas. 

Por ejemplo, en función de la información de la alerta [de reconocimiento de direcciones IP y usuario (SMB](eval-defender-investigate-respond-simulate-attack.md#alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity)), puede usar la `IdentityDirectoryEvents` tabla para buscar todos los eventos de enumeración de sesión SMB o buscar más actividades de detección en otros protocolos de Microsoft Defender for Identity datos mediante la `IdentityQueryEvents` tabla.


### <a name="hunting-environment-requirements"></a>Requisitos del entorno de búsqueda

Hay un único buzón interno y dispositivo necesarios para esta simulación. También necesitará una cuenta de correo electrónico externa para enviar el mensaje de prueba.

1. Compruebe que el inquilino ha [habilitado Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).
2. Identifique un buzón de destino que se usará para recibir correo electrónico.

   - Este buzón debe supervisarse mediante Microsoft Defender para Office 365

   - El dispositivo del requisito 3 debe tener acceso a este buzón

3. Configuración de un dispositivo de prueba:

    a. Asegúrese de que usa Windows 10 versión 1903 o posterior.

    b. Unir el dispositivo de prueba al dominio de prueba.

    c. [Active antivirus de Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). Si tiene problemas para habilitar el Antivirus de Microsoft Defender, consulte [este tema de solución de problemas](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

    d. [Incorporación a Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Ejecución de la simulación

1. Desde una cuenta de correo electrónico externa, envíe un correo electrónico al buzón identificado en el paso 2 de la sección de requisitos del entorno de búsqueda. Incluya datos adjuntos que se permitirán a través de las directivas de filtro de correo electrónico existentes. Este archivo no tiene que ser malintencionado ni ejecutable. Los tipos de archivo sugeridos son <i>.pdf</i>, <i>.exe</i> (si se permite) o un tipo de documento de Office, como un archivo de Word.

2. Abra el correo electrónico enviado desde el dispositivo configurado como se define en el paso 3 de la sección de requisitos del entorno de búsqueda. Abra los datos adjuntos o guarde el archivo en el dispositivo.

#### <a name="go-hunting"></a>Ir a buscar

1. Abra el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

2. En el panel de navegación, seleccione **Caza > Búsqueda avanzada**.

3. Cree una consulta que comience recopilando eventos de correo electrónico.

   1. Seleccione **Query > New (Consultar > nuevo).**

   1. En el **Email** grupos en **Búsqueda avanzada**, haga doble clic en **EmailEvents**. Debería ver esto en la ventana de consulta.

      ```console
      EmailEvents
      ```

   1. Cambie el período de tiempo de la consulta a las últimas 24 horas. Suponiendo que el correo electrónico que envió cuando ejecutó la simulación anterior fue en las últimas 24 horas, de lo contrario, cambie el período de tiempo según sea necesario.

   1. Seleccione **Ejecutar consulta**. Es posible que tenga resultados diferentes en función del entorno piloto.

      > [!NOTE]
      > Consulte el paso siguiente para ver las opciones de filtrado para limitar la devolución de datos.

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-1.png" alt-text="Página Búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-incident-response-try-1.png":::

        > [!NOTE]
        > La búsqueda avanzada muestra los resultados de la consulta como datos tabulares. También puede optar por ver los datos en otros tipos de formato, como gráficos.

   1. Examine los resultados y vea si puede identificar el correo electrónico que ha abierto. El mensaje puede tardar hasta dos horas en aparecer en la búsqueda avanzada. Para restringir los resultados, puede agregar la condición **where** a la consulta para buscar solo correos electrónicos que tengan "yahoo.com" como su SenderMailFromDomain. Por ejemplo:

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Haga clic en las filas resultantes de la consulta para poder inspeccionar el registro.

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-2.png" alt-text="La sección Inspeccionar registro de la página Búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-incident-response-try-2.png":::

4. Ahora que ha comprobado que puede ver el correo electrónico, agregue un filtro para los datos adjuntos. Céntrese en todos los correos electrónicos con datos adjuntos en el entorno. Para esta simulación, céntrese en los correos electrónicos entrantes, no en los que se envían desde su entorno. Quite los filtros que haya agregado para buscar el mensaje y agregar "| where **AttachmentCount > 0** y **EmailDirection** == **"Inbound""**

   La consulta siguiente le mostrará el resultado con una lista más corta que la consulta inicial para todos los eventos de correo electrónico:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. A continuación, incluya la información sobre los datos adjuntos (como: nombre de archivo, hashes) en el conjunto de resultados. Para ello, únase a la tabla **EmailAttachmentInfo** . Los campos comunes que se usarán para la unión, en este caso **, son NetworkMessageId** y **RecipientObjectId**.

   La consulta siguiente también incluye una línea adicional "| **project-rename EmailTimestamp=Timestamp**" que ayudará a identificar qué marca de tiempo estaba relacionada con el correo electrónico frente a las marcas de tiempo relacionadas con las acciones de archivo que agregará en el paso siguiente.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. A continuación, use el valor **SHA256** de la tabla **EmailAttachmentInfo** para buscar **DeviceFileEvents** (acciones de archivo que se produjeron en el punto de conexión) para ese hash. El campo común aquí será el hash SHA256 para los datos adjuntos.

   La tabla resultante ahora incluye detalles del punto de conexión (Microsoft Defender para punto de conexión), como el nombre del dispositivo, qué acción se realizó (en este caso, filtrada para incluir solo eventos FileCreated) y dónde se almacenó el archivo. También se incluirá el nombre de cuenta asociado al proceso.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   Ahora ha creado una consulta que identificará todos los correos electrónicos entrantes en los que el usuario abrió o guardó los datos adjuntos. También puede refinar esta consulta para filtrar por dominios de remitente específicos, tamaños de archivo, tipos de archivo, etc.

7. Las funciones son un tipo especial de combinación, que le permite extraer más datos de TI sobre un archivo como su prevalencia, firmante e información del emisor, etc. Para obtener más detalles sobre el archivo, use el enriquecimiento de funciones **FileProfile():**

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

#### <a name="create-a-detection"></a>Creación de una detección

Una vez que haya creado una consulta que identifique la información sobre la que desea **recibir una alerta** si se producen en el futuro, puede crear una detección personalizada a partir de la consulta.

Las detecciones personalizadas ejecutarán la consulta según la frecuencia establecida y los resultados de las consultas crearán alertas de seguridad en función de los recursos afectados que elija. Estas alertas se correlacionarán con incidentes y se pueden evaluar como cualquier otra alerta de seguridad generada por uno de los productos.

1. En la página de consulta, quite las líneas 7 y 8 que se agregaron en el paso 7 de las instrucciones de búsqueda de Go y haga clic en **Crear regla de detección**.

   :::image type="content" source="../../media/advanced-hunting-incident-response-try-3.png" alt-text="La sección Edición de consultas de la página Búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-incident-response-try-3.png":::

   > [!NOTE]
   > Si hace clic en **Crear regla de detección** y tiene errores de sintaxis en la consulta, la regla de detección no se guardará. Compruebe la consulta de forma doble para asegurarse de que no hay errores.

2. Rellene los campos necesarios con la información que permitirá al equipo de seguridad comprender la alerta, por qué se generó y qué acciones espera que realice.

   :::image type="content" source="../../media/mtp/fig23.png" alt-text="Página Detalles de la alerta del portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig23.png":::

   Asegúrese de rellenar los campos con claridad para ayudar a dar al siguiente usuario una decisión informada sobre esta alerta de regla de detección.

3. Seleccione qué entidades se ven afectadas en esta alerta. En este caso, seleccione **Dispositivo** y **Buzón**.

   :::image type="content" source="../../media/mtp/fig24.png" alt-text="Página de detalles de entidades afectadas en el portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig24.png":::

4. Determine qué acciones deben realizarse si se desencadena la alerta. En este caso, ejecute un examen antivirus, aunque se podrían realizar otras acciones.

   :::image type="content" source="../../media/mtp/fig25.png" alt-text="Página Acciones del portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig25.png":::

5. Seleccione el ámbito de la regla de alertas. Dado que esta consulta implica dispositivos, los grupos de dispositivos son relevantes en esta detección personalizada según Microsoft Defender para punto de conexión contexto. Al crear una detección personalizada que no incluye dispositivos como entidades afectadas, el ámbito no se aplica.

   :::image type="content" source="../../media/mtp/fig26.png" alt-text="Página Ámbito del portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig26.png":::


   Para este piloto, es posible que desee limitar esta regla a un subconjunto de dispositivos de prueba en el entorno de producción.

6. Seleccione **Crear**. A continuación, seleccione **Reglas de detección personalizadas** en el panel de navegación.

   :::image type="content" source="../../media/mtp/fig27a.png" alt-text="Opción Reglas de detección personalizadas en el portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig27a.png":::

   :::image type="content" source="../../media/mtp/fig27b.png" alt-text="Página que muestra las reglas de detección y los detalles de ejecución en el portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig27b.png":::

   En esta página, puede seleccionar la regla de detección, que abrirá una página de detalles.

   :::image type="content" source="../../media/mtp/fig28.png" alt-text="Página que muestra los detalles de las alertas desencadenadas en el portal de Microsoft 365 Defender" lightbox="../../media/mtp/fig28.png":::


### <a name="expert-training-on-advanced-hunting"></a>Formación de expertos sobre la búsqueda avanzada

**El seguimiento del adversario** es una serie de webcast para nuevos analistas de seguridad y cazadores de amenazas experimentados. Le guía por los conceptos básicos de la búsqueda avanzada hasta crear sus propias consultas sofisticadas. 

Consulte [Obtención de formación de expertos sobre la búsqueda avanzada](advanced-hunting-expert-training.md) para empezar.

### <a name="navigation-you-may-need"></a>Navegación que puede necesitar

[Creación del entorno de evaluación de Microsoft 365 Defender](eval-create-eval-environment.md)
