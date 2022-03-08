---
title: Investigar archivos de Punto de conexión de Microsoft Defender
description: Use las opciones de investigación para obtener detalles sobre los archivos asociados con alertas, comportamientos o eventos.
keywords: investigar, investigar, archivo, actividad malintencionada, motivación de ataque, análisis profundo, informe de análisis profundo
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 6f93a5ec90404ca28fd47d4115a8ebf8d488216e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322049"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatefiles-abovefoldlink)

Investigue los detalles de un archivo asociado a una alerta, comportamiento o evento específicos para determinar si el archivo muestra actividades malintencionadas, identificar la motivación del ataque y comprender el ámbito potencial de la infracción.

Hay muchas maneras de obtener acceso a la página de perfil detallada de un archivo específico. Por ejemplo, puedes usar la característica de búsqueda, hacer clic en un vínculo del árbol del proceso de **alerta, gráfico** de **incidentes, escala** de tiempo de artefactos o seleccionar un evento que aparece en la escala de tiempo **del dispositivo**. 

Una vez en la página de perfil detallada, puede cambiar entre los diseños de página nuevos y antiguos alternando la **nueva página Archivo**. El resto de este artículo describe el diseño de página más reciente.

Puede obtener información de las siguientes secciones en la vista de archivos:

- Detalles del archivo, Detección de malware, Prevalencia de archivos
- Análisis detallado
- Alertas
- Observado en la organización
- Análisis detallado
- Nombres de archivo

También puede realizar acciones en un archivo de esta página.

## <a name="file-actions"></a>Acciones de archivo

En la parte superior de la página de perfil, encima de las tarjetas de información del archivo. Las acciones que puede realizar aquí incluyen:

- Detener y poner en cuarentena un archivo
- Indicador Agregar o editar
- Descargar archivo
- Consultar a un experto en amenazas
- Centro de actividades

Para obtener más información sobre estas acciones, vea [Realizar una acción de respuesta en un archivo](respond-file-alerts.md).

## <a name="file-details-malware-detection-and-file-prevalence"></a>Detalles del archivo, detección de malware y prevalencia de archivos

Los detalles del archivo, incidentes, detección de malware y tarjetas de prevalencia de archivos muestran varios atributos sobre el archivo.

Verá detalles como MD5 del archivo, la relación de detección total de virus y la detección de antivirus de Microsoft Defender si está disponible y la prevalencia del archivo.

La tarjeta de prevalencia de archivos muestra dónde se ha visto el archivo en dispositivos de la organización y en todo el mundo.

> [!NOTE]
> Los diferentes usuarios pueden ver valores distintos en los dispositivos *de la sección de* organización de la tarjeta de prevalencia de archivos. Esto se debe a que la tarjeta muestra información basada en el ámbito RBAC que tiene un usuario. Es decir, si a un usuario se le ha concedido visibilidad en un conjunto específico de dispositivos, solo verá la prevalencia organizativa de archivos en esos dispositivos.

![Imagen de la información del archivo.](images/atp-file-information.png)

## <a name="alerts"></a>Alertas

La **pestaña** Alertas proporciona una lista de alertas asociadas con el archivo. Esta lista cubre gran parte de la misma información que la cola de alertas, excepto para el grupo de dispositivos, si existe, al que pertenece el dispositivo afectado. Puede elegir qué tipo de información se muestra seleccionando Personalizar **columnas de la** barra de herramientas encima de los encabezados de columna.

![Imagen de alertas relacionadas con la sección de archivos.](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a>Observado en la organización

La **pestaña Observed in organization** le permite especificar un intervalo de fechas para ver qué dispositivos se han observado con el archivo.

> [!NOTE]
> Esta pestaña mostrará un número máximo de 100 dispositivos. Para ver _todos los_ dispositivos con el archivo, exporte la pestaña a un archivo CSV **seleccionando Exportar** en el menú de acciones encima de los encabezados de columna de la pestaña.

![Imagen del dispositivo observado más reciente con el archivo.](images/atp-observed-machines.png)

Use el control deslizante o el selector de intervalos para especificar rápidamente un período de tiempo que desea comprobar si hay eventos relacionados con el archivo. Puede especificar una ventana de tiempo tan pequeña como un solo día. Esto le permitirá ver solo los archivos que se comunicaron con esa dirección IP en ese momento, lo que reduce drásticamente el desplazamiento y la búsqueda innecesarios.

## <a name="deep-analysis"></a>Análisis detallado

La **pestaña Análisis** profundo permite enviar el archivo para un análisis [profundo, para](respond-file-alerts.md#deep-analysis) descubrir más detalles sobre el comportamiento del archivo, así como el efecto que está teniendo en sus organizaciones. Después de enviar el archivo, el informe de análisis profundo aparecerá en esta pestaña una vez que estén disponibles los resultados. Si el análisis profundo no encontró nada, el informe estará vacío y el espacio de resultados permanecerá en blanco.

![Imagen de la pestaña análisis profundo.](images/submit-file.png)

## <a name="file-names"></a>Nombres de archivo

La **pestaña Nombres de** archivo enumera todos los nombres que se ha observado que el archivo debe usar en las organizaciones.

![Imagen de la pestaña nombres de archivo.](images/atp-file-names.png)

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de Microsoft Defender para endpoint](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigar una cuenta de usuario en Microsoft Defender para endpoint](investigate-user.md)
- [Realizar acciones de respuesta en un archivo](respond-file-alerts.md)
