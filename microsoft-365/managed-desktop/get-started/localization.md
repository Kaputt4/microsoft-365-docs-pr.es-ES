---
title: Localizar la experiencia del usuario
description: Cómo localización de dispositivos para usuarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023266"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="e7bf5-104">Localizar la experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="e7bf5-104">Localize the user experience</span></span>

<span data-ttu-id="e7bf5-105">Los usuarios Escritorio administrado de Microsoft dispositivos pueden seleccionar el idioma que prefieran durante el proceso de configuración (la experiencia "fuera de la caja") o después.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="e7bf5-106">Durante la instalación (la experiencia "fuera de la caja")</span><span class="sxs-lookup"><span data-stu-id="e7bf5-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="e7bf5-107">Durante el proceso de completar la configuración, los usuarios pueden seleccionar el idioma que prefieran.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="e7bf5-108">Esta selección afecta a estos atributos:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="e7bf5-109">Windows 10 de idioma:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="e7bf5-110">Idioma para mostrar</span><span class="sxs-lookup"><span data-stu-id="e7bf5-110">Display language</span></span>
    - <span data-ttu-id="e7bf5-111">Idioma del teclado</span><span class="sxs-lookup"><span data-stu-id="e7bf5-111">Keyboard language</span></span>
    - <span data-ttu-id="e7bf5-112">Características relacionadas con el idioma a petición</span><span class="sxs-lookup"><span data-stu-id="e7bf5-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="e7bf5-113">Aplicaciones Microsoft 365 para Enterprise de idioma:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="e7bf5-114">Idioma para mostrar</span><span class="sxs-lookup"><span data-stu-id="e7bf5-114">Display language</span></span>
    - <span data-ttu-id="e7bf5-115">Herramientas de corrección y creación</span><span class="sxs-lookup"><span data-stu-id="e7bf5-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="e7bf5-116">Los usuarios solo pueden obtener características relacionadas con el idioma a petición seleccionando el idioma durante el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="e7bf5-117">Después de completar la configuración</span><span class="sxs-lookup"><span data-stu-id="e7bf5-117">After completing setup</span></span>

<span data-ttu-id="e7bf5-118">Los usuarios pueden seleccionar el idioma que prefieran para Windows 10 y Aplicaciones Microsoft 365 para Enterprise en cualquier momento después de que se complete el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="e7bf5-119">En particular:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-119">Specifically:</span></span>

- <span data-ttu-id="e7bf5-120">Windows 10 de idioma:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="e7bf5-121">Idioma para mostrar</span><span class="sxs-lookup"><span data-stu-id="e7bf5-121">Display language</span></span>
    - <span data-ttu-id="e7bf5-122">Idioma del teclado</span><span class="sxs-lookup"><span data-stu-id="e7bf5-122">Keyboard language</span></span>

- <span data-ttu-id="e7bf5-123">Aplicaciones Microsoft 365 para Enterprise de idioma:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="e7bf5-124">Idioma para mostrar</span><span class="sxs-lookup"><span data-stu-id="e7bf5-124">Display language</span></span>
    - <span data-ttu-id="e7bf5-125">Herramientas de corrección y creación</span><span class="sxs-lookup"><span data-stu-id="e7bf5-125">Proofing and authoring tools</span></span>

<span data-ttu-id="e7bf5-126">Para que los [idiomas admitidos](#supported-languages) para Aplicaciones Microsoft 365 para Enterprise que los usuarios puedan instalar, agregue los usuarios al grupo **Modern Workplace-Office-Language_Packs.**</span><span class="sxs-lookup"><span data-stu-id="e7bf5-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="e7bf5-127">Los idiomas estarán disponibles en el Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="e7bf5-128">Idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="e7bf5-128">Supported languages</span></span>

<span data-ttu-id="e7bf5-129">Para los nuevos dispositivos, el fabricante debe proporcionar imágenes de dispositivo que incluyan los idiomas que necesites.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="e7bf5-130">Si la imagen del fabricante incluye idiomas distintos de los proporcionados en la lista de idiomas admitidos, el servicio aún la admite.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="e7bf5-131">Si vas a volver a usar dispositivos existentes, es posible que debas trabajar con el representante de tu cuenta microsoft para obtener las imágenes adecuadas.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="e7bf5-132">Para obtener más información, consulta [Imágenes del dispositivo](../service-description/device-images.md).</span><span class="sxs-lookup"><span data-stu-id="e7bf5-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="e7bf5-133">La [imagen universal](../service-description/device-images.md#universal-image) proporcionada por Escritorio administrado de Microsoft incluye estos idiomas y para Windows 10:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="e7bf5-134">Árabe</span><span class="sxs-lookup"><span data-stu-id="e7bf5-134">Arabic</span></span>
- <span data-ttu-id="e7bf5-135">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="e7bf5-135">Bulgarian</span></span>
- <span data-ttu-id="e7bf5-136">Chino simplificado</span><span class="sxs-lookup"><span data-stu-id="e7bf5-136">Chinese Simplified</span></span>
- <span data-ttu-id="e7bf5-137">Chino tradicional</span><span class="sxs-lookup"><span data-stu-id="e7bf5-137">Chinese Traditional</span></span>
- <span data-ttu-id="e7bf5-138">Croata</span><span class="sxs-lookup"><span data-stu-id="e7bf5-138">Croatian</span></span>
- <span data-ttu-id="e7bf5-139">Checo</span><span class="sxs-lookup"><span data-stu-id="e7bf5-139">Czech</span></span>
- <span data-ttu-id="e7bf5-140">Danés</span><span class="sxs-lookup"><span data-stu-id="e7bf5-140">Danish</span></span>  
- <span data-ttu-id="e7bf5-141">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="e7bf5-141">Dutch</span></span>  
- <span data-ttu-id="e7bf5-142">Inglés (US, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="e7bf5-143">Estonio</span><span class="sxs-lookup"><span data-stu-id="e7bf5-143">Estonian</span></span>
- <span data-ttu-id="e7bf5-144">Finés</span><span class="sxs-lookup"><span data-stu-id="e7bf5-144">Finnish</span></span> 
- <span data-ttu-id="e7bf5-145">Francés (Francia, Canadá)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-145">French (France, Canada)</span></span>
- <span data-ttu-id="e7bf5-146">Alemán</span><span class="sxs-lookup"><span data-stu-id="e7bf5-146">German</span></span>
- <span data-ttu-id="e7bf5-147">Griego</span><span class="sxs-lookup"><span data-stu-id="e7bf5-147">Greek</span></span>
- <span data-ttu-id="e7bf5-148">Hebreo</span><span class="sxs-lookup"><span data-stu-id="e7bf5-148">Hebrew</span></span>
- <span data-ttu-id="e7bf5-149">Húngaro</span><span class="sxs-lookup"><span data-stu-id="e7bf5-149">Hungarian</span></span>
- <span data-ttu-id="e7bf5-150">Indonesio</span><span class="sxs-lookup"><span data-stu-id="e7bf5-150">Indonesian</span></span>
- <span data-ttu-id="e7bf5-151">Italiano</span><span class="sxs-lookup"><span data-stu-id="e7bf5-151">Italian</span></span>
- <span data-ttu-id="e7bf5-152">Japonés</span><span class="sxs-lookup"><span data-stu-id="e7bf5-152">Japanese</span></span>
- <span data-ttu-id="e7bf5-153">Coreano</span><span class="sxs-lookup"><span data-stu-id="e7bf5-153">Korean</span></span>
- <span data-ttu-id="e7bf5-154">Letón</span><span class="sxs-lookup"><span data-stu-id="e7bf5-154">Latvian</span></span>
- <span data-ttu-id="e7bf5-155">Lituano</span><span class="sxs-lookup"><span data-stu-id="e7bf5-155">Lithuanian</span></span>
- <span data-ttu-id="e7bf5-156">Noruego (bokmal)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="e7bf5-157">Polaco</span><span class="sxs-lookup"><span data-stu-id="e7bf5-157">Polish</span></span>
- <span data-ttu-id="e7bf5-158">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="e7bf5-159">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="e7bf5-160">Rumano</span><span class="sxs-lookup"><span data-stu-id="e7bf5-160">Romanian</span></span>
- <span data-ttu-id="e7bf5-161">Ruso</span><span class="sxs-lookup"><span data-stu-id="e7bf5-161">Russian</span></span> 
- <span data-ttu-id="e7bf5-162">Serbio (alfabeto latino)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="e7bf5-163">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="e7bf5-163">Slovak</span></span>
- <span data-ttu-id="e7bf5-164">Esloveno</span><span class="sxs-lookup"><span data-stu-id="e7bf5-164">Slovenian</span></span>
- <span data-ttu-id="e7bf5-165">Español (España, México)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="e7bf5-166">Sueco</span><span class="sxs-lookup"><span data-stu-id="e7bf5-166">Swedish</span></span>
- <span data-ttu-id="e7bf5-167">Tailandés</span><span class="sxs-lookup"><span data-stu-id="e7bf5-167">Thai</span></span>
- <span data-ttu-id="e7bf5-168">Turco</span><span class="sxs-lookup"><span data-stu-id="e7bf5-168">Turkish</span></span>
- <span data-ttu-id="e7bf5-169">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="e7bf5-169">Ukrainian</span></span>
- <span data-ttu-id="e7bf5-170">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="e7bf5-170">Vietnamese</span></span>

<span data-ttu-id="e7bf5-171">Aplicaciones Microsoft 365 para Enterprise puede admitir una lista ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="e7bf5-172">Si los usuarios necesitan un idioma distinto de los enumerados aquí, debe presentar una solicitud de soporte [técnico](../working-with-managed-desktop/admin-support.md) mediante el portal [de administración](access-admin-portal.md).</span><span class="sxs-lookup"><span data-stu-id="e7bf5-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="e7bf5-173">Idiomas para soporte técnico y operaciones</span><span class="sxs-lookup"><span data-stu-id="e7bf5-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="e7bf5-174">Soporte al usuario</span><span class="sxs-lookup"><span data-stu-id="e7bf5-174">User support</span></span>
<span data-ttu-id="e7bf5-175">Escritorio administrado de Microsoft solo admite en inglés.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="e7bf5-176">Si los usuarios eligen otro idioma en la aplicación Obtener ayuda, recibirán soporte técnico de los canales de soporte general de Microsoft, en lugar de admitir directamente desde Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="e7bf5-177">Para obtener más información, vea [Obtener ayuda para los usuarios](../working-with-managed-desktop/end-user-support.md).</span><span class="sxs-lookup"><span data-stu-id="e7bf5-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="e7bf5-178">Si los usuarios necesitan soporte técnico en otros idiomas, tendrás que proporcionarlo a través de orígenes de soporte técnico que no son de Microsoft o de tu propia organización.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="e7bf5-179">Soporte técnico y operaciones de administración</span><span class="sxs-lookup"><span data-stu-id="e7bf5-179">Admin support and operations</span></span>
<span data-ttu-id="e7bf5-180">Escritorio administrado de Microsoft proporciona soporte técnico para administradores solo en inglés.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="e7bf5-181">Esto incluye el portal de administración y todas las comunicaciones con Escritorio administrado de Microsoft operaciones.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="e7bf5-182">Debe asumir que todas las interacciones e interfaces relacionadas con el administrador estarán en inglés, a menos que se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


