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
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="2a49c-103">SDK de base de prueba para Python</span><span class="sxs-lookup"><span data-stu-id="2a49c-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="2a49c-104">Información general</span><span class="sxs-lookup"><span data-stu-id="2a49c-104">Overview</span></span>
<span data-ttu-id="2a49c-105">El SDK de Test Base se puede usar para interactuar con el recurso base de prueba de Azure.</span><span class="sxs-lookup"><span data-stu-id="2a49c-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="2a49c-106">(es decir, administrar el paquete de la aplicación, incluir crear paquete, editar paquete y eliminar paquete)</span><span class="sxs-lookup"><span data-stu-id="2a49c-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="2a49c-107">Con el SDK, el resumen de prueba y el resultado del análisis que se pueden obtener incluyen: scriptExecution, confiabilidad, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="2a49c-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="2a49c-108">Con el SDK de Base de prueba, puede integrar la base de pruebas en la canalización de CI/CD.</span><span class="sxs-lookup"><span data-stu-id="2a49c-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="2a49c-109">Biblioteca de cliente</span><span class="sxs-lookup"><span data-stu-id="2a49c-109">Client Library</span></span>

<span data-ttu-id="2a49c-110">Instale el paquete base de prueba con pip.</span><span class="sxs-lookup"><span data-stu-id="2a49c-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="2a49c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a49c-111">Example</span></span>
