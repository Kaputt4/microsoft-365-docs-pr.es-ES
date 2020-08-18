---
title: Equipo aislado para un proyecto principal de la compañía contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso usó un equipo con aislamiento de seguridad para un proyecto de secreto principal para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: ba9a66d2419e81aeb1eac026b16c0475ac6d0614
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778601"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="c6d08-103">Equipo aislado para un proyecto principal de la compañía contoso</span><span class="sxs-lookup"><span data-stu-id="c6d08-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="c6d08-104">Después de una ejecutiva fuera del sitio, el CEO de Contoso solicitó el desarrollo de un nuevo conjunto de productos y servicios que podían duplicar las ganancias de Contoso en los próximos cinco años.</span><span class="sxs-lookup"><span data-stu-id="c6d08-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="c6d08-105">El proyecto principal para desarrollar el plan empresarial, de ingeniería y de mercado se llamaba **proyecto 2x** y el personal clave en toda la compañía ha sido reclutado.</span><span class="sxs-lookup"><span data-stu-id="c6d08-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="c6d08-106">Las escalas de tiempo para la investigación y el desarrollo han sido estrictas, lo que significaba que la colaboración tenía que ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="c6d08-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="c6d08-107">Las entregas resultantes del proyecto 2 fueron los planes de negocio, las especificaciones de ingeniería y productos, y los materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c6d08-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="c6d08-108">Debido a su naturaleza confidencial, el acceso a estos archivos ha sido:</span><span class="sxs-lookup"><span data-stu-id="c6d08-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="c6d08-109">Restringido al proyecto el doble de miembros del equipo y al liderazgo Senior.</span><span class="sxs-lookup"><span data-stu-id="c6d08-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="c6d08-110">Cifrado y protegido con permisos para permitir el acceso únicamente al proyecto el doble de miembros del equipo y al liderazgo Senior, incluso si los archivos se distribuyeron fuera de sus carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c6d08-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="c6d08-111">El personal de TI de Contoso usó un [equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para el proyecto 2x y estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c6d08-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="c6d08-112">Paso 1: creado un equipo privado</span><span class="sxs-lookup"><span data-stu-id="c6d08-112">Step 1: Created a private team</span></span>

<span data-ttu-id="c6d08-113">En primer lugar, para proteger el acceso al sitio de SharePoint subyacente para el equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c6d08-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c6d08-114">A continuación, un administrador de Contoso ha creado un nuevo equipo privado denominado proyecto 2X y ha agregado las cuentas de usuario del proyecto el doble de personal como miembros.</span><span class="sxs-lookup"><span data-stu-id="c6d08-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="c6d08-115">También configuraron el equipo para que solo los propietarios del equipo del proyecto más 2X puedan crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="c6d08-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="c6d08-116">Para obtener información detallada sobre la configuración, vea [crear un equipo privado](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="c6d08-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="c6d08-117">Paso 2: se creó una etiqueta de confidencialidad para el equipo del proyecto de dos equipos</span><span class="sxs-lookup"><span data-stu-id="c6d08-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="c6d08-118">Los administradores de Contoso crearon una nueva etiqueta de confidencialidad denominada **proyecto 2x** que:</span><span class="sxs-lookup"><span data-stu-id="c6d08-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="c6d08-119">Cifrado habilitado.</span><span class="sxs-lookup"><span data-stu-id="c6d08-119">Enabled encryption.</span></span>
- <span data-ttu-id="c6d08-120">Permisos de co-autoría permitidos para el grupo de 2 proyectos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6d08-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="c6d08-121">Permisos de visor permitidos para el grupo de liderazgo Senior.</span><span class="sxs-lookup"><span data-stu-id="c6d08-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="c6d08-122">Acceso bloqueado a dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="c6d08-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="c6d08-123">Los archivos de la sección **documentos** del proyecto subyacente 2x del sitio de SharePoint estaban protegidos por:</span><span class="sxs-lookup"><span data-stu-id="c6d08-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="c6d08-124">Los permisos del sitio, que solo permiten permisos totales a miembros del proyecto con un 365 doble de permisos de grupo y lectura para el grupo de liderazgo Senior.</span><span class="sxs-lookup"><span data-stu-id="c6d08-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="c6d08-125">La etiqueta de sensibilidad proyecto 2X, con cifrado y permisos que viajan con el archivo si se mueven o se copian del sitio.</span><span class="sxs-lookup"><span data-stu-id="c6d08-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="c6d08-126">Para obtener información detallada sobre la configuración, vea [crear una etiqueta de confidencialidad](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="c6d08-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="c6d08-127">Paso 3: configurar el sitio de SharePoint subyacente</span><span class="sxs-lookup"><span data-stu-id="c6d08-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="c6d08-128">En primer lugar, para proteger el acceso al sitio de SharePoint subyacente para el equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c6d08-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="c6d08-129">A continuación, se configuraron parámetros de permisos adicionales para el sitio:</span><span class="sxs-lookup"><span data-stu-id="c6d08-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="c6d08-130">Para evitar que los miembros del grupo 2X del proyecto compartan el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="c6d08-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="c6d08-131">Para obtener información detallada sobre la configuración, vea [SharePoint Settings for a Team with Security Isolation](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="c6d08-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="c6d08-132">Para permisos de lectura para el grupo de liderazgo Senior.</span><span class="sxs-lookup"><span data-stu-id="c6d08-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="c6d08-133">A continuación, configuraron opciones de permisos adicionales para el sitio con el fin de evitar que los miembros del grupo 2X del proyecto compartan el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="c6d08-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="c6d08-134">Como se crearon los canales privados para el proyecto 2X, el propietario del grupo deshabilitó el uso compartido de invitado y estableció el vínculo compartir predeterminado con el valor **específico de personas** .</span><span class="sxs-lookup"><span data-stu-id="c6d08-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="c6d08-135">A continuación se muestra la configuración resultante del equipo del proyecto de 2X con aislamiento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c6d08-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![La configuración resultante del equipo del proyecto de 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="c6d08-137">Paso 4: miembros del equipo con experiencia en el 2X del proyecto</span><span class="sxs-lookup"><span data-stu-id="c6d08-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="c6d08-138">El personal de seguridad de Contoso ha entrenado en el proyecto el doble de miembros del equipo en un curso obligatorio que les ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="c6d08-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="c6d08-139">Cómo obtener acceso al nuevo proyecto el equipo al doble, usar reuniones y chats y cómo colaborar en archivos de equipo.</span><span class="sxs-lookup"><span data-stu-id="c6d08-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="c6d08-140">Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados de forma local.</span><span class="sxs-lookup"><span data-stu-id="c6d08-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="c6d08-141">Cómo etiquetar archivos con la etiqueta de confidencialidad del proyecto de dos.</span><span class="sxs-lookup"><span data-stu-id="c6d08-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="c6d08-142">Una demostración de cómo la etiqueta del proyecto 2X protege un archivo incluso cuando éste sale del equipo.</span><span class="sxs-lookup"><span data-stu-id="c6d08-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="c6d08-143">El resultado final fue un entorno seguro en el que el proyecto 2X de miembros del equipo colaboraron en un entorno seguro para chats, reuniones y archivos.</span><span class="sxs-lookup"><span data-stu-id="c6d08-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="c6d08-144">A continuación, se muestra un ejemplo de un archivo almacenado en el sitio del espacio de nombre 2 subyacente con la etiqueta de sensibilidad espacio de proyecto 2 asignada.</span><span class="sxs-lookup"><span data-stu-id="c6d08-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Un ejemplo de un archivo almacenado en el sitio del proyecto 2X subyacente](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="c6d08-146">En un par de instancias, Project 2X los miembros del equipo descargaron archivos protegidos por la etiqueta del proyecto 2X en una unidad local para trabajar sin conexión.</span><span class="sxs-lookup"><span data-stu-id="c6d08-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="c6d08-147">Sin embargo, después de que se soliciten las credenciales al abrirlas, se han dado cuenta de su error y se han eliminado.</span><span class="sxs-lookup"><span data-stu-id="c6d08-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="c6d08-148">Debido al entorno de colaboración de Microsoft Teams y las características de seguridad de Microsoft 365, los detalles del proyecto 2X se mantuvieron en secreto mientras dure el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c6d08-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="c6d08-149">Contoso anunció sus planes y se encuentra en el proceso de implementar los nuevos productos y servicios a la alegría de sus clientes e inversionistas y la Chagrin de sus competidores.</span><span class="sxs-lookup"><span data-stu-id="c6d08-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="c6d08-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c6d08-150">Next step</span></span>

<span data-ttu-id="c6d08-151">[Implemente un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) en su organización.</span><span class="sxs-lookup"><span data-stu-id="c6d08-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

