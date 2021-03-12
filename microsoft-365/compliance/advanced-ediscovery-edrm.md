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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos descrito por el Modelo de referencia de detección electrónica (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727493"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Alineación avanzada de eDiscovery con el modelo de referencia de detección electrónica

El flujo de trabajo integrado de eDiscovery avanzado en Microsoft 365 se alinea con el proceso de exhibición de documentos electrónicos descrito por el Modelo de referencia de detección electrónica (EDRM).

![Modelo de referencia de detección electrónica (EDRM)](../media/EDRMv1.png)

(Origen de la imagen cortesía de edrm.net. La imagen de origen estaba disponible en Creative Commons Attribution 3.0 Unported License).)

En un nivel alto, este es el modo en que eDiscovery avanzado admite el flujo de trabajo de EDRM:

- **Identificación.** Después de identificar posibles personas de interés en una investigación, puede agregarlas como custodios (también *denominadas custodios* de datos, porque pueden tener información relevante para la investigación) a un caso de exhibición de documentos electrónicos avanzado. Después de agregar a los usuarios como custodios, es fácil conservar, recopilar y revisar documentos de custodia.

- **Conservación.** Para conservar y proteger los datos que son relevantes para una investigación, eDiscovery avanzado le permite colocar una retención legal en los orígenes de datos asociados con los custodios en un caso. También puede poner en espera datos que no son custodia. La exhibición de documentos electrónicos avanzada también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de retención legal a los custodios y realizar un seguimiento de sus confirmaciones.

- **Colección.** Después de identificar (y conservar) los orígenes de datos relevantes para la investigación, puede usar la herramienta de búsqueda integrada en Búsqueda avanzada de exhibición de documentos electrónicos para buscar y recopilar datos en directo de los orígenes de datos con custodia (y orígenes de datos no custodiados, si procede) que puedan ser relevantes para el caso.

- **Procesamiento.** Después de recopilar todos los datos relevantes para el caso, el siguiente paso es procesarlo para su posterior revisión y análisis. En exhibición de documentos electrónicos avanzada, los datos en sitio que identificó en la fase de colección se copian en una ubicación de Azure Storage (denominada conjunto de revisión), lo que le proporciona una vista estática de los datos de caso. 

- **Revisar.** Después de agregar datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo que es más relevante para el caso. Además, puede anotar y etiquetar documentos específicos.

- **Análisis.** La exhibición de documentos electrónicos avanzada proporciona una herramienta de análisis integrada que le ayuda a obtener más datos del conjunto de revisión que determine que no es relevante para la investigación. Además de reducir el volumen de datos relevantes, la exhibición de documentos electrónicos anticipada también le ayuda a ahorrar costos de revisión legal, ya que le permite organizar el contenido para que el proceso de revisión sea más fácil y eficaz.

- **Producción** y **presentación.** Cuando esté listo, puede exportar documentos de un conjunto de revisión para su revisión legal. Puede exportar documentos en su formato nativo o en un formato especificado por EDRM para que se puedan importar a aplicaciones de revisión de terceros.

## <a name="more-information"></a>Más información

Para empezar a usar eDiscovery avanzada, consulte:

- [Configurar eDiscovery avanzado](get-started-with-advanced-ediscovery.md)

- [Crear y administrar un caso de exhibición de documentos electrónicos avanzada](create-and-manage-advanced-ediscoveryv2-case.md)