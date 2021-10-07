---
title: Comentarios e información de NPS de productos de Microsoft para su organización
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Usa las puntuaciones de net promoter (NPS) de los usuarios finales para ver cómo se sienten acerca de los productos y servicios de Microsoft.
ms.openlocfilehash: afde0abf85cca682a5cda3206fa78d24cafc8cb8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168127"
---
# <a name="microsoft-product-nps-feedback-and-insights-for-your-organization"></a>Comentarios e información de NPS de productos de Microsoft para su organización

Como administrador de una Microsoft 365, ahora puede ver información y datos generados por los usuarios de la organización.

Las encuestas de puntuación neta de patrocinador (NPS) recopilan comentarios de los usuarios y miden la probabilidad de que los usuarios digan que recomiendan productos y servicios a amigos y compañeros. Estos datos se pueden usar en el nivel organizativo para determinar estrategias de adopción y lanzamiento.

Usamos encuestas y comentarios de NPS de los usuarios finales para proporcionarle información sobre los productos y servicios de Microsoft. Esta información puede ayudarle a averiguar qué productos y servicios usan los usuarios finales de su organización, así como ayudarle a identificar problemas y resolverlos rápidamente. Con esta información puede:

<!--See location of users who have submitted feedback-->
- Ver qué sistema operativo o plataforma están usando
- Filtrar por producto, plataforma y búsqueda mediante palabras clave
- Ver comentarios del usuario final sobre los principales productos y problemas
- Exportar comentarios e información de encuesta a un archivo CSV para una investigación posterior

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador para ver [y](../add-users/about-admin-roles.md) leer informes de encuestas. Su organización debe tener encuestas de comentarios activadas para ver y leer informes de encuestas. Consulte Administrar [los comentarios de Microsoft para su organización](manage-feedback-ms-org.md) para obtener más información.

## <a name="survey-insights"></a>Información de la encuesta

1. En el Centro de administración, vaya a la **información de** la encuesta NPS de comentarios del producto  >    >  **de mantenimiento.**
2. En la **página Nps survey insights,** navegue por la página para ver información sobre encuestas relacionadas con NPS para su organización.

:::image type="content" source="../../media/prosight-product-feedback.png" alt-text="Captura de pantalla: Microsoft 365 de la encuesta nps":::

### <a name="chart-information"></a>Información del gráfico

**Los comentarios totales** muestran el número total de respuestas de comentarios de NPS enviadas por los usuarios finales, incluyen comentarios de NPS con comentarios y sin comentarios.

**Los** comentarios muestran el número total de respuestas de comentarios de NPS enviadas por el usuario final que incluyen comentarios.

**Volumen por aplicación** muestra el número total de volumen de respuesta de nps por aplicación.

**El volumen de comentarios por mes** muestra el número total de respuestas nps por mes.

:::image type="content" source="../../media/prosight-charts-area.png" alt-text="Captura de pantalla: Microsoft 365 de la encuesta":::

### <a name="top-topic-filters"></a>Filtros de temas principales

Los temas son modelos de aprendizaje automático que ayudan a analizar comentarios, frases y literales de los comentarios de la encuesta de NPS, lo que proporciona acceso a los temas más comunes en un nivel superior. Los filtros de temas principales muestran los 5 temas principales con el mayor volumen de comentarios literales.

:::image type="content" source="../../media/prosight-top-topic-filters-2.png" alt-text="Captura de pantalla: principales filtros de temas en los datos de la encuesta NPS":::

> [!NOTE]
> Solo publicamos un tema inteligente después de que cumpla con una barra de calidad mínima establecida en asociación con expertos en la materia. Las métricas de precisión y recuperación se usan para determinar lo mismo.

**La precisión literal** es la probabilidad de que un literal clasificado en este tema sea correcto.

**Verbatim Recall** es la probabilidad de que un literal relacionado con este tema se clasifique en este tema.

Los temas que están disponibles actualmente son los siguientes:

**La** navegación incluye comentarios del cliente sobre la navegación de aplicaciones y la facilidad de uso.

- Precisión verbatim- 93%
- Recuperación de Verbatim- 98%

**La** colaboración hace referencia a la facilidad de los usuarios para colaborar con aplicaciones de Microsoft.

- Precisión literal: 92%
- Recuperación de Verbatim-91%

**El valor** hace referencia a las percepciones de los clientes sobre temas como precios y preferencias de pago.

- Precisión verbatim- 86%
- Recuperación de Verbatim- 100%

**La confiabilidad** incluye comentarios del cliente sobre el comportamiento de la aplicación y el sistema, lo que da como resultado una terminación inesperada.

- Precisión verbatim- 97%
- Recuperación de verbatim: 94%

**El** rendimiento hace referencia a los comentarios de los clientes que abordan problemas relacionados con la velocidad percibida de las operaciones que experimenta un usuario al usar un producto de Microsoft. En este tema no se cubren las áreas de bloqueos o problemas de confiabilidad más amplios.

- Precisión literal: 92%
- Recuperación de Verbatim- 98%

**Los comentarios de Educación** del usuario incluyen comentarios de clientes sobre documentación de ayuda, tutoriales, guías y otro contenido de aprendizaje en línea o en el producto.

- Precisión verbatim- 83%
- Recuperación de Verbatim- 87%

**La** complejidad hace referencia a los comentarios de los clientes sobre si creen que las aplicaciones son complejas o sencillas de usar.

- Precisión literal: 92%
- Recuperación de verbatim- 89%

**La Elogio** se refiere a los comentarios de los clientes que tienen un sentimiento positivo y no encajan en ningún otro tema.

- Precisión verbatim- 93%
- Recuperación de Verbatim- 98%

### <a name="export-to-csv-and-search"></a>Exportar a CSV y búsqueda

Puede exportar datos sin procesar para realizar análisis adicionales mediante la funcionalidad Exportar a CSV.

> [!NOTE]
> Los datos sin procesar incluyen todos los tipos de comentarios, incluidos los comentarios que no son de NPS.

### <a name="filters"></a>Filtros

Puede filtrar por **canales,** **productos,** **plataformas** y **tipos de comentarios.**

**Los** canales son una forma de que las organizaciones seleccionen la frecuencia con la que obtienen actualizaciones de características para Office. Obtenga más información en [Overview of update channels for Aplicaciones Microsoft 365](/deployoffice/overview-update-channels). Este filtro permite filtrar hacia abajo a los comentarios enviados por un usuario en un canal específico

Los comentarios se pueden enviar en varias **plataformas** como Android, iOS, Mac y Windows. Este filtro le permite filtrar los comentarios en función de la plataforma en la que se envió.

La mayoría de Microsoft 365 productos **para** empresas se pueden encontrar en este filtro. Use este filtro para seleccionar los productos que han enviado comentarios.

Use **tipos de comentarios** (establecidos solo en tipos de comentarios NPS) para filtrar los comentarios que recopilamos.

:::image type="content" source="../../media/prosight-filters.png" alt-text="Captura de pantalla: Microsoft 365 de información de encuestas de NPS":::
