---
title: Establecer la configuración avanzada de ANALYZE en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 'Obtenga información acerca de cómo configurar las opciones avanzadas, incluidos los mensajes casi duplicados, los subprocesos de correo electrónico y los temas, para analizar el proceso en eDiscovery avanzado. '
ms.openlocfilehash: 91faf9e39fe7b8a7fada7b05ccd88351d813b148
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631277"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="a6211-103">Establecer la configuración avanzada de ANALYZE en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="a6211-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a6211-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a6211-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a6211-106">EDiscovery avanzado proporciona parámetros avanzados predeterminados para la configuración del módulo de análisis.</span><span class="sxs-lookup"><span data-stu-id="a6211-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="a6211-107">En el procedimiento siguiente se describe la configuración que se puede especificar.</span><span class="sxs-lookup"><span data-stu-id="a6211-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="a6211-108">En la **ficha \> preparar \> la configuración de ANALYZE** , haga clic en **Configuración avanzada** (en la parte inferior de la página).</span><span class="sxs-lookup"><span data-stu-id="a6211-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="a6211-109">Se muestra el siguiente panel.</span><span class="sxs-lookup"><span data-stu-id="a6211-109">The following panel is displayed.</span></span> 
    
    ![Establecer la configuración avanzada del análisis](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="a6211-111">En **parámetros casi duplicados y de subprocesos de correo electrónico**, seleccione valores para las siguientes opciones, según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="a6211-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="a6211-112">**Número mínimo de palabras**: número mínimo de palabras, por debajo del cual no se envía un archivo para análisis casi duplicados.</span><span class="sxs-lookup"><span data-stu-id="a6211-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="a6211-113">**Número máximo de palabras**: número máximo de palabras, por encima de las cuales no se envía un archivo para análisis casi duplicados.</span><span class="sxs-lookup"><span data-stu-id="a6211-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="a6211-114">**Similitud de correo electrónico**: el nivel mínimo de semejanza de dos correos electrónicos se considerará similar.</span><span class="sxs-lookup"><span data-stu-id="a6211-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="a6211-115">El valor es siempre igual a o mayor que el de la similitud del documento.</span><span class="sxs-lookup"><span data-stu-id="a6211-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="a6211-116">El valor predeterminado es 90%.</span><span class="sxs-lookup"><span data-stu-id="a6211-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="a6211-117">En **los parámetros de los temas**, active la casilla **incluir números en el análisis del tema** para incluir números en el procesamiento de temas durante el análisis.</span><span class="sxs-lookup"><span data-stu-id="a6211-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="a6211-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a6211-118">Click **Save**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="a6211-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6211-119">See also</span></span>

[<span data-ttu-id="a6211-120">Advanced eDiscovery (clásico)</span><span class="sxs-lookup"><span data-stu-id="a6211-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a6211-121">Descripción de la similitud de documentos</span><span class="sxs-lookup"><span data-stu-id="a6211-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6211-122">Configuración de las opciones de análisis</span><span class="sxs-lookup"><span data-stu-id="a6211-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6211-123">Configuración de omitir texto</span><span class="sxs-lookup"><span data-stu-id="a6211-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a6211-124">Visualización de los resultados del análisis</span><span class="sxs-lookup"><span data-stu-id="a6211-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

