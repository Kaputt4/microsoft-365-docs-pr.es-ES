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
ms.openlocfilehash: 64c47566959cbe83088ac7855f8f3cd6a8473d2ad86d5ab2957fbbdf41d10bf7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53852964"
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
