---
title: Equipo aislado para un proyecto secreto de Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
description: 'Resumen: cómo Contoso usó un equipo con aislamiento de seguridad para un proyecto secreto para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029021"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="7ef42-103">Equipo aislado para un proyecto secreto de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="7ef42-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="7ef42-104">Después de un ejecutivo fuera del sitio, el director ejecutivo de Contoso ordenó el desarrollo de un nuevo conjunto de productos y servicios que podría duplicar las ganancias de Contoso en los próximos cinco años.</span><span class="sxs-lookup"><span data-stu-id="7ef42-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="7ef42-105">El proyecto secreto para desarrollar el plan de negocio, ingeniería y mercado se llamó **Project 2X** y se reclutó personal clave en toda la compañía.</span><span class="sxs-lookup"><span data-stu-id="7ef42-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="7ef42-106">Las escalas de tiempo para la investigación y el desarrollo eran estrechas, lo que significaba que la colaboración debía ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="7ef42-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="7ef42-107">Los resultados de Project 2X fueron planes de negocio, especificaciones de producto e ingeniería, y materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7ef42-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="7ef42-108">Debido a su naturaleza confidencial, el acceso a estos archivos era:</span><span class="sxs-lookup"><span data-stu-id="7ef42-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="7ef42-109">Restringido a los miembros del equipo de Project 2X y a los altos directivos.</span><span class="sxs-lookup"><span data-stu-id="7ef42-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="7ef42-110">Cifrado y protegido con permisos para permitir el acceso solo a los miembros del equipo de Project 2X y a los jefes de equipo, incluso si los archivos se distribuyeron fuera de sus carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="7ef42-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="7ef42-111">El personal de TI de Contoso usó un [equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para Project 2X y estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7ef42-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="7ef42-112">Paso 1: Crear un equipo privado</span><span class="sxs-lookup"><span data-stu-id="7ef42-112">Step 1: Created a private team</span></span>

<span data-ttu-id="7ef42-113">En primer lugar, para proteger el acceso al sitio subyacente de SharePoint para el equipo, los administradores de TI de Contoso configuraron las directivas de acceso [de SharePoint recomendadas.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ef42-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="7ef42-114">A continuación, un administrador de TI de Contoso creó un nuevo equipo privado denominado Project 2X y agregó las cuentas de usuario del personal de Project 2X como miembros.</span><span class="sxs-lookup"><span data-stu-id="7ef42-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="7ef42-115">También configuraron el equipo para que solo los propietarios de equipos de Project 2X puedan crear canales privados.</span><span class="sxs-lookup"><span data-stu-id="7ef42-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="7ef42-116">Para obtener los detalles de configuración, vea [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="7ef42-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="7ef42-117">Paso 2: Crear una etiqueta de confidencialidad para el equipo de Project 2X</span><span class="sxs-lookup"><span data-stu-id="7ef42-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="7ef42-118">Los administradores de Contoso crearon una nueva etiqueta de confidencialidad denominada **Project 2X** que:</span><span class="sxs-lookup"><span data-stu-id="7ef42-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="7ef42-119">Cifrado habilitado.</span><span class="sxs-lookup"><span data-stu-id="7ef42-119">Enabled encryption.</span></span>
- <span data-ttu-id="7ef42-120">Se Co-Author permisos para el grupo de Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ef42-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="7ef42-121">Permisos de visor permitidos para el grupo de liderazgo sénior.</span><span class="sxs-lookup"><span data-stu-id="7ef42-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="7ef42-122">Acceso bloqueado a dispositivos no administrados.</span><span class="sxs-lookup"><span data-stu-id="7ef42-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="7ef42-123">Los archivos de la **sección Documentos** del sitio subyacente de SharePoint de Project 2X estaban protegidos por:</span><span class="sxs-lookup"><span data-stu-id="7ef42-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="7ef42-124">Permisos de sitio, que solo permiten permisos completos a los miembros del grupo de Project 2X Microsoft 365 y permisos de lectura para el grupo de liderazgo sénior.</span><span class="sxs-lookup"><span data-stu-id="7ef42-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="7ef42-125">Etiqueta de confidencialidad de Project 2X, con cifrado y permisos que viajan con el archivo si se mueve o copia del sitio.</span><span class="sxs-lookup"><span data-stu-id="7ef42-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="7ef42-126">Para obtener los detalles de configuración, vea [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="7ef42-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="7ef42-127">Paso 3: Configurar el sitio subyacente de SharePoint</span><span class="sxs-lookup"><span data-stu-id="7ef42-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="7ef42-128">En primer lugar, para proteger el acceso al sitio subyacente de SharePoint para el equipo, los administradores de TI de Contoso configuraron las directivas de acceso [de SharePoint recomendadas.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ef42-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="7ef42-129">A continuación, configuraron opciones de permisos adicionales para el sitio:</span><span class="sxs-lookup"><span data-stu-id="7ef42-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="7ef42-130">Para evitar que los miembros del grupo de Project 2X compartan el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="7ef42-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="7ef42-131">Para obtener más información sobre la configuración, [vea Configuración de SharePoint para un equipo con aislamiento de seguridad.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="7ef42-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="7ef42-132">Para permisos de lectura para el grupo de liderazgo sénior.</span><span class="sxs-lookup"><span data-stu-id="7ef42-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="7ef42-133">A continuación, configuraron opciones de permisos adicionales para el sitio para impedir que los miembros del grupo de Project 2X compartan el acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="7ef42-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="7ef42-134">Cuando se crearon canales privados para Project 2X, el propietario del grupo deshabilitó el uso compartido de invitados y estableció el vínculo de uso compartido predeterminado en **el valor Personas** específicas.</span><span class="sxs-lookup"><span data-stu-id="7ef42-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="7ef42-135">Esta es la configuración resultante del equipo de Project 2X con aislamiento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7ef42-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![La configuración resultante del equipo de Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="7ef42-137">Paso 4: Miembros del equipo de Project 2X formados</span><span class="sxs-lookup"><span data-stu-id="7ef42-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="7ef42-138">El personal de seguridad de Contoso entrenó a los miembros del equipo de Project 2X en un curso obligatorio que les intensó:</span><span class="sxs-lookup"><span data-stu-id="7ef42-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="7ef42-139">Cómo acceder al nuevo equipo de Project 2X, usar reuniones y chats y cómo colaborar en archivos de equipo.</span><span class="sxs-lookup"><span data-stu-id="7ef42-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="7ef42-140">Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados localmente.</span><span class="sxs-lookup"><span data-stu-id="7ef42-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="7ef42-141">Cómo etiquetar archivos con la etiqueta de confidencialidad de Project 2X.</span><span class="sxs-lookup"><span data-stu-id="7ef42-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="7ef42-142">Una demostración de cómo la etiqueta de Project 2X protege un archivo incluso cuando deja el equipo.</span><span class="sxs-lookup"><span data-stu-id="7ef42-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="7ef42-143">El resultado final fue un entorno seguro en el que los miembros del equipo de Project 2X colaboraban en un entorno seguro para chats, reuniones y archivos.</span><span class="sxs-lookup"><span data-stu-id="7ef42-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="7ef42-144">Este es un ejemplo de un archivo almacenado en el sitio subyacente de Project 2X con la etiqueta de confidencialidad de Project 2X asignada.</span><span class="sxs-lookup"><span data-stu-id="7ef42-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Un ejemplo de un archivo almacenado en el sitio subyacente de Project 2X](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="7ef42-146">En un par de instancias, los miembros del equipo de Project 2X descargaron archivos protegidos por la etiqueta de Project 2X en una unidad local para el trabajo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="7ef42-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="7ef42-147">Sin embargo, después de que se les pidan credenciales al abrirlos, se dieron cuenta de su error y los eliminaron.</span><span class="sxs-lookup"><span data-stu-id="7ef42-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="7ef42-148">Debido al entorno de colaboración de Teams y las características de seguridad de Microsoft 365, los detalles de Project 2X se mantuvieron en secreto durante la duración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ef42-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="7ef42-149">Contoso anunció sus planes y está en el proceso de implementar los nuevos productos y servicios para el deleite de sus clientes e inversores y el enojo de sus competidores.</span><span class="sxs-lookup"><span data-stu-id="7ef42-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="7ef42-150">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7ef42-150">Next step</span></span>

<span data-ttu-id="7ef42-151">[Implementar un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) en la organización.</span><span class="sxs-lookup"><span data-stu-id="7ef42-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

