---
title: Administrar contratos con una solución de Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.service: microsoft-365-enterprise
ms.collection:
- m365solution-managecontracts
- m365solution-overview
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: Obtenga información sobre cómo administrar contratos mediante una solución de Microsoft 365 de SharePoint Syntex, listas de SharePoint, Microsoft Teams y Power Automate.
ms.openlocfilehash: 6d925999c70e49ec17dcb04925256a2b229007bf
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67812268"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Administrar contratos con una solución de Microsoft 365

En este artículo se describe cómo crear una solución de administración de contratos para su organización mediante SharePoint Syntex y componentes de Microsoft 365. Le proporciona un marco para ayudarle a planear y crear una solución que se adapte a sus necesidades empresariales únicas. Aunque esta solución habla de la administración de contratos, puede adaptarla para crear otras soluciones de administración de documentos, como declaraciones de trabajo o facturas.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWJUR0]

</br>

## <a name="identify-the-business-problem"></a>Identificar el problema empresarial

El primer paso para planear el sistema de administración de contratos es comprender el problema que intenta resolver. Para esta solución, es necesario solucionar cuatro problemas clave:

- **Identificar contratos**. Su organización trabaja con muchos documentos, como facturas, contratos, declaraciones de trabajo, etc.  Algunos son recursos digitales enviados por correo electrónico y otros son activos en papel enviados a través del correo tradicional. Necesita una manera de identificar todos los contratos de cliente de todos los demás documentos y clasificarlos como tales.

- **Realice un seguimiento del historial de aprobaciones de contratos**. Su organización necesita una manera confiable de averiguar si los contratos se han aprobado o rechazado, y si se ha procesado el pago. 

- **Sitio para administrar las aprobaciones de contratos**. Su organización debe configurar un sitio de colaboración en el que todas las partes interesadas necesarias puedan revisar fácilmente los contratos. Las partes interesadas deben poder revisar todo el contrato si es necesario, pero principalmente se preocupan por ver varios campos clave de cada contrato (por ejemplo, nombre del cliente, número de pedido de compra y costo total). Las partes interesadas deben poder aprobar o rechazar fácilmente los contratos entrantes.

- **Enrutar contratos revisados**. Los contratos aprobados y rechazados deben enrutarse a través de un flujo de trabajo específico. Los contratos aprobados deben enrutarse a una aplicación de terceros para el procesamiento de pagos. Los contratos rechazados deben enrutarse para una revisión adicional.

## <a name="overview-of-the-solution"></a>Información general de la solución

  ![Diagrama de la solución mediante SharePoint Syntex, listas de SharePoint, Teams y Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Esta guía de la solución de administración de contratos incluye cuatro componentes de Microsoft 365:

- **Microsoft SharePoint Syntex**: cree modelos para identificar y clasificar los archivos de contrato y, a continuación, extraer los datos adecuados de ellos.

- **Listas de Microsoft SharePoint**: use el formato disponible en las listas modernas de SharePoint para presentar contratos en un formato descriptivo para la empresa.

- **Microsoft Teams**: use la funcionalidad de un canal de Teams y las pestañas asociadas para permitir que las partes interesadas revisen y administren los contratos.

- **Power Automate**: use flujos para guiar los contratos a través del proceso de aprobación y, a continuación, a una aplicación de terceros para el pago.

### <a name="how-it-all-works"></a>Cómo funciona todo

  ![Diagrama de la solución que muestra el flujo de trabajo para cargar documentos, extraer datos, notificar a las partes interesadas y aprobar o rechazar el contrato.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Los documentos se cargan en una biblioteca de documentos de SharePoint. Se ha aplicado un modelo de comprensión de documentos SharePoint Syntex a la biblioteca de documentos. Comprueba cada archivo para ver si hay coincidencia con un tipo de contenido "contrato" que se va a buscar. Si encuentra una coincidencia, clasifica el archivo como un "contrato" y actualiza el tipo de contenido del documento.

2. El modelo también extrae datos específicos de cada archivo de contrato que las partes interesadas están interesadas en ver, como el *cliente*, *el contratista* y el *importe de la tarifa*.

    La página siguiente es un ejemplo de un contrato que el modelo está entrenado para identificar.

      ![Ejemplo de un contrato.](../media/content-understanding/contract.png)

3. En Microsoft Teams, todas las partes interesadas son miembros de un canal seguro de Teams en el que todos los contratos de la biblioteca de documentos son visibles para su aprobación o rechazo. Mediante la funcionalidad de Teams, se notifica a todas las partes interesadas cuando es necesario revisar nuevos contratos.

4. Con Power Automate, los contratos se mueven a través del proceso de aprobación en el canal de Teams. Cuando un miembro aprueba un contrato, el estado del contrato cambia a aprobado, se notifica a todos los miembros a través de una publicación de Teams y se crea un elemento de línea para mostrar que el contrato está listo para el pago. Este proceso se puede ampliar para escribir directamente en una solicitud financiera de terceros para el pago.

5. Cuando un miembro rechaza un contrato, el estado cambia a rechazado y se notifica a todos los miembros a través de una publicación de Teams.

6. El resultado final de esta solución es un proceso empresarial automatizado para su organización. Los empleados pueden usar fácilmente la vista de icono personalizada en Teams para iniciar y supervisar el flujo de trabajo de aprobación de los documentos. 

     ![Pestaña Contratos.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>Requisitos de licencias

Esta solución se basa en la siguiente funcionalidad, todas disponibles como parte de una licencia de Microsoft 365 Enterprise (E1, E3, E5, F3) o Business (Básico, Estándar o Premium):

- Microsoft SharePoint Syntex
- Microsoft Teams
- Power Automate

### <a name="learn-how-to-use-sharepoint-syntex"></a>Aprenda a usar SharePoint Syntex

¿Es nuevo en SharePoint Syntex? Aprenda a usar SharePoint Syntex para administrar contenido mediante inteligencia artificial.

La ruta [de aprendizaje Introducción a SharePoint Syntex](/training/paths/syntex-get-started) le enseñará cómo puede usar los modelos de comprensión de documentos y procesamiento de formularios para clasificar documentos, extraer texto y etiquetar los documentos para una administración de conocimientos rápida y sencilla.

## <a name="create-the-solution"></a>Creación de la solución

En las secciones siguientes se detallará cómo configurar la solución de administración de contratos. Se divide en tres pasos:

- [Paso 1. Uso de SharePoint Syntex para identificar archivos de contrato y extraer datos](solution-manage-contracts-step1.md)
- [Paso 2. Uso de Microsoft Teams para crear el canal de administración de contratos](solution-manage-contracts-step2.md)
- [Paso 3. Uso de Power Automate para crear el flujo para procesar los contratos](solution-manage-contracts-step3.md)
