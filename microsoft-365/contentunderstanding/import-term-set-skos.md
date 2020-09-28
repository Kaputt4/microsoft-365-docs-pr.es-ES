---
title: Importar un conjunto de términos mediante un formato basado en SKOS
description: Obtener información sobre cómo importar un conjunto de términos mediante un formato basado en SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296074"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="7e542-103">Importar un conjunto de términos mediante un formato basado en SKOS</span><span class="sxs-lookup"><span data-stu-id="7e542-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="7e542-104">Puede importar un conjunto de términos con un formato basado en SKOS.</span><span class="sxs-lookup"><span data-stu-id="7e542-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="7e542-105">Para obtener más información sobre el formato, consulte [SharePoint TAXONOMY SKOS Format Reference](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7e542-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="7e542-106">Se recomienda mantener los archivos de importación en menos de 20.000 términos.</span><span class="sxs-lookup"><span data-stu-id="7e542-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="7e542-107">Los archivos de mayor tamaño pueden aumentar el tiempo necesario para la validación y la importación.</span><span class="sxs-lookup"><span data-stu-id="7e542-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="7e542-108">En el centro de administración de SharePoint, expanda **servicios de contenido**y, a continuación, haga clic en **almacén de términos**.</span><span class="sxs-lookup"><span data-stu-id="7e542-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="7e542-109">Seleccione el grupo de términos en el que desea importar el conjunto de términos.</span><span class="sxs-lookup"><span data-stu-id="7e542-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="7e542-110">En la barra de comandos, haga clic en **importar conjunto de términos**.</span><span class="sxs-lookup"><span data-stu-id="7e542-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="7e542-111">Si desea descargar un archivo de ejemplo para usarlo como plantilla, haga clic en **Sample-Metadata. TTL** para obtener un archivo de ejemplo que usa el formato basado en SKOS.</span><span class="sxs-lookup"><span data-stu-id="7e542-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="7e542-112">Cree el archivo de importación que contenga los conjuntos de términos & términos que desea importar.</span><span class="sxs-lookup"><span data-stu-id="7e542-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="7e542-113">En **formato de archivo**, seleccione **SKOS (\*. TTL)**.</span><span class="sxs-lookup"><span data-stu-id="7e542-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="7e542-114">Haga clic en **examinar** y vaya a y agregue el archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="7e542-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="7e542-115">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7e542-115">Click **Import**.</span></span> <span data-ttu-id="7e542-116">No cierre el panel hasta que se complete la importación.</span><span class="sxs-lookup"><span data-stu-id="7e542-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="7e542-117">Si se ha importado correctamente el archivo, se mostrará un mensaje de operación correcta y se actualizará el almacén de términos y se podrá navegar a los conjuntos de términos recién creados.</span><span class="sxs-lookup"><span data-stu-id="7e542-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e542-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e542-118">See also</span></span>

[<span data-ttu-id="7e542-119">Introducción a los metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="7e542-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="7e542-120">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="7e542-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="7e542-121">Importación de conjuntos de términos (nivel de sitio)</span><span class="sxs-lookup"><span data-stu-id="7e542-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)