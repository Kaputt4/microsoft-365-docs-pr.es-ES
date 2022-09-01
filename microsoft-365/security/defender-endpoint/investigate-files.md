---
title: Investigación de archivos Microsoft Defender para punto de conexión
description: Use las opciones de investigación para obtener detalles sobre los archivos asociados a alertas, comportamientos o eventos.
keywords: investigación, investigación, archivo, actividad malintencionada, motivación de ataque, análisis profundo, informe de análisis profundo
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
ms.openlocfilehash: f590d8dfba215117269687ac952f9c181c570c7a
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67519916"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigación de un archivo asociado a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatefiles-abovefoldlink)

Investigue los detalles de un archivo asociado a una alerta, un comportamiento o un evento específicos para ayudar a determinar si el archivo presenta actividades malintencionadas, identificar la motivación del ataque y comprender el posible ámbito de la infracción.

Hay muchas maneras de acceder a la página de perfil detallada de un archivo específico. Por ejemplo, puede usar la característica de búsqueda, hacer clic en un vínculo del **árbol proceso de alerta**, **el gráfico de incidentes**, la **escala de tiempo de artefactos** o seleccionar un evento que aparece en la **escala de tiempo del dispositivo**.

Una vez en la página de perfil detallada, puede cambiar entre los diseños de página nuevo y antiguo si cambia la **nueva página Archivo**. En el resto de este artículo se describe el diseño de página más reciente.

Puede obtener información de las secciones siguientes en la vista de archivos:

- Detalles del archivo, Detección de malware, Prevalencia de archivos
- Metadatos de PE de archivo (si existe)
- Análisis detallado
- Alertas
- Observado en la organización
- Análisis detallado
- Nombres de archivo

También puede realizar acciones en un archivo desde esta página.

## <a name="file-actions"></a>Acciones de archivo

A lo largo de la parte superior de la página de perfil, encima de las tarjetas de información de archivo. Entre las acciones que puede realizar aquí se incluyen:

- Detener y poner en cuarentena un archivo
- Indicador de adición y edición
- Descargar archivo
- Consultar a un experto en amenazas
- Centro de actividades

Para obtener más información sobre estas acciones, consulte [Acción de respuesta en un archivo](respond-file-alerts.md).

## <a name="file-details-malware-detection-and-file-prevalence"></a>Detalles del archivo, detección de malware y prevalencia de archivos

Los detalles del archivo, el incidente, la detección de malware y las tarjetas de prevalencia de archivos muestran varios atributos sobre el archivo.

Verá detalles como md5 del archivo, la relación de detección total de virus y la detección de Antivirus de Microsoft Defender si está disponible y la prevalencia del archivo.

La tarjeta de prevalencia de archivos muestra dónde se ha visto el archivo en los dispositivos de la organización y en todo el mundo. Puede girar fácilmente a los primeros y últimos dispositivos en los que se ha visto el archivo y continuar la investigación en la escala de tiempo del dispositivo. 

> [!NOTE]
> Es posible que distintos usuarios vean valores diferentes en la sección *dispositivos de la organización* de la tarjeta de prevalencia de archivos. Esto se debe a que la tarjeta muestra información basada en el ámbito de RBAC que tiene un usuario. Es decir, si a un usuario se le ha concedido visibilidad en un conjunto específico de dispositivos, solo verá la prevalencia de la organización del archivo en esos dispositivos.

:::image type="content" source="images/atp-file-information.png" alt-text="La información del archivo" lightbox="images/atp-file-information.png":::

## <a name="alerts"></a>Alertas

La pestaña **Alertas** proporciona una lista de alertas asociadas al archivo, así como el incidente al que está vinculada la alerta. Esta lista cubre gran parte de la misma información que la cola de alertas, excepto para el grupo de dispositivos, si existe, al que pertenece el dispositivo afectado. Para elegir qué tipo de información se muestra, seleccione **Personalizar columnas** en la barra de herramientas situada encima de los encabezados de columna.

:::image type="content" source="images/atp-alerts-related-to-file.png" alt-text="Las alertas relacionadas con la sección de archivo" lightbox="images/atp-alerts-related-to-file.png":::

## <a name="observed-in-organization"></a>Observado en la organización

La pestaña **Observada en la organización** permite especificar un intervalo de fechas para ver qué dispositivos se han observado con el archivo.

> [!NOTE]
> Esta pestaña mostrará un número máximo de 100 dispositivos. Para ver _todos los_ dispositivos con el archivo, exporte la pestaña a un archivo CSV; para ello, seleccione **Exportar** en el menú de acciones situado encima de los encabezados de columna de la pestaña.

:::image type="content" source="images/atp-observed-machines.png" alt-text="Los dispositivos observados más recientes con el archivo" lightbox="images/atp-observed-machines.png":::

Use el control deslizante o el selector de intervalos para especificar rápidamente un período de tiempo que desea comprobar si hay eventos relacionados con el archivo. Puede recibir asistencia de la indicación de alertas en el intervalo. Puede especificar una ventana de tiempo tan pequeña como un solo día. Esto le permitirá ver solo los archivos que se comunicaron con esa dirección IP en ese momento, lo que reduce drásticamente el desplazamiento y la búsqueda innecesarios.

## <a name="deep-analysis"></a>Análisis detallado

La pestaña **Análisis profundo** le permite [enviar el archivo para un análisis profundo](respond-file-alerts.md#deep-analysis), para descubrir más detalles sobre el comportamiento del archivo, así como el efecto que está teniendo dentro de las organizaciones. Después de enviar el archivo, el informe de análisis profundo aparecerá en esta pestaña una vez que estén disponibles los resultados. Si el análisis profundo no encontró nada, el informe estará vacío y el espacio de resultados permanecerá en blanco.

:::image type="content" source="images/submit-file.png" alt-text="Pestaña Análisis profundo" lightbox="images/submit-file.png":::

## <a name="file-names"></a>Nombres de archivo

En la pestaña **Nombres de** archivo se enumeran todos los nombres que se han observado que el archivo debe usarse dentro de las organizaciones.

:::image type="content" source="images/atp-file-names.png" alt-text="Pestaña Nombres de archivo" lightbox="images/atp-file-names.png":::

## <a name="action-center"></a>Centro de actividades

El **Centro de acciones** muestra el centro de acciones filtrado en un archivo específico, para que pueda ver las acciones pendientes y el historial de acciones realizadas en el archivo.

## <a name="related-topics"></a>Temas relacionados

- [Visualización y organización de la cola de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigación de un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión](investigate-user.md)
- [Realizar acciones de respuesta en un archivo](respond-file-alerts.md)
