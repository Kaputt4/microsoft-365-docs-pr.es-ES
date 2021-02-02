---
title: Cifrado de clave doble (DKE)
description: DKE le permite proteger datos altamente confidenciales a la vez que mantiene el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066863"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="e3105-103">Cifrado de doble clave para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3105-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="e3105-104">*Se aplica a: Cifrado de doble clave para Microsoft 365, Cumplimiento de [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compliance-management) [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="e3105-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="e3105-105">*Instrucciones para: Cliente de etiquetado unificado de [Azure Information Protection para Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="e3105-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="e3105-106">*Descripción del servicio para: [Cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="e3105-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="e3105-107">El cifrado de doble clave (DKE) usa dos claves juntas para obtener acceso al contenido protegido.</span><span class="sxs-lookup"><span data-stu-id="e3105-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="e3105-108">Microsoft almacena una clave en Microsoft Azure y usted mantiene la otra clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="e3105-109">Mantiene el control total de una de las claves mediante el servicio cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="e3105-110">Puede aplicar protección mediante el cliente de etiquetado unificado de Azure Information Protection a su contenido altamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="e3105-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="e3105-111">El cifrado de doble clave admite implementaciones locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="e3105-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="e3105-112">Estas implementaciones ayudan a garantizar que los datos cifrados permanecen opacos donde se almacenan los datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="e3105-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="e3105-113">Para obtener más información acerca de las claves raíz de inquilino predeterminadas basadas en la nube, consulte Planeación e implementación de la clave de inquilino [de Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)</span><span class="sxs-lookup"><span data-stu-id="e3105-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="e3105-114">Cuándo debe adoptar su organización DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="e3105-115">El cifrado de doble clave está pensado para los datos más confidenciales que están sujetos a los requisitos de protección más estrictos.</span><span class="sxs-lookup"><span data-stu-id="e3105-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="e3105-116">DKE no está pensado para todos los datos.</span><span class="sxs-lookup"><span data-stu-id="e3105-116">DKE is not intended for all data.</span></span> <span data-ttu-id="e3105-117">En general, va a usar cifrado de doble clave para proteger solo una pequeña parte de los datos generales.</span><span class="sxs-lookup"><span data-stu-id="e3105-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="e3105-118">Debe realizar la debida diligencia a la hora de identificar los datos adecuados que se deben cubrir con esta solución antes de implementar.</span><span class="sxs-lookup"><span data-stu-id="e3105-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="e3105-119">En algunos casos, es posible que deba restringir el ámbito y usar otras soluciones para la mayoría de los datos, como Microsoft Information Protection con claves administradas por Microsoft o BYOK.</span><span class="sxs-lookup"><span data-stu-id="e3105-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="e3105-120">Estas soluciones son suficientes para documentos que no están sujetos a protecciones mejoradas y requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="e3105-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="e3105-121">Además, estas soluciones le permiten usar los servicios más eficaces de Office 365; que no puede usar con contenido cifrado DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="e3105-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-122">For example:</span></span>

- <span data-ttu-id="e3105-123">Reglas de transporte como antimalware y correo no deseado que requieren visibilidad de los datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="e3105-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="e3105-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="e3105-124">Microsoft Delve</span></span>
- <span data-ttu-id="e3105-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e3105-125">eDiscovery</span></span>
- <span data-ttu-id="e3105-126">Búsqueda e indización de contenido</span><span class="sxs-lookup"><span data-stu-id="e3105-126">Content search and indexing</span></span>
- <span data-ttu-id="e3105-127">Office Web Apps, incluida la funcionalidad de coautoría</span><span class="sxs-lookup"><span data-stu-id="e3105-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="e3105-128">Las aplicaciones o servicios externos que no están integrados con DKE a través del SDK de MIP no podrán realizar acciones en los datos cifrados.</span><span class="sxs-lookup"><span data-stu-id="e3105-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="e3105-129">Microsoft Information Protection SDK 1.7+ admite el cifrado de doble clave; las aplicaciones que se integran con nuestro SDK podrán realizar una razón sobre estos datos con permisos e integraciones suficientes en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e3105-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="e3105-130">Se recomienda que las organizaciones usen las capacidades de Protección de la información de Microsoft (clasificación y etiquetado) para proteger la mayoría de sus datos confidenciales y usar solo DKE para sus datos fundamentales.</span><span class="sxs-lookup"><span data-stu-id="e3105-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="e3105-131">El cifrado de doble clave es relevante para datos confidenciales en sectores altamente regulados, como servicios financieros y sanidad.</span><span class="sxs-lookup"><span data-stu-id="e3105-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="e3105-132">Si su organización tiene cualquiera de los siguientes requisitos, puede usar DKE para ayudar a proteger su contenido:</span><span class="sxs-lookup"><span data-stu-id="e3105-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="e3105-133">Desea asegurarse de que *solo usted pueda* descifrar el contenido protegido, en todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="e3105-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="e3105-134">No quiere que Microsoft tenga acceso a datos protegidos por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="e3105-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="e3105-135">Tiene requisitos normativos para contener claves dentro de un límite geográfico.</span><span class="sxs-lookup"><span data-stu-id="e3105-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="e3105-136">Todas las claves que conserva para el cifrado y descifrado de datos se mantienen en el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="e3105-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="e3105-137">Requisitos de sistema y licencias para DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="e3105-138">**Cifrado de doble clave para Microsoft 365** viene con Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e3105-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="e3105-139">Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba.](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="e3105-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="e3105-140">Para obtener más información acerca de estas licencias, vea la guía de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para la seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e3105-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="e3105-141">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="e3105-141">**Azure Information Protection**.</span></span> <span data-ttu-id="e3105-142">DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="e3105-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="e3105-143">Las etiquetas de confidencialidad DKE están disponibles para los usuarios finales a través de la cinta de opciones de confidencialidad en aplicaciones de escritorio de Office.</span><span class="sxs-lookup"><span data-stu-id="e3105-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="e3105-144">Instale estos requisitos previos en cada equipo cliente donde desee proteger y consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="e3105-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="e3105-145">**Microsoft Office Aplicaciones para** empresas versión \*.12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.</span><span class="sxs-lookup"><span data-stu-id="e3105-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="e3105-146">**Cliente de etiquetado unificado de Azure Information Protection** versión 2.7.93.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e3105-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="e3105-147">Descargue e instale el cliente de etiquetado unificado desde el Centro [de descarga de Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="e3105-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="e3105-148">Entornos admitidos para almacenar y ver contenido protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="e3105-149">**Aplicaciones admitidas.**</span><span class="sxs-lookup"><span data-stu-id="e3105-149">**Supported applications**.</span></span> <span data-ttu-id="e3105-150">[Aplicaciones de Microsoft 365 para clientes empresariales](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) en Windows, incluidos Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e3105-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="e3105-151">**Compatibilidad con contenido en línea.**</span><span class="sxs-lookup"><span data-stu-id="e3105-151">**Online content support**.</span></span> <span data-ttu-id="e3105-152">Se admiten documentos y archivos almacenados en línea en Microsoft SharePoint y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="e3105-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="e3105-153">Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos y archivos cifrados en línea.</span><span class="sxs-lookup"><span data-stu-id="e3105-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="e3105-154">En su lugar, debes ver el contenido protegido mediante las aplicaciones de escritorio del equipo local.</span><span class="sxs-lookup"><span data-stu-id="e3105-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="e3105-155">Información general sobre la implementación de DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-155">Overview of deploying DKE</span></span>

<span data-ttu-id="e3105-156">Siga estos pasos generales para configurar DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="e3105-157">Una vez que haya completado estos pasos, los usuarios finales podrán proteger los datos altamente confidenciales con cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-157">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="e3105-158">Implemente el servicio DKE como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="e3105-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="e3105-159">Cree una etiqueta con cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="e3105-160">Vaya a Protección de la información en el Centro [de cumplimiento de Microsoft 365](https://compliance.microsoft.com) y cree una nueva etiqueta con cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="e3105-161">Vea [Restringir el acceso al contenido mediante etiquetas de confidencialidad para aplicar el cifrado.](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="e3105-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="e3105-162">Use etiquetas de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="e3105-163">Proteja los datos seleccionando la etiqueta Cifrado de doble clave en la cinta de opciones de confidencialidad Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="e3105-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="e3105-164">Hay varias maneras de completar algunos de los pasos para implementar el cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="e3105-165">En este artículo se proporcionan instrucciones detalladas para que los administradores menos experimentados implemente correctamente el servicio.</span><span class="sxs-lookup"><span data-stu-id="e3105-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="e3105-166">Si se siente cómodo al hacerlo, puede elegir usar sus propios métodos.</span><span class="sxs-lookup"><span data-stu-id="e3105-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="e3105-167">Implementar DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-167">Deploy DKE</span></span>

<span data-ttu-id="e3105-168">Este artículo y el vídeo de implementación usan Azure como destino de implementación para el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="e3105-169">Si está implementando en otra ubicación, deberá proporcionar sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="e3105-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="e3105-170">Vea el [vídeo de implementación de cifrado de doble](https://youtu.be/vDWfHN_kygg) clave para ver una introducción paso a paso de los conceptos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e3105-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="e3105-171">El vídeo tarda unos 18 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="e3105-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="e3105-172">Siga estos pasos generales para configurar el cifrado de doble clave para su organización.</span><span class="sxs-lookup"><span data-stu-id="e3105-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="e3105-173">Instalación de requisitos previos de software para el servicio DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="e3105-174">Clonar el repositorio de GitHub de cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="e3105-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="e3105-175">Modificar la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e3105-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="e3105-176">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="e3105-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="e3105-177">Compilar el proyecto</span><span class="sxs-lookup"><span data-stu-id="e3105-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="e3105-178">Implementar el servicio DKE y publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="e3105-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="e3105-179">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="e3105-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="e3105-180">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="e3105-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="e3105-181">Crear etiquetas de confidencialidad con DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="e3105-182">Habilitar DKE en el cliente</span><span class="sxs-lookup"><span data-stu-id="e3105-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="e3105-183">Migrar archivos protegidos de etiquetas HYOK a etiquetas DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="e3105-184">Cuando haya terminado, puede cifrar documentos y archivos mediante DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="e3105-185">Para obtener información, vea [Aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office.](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)</span><span class="sxs-lookup"><span data-stu-id="e3105-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="e3105-186">Instalación de requisitos previos de software para el servicio DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="e3105-187">Instale estos requisitos previos en el equipo donde desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="e3105-188">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="e3105-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="e3105-189">Descargue e instale el SDK desde [Descargar .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="e3105-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="e3105-190">**Visual Studio código.**</span><span class="sxs-lookup"><span data-stu-id="e3105-190">**Visual Studio Code**.</span></span> <span data-ttu-id="e3105-191">Descargar Visual Studio código de [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="e3105-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="e3105-192">Una vez instalado, ejecute Visual Studio  código y seleccione \> **Ver extensiones**.</span><span class="sxs-lookup"><span data-stu-id="e3105-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="e3105-193">Instale estas extensiones.</span><span class="sxs-lookup"><span data-stu-id="e3105-193">Install these extensions.</span></span>

- <span data-ttu-id="e3105-194">C# para Visual Studio código</span><span class="sxs-lookup"><span data-stu-id="e3105-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="e3105-195">NuGet Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="e3105-195">NuGet Package Manager</span></span>

<span data-ttu-id="e3105-196">**Recursos de Git**.</span><span class="sxs-lookup"><span data-stu-id="e3105-196">**Git resources**.</span></span> <span data-ttu-id="e3105-197">Descargue e instale una de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="e3105-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="e3105-198">Git</span><span class="sxs-lookup"><span data-stu-id="e3105-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="e3105-199">Escritorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="e3105-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="e3105-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="e3105-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="e3105-201">**OpenSSL** Debe tener [OpenSSL instalado](https://slproweb.com/products/Win32OpenSSL.html) para generar [claves de prueba](#generate-test-keys) después de implementar DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="e3105-202">Asegúrese de invocarlo correctamente desde la ruta de variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="e3105-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="e3105-203">Por ejemplo, consulte "Agregar el directorio de instalación a PATH" para [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e3105-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="e3105-204">Clonar el repositorio de GitHub de DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="e3105-205">Microsoft proporciona los archivos de origen DKE en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="e3105-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="e3105-206">Clone el repositorio para compilar el proyecto localmente para el uso de su organización.</span><span class="sxs-lookup"><span data-stu-id="e3105-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="e3105-207">El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="e3105-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="e3105-208">Las siguientes instrucciones están pensadas para usuarios de git o Visual Studio código no experimentados:</span><span class="sxs-lookup"><span data-stu-id="e3105-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="e3105-209">En el explorador, vaya a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="e3105-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="e3105-210">Hacia el lado derecho de la pantalla, seleccione **Código**.</span><span class="sxs-lookup"><span data-stu-id="e3105-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="e3105-211">Es posible que la versión de la interfaz de usuario muestre un **botón Clonar o** descargar.</span><span class="sxs-lookup"><span data-stu-id="e3105-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="e3105-212">A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="e3105-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="e3105-213">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-213">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3105-214">![Clonar el repositorio del servicio de cifrado de doble clave desde GitHub](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="e3105-214">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="e3105-215">En Visual Studio, seleccione **Ver** paleta \> **de** comandos y **seleccione Git: Clonar**.</span><span class="sxs-lookup"><span data-stu-id="e3105-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="e3105-216">Para ir a la opción de la lista, empiece a escribir para filtrar las entradas y, a continuación, `git: clone` selecciónelo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e3105-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="e3105-217">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-217">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3105-218">![Visual Studio de código GIT:Clone](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="e3105-218">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="e3105-219">En el cuadro de texto, pegue la dirección URL que copió de Git y seleccione **Clonar desde GitHub**.</span><span class="sxs-lookup"><span data-stu-id="e3105-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="e3105-220">En el **cuadro de diálogo Seleccionar** carpeta que aparece, busque y seleccione una ubicación para almacenar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="e3105-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="e3105-221">En el símbolo del sistema, seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e3105-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="e3105-222">El repositorio se abre en Visual Studio código y muestra la rama de Git actual en la parte inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="e3105-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="e3105-223">Por ejemplo, la rama debe ser **principal.**</span><span class="sxs-lookup"><span data-stu-id="e3105-223">For example,  The branch should be **main**.</span></span> <span data-ttu-id="e3105-224">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-224">For example:</span></span>

   ![Captura de pantalla del repositorio DKE en Visual Studio código que muestra la rama principal](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="e3105-226">Si no estás en la rama principal, tendrás que seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="e3105-226">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="e3105-227">En Visual Studio código, seleccione la rama y elija **principal** en la lista de sucursales que se muestra.</span><span class="sxs-lookup"><span data-stu-id="e3105-227">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e3105-228">La selección de la rama principal garantiza que tiene los archivos correctos para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e3105-228">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="e3105-229">Si no elige la rama correcta, se producirá un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="e3105-229">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="e3105-230">Ahora tiene el repositorio de origen de DKE configurado localmente.</span><span class="sxs-lookup"><span data-stu-id="e3105-230">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="e3105-231">A [continuación, modifique la configuración de](#modify-application-settings) la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="e3105-231">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="e3105-232">Modificar la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e3105-232">Modify application settings</span></span>

<span data-ttu-id="e3105-233">Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e3105-233">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="e3105-234">Configuración de acceso de teclas</span><span class="sxs-lookup"><span data-stu-id="e3105-234">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="e3105-235">Configuración de inquilino y clave</span><span class="sxs-lookup"><span data-stu-id="e3105-235">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="e3105-236">La configuración de la aplicación se modifica en el appsettings.jsdel archivo.</span><span class="sxs-lookup"><span data-stu-id="e3105-236">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="e3105-237">Este archivo se encuentra en el repositorio DoubleKeyEncryptionService clonado localmente en DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="e3105-237">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="e3105-238">Por ejemplo, en Visual Studio código, puede examinar el archivo como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="e3105-238">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Ubicar el archivo appsettings.jsarchivo de DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="e3105-240">Configuración de acceso de teclas</span><span class="sxs-lookup"><span data-stu-id="e3105-240">Key access settings</span></span>

<span data-ttu-id="e3105-241">Elija si desea usar la autorización de correo electrónico o rol.</span><span class="sxs-lookup"><span data-stu-id="e3105-241">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="e3105-242">DKE solo admite uno de estos métodos de autenticación a la vez.</span><span class="sxs-lookup"><span data-stu-id="e3105-242">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="e3105-243">**Autorización de correo electrónico.**</span><span class="sxs-lookup"><span data-stu-id="e3105-243">**Email authorization**.</span></span> <span data-ttu-id="e3105-244">Permite que su organización autorice el acceso a las claves solo en función de las direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e3105-244">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="e3105-245">**Autorización de roles.**</span><span class="sxs-lookup"><span data-stu-id="e3105-245">**Role authorization**.</span></span> <span data-ttu-id="e3105-246">Permite que su organización autorice el acceso a claves basadas en grupos de Active Directory y requiere que el servicio web pueda consultar LDAP.</span><span class="sxs-lookup"><span data-stu-id="e3105-246">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="e3105-247">**Para establecer la configuración de acceso clave para DKE mediante la autorización de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="e3105-247">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="e3105-248">Abra el **appsettings.jsen el archivo** y busque la `AuthorizedEmailAddress` configuración.</span><span class="sxs-lookup"><span data-stu-id="e3105-248">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="e3105-249">Agregue la dirección de correo electrónico o las direcciones que desee autorizar.</span><span class="sxs-lookup"><span data-stu-id="e3105-249">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="e3105-250">Separe varias direcciones de correo electrónico con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="e3105-250">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="e3105-251">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-251">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="e3105-252">Busque la `LDAPPath` configuración y quite el texto entre las `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="e3105-252">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="e3105-253">Deje las comillas dobles en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e3105-253">Leave the double quotes in place.</span></span> <span data-ttu-id="e3105-254">Cuando haya terminado, la configuración debería tener este aspecto.</span><span class="sxs-lookup"><span data-stu-id="e3105-254">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="e3105-255">Busque la `AuthorizedRoles` configuración y elimine toda la línea.</span><span class="sxs-lookup"><span data-stu-id="e3105-255">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="e3105-256">En esta imagen se muestra **appsettings.jsarchivo** con el formato correcto para la autorización de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e3105-256">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![El appsettings.jsarchivo que muestra el método de autorización de correo electrónico](../media/dke-email-accesssetting.png)

<span data-ttu-id="e3105-258">**Para establecer la configuración de acceso clave para DKE mediante la autorización de roles**</span><span class="sxs-lookup"><span data-stu-id="e3105-258">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="e3105-259">Abra el **appsettings.jsen el archivo** y busque la `AuthorizedRoles` configuración.</span><span class="sxs-lookup"><span data-stu-id="e3105-259">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="e3105-260">Agregue los nombres de grupo de Active Directory que desee autorizar.</span><span class="sxs-lookup"><span data-stu-id="e3105-260">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="e3105-261">Separe varios nombres de grupo con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="e3105-261">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="e3105-262">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-262">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="e3105-263">Busque la `LDAPPath` configuración y agregue el dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3105-263">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="e3105-264">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-264">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="e3105-265">Busque la `AuthorizedEmailAddress` configuración y elimine toda la línea.</span><span class="sxs-lookup"><span data-stu-id="e3105-265">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="e3105-266">En esta imagen se muestra **appsettings.jsarchivo** con el formato correcto para la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="e3105-266">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsarchivo que muestra el método de autorización de roles](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="e3105-268">Configuración de inquilino y clave</span><span class="sxs-lookup"><span data-stu-id="e3105-268">Tenant and key settings</span></span>

<span data-ttu-id="e3105-269">La configuración del inquilino y la clave de DKE se encuentran **enappsettings.jsarchivo de** inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e3105-269">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="e3105-270">**Para configurar el espacio empresarial y las opciones de clave para DKE**</span><span class="sxs-lookup"><span data-stu-id="e3105-270">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="e3105-271">Abra el **appsettings.jsen el** archivo.</span><span class="sxs-lookup"><span data-stu-id="e3105-271">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="e3105-272">Busque la `ValidIssuers` configuración y reempláctela `<tenantid>` por su id. de espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="e3105-272">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="e3105-273">Puede buscar su id. de inquilino yendo a Azure Portal y viendo las propiedades [del espacio empresarial.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="e3105-273">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="e3105-274">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-274">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="e3105-275">Busque el `JwtAudience` archivo .</span><span class="sxs-lookup"><span data-stu-id="e3105-275">Locate the `JwtAudience`.</span></span> <span data-ttu-id="e3105-276">Reemplace `<yourhostname>` por el nombre de host de la máquina donde se ejecutará el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-276">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="e3105-277">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-277">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e3105-278">El valor debe `JwtAudience` coincidir exactamente con el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="e3105-278">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="e3105-279">Puede usar **localhost:5001** durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="e3105-279">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="e3105-280">Sin embargo, cuando haya terminado la depuración, asegúrese de actualizar este valor al nombre de host del servidor.</span><span class="sxs-lookup"><span data-stu-id="e3105-280">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="e3105-281">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="e3105-281">`TestKeys:Name`.</span></span> <span data-ttu-id="e3105-282">Escriba un nombre para la clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-282">Enter a name for your key.</span></span> <span data-ttu-id="e3105-283">Por ejemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="e3105-283">For example: `TestKey1`</span></span>
- <span data-ttu-id="e3105-284">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="e3105-284">`TestKeys:Id`.</span></span> <span data-ttu-id="e3105-285">Crear un GUID y escribirlo como `TestKeys:ID` el valor.</span><span class="sxs-lookup"><span data-stu-id="e3105-285">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="e3105-286">Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="e3105-286">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="e3105-287">Puede usar un sitio como [el generador guid en](https://guidgenerator.com/) línea para generar aleatoriamente un GUID.</span><span class="sxs-lookup"><span data-stu-id="e3105-287">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="e3105-288">Esta imagen muestra el formato correcto para la configuración del espacio empresarial y las **clavesappsettings.jsen**.</span><span class="sxs-lookup"><span data-stu-id="e3105-288">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="e3105-289">`LDAPPath` está configurado para la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="e3105-289">`LDAPPath` is configured for role authorization.</span></span>

![Muestra la configuración de inquilino y clave correcta para DKE en appsettings.jsarchivo on.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="e3105-291">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="e3105-291">Generate test keys</span></span>

<span data-ttu-id="e3105-292">Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.</span><span class="sxs-lookup"><span data-stu-id="e3105-292">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="e3105-293">Para generar claves:</span><span class="sxs-lookup"><span data-stu-id="e3105-293">To generate keys:</span></span>

1. <span data-ttu-id="e3105-294">En el menú Inicio de Windows, ejecuta el símbolo del sistema de OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="e3105-294">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="e3105-295">Cambie a la carpeta donde desea guardar las claves de prueba.</span><span class="sxs-lookup"><span data-stu-id="e3105-295">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="e3105-296">Los archivos que cree completando los pasos de esta tarea se almacenan en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="e3105-296">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="e3105-297">Genere la nueva clave de prueba.</span><span class="sxs-lookup"><span data-stu-id="e3105-297">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="e3105-298">Genera la clave privada.</span><span class="sxs-lookup"><span data-stu-id="e3105-298">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="e3105-299">Genere la clave pública.</span><span class="sxs-lookup"><span data-stu-id="e3105-299">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="e3105-300">En un editor de texto, **abra pubkeyonly.pem**.</span><span class="sxs-lookup"><span data-stu-id="e3105-300">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="e3105-301">Copie todo el contenido del archivo **pubkeyonly.pem,** excepto la primera y la última línea, en la sección del archivo `PublicPem` **appsettings.jsarchivo.**</span><span class="sxs-lookup"><span data-stu-id="e3105-301">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="e3105-302">En un editor de texto, abra **privkeynopass.pem**.</span><span class="sxs-lookup"><span data-stu-id="e3105-302">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="e3105-303">Copie todo el contenido del archivo **privkeynopass.pem,** excepto la primera y la última línea, en la sección del archivo `PrivatePem` **appsettings.jsarchivo.**</span><span class="sxs-lookup"><span data-stu-id="e3105-303">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="e3105-304">Quite todos los espacios en blanco y las nuevas líneas tanto en `PublicPem` las secciones como en las `PrivatePem` secciones.</span><span class="sxs-lookup"><span data-stu-id="e3105-304">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e3105-305">Al copiar este contenido, no elimine ninguno de los datos PEM.</span><span class="sxs-lookup"><span data-stu-id="e3105-305">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="e3105-306">En Visual Studio código, vaya al **Startup.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="e3105-306">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="e3105-307">Este archivo se encuentra en el repositorio DoubleKeyEncryptionService clonado localmente en DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="e3105-307">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="e3105-308">Busque las líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3105-308">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="e3105-309">Reemplace estas líneas por el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3105-309">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="e3105-310">Los resultados finales deben ser similares a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="e3105-310">The end results should look similar to the following.</span></span>

    ![startup.cs de vista previa pública](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="e3105-312">Ahora ya está listo para compilar [el proyecto DKE.](#build-the-project)</span><span class="sxs-lookup"><span data-stu-id="e3105-312">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="e3105-313">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e3105-313">Build the project</span></span>

<span data-ttu-id="e3105-314">Siga las instrucciones siguientes para crear el proyecto DKE localmente:</span><span class="sxs-lookup"><span data-stu-id="e3105-314">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="e3105-315">En Visual Studio código, en el repositorio del servicio  DKE, seleccione Ver paleta de comandos y, a \>  continuación, **escriba compilación** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="e3105-315">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="e3105-316">En la lista, elija **Tareas: Ejecutar tarea de compilación.**</span><span class="sxs-lookup"><span data-stu-id="e3105-316">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="e3105-317">Si no se encuentran tareas de compilación, seleccione Configurar tarea **de** compilación y cree una para .NET Core de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="e3105-317">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Configurar la tarea de compilación que falta para .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="e3105-319">Elija **Crear tasks.jsa partir de la plantilla.**</span><span class="sxs-lookup"><span data-stu-id="e3105-319">Choose **Create tasks.json from template**.</span></span>

      ![Crear tasks.jsarchivo a partir de la plantilla para DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="e3105-321">En la lista de tipos de plantilla, seleccione **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="e3105-321">From the list of template types, select **.NET Core**.</span></span>

      ![Seleccionar la plantilla correcta para DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="e3105-323">En la sección de compilación, busque la ruta de acceso al **archivo customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="e3105-323">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="e3105-324">Si no está ahí, agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="e3105-324">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="e3105-325">Vuelva a ejecutar la compilación.</span><span class="sxs-lookup"><span data-stu-id="e3105-325">Run the build again.</span></span>

3. <span data-ttu-id="e3105-326">Compruebe que no haya errores rojos en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="e3105-326">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="e3105-327">Si hay errores de color rojo, compruebe la salida de la consola.</span><span class="sxs-lookup"><span data-stu-id="e3105-327">If there are red errors, check the console output.</span></span> <span data-ttu-id="e3105-328">Asegúrese de que ha completado todos los pasos anteriores correctamente y de que están presentes las versiones de compilación correctas.</span><span class="sxs-lookup"><span data-stu-id="e3105-328">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="e3105-329">Seleccione **Ejecutar** \> **la depuración de inicio** para depurar el proceso.</span><span class="sxs-lookup"><span data-stu-id="e3105-329">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="e3105-330">Si se le pide que seleccione un entorno, seleccione **.NET core**.</span><span class="sxs-lookup"><span data-stu-id="e3105-330">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="e3105-331">El depurador de .NET core normalmente se inicia en `https://localhost:5001` .</span><span class="sxs-lookup"><span data-stu-id="e3105-331">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="e3105-332">Para ver la clave de prueba, vaya y anexe una barra diagonal `https://localhost:5001` (/) y el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-332">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="e3105-333">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-333">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="e3105-334">La clave debe mostrarse en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="e3105-334">The key should display in JSON format.</span></span>

<span data-ttu-id="e3105-335">La configuración ya está completa.</span><span class="sxs-lookup"><span data-stu-id="e3105-335">Your setup is now complete.</span></span> <span data-ttu-id="e3105-336">Antes de publicar el almacén de claves, en appsettings.js, para la configuración JwtAudience, asegúrate de que el valor del nombre de host coincida exactamente con el nombre de host de App Service.</span><span class="sxs-lookup"><span data-stu-id="e3105-336">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="e3105-337">Es posible que lo haya cambiado a localhost para solucionar problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e3105-337">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="e3105-338">Implementar el servicio DKE y publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="e3105-338">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="e3105-339">Para implementaciones de producción, implemente el servicio en una nube de terceros o [publeméntelo en un sistema local.](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)</span><span class="sxs-lookup"><span data-stu-id="e3105-339">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="e3105-340">Es posible que prefieras otros métodos para implementar las claves.</span><span class="sxs-lookup"><span data-stu-id="e3105-340">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="e3105-341">Seleccione el método que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="e3105-341">Select the method that works best for your organization.</span></span>

<span data-ttu-id="e3105-342">Para las implementaciones piloto, puede implementar en Azure y empezar a trabajar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e3105-342">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="e3105-343">**Para crear una instancia de Azure Web App para hospedar la implementación de DKE**</span><span class="sxs-lookup"><span data-stu-id="e3105-343">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="e3105-344">Para publicar el almacén de claves, creará una instancia de Azure App Service para hospedar la implementación de DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-344">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="e3105-345">A continuación, publicará las claves generadas en Azure.</span><span class="sxs-lookup"><span data-stu-id="e3105-345">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="e3105-346">En el explorador, inicie sesión en [Microsoft Azure Portal](https://ms.portal.azure.com)y vaya a App **Services**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="e3105-346">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="e3105-347">Seleccione la suscripción y el grupo de recursos y defina los detalles de la instancia.</span><span class="sxs-lookup"><span data-stu-id="e3105-347">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="e3105-348">Escriba el nombre de host del equipo donde desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-348">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="e3105-349">Asegúrese de que es el mismo nombre que el definido para la configuración jwtAudience en el [**appsettings.jsarchivo on.**](#tenant-and-key-settings)</span><span class="sxs-lookup"><span data-stu-id="e3105-349">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="e3105-350">El valor que proporcione para el nombre también es WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="e3105-350">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="e3105-351">Para **Publicar,** seleccionar **código y** para la pila de tiempo **de** ejecución, seleccione **.NET Core 3.1**.</span><span class="sxs-lookup"><span data-stu-id="e3105-351">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="e3105-352">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-352">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3105-353">![Agregar el servicio de aplicaciones](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="e3105-353">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="e3105-354">En la parte inferior de la página, seleccione **Revisar + crear** y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e3105-354">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="e3105-355">Realice una de las siguientes acciones para publicar las claves generadas:</span><span class="sxs-lookup"><span data-stu-id="e3105-355">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="e3105-356">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e3105-356">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="e3105-357">Publicar a través de FTP</span><span class="sxs-lookup"><span data-stu-id="e3105-357">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="e3105-358">Publicar a Visual Studio 2019 o posterior</span><span class="sxs-lookup"><span data-stu-id="e3105-358">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="e3105-359">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e3105-359">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="e3105-360">Vaya a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="e3105-360">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="e3105-361">Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e3105-361">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="e3105-362">En el código base del almacén de claves, vaya a la carpeta **customer-key-store\src\customer-key-store** y compruebe que esta carpeta contiene el archivo **customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="e3105-362">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="e3105-363">Ejecutar: **publicación de dotnet**</span><span class="sxs-lookup"><span data-stu-id="e3105-363">Run: **dotnet publish**</span></span>

   <span data-ttu-id="e3105-364">La ventana de salida muestra el directorio donde se implementó la publicación.</span><span class="sxs-lookup"><span data-stu-id="e3105-364">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="e3105-365">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="e3105-365">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="e3105-366">Envíe todos los archivos del directorio de publicación a un archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="e3105-366">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="e3105-367">Al crear el archivo .zip, asegúrate de que todos los archivos del directorio se encuentran en el nivel raíz del archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="e3105-367">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="e3105-368">Arrastre y coloque el archivo .zip que cree en el sitio ZipDeployUI que abrió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e3105-368">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="e3105-369">Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e3105-369">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="e3105-370">DKE se implementa y puede buscar las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e3105-370">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="e3105-371">Continúe [validando la implementación que se muestra](#validate-your-deployment) a continuación.</span><span class="sxs-lookup"><span data-stu-id="e3105-371">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="e3105-372">Publicar a través de FTP</span><span class="sxs-lookup"><span data-stu-id="e3105-372">Publish via FTP</span></span>

1. <span data-ttu-id="e3105-373">Conéctese al servicio de aplicaciones que creó [anteriormente.](#deploy-the-dke-service-and-publish-the-key-store)</span><span class="sxs-lookup"><span data-stu-id="e3105-373">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="e3105-374">En el explorador, vaya a: Panel FTP de implementación manual del Centro de implementación de **Azure Portal** App  >    >    >    >    >  Service.</span><span class="sxs-lookup"><span data-stu-id="e3105-374">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="e3105-375">Copie las cadenas de conexión que se muestran en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="e3105-375">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="e3105-376">Usará estas cadenas para conectarse al servicio web de aplicaciones y cargar archivos a través de FTP.</span><span class="sxs-lookup"><span data-stu-id="e3105-376">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="e3105-377">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-377">For example:</span></span>

   ![Copiar cadenas de conexión desde el panel FTP](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="e3105-379">En el código base para el almacenamiento de claves, vaya al directorio **customer-key-store\src\customer-key-store**.</span><span class="sxs-lookup"><span data-stu-id="e3105-379">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="e3105-380">Compruebe que este directorio contiene el **archivo customerkeystore.csproj.**</span><span class="sxs-lookup"><span data-stu-id="e3105-380">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="e3105-381">Ejecutar: **publicación de dotnet**</span><span class="sxs-lookup"><span data-stu-id="e3105-381">Run: **dotnet publish**</span></span>

   <span data-ttu-id="e3105-382">El resultado contiene el directorio donde se implementó la publicación.</span><span class="sxs-lookup"><span data-stu-id="e3105-382">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="e3105-383">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="e3105-383">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="e3105-384">Envíe todos los archivos del directorio de publicación a un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="e3105-384">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="e3105-385">Al crear el archivo .zip, asegúrate de que todos los archivos del directorio se encuentran en el nivel raíz del archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="e3105-385">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="e3105-386">Desde el cliente FTP, use la información de conexión que copió para conectarse a App Service.</span><span class="sxs-lookup"><span data-stu-id="e3105-386">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="e3105-387">Cargue el archivo .zip que creó en el paso anterior en el directorio raíz de la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="e3105-387">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="e3105-388">DKE está implementado y puede buscar las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e3105-388">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="e3105-389">A continuación, [valide la implementación.](#validate-your-deployment)</span><span class="sxs-lookup"><span data-stu-id="e3105-389">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="e3105-390">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="e3105-390">Validate your deployment</span></span>

<span data-ttu-id="e3105-391">Después de implementar DKE mediante uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="e3105-391">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="e3105-392">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="e3105-392">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="e3105-393">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-393">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="e3105-394">Asegúrese de que no aparecen errores en el resultado.</span><span class="sxs-lookup"><span data-stu-id="e3105-394">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="e3105-395">Cuando esté listo, [registre el almacén de claves.](#register-your-key-store)</span><span class="sxs-lookup"><span data-stu-id="e3105-395">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="e3105-396">El nombre de la clave distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e3105-396">The key name is case sensitive.</span></span> <span data-ttu-id="e3105-397">Escriba el nombre de la clave tal como aparece en el appsettings.jsarchivo de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="e3105-397">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="e3105-398">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="e3105-398">Register your key store</span></span>

<span data-ttu-id="e3105-399">Los siguientes pasos permiten registrar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-399">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="e3105-400">El último paso para implementar DKE es registrar el servicio DKE antes de empezar a crear etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e3105-400">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="e3105-401">Para registrar el servicio DKE:</span><span class="sxs-lookup"><span data-stu-id="e3105-401">To register the DKE service:</span></span>

1. <span data-ttu-id="e3105-402">En el explorador, abra [Microsoft Azure Portal](https://ms.portal.azure.com/)y vaya a **Registros** de aplicaciones de identidad de todos \>  \> **los servicios.**</span><span class="sxs-lookup"><span data-stu-id="e3105-402">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="e3105-403">Seleccione **Nuevo registro** y escriba un nombre significativo.</span><span class="sxs-lookup"><span data-stu-id="e3105-403">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="e3105-404">Seleccione un tipo de cuenta de las opciones mostradas.</span><span class="sxs-lookup"><span data-stu-id="e3105-404">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="e3105-405">Si usa Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com,** seleccione Solo cuentas en este directorio de la organización **(Solo Microsoft - Inquilino único).**</span><span class="sxs-lookup"><span data-stu-id="e3105-405">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="e3105-406">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-406">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3105-407">![Registro de nuevas aplicaciones](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="e3105-407">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="e3105-408">En la parte inferior de la página, seleccione **Registrar** para crear el nuevo registro de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e3105-408">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="e3105-409">En el nuevo registro de aplicaciones, en el panel izquierdo, en **Administrar**, seleccione **Autenticación.**</span><span class="sxs-lookup"><span data-stu-id="e3105-409">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="e3105-410">Seleccione **Agregar una plataforma.**</span><span class="sxs-lookup"><span data-stu-id="e3105-410">Select **Add a platform**.</span></span>

7. <span data-ttu-id="e3105-411">En el elemento **emergente Configurar plataformas,** seleccione **Web**.</span><span class="sxs-lookup"><span data-stu-id="e3105-411">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="e3105-412">En **URI de redireccionamiento,** escriba el URI de su servicio de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-412">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="e3105-413">Escribe la dirección URL de App Service, incluidos el nombre de host y el dominio.</span><span class="sxs-lookup"><span data-stu-id="e3105-413">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="e3105-414">Por ejemplo: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="e3105-414">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="e3105-415">La dirección URL que escriba debe coincidir con el nombre de host donde se implementa el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-415">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="e3105-416">Si está probando localmente con Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="e3105-416">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="e3105-417">En todos los casos, el esquema debe ser **https**.</span><span class="sxs-lookup"><span data-stu-id="e3105-417">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="e3105-418">Asegúrate de que el nombre de host coincida exactamente con el nombre de host de App Service.</span><span class="sxs-lookup"><span data-stu-id="e3105-418">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="e3105-419">Es posible que lo haya cambiado para `localhost` solucionar problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e3105-419">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="e3105-420">En **appsettings.js,** este valor es el nombre de host para el que se estableció `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="e3105-420">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="e3105-421">En **Concesión implícita,** active la casilla **de verificación de tokens de** identificador.</span><span class="sxs-lookup"><span data-stu-id="e3105-421">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="e3105-422">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e3105-422">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="e3105-423">En el panel izquierdo, seleccione **Exponer una API** y, a continuación, junto a URI de id. de aplicación, seleccione **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="e3105-423">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="e3105-424">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select Add a **scope**.</span><span class="sxs-lookup"><span data-stu-id="e3105-424">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="e3105-425">En el nuevo ámbito:</span><span class="sxs-lookup"><span data-stu-id="e3105-425">In the new scope:</span></span>

    1. <span data-ttu-id="e3105-426">Defina el nombre del ámbito **como user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="e3105-426">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="e3105-427">Seleccione los administradores y usuarios que pueden dar su consentimiento.</span><span class="sxs-lookup"><span data-stu-id="e3105-427">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="e3105-428">Defina los valores restantes necesarios.</span><span class="sxs-lookup"><span data-stu-id="e3105-428">Define any remaining values required.</span></span>

    4. <span data-ttu-id="e3105-429">Seleccione **Agregar ámbito**.</span><span class="sxs-lookup"><span data-stu-id="e3105-429">Select **Add scope**.</span></span>

    5. <span data-ttu-id="e3105-430">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e3105-430">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="e3105-431">En la página **Exponer una API,** en el **área Aplicaciones cliente autorizadas,** seleccione Agregar una **aplicación cliente.**</span><span class="sxs-lookup"><span data-stu-id="e3105-431">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="e3105-432">En la nueva aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="e3105-432">In the new client application:</span></span>

    1. <span data-ttu-id="e3105-433">Defina el identificador de cliente como **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="e3105-433">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="e3105-434">Este valor es el Microsoft Office de cliente y permite a Office obtener un token de acceso para el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="e3105-434">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="e3105-435">En **Ámbitos autorizados,** seleccione **user_impersonation** ámbito.</span><span class="sxs-lookup"><span data-stu-id="e3105-435">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="e3105-436">Seleccione **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="e3105-436">Select **Add application**.</span></span>

    4. <span data-ttu-id="e3105-437">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e3105-437">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="e3105-438">El servicio DKE ya está registrado.</span><span class="sxs-lookup"><span data-stu-id="e3105-438">Your DKE service is now registered.</span></span> <span data-ttu-id="e3105-439">Continúe creando [etiquetas con DKE](#create-sensitivity-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="e3105-439">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="e3105-440">Crear etiquetas de confidencialidad con DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-440">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="e3105-441">En el Centro de cumplimiento de Microsoft 365, cree una nueva etiqueta de confidencialidad y aplique el cifrado como lo haría de otro modo.</span><span class="sxs-lookup"><span data-stu-id="e3105-441">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="e3105-442">Seleccione **Usar cifrado de doble clave** y escriba la dirección URL del extremo de la clave.</span><span class="sxs-lookup"><span data-stu-id="e3105-442">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="e3105-443">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3105-443">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e3105-444">![Seleccione Usar cifrado de doble clave en el Centro de cumplimiento de Microsoft 365](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="e3105-444">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="e3105-445">Las etiquetas DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de Aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="e3105-445">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="e3105-446">Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e3105-446">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="e3105-447">Habilitar DKE en el cliente</span><span class="sxs-lookup"><span data-stu-id="e3105-447">Enable DKE in your client</span></span>

<span data-ttu-id="e3105-448">Si es un usuario de Office Insider, DKE está habilitado para usted.</span><span class="sxs-lookup"><span data-stu-id="e3105-448">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="e3105-449">De lo contrario, habilite DKE para el cliente agregando las siguientes claves del Registro:</span><span class="sxs-lookup"><span data-stu-id="e3105-449">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="e3105-450">Migrar archivos protegidos de etiquetas HYOK a etiquetas DKE</span><span class="sxs-lookup"><span data-stu-id="e3105-450">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="e3105-451">Si lo desea, una vez que haya terminado de configurar DKE, puede migrar el contenido que ha protegido mediante etiquetas HYOK a etiquetas DKE.</span><span class="sxs-lookup"><span data-stu-id="e3105-451">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="e3105-452">Para migrar, usará el escáner AIP.</span><span class="sxs-lookup"><span data-stu-id="e3105-452">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="e3105-453">Para empezar a usar el escáner, consulte ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)</span><span class="sxs-lookup"><span data-stu-id="e3105-453">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="e3105-454">Si no migra contenido, el contenido protegido con HYOK no se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="e3105-454">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
