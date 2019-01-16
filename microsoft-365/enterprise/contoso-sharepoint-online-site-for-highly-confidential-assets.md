---
title: Sitio de SharePoint Online para activos digitales altamente confidenciales de la empresa Contoso
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Resumen: Cómo Contoso implementa un sitio de SharePoint Online para altamente regulados datos para facilitar la colaboración entre su investigación de los equipos.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871750"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="60ea3-103">Sitio de SharePoint Online para activos digitales altamente confidenciales de la empresa Contoso</span><span class="sxs-lookup"><span data-stu-id="60ea3-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="60ea3-104">**Resumen:** Cómo Contoso implementa un sitio de SharePoint Online para datos altamente regulados para facilitar la colaboración entre sus equipos de investigación.</span><span class="sxs-lookup"><span data-stu-id="60ea3-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="60ea3-p101">Activos más valiosos de Contoso son de su propiedad intelectual en el formulario de secretos comerciales, como las técnicas de fabricación propietario y las especificaciones de productos que se encuentran en el desarrollo de diseño. Estos activos están en formato digital, que originalmente se almacenan como archivos en un sitio de SharePoint Server 2016. Cuando Contoso implementa Microsoft 365 Enterprise, que deseaba realizar la transición de sus activos digitales de local a la nube para facilitar el acceso y la colaboración más susceptible a través de equipos de investigación en Bangalore, Moscú, Nueva York, Beijing y París.</span><span class="sxs-lookup"><span data-stu-id="60ea3-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="60ea3-108">Sin embargo, debido a su naturaleza confidencial, debe tener acceso a estos archivos:</span><span class="sxs-lookup"><span data-stu-id="60ea3-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="60ea3-109">Restringido al conjunto de personas que tienen permiso para ver o cambiar a ellas, con permisos de curso para el sitio administrados sólo por los administradores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60ea3-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="60ea3-110">Protegida con la prevención de pérdida de datos (DLP) para evitar que los usuarios de distribución de los mismos fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="60ea3-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="60ea3-111">Access cifrada y protegida con control de listas para impedir que los usuarios no autorizados obtengan acceso a su contenido, incluso si se distribuyen fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="60ea3-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="60ea3-112">Los administradores de seguridad y SharePoint en Contoso del departamento de TI decidió usar un [sitio de SharePoint Online para altamente regulado datos](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="60ea3-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="60ea3-113">Contoso utiliza estos pasos para crear y proteger un sitios de grupo de SharePoint Online para sus equipos de investigación.</span><span class="sxs-lookup"><span data-stu-id="60ea3-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="60ea3-114">Paso 1: Revisar y comprobar a los miembros de grupos de investigación de equipo</span><span class="sxs-lookup"><span data-stu-id="60ea3-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="60ea3-p102">Los administradores de TI de Contoso realizan una revisión del conjunto de grupos de seguridad de sus equipos de investigación. Ha quitado cualquier persona que no era un entrevistador o no tuvo acceso a los activos de investigación.</span><span class="sxs-lookup"><span data-stu-id="60ea3-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="60ea3-117">También y crea estos nuevos grupos de seguridad:</span><span class="sxs-lookup"><span data-stu-id="60ea3-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="60ea3-118">**Administradores de investigación**  El conjunto de administradores de SharePoint que tienen control total a través del sitio, incluida la posibilidad de modificar los permisos.</span><span class="sxs-lookup"><span data-stu-id="60ea3-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="60ea3-119">**Research (miembros)**  El conjunto de grupos de seguridad para los equipos de investigación todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="60ea3-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="60ea3-120">**Visores de investigación**  El conjunto de usuarios de administración, como los ejecutivos en la organización de investigación, que puede ver los activos en el sitio.</span><span class="sxs-lookup"><span data-stu-id="60ea3-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="60ea3-121">Paso 2: Crear un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="60ea3-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="60ea3-p103">Los administradores de Contoso SharePoint crea por primera vez un nuevo sitio de grupo con el nombre **Research**. A continuación, configurar:</span><span class="sxs-lookup"><span data-stu-id="60ea3-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="60ea3-124">El nivel de permiso Control total para utilizar el grupo de SharePoint de propietarios de investigación, que tiene el grupo de seguridad **Administradores de investigación** como un miembro</span><span class="sxs-lookup"><span data-stu-id="60ea3-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="60ea3-125">El nivel de permisos Editar para usar el grupo de SharePoint miembros de investigación, que tiene el grupo de seguridad de **Los miembros de investigación** como un miembro</span><span class="sxs-lookup"><span data-stu-id="60ea3-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="60ea3-126">El nivel de permiso de lectura para usar el grupo de visitantes de SharePoint de investigación, que tiene el grupo de seguridad de **Visores de investigación** como un miembro</span><span class="sxs-lookup"><span data-stu-id="60ea3-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="60ea3-127">A continuación presentamos los niveles de permisos de SharePoint resultantes, los grupos de SharePoint y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="60ea3-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="60ea3-128">A continuación, configuran restricciones adicionales para el sitio.</span><span class="sxs-lookup"><span data-stu-id="60ea3-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="60ea3-129">Para los detalles de configuración, vea [implementar un sitio de grupo de SharePoint Online aislado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="60ea3-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="60ea3-130">Paso 3: Configurar el sitio para una etiqueta de Office 365 restrictivo directiva de DLP</span><span class="sxs-lookup"><span data-stu-id="60ea3-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="60ea3-131">En primer lugar, los administradores de Contoso aplican la etiqueta de Office 365 **Altamente confidencial** en el sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="60ea3-132">A continuación, crea una nueva directiva de DLP de Office 365 con el nombre **Research** que:</span><span class="sxs-lookup"><span data-stu-id="60ea3-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="60ea3-133">Utiliza la etiqueta de Office 365 **Altamente confidencial** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="60ea3-134">Se aplica al sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="60ea3-135">Impide que los usuarios compartir documentos.</span><span class="sxs-lookup"><span data-stu-id="60ea3-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="60ea3-136">Para los detalles de configuración, vea [archivos de protección de SharePoint Online con las etiquetas de Office 365 y DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="60ea3-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="60ea3-137">Paso 4: Crear una etiqueta de fracciones de protección de la información de Azure para el sitio</span><span class="sxs-lookup"><span data-stu-id="60ea3-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="60ea3-138">Los administradores de Contoso creados una nueva etiqueta de fracciones de protección de la información de Azure denominan **investigación** de la etiqueta **Altamente confidencial** de forma predeterminada en una directiva de ámbito:</span><span class="sxs-lookup"><span data-stu-id="60ea3-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="60ea3-139">Requiere cifrado.</span><span class="sxs-lookup"><span data-stu-id="60ea3-139">Requires encryption.</span></span>
- <span data-ttu-id="60ea3-140">Permite acceso total por los miembros del grupo de seguridad de **Los miembros de la investigación** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="60ea3-141">Permite el acceso de lectura por los miembros del grupo de seguridad de **Los visores de investigación** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="60ea3-142">A continuación, implementa al cliente de protección de la información de Azure en los dispositivos de miembros del equipo de investigación.</span><span class="sxs-lookup"><span data-stu-id="60ea3-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="60ea3-143">Para los detalles de configuración, vea [archivos de protección de SharePoint Online con protección de la información de Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="60ea3-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="60ea3-144">Aquí es la configuración resultante del sitio de **investigación** de activos altamente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="60ea3-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="60ea3-145">Paso 5: Migrar los datos de investigación de SharePoint local</span><span class="sxs-lookup"><span data-stu-id="60ea3-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="60ea3-146">Los administradores de Contoso se mueven que todos los locales en los archivos en el sitio de SharePoint Server 2016 local a las carpetas en el nuevo sitio de SharePoint Online de **investigación** de la investigación.</span><span class="sxs-lookup"><span data-stu-id="60ea3-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="60ea3-147">Paso 6: Aprendizaje a sus usuarios</span><span class="sxs-lookup"><span data-stu-id="60ea3-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="60ea3-148">Personal de seguridad de Contoso formado los equipos de investigación en un curso obligatorio que había escalonada ellos a través de:</span><span class="sxs-lookup"><span data-stu-id="60ea3-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="60ea3-149">Cómo obtener acceso a sus archivos existentes y el nuevo sitio de SharePoint Online de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="60ea3-150">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="60ea3-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="60ea3-151">Una demostración de cómo la directiva de DLP bloquea los archivos desde que se está compartiendo externamente.</span><span class="sxs-lookup"><span data-stu-id="60ea3-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="60ea3-152">Cómo utilizar al cliente de protección de la información de Azure para etiquetar los archivos de investigación con la etiqueta de fracciones de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="60ea3-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="60ea3-153">Una demostración de cómo la etiqueta subcaracterística **Research** protege un archivo incluso cuando lo se agotaron desde el sitio.</span><span class="sxs-lookup"><span data-stu-id="60ea3-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="60ea3-154">El resultado final es un entorno seguro en el que los investigadores puedan colaborar en toda la organización en un entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="60ea3-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="60ea3-155">Si un documento de investigación con la etiqueta de fracciones de **investigación** se agotaron desde el sitio de **investigación** , es cifradas y sólo pueden tener acceso los miembros de los grupos de seguridad de **Los miembros de la investigación** y **Los visores de investigación** con credenciales válidas.</span><span class="sxs-lookup"><span data-stu-id="60ea3-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="60ea3-156">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="60ea3-156">Next step</span></span>

<span data-ttu-id="60ea3-157">[Implemente](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="60ea3-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

