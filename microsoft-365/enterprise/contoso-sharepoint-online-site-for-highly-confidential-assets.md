---
title: Sitio de SharePoint para activos digitales altamente confidenciales de Contoso Corporation
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
description: 'Resumen: Cómo contoso implementó un sitio de SharePoint para datos altamente regulados para una colaboración más sencilla entre sus equipos de investigación.'
ms.openlocfilehash: 0a4bc2f685cf015611da62ebbed000218f37f31e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634257"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="4faae-103">Sitio de SharePoint para activos digitales altamente confidenciales de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="4faae-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

<span data-ttu-id="4faae-104">Los activos más valiosos de Contoso son su propiedad intelectual en forma de secretos comerciales, como técnicas de fabricación patentadas, así como especificaciones de diseño para productos que están en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4faae-104">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="4faae-105">Estos activos estaban en formato digital, que se almacenaban originalmente como archivos en un sitio de SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="4faae-105">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="4faae-106">Cuando contoso implementó Microsoft 365 Enterprise, quería realizar la transición de sus activos digitales locales a la nube para facilitar el acceso y aumentar la colaboración entre los equipos de investigación de París, Moscú, Nueva York, Beijing y Bangalore.</span><span class="sxs-lookup"><span data-stu-id="4faae-106">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="4faae-107">Sin embargo, debido a su carácter confidencial, el acceso a estos archivos debe ser:</span><span class="sxs-lookup"><span data-stu-id="4faae-107">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="4faae-108">Restringido al conjunto de personas a las que se les permite acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="4faae-108">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="4faae-109">Protegido con una directiva de prevención de pérdida de datos (DLP) para evitar que los usuarios los distribuyan fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="4faae-109">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="4faae-110">Cifrado y protegido con permisos para evitar que los usuarios no autorizados obtengan acceso a su contenido, incluso si se distribuyen fuera del sitio.</span><span class="sxs-lookup"><span data-stu-id="4faae-110">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="4faae-111">Los administradores de SharePoint y de seguridad en el Departamento de TI de Contoso decidieron usar un [sitio de SharePoint para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="4faae-111">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="4faae-112">Contoso usó estos pasos para crear y proteger sitios de grupo de SharePoint para sus equipos de investigación.</span><span class="sxs-lookup"><span data-stu-id="4faae-112">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="4faae-113">Paso 1: crear un sitio de grupo privado de SharePoint</span><span class="sxs-lookup"><span data-stu-id="4faae-113">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="4faae-114">Para proteger el acceso al sitio de SharePoint, contoso ha configurado las [directivas de acceso de SharePoint recomendadas](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4faae-114">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="4faae-115">Después, los administradores de Contoso IT recopilaron una lista de las cuentas de usuario de los investigadores de sus oficinas de París, Moscú, Nueva York, Beijing y Bangalore.</span><span class="sxs-lookup"><span data-stu-id="4faae-115">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="4faae-116">A continuación, un administrador de TI de Contoso ha creado un nuevo sitio de grupo privado denominado **Research** y ha agregado todas las cuentas de usuario para sus investigadores.</span><span class="sxs-lookup"><span data-stu-id="4faae-116">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="4faae-117">A continuación, se configuraron opciones de permisos adicionales para el sitio con el fin de evitar que los investigadores compartan el acceso al sitio y evitar que los investigadores soliciten acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="4faae-117">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="4faae-118">Paso 2: configurar el sitio para una directiva DLP restrictiva</span><span class="sxs-lookup"><span data-stu-id="4faae-118">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="4faae-119">En primer lugar, los administradores de Contoso aplicaron la etiqueta de retención **altamente confidencial** existente a la carpeta documentos del sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="4faae-119">First, Contoso admins applied the existing **Highly Confidential** retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="4faae-120">A continuación, creamos una nueva Directiva de DLP denominada **Research** que:</span><span class="sxs-lookup"><span data-stu-id="4faae-120">Next, they created a new DLP policy named **Research** that:</span></span>

- <span data-ttu-id="4faae-121">Usa la etiqueta de retención **muy confidencial** .</span><span class="sxs-lookup"><span data-stu-id="4faae-121">Uses the **Highly Confidential** retention label.</span></span> 
- <span data-ttu-id="4faae-122">Bloquea a los usuarios cuando intentan compartir un activo digital en el sitio de **investigación** fuera de contoso.</span><span class="sxs-lookup"><span data-stu-id="4faae-122">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="4faae-123">Para obtener información detallada sobre la configuración, vea [proteger archivos de SharePoint con etiquetas de retención y DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="4faae-123">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-3-created-a-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="4faae-124">Paso 3: se creó una subetiqueta de confidencialidad para el sitio</span><span class="sxs-lookup"><span data-stu-id="4faae-124">Step 3: Created a sensitivity sublabel for the site</span></span>

<span data-ttu-id="4faae-125">Los administradores de Contoso crearon una nueva subetiqueta de sensibilidad denominada **Research Teams** de la etiqueta **extremadamente confidencial** que:</span><span class="sxs-lookup"><span data-stu-id="4faae-125">Contoso admins created a new sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="4faae-126">Requiere cifrado.</span><span class="sxs-lookup"><span data-stu-id="4faae-126">Requires encryption.</span></span>
- <span data-ttu-id="4faae-127">Permite permisos de co-autoría para el grupo de **investigación** 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4faae-127">Allows Co-Author permissions for the **Research** Microsoft 365 group</span></span>
- <span data-ttu-id="4faae-128">Se aplica al grupo de **investigación** de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4faae-128">Applies to the **Research** Microsoft 365 group</span></span>

<span data-ttu-id="4faae-129">Esta es la configuración resultante del sitio de grupo de **investigación** para los activos extremadamente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4faae-129">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![La configuración resultante del sitio de grupo de investigación para los activos extremadamente confidenciales](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="4faae-131">Los archivos de las carpetas del sitio de **investigación** están protegidos por:</span><span class="sxs-lookup"><span data-stu-id="4faae-131">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="4faae-132">Los permisos del sitio, que solo permiten el acceso a los miembros del grupo de **investigación** 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4faae-132">The site permissions, which only allow access to members of the **Research** Microsoft 365 group.</span></span>
- <span data-ttu-id="4faae-133">La Directiva DLP de **investigación** , que usa la etiqueta de retención y la configuración de retención **extremadamente confidenciales** , que impiden que el archivo se comparta con usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="4faae-133">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="4faae-134">Subetiqueta de confidencialidad de los **equipos de investigación** , con cifrado y permisos que viajan con el archivo si se mueven o se copian desde el sitio de **investigación** .</span><span class="sxs-lookup"><span data-stu-id="4faae-134">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="4faae-135">A continuación, se muestra un ejemplo de un archivo almacenado en el sitio de **investigación** con la subetiqueta de confidencialidad de **Teams de investigación** asignada.</span><span class="sxs-lookup"><span data-stu-id="4faae-135">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![La configuración resultante del sitio de grupo de investigación para los activos extremadamente confidenciales](../media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-4-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="4faae-137">Paso 4: migrar los datos de la investigación de SharePoint local</span><span class="sxs-lookup"><span data-stu-id="4faae-137">Step 4: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="4faae-138">Los administradores de Contoso movieron todos los archivos de investigación local en el sitio local de SharePoint Server 2016 a las carpetas del nuevo sitio de SharePoint de **referencia** .</span><span class="sxs-lookup"><span data-stu-id="4faae-138">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-5-trained-their-researchers"></a><span data-ttu-id="4faae-139">Paso 5: formación de sus investigadores</span><span class="sxs-lookup"><span data-stu-id="4faae-139">Step 5: Trained their researchers</span></span>

<span data-ttu-id="4faae-140">El personal de seguridad de Contoso ha entrenado a los miembros del grupo de **investigación** Microsoft 365 en un curso obligatorio que les ha ejecutado:</span><span class="sxs-lookup"><span data-stu-id="4faae-140">Contoso security staff trained the members of the **Research** Microsoft 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="4faae-141">Cómo obtener acceso al nuevo sitio de **investigación** y sus archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="4faae-141">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="4faae-142">Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.</span><span class="sxs-lookup"><span data-stu-id="4faae-142">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="4faae-143">Una demostración de cómo la Directiva DLP de **investigación** bloquea los archivos para que no se compartan de forma externa.</span><span class="sxs-lookup"><span data-stu-id="4faae-143">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="4faae-144">Cómo etiquetar archivos con la subetiqueta de confidencialidad de los **equipos de investigación** .</span><span class="sxs-lookup"><span data-stu-id="4faae-144">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="4faae-145">Una demostración de cómo la subcarpeta **equipos de investigación** protege un archivo incluso cuando se pierde del sitio.</span><span class="sxs-lookup"><span data-stu-id="4faae-145">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="4faae-146">El resultado final es un entorno seguro en el que los investigadores pueden colaborar a través de Contoso en un entorno seguro en archivos que contienen información de referencia.</span><span class="sxs-lookup"><span data-stu-id="4faae-146">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="4faae-147">Si un documento de investigación de la subetiqueta **equipos de investigación** abandona el sitio de **investigación** , sólo se cifra y es accesible para los miembros del grupo de Microsoft 365 **Research** con credenciales de cuenta de usuario válidas.</span><span class="sxs-lookup"><span data-stu-id="4faae-147">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Microsoft 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="4faae-148">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="4faae-148">Next step</span></span>

<span data-ttu-id="4faae-149">[Implementar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="4faae-149">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="4faae-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="4faae-150">See also</span></span>

<span data-ttu-id="4faae-151">[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="4faae-151">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
