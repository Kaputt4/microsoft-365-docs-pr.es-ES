---
title: Buscar metadatos en bibliotecas de documentos en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: kkameth
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: high
description: Obtenga información sobre cómo usar la búsqueda avanzada de metadatos y la búsqueda de columnas de sitio personalizadas para buscar elementos en bibliotecas de documentos de SharePoint con SharePoint Syntex.
ms.openlocfilehash: 50b9ef7ff6fe7942266ec59f8d5ad81e0dfbecd4
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65679579"
---
# <a name="search-for-metadata-in-document-libraries-in-microsoft-sharepoint-syntex"></a>Buscar metadatos en bibliotecas de documentos en Microsoft SharePoint Syntex

La característica de búsqueda avanzada de metadatos de SharePoint Syntex le permite realizar consultas específicas basadas en metadatos en bibliotecas de documentos de SharePoint. Puede realizar consultas más rápidas y precisas basadas en valores de columna de metadatos específicos, en lugar de simplemente buscar palabras clave.

La búsqueda avanzada de metadatos le permite usar los metadatos asociados a un documento para ayudar a localizar el archivo en una biblioteca de documentos de SharePoint. Esta función es especialmente útil cuando tiene una parte específica de la información que desea buscar, por ejemplo, cuándo se modificó por última vez un documento, una persona específica asociada a un archivo o un tipo de archivo específico.

> [!NOTE]
> Esta característica solo está disponible para los usuarios con licencia para SharePoint Syntex. 

## <a name="to-use-advanced-metadata-search"></a>Para usar la búsqueda avanzada de metadatos

1. En una biblioteca de documentos de SharePoint, en el cuadro **Busca esta biblioteca**, seleccione el icono de búsqueda de metadatos (![Pantalla del icono de búsqueda de metadatos.](../media/content-understanding/metadata-search-icon.png)).

    ![Captura de pantalla de una página de biblioteca de documentos que muestra el cuadro de búsqueda con el icono de búsqueda de metadatos resaltado.](../media/content-understanding/metadata-search-box.png)

2. En el panel de búsqueda de metadatos, escriba el texto o seleccione el parámetro que desea buscar en uno o varios de los campos de búsqueda.

    ![Captura de pantalla de una página de biblioteca de documentos que muestra el panel de búsqueda de metadatos.](../media/content-understanding/metadata-search-pane.png)

   Actualmente hay los siguientes campos de búsqueda de metadatos disponibles. En el futuro se agregarán más campos.

   |Field    |Use este campo para  |
   |---------|---------|
   |Palabras clave |Busque una coincidencia de cadena en los metadatos o en el texto completo de un documento. |
   |Nombre de archivo     |Busque en la columna **Nombre** en la biblioteca.          |
   |Contactos   |Busque una coincidencia en las personas de cualquier columna de la biblioteca.   |
   |Fecha de modificación |Buscar por intervalo de fechas seleccionado en la columna **Modificado** en la biblioteca.         |
   |Tipo de archivo     |Buscar por tipo de archivo seleccionado (por ejemplo, documento de Word o PDF).        |
   |Tipo de contenido  |Buscar por tipo de contenido seleccionado. Esta opción solo aparecerá si hay un tipo de contenido no predeterminado aplicado a la biblioteca. Los tipos de contenido predeterminado son *documento* y *carpeta*.        |

3. También puede buscar columnas de sitio personalizadas que se encuentran en la vista de la biblioteca actual. Esto es especialmente útil si tiene un modelo que se ejecuta en la biblioteca porque los extractores de metadatos rellenan automáticamente la información en las columnas del sitio.  

    Para agregar una columna de sitio personalizada a la búsqueda, seleccione **Agregar más opciones** y, a continuación, seleccione el nombre de la columna del sitio.

    ![Captura de pantalla del menú Agregar más opciones en el panel de búsqueda de metadatos.](../media/content-understanding/metadata-search-add-more-options.png)

4. Seleccione **Buscar**. Los documentos que coinciden con su búsqueda de metadatos se muestran en la página de resultados. 
