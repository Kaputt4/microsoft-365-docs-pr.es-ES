---
title: Equipo aislado para un proyecto principal de la compañía contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso usó un equipo con aislamiento de seguridad para un proyecto de secreto principal para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: 1083c9d3db3be9ca528b2eee40f072aa17c7431e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159460"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="843c6-103">Equipo aislado para un proyecto principal de la compañía contoso</span><span class="sxs-lookup"><span data-stu-id="843c6-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="843c6-104">Después de una ejecutiva fuera del sitio, el CEO de Contoso solicitó el desarrollo de un nuevo conjunto de productos y servicios que podían duplicar las ganancias de Contoso en los próximos cinco años.</span><span class="sxs-lookup"><span data-stu-id="843c6-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="843c6-105">El proyecto principal para desarrollar el plan empresarial, de ingeniería y de mercado se llamaba **proyecto 2x** y el personal clave en toda la compañía ha sido reclutado.</span><span class="sxs-lookup"><span data-stu-id="843c6-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="843c6-106">Las escalas de tiempo para la investigación y el desarrollo han sido estrictas, lo que significaba que la colaboración tenía que ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="843c6-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="843c6-107">Las entregas resultantes del proyecto 2 fueron los planes de negocio, las especificaciones de ingeniería y productos, y los materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="843c6-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="843c6-108">Debido a su naturaleza confidencial, el acceso a estos archivos ha sido:</span><span class="sxs-lookup"><span data-stu-id="843c6-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="843c6-109">Restringido al proyecto el doble de miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="843c6-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="843c6-110">Cifrado y protegido con permisos para permitir el acceso solo al doble de miembros del equipo, incluso si los archivos se distribuyeron fuera de sus carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="843c6-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="843c6-111">El personal de TI de Contoso usó un [equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para el proyecto 2x y estos pasos.</span><span class="sxs-lookup"><span data-stu-id="843c6-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="843c6-112">Paso 1: creado un equipo privado</span><span class="sxs-lookup"><span data-stu-id="843c6-112">Step 1: Created a private team</span></span>

<span data-ttu-id="843c6-113">En primer lugar, para proteger el acceso al sitio de SharePoint subyacente para el equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="843c6-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="843c6-114">A continuación, un administrador de Contoso ha creado un nuevo equipo privado denominado proyecto 2X y ha agregado las cuentas de usuario del proyecto el doble de personal como miembros.</span><span class="sxs-lookup"><span data-stu-id="843c6-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="843c6-115">Para obtener información detallada sobre la configuración, vea [crear un equipo privado](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="843c6-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="843c6-116">Paso 2: se creó una etiqueta de confidencialidad para el equipo del proyecto de dos equipos</span><span class="sxs-lookup"><span data-stu-id="843c6-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="843c6-117">Los administradores de Contoso crearon una nueva etiqueta de confidencialidad denominada **proyecto 2x** que:</span><span class="sxs-lookup"><span data-stu-id="843c6-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="843c6-118">Requiere cifrado.</span><span class="sxs-lookup"><span data-stu-id="843c6-118">Requires encryption.</span></span>
- <span data-ttu-id="843c6-119">Permite permisos de coautoría para el grupo 2 del proyecto en el segundo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="843c6-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="843c6-120">Los archivos de la sección **documentos** del proyecto subyacente 2x del sitio de SharePoint estaban protegidos por:</span><span class="sxs-lookup"><span data-stu-id="843c6-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="843c6-121">Los permisos del sitio, que solo permiten el acceso a los miembros del grupo de 2 a 2 grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="843c6-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="843c6-122">La etiqueta de sensibilidad proyecto 2X, con cifrado y permisos que viajan con el archivo si se mueven o se copian del sitio.</span><span class="sxs-lookup"><span data-stu-id="843c6-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="843c6-123">Para obtener información detallada sobre la configuración, vea [crear una etiqueta de confidencialidad](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="843c6-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="843c6-124">Paso 3: configurar el sitio de SharePoint subyacente</span><span class="sxs-lookup"><span data-stu-id="843c6-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="843c6-125">En primer lugar, para proteger el acceso al sitio de SharePoint subyacente para el equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="843c6-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="843c6-126">A continuación, se configuraron opciones de permisos adicionales para el sitio con el fin de evitar que Project 2X comparta el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="843c6-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="843c6-127">Para obtener información detallada sobre la configuración, vea [SharePoint Settings for a Team with Security Isolation](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="843c6-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="843c6-128">Esta es la configuración resultante del equipo del proyecto de 2X.</span><span class="sxs-lookup"><span data-stu-id="843c6-128">Here is the resulting configuration of the Project 2X team.</span></span>

![La configuración resultante del equipo del proyecto de 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="843c6-130">Paso 4: miembros del equipo con experiencia en el 2X del proyecto</span><span class="sxs-lookup"><span data-stu-id="843c6-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="843c6-131">El personal de seguridad de Contoso ha entrenado en el proyecto el doble de miembros del equipo en un curso obligatorio que les ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="843c6-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="843c6-132">Cómo obtener acceso al nuevo proyecto el equipo al doble, usar reuniones y chats y cómo colaborar en archivos de equipo.</span><span class="sxs-lookup"><span data-stu-id="843c6-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="843c6-133">Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados de forma local.</span><span class="sxs-lookup"><span data-stu-id="843c6-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="843c6-134">Una demostración de cómo la Directiva DLP bloquea los archivos para que no se compartan de forma externa.</span><span class="sxs-lookup"><span data-stu-id="843c6-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="843c6-135">Cómo etiquetar archivos con la etiqueta de confidencialidad del proyecto de dos.</span><span class="sxs-lookup"><span data-stu-id="843c6-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="843c6-136">Una demostración de cómo la etiqueta del proyecto 2X protege un archivo incluso cuando éste sale del equipo.</span><span class="sxs-lookup"><span data-stu-id="843c6-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="843c6-137">El resultado final fue un entorno seguro en el que el proyecto 2X de miembros del equipo colaboraron en un entorno seguro para chats, reuniones y archivos.</span><span class="sxs-lookup"><span data-stu-id="843c6-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="843c6-138">A continuación, se muestra un ejemplo de un archivo almacenado en el sitio del espacio de nombre 2 subyacente con la etiqueta de sensibilidad espacio de proyecto 2 asignada.</span><span class="sxs-lookup"><span data-stu-id="843c6-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Un ejemplo de un archivo almacenado en el sitio del proyecto 2X subyacente](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="843c6-140">En un par de instancias, Project 2X los miembros del equipo descargaron archivos protegidos por la etiqueta del proyecto 2X en una unidad local para trabajar sin conexión.</span><span class="sxs-lookup"><span data-stu-id="843c6-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="843c6-141">Sin embargo, después de que se soliciten las credenciales al abrirlas, se han dado cuenta de su error y se han eliminado.</span><span class="sxs-lookup"><span data-stu-id="843c6-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="843c6-142">Debido al entorno de colaboración de Microsoft Teams y las características de seguridad de Microsoft 365, los detalles del proyecto 2X se mantuvieron en secreto mientras dure el proyecto.</span><span class="sxs-lookup"><span data-stu-id="843c6-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="843c6-143">Contoso anunció sus planes y se encuentra en el proceso de implementar los nuevos productos y servicios a la alegría de sus clientes e inversionistas y la Chagrin de sus competidores.</span><span class="sxs-lookup"><span data-stu-id="843c6-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="843c6-144">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="843c6-144">Next step</span></span>

<span data-ttu-id="843c6-145">[Implemente un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) en su organización.</span><span class="sxs-lookup"><span data-stu-id="843c6-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

