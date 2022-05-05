---
title: Comentarios e información sobre NPS de productos de Microsoft para su organización
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
description: Use las puntuaciones de promotores de Net (NPS) de los usuarios finales para ver cómo se sienten sobre los productos y servicios de Microsoft.
ms.openlocfilehash: ec261553a5713d9e12205cbf4c88611a128bc48b
ms.sourcegitcommit: b3f5fe84a319741583954ef8ff2ec9ec6da69bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217362"
---
# <a name="microsoft-product-nps-feedback-and-insights-for-your-organization"></a>Comentarios e información sobre NPS de productos de Microsoft para su organización

Como administrador de una organización Microsoft 365, puede acceder y obtener información de encuestas de productos NPS enviadas por Microsoft.  

Las encuestas de Net Promoter Score (NPS) recopilan comentarios de los usuarios y miden la probabilidad de que los usuarios digan que recomiendan productos y servicios a amigos y compañeros. Estos datos se pueden usar en su organización para determinar las estrategias de adopción e implementación de Microsoft 365 productos y servicios.

Usamos encuestas y comentarios de NPS de los usuarios finales para proporcionarle información sobre los productos y servicios de Microsoft. Esta información puede ayudarle a averiguar qué productos y servicios usan los usuarios finales de su organización, así como a identificar problemas y resolverlos rápidamente. Con esta información puede:

- El acceso a los temas principales que los usuarios están analizando.
- Identificar usuarios felices.
- Solucione las quejas de los usuarios infelices.
- Vea qué sistema operativo o plataforma usan los usuarios.
- Filtre por producto, plataforma, canal o búsqueda mediante palabras clave.
- Consulte los comentarios del usuario final sobre los principales productos y problemas.
- Exportar información de comentarios y encuestas a un archivo CSV.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser [administrador](../add-users/about-admin-roles.md) para ver y leer informes de encuestas. Su organización debe tener activadas las encuestas de comentarios para ver y leer informes de encuestas. Consulte [Administrar comentarios de Microsoft para su organización](manage-feedback-ms-org.md) para obtener más información.

> [!IMPORTANT]
> Se requiere un mínimo de 30 envíos de encuestas NPS de los usuarios finales para poder ver la información de las encuestas de NPS.

## <a name="nps-survey-insights"></a>Conclusiones de encuestas de NPS

1. En el centro de administración, vaya a **HealthProduct feedback** Insights (Información  >  de la encuesta **deNPS** > **).**
2. En la página **de conclusiones de encuestas de NPS** , vaya a la página para ver información sobre encuestas relacionadas con NPS para su organización.

:::image type="content" source="../../media/product-feedback-main-page.png" alt-text="Captura de pantalla: Gráfico principal de Puntuación de promotor neto (NPS)":::

### <a name="top-topic-filters"></a>Filtros de temas principales

Hemos identificado los temas comunes de los comentarios de los usuarios. A continuación, usamos modelos de aprendizaje automático que entrenan los conjuntos de datos y organizan automáticamente los comentarios en **temas principales**. A continuación, puede identificar los cinco temas principales con el mayor volumen de comentarios textuales.  

:::image type="content" source="../../media/top-topics-filter.png" alt-text="Captura de pantalla: Cinco temas principales con los comentarios más textuales":::

> [!NOTE]
> Solo publicamos un tema inteligente después de que cumpla con una barra de calidad mínima establecida en asociación con expertos en la materia. Las métricas de precisión y recuperación se usan para determinar lo mismo.

**La precisión textual** es la probabilidad de que un literal clasificado en este tema sea correcto.

**La recuperación textual** es la probabilidad de que un textual relacionado con este tema se clasifique en este tema.

Los temas que están disponibles actualmente son los siguientes:

**Change Management** hace referencia a los comentarios de los clientes relacionados con experiencias actualizadas, incluido el proceso de actualización, cómo usar aplicaciones favoritas y cambios de diseño.

- Precisión textual- 82%
- Recuperación textual: 81%

**La colaboración** hace referencia a la facilidad con la que los usuarios pueden colaborar con aplicaciones de Microsoft.

- Precisión textual- 92%
- Recuperación textual-91%

**La complejidad** hace referencia a los comentarios de los clientes sobre si consideran que las aplicaciones son complejas o sencillas de usar.

- Precisión textual- 92%
- Recuperación textual: 89%

**La Elogio general** hace referencia a los comentarios de los clientes que tienen una opinión positiva y no encajan en otro tema.

- Precisión textual- 93%
- Recuperación textual: 98%

**La confiabilidad** incluye los comentarios de los clientes sobre el comportamiento de la aplicación y del sistema que dan lugar a una terminación inesperada.

- Precisión textual- 97%
- Recuperación textual- 94%

**La navegación** incluye comentarios del cliente sobre la navegación y la facilidad de uso de la aplicación.  

- Precisión textual- 93%
- Recuperación textual: 98%

**El rendimiento** hace referencia a los comentarios de los clientes que abordan problemas relacionados con la velocidad percibida de las operaciones que experimenta un usuario al usar un producto de Microsoft. En este tema no se tratan las áreas de bloqueos ni problemas de confiabilidad más amplios.

- Precisión textual- 92%
- Recuperación textual: 98%

**La confiabilidad** hace referencia a los comentarios del cliente sobre el comportamiento de la aplicación y del sistema, lo que provoca una terminación inesperada.  

Precisión textual- 97% Recuperación textual- 94%

**User Education** consta de comentarios de los clientes sobre documentación de ayuda, tutoriales, guías y otro contenido de aprendizaje en el producto o en línea.

- Precisión textual- 83%
- Recuperación textual: 87%

**El valor** hace referencia a las percepciones de los clientes sobre temas como los precios y las preferencias de pago.  

- Precisión textual- 86%
- Recuperación textual: 100%

### <a name="chart-information"></a>Información del gráfico

**El total de comentarios** muestra el número total de respuestas de comentarios NPS enviadas por los usuarios finales, incluidos los comentarios de NPS con comentarios y sin comentarios.

**Los comentarios** muestran el número total de respuestas de comentarios NPS enviadas por el usuario final que incluyen comentarios.

**El volumen de respuesta por aplicación** muestra el número total de volúmenes de respuesta de comentarios NPS por aplicación.

**El volumen de respuesta por plataforma** muestra el número total de volúmenes de respuesta de comentarios NPS por plataforma.

**El volumen de comentarios por mes** muestra el número total de volúmenes de respuesta de comentarios NPS de los últimos doce meses.

:::image type="content" source="../../media/response-details.png" alt-text="Captura de pantalla: Volumen de respuesta y volumen de respuesta por mes":::

Los gráficos se filtran por la clasificación NPS de la siguiente manera:

- Los detractores son clientes insatisfechos que no suelen recomendar su producto o servicio.
- Los pasivos son clientes que están satisfechos con el servicio, pero no son suficientes para recomendar su producto o servicio.
- Promotores: clientes felices que son leales, entusiastas y que probablemente recomiendan su producto o servicio.

:::image type="content" source="../../media/how-likely-recommend.png" alt-text="Captura de pantalla: Gráfico que muestra la probabilidad de recomendar una aplicación a un amigo o compañero":::

### <a name="export-to-csv-and-search"></a>Exportación a CSV y búsqueda

Puede exportar datos sin procesar para un análisis adicional mediante la funcionalidad Exportar a CSV. Puede buscar palabras clave en la sección de comentarios correspondiente al área de comentarios.

:::image type="content" source="../../media/export-to-csv.png" alt-text="Captura de pantalla: Seleccionar para exportar a CSV":::

> [!NOTE]
> Los datos sin procesar incluyen todos los tipos de comentarios, incluidos los que no son de NPS.

### <a name="filters"></a>Filtros

Puede filtrar por **canales**, **productos**, **plataformas** y **tipos de comentarios**.

**Los canales** son una manera de que las organizaciones seleccionen la frecuencia con la que obtienen actualizaciones de características para Office. Obtenga más información en [Introducción a los canales de actualización para Aplicaciones Microsoft 365](/deployoffice/overview-update-channels). Este filtro le permite filtrar por los comentarios enviados por un usuario en un canal específico.

Los comentarios se pueden enviar en varias **plataformas**, como Android, iOS, Mac y Windows. Este filtro le permite filtrar los comentarios en función de la plataforma en la que se envió.

La mayoría de Microsoft 365 para empresas **Productos** se puede encontrar en este filtro. Use este filtro para seleccionar los productos que han enviado comentarios.

Use **los tipos de comentarios** (establecidos solo en tipos de comentarios NPS) para filtrar los comentarios que recopilamos.

:::image type="content" source="../../media/feedback-filters.png" alt-text="Captura de pantalla: Gráfico que muestra los tipos de comentarios":::

### <a name="we-want-to-hear-from-you"></a>Queremos escuchar sus comentarios

Comparta sus ideas sobre el panel de conclusiones de la encuesta NPS y sus ideas sobre cómo mejorarlo. Use las secciones Comentarios de los productos y servicios. También puede enviarnos un correo electrónico a prosight@microsoft.com
