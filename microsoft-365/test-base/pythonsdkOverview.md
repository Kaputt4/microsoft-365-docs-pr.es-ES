---
title: SDK de base de prueba para Python
description: Detalles sobre cómo comprender el SDK de Test Base para Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323123"
---
# <a name="test-base-sdk-for-python"></a>SDK de base de prueba para Python

## <a name="overview"></a>Información general
El SDK de Test Base se puede usar para interactuar con el recurso base de prueba de Azure. (es decir, administrar el paquete de la aplicación, incluir crear paquete, editar paquete y eliminar paquete)

Con el SDK, el resumen de prueba y el resultado del análisis que se pueden obtener incluyen: scriptExecution, confiabilidad, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.

Con el SDK de Base de prueba, puede integrar la base de pruebas en la canalización de CI/CD.

## <a name="client-library"></a>Biblioteca de cliente

Instale el paquete base de prueba con pip.

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>Ejemplo
