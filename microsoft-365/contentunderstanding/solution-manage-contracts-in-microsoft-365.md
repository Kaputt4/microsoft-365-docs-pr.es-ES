---
title: Administrar contratos mediante una Microsoft 365 solución
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo administrar contratos mediante una Microsoft 365 de SharePoint Syntex, Microsoft Teams y Power Automate.
ms.openlocfilehash: 806ea9fd048dec198a19fa79f3b60f3f3cb81018
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281313"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Administrar contratos mediante una Microsoft 365 solución

En este artículo se describe cómo crear una solución de administración de contratos para su organización mediante SharePoint Syntex y componentes de Microsoft 365. Le proporciona un marco para ayudarle a planear y crear una solución que se adapte a sus necesidades empresariales únicas. Incluso si esta solución no se adapta a sus necesidades empresariales en su conjunto, partes de ella se pueden adoptar en la planeación para crear una solución de administración de contratos personalizada.

## <a name="identify-the-business-problem"></a>Identificar el problema empresarial

El primer paso para planear el sistema de administración de contratos es comprender el problema que está intentando resolver. Para esta solución, deben tratarse cuatro problemas clave:

- **Identificar contratos**. Su organización trabaja con muchos documentos, como facturas, contratos, extractos de trabajo, entre otros.  Algunos son activos digitales enviados por correo electrónico y otros son activos de papel enviados a través del correo tradicional. Necesita una forma de identificar todos los contratos de clientes de todos los demás documentos y, a continuación, clasificarlos como tales.

- **Realice un seguimiento del historial de aprobaciones de contratos**. Su organización necesita una forma confiable de averiguar si los contratos se han aprobado o rechazado, y si se ha procesado el pago. 

- **Sitio para administrar aprobaciones de contratos**. Su organización debe configurar un sitio de colaboración en el que todas las partes interesadas necesarias puedan revisar fácilmente los contratos. Las partes interesadas deben poder revisar todo el contrato si es necesario, pero sobre todo se preocupan por ver varios campos clave de cada contrato (por ejemplo, nombre del cliente, número de pedido y costo total). Las partes interesadas deben poder aprobar o rechazar fácilmente los contratos entrantes.

- **Enrutar contratos revisados**. Los contratos aprobados y rechazados deben enrutarse a través de un flujo de trabajo específico. Los contratos aprobados deben enrutrse a una aplicación de terceros para el procesamiento de pagos. Los contratos rechazados deben enrutarse para una revisión adicional.

## <a name="overview-of-the-solution"></a>Información general sobre la solución

  ![Diagrama de la solución mediante SharePoint Syntex, SharePoint listas, Teams y Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Esta guía de solución de administración de contratos incluye cuatro componentes Microsoft 365:

- **Microsoft SharePoint Syntex:** cree modelos para identificar y clasificar los archivos de contrato y, a continuación, extraer los datos adecuados de ellos.

- **Listas SharePoint microsoft:** use el formato disponible en listas de SharePoint modernas para presentar contratos en un formato descriptivo para empresas.

- **Microsoft Teams:** use la funcionalidad de un canal de Teams y pestañas asociadas para permitir a las partes interesadas revisar y administrar contratos.

- **Power Automate:** use flujos para guiar los contratos a través del proceso de aprobación y, a continuación, a una aplicación de terceros para su pago.

### <a name="how-it-all-works"></a>Cómo funciona todo

  ![Diagrama de la solución que muestra el flujo de trabajo para cargar documentos, extraer datos, notificar a las partes interesadas y aprobar o rechazar el contrato.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Los documentos se cargan en una SharePoint de documentos. Se SharePoint modelo de comprensión de documentos Syntex a la biblioteca de documentos. Comprueba cada archivo para ver si coincide con un tipo de contenido "contrato" que está capacitado para buscar. Si encuentra una coincidencia, clasifica el archivo como un "contrato" y actualiza el tipo de contenido del documento.

2. El modelo también extrae datos específicos de cada archivo de contrato que las partes interesadas están interesadas en ver, como el importe de *cliente,* contratista *y* *tarifa.*

    La página siguiente es un ejemplo de un contrato que el modelo está capacitado para identificar.

      ![Ejemplo de un contrato.](../media/content-understanding/contract.png)

3. En Microsoft Teams, todas las partes interesadas son miembros de un canal de Teams seguro en el que todos los contratos de la biblioteca de documentos están visibles para su aprobación o rechazo. Al usar Teams, se notifica a todas las partes interesadas cuando es necesario revisar nuevos contratos.
 
4. Al usar Power Automate, los contratos se mueven a través del proceso de aprobación en el Teams canal. Cuando un miembro aprueba un contrato, se cambia el estado del contrato para aprobarlo, se notifica a todos los miembros a través de una publicación de Teams y se crea un elemento de línea para mostrar que el contrato está listo para el pago. Este proceso se puede extender para escribir directamente en una aplicación financiera de terceros para su pago.

5.  Cuando un miembro rechaza un contrato, el estado cambia a rechazado y se notifica a todos los miembros a través de una Teams correo.

## <a name="create-the-solution"></a>Crear la solución

En las siguientes secciones se detallará cómo configurar la solución de administración de contratos. Se divide en tres pasos:

- [Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos](solution-manage-contracts-step1.md)
- [Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos](solution-manage-contracts-step2.md)
- [Paso 3. Usar Power Automate para crear el flujo para procesar los contratos](solution-manage-contracts-step3.md)
