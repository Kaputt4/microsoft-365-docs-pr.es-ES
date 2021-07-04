---
title: Importar un conjunto de términos con un formato basado en SKOS
description: Obtenga información sobre cómo importar un conjunto de términos con un formato basado en SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288520"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="ac0a9-103">Importar un conjunto de términos con un formato basado en SKOS</span><span class="sxs-lookup"><span data-stu-id="ac0a9-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="ac0a9-104">Puede importar un conjunto de términos con un formato basado en SKOS.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="ac0a9-105">Para más información sobre el formato, consulte [Referencia de formato SKOS de la taxonomía de SharePoint](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ac0a9-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="ac0a9-106">Esta característica requiere una licencia de [SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="ac0a9-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="ac0a9-107">Le recomendamos mantener sus archivos de importación con menos de 20 000 términos.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="ac0a9-108">Los archivos de mayor tamaño pueden aumentar el tiempo necesario para la validación y la importación.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="ac0a9-109">En el Centro de administración de SharePoint, expanda **Servicios de contenido** y, después, haga clic en **Almacén de términos**.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="ac0a9-110">Seleccione el grupo de términos en el que quiere importar el conjunto de términos.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="ac0a9-111">En la barra de comandos, haga clic en **Importar conjunto de términos**.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-111">In the command bar, click **Import term set**.</span></span>

4. <span data-ttu-id="ac0a9-112">Si desea descargar un archivo de ejemplo para usarlo como plantilla, haga clic en **sample-metadata.ttl** para obtener un archivo de ejemplo que use el formato basado en SKOS.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>

5. <span data-ttu-id="ac0a9-113">Cree el archivo de importación que contiene los conjuntos de términos y los términos que desee importar.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6. <span data-ttu-id="ac0a9-114">En **Formato de archivo**, selecione **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7. <span data-ttu-id="ac0a9-115">Haga clic en **Examinar**, desplácese al archivo de importación y agréguelo.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-115">Click **Browse** and navigate to and add your import file.</span></span>

8. <span data-ttu-id="ac0a9-116">Haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-116">Click **Import**.</span></span> <span data-ttu-id="ac0a9-117">No cierre el panel hasta que finalice la importación.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="ac0a9-118">Si la importación del archivo se ha realizado correctamente, se mostrará un mensaje que así lo indicará, se actualizará el almacén de términos y podrá navegar a los conjuntos de términos recién creados.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac0a9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac0a9-119">See also</span></span>

[<span data-ttu-id="ac0a9-120">Introducción a los metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="ac0a9-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="ac0a9-121">Información general de la comprensión mediante documentos</span><span class="sxs-lookup"><span data-stu-id="ac0a9-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="ac0a9-122">Importar conjuntos de términos (nivel de sitio)</span><span class="sxs-lookup"><span data-stu-id="ac0a9-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
