---
title: Equipo para un proyecto confidencial de la empresa Contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso usó un equipo para datos altamente regulados para un proyecto de secreto principal para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636503"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="73770-103">Equipo para un proyecto confidencial de la empresa Contoso</span><span class="sxs-lookup"><span data-stu-id="73770-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="73770-104">Después de una ejecutiva fuera del sitio, el CEO de Contoso solicitó el desarrollo de un nuevo conjunto de productos y servicios que podían duplicar las ganancias de Contoso en los próximos cinco años.</span><span class="sxs-lookup"><span data-stu-id="73770-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="73770-105">El proyecto principal para desarrollar el plan empresarial, de ingeniería y de mercado se llamaba **proyecto 2x** y el personal clave en toda la compañía ha sido reclutado.</span><span class="sxs-lookup"><span data-stu-id="73770-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="73770-106">Las escalas de tiempo para la investigación y el desarrollo han sido estrictas, lo que significaba que la colaboración tenía que ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="73770-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="73770-107">Las entregas resultantes del proyecto 2 fueron los planes de negocio, las especificaciones de ingeniería y productos, y los materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="73770-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="73770-108">Debido a su naturaleza confidencial, el acceso a estos archivos ha sido:</span><span class="sxs-lookup"><span data-stu-id="73770-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="73770-109">Restringido al proyecto el doble de miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="73770-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="73770-110">Está protegido con una directiva de prevención de pérdida de datos (DLP) para evitar que los miembros del equipo con un uso compartido al doble del equipo lo compartan fuera del equipo.</span><span class="sxs-lookup"><span data-stu-id="73770-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="73770-111">Cifrado y protegido con permisos para permitir el acceso solo al doble integrante del equipo, incluso si los archivos se distribuyeron fuera de contoso.</span><span class="sxs-lookup"><span data-stu-id="73770-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="73770-112">El personal de TI de Contoso usó un [equipo para datos altamente regulados](secure-teams-highly-regulated-data-scenario.md) para el proyecto 2x y estos pasos.</span><span class="sxs-lookup"><span data-stu-id="73770-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="73770-113">Paso 1: creación de un equipo privado y bloqueo del sitio de SharePoint subyacente</span><span class="sxs-lookup"><span data-stu-id="73770-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="73770-114">Para proteger el acceso al sitio de SharePoint subyacente del equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="73770-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="73770-115">A continuación, un administrador de Contoso ha creado un nuevo equipo privado denominado proyecto 2X y ha agregado las cuentas de usuario del proyecto el doble de personal como miembros.</span><span class="sxs-lookup"><span data-stu-id="73770-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="73770-116">A continuación, se configuraron opciones de permisos adicionales para el sitio con el fin de evitar que Project 2X comparta el acceso al sitio y evitar que se solicite el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="73770-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="73770-117">Para obtener información detallada sobre la configuración, vea [configuración de SharePoint para un equipo altamente regulado](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="73770-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="73770-118">Paso 2: configurar una directiva DLP y el sitio subyacente para una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="73770-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="73770-119">En primer lugar, los administradores de Contoso aplicaron la etiqueta de retención **altamente confidencial** existente a la sección de **documentos** del sitio de SharePoint subyacente del equipo del proyecto de dos equipos.</span><span class="sxs-lookup"><span data-stu-id="73770-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="73770-120">A continuación, creamos una nueva Directiva DLP denominada **proyecto 2x** que:</span><span class="sxs-lookup"><span data-stu-id="73770-120">Next, they created a new DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="73770-121">Usa la etiqueta de retención muy confidencial.</span><span class="sxs-lookup"><span data-stu-id="73770-121">Uses the Highly Confidential retention label.</span></span>
- <span data-ttu-id="73770-122">Bloquea a los usuarios cuando intentan compartir un archivo en el equipo del proyecto el doble de equipo fuera de contoso.</span><span class="sxs-lookup"><span data-stu-id="73770-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="73770-123">Para obtener información detallada sobre la configuración, consulte [proteger archivos en Microsoft Teams con etiquetas de retención y DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="73770-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="73770-124">Paso 3: se creó una etiqueta de confidencialidad para el equipo del proyecto de dos equipos</span><span class="sxs-lookup"><span data-stu-id="73770-124">Step 3: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="73770-125">Los administradores de Contoso crearon una nueva etiqueta de confidencialidad denominada **proyecto 2x** que:</span><span class="sxs-lookup"><span data-stu-id="73770-125">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="73770-126">Requiere cifrado.</span><span class="sxs-lookup"><span data-stu-id="73770-126">Requires encryption.</span></span>
- <span data-ttu-id="73770-127">Permite permisos de coautoría para el grupo 2 del proyecto en el segundo grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73770-127">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="73770-128">Esta es la configuración resultante del equipo del proyecto de 2X.</span><span class="sxs-lookup"><span data-stu-id="73770-128">Here is the resulting configuration of the Project 2X team.</span></span>

![La configuración resultante del equipo del proyecto de 2X](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="73770-130">Los archivos de la sección documentos del proyecto subyacente 2X del sitio de SharePoint estaban protegidos por:</span><span class="sxs-lookup"><span data-stu-id="73770-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="73770-131">Los permisos del sitio, que solo permiten el acceso a los miembros del grupo de 2 a 2 grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73770-131">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="73770-132">La etiqueta de retención extremadamente confidencial, que se asigna automáticamente a nuevos archivos.</span><span class="sxs-lookup"><span data-stu-id="73770-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="73770-133">Una directiva DLP que usa la etiqueta de retención extremadamente confidencial y la configuración que impide que el archivo se comparta con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="73770-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="73770-134">La etiqueta de sensibilidad proyecto 2X, con cifrado y permisos que viajan con el archivo si se mueven o se copian del sitio.</span><span class="sxs-lookup"><span data-stu-id="73770-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="73770-135">A continuación, se muestra un ejemplo de un archivo almacenado en el sitio del espacio de nombre 2X subyacente con la etiqueta de retención altamente regulada y la etiqueta de sensibilidad espacio en proyecto 2X asignada.</span><span class="sxs-lookup"><span data-stu-id="73770-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Un ejemplo de un archivo almacenado en el sitio del proyecto 2X subyacente](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="73770-137">Paso 4: miembros del equipo con experiencia en el 2X del proyecto</span><span class="sxs-lookup"><span data-stu-id="73770-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="73770-138">El personal de seguridad de Contoso ha entrenado en el proyecto el doble de miembros del equipo en un curso obligatorio que les ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="73770-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="73770-139">Cómo obtener acceso al nuevo proyecto el equipo al doble, usar reuniones y chats y cómo colaborar en archivos de equipo.</span><span class="sxs-lookup"><span data-stu-id="73770-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="73770-140">Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados de forma local.</span><span class="sxs-lookup"><span data-stu-id="73770-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="73770-141">Una demostración de cómo la Directiva DLP bloquea los archivos para que no se compartan de forma externa.</span><span class="sxs-lookup"><span data-stu-id="73770-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="73770-142">Cómo etiquetar archivos con la etiqueta de confidencialidad del proyecto de dos.</span><span class="sxs-lookup"><span data-stu-id="73770-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="73770-143">Una demostración de cómo la etiqueta del proyecto 2X protege un archivo incluso cuando éste sale del equipo.</span><span class="sxs-lookup"><span data-stu-id="73770-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="73770-144">El resultado final fue un entorno seguro en el que el proyecto 2X de miembros del equipo colaboraron en un entorno seguro para chats, reuniones y archivos.</span><span class="sxs-lookup"><span data-stu-id="73770-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="73770-145">En un par de instancias, Project 2X los miembros del equipo descargaron archivos protegidos por la etiqueta del proyecto 2X en una unidad local para trabajar sin conexión.</span><span class="sxs-lookup"><span data-stu-id="73770-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="73770-146">Sin embargo, después de que se soliciten las credenciales al abrirlas, se han dado cuenta de su error y se han eliminado.</span><span class="sxs-lookup"><span data-stu-id="73770-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="73770-147">Debido al entorno de colaboración de Microsoft Teams y las características de seguridad de Microsoft 365, los detalles del proyecto 2X se mantuvieron en secreto mientras dure el proyecto.</span><span class="sxs-lookup"><span data-stu-id="73770-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="73770-148">Contoso anunció sus planes y se encuentra en el proceso de implementar los nuevos productos y servicios a la alegría de sus clientes e inversionistas y la Chagrin de sus competidores.</span><span class="sxs-lookup"><span data-stu-id="73770-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="73770-149">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="73770-149">Next step</span></span>

<span data-ttu-id="73770-150">[Implementar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="73770-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="73770-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="73770-151">See also</span></span>

<span data-ttu-id="73770-152">[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="73770-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
