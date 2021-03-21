---
title: Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta Guía del laboratorio de pruebas para crear y usar etiquetas de retención en documentos de su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919193"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5a649-103">Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5a649-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5a649-104">*Esta guía del laboratorio de pruebas se puede usar para entornos de prueba de Microsoft 365 para empresas y office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5a649-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5a649-105">En este artículo se describe cómo configurar la clasificación de datos mediante etiquetas de retención en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="5a649-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="5a649-106">Clasificar datos en el entorno de prueba implica tres fases:</span><span class="sxs-lookup"><span data-stu-id="5a649-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="5a649-107">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5a649-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="5a649-108">Fase 2: Crear etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="5a649-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="5a649-109">Fase 3: Aplicar etiquetas de retención a documentos</span><span class="sxs-lookup"><span data-stu-id="5a649-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5a649-111">Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para](../downloads/Microsoft365EnterpriseTLGStack.pdf)enterprise Test Lab Guide Stack .</span><span class="sxs-lookup"><span data-stu-id="5a649-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5a649-112">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5a649-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5a649-113">Si solo desea configurar etiquetas de retención de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="5a649-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5a649-114">Si desea configurar etiquetas de retención en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5a649-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a649-115">La prueba de etiquetas de retención no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5a649-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5a649-116">Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="5a649-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="5a649-117">Fase 2: Crear etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="5a649-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="5a649-118">En esta fase, cree las etiquetas de retención para los diferentes niveles de retención de carpetas de documentos de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="5a649-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="5a649-119">Inicie sesión en el [Centro de seguridad de Microsoft 365](https://security.microsoft.com/homepage) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5a649-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="5a649-120">En la **pestaña Inicio - Seguridad de Microsoft 365** del explorador, seleccione **Etiquetas de** retención de  >  **clasificación.**</span><span class="sxs-lookup"><span data-stu-id="5a649-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="5a649-121">Seleccione **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5a649-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="5a649-122">En el **panel Nombre de la etiqueta,** escriba Public **interno** en Nombre de la **etiqueta** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="5a649-123">En el **panel Descriptores de plan de archivos,** seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="5a649-124">En el **panel Configuración de** etiqueta, si es necesario, establezca **Retención** en **On** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="5a649-125">En el **panel Revisar la configuración,** seleccione **Crear la etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="5a649-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="5a649-126">Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="5a649-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="5a649-127">Private</span><span class="sxs-lookup"><span data-stu-id="5a649-127">Private</span></span>
  - <span data-ttu-id="5a649-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="5a649-128">Sensitive</span></span>
  - <span data-ttu-id="5a649-129">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="5a649-129">Highly Confidential</span></span>
1. <span data-ttu-id="5a649-130">En el **panel Etiquetas de** retención, seleccione **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5a649-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="5a649-131">En el **panel Elegir etiquetas para publicar,** seleccione **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="5a649-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="5a649-132">En el **panel Elegir etiquetas,** seleccione **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="5a649-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="5a649-133">Seleccione **Agregar** y, a continuación, **Seleccione Listo**.</span><span class="sxs-lookup"><span data-stu-id="5a649-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="5a649-134">En el **panel Elegir etiquetas para publicar,** seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="5a649-135">En el **panel Elegir ubicaciones,** seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="5a649-136">En el **panel Nombre de la directiva,** escriba **Organización** de ejemplo en **Nombre** y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="5a649-137">En el **panel Revisar la configuración,** seleccione **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="5a649-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="5a649-138">Las etiquetas de retención pueden tardar unos minutos en publicarse.</span><span class="sxs-lookup"><span data-stu-id="5a649-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="5a649-139">Fase 3: Aplicar etiquetas de retención a documentos</span><span class="sxs-lookup"><span data-stu-id="5a649-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="5a649-140">En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención de los archivos de la carpeta Documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.</span><span class="sxs-lookup"><span data-stu-id="5a649-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="5a649-141">En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:</span><span class="sxs-lookup"><span data-stu-id="5a649-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="5a649-142">Con una instancia privada del explorador, inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5a649-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="5a649-143">En la lista de iconos, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="5a649-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="5a649-144">En la nueva **pestaña de SharePoint** del explorador, seleccione **Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="5a649-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="5a649-145">En la página **Crear un sitio**, seleccione **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="5a649-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="5a649-146">En el **cuadro Nombre del sitio del** equipo, escriba **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="5a649-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="5a649-147">En el **cuadro Descripción del sitio de** grupo, escriba Sitio de **SharePoint para archivos confidenciales.**</span><span class="sxs-lookup"><span data-stu-id="5a649-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="5a649-148">En **Configuración de privacidad,** **seleccione Privado: solo los miembros** pueden tener acceso a este sitio y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a649-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="5a649-149">En el **panel ¿A quién desea agregar?,** seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5a649-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="5a649-150">A continuación, configure la carpeta Documentos del sitio de grupo SensitiveFiles para la etiqueta de retención Confidencial.</span><span class="sxs-lookup"><span data-stu-id="5a649-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="5a649-151">En la **pestaña SensitiveFiles** del explorador, seleccione **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="5a649-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="5a649-152">Seleccione el **icono Configuración** y, a continuación, seleccione Configuración **de biblioteca.**</span><span class="sxs-lookup"><span data-stu-id="5a649-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="5a649-153">En **Permisos y administración,** seleccione **Aplicar etiqueta a los elementos de esta lista o biblioteca.**</span><span class="sxs-lookup"><span data-stu-id="5a649-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="5a649-154">Si esta opción no aparece, las etiquetas de retención aún no se publican.</span><span class="sxs-lookup"><span data-stu-id="5a649-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="5a649-155">Pruebe este paso más adelante.</span><span class="sxs-lookup"><span data-stu-id="5a649-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="5a649-156">En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** en el cuadro desplegable y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5a649-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="5a649-157">A continuación, cree un nuevo documento en el sitio SensitiveFiles y cambie su etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="5a649-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="5a649-158">En la carpeta documentos, seleccione **Nuevo**  >  **documento de Word**.</span><span class="sxs-lookup"><span data-stu-id="5a649-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="5a649-159">Escriba texto en el documento en blanco.</span><span class="sxs-lookup"><span data-stu-id="5a649-159">Enter some text in the blank document.</span></span> <span data-ttu-id="5a649-160">Espere a que se guarde el texto.</span><span class="sxs-lookup"><span data-stu-id="5a649-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="5a649-161">En la barra de menús, seleccione **Documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="5a649-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="5a649-162">Junto al nombre **Document.docx** archivo, seleccione los puntos suspensivos verticales y, a continuación, **seleccione Detalles**.</span><span class="sxs-lookup"><span data-stu-id="5a649-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="5a649-163">En el panel derecho, en la sección **Propiedades,** en **Aplicar** etiqueta de retención, tenga en cuenta que el documento se ha aplicado automáticamente la **etiqueta** de retención confidencial.</span><span class="sxs-lookup"><span data-stu-id="5a649-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="5a649-164">Haga clic en **Editar todo**.</span><span class="sxs-lookup"><span data-stu-id="5a649-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="5a649-165">En el **Document.docx,** en **Aplicar** etiqueta de retención, seleccione la **etiqueta Extremadamente** confidencial y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5a649-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="5a649-166">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5a649-166">Next step</span></span>

<span data-ttu-id="5a649-167">Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en el entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="5a649-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a649-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a649-168">See also</span></span>

[<span data-ttu-id="5a649-169">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5a649-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5a649-170">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5a649-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5a649-171">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5a649-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)