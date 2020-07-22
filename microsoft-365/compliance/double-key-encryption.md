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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201776"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="a852f-103">Cifrado de doble clave (DKE)</span><span class="sxs-lookup"><span data-stu-id="a852f-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="a852f-104">*Se aplica a: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="a852f-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="a852f-105">*Instrucciones para: [cliente de etiquetado Unificado de Azure Information Protection para Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="a852f-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="a852f-106">*Descripción del servicio para: [cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="a852f-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="a852f-107">Esta versión preliminar pública de cifrado de doble clave (DKE) permite usar el cliente de etiquetado Unificado de Azure Information Protection para proteger el contenido altamente confidencial, a la vez que mantiene el control total de la clave.</span><span class="sxs-lookup"><span data-stu-id="a852f-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="a852f-108">El cifrado de doble clave requiere dos claves, que se usan juntas, para obtener acceso al contenido protegido.</span><span class="sxs-lookup"><span data-stu-id="a852f-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="a852f-109">Se almacena una clave en Microsoft Azure y se mantiene la otra clave.</span><span class="sxs-lookup"><span data-stu-id="a852f-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="a852f-110">El cifrado de doble clave admite tanto la nube como las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="a852f-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="a852f-111">Estas implementaciones ayudan a garantizar que los datos cifrados permanezcan opacos dondequiera que almacene los datos protegidos.</span><span class="sxs-lookup"><span data-stu-id="a852f-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="a852f-112">Para obtener más información acerca de las claves predeterminadas de raíz de inquilino basadas en la nube, vea [Planning and Implementing Your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="a852f-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="a852f-113">El cifrado de doble clave es similar a un cuadro de depósito de seguridad que requiere una clave de banco y una clave de cliente para obtener acceso.</span><span class="sxs-lookup"><span data-stu-id="a852f-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="a852f-114">Para descifrar el contenido protegido, debe usar la clave administrada de Microsoft y la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="a852f-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="a852f-115">En el siguiente vídeo se muestra cómo funciona el cifrado doble de claves para proteger el contenido.</span><span class="sxs-lookup"><span data-stu-id="a852f-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="a852f-116">Si las organizaciones tienen alguno de los siguientes requisitos, puede usar DKE para ayudar a proteger el contenido:</span><span class="sxs-lookup"><span data-stu-id="a852f-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="a852f-117">Desea asegurarse de que *solo usted* puede descifrar el contenido protegido en todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="a852f-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="a852f-118">No desea que Microsoft tenga acceso a datos protegidos por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="a852f-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="a852f-119">Tiene requisitos normativos para mantener las claves dentro de un límite geográfico.</span><span class="sxs-lookup"><span data-stu-id="a852f-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="a852f-120">Todas las claves de clientes para el cifrado y el descifrado de datos se mantienen en su centro de datos.</span><span class="sxs-lookup"><span data-stu-id="a852f-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="a852f-121">Requisitos de licencia y sistema para DKE</span><span class="sxs-lookup"><span data-stu-id="a852f-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="a852f-122">Esta versión preliminar pública de cifrado de doble clave para Microsoft 365 está disponible como parte de Microsoft 365 E5 y Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a852f-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="a852f-123">Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="a852f-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="a852f-124">Para obtener más información acerca de estas licencias, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="a852f-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="a852f-125">**Office Insider** Para usar la versión preliminar pública, debe ser miembro del programa Office Insider.</span><span class="sxs-lookup"><span data-stu-id="a852f-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="a852f-126">Para unirse a Office Insider, vaya a [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="a852f-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="a852f-127">Una vez que sea miembro, prepare el entorno para implementar las compilaciones de Office Insider eligiendo el método de implementación adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="a852f-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="a852f-128">Para obtener instrucciones, consulte [Introducción a la implementación de compilaciones de Office Insider](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="a852f-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="a852f-129">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="a852f-129">**Azure Information Protection**.</span></span> <span data-ttu-id="a852f-130">DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="a852f-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="a852f-131">Entornos admitidos para almacenar y ver contenido protegido por DKE</span><span class="sxs-lookup"><span data-stu-id="a852f-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="a852f-132">**Aplicaciones compatibles**.</span><span class="sxs-lookup"><span data-stu-id="a852f-132">**Supported applications**.</span></span> <span data-ttu-id="a852f-133">[Microsoft 365 apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients in Windows, incluidos Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="a852f-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="a852f-134">**Soporte de contenido en línea**.</span><span class="sxs-lookup"><span data-stu-id="a852f-134">**Online content support**.</span></span> <span data-ttu-id="a852f-135">Se admiten los documentos y archivos almacenados en línea tanto en Microsoft SharePoint como en OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="a852f-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="a852f-136">Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos cifrados y archivos en línea.</span><span class="sxs-lookup"><span data-stu-id="a852f-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="a852f-137">En su lugar, debe ver el contenido protegido con las aplicaciones de escritorio en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="a852f-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="a852f-138">Acerca de este artículo de la versión preliminar pública</span><span class="sxs-lookup"><span data-stu-id="a852f-138">About this public preview article</span></span>

<span data-ttu-id="a852f-139">Hay varias formas de realizar algunos de los pasos para implementar el cifrado doble de claves.</span><span class="sxs-lookup"><span data-stu-id="a852f-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="a852f-140">En este artículo se proporcionan instrucciones detalladas para que los administradores menos experimentados implementen correctamente el servicio.</span><span class="sxs-lookup"><span data-stu-id="a852f-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="a852f-141">Si tiene experiencia con las tecnologías comunes, como GIT, compartidas por los métodos de implementación descritos en este artículo, puede optar por usar sus propios métodos.</span><span class="sxs-lookup"><span data-stu-id="a852f-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="a852f-142">Para la versión preliminar pública, hemos incluido instrucciones paso a paso sobre cómo implementar el servicio de cifrado de doble clave en Azure.</span><span class="sxs-lookup"><span data-stu-id="a852f-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="a852f-143">Este escenario no es algo que probablemente haría en producción.</span><span class="sxs-lookup"><span data-stu-id="a852f-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="a852f-144">Para la versión preliminar pública, el uso de Azure es una forma rápida de implementar que le permite empezar a usar el cifrado de doble clave inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a852f-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="a852f-145">Puede optar por implementar el servicio siempre que lo desee, ya sea de forma local en la red o con otro proveedor.</span><span class="sxs-lookup"><span data-stu-id="a852f-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="a852f-146">Deberá publicar el almacén de claves con los métodos apropiados para esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="a852f-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="a852f-147">Implementar el cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="a852f-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="a852f-148">Deberá seguir estos pasos generales para configurar el cifrado de doble clave para su organización.</span><span class="sxs-lookup"><span data-stu-id="a852f-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="a852f-149">El ejemplo de este artículo usa Azure como destino de implementación para el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="a852f-150">Si va a realizar la implementación en otra ubicación, deberá proporcionar sus propios valores.</span><span class="sxs-lookup"><span data-stu-id="a852f-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="a852f-151">Requisitos previos de instalación de software</span><span class="sxs-lookup"><span data-stu-id="a852f-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="a852f-152">Clone el repositorio de GitHub con cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="a852f-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="a852f-153">Modificación de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a852f-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="a852f-154">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="a852f-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="a852f-155">Compilar el proyecto</span><span class="sxs-lookup"><span data-stu-id="a852f-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="a852f-156">Publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="a852f-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="a852f-157">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="a852f-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="a852f-158">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="a852f-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="a852f-159">Cree etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="a852f-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="a852f-160">Cuando haya terminado, puede cifrar documentos y archivos con DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="a852f-161">Para obtener más información, consulte [aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="a852f-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="a852f-162">Requisitos previos de instalación de software</span><span class="sxs-lookup"><span data-stu-id="a852f-162">Install software prerequisites</span></span>

<span data-ttu-id="a852f-163">Existen dos tipos de requisitos previos de software para el cifrado doble de claves</span><span class="sxs-lookup"><span data-stu-id="a852f-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="a852f-164">Requisitos previos del servicio de cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="a852f-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="a852f-165">Requisitos previos de cifrado de doble clave para equipos cliente</span><span class="sxs-lookup"><span data-stu-id="a852f-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="a852f-166">Requisitos previos del servicio de cifrado de doble clave</span><span class="sxs-lookup"><span data-stu-id="a852f-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="a852f-167">Instale estos requisitos previos en el equipo en el que desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="a852f-168">**SDK .net Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="a852f-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="a852f-169">Descargue e instale el SDK desde [download .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="a852f-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="a852f-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="a852f-170">**Visual Studio Code**.</span></span> <span data-ttu-id="a852f-171">Descargue Visual Studio Code desde [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="a852f-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="a852f-172">Una vez instalado, ejecute Visual Studio Code y seleccione **Ver** \> **extensiones**.</span><span class="sxs-lookup"><span data-stu-id="a852f-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="a852f-173">Instale estas extensiones.</span><span class="sxs-lookup"><span data-stu-id="a852f-173">Install these extensions.</span></span>

- <span data-ttu-id="a852f-174">C# para Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a852f-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="a852f-175">Administrador de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="a852f-175">NuGet Package Manager</span></span>

<span data-ttu-id="a852f-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="a852f-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="a852f-177">Configure al menos un [método de implementación](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="a852f-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="a852f-178">**Recursos git**.</span><span class="sxs-lookup"><span data-stu-id="a852f-178">**Git resources**.</span></span> <span data-ttu-id="a852f-179">Descargue e instale uno de los siguientes elementos.</span><span class="sxs-lookup"><span data-stu-id="a852f-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="a852f-180">Git</span><span class="sxs-lookup"><span data-stu-id="a852f-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="a852f-181">Escritorio de GitHub</span><span class="sxs-lookup"><span data-stu-id="a852f-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="a852f-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="a852f-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="a852f-183">**OpenSSL** Debe tener instalado [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) para [generar las claves de prueba](#generate-test-keys) después de implementar DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="a852f-184">Asegúrese de que está invocando correctamente desde la ruta de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="a852f-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="a852f-185">Por ejemplo, consulte "agregar el directorio de instalación a la ruta de acceso" en https://www.osradar.com/install-openssl-windows/ para más detalles.</span><span class="sxs-lookup"><span data-stu-id="a852f-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="a852f-186">Requisitos previos de cifrado de doble clave para equipos cliente</span><span class="sxs-lookup"><span data-stu-id="a852f-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="a852f-187">Instale estos requisitos previos en cada equipo cliente donde quiera proteger y consumir documentos protegidos.</span><span class="sxs-lookup"><span data-stu-id="a852f-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="a852f-188">**Microsoft Office** versión \*. 12711 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a852f-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="a852f-189">**Azure Information Protection el cliente de etiquetado unificado** versiones 2.7.93.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a852f-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="a852f-190">Descargue e instale el cliente de etiquetado Unificado de [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="a852f-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="a852f-191">Clonar el repositorio de GitHub DKE</span><span class="sxs-lookup"><span data-stu-id="a852f-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="a852f-192">Microsoft proporciona los archivos de origen de DKE en un repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a852f-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="a852f-193">Clonar el repositorio para compilar el proyecto de forma local para el uso de su organización.</span><span class="sxs-lookup"><span data-stu-id="a852f-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="a852f-194">El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="a852f-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="a852f-195">Las siguientes instrucciones están destinadas a usuarios no con experiencia de Git o Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="a852f-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="a852f-196">En el explorador, vaya a:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="a852f-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="a852f-197">Hacia el lado derecho de la pantalla, seleccione **código**.</span><span class="sxs-lookup"><span data-stu-id="a852f-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="a852f-198">Es posible que la versión de la interfaz de usuario muestre un botón **clonar o descargar** .</span><span class="sxs-lookup"><span data-stu-id="a852f-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="a852f-199">A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="a852f-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="a852f-200">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Clone el repositorio del servicio de cifrado de doble clave desde GitHub":::

3. <span data-ttu-id="a852f-202">En Visual Studio Code, seleccione **Ver** \> **paleta de comandos** y seleccione **git: clon**.</span><span class="sxs-lookup"><span data-stu-id="a852f-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="a852f-203">Para ir a la opción de la lista, empiece a escribir `git: clone` para filtrar las entradas y, a continuación, selecciónela en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a852f-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="a852f-204">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Opción de Visual Studio Code GIT: Clone":::

4. <span data-ttu-id="a852f-206">En el cuadro de texto, pegue la dirección URL que copió desde git y seleccione **clonar desde GitHub**.</span><span class="sxs-lookup"><span data-stu-id="a852f-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="a852f-207">En el cuadro de diálogo **Seleccionar carpeta** que aparece, busque y seleccione una ubicación para almacenar el repositorio.</span><span class="sxs-lookup"><span data-stu-id="a852f-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="a852f-208">En el símbolo del sistema, seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="a852f-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="a852f-209">El repositorio se abre en Visual Studio Code y muestra la rama git actual en la parte inferior izquierda.</span><span class="sxs-lookup"><span data-stu-id="a852f-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="a852f-210">La rama actual debe ser **maestra**.</span><span class="sxs-lookup"><span data-stu-id="a852f-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="a852f-211">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Rama de patrón de Visual Studio Code":::

6. <span data-ttu-id="a852f-213">Seleccione el **patrón** de palabras y, a continuación, seleccione **public_preview** de la lista de ramas.</span><span class="sxs-lookup"><span data-stu-id="a852f-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="a852f-214">Al seleccionar la rama public_preview, se asegura de que tiene los archivos correctos para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a852f-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="a852f-215">Si no elige la rama correcta, se producirá un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="a852f-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="a852f-216">Ahora tiene su repositorio de origen de DKE configurado de forma local.</span><span class="sxs-lookup"><span data-stu-id="a852f-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="a852f-217">A continuación, [modifique la configuración](#modify-application-settings) de la aplicación para su organización.</span><span class="sxs-lookup"><span data-stu-id="a852f-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="a852f-218">Modificación de la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a852f-218">Modify application settings</span></span>

<span data-ttu-id="a852f-219">Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de aplicación:</span><span class="sxs-lookup"><span data-stu-id="a852f-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="a852f-220">Configuración de acceso a claves</span><span class="sxs-lookup"><span data-stu-id="a852f-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="a852f-221">Configuración de inquilinos y claves</span><span class="sxs-lookup"><span data-stu-id="a852f-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="a852f-222">Modifique la configuración de la aplicación en el appsettings.jsarchivo.</span><span class="sxs-lookup"><span data-stu-id="a852f-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="a852f-223">Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="a852f-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="a852f-224">Por ejemplo, en Visual Studio Code, puede desplazarse hasta el archivo como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="a852f-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Buscar el appsettings.jsen el archivo para DKE.":::

#### <a name="key-access-settings"></a><span data-ttu-id="a852f-226">Configuración de acceso a claves</span><span class="sxs-lookup"><span data-stu-id="a852f-226">Key access settings</span></span>

<span data-ttu-id="a852f-227">Elija si desea usar el correo electrónico o la autorización de roles.</span><span class="sxs-lookup"><span data-stu-id="a852f-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="a852f-228">DKE solo admite uno de estos métodos de autenticación a la vez.</span><span class="sxs-lookup"><span data-stu-id="a852f-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="a852f-229">**Autorización de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="a852f-229">**Email authorization**.</span></span> <span data-ttu-id="a852f-230">Permite a su organización autorizar el acceso a claves basadas solo en direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a852f-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="a852f-231">**Autorización de roles**.</span><span class="sxs-lookup"><span data-stu-id="a852f-231">**Role authorization**.</span></span> <span data-ttu-id="a852f-232">Permite a su organización autorizar el acceso a las claves en función de los grupos de Active Directory y requiere que el servicio Web pueda consultar LDAP.</span><span class="sxs-lookup"><span data-stu-id="a852f-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="a852f-233">Para establecer la configuración de acceso clave para DKE:</span><span class="sxs-lookup"><span data-stu-id="a852f-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="a852f-234">En el **appsettings.js** del archivo, defina solo una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="a852f-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="a852f-235">Para la autorización de correo electrónico, busque la opción **AuthorizedEmailAddresses** .</span><span class="sxs-lookup"><span data-stu-id="a852f-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="a852f-236">Agregue la dirección de correo electrónico que quiera autorizar.</span><span class="sxs-lookup"><span data-stu-id="a852f-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="a852f-237">Separe varias direcciones de correo electrónico con comillas dobles y comas.</span><span class="sxs-lookup"><span data-stu-id="a852f-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="a852f-238">Por ejemplo: **"' AuthorizedEmailAddresses '": ["email1@company.com", "email2@company.com", email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="a852f-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="appsettings.jsen archivo que muestra el método de autorización de correo electrónico":::

   - <span data-ttu-id="a852f-240">Para la autorización de roles, busque la opción **AuthorizedRoles** .</span><span class="sxs-lookup"><span data-stu-id="a852f-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="a852f-241">Defina con los nombres de los grupos de ActiveDirectory que desea autorizar.</span><span class="sxs-lookup"><span data-stu-id="a852f-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="a852f-242">Por ejemplo: **"AuthorizedRoles": ["Grupo1", "grupo2", "Group3"]**</span><span class="sxs-lookup"><span data-stu-id="a852f-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsen el archivo que muestra el método de autorización de roles":::

2. <span data-ttu-id="a852f-244">Quite la configuración que no sea relevante para el método de autorización elegido.</span><span class="sxs-lookup"><span data-stu-id="a852f-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="a852f-245">Configuración de inquilinos y claves</span><span class="sxs-lookup"><span data-stu-id="a852f-245">Tenant and key settings</span></span>

<span data-ttu-id="a852f-246">La configuración de clave y de inquilino de DKE se encuentra en la **appsettings.jsen** el archivo y en el archivo **Startup.CS** .</span><span class="sxs-lookup"><span data-stu-id="a852f-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="a852f-247">En el **appsettings.js** del archivo, modifique los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a852f-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="a852f-248">**ValidIssuers**.</span><span class="sxs-lookup"><span data-stu-id="a852f-248">**ValidIssuers**.</span></span> <span data-ttu-id="a852f-249">Reemplace `<tenantid>` por el GUID del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a852f-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="a852f-250">**JwtAudience**.</span><span class="sxs-lookup"><span data-stu-id="a852f-250">**JwtAudience**.</span></span> <span data-ttu-id="a852f-251">Reemplace `<yourhostname>` por el nombre de host del equipo en el que se ejecutará el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="a852f-252">El valor de JwtAudience debe coincidir *exactamente*con el nombre de su host.</span><span class="sxs-lookup"><span data-stu-id="a852f-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="a852f-253">Puede usar **localhost: 5000** durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="a852f-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="a852f-254">Sin embargo, cuando haya terminado la depuración, asegúrese de actualizar este valor al nombre de host del servidor.</span><span class="sxs-lookup"><span data-stu-id="a852f-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="a852f-255">**LDAPPath**.</span><span class="sxs-lookup"><span data-stu-id="a852f-255">**LDAPPath**.</span></span> <span data-ttu-id="a852f-256">Establezca el valor de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a852f-256">Set the value as follows:</span></span>

  - <span data-ttu-id="a852f-257">Si está usando la autorización de roles, escriba el dominio LDAP.</span><span class="sxs-lookup"><span data-stu-id="a852f-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="a852f-258">Si está usando autorización de correo electrónico, deje este valor vacío.</span><span class="sxs-lookup"><span data-stu-id="a852f-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="a852f-259">Para obtener más información, consulte [configuración de acceso clave](#key-access-settings).</span><span class="sxs-lookup"><span data-stu-id="a852f-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="a852f-260">**TestKeys: nombre**.</span><span class="sxs-lookup"><span data-stu-id="a852f-260">**TestKeys:Name**.</span></span> <span data-ttu-id="a852f-261">Escriba un nombre para la clave.</span><span class="sxs-lookup"><span data-stu-id="a852f-261">Enter a name for your key.</span></span> <span data-ttu-id="a852f-262">Ejemplo: **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="a852f-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="a852f-263">**TestKeys: ID**. Cree un GUID y escríbalo como el valor **TestKeys: ID** .</span><span class="sxs-lookup"><span data-stu-id="a852f-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="a852f-264">Por ejemplo, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span><span class="sxs-lookup"><span data-stu-id="a852f-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="a852f-265">Puede usar un sitio como el [generador de GUID en línea](https://guidgenerator.com/) para generar un GUID de forma aleatoria.</span><span class="sxs-lookup"><span data-stu-id="a852f-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="a852f-266">Generar claves de prueba</span><span class="sxs-lookup"><span data-stu-id="a852f-266">Generate test keys</span></span>

<span data-ttu-id="a852f-267">Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.</span><span class="sxs-lookup"><span data-stu-id="a852f-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="a852f-268">Para generar claves:</span><span class="sxs-lookup"><span data-stu-id="a852f-268">To generate keys:</span></span>

1. <span data-ttu-id="a852f-269">En el menú Inicio de Windows, ejecute el símbolo del sistema de OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="a852f-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="a852f-270">Cambie a la carpeta en la que desea guardar las claves de prueba.</span><span class="sxs-lookup"><span data-stu-id="a852f-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="a852f-271">Los archivos que crea al completar los pasos de esta tarea se almacenan en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="a852f-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="a852f-272">Generar la nueva clave de prueba.</span><span class="sxs-lookup"><span data-stu-id="a852f-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="a852f-273">Generar la clave privada.</span><span class="sxs-lookup"><span data-stu-id="a852f-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="a852f-274">Generar la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a852f-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="a852f-275">En un editor de texto, Abra **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="a852f-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="a852f-276">Copie todo el contenido del archivo **pubkeyonly. pem** , excepto la primera y la última línea, en la sección **PublicPem** de la **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="a852f-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="a852f-277">En un editor de texto, Abra **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="a852f-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="a852f-278">Copie todo el contenido del archivo **privkeynopass. pem** , excepto la primera y la última línea, en la sección **PrivatePem** de la **appsettings.jsen** el archivo.</span><span class="sxs-lookup"><span data-stu-id="a852f-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="a852f-279">Quite todos los espacios en blanco y las nuevas líneas en las secciones **PublicPem** y **PrivatePem** .</span><span class="sxs-lookup"><span data-stu-id="a852f-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a852f-280">Cuando copie este contenido, no elimine ninguno de los datos del PEM.</span><span class="sxs-lookup"><span data-stu-id="a852f-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="a852f-281">Abra el archivo **Startup.CS** y busque las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="a852f-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="a852f-282">Reemplace estas líneas con el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="a852f-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="a852f-283">Los resultados finales deben parecerse a la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="a852f-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="archivo startup.cs para la versión preliminar pública":::

<span data-ttu-id="a852f-285">Ahora está listo para [compilar el proyecto DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="a852f-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="a852f-286">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a852f-286">Build the project</span></span>

<span data-ttu-id="a852f-287">Use las siguientes instrucciones para crear el proyecto DKE de forma local:</span><span class="sxs-lookup"><span data-stu-id="a852f-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="a852f-288">En Visual Studio Code, en el repositorio del servicio DKE, seleccione **Ver** \> **paleta de comandos** y, a continuación, escriba **generar** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a852f-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="a852f-289">En la lista, elija **tareas: Ejecutar tarea de compilación**.</span><span class="sxs-lookup"><span data-stu-id="a852f-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="a852f-290">Si no se encuentra ninguna tarea de compilación, seleccione **Configurar tarea de compilación** y cree una para .net Core de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="a852f-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Configurar la tarea de compilación que falta para .NET":::

   1. <span data-ttu-id="a852f-292">Elija **crear tasks.jsen a partir de plantilla**.</span><span class="sxs-lookup"><span data-stu-id="a852f-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Crear tasks.jsen archivo de plantilla para DKE":::

   2. <span data-ttu-id="a852f-294">En la lista de tipos de plantilla, seleccione **.net Core**.</span><span class="sxs-lookup"><span data-stu-id="a852f-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Crear tasks.jsen archivo de plantilla para DKE":::

   3. <span data-ttu-id="a852f-296">En la sección generar, busque la ruta de acceso al archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="a852f-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="a852f-297">Si no está ahí, agregue la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="a852f-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="a852f-298">Vuelva a ejecutar la compilación.</span><span class="sxs-lookup"><span data-stu-id="a852f-298">Run the build again.</span></span>

1. <span data-ttu-id="a852f-299">Compruebe que no haya errores rojos en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="a852f-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="a852f-300">Si hay errores rojos, compruebe el resultado de la consola.</span><span class="sxs-lookup"><span data-stu-id="a852f-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="a852f-301">Asegúrese de que ha completado todos los pasos anteriores correctamente y de que las versiones de compilación correctas están presentes.</span><span class="sxs-lookup"><span data-stu-id="a852f-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="a852f-302">**Ejecutar** \> **Inicie la depuración** para depurar el proceso.</span><span class="sxs-lookup"><span data-stu-id="a852f-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="a852f-303">Si se le pide que seleccione un entorno, seleccione **.net Core**.</span><span class="sxs-lookup"><span data-stu-id="a852f-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="a852f-304">El depurador de .NET Core se inicia normalmente en **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="a852f-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="a852f-305">Para ver la clave de prueba, vaya a **https://localhost:5001** y agregue una barra diagonal (/) y el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="a852f-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="a852f-306">Por ejemplo:**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="a852f-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="a852f-307">La clave debe mostrarse en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="a852f-307">The key should display in JSON format.</span></span>

<span data-ttu-id="a852f-308">La configuración se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a852f-308">Your setup is now complete.</span></span> <span data-ttu-id="a852f-309">Antes de publicar el almacén de claves, en appsettings.jsen la configuración de JwtAudience, asegúrese de que el valor para hostname coincide exactamente con el nombre de host del servicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a852f-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="a852f-310">Puede que lo haya cambiado a localhost para solucionar los problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a852f-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="a852f-311">Publicar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="a852f-311">Publish the key store</span></span>

<span data-ttu-id="a852f-312">En los siguientes pasos se describe cómo crear una instancia de Azure App Service para hospedar la implementación de DKE y cómo publicar las claves generadas en Azure.</span><span class="sxs-lookup"><span data-stu-id="a852f-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="a852f-313">Para crear una instancia de la aplicación Web de Azure para hospedar la implementación de DKE:</span><span class="sxs-lookup"><span data-stu-id="a852f-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="a852f-314">En el explorador, inicie sesión en el [portal de Microsoft Azure](https://ms.portal.azure.com)y vaya a **App Services**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="a852f-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="a852f-315">Seleccione su suscripción y grupo de recursos y defina los detalles de la instancia.</span><span class="sxs-lookup"><span data-stu-id="a852f-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="a852f-316">Escriba el nombre de host del equipo en el que desea instalar el servicio DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="a852f-317">Asegúrese de que es el mismo nombre que el definido para la configuración JwtAudience en el [**appsettings.jsen**](#tenant-and-key-settings) el archivo.</span><span class="sxs-lookup"><span data-stu-id="a852f-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="a852f-318">El valor que se proporciona para el nombre también es WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="a852f-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="a852f-319">Para **publicar**, seleccionar **código**y, para **pila en tiempo de ejecución**, seleccione **.net Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="a852f-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="a852f-320">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Agregar el servicio de aplicaciones":::

1. <span data-ttu-id="a852f-322">En la parte inferior de la página, seleccione **revisar + crear**y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a852f-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="a852f-323">Realice una de las siguientes acciones para publicar las claves generadas en Azure:</span><span class="sxs-lookup"><span data-stu-id="a852f-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="a852f-324">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="a852f-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="a852f-325">Publicar mediante FTP</span><span class="sxs-lookup"><span data-stu-id="a852f-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="a852f-326">Publicar a través de Visual Studio 2019 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="a852f-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="a852f-327">Publicar en un sistema local</span><span class="sxs-lookup"><span data-stu-id="a852f-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="a852f-328">Puede que prefiera otros métodos para implementar las claves.</span><span class="sxs-lookup"><span data-stu-id="a852f-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="a852f-329">Seleccione el método que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="a852f-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="a852f-330">La [publicación a través de Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) y a un [sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) se describe en la [documentación de ASP .net](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="a852f-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="a852f-331">Si usa uno de estos métodos, abra las instrucciones en una pestaña independiente para que pueda volver fácilmente cuando termine.</span><span class="sxs-lookup"><span data-stu-id="a852f-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="a852f-332">Publicar a través de ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="a852f-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="a852f-333">Vaya a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="a852f-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="a852f-334">Por ejemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="a852f-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="a852f-335">En el código base del almacén de claves, vaya a la carpeta **Customer-Key-store\src\customer-Key-Store** y compruebe que esta carpeta contiene el archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="a852f-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="a852f-336">Ejecutar: **publicación dotnet**</span><span class="sxs-lookup"><span data-stu-id="a852f-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="a852f-337">La ventana resultados muestra el directorio en el que se ha implementado la publicación.</span><span class="sxs-lookup"><span data-stu-id="a852f-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="a852f-338">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="a852f-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="a852f-339">Enviar todos los archivos del directorio de publicación a un archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="a852f-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="a852f-340">Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="a852f-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="a852f-341">Arrastre y coloque el archivo. zip que ha creado en el sitio de ZipDeployUI que ha abierto anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a852f-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="a852f-342">Por ejemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="a852f-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="a852f-343">DKE está implementado y puede ir a las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="a852f-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="a852f-344">Siga [validando la implementación](#validate-your-deployment) a continuación.</span><span class="sxs-lookup"><span data-stu-id="a852f-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="a852f-345">Publicar mediante FTP</span><span class="sxs-lookup"><span data-stu-id="a852f-345">Publish via FTP</span></span>

1. <span data-ttu-id="a852f-346">Conéctese al App Service que creó [anteriormente](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="a852f-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="a852f-347">En el explorador, vaya a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **manual de implementación**de  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="a852f-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="a852f-348">Copie las cadenas de conexión que se muestran en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="a852f-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="a852f-349">Usaremos estas cadenas para conectar con el servicio de la aplicación web y cargar archivos a través de FTP.</span><span class="sxs-lookup"><span data-stu-id="a852f-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="a852f-350">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Copiar cadenas de conexión del panel FTP":::

1. <span data-ttu-id="a852f-352">En el código base para el almacenamiento de claves, vaya al **directorio Customer-Key-store\src\customer-Key-Store**.</span><span class="sxs-lookup"><span data-stu-id="a852f-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="a852f-353">Compruebe que este directorio contiene el archivo **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="a852f-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="a852f-354">Ejecutar: **publicación dotnet**</span><span class="sxs-lookup"><span data-stu-id="a852f-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="a852f-355">El resultado contiene el directorio en el que se ha implementado la publicación.</span><span class="sxs-lookup"><span data-stu-id="a852f-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="a852f-356">Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="a852f-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="a852f-357">Enviar todos los archivos del directorio de publicación a un archivo zip.</span><span class="sxs-lookup"><span data-stu-id="a852f-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="a852f-358">Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="a852f-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="a852f-359">Desde el cliente FTP, use la información de conexión que copió para conectarse a su servicio de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a852f-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="a852f-360">Cargue el archivo. zip que creó en el paso anterior en el directorio raíz de la aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="a852f-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="a852f-361">DKE está implementado y puede desplazarse a las claves de prueba que ha creado.</span><span class="sxs-lookup"><span data-stu-id="a852f-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="a852f-362">A continuación, [valide la implementación](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="a852f-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="a852f-363">Validar la implementación</span><span class="sxs-lookup"><span data-stu-id="a852f-363">Validate your deployment</span></span>

<span data-ttu-id="a852f-364">Después de implementar DKE con uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="a852f-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="a852f-365">Realizar</span><span class="sxs-lookup"><span data-stu-id="a852f-365">Run:</span></span>

<span data-ttu-id="a852f-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="a852f-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="a852f-367">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-367">For example:</span></span>

<span data-ttu-id="a852f-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="a852f-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="a852f-369">Asegúrese de que no aparecen errores en el resultado.</span><span class="sxs-lookup"><span data-stu-id="a852f-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="a852f-370">Cuando esté listo, [Registre el almacén de claves](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="a852f-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="a852f-371">Registrar el almacén de claves</span><span class="sxs-lookup"><span data-stu-id="a852f-371">Register your key store</span></span>

<span data-ttu-id="a852f-372">Los siguientes pasos le permiten registrar el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="a852f-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="a852f-373">Registrar el almacén de claves es el último paso para implementar DKE antes de empezar a crear etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a852f-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="a852f-374">Para registrar el almacén de claves:</span><span class="sxs-lookup"><span data-stu-id="a852f-374">To register your key store:</span></span>

1. <span data-ttu-id="a852f-375">En el explorador, abra el [portal de Microsoft Azure](https://ms.portal.azure.com/)y vaya a **todos los** registros de la aplicación de \> **identidad** de servicios \> **App Registrations**.</span><span class="sxs-lookup"><span data-stu-id="a852f-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="a852f-376">Seleccione **nuevo registro**y escriba un nombre significativo.</span><span class="sxs-lookup"><span data-stu-id="a852f-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="a852f-377">Seleccione un tipo de cuenta en las opciones que se muestran.</span><span class="sxs-lookup"><span data-stu-id="a852f-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="a852f-378">Si está usando Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com**, seleccione **cuentas solo en este directorio de organización (solo para el inquilino único de Microsoft).**</span><span class="sxs-lookup"><span data-stu-id="a852f-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="a852f-379">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Nuevo registro de la aplicación":::

4. <span data-ttu-id="a852f-381">En la parte inferior de la página, seleccione **registrar** para crear el nuevo registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a852f-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="a852f-382">En el registro de la nueva aplicación, en el panel izquierdo, en **administrar**, seleccione **autenticación**.</span><span class="sxs-lookup"><span data-stu-id="a852f-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="a852f-383">Seleccione **Agregar una plataforma**.</span><span class="sxs-lookup"><span data-stu-id="a852f-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="a852f-384">En el menú emergente **configurar plataformas** , seleccione **Web**.</span><span class="sxs-lookup"><span data-stu-id="a852f-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="a852f-385">En **URI de redireccionamiento** , escriba el URI del servicio de cifrado de doble clave.</span><span class="sxs-lookup"><span data-stu-id="a852f-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="a852f-386">Escriba la dirección URL del servicio de aplicaciones, incluidos el nombre de host y el dominio.</span><span class="sxs-lookup"><span data-stu-id="a852f-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="a852f-387">Por ejemplo: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="a852f-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="a852f-388">La dirección URL que especifique debe coincidir con el nombre de host en el que se ha implementado el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="a852f-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="a852f-389">Si está probando localmente con Visual Studio, use **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="a852f-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="a852f-390">En todos los casos, el esquema debe ser **https**.</span><span class="sxs-lookup"><span data-stu-id="a852f-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="a852f-391">Asegúrese de que el nombre de host coincida exactamente con el nombre de host de App Service.</span><span class="sxs-lookup"><span data-stu-id="a852f-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="a852f-392">Puede que lo haya cambiado a localhost para solucionar los problemas de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a852f-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="a852f-393">En appsettings.jsen, este es el nombre de host que identificó como valor para la configuración de JwtAudience.</span><span class="sxs-lookup"><span data-stu-id="a852f-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="a852f-394">En **concesión implícita**, active la casilla de verificación **tokens de identificador** .</span><span class="sxs-lookup"><span data-stu-id="a852f-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="a852f-395">Seleccione **Guardar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a852f-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="a852f-396">En el panel izquierdo, seleccione **exponer una API**y, a continuación, junto a URI de identificador de aplicación, seleccione **establecer**.</span><span class="sxs-lookup"><span data-stu-id="a852f-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="a852f-397">Aún en la página **exponer una API** , en el área **ámbitos definidos por esta API** , seleccione **Agregar un ámbito**.</span><span class="sxs-lookup"><span data-stu-id="a852f-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="a852f-398">En el nuevo ámbito:</span><span class="sxs-lookup"><span data-stu-id="a852f-398">In the new scope:</span></span>

    1. <span data-ttu-id="a852f-399">Defina el nombre del ámbito como **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="a852f-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="a852f-400">Seleccione a los administradores y usuarios que pueden conceder consentimiento.</span><span class="sxs-lookup"><span data-stu-id="a852f-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="a852f-401">Defina los valores restantes necesarios.</span><span class="sxs-lookup"><span data-stu-id="a852f-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="a852f-402">Seleccione **Agregar ámbito.**</span><span class="sxs-lookup"><span data-stu-id="a852f-402">Select **Add scope.**</span></span>

    <span data-ttu-id="a852f-403">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a852f-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="a852f-404">Aún en la página **exponer una API** , en el área **aplicaciones cliente autorizadas** , seleccione **Agregar una aplicación cliente**.</span><span class="sxs-lookup"><span data-stu-id="a852f-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="a852f-405">En la nueva aplicación cliente:</span><span class="sxs-lookup"><span data-stu-id="a852f-405">In the new client application:</span></span>

    1. <span data-ttu-id="a852f-406">Defina el identificador de cliente como **d3590ed6-52b3-4102-AEFF-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="a852f-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="a852f-407">Este valor es el identificador del cliente de Microsoft Office y permite a Office obtener un token de acceso para su almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="a852f-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="a852f-408">En **ámbitos autorizados**, seleccione el ámbito de la **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="a852f-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="a852f-409">Seleccione **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a852f-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="a852f-410">Seleccione **Guardar** en la parte superior para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="a852f-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="a852f-411">El almacén de claves de DKE está registrado.</span><span class="sxs-lookup"><span data-stu-id="a852f-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="a852f-412">Para continuar, [cree etiquetas con DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="a852f-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="a852f-413">Crear etiquetas con DKE</span><span class="sxs-lookup"><span data-stu-id="a852f-413">Create labels using DKE</span></span>

<span data-ttu-id="a852f-414">Una vez que haya registrado el almacén de claves, configure las etiquetas de confidencialidad en el centro de cumplimiento de Microsoft 365 y aplique el cifrado de doble clave a dichas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a852f-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="a852f-415">En la interfaz de usuario de creación de etiquetas, seleccione la opción **usar cifrado de doble clave** y escriba la dirección URL del punto de conexión para la clave.</span><span class="sxs-lookup"><span data-stu-id="a852f-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="a852f-416">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a852f-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Seleccione usar el cifrado de doble clave en el centro de cumplimiento de Microsoft 365":::

<span data-ttu-id="a852f-418">Las etiquetas de DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de las aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="a852f-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="a852f-419">Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a852f-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="a852f-420">Habilitar DKE en el cliente</span><span class="sxs-lookup"><span data-stu-id="a852f-420">Enable DKE in your client</span></span>

<span data-ttu-id="a852f-421">Si las etiquetas DKE no aparecen en la cinta de confidencialidad en Microsoft Office, es posible que el cliente no tenga habilitada la DKE.</span><span class="sxs-lookup"><span data-stu-id="a852f-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="a852f-422">Para habilitar DKE para el cliente, agregue las siguientes claves del registro:</span><span class="sxs-lookup"><span data-stu-id="a852f-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
