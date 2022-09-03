---
title: Automatización de la generación de documentos con SharePoint Syntex y Power Automate (versión preliminar)
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto, shrganguly
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo crear automáticamente documentos y otro contenido mediante SharePoint Syntex y Power Automate.
ms.openlocfilehash: 7ed0756b4aaed2ef564dd4796368e25d7f78dd97
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584903"
---
# <a name="automate-document-generation-with-sharepoint-syntex-and-power-automate-preview"></a>Automatización de la generación de documentos con SharePoint Syntex y Power Automate (versión preliminar)

Con el ensamblado de contenido en SharePoint Syntex junto con Power Automate, puede automatizar la generación de documentos mediante plantillas modernas. 

Esta versión preliminar es una acción de Power Automate en un conector de SharePoint. La acción se denomina "Generar documento mediante SharePoint Syntex (versión preliminar)" y tiene funcionalidades limitadas para la versión preliminar. 

## <a name="scope-of-the-preview"></a>Ámbito de la versión preliminar 

El ámbito actual de la versión preliminar le permite:  

- Elija una lista de SharePoint como punto de partida para la generación de documentos. Es decir, quiere que se genere un documento con los valores de la lista de SharePoint una vez que se haya agregado, modificado o eliminado un elemento de la lista. 

- Elija una plantilla moderna y asocie sus campos con columnas de la lista de SharePoint elegida. 

La versión preliminar se crea y se prueba para que funcione con los tres desencadenadores siguientes en SharePoint Connector:

- Cuando se crea un elemento
- Cuando se crea o modifica un elemento
- Cuando se elimina un elemento

## <a name="automate-document-generation"></a>Automatización de la generación de documentos 

Siga estos pasos para generar automáticamente documentos mediante una plantilla moderna y Power Automate. 

1. Iniciar sesión en Power Automate.

2. En el panel izquierdo, seleccione **Conectores**. En el cuadro de búsqueda, busque *SharePoint* y seleccione el conector de **SharePoint** .

3. En la página conector de SharePoint, seleccione el desencadenador que desea usar para iniciar el proceso de generación de documentos automatizado. 

    Se recomienda empezar con cualquiera de los tres desencadenadores siguientes:

    - Cuando se crea un elemento
    - Cuando se crea o modifica un elemento
    - Cuando se elimina un elemento

4. A continuación, configure el desencadenador escribiendo la dirección del sitio de SharePoint y el nombre de la lista de SharePoint. Seleccione **Nuevo paso**. 

   ![Captura de pantalla del desencadenador Cuando se crea o modifica un documento que muestra una dirección de sitio de ejemplo y un nombre de sitio.](../media/content-understanding/document-generation-trigger.png)

5. Vuelva a seleccionar el conector de SharePoint. En el cuadro de búsqueda, busque y seleccione la acción **Generar documento mediante SharePoint Syntex (versión preliminar).**

   ![Captura de pantalla de la pestaña Acciones del conector de SharePoint que muestra la acción Generar documento mediante SharePoint Syntex (versión preliminar).](../media/content-understanding/document-generation-action.png) 

6. Escriba la información del sitio y seleccione la biblioteca de documentos que contiene la plantilla moderna. 

7. Una vez seleccionada la plantilla, comenzará a ver los campos de plantilla. Asocie los campos a las columnas de la lista. 

    > [!NOTE]
    >La asignación de datos en la plantilla no se admite en esta versión preliminar. Por ejemplo, si ha asociado un campo de la plantilla a una columna de metadatos administrados, durante la generación automatizada podrá asociar este campo a una columna de una lista. 

8. Cuando haya terminado, seleccione **Guardar** para guardar el flujo. 

    > [!NOTE]
    > Se recomienda usar plantillas que no necesiten que los usuarios agreguen manualmente valores para la generación de documentos. Si la plantilla necesita entrada manual para un campo, puede especificar ese valor en el campo en lugar de asignarlo a una columna de lista de SharePoint.<br><br> Actualmente, solo se admiten documentos de Word (.Docx) mediante esta acción.  

## <a name="see-also"></a>Vea también

 [Creación de documentos mediante el ensamblado de contenido en SharePoint Syntex](content-assembly.md)
