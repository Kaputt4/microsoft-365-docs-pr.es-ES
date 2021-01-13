---
title: Alineación avanzada de eDiscovery con EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos que describe el modelo de referencia de detección electrónica (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841658"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Alineación avanzada de eDiscovery con el modelo de referencia de detección electrónica

El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos que describe el modelo de referencia de detección electrónica (EDRM).

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

(El origen de la imagen es cortesía de edrm.net. La imagen de origen estaba disponible en Creative Commons Attribution 3.0 Unported License.)

En un nivel alto, así es como eDiscovery avanzado admite el flujo de trabajo de EDRM:

- **Identificación.** Después de identificar posibles personas de interés en una investigación, puede agregarlas como administradores (también *denominados* administradores de datos, porque pueden poseer información relevante para la investigación) a un caso de eDiscovery avanzado. Una vez que los usuarios se agregan como administradores, es fácil conservar, recopilar y revisar documentos de administrador.

- **Conservación.** Para conservar y proteger los datos que son relevantes para una investigación, eDiscovery avanzado le permite colocar una retención legal en los orígenes de datos asociados con los administradores en un caso. También puede poner en retención los datos que no son de custodia. EDiscovery avanzado también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de retención legal a los administradores y realizar un seguimiento de sus confirmaciones.

- **Colección.** Después de identificar (y conservar) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en la búsqueda de eDiscovery avanzado para buscar y recopilar datos en directo de los orígenes de datos de custodia (y orígenes de datos no administradores, si procede) que puedan ser relevantes para el caso.

- **Procesamiento.** Después de recopilar todos los datos relevantes para el caso, el siguiente paso es procesarlo para su posterior revisión y análisis. En eDiscovery avanzado, los datos en el lugar que identificó en la fase de recopilación se copian *en* una ubicación de Azure Storage (denominada conjunto de revisión), que proporciona una vista estática de los datos del caso. 

- **Revisar.** Después de agregar datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo más relevante para el caso. Además, puede anotar y etiquetar documentos específicos.

- **Análisis.** EDiscovery avanzado proporciona una herramienta de análisis integrado que le ayuda a obtener más información sobre el conjunto de revisión que determine que no es relevante para la investigación. Además de reducir el volumen de datos relevantes, eDiscovery avanzado también le ayuda a ahorrar costos de revisión legal, ya que le permite organizar el contenido para que el proceso de revisión sea más fácil y eficaz.

- **Producción** y **presentación.** Cuando esté listo, puede exportar documentos de un conjunto de revisión para revisión legal. Puede exportar documentos en su formato nativo o en un formato especificado por EDRM para que se puedan importar a aplicaciones de revisión de terceros.

## <a name="more-information"></a>Más información

Para empezar a usar eDiscovery avanzado, consulte:

- [Configurar eDiscovery avanzado](get-started-with-advanced-ediscovery.md)

- [Crear y administrar un caso de eDiscovery avanzado](create-and-manage-advanced-ediscoveryv2-case.md)