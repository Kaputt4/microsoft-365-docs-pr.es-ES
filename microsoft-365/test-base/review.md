---
title: Revisar
description: Sección Revisar después de la incorporación.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323288"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a><span data-ttu-id="a4477-103">Paso 6: Revisar las selecciones para crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="a4477-103">Step 6: Review your selections to create your package.</span></span>

1.  <span data-ttu-id="a4477-104">En esta pestaña, el servicio muestra los detalles de la prueba y ejecuta una comprobación de integridad rápida.</span><span class="sxs-lookup"><span data-stu-id="a4477-104">On this tab, the service displays your test details and runs a quick completeness check.</span></span> 

    <span data-ttu-id="a4477-105">A ```Validation passed``` o message shows whether you can proceed to next steps or ```Validation failed``` not.</span><span class="sxs-lookup"><span data-stu-id="a4477-105">A ```Validation passed``` or ```Validation failed``` message shows whether you can proceed to next steps or not.</span></span>

2.  <span data-ttu-id="a4477-106">Revise los detalles de la prueba y, si se cumple, haga clic en el ```Create``` botón.</span><span class="sxs-lookup"><span data-stu-id="a4477-106">Review your test details and if satisfied, click on the ```Create``` button.</span></span> 

![Ver validación](Media/validation.png)

3.  <span data-ttu-id="a4477-108">Esto incorporará el paquete al entorno base de prueba.</span><span class="sxs-lookup"><span data-stu-id="a4477-108">This will onboard your package to the Test Base environment.</span></span> <span data-ttu-id="a4477-109">Si el paquete se crea correctamente, se desencadenará una prueba automatizada que compruebe si el paquete se puede ejecutar correctamente en Azure.</span><span class="sxs-lookup"><span data-stu-id="a4477-109">If your package is successfully created, an automated test which verifys whether your package can be successfully executed on Azure will be triggered.</span></span>

![Resultado correcto](Media/successful.png)

> [!Note]
> <span data-ttu-id="a4477-111">Recibirá una notificación de Azure Portal para notificarle sobre el éxito o el error de la comprobación del paquete.</span><span class="sxs-lookup"><span data-stu-id="a4477-111">You will get a notification from the Azure portal to notify you on the success or failure of the package verification.</span></span> 
>
> <span data-ttu-id="a4477-112">Tenga en cuenta que el proceso puede tardar hasta 24 horas, por lo que es probable que la página web agote el tiempo de espera si no está activo en él y, por lo tanto, la notificación no le informará de la finalización de esta ejecución a petición.</span><span class="sxs-lookup"><span data-stu-id="a4477-112">Please note that the process can take up to 24 hours, so it is likely your webpage will timeout if you are not active on it and hence, the notification will not inform you of the completion of this on-demand run.</span></span> 

  - <span data-ttu-id="a4477-113">Peradventure esto sucede, puedes ver el estado del paquete en la ```Manage packages``` pestaña.</span><span class="sxs-lookup"><span data-stu-id="a4477-113">Peradventure this happens, you can view the status of your package on the ```Manage packages``` tab.</span></span>

![Imagen para administrar paquetes](Media/managepackages.png)

  - <span data-ttu-id="a4477-115">Para las pruebas de éxito, sus resultados se pueden ver a través de las páginas y a intervalos programados, a menudo a partir de unos días ```Test Summary``` ```Security Updates Results``` después de la ```Feature Updates Results``` carga.</span><span class="sxs-lookup"><span data-stu-id="a4477-115">For succesful tests, their results can be seen via the ```Test Summary```, ```Security Updates Results``` and ```Feature Updates Results``` pages at scheduled intervals, often starting a few days after your upload.</span></span>
  
  - <span data-ttu-id="a4477-116">Si bien se han fallado las pruebas, es necesario cargar un nuevo paquete.</span><span class="sxs-lookup"><span data-stu-id="a4477-116">While failed tests, require you to upload a new package.</span></span> 
  
    <span data-ttu-id="a4477-117">Puede descargar el ```test logs``` análisis para obtener más información desde las páginas ' ```Security update results``` ```Feature updates results``` y.</span><span class="sxs-lookup"><span data-stu-id="a4477-117">You can download the ```test logs``` for further analysis from the ‘```Security update results``` and ```Feature updates results``` pages.</span></span>

  - <span data-ttu-id="a4477-118">Si experimenta errores de prueba repetidos, póngase en contacto testbasepreview@microsoft.com con los detalles del error.</span><span class="sxs-lookup"><span data-stu-id="a4477-118">If you experience repeated test failures, please reach out to testbasepreview@microsoft.com with details of your error.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a4477-119">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a4477-119">Next steps</span></span>

<span data-ttu-id="a4477-120">Descubra nuestras Directrices de contenido a través del siguiente vínculo.</span><span class="sxs-lookup"><span data-stu-id="a4477-120">Discover our Content Guidelines via the link below.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="a4477-121">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a4477-121">Next step</span></span>](contentguideline.md)
