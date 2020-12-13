---
title: Cifrado de clave doble (DKE)
description: DKE permite proteger datos extremadamente confidenciales y mantener el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 9607b095ba073229edae43c1d2f0e893db07c634
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663095"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="f07b2-103">Cifrado de doble clave para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f07b2-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="f07b2-104">*Se aplica a: cifrado de doble clave para Microsoft 365, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="f07b2-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="f07b2-105">*Instrucciones para: [cliente de etiquetado Unificado de Azure Information Protection para Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="f07b2-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="f07b2-106">*Descripción del servicio para: [cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="f07b2-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="f07b2-107">El cifrado de doble clave (DKE) utiliza dos claves conjuntamente para obtener acceso al contenido protegido.</span><span class="sxs-lookup"><span data-stu-id="f07b2-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="f07b2-108">Microsoft almacena una clave en Microsoft Azure y mantiene la otra clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="f07b2-109">Se mantiene un control total de una de las claves mediante el servicio de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="f07b2-110">La protección se aplica mediante el cliente de etiquetado Unificado de Azure Information Protection a su contenido extremadamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="f07b2-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="f07b2-111">El cifrado de doble clave admite tanto la nube como las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="f07b2-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="f07b2-112">Estas implementaciones ayudan a garantizar que los datos cifrados permanezcan opacos dondequiera que almacene los datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="f07b2-113">Para obtener más información acerca de las claves predeterminadas de raíz de inquilino basadas en la nube, vea [Planning and Implementing Your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="f07b2-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="f07b2-114">Cuando su organización debe adoptar DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="f07b2-115">El cifrado de doble clave está destinado a los datos más confidenciales que están sujetos a los requisitos de protección más estrictos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="f07b2-116">DKE no está pensada para todos los datos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-116">DKE is not intended for all data.</span></span> <span data-ttu-id="f07b2-117">En general, utilizará el cifrado de doble clave para proteger solo una parte muy pequeña de los datos globales.</span><span class="sxs-lookup"><span data-stu-id="f07b2-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="f07b2-118">Debe llevar a cabo la diligencia debida para identificar los datos correctos que se incluirán con esta solución antes de implementarla.</span><span class="sxs-lookup"><span data-stu-id="f07b2-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="f07b2-119">En algunos casos, es posible que necesite limitar el ámbito y usar otras soluciones para la mayoría de los datos, como Microsoft Information Protection con claves administradas por Microsoft o BYOK.</span><span class="sxs-lookup"><span data-stu-id="f07b2-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="f07b2-120">Estas soluciones son suficientes para los documentos que no están sujetos a las protecciones mejoradas y a los requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="f07b2-121">Además, estas soluciones le permiten usar los servicios de Office 365 más eficaces; servicios que no se pueden usar con contenido cifrado de DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="f07b2-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-122">For example:</span></span>

- <span data-ttu-id="f07b2-123">Reglas de transporte que incluyen protección contra malware y correo no deseado que requieren visibilidad en los datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="f07b2-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="f07b2-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="f07b2-124">Microsoft Delve</span></span>
- <span data-ttu-id="f07b2-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f07b2-125">eDiscovery</span></span>
- <span data-ttu-id="f07b2-126">Búsqueda de contenido e indización</span><span class="sxs-lookup"><span data-stu-id="f07b2-126">Content search and indexing</span></span>
- <span data-ttu-id="f07b2-127">Office Web Apps, incluida la funcionalidad de co-autoría</span><span class="sxs-lookup"><span data-stu-id="f07b2-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="f07b2-128">Cualquier aplicación o servicio externo que no esté integrado con DKE a través del SDK de MIP no podrá realizar acciones en los datos cifrados.</span><span class="sxs-lookup"><span data-stu-id="f07b2-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="f07b2-129">El SDK de Microsoft Information Protection 1.7 + admite el cifrado de doble clave; las aplicaciones que se integran con nuestro SDK podrán conllevarle motivos sobre estos datos con los permisos e integraciones suficientes.</span><span class="sxs-lookup"><span data-stu-id="f07b2-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="f07b2-130">Recomendamos que las organizaciones usen las capacidades de Microsoft Information Protection (clasificación y etiquetado) para proteger la mayoría de sus datos confidenciales y solo usen DKE para sus datos de misión crítica.</span><span class="sxs-lookup"><span data-stu-id="f07b2-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="f07b2-131">El cifrado de doble clave es especialmente relevante para los datos extremadamente confidenciales en industrias altamente reguladas, como los servicios financieros y la asistencia sanitaria.</span><span class="sxs-lookup"><span data-stu-id="f07b2-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="f07b2-132">Si las organizaciones tienen alguno de los siguientes requisitos, puede usar DKE para ayudar a proteger el contenido:</span><span class="sxs-lookup"><span data-stu-id="f07b2-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="f07b2-133">Desea asegurarse de que *solo usted* puede descifrar el contenido protegido en todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="f07b2-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="f07b2-134">No desea que Microsoft tenga acceso a datos protegidos por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="f07b2-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="f07b2-135">Tiene requisitos normativos para mantener las claves dentro de un límite geográfico.</span><span class="sxs-lookup"><span data-stu-id="f07b2-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="f07b2-136">Todas las claves que se incluyen para el cifrado y descifrado de datos se mantienen en el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="f07b2-137">Requisitos de licencia y sistema para DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="f07b2-138">El **cifrado de doble clave para microsoft 365** incluye Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f07b2-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="f07b2-139">Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="f07b2-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="f07b2-140">Para obtener más información acerca de estas licencias, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="f07b2-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="f07b2-141">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-141">**Azure Information Protection**.</span></span> <span data-ttu-id="f07b2-142">DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="f07b2-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="f07b2-143">Las etiquetas de confidencialidad de DKE están disponibles para los usuarios finales a través de la cinta de confidencialidad en las aplicaciones de escritorio de Office.</span><span class="sxs-lookup"><span data-stu-id="f07b2-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="f07b2-144">Instale estos requisitos previos en cada equipo cliente donde quiera proteger y consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="f07b2-145">**Microsoft Office apps for Enterprise** versión \*. 12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.</span><span class="sxs-lookup"><span data-stu-id="f07b2-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="f07b2-146">**Azure Information Protection el cliente de etiquetado unificado** versiones 2.7.93.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f07b2-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="f07b2-147">Descargue e instale el cliente de etiquetado unificado desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="f07b2-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="f07b2-148">Entornos admitidos para almacenar y ver contenido protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="f07b2-149">**Aplicaciones compatibles**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-149">**Supported applications**.</span></span> <span data-ttu-id="f07b2-150">[Microsoft 365 apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients in Windows, incluidos Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f07b2-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="f07b2-151">**Soporte de contenido en línea**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-151">**Online content support**.</span></span> <span data-ttu-id="f07b2-152">Se admiten los documentos y archivos almacenados en línea tanto en Microsoft SharePoint como en OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="f07b2-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="f07b2-153">Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos cifrados y archivos en línea.</span><span class="sxs-lookup"><span data-stu-id="f07b2-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="f07b2-154">En su lugar, debe ver el contenido protegido con las aplicaciones de escritorio en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="f07b2-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="f07b2-155">Información general sobre la implementación de DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-155">Overview of deploying DKE</span></span>

<span data-ttu-id="f07b2-156">Seguiremos estos pasos generales para configurar DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="f07b2-157">Una vez que haya completado estos pasos, los usuarios finales podrán proteger los datos extremadamente confidenciales con el cifrado doble de claves.</span><span class="sxs-lookup"><span data-stu-id="f07b2-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="f07b2-158">Implemente el servicio DKE tal como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="f07b2-159">Cree una etiqueta con dos claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="f07b2-160">Navegue a Information Protection en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) y cree una nueva etiqueta con cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="f07b2-161">Consulte [restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="f07b2-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="f07b2-162">Use las etiquetas de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="f07b2-163">Proteja los datos seleccionando la etiqueta cifrada de doble clave en la cinta de confidencialidad de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f07b2-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="f07b2-164">Hay varias formas de realizar algunos de los pasos para implementar el cifrado doble de claves.</span><span class="sxs-lookup"><span data-stu-id="f07b2-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="f07b2-165">En este artículo se proporcionan instrucciones detalladas para que los administradores menos experimentados implementen correctamente el servicio.</span><span class="sxs-lookup"><span data-stu-id="f07b2-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="f07b2-166">Si le resulta cómodo hacerlo, puede elegir usar sus propios métodos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="f07b2-167">Implementar DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-167">Deploy DKE</span></span>

<span data-ttu-id="f07b2-168">Este artículo y el vídeo de implementación usan Azure como destino de implementación para el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="f07b2-169">Si va a realizar la implementación en otra ubicación, deberá proporcionar sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="f07b2-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="f07b2-170">Vea el [vídeo sobre la implementación de doble clave](https://youtu.be/vDWfHN_kygg) para ver una introducción paso a paso de los conceptos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="f07b2-171">El vídeo tarda unos 18 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="f07b2-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="f07b2-172">Deberá seguir estos pasos generales para configurar el cifrado de doble clave para su organización.</span><span class="sxs-lookup"><span data-stu-id="f07b2-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="f07b2-173">Instalar los requisitos previos de software para el servicio DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="f07b2-174">Clone el repositorio de GitHub con cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="f07b2-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="f07b2-175">Modificación de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f07b2-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="f07b2-176">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="f07b2-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="f07b2-177">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f07b2-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="f07b2-178">Implementar el servicio DKE y publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="f07b2-179">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="f07b2-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="f07b2-180">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="f07b2-181">Crear etiquetas de confidencialidad mediante DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="f07b2-182">Habilitar DKE en el cliente</span><span class="sxs-lookup"><span data-stu-id="f07b2-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="f07b2-183">Migrar archivos protegidos desde etiquetas HYOK a etiquetas DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="f07b2-184">Cuando haya terminado, puede cifrar documentos y archivos con DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="f07b2-185">Para obtener más información, consulte [aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="f07b2-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="f07b2-186">Instalar los requisitos previos de software para el servicio DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="f07b2-187">Instale estos requisitos previos en el equipo en el que desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="f07b2-188">**SDK .net Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="f07b2-189">Descargue e instale el SDK desde [download .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="f07b2-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="f07b2-190">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-190">**Visual Studio Code**.</span></span> <span data-ttu-id="f07b2-191">Descargue Visual Studio Code desde [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="f07b2-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="f07b2-192">Una vez instalado, ejecute Visual Studio Code y seleccione **Ver** \> **extensiones**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="f07b2-193">Instale estas extensiones.</span><span class="sxs-lookup"><span data-stu-id="f07b2-193">Install these extensions.</span></span>

- <span data-ttu-id="f07b2-194">C# para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f07b2-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="f07b2-195">Administrador de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="f07b2-195">NuGet Package Manager</span></span>

<span data-ttu-id="f07b2-196">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-196">**Git resources**.</span></span> <span data-ttu-id="f07b2-197">Descargue e instale uno de los siguientes elementos.</span><span class="sxs-lookup"><span data-stu-id="f07b2-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="f07b2-198">Git</span><span class="sxs-lookup"><span data-stu-id="f07b2-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="f07b2-199">Escritorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="f07b2-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="f07b2-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="f07b2-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="f07b2-201">**OpenSSL** Debe tener instalado [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) para [generar las claves de prueba](#generate-test-keys) después de implementar DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="f07b2-202">Asegúrese de que está invocando correctamente desde la ruta de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="f07b2-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="f07b2-203">Por ejemplo, consulte "agregar el directorio de instalación a la ruta de acceso" en [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para más detalles.</span><span class="sxs-lookup"><span data-stu-id="f07b2-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="f07b2-204">Clonar el repositorio de GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="f07b2-205">Microsoft proporciona los archivos de origen de DKE en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="f07b2-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="f07b2-206">Clonar el repositorio para compilar el proyecto de forma local para el uso de su organización.</span><span class="sxs-lookup"><span data-stu-id="f07b2-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="f07b2-207">El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="f07b2-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="f07b2-208">Las siguientes instrucciones están destinadas a usuarios no con experiencia de Git o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="f07b2-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="f07b2-209">En el explorador, vaya a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="f07b2-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="f07b2-210">Hacia el lado derecho de la pantalla, seleccione **código**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="f07b2-211">Es posible que la versión de la interfaz de usuario muestre un botón **clonar o descargar** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="f07b2-212">A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="f07b2-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="f07b2-213">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-213">For example:</span></span>

   ![Clone el repositorio del servicio de cifrado de doble clave desde GitHub](../media/dke-clone.png)

3. <span data-ttu-id="f07b2-215">En Visual Studio Code, seleccione **Ver** \> **paleta de comandos** y seleccione **git: clon**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="f07b2-216">Para ir a la opción de la lista, empiece a escribir `git: clone` para filtrar las entradas y, a continuación, selecciónela en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f07b2-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="f07b2-217">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-217">For example:</span></span>

   ![Opción de Visual Studio Code GIT: Clone](../media/dke-vscode-clone.png)

4. <span data-ttu-id="f07b2-219">En el cuadro de texto, pegue la dirección URL que copió desde git y seleccione **clonar desde GitHub**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="f07b2-220">En el cuadro de diálogo **Seleccionar carpeta** que aparece, busque y seleccione una ubicación para almacenar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="f07b2-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="f07b2-221">En el símbolo del sistema, seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="f07b2-222">El repositorio se abre en Visual Studio Code y muestra la rama git actual en la parte inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="f07b2-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="f07b2-223">La rama debe ser **maestra**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-223">The branch should be **master**.</span></span>

    <span data-ttu-id="f07b2-224">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-224">For example:</span></span>

   ![Rama de patrón de Visual Studio Code](../media/dke-vscode-master.png)

6. <span data-ttu-id="f07b2-226">Seleccione el **patrón** de palabras de la lista de ramas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f07b2-227">La selección de la rama maestra garantiza que tenga los archivos correctos para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f07b2-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="f07b2-228">Si no elige la rama correcta, se producirá un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="f07b2-229">Ahora tiene su repositorio de origen de DKE configurado de forma local.</span><span class="sxs-lookup"><span data-stu-id="f07b2-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="f07b2-230">A continuación, [modifique la configuración](#modify-application-settings) de la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="f07b2-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="f07b2-231">Modificación de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f07b2-231">Modify application settings</span></span>

<span data-ttu-id="f07b2-232">Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de aplicación:</span><span class="sxs-lookup"><span data-stu-id="f07b2-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="f07b2-233">Configuración de acceso a claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="f07b2-234">Configuración de inquilinos y claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="f07b2-235">Modifique la configuración de la aplicación en el appsettings.jsarchivo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="f07b2-236">Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="f07b2-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="f07b2-237">Por ejemplo, en Visual Studio Code, puede desplazarse hasta el archivo como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="f07b2-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Buscar el appsettings.jsen el archivo para DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="f07b2-239">Configuración de acceso a claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-239">Key access settings</span></span>

<span data-ttu-id="f07b2-240">Elija si desea usar el correo electrónico o la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="f07b2-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="f07b2-241">DKE solo admite uno de estos métodos de autenticación a la vez.</span><span class="sxs-lookup"><span data-stu-id="f07b2-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="f07b2-242">**Autorización de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-242">**Email authorization**.</span></span> <span data-ttu-id="f07b2-243">Permite a su organización autorizar el acceso a claves basadas solo en direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f07b2-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="f07b2-244">**Autorización de roles**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-244">**Role authorization**.</span></span> <span data-ttu-id="f07b2-245">Permite a su organización autorizar el acceso a las claves en función de los grupos de Active Directory y requiere que el servicio Web pueda consultar LDAP.</span><span class="sxs-lookup"><span data-stu-id="f07b2-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="f07b2-246">**Para establecer la configuración de acceso clave para DKE mediante autorización de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="f07b2-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="f07b2-247">Abra el **appsettings.jsen** archivo y busque la `AuthorizedEmailAddress` configuración.</span><span class="sxs-lookup"><span data-stu-id="f07b2-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="f07b2-248">Agregue las direcciones o direcciones de correo electrónico que quiera autorizar.</span><span class="sxs-lookup"><span data-stu-id="f07b2-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="f07b2-249">Separe varias direcciones de correo electrónico con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="f07b2-250">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="f07b2-251">Busque la `LDAPPath` configuración y quite el texto `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` comprendido entre las comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="f07b2-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="f07b2-252">Deje las comillas dobles en su posición.</span><span class="sxs-lookup"><span data-stu-id="f07b2-252">Leave the double quotes in place.</span></span> <span data-ttu-id="f07b2-253">Cuando haya terminado, la configuración debería ser similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="f07b2-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="f07b2-254">Busque la `AuthorizedRoles` configuración y elimine la línea completa.</span><span class="sxs-lookup"><span data-stu-id="f07b2-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="f07b2-255">Esta imagen muestra la **appsettings.jsen** un archivo con el formato correcto para la autorización de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f07b2-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![El appsettings.jsen archivo que muestra el método de autorización de correo electrónico](../media/dke-email-accesssetting.png)

<span data-ttu-id="f07b2-257">**Para establecer la configuración de acceso clave de DKE mediante la autorización de roles**</span><span class="sxs-lookup"><span data-stu-id="f07b2-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="f07b2-258">Abra el **appsettings.jsen** archivo y busque la `AuthorizedRoles` configuración.</span><span class="sxs-lookup"><span data-stu-id="f07b2-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="f07b2-259">Agregue los nombres de grupo de Active Directory que desea autorizar.</span><span class="sxs-lookup"><span data-stu-id="f07b2-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="f07b2-260">Separe varios nombres de grupo con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="f07b2-261">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="f07b2-262">Busque la `LDAPPath` opción y agregue el dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f07b2-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="f07b2-263">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="f07b2-264">Busque la `AuthorizedEmailAddress` configuración y elimine la línea completa.</span><span class="sxs-lookup"><span data-stu-id="f07b2-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="f07b2-265">Esta imagen muestra la **appsettings.jsen** un archivo con el formato correcto para la autorización de rol.</span><span class="sxs-lookup"><span data-stu-id="f07b2-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsen el archivo que muestra el método de autorización de roles](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="f07b2-267">Configuración de inquilinos y claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-267">Tenant and key settings</span></span>

<span data-ttu-id="f07b2-268">La configuración de clave y de inquilino de DKE se encuentra en el **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="f07b2-269">**Para establecer la configuración de inquilinos y claves para DKE**</span><span class="sxs-lookup"><span data-stu-id="f07b2-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="f07b2-270">Abra el **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="f07b2-271">Busque la `ValidIssuers` configuración y sustitúyala `<tenantid>` por el identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="f07b2-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="f07b2-272">Puede encontrar el identificador de inquilino en el portal de Azure y ver las [propiedades del espacio](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)empresarial.</span><span class="sxs-lookup"><span data-stu-id="f07b2-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="f07b2-273">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="f07b2-274">Busque el `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="f07b2-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="f07b2-275">Reemplace `<yourhostname>` por el nombre de host del equipo en el que se ejecutará el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="f07b2-276">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f07b2-277">El valor de `JwtAudience` debe coincidir *exactamente* con el nombre de su host.</span><span class="sxs-lookup"><span data-stu-id="f07b2-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="f07b2-278">Puede usar **localhost: 5001** durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="f07b2-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="f07b2-279">Sin embargo, cuando haya terminado la depuración, asegúrese de actualizar este valor al nombre de host del servidor.</span><span class="sxs-lookup"><span data-stu-id="f07b2-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="f07b2-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="f07b2-280">`TestKeys:Name`.</span></span> <span data-ttu-id="f07b2-281">Escriba un nombre para la clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-281">Enter a name for your key.</span></span> <span data-ttu-id="f07b2-282">Por ejemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="f07b2-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="f07b2-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="f07b2-283">`TestKeys:Id`.</span></span> <span data-ttu-id="f07b2-284">Cree un GUID y escríbalo como el `TestKeys:ID` valor.</span><span class="sxs-lookup"><span data-stu-id="f07b2-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="f07b2-285">Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="f07b2-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="f07b2-286">Puede usar un sitio como el [generador de GUID en línea](https://guidgenerator.com/) para generar un GUID de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="f07b2-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="f07b2-287">Esta imagen muestra el formato correcto para la configuración de inquilinos y claves de **appsettings.js**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="f07b2-288">`LDAPPath` está configurado para la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="f07b2-288">`LDAPPath` is configured for role authorization.</span></span>

![Muestra los valores correctos de las claves y los inquilinos para DKE en el appsettings.jsen el archivo.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="f07b2-290">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="f07b2-290">Generate test keys</span></span>

<span data-ttu-id="f07b2-291">Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="f07b2-292">Para generar claves:</span><span class="sxs-lookup"><span data-stu-id="f07b2-292">To generate keys:</span></span>

1. <span data-ttu-id="f07b2-293">En el menú Inicio de Windows, ejecute el símbolo del sistema de OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="f07b2-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="f07b2-294">Cambie a la carpeta en la que desea guardar las claves de prueba.</span><span class="sxs-lookup"><span data-stu-id="f07b2-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="f07b2-295">Los archivos que crea al completar los pasos de esta tarea se almacenan en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="f07b2-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="f07b2-296">Generar la nueva clave de prueba.</span><span class="sxs-lookup"><span data-stu-id="f07b2-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="f07b2-297">Generar la clave privada.</span><span class="sxs-lookup"><span data-stu-id="f07b2-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="f07b2-298">Generar la clave pública.</span><span class="sxs-lookup"><span data-stu-id="f07b2-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="f07b2-299">En un editor de texto, Abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="f07b2-300">Copie todo el contenido del archivo **pubkeyonly. pem** , excepto la primera y la última línea, en la `PublicPem` sección de la **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="f07b2-301">En un editor de texto, Abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="f07b2-302">Copie todo el contenido del archivo **privkeynopass. pem** , excepto la primera y la última línea, en la `PrivatePem` sección de la **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="f07b2-303">Quite todos los espacios en blanco y las nuevas líneas en las `PublicPem` `PrivatePem` secciones y.</span><span class="sxs-lookup"><span data-stu-id="f07b2-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f07b2-304">Cuando copie este contenido, no elimine ninguno de los datos del PEM.</span><span class="sxs-lookup"><span data-stu-id="f07b2-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="f07b2-305">En Visual Studio Code, vaya al archivo **Startup.CS** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="f07b2-306">Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="f07b2-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="f07b2-307">Busque las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="f07b2-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="f07b2-308">Reemplace estas líneas con el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="f07b2-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="f07b2-309">Los resultados finales deben ser similares a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="f07b2-309">The end results should look similar to the following.</span></span>

   ![archivo startup.cs para la versión preliminar pública](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="f07b2-311">Ahora está listo para [compilar el proyecto DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="f07b2-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="f07b2-312">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f07b2-312">Build the project</span></span>

<span data-ttu-id="f07b2-313">Use las siguientes instrucciones para crear el proyecto DKE de forma local:</span><span class="sxs-lookup"><span data-stu-id="f07b2-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="f07b2-314">En Visual Studio Code, en el repositorio del servicio DKE, seleccione **Ver** \> **paleta de comandos** y, a continuación, escriba **generar** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f07b2-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="f07b2-315">En la lista, elija **tareas: Ejecutar tarea de compilación**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="f07b2-316">Si no se encuentra ninguna tarea de compilación, seleccione **Configurar tarea de compilación** y cree una para .net Core de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="f07b2-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Configurar la tarea de compilación que falta para .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="f07b2-318">Elija **crear tasks.jsen a partir de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-318">Choose **Create tasks.json from template**.</span></span>

      ![Crear tasks.jsen archivo de plantilla para DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="f07b2-320">En la lista de tipos de plantilla, seleccione **.net Core**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-320">From the list of template types, select **.NET Core**.</span></span>

      ![Seleccione la plantilla correcta para DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="f07b2-322">En la sección generar, busque la ruta de acceso al archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="f07b2-323">Si no está ahí, agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="f07b2-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="f07b2-324">Vuelva a ejecutar la compilación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-324">Run the build again.</span></span>

3. <span data-ttu-id="f07b2-325">Compruebe que no haya errores rojos en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="f07b2-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="f07b2-326">Si hay errores rojos, compruebe el resultado de la consola.</span><span class="sxs-lookup"><span data-stu-id="f07b2-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="f07b2-327">Asegúrese de que ha completado todos los pasos anteriores correctamente y de que las versiones de compilación correctas están presentes.</span><span class="sxs-lookup"><span data-stu-id="f07b2-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="f07b2-328">Seleccione **Ejecutar** \> la **depuración de inicio** para depurar el proceso.</span><span class="sxs-lookup"><span data-stu-id="f07b2-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="f07b2-329">Si se le pide que seleccione un entorno, seleccione **.net Core**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="f07b2-330">El depurador de .NET Core se inicia normalmente en `https://localhost:5001` .</span><span class="sxs-lookup"><span data-stu-id="f07b2-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="f07b2-331">Para ver la clave de prueba, vaya a `https://localhost:5001` y anexe una barra diagonal (/) y el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="f07b2-332">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="f07b2-333">La clave debe mostrarse en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="f07b2-333">The key should display in JSON format.</span></span>

<span data-ttu-id="f07b2-334">La configuración se ha completado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-334">Your setup is now complete.</span></span> <span data-ttu-id="f07b2-335">Antes de publicar el almacén de claves, en appsettings.jsen la configuración de JwtAudience, asegúrese de que el valor para hostname coincide exactamente con el nombre de host del servicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="f07b2-336">Puede que lo haya cambiado a localhost para solucionar los problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="f07b2-337">Implementar el servicio DKE y publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="f07b2-338">Para las implementaciones de producción, implemente el servicio en una nube de terceros o [publíquelo en un sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span><span class="sxs-lookup"><span data-stu-id="f07b2-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="f07b2-339">Puede que prefiera otros métodos para implementar las claves.</span><span class="sxs-lookup"><span data-stu-id="f07b2-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="f07b2-340">Seleccione el método que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="f07b2-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="f07b2-341">Para las implementaciones piloto, puede implementar en Azure y comenzar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="f07b2-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="f07b2-342">**Para crear una instancia de la aplicación Web de Azure para hospedar la implementación de DKE**</span><span class="sxs-lookup"><span data-stu-id="f07b2-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="f07b2-343">Para publicar el almacén de claves, debe crear una instancia de Azure App Service para hospedar la implementación de DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="f07b2-344">A continuación, publicará las claves generadas en Azure.</span><span class="sxs-lookup"><span data-stu-id="f07b2-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="f07b2-345">En el explorador, inicie sesión en el [portal de Microsoft Azure](https://ms.portal.azure.com)y vaya a **App Services**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="f07b2-346">Seleccione su suscripción y grupo de recursos y defina los detalles de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f07b2-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="f07b2-347">Escriba el nombre de host del equipo en el que desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="f07b2-348">Asegúrese de que es el mismo nombre que el definido para la configuración JwtAudience en el [**appsettings.jsen**](#tenant-and-key-settings) el archivo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="f07b2-349">El valor que se proporciona para el nombre también es WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="f07b2-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="f07b2-350">Para **publicar**, seleccionar **código** y, para **pila en tiempo de ejecución**, seleccione **.net Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="f07b2-351">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-351">For example:</span></span>

   ![Agregar el servicio de aplicaciones](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="f07b2-353">En la parte inferior de la página, seleccione **revisar + crear** y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="f07b2-354">Realice una de las siguientes acciones para publicar las claves generadas:</span><span class="sxs-lookup"><span data-stu-id="f07b2-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="f07b2-355">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="f07b2-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="f07b2-356">Publicar mediante FTP</span><span class="sxs-lookup"><span data-stu-id="f07b2-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="f07b2-357">Publicar a través de Visual Studio 2019 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f07b2-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="f07b2-358">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="f07b2-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="f07b2-359">Vaya a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="f07b2-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="f07b2-360">Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="f07b2-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="f07b2-361">En el código base del almacén de claves, vaya a la carpeta **Customer-Key-store\src\customer-Key-Store** y compruebe que esta carpeta contiene el archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="f07b2-362">Ejecutar: **publicación dotnet**</span><span class="sxs-lookup"><span data-stu-id="f07b2-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="f07b2-363">La ventana resultados muestra el directorio en el que se ha implementado la publicación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="f07b2-364">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="f07b2-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="f07b2-365">Enviar todos los archivos del directorio de publicación a un archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="f07b2-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="f07b2-366">Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="f07b2-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="f07b2-367">Arrastre y coloque el archivo. zip que ha creado en el sitio de ZipDeployUI que ha abierto anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f07b2-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="f07b2-368">Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="f07b2-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="f07b2-369">DKE está implementado y puede ir a las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="f07b2-370">Siga [validando la implementación](#validate-your-deployment) a continuación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="f07b2-371">Publicar mediante FTP</span><span class="sxs-lookup"><span data-stu-id="f07b2-371">Publish via FTP</span></span>

1. <span data-ttu-id="f07b2-372">Conéctese al App Service que creó [anteriormente](#deploy-the-dke-service-and-publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="f07b2-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="f07b2-373">En el explorador, vaya a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **manual de implementación** de  >  **FTP**  >  .</span><span class="sxs-lookup"><span data-stu-id="f07b2-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="f07b2-374">Copie las cadenas de conexión que se muestran en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="f07b2-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="f07b2-375">Usaremos estas cadenas para conectar con el servicio de la aplicación web y cargar archivos a través de FTP.</span><span class="sxs-lookup"><span data-stu-id="f07b2-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="f07b2-376">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-376">For example:</span></span>

   ![Copiar cadenas de conexión del panel FTP](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="f07b2-378">En el código base para el almacenamiento de claves, vaya al **directorio Customer-Key-store\src\customer-Key-Store**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="f07b2-379">Compruebe que este directorio contiene el archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="f07b2-380">Ejecutar: **publicación dotnet**</span><span class="sxs-lookup"><span data-stu-id="f07b2-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="f07b2-381">El resultado contiene el directorio en el que se ha implementado la publicación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="f07b2-382">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="f07b2-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="f07b2-383">Enviar todos los archivos del directorio de publicación a un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="f07b2-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="f07b2-384">Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="f07b2-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="f07b2-385">Desde el cliente FTP, use la información de conexión que copió para conectarse a su servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f07b2-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="f07b2-386">Cargue el archivo. zip que creó en el paso anterior en el directorio raíz de la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="f07b2-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="f07b2-387">DKE está implementado y puede desplazarse a las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="f07b2-388">A continuación, [valide la implementación](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="f07b2-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="f07b2-389">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="f07b2-389">Validate your deployment</span></span>

<span data-ttu-id="f07b2-390">Después de implementar DKE con uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="f07b2-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="f07b2-391">Realizar</span><span class="sxs-lookup"><span data-stu-id="f07b2-391">Run:</span></span>

<span data-ttu-id="f07b2-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span><span class="sxs-lookup"><span data-stu-id="f07b2-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="f07b2-393">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-393">For example:</span></span>

<span data-ttu-id="f07b2-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="f07b2-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="f07b2-395">Asegúrese de que no aparecen errores en el resultado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="f07b2-396">Cuando esté listo, [Registre el almacén de claves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="f07b2-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="f07b2-397">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="f07b2-397">Register your key store</span></span>

<span data-ttu-id="f07b2-398">Los siguientes pasos le permiten registrar el servicio de DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="f07b2-399">El registro del servicio DKE es el último paso en la implementación de DKE para poder empezar a crear etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="f07b2-400">Para registrar el servicio DKE:</span><span class="sxs-lookup"><span data-stu-id="f07b2-400">To register the DKE service:</span></span>

1. <span data-ttu-id="f07b2-401">En el explorador, abra el [portal de Microsoft Azure](https://ms.portal.azure.com/)y vaya a **todos los** registros de la aplicación de \> **identidad** de servicios \> .</span><span class="sxs-lookup"><span data-stu-id="f07b2-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="f07b2-402">Seleccione **nuevo registro** y escriba un nombre significativo.</span><span class="sxs-lookup"><span data-stu-id="f07b2-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="f07b2-403">Seleccione un tipo de cuenta en las opciones que se muestran.</span><span class="sxs-lookup"><span data-stu-id="f07b2-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="f07b2-404">Si está usando Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com**, seleccione **cuentas solo en este directorio de organización (solo para el inquilino único de Microsoft).**</span><span class="sxs-lookup"><span data-stu-id="f07b2-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="f07b2-405">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-405">For example:</span></span>

   ![Nuevo registro de la aplicación](../media/dke-app-registration.png)

4. <span data-ttu-id="f07b2-407">En la parte inferior de la página, seleccione **registrar** para crear el nuevo registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="f07b2-408">En el registro de la nueva aplicación, en el panel izquierdo, en **administrar**, seleccione **autenticación**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="f07b2-409">Seleccione **Agregar una plataforma**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="f07b2-410">En el menú emergente **configurar plataformas** , seleccione **Web**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="f07b2-411">En **URI de redireccionamiento**, escriba el URI del servicio de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="f07b2-412">Escriba la dirección URL del servicio de aplicaciones, incluidos el nombre de host y el dominio.</span><span class="sxs-lookup"><span data-stu-id="f07b2-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="f07b2-413">Por ejemplo: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="f07b2-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="f07b2-414">La dirección URL que especifique debe coincidir con el nombre de host en el que está implementado el servicio de DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="f07b2-415">Si está probando localmente con Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="f07b2-416">En todos los casos, el esquema debe ser **https**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="f07b2-417">Asegúrese de que el nombre de host coincida exactamente con el nombre de host del servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f07b2-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="f07b2-418">Puede que lo haya cambiado a `localhost` para solucionar los problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="f07b2-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="f07b2-419">En **appsettings.jsactivado**, este valor es el nombre de host que se establece para `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="f07b2-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="f07b2-420">En **concesión implícita**, active la casilla de verificación **tokens de identificador** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="f07b2-421">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f07b2-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="f07b2-422">En el panel izquierdo, seleccione **exponer una API** y, a continuación, junto a URI de identificador de aplicación, seleccione **establecer**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="f07b2-423">Aún en la página **exponer una API** , en el área **ámbitos definidos por esta API** , seleccione **Agregar un ámbito**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="f07b2-424">En el nuevo ámbito:</span><span class="sxs-lookup"><span data-stu-id="f07b2-424">In the new scope:</span></span>

    1. <span data-ttu-id="f07b2-425">Defina el nombre del ámbito como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="f07b2-426">Seleccione a los administradores y usuarios que pueden conceder consentimiento.</span><span class="sxs-lookup"><span data-stu-id="f07b2-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="f07b2-427">Defina los valores restantes necesarios.</span><span class="sxs-lookup"><span data-stu-id="f07b2-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="f07b2-428">Seleccione **Agregar ámbito**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="f07b2-429">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f07b2-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="f07b2-430">Aún en la página **exponer una API** , en el área **aplicaciones cliente autorizadas** , seleccione **Agregar una aplicación cliente**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="f07b2-431">En la nueva aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="f07b2-431">In the new client application:</span></span>

    1. <span data-ttu-id="f07b2-432">Defina el identificador de cliente como **d3590ed6-52b3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="f07b2-433">Este valor es el identificador del cliente de Microsoft Office y permite a Office obtener un token de acceso para su almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="f07b2-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="f07b2-434">En **ámbitos autorizados**, seleccione el ámbito de la **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="f07b2-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="f07b2-435">Seleccione **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="f07b2-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="f07b2-436">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f07b2-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="f07b2-437">El servicio de DKE se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-437">Your DKE service is now registered.</span></span> <span data-ttu-id="f07b2-438">Para continuar, [cree etiquetas con DKE](#create-sensitivity-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="f07b2-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="f07b2-439">Crear etiquetas de confidencialidad mediante DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="f07b2-440">En el centro de cumplimiento de Microsoft 365, cree una nueva etiqueta de confidencialidad y aplique el cifrado como lo haría en otro caso.</span><span class="sxs-lookup"><span data-stu-id="f07b2-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="f07b2-441">Seleccione **usar cifrado doble de clave** y escriba la dirección URL del punto de conexión para la clave.</span><span class="sxs-lookup"><span data-stu-id="f07b2-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="f07b2-442">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f07b2-442">For example:</span></span>

![Seleccione usar el cifrado de doble clave en el centro de cumplimiento de Microsoft 365](../media/dke-use-dke.png)

<span data-ttu-id="f07b2-444">Las etiquetas de DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de las aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="f07b2-445">Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f07b2-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="f07b2-446">Habilitar DKE en el cliente</span><span class="sxs-lookup"><span data-stu-id="f07b2-446">Enable DKE in your client</span></span>

<span data-ttu-id="f07b2-447">Si es Office Insider, DKE está habilitado para usted.</span><span class="sxs-lookup"><span data-stu-id="f07b2-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="f07b2-448">De lo contrario, habilite DKE para el cliente agregando las siguientes claves del registro:</span><span class="sxs-lookup"><span data-stu-id="f07b2-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="f07b2-449">Migrar archivos protegidos desde etiquetas HYOK a etiquetas DKE</span><span class="sxs-lookup"><span data-stu-id="f07b2-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="f07b2-450">Si quiere, una vez que haya finalizado la configuración de DKE, puede migrar el contenido que ha protegido mediante etiquetas HYOK a etiquetas de DKE.</span><span class="sxs-lookup"><span data-stu-id="f07b2-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="f07b2-451">Para realizar la migración, debe usar el analizador de AIP.</span><span class="sxs-lookup"><span data-stu-id="f07b2-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="f07b2-452">Para empezar a usar el escáner, vea [¿Qué es el escáner de etiquetado Unificado de Azure Information Protection?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span><span class="sxs-lookup"><span data-stu-id="f07b2-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="f07b2-453">Si no migra contenido, el contenido protegido HYOK no se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="f07b2-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
