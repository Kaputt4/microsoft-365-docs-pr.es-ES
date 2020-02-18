---
title: Protección de los archivos de los equipos con etiquetas de confidencialidad
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Resumen: Aplique etiquetas de sensibilidad para proteger los archivos en un equipo extremadamente confidencial.'
ms.openlocfilehash: b263aeae335b83cadb45b16d70a2a45d56f1cbd3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083378"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="76b02-103">Protección de los archivos de los equipos con etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="76b02-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="76b02-104">A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un equipo extremadamente confidencial necesita su propia etiqueta o subetiqueta para que los archivos asignados:</span><span class="sxs-lookup"><span data-stu-id="76b02-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a highly confidential team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="76b02-105">Se cifren individualmente.</span><span class="sxs-lookup"><span data-stu-id="76b02-105">Are individually encrypted.</span></span>
- <span data-ttu-id="76b02-106">Contengan permisos personalizados para que solo los miembros del equipo puedan abrirlo.</span><span class="sxs-lookup"><span data-stu-id="76b02-106">Contain custom permissions so that only members of the team can open it.</span></span>

<span data-ttu-id="76b02-107">Para lograr este nivel extra de seguridad en los archivos almacenados en el sitio de SharePoint subyacente del equipo, debe configurar una etiqueta de confidencialidad personalizada que sea su propia etiqueta o una subetiqueta de la etiqueta general para datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="76b02-107">To accomplish this additional level of security for files stored in the underlying SharePoint site of a team, you must configure a customized sensitivity label that is either its own label or a sublabel of the general label for highly regulated data.</span></span> <span data-ttu-id="76b02-108">Solo los miembros del equipo verán la etiqueta o subetiqueta personalizada en sus listas de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="76b02-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="76b02-109">Use una etiqueta de confidencialidad cuando necesite un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados.</span><span class="sxs-lookup"><span data-stu-id="76b02-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="76b02-110">Use una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o quiera organizar etiquetas para equipos extremadamente confidenciales bajo la etiqueta altamente regulada.</span><span class="sxs-lookup"><span data-stu-id="76b02-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for highly confidential teams under the highly regulated label.</span></span>

<span data-ttu-id="76b02-111">Siga [estas instrucciones ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una etiqueta o subetiqueta aparte con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="76b02-111">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="76b02-112">El nombre de la etiqueta o de la subetiqueta contiene el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="76b02-112">The name of the label or sublabel contains the name of the team</span></span>
- <span data-ttu-id="76b02-113">El cifrado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="76b02-113">Encryption is enabled</span></span>
- <span data-ttu-id="76b02-114">El grupo de Office 365 del equipo tiene permisos de coautoría.</span><span class="sxs-lookup"><span data-stu-id="76b02-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="76b02-115">Tras crear la nueva etiqueta o subetiqueta, publíquela para los usuarios, que podrán aplicarlas a los archivos, ya sea de forma local antes de cargarlas en el equipo o más tarde, cuando el archivo se almacene en el equipo.</span><span class="sxs-lookup"><span data-stu-id="76b02-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="76b02-116">Esta es la configuración del equipo extremadamente confidencial que usa etiquetas de confidencialidad para el cifrado de archivos y los permisos.</span><span class="sxs-lookup"><span data-stu-id="76b02-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![Protección de nivel de línea base de un equipo público.](../../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="76b02-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="76b02-118">See Also</span></span>

[<span data-ttu-id="76b02-119">Proteger los archivos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76b02-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="76b02-120">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="76b02-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
