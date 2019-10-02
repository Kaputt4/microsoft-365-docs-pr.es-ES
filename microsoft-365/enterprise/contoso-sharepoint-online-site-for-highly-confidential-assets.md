---
title: Sitio de SharePoint Online para activos digitales altamente confidenciales de Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso implementó un sitio de SharePoint Online para datos altamente regulados para una colaboración más sencilla entre sus equipos de investigación.'
ms.openlocfilehash: 6c61d02c802a77afeb93a58b59114741c6630f9e
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369531"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="30ef2-103">Sitio de SharePoint Online para activos digitales altamente confidenciales de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="30ef2-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="30ef2-104">**Resumen:** Cómo contoso implementó un sitio de SharePoint Online para datos altamente regulados para una colaboración más sencilla entre sus equipos de investigación.</span><span class="sxs-lookup"><span data-stu-id="30ef2-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="30ef2-105">Los activos más valiosos de Contoso son su propiedad intelectual en forma de secretos comerciales, como técnicas de fabricación patentadas, así como especificaciones de diseño para productos que están en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="30ef2-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="30ef2-106">Estos activos están en formato digital, que se almacenaban originalmente como archivos en un sitio de SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="30ef2-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="30ef2-107">Cuando contoso implementó Microsoft 365 Enterprise, quería realizar la transición de sus activos digitales locales a la nube para facilitar el acceso y aumentar la colaboración entre los equipos de investigación de París, Moscú, Nueva York, Beijing y Bangalore.</span><span class="sxs-lookup"><span data-stu-id="30ef2-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="30ef2-108">Sin embargo, debido a su carácter confidencial, el acceso a estos archivos debe ser:</span><span class="sxs-lookup"><span data-stu-id="30ef2-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="30ef2-109">Se limita al conjunto de personas a las que se les permite ver o cambiar, con permisos en curso para el sitio administrado solo por los administradores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="30ef2-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="30ef2-110">Protegido con prevención de pérdida de datos (DLP) para evitar que los usuarios los distribuyan fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="30ef2-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="30ef2-111">Cifrado y protegido con listas de control de acceso para evitar que los usuarios no autorizados obtengan acceso a su contenido, incluso si se distribuyen fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="30ef2-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="30ef2-112">Los administradores de SharePoint y de seguridad en el Departamento de TI de Contoso decidieron usar un [sitio de SharePoint Online para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="30ef2-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="30ef2-113">Contoso usó estos pasos para crear y proteger sitios de grupo de SharePoint Online para sus equipos de investigación.</span><span class="sxs-lookup"><span data-stu-id="30ef2-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="30ef2-114">Paso 1: revisado y comprobado los miembros de los grupos de equipo de investigación</span><span class="sxs-lookup"><span data-stu-id="30ef2-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="30ef2-115">Los administradores de TI de Contoso realizaron una revisión del conjunto de grupos de seguridad para sus equipos de investigación.</span><span class="sxs-lookup"><span data-stu-id="30ef2-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="30ef2-116">Quitaron a todos los usuarios que no eran un investigador o no necesitaban acceso a los activos de investigación.</span><span class="sxs-lookup"><span data-stu-id="30ef2-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="30ef2-117">También han creado estos nuevos grupos de seguridad:</span><span class="sxs-lookup"><span data-stu-id="30ef2-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="30ef2-118">**Investigación: administradores**  El conjunto de administradores de SharePoint que tienen control total sobre el sitio, incluida la capacidad de modificar permisos.</span><span class="sxs-lookup"><span data-stu-id="30ef2-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="30ef2-119">**Investigación: miembros**  El conjunto de grupos de seguridad para los equipos de investigación de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="30ef2-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="30ef2-120">**Investigación-visores**  El conjunto de usuarios de administración, como los ejecutivos de la organización de investigación, que solo pueden ver los activos del sitio.</span><span class="sxs-lookup"><span data-stu-id="30ef2-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="30ef2-121">Paso 2: crear un sitio de grupo de SharePoint Online aislado</span><span class="sxs-lookup"><span data-stu-id="30ef2-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="30ef2-122">En primer lugar, los administradores de SharePoint de Contoso creaban un nuevo sitio de grupo denominado **Research**.</span><span class="sxs-lookup"><span data-stu-id="30ef2-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="30ef2-123">A continuación, se configuran:</span><span class="sxs-lookup"><span data-stu-id="30ef2-123">They then configured:</span></span>

- <span data-ttu-id="30ef2-124">El nivel de permiso control total para usar el grupo de SharePoint propietarios de la investigación, que tiene el grupo de seguridad **Research-Admins** como miembro</span><span class="sxs-lookup"><span data-stu-id="30ef2-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="30ef2-125">El nivel de permisos editar para usar el grupo de SharePoint miembros de Research, que tiene el grupo de seguridad **integrantes de investigación** como miembro</span><span class="sxs-lookup"><span data-stu-id="30ef2-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="30ef2-126">El nivel de permiso de lectura para usar el grupo de SharePoint visitantes de investigación, que tiene el grupo **de seguridad Research-views** como miembro</span><span class="sxs-lookup"><span data-stu-id="30ef2-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="30ef2-127">Estos son los niveles de permisos resultantes de SharePoint, los grupos de SharePoint y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="30ef2-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![Niveles de permisos de SharePoint, grupos de SharePoint y sus miembros](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="30ef2-129">A continuación, se configuraron restricciones adicionales para el sitio.</span><span class="sxs-lookup"><span data-stu-id="30ef2-129">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="30ef2-130">Para obtener información detallada sobre la configuración, vea [implementar un sitio de grupo de SharePoint Online aislado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="30ef2-130">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="30ef2-131">Paso 3: configurar el sitio para una directiva DLP restrictiva</span><span class="sxs-lookup"><span data-stu-id="30ef2-131">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="30ef2-132">En primer lugar, los administradores de Contoso aplicaron la etiqueta de retención **altamente confidencial** de Office 365 al sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-132">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="30ef2-133">A continuación, creamos una nueva Directiva de DLP de Office 365 denominada **Research** que:</span><span class="sxs-lookup"><span data-stu-id="30ef2-133">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="30ef2-134">Usa la etiqueta de retención **alta confidencial** de Office 365.</span><span class="sxs-lookup"><span data-stu-id="30ef2-134">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="30ef2-135">Se aplica al sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-135">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="30ef2-136">Bloquea a los usuarios cuando intentan compartir un activo digital en el sitio de **investigación** fuera de contoso.</span><span class="sxs-lookup"><span data-stu-id="30ef2-136">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="30ef2-137">Para obtener información detallada sobre la configuración, vea [proteger archivos de SharePoint Online con etiquetas de retención y DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="30ef2-137">For the configuration details, see [Protect SharePoint Online files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="30ef2-138">Paso 4: se creó una etiqueta secundaria de Azure Information Protection para el sitio</span><span class="sxs-lookup"><span data-stu-id="30ef2-138">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="30ef2-139">Los administradores de Contoso crearon una nueva etiqueta secundaria de Azure Information Protection denominada **Research** of the default **extremadamente Confidential** Label en una directiva con ámbito que:</span><span class="sxs-lookup"><span data-stu-id="30ef2-139">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="30ef2-140">Requiere cifrado.</span><span class="sxs-lookup"><span data-stu-id="30ef2-140">Requires encryption.</span></span>
- <span data-ttu-id="30ef2-141">Permite el acceso total por parte de miembros del grupo de seguridad **Research-Members** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-141">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="30ef2-142">Permite el acceso de lectura por parte de los miembros del grupo de seguridad **Research-Viewers** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-142">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="30ef2-143">A continuación, implementó el cliente de Azure Information Protection en los dispositivos de los miembros del equipo de investigación.</span><span class="sxs-lookup"><span data-stu-id="30ef2-143">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="30ef2-144">Para obtener información detallada sobre la configuración, vea [proteger archivos de SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="30ef2-144">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="30ef2-145">Esta es la configuración resultante del sitio de **investigación** para los activos extremadamente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="30ef2-145">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![La configuración resultante del sitio \* \* Research \* \* para los activos extremadamente confidenciales](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="30ef2-147">Los archivos de las carpetas del sitio de **investigación** están protegidos por:</span><span class="sxs-lookup"><span data-stu-id="30ef2-147">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="30ef2-148">La subetiqueta **Research** Azure Information Protection, que aplica cifrado y permssions a cada archivo que viaja con el archivo cuando se mueve o se copia desde el sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-148">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="30ef2-149">La Directiva DLP de **investigación** , que usa la etiqueta de retención y las opciones de retención **altamente confidenciales** , que impiden que el archivo se comparta con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="30ef2-149">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="30ef2-150">El conjunto de permisos de sitio, que solo permiten el acceso a los miembros de los grupos de seguridad Research- **Members** y Research **-views** y a la administración por parte de los miembros del grupo de seguridad **Research-Admins** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-150">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="30ef2-151">Paso 5: migrar los datos de la investigación de SharePoint local</span><span class="sxs-lookup"><span data-stu-id="30ef2-151">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="30ef2-152">Los administradores de Contoso movieron todos los archivos de investigación local en el sitio local de SharePoint Server 2016 a las carpetas del nuevo sitio de **referencia** de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="30ef2-152">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="30ef2-153">Paso 6: formación para los usuarios</span><span class="sxs-lookup"><span data-stu-id="30ef2-153">Step 6: Trained their users</span></span> 

<span data-ttu-id="30ef2-154">El personal de seguridad de Contoso ha entrenado a los equipos de investigación en un curso obligatorio que les ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="30ef2-154">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="30ef2-155">Cómo obtener acceso al nuevo sitio de SharePoint Online de **referencia** y sus archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="30ef2-155">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="30ef2-156">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="30ef2-156">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="30ef2-157">Una demostración de cómo la Directiva DLP bloquea los archivos para que no se compartan de forma externa.</span><span class="sxs-lookup"><span data-stu-id="30ef2-157">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="30ef2-158">Cómo usar el cliente de Azure Information Protection para etiquetar archivos de referencia con la etiqueta secundaria **Research** .</span><span class="sxs-lookup"><span data-stu-id="30ef2-158">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="30ef2-159">Una demostración de cómo la subetiqueta **Research** protege un archivo incluso cuando se pierde del sitio.</span><span class="sxs-lookup"><span data-stu-id="30ef2-159">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="30ef2-160">El resultado final es un entorno seguro en el que los investigadores pueden colaborar en toda la organización en un entorno seguro.</span><span class="sxs-lookup"><span data-stu-id="30ef2-160">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="30ef2-161">Si se pierde del sitio de **investigación** un documento de investigación con la subetiqueta **Research** , este se cifra y es accesible sólo para los miembros de los grupos de seguridad **Research-Members** y **Research-Viewers** con credenciales válidas.</span><span class="sxs-lookup"><span data-stu-id="30ef2-161">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="30ef2-162">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="30ef2-162">Next step</span></span>

<span data-ttu-id="30ef2-163">[Implementar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="30ef2-163">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

