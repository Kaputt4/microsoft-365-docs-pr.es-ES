---
title: Cifrado de doble clave (DKE)
description: DKE permite proteger datos extremadamente confidenciales y mantener el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7f54832001f80418ffb09bc45da8f32c79f3df53
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503041"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="4b509-103">Cifrado de doble clave (DKE)</span><span class="sxs-lookup"><span data-stu-id="4b509-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="4b509-104">*Se aplica a: cifrado de doble clave para Microsoft 365 Public Preview, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="4b509-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="4b509-105">*Instrucciones para: [cliente de etiquetado Unificado de Azure Information Protection para Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="4b509-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="4b509-106">*Descripción del servicio para: [cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="4b509-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="4b509-107">El cifrado de doble clave (DKE) utiliza dos claves conjuntamente para obtener acceso al contenido protegido.</span><span class="sxs-lookup"><span data-stu-id="4b509-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="4b509-108">Se almacena una clave en Microsoft Azure y se mantiene la otra clave.</span><span class="sxs-lookup"><span data-stu-id="4b509-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="4b509-109">El cliente de etiqueta Unificado de Azure Information Protection protege el contenido altamente confidencial mientras mantiene un control total de una de las claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="4b509-110">El cifrado de doble clave admite tanto la nube como las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="4b509-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="4b509-111">Estas implementaciones ayudan a garantizar que los datos cifrados permanezcan opacos dondequiera que almacene los datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="4b509-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="4b509-112">Para obtener más información acerca de las claves predeterminadas de raíz de inquilino basadas en la nube, vea [Planning and Implementing Your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="4b509-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="4b509-113">Si las organizaciones tienen alguno de los siguientes requisitos, puede usar DKE para ayudar a proteger el contenido:</span><span class="sxs-lookup"><span data-stu-id="4b509-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="4b509-114">Desea asegurarse de que *solo usted* puede descifrar el contenido protegido en todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="4b509-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="4b509-115">No desea que Microsoft tenga acceso a datos protegidos por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="4b509-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="4b509-116">Tiene requisitos normativos para mantener las claves dentro de un límite geográfico.</span><span class="sxs-lookup"><span data-stu-id="4b509-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="4b509-117">Todas las claves que se incluyen para el cifrado y descifrado de datos se mantienen en el centro de datos.</span><span class="sxs-lookup"><span data-stu-id="4b509-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="4b509-118">Requisitos de licencia y sistema para DKE</span><span class="sxs-lookup"><span data-stu-id="4b509-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="4b509-119">El cifrado de doble clave para Microsoft 365 incluye Microsoft 365 E5 y Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4b509-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="4b509-120">Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="4b509-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="4b509-121">Para obtener más información acerca de estas licencias, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="4b509-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="4b509-122">**Office Insider** Para usar la versión preliminar pública, debe ser miembro del programa Office Insider.</span><span class="sxs-lookup"><span data-stu-id="4b509-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="4b509-123">Para unirse a Office Insider, vaya a [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="4b509-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="4b509-124">Una vez que sea miembro, prepare el entorno para implementar las compilaciones de Office Insider eligiendo el método de implementación adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="4b509-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="4b509-125">Para obtener instrucciones, consulte [Introducción a la implementación de compilaciones de Office Insider](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="4b509-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="4b509-126">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="4b509-126">**Azure Information Protection**.</span></span> <span data-ttu-id="4b509-127">DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="4b509-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="4b509-128">Entornos admitidos para almacenar y ver contenido protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="4b509-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="4b509-129">**Aplicaciones compatibles**.</span><span class="sxs-lookup"><span data-stu-id="4b509-129">**Supported applications**.</span></span> <span data-ttu-id="4b509-130">[Microsoft 365 apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients in Windows, incluidos Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="4b509-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="4b509-131">**Soporte de contenido en línea**.</span><span class="sxs-lookup"><span data-stu-id="4b509-131">**Online content support**.</span></span> <span data-ttu-id="4b509-132">Se admiten los documentos y archivos almacenados en línea tanto en Microsoft SharePoint como en OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="4b509-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="4b509-133">Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos cifrados y archivos en línea.</span><span class="sxs-lookup"><span data-stu-id="4b509-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="4b509-134">En su lugar, debe ver el contenido protegido con las aplicaciones de escritorio en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="4b509-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="4b509-135">Acerca de este artículo de la versión preliminar pública</span><span class="sxs-lookup"><span data-stu-id="4b509-135">About this public preview article</span></span>

<span data-ttu-id="4b509-136">Hay varias formas de realizar algunos de los pasos para implementar el cifrado doble de claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="4b509-137">En este artículo se proporcionan instrucciones detalladas para que los administradores menos experimentados implementen correctamente el servicio.</span><span class="sxs-lookup"><span data-stu-id="4b509-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="4b509-138">Si le resulta cómodo hacerlo, puede elegir usar sus propios métodos.</span><span class="sxs-lookup"><span data-stu-id="4b509-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="4b509-139">En este artículo se incluyen instrucciones paso a paso sobre cómo implementar el servicio de cifrado de doble clave en Azure.</span><span class="sxs-lookup"><span data-stu-id="4b509-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="4b509-140">Este escenario no es algo que probablemente haría en producción.</span><span class="sxs-lookup"><span data-stu-id="4b509-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="4b509-141">Para la versión preliminar pública, el uso de Azure es una forma rápida de implementar DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="4b509-142">La implementación en Azure le permite empezar a usar el cifrado de doble clave inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4b509-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="4b509-143">Puede implementar el servicio localmente en la red o con otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="4b509-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="4b509-144">Deberá publicar el almacén de claves con los métodos apropiados para esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="4b509-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="4b509-145">Implementar el cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="4b509-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="4b509-146">Este artículo y el vídeo de implementación usan Azure como destino de implementación para el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="4b509-147">Si va a realizar la implementación en otra ubicación, deberá proporcionar sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="4b509-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="4b509-148">Vea el [vídeo sobre la implementación de doble clave](https://youtu.be/vDWfHN_kygg) para ver una introducción paso a paso de los conceptos del artículo.</span><span class="sxs-lookup"><span data-stu-id="4b509-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="4b509-149">El vídeo tarda unos 18 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="4b509-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="4b509-150">Deberá seguir estos pasos generales para configurar el cifrado de doble clave para su organización.</span><span class="sxs-lookup"><span data-stu-id="4b509-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="4b509-151">Requisitos previos de instalación de software</span><span class="sxs-lookup"><span data-stu-id="4b509-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="4b509-152">Clone el repositorio de GitHub con cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="4b509-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="4b509-153">Modificación de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4b509-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="4b509-154">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="4b509-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="4b509-155">Compilar el proyecto</span><span class="sxs-lookup"><span data-stu-id="4b509-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="4b509-156">Publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="4b509-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="4b509-157">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="4b509-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="4b509-158">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="4b509-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="4b509-159">Cree etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="4b509-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="4b509-160">Cuando haya terminado, puede cifrar documentos y archivos con DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="4b509-161">Para obtener más información, consulte [aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="4b509-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="4b509-162">Requisitos previos de instalación de software</span><span class="sxs-lookup"><span data-stu-id="4b509-162">Install software prerequisites</span></span>

<span data-ttu-id="4b509-163">Existen dos tipos de requisitos previos de software para el cifrado doble de claves</span><span class="sxs-lookup"><span data-stu-id="4b509-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="4b509-164">Requisitos previos del servicio de cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="4b509-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="4b509-165">Requisitos previos de cifrado de doble clave para equipos cliente</span><span class="sxs-lookup"><span data-stu-id="4b509-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="4b509-166">Requisitos previos del servicio de cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="4b509-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="4b509-167">Instale estos requisitos previos en el equipo en el que desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="4b509-168">**SDK .net Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="4b509-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="4b509-169">Descargue e instale el SDK desde [download .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="4b509-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="4b509-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="4b509-170">**Visual Studio Code**.</span></span> <span data-ttu-id="4b509-171">Descargue Visual Studio Code desde [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="4b509-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="4b509-172">Una vez instalado, ejecute Visual Studio Code y seleccione **Ver** \> **extensiones**.</span><span class="sxs-lookup"><span data-stu-id="4b509-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="4b509-173">Instale estas extensiones.</span><span class="sxs-lookup"><span data-stu-id="4b509-173">Install these extensions.</span></span>

- <span data-ttu-id="4b509-174">C# para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4b509-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="4b509-175">Administrador de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="4b509-175">NuGet Package Manager</span></span>

<span data-ttu-id="4b509-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="4b509-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="4b509-177">Configure al menos un [método de implementación](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="4b509-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="4b509-178">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="4b509-178">**Git resources**.</span></span> <span data-ttu-id="4b509-179">Descargue e instale uno de los siguientes elementos.</span><span class="sxs-lookup"><span data-stu-id="4b509-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="4b509-180">Git</span><span class="sxs-lookup"><span data-stu-id="4b509-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="4b509-181">Escritorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="4b509-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="4b509-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b509-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="4b509-183">**OpenSSL** Debe tener instalado [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) para [generar las claves de prueba](#generate-test-keys) después de implementar DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="4b509-184">Asegúrese de que está invocando correctamente desde la ruta de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="4b509-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="4b509-185">Por ejemplo, consulte "agregar el directorio de instalación a la ruta de acceso" en https://www.osradar.com/install-openssl-windows/ para más detalles.</span><span class="sxs-lookup"><span data-stu-id="4b509-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="4b509-186">Requisitos previos de cifrado de doble clave para equipos cliente</span><span class="sxs-lookup"><span data-stu-id="4b509-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="4b509-187">Instale estos requisitos previos en cada equipo cliente donde quiera proteger y consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="4b509-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="4b509-188">**Microsoft Office** versión \*. 12711 o posterior.</span><span class="sxs-lookup"><span data-stu-id="4b509-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="4b509-189">**Azure Information Protection el cliente de etiquetado unificado** versiones 2.7.93.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="4b509-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="4b509-190">Descargue e instale el cliente de etiquetado Unificado de [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="4b509-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="4b509-191">Clonar el repositorio de GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="4b509-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="4b509-192">Microsoft proporciona los archivos de origen de DKE en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="4b509-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="4b509-193">Clonar el repositorio para compilar el proyecto de forma local para el uso de su organización.</span><span class="sxs-lookup"><span data-stu-id="4b509-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="4b509-194">El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="4b509-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="4b509-195">Las siguientes instrucciones están destinadas a usuarios no con experiencia de Git o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="4b509-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="4b509-196">En el explorador, vaya a:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="4b509-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="4b509-197">Hacia el lado derecho de la pantalla, seleccione **código**.</span><span class="sxs-lookup"><span data-stu-id="4b509-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="4b509-198">Es posible que la versión de la interfaz de usuario muestre un botón **clonar o descargar** .</span><span class="sxs-lookup"><span data-stu-id="4b509-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="4b509-199">A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="4b509-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="4b509-200">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Clone el repositorio del servicio de cifrado de doble clave desde GitHub":::

3. <span data-ttu-id="4b509-202">En Visual Studio Code, seleccione **Ver** \> **paleta de comandos** y seleccione **git: clon**.</span><span class="sxs-lookup"><span data-stu-id="4b509-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="4b509-203">Para ir a la opción de la lista, empiece a escribir `git: clone` para filtrar las entradas y, a continuación, selecciónela en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4b509-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="4b509-204">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Opción de Visual Studio Code GIT: Clone":::

4. <span data-ttu-id="4b509-206">En el cuadro de texto, pegue la dirección URL que copió desde git y seleccione **clonar desde GitHub**.</span><span class="sxs-lookup"><span data-stu-id="4b509-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="4b509-207">En el cuadro de diálogo **Seleccionar carpeta** que aparece, busque y seleccione una ubicación para almacenar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="4b509-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="4b509-208">En el símbolo del sistema, seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="4b509-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="4b509-209">El repositorio se abre en Visual Studio Code y muestra la rama git actual en la parte inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="4b509-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="4b509-210">La rama debe ser **maestra**.</span><span class="sxs-lookup"><span data-stu-id="4b509-210">The branch should be **master**.</span></span>

    <span data-ttu-id="4b509-211">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Rama de patrón de Visual Studio Code":::

6. <span data-ttu-id="4b509-213">Seleccione el **patrón** de palabras y, a continuación, seleccione **public_preview** de la lista de ramas.</span><span class="sxs-lookup"><span data-stu-id="4b509-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4b509-214">Al seleccionar la rama public_preview, se asegura de que tiene los archivos correctos para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b509-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="4b509-215">Si no elige la rama correcta, se producirá un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="4b509-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="4b509-216">Ahora tiene su repositorio de origen de DKE configurado de forma local.</span><span class="sxs-lookup"><span data-stu-id="4b509-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="4b509-217">A continuación, [modifique la configuración](#modify-application-settings) de la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="4b509-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="4b509-218">Modificación de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4b509-218">Modify application settings</span></span>

<span data-ttu-id="4b509-219">Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de aplicación:</span><span class="sxs-lookup"><span data-stu-id="4b509-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="4b509-220">Configuración de acceso a claves</span><span class="sxs-lookup"><span data-stu-id="4b509-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="4b509-221">Configuración de inquilinos y claves</span><span class="sxs-lookup"><span data-stu-id="4b509-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="4b509-222">Modifique la configuración de la aplicación en el appsettings.jsarchivo.</span><span class="sxs-lookup"><span data-stu-id="4b509-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="4b509-223">Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="4b509-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="4b509-224">Por ejemplo, en Visual Studio Code, puede desplazarse hasta el archivo como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="4b509-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Buscar el appsettings.jsen el archivo para DKE.":::

#### <a name="key-access-settings"></a><span data-ttu-id="4b509-226">Configuración de acceso a claves</span><span class="sxs-lookup"><span data-stu-id="4b509-226">Key access settings</span></span>

<span data-ttu-id="4b509-227">Elija si desea usar el correo electrónico o la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="4b509-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="4b509-228">DKE solo admite uno de estos métodos de autenticación a la vez.</span><span class="sxs-lookup"><span data-stu-id="4b509-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="4b509-229">**Autorización de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="4b509-229">**Email authorization**.</span></span> <span data-ttu-id="4b509-230">Permite a su organización autorizar el acceso a claves basadas solo en direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4b509-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="4b509-231">**Autorización de roles**.</span><span class="sxs-lookup"><span data-stu-id="4b509-231">**Role authorization**.</span></span> <span data-ttu-id="4b509-232">Permite a su organización autorizar el acceso a las claves en función de los grupos de Active Directory y requiere que el servicio Web pueda consultar LDAP.</span><span class="sxs-lookup"><span data-stu-id="4b509-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="4b509-233">**Para establecer la configuración de acceso clave para DKE mediante autorización de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="4b509-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="4b509-234">Abra el **appsettings.jsen** archivo y busque la `AuthorizedEmailAddress` configuración.</span><span class="sxs-lookup"><span data-stu-id="4b509-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="4b509-235">Agregue las direcciones o direcciones de correo electrónico que quiera autorizar.</span><span class="sxs-lookup"><span data-stu-id="4b509-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="4b509-236">Separe varias direcciones de correo electrónico con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="4b509-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="4b509-237">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="4b509-238">Busque la `LDAPPath` configuración y quite el texto `If role authorization is used then this is the LDAP path` comprendido entre las comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="4b509-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="4b509-239">Deje las comillas dobles en su posición.</span><span class="sxs-lookup"><span data-stu-id="4b509-239">Leave the double quotes in place.</span></span> <span data-ttu-id="4b509-240">Cuando haya terminado, la configuración debería ser similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="4b509-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="4b509-241">Busque la `AuthorizedRoles` configuración y elimine la línea completa.</span><span class="sxs-lookup"><span data-stu-id="4b509-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="4b509-242">Esta imagen muestra la **appsettings.jsen** un archivo con el formato correcto para la autorización de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4b509-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="El appsettings.jsen archivo que muestra el método de autorización de correo electrónico":::

<span data-ttu-id="4b509-244">**Para establecer la configuración de acceso clave de DKE mediante la autorización de roles**</span><span class="sxs-lookup"><span data-stu-id="4b509-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="4b509-245">Abra el **appsettings.jsen** archivo y busque la `AuthorizedRoles` configuración.</span><span class="sxs-lookup"><span data-stu-id="4b509-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="4b509-246">Agregue los nombres de grupo de Active Directory que desea autorizar.</span><span class="sxs-lookup"><span data-stu-id="4b509-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="4b509-247">Separe varios nombres de grupo con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="4b509-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="4b509-248">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="4b509-249">Busque la `LDAPPath` opción y agregue el dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4b509-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="4b509-250">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="4b509-251">Busque la `AuthorizedEmailAddress` configuración y elimine la línea completa.</span><span class="sxs-lookup"><span data-stu-id="4b509-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="4b509-252">Esta imagen muestra la **appsettings.jsen** un archivo con el formato correcto para la autorización de rol.</span><span class="sxs-lookup"><span data-stu-id="4b509-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsen el archivo que muestra el método de autorización de roles":::

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="4b509-254">Configuración de inquilinos y claves</span><span class="sxs-lookup"><span data-stu-id="4b509-254">Tenant and key settings</span></span>

<span data-ttu-id="4b509-255">La configuración de clave y de inquilino de DKE se encuentra en el **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b509-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="4b509-256">**Para establecer la configuración de inquilinos y claves para DKE**</span><span class="sxs-lookup"><span data-stu-id="4b509-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="4b509-257">Abra el **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b509-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="4b509-258">Busque la `ValidIssuers` configuración y sustitúyala `<tenantid>` por el identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="4b509-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="4b509-259">Puede encontrar el identificador de inquilino en el portal de Azure y ver las [propiedades del espacio](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)empresarial.</span><span class="sxs-lookup"><span data-stu-id="4b509-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="4b509-260">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="4b509-261">Busque el `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="4b509-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="4b509-262">Reemplace `<yourhostname>` por el nombre de host del equipo en el que se ejecutará el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="4b509-263">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="4b509-264">El valor de `JwtAudience` debe coincidir *exactamente*con el nombre de su host.</span><span class="sxs-lookup"><span data-stu-id="4b509-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="4b509-265">Puede usar **localhost: 5001** durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="4b509-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="4b509-266">Sin embargo, cuando haya terminado la depuración, asegúrese de actualizar este valor al nombre de host del servidor.</span><span class="sxs-lookup"><span data-stu-id="4b509-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="4b509-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="4b509-267">`TestKeys:Name`.</span></span> <span data-ttu-id="4b509-268">Escriba un nombre para la clave.</span><span class="sxs-lookup"><span data-stu-id="4b509-268">Enter a name for your key.</span></span> <span data-ttu-id="4b509-269">Por ejemplo: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="4b509-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="4b509-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="4b509-270">`TestKeys:Id`.</span></span> <span data-ttu-id="4b509-271">Cree un GUID y escríbalo como el `TestKeys:ID` valor.</span><span class="sxs-lookup"><span data-stu-id="4b509-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="4b509-272">Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="4b509-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="4b509-273">Puede usar un sitio como el [generador de GUID en línea](https://guidgenerator.com/) para generar un GUID de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="4b509-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="4b509-274">Esta imagen muestra el formato correcto para la configuración de inquilinos y claves de **appsettings.js**.</span><span class="sxs-lookup"><span data-stu-id="4b509-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="4b509-275">`LDAPPath`está configurado para la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="4b509-275">`LDAPPath` is configured for role authorization.</span></span>

:::image type="content" source="../media/dke-appsettingsjson-tenantkeysettings.png" alt-text="Muestra los valores correctos de las claves y los inquilinos para DKE en el appsettings.jsen el archivo.":::

### <a name="generate-test-keys"></a><span data-ttu-id="4b509-277">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="4b509-277">Generate test keys</span></span>

<span data-ttu-id="4b509-278">Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.</span><span class="sxs-lookup"><span data-stu-id="4b509-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="4b509-279">Para generar claves:</span><span class="sxs-lookup"><span data-stu-id="4b509-279">To generate keys:</span></span>

1. <span data-ttu-id="4b509-280">En el menú Inicio de Windows, ejecute el símbolo del sistema de OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="4b509-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="4b509-281">Cambie a la carpeta en la que desea guardar las claves de prueba.</span><span class="sxs-lookup"><span data-stu-id="4b509-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="4b509-282">Los archivos que crea al completar los pasos de esta tarea se almacenan en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="4b509-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="4b509-283">Generar la nueva clave de prueba.</span><span class="sxs-lookup"><span data-stu-id="4b509-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="4b509-284">Generar la clave privada.</span><span class="sxs-lookup"><span data-stu-id="4b509-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="4b509-285">Generar la clave pública.</span><span class="sxs-lookup"><span data-stu-id="4b509-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="4b509-286">En un editor de texto, Abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="4b509-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="4b509-287">Copie todo el contenido del archivo **pubkeyonly. pem** , excepto la primera y la última línea, en la `PublicPem` sección de la **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b509-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="4b509-288">En un editor de texto, Abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="4b509-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="4b509-289">Copie todo el contenido del archivo **privkeynopass. pem** , excepto la primera y la última línea, en la `PrivatePem` sección de la **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b509-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="4b509-290">Quite todos los espacios en blanco y las nuevas líneas en las `PublicPem` `PrivatePem` secciones y.</span><span class="sxs-lookup"><span data-stu-id="4b509-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4b509-291">Cuando copie este contenido, no elimine ninguno de los datos del PEM.</span><span class="sxs-lookup"><span data-stu-id="4b509-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="4b509-292">En Visual Studio Code, vaya al archivo **Startup.CS** .</span><span class="sxs-lookup"><span data-stu-id="4b509-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="4b509-293">Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="4b509-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="4b509-294">Busque las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="4b509-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="4b509-295">Reemplace estas líneas con el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b509-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="4b509-296">Los resultados finales deben ser similares a los siguientes.</span><span class="sxs-lookup"><span data-stu-id="4b509-296">The end results should look similar to the following.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="archivo startup.cs para la versión preliminar pública":::

<span data-ttu-id="4b509-298">Ahora está listo para [compilar el proyecto DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="4b509-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="4b509-299">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b509-299">Build the project</span></span>

<span data-ttu-id="4b509-300">Use las siguientes instrucciones para crear el proyecto DKE de forma local:</span><span class="sxs-lookup"><span data-stu-id="4b509-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="4b509-301">En Visual Studio Code, en el repositorio del servicio DKE, seleccione **Ver** \> **paleta de comandos** y, a continuación, escriba **generar** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4b509-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="4b509-302">En la lista, elija **tareas: Ejecutar tarea de compilación**.</span><span class="sxs-lookup"><span data-stu-id="4b509-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="4b509-303">Si no se encuentra ninguna tarea de compilación, seleccione **Configurar tarea de compilación** y cree una para .net Core de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="4b509-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Configurar la tarea de compilación que falta para .NET":::

   1. <span data-ttu-id="4b509-305">Elija **crear tasks.jsen a partir de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="4b509-305">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Crear tasks.jsen archivo de plantilla para DKE":::

   2. <span data-ttu-id="4b509-307">En la lista de tipos de plantilla, seleccione **.net Core**.</span><span class="sxs-lookup"><span data-stu-id="4b509-307">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Crear tasks.jsen archivo de plantilla para DKE":::

   3. <span data-ttu-id="4b509-309">En la sección generar, busque la ruta de acceso al archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="4b509-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="4b509-310">Si no está ahí, agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="4b509-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="4b509-311">Vuelva a ejecutar la compilación.</span><span class="sxs-lookup"><span data-stu-id="4b509-311">Run the build again.</span></span>

1. <span data-ttu-id="4b509-312">Compruebe que no haya errores rojos en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="4b509-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="4b509-313">Si hay errores rojos, compruebe el resultado de la consola.</span><span class="sxs-lookup"><span data-stu-id="4b509-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="4b509-314">Asegúrese de que ha completado todos los pasos anteriores correctamente y de que las versiones de compilación correctas están presentes.</span><span class="sxs-lookup"><span data-stu-id="4b509-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="4b509-315">Seleccione **Ejecutar** \> la **depuración de inicio** para depurar el proceso.</span><span class="sxs-lookup"><span data-stu-id="4b509-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="4b509-316">Si se le pide que seleccione un entorno, seleccione **.net Core**.</span><span class="sxs-lookup"><span data-stu-id="4b509-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="4b509-317">Normalmente, el depurador de .net Core se inicia en ' ' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' y se anexa una barra diagonal (/) y el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="4b509-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="4b509-318">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="4b509-319">La clave debe mostrarse en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="4b509-319">The key should display in JSON format.</span></span>

<span data-ttu-id="4b509-320">La configuración se ha completado.</span><span class="sxs-lookup"><span data-stu-id="4b509-320">Your setup is now complete.</span></span> <span data-ttu-id="4b509-321">Antes de publicar el almacén de claves, en appsettings.jsen la configuración de JwtAudience, asegúrese de que el valor para hostname coincide exactamente con el nombre de host del servicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b509-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="4b509-322">Puede que lo haya cambiado a localhost para solucionar los problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="4b509-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="4b509-323">Publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="4b509-323">Publish the key store</span></span>

<span data-ttu-id="4b509-324">Para publicar el almacén de claves, debe crear una instancia de Azure App Service para hospedar la implementación de DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="4b509-325">A continuación, publicará las claves generadas en Azure.</span><span class="sxs-lookup"><span data-stu-id="4b509-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="4b509-326">**Para crear una instancia de la aplicación Web de Azure para hospedar la implementación de DKE**</span><span class="sxs-lookup"><span data-stu-id="4b509-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="4b509-327">En el explorador, inicie sesión en el [portal de Microsoft Azure](https://ms.portal.azure.com)y vaya a **App Services**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="4b509-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="4b509-328">Seleccione su suscripción y grupo de recursos y defina los detalles de la instancia.</span><span class="sxs-lookup"><span data-stu-id="4b509-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="4b509-329">Escriba el nombre de host del equipo en el que desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="4b509-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="4b509-330">Asegúrese de que es el mismo nombre que el definido para la configuración JwtAudience en el [**appsettings.jsen**](#tenant-and-key-settings) el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b509-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="4b509-331">El valor que se proporciona para el nombre también es WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="4b509-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="4b509-332">Para **publicar**, seleccionar **código**y, para **pila en tiempo de ejecución**, seleccione **.net Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="4b509-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="4b509-333">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-333">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Agregar el servicio de aplicaciones":::

1. <span data-ttu-id="4b509-335">En la parte inferior de la página, seleccione **revisar + crear**y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4b509-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="4b509-336">Realice una de las siguientes acciones para publicar las claves generadas en Azure:</span><span class="sxs-lookup"><span data-stu-id="4b509-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="4b509-337">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4b509-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="4b509-338">Publicar mediante FTP</span><span class="sxs-lookup"><span data-stu-id="4b509-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="4b509-339">Publicar a través de Visual Studio 2019 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4b509-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="4b509-340">Publicar en un sistema local</span><span class="sxs-lookup"><span data-stu-id="4b509-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="4b509-341">Puede que prefiera otros métodos para implementar las claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="4b509-342">Seleccione el método que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="4b509-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="4b509-343">La [publicación a través de Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) y a un [sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) se describe en la [documentación de ASP .net](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="4b509-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="4b509-344">Si usa uno de estos métodos, abra las instrucciones en una pestaña independiente para que pueda volver fácilmente cuando termine.</span><span class="sxs-lookup"><span data-stu-id="4b509-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="4b509-345">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4b509-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="4b509-346">Vaya a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="4b509-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="4b509-347">Por ejemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4b509-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="4b509-348">En el código base del almacén de claves, vaya a la carpeta **Customer-Key-store\src\customer-Key-Store** y compruebe que esta carpeta contiene el archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="4b509-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="4b509-349">Ejecutar: **publicación dotnet**</span><span class="sxs-lookup"><span data-stu-id="4b509-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="4b509-350">La ventana resultados muestra el directorio en el que se ha implementado la publicación.</span><span class="sxs-lookup"><span data-stu-id="4b509-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="4b509-351">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4b509-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="4b509-352">Enviar todos los archivos del directorio de publicación a un archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="4b509-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="4b509-353">Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="4b509-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="4b509-354">Arrastre y coloque el archivo. zip que ha creado en el sitio de ZipDeployUI que ha abierto anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4b509-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="4b509-355">Por ejemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="4b509-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="4b509-356">DKE está implementado y puede ir a las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="4b509-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="4b509-357">Siga [validando la implementación](#validate-your-deployment) a continuación.</span><span class="sxs-lookup"><span data-stu-id="4b509-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="4b509-358">Publicar mediante FTP</span><span class="sxs-lookup"><span data-stu-id="4b509-358">Publish via FTP</span></span>

1. <span data-ttu-id="4b509-359">Conéctese al App Service que creó [anteriormente](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="4b509-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="4b509-360">En el explorador, vaya a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **manual de implementación**de  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="4b509-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="4b509-361">Copie las cadenas de conexión que se muestran en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="4b509-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="4b509-362">Usaremos estas cadenas para conectar con el servicio de la aplicación web y cargar archivos a través de FTP.</span><span class="sxs-lookup"><span data-stu-id="4b509-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="4b509-363">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-363">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Copiar cadenas de conexión del panel FTP":::

1. <span data-ttu-id="4b509-365">En el código base para el almacenamiento de claves, vaya al **directorio Customer-Key-store\src\customer-Key-Store**.</span><span class="sxs-lookup"><span data-stu-id="4b509-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="4b509-366">Compruebe que este directorio contiene el archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="4b509-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="4b509-367">Ejecutar: **publicación dotnet**</span><span class="sxs-lookup"><span data-stu-id="4b509-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="4b509-368">El resultado contiene el directorio en el que se ha implementado la publicación.</span><span class="sxs-lookup"><span data-stu-id="4b509-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="4b509-369">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4b509-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="4b509-370">Enviar todos los archivos del directorio de publicación a un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="4b509-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="4b509-371">Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="4b509-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="4b509-372">Desde el cliente FTP, use la información de conexión que copió para conectarse a su servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4b509-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="4b509-373">Cargue el archivo. zip que creó en el paso anterior en el directorio raíz de la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="4b509-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="4b509-374">DKE está implementado y puede desplazarse a las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="4b509-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="4b509-375">A continuación, [valide la implementación](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="4b509-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="4b509-376">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="4b509-376">Validate your deployment</span></span>

<span data-ttu-id="4b509-377">Después de implementar DKE con uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="4b509-378">Realizar</span><span class="sxs-lookup"><span data-stu-id="4b509-378">Run:</span></span>

<span data-ttu-id="4b509-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="4b509-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="4b509-380">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-380">For example:</span></span>

<span data-ttu-id="4b509-381">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="4b509-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="4b509-382">Asegúrese de que no aparecen errores en el resultado.</span><span class="sxs-lookup"><span data-stu-id="4b509-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="4b509-383">Cuando esté listo, [Registre el almacén de claves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="4b509-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="4b509-384">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="4b509-384">Register your key store</span></span>

<span data-ttu-id="4b509-385">Los siguientes pasos le permiten registrar el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="4b509-386">Registrar el almacén de claves es el último paso para implementar DKE antes de empezar a crear etiquetas.</span><span class="sxs-lookup"><span data-stu-id="4b509-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="4b509-387">Para registrar el almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="4b509-387">To register your key store:</span></span>

1. <span data-ttu-id="4b509-388">En el explorador, abra el [portal de Microsoft Azure](https://ms.portal.azure.com/)y vaya a **todos los** registros de la aplicación de \> **identidad** de servicios \> **App Registrations**.</span><span class="sxs-lookup"><span data-stu-id="4b509-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="4b509-389">Seleccione **nuevo registro**y escriba un nombre significativo.</span><span class="sxs-lookup"><span data-stu-id="4b509-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="4b509-390">Seleccione un tipo de cuenta en las opciones que se muestran.</span><span class="sxs-lookup"><span data-stu-id="4b509-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="4b509-391">Si está usando Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com**, seleccione **cuentas solo en este directorio de organización (solo para el inquilino único de Microsoft).**</span><span class="sxs-lookup"><span data-stu-id="4b509-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="4b509-392">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-392">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Nuevo registro de la aplicación":::

4. <span data-ttu-id="4b509-394">En la parte inferior de la página, seleccione **registrar** para crear el nuevo registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b509-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="4b509-395">En el registro de la nueva aplicación, en el panel izquierdo, en **administrar**, seleccione **autenticación**.</span><span class="sxs-lookup"><span data-stu-id="4b509-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="4b509-396">Seleccione **Agregar una plataforma**.</span><span class="sxs-lookup"><span data-stu-id="4b509-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="4b509-397">En el menú emergente **configurar plataformas** , seleccione **Web**.</span><span class="sxs-lookup"><span data-stu-id="4b509-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="4b509-398">En **URI de redireccionamiento**, escriba el URI del servicio de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="4b509-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="4b509-399">Escriba la dirección URL del servicio de aplicaciones, incluidos el nombre de host y el dominio.</span><span class="sxs-lookup"><span data-stu-id="4b509-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="4b509-400">Por ejemplo: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="4b509-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="4b509-401">La dirección URL que especifique debe coincidir con el nombre de host en el que se ha implementado el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="4b509-402">Si está probando localmente con Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="4b509-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="4b509-403">En todos los casos, el esquema debe ser **https**.</span><span class="sxs-lookup"><span data-stu-id="4b509-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="4b509-404">Asegúrese de que el nombre de host coincida exactamente con el nombre de host de App Service.</span><span class="sxs-lookup"><span data-stu-id="4b509-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="4b509-405">Puede que lo haya cambiado a `localhost` para solucionar los problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="4b509-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="4b509-406">En **appsettings.jsactivado**, este valor es el nombre de host que se establece para `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="4b509-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="4b509-407">En **concesión implícita**, active la casilla de verificación **tokens de identificador** .</span><span class="sxs-lookup"><span data-stu-id="4b509-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="4b509-408">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="4b509-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="4b509-409">En el panel izquierdo, seleccione **exponer una API**y, a continuación, junto a URI de identificador de aplicación, seleccione **establecer**.</span><span class="sxs-lookup"><span data-stu-id="4b509-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="4b509-410">Aún en la página **exponer una API** , en el área **ámbitos definidos por esta API** , seleccione **Agregar un ámbito**.</span><span class="sxs-lookup"><span data-stu-id="4b509-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="4b509-411">En el nuevo ámbito:</span><span class="sxs-lookup"><span data-stu-id="4b509-411">In the new scope:</span></span>

    1. <span data-ttu-id="4b509-412">Defina el nombre del ámbito como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="4b509-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="4b509-413">Seleccione a los administradores y usuarios que pueden conceder consentimiento.</span><span class="sxs-lookup"><span data-stu-id="4b509-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="4b509-414">Defina los valores restantes necesarios.</span><span class="sxs-lookup"><span data-stu-id="4b509-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="4b509-415">Seleccione **Agregar ámbito.**</span><span class="sxs-lookup"><span data-stu-id="4b509-415">Select **Add scope.**</span></span>

    <span data-ttu-id="4b509-416">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="4b509-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="4b509-417">Aún en la página **exponer una API** , en el área **aplicaciones cliente autorizadas** , seleccione **Agregar una aplicación cliente**.</span><span class="sxs-lookup"><span data-stu-id="4b509-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="4b509-418">En la nueva aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="4b509-418">In the new client application:</span></span>

    1. <span data-ttu-id="4b509-419">Defina el identificador de cliente como **d3590ed6-52b3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="4b509-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="4b509-420">Este valor es el identificador del cliente de Microsoft Office y permite a Office obtener un token de acceso para su almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="4b509-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="4b509-421">En **ámbitos autorizados**, seleccione el ámbito de la **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="4b509-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="4b509-422">Seleccione **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4b509-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="4b509-423">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="4b509-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="4b509-424">El almacén de claves de DKE está registrado.</span><span class="sxs-lookup"><span data-stu-id="4b509-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="4b509-425">Para continuar, [cree etiquetas con DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="4b509-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="4b509-426">Crear etiquetas con DKE</span><span class="sxs-lookup"><span data-stu-id="4b509-426">Create labels using DKE</span></span>

<span data-ttu-id="4b509-427">En el centro de cumplimiento de Microsoft 365, cree una nueva etiqueta de confidencialidad y aplique el cifrado como lo haría en otro caso.</span><span class="sxs-lookup"><span data-stu-id="4b509-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="4b509-428">Seleccione **usar cifrado doble de clave** y escriba la dirección URL del punto de conexión para la clave.</span><span class="sxs-lookup"><span data-stu-id="4b509-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="4b509-429">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4b509-429">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Seleccione usar el cifrado de doble clave en el centro de cumplimiento de Microsoft 365":::

<span data-ttu-id="4b509-431">Las etiquetas de DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de las aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="4b509-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="4b509-432">Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="4b509-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="4b509-433">Habilitar DKE en el cliente</span><span class="sxs-lookup"><span data-stu-id="4b509-433">Enable DKE in your client</span></span>

<span data-ttu-id="4b509-434">Para habilitar DKE para el cliente, agregue las siguientes claves del registro:</span><span class="sxs-lookup"><span data-stu-id="4b509-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
