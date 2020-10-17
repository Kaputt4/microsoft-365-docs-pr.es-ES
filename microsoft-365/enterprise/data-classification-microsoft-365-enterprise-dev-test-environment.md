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
description: Use esta guía del entorno de pruebas para crear y usar etiquetas de retención en documentos en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487737"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e76c4-103">Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e76c4-103">Data classification for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e76c4-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="e76c4-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e76c4-105">En este artículo se describe cómo configurar la clasificación de datos con etiquetas de retención en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="e76c4-105">This article describes how to configure data classification using retention labels in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="e76c4-106">La clasificación de datos en el entorno de prueba implica tres fases:</span><span class="sxs-lookup"><span data-stu-id="e76c4-106">Classifying data in your test environment involves three phases:</span></span>
- [<span data-ttu-id="e76c4-107">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e76c4-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e76c4-108">Fase 2: crear etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="e76c4-108">Phase 2: Create retention labels</span></span>](#phase-2-create-retention-labels)
- [<span data-ttu-id="e76c4-109">Fase 3: aplicar etiquetas de retención a los documentos</span><span class="sxs-lookup"><span data-stu-id="e76c4-109">Phase 3: Apply retention labels to documents</span></span>](#phase-3-apply-retention-labels-to-documents)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e76c4-111">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e76c4-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e76c4-112">Fase 1: crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e76c4-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e76c4-113">Si solo quiere configurar las etiquetas de retención de una manera ligera con los requisitos mínimos, siga las instrucciones de [configuración de base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e76c4-113">If you just want to configure retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e76c4-114">Si desea configurar las etiquetas de retención en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e76c4-114">If you want to configure retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e76c4-115">La prueba de las etiquetas de retención no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="e76c4-115">Testing retention labels doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e76c4-116">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="e76c4-116">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-retention-labels"></a><span data-ttu-id="e76c4-117">Fase 2: crear etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="e76c4-117">Phase 2: Create retention labels</span></span>

<span data-ttu-id="e76c4-118">En esta fase, cree las etiquetas de retención para los distintos niveles de retención para las carpetas de documentos de SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="e76c4-118">In this phase, create the retention labels for the different levels of retention for SharePoint Online documents folders:</span></span>

1. <span data-ttu-id="e76c4-119">Inicie sesión en el [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e76c4-119">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
1. <span data-ttu-id="e76c4-120">En la pestaña **Inicio-seguridad de Microsoft 365** del explorador, seleccione **Classification**  >  **etiquetas de retención**de clasificación.</span><span class="sxs-lookup"><span data-stu-id="e76c4-120">From the **Home - Microsoft 365 security** tab of your browser, select **Classification** > **Retention labels**.</span></span>
1. <span data-ttu-id="e76c4-121">Seleccione**Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-121">Select **Create a label**.</span></span>
1. <span data-ttu-id="e76c4-122">En el panel **asignar un nombre a la etiqueta** , escriba **público interno** en **nombre de la etiqueta**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-122">In the **Name your label** pane, enter **Internal Public** in **Name your label**, and then select **Next**.</span></span>
1. <span data-ttu-id="e76c4-123">En el panel **descriptores del plan de archivos** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-123">In the **File plan descriptors** pane, select **Next**.</span></span>
1. <span data-ttu-id="e76c4-124">En el **panel Configuración de etiqueta** , si es necesario, establezca **retenciones** en **activado**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-124">In the **Label settings** pane, if needed, set **Retention** to **On**, and then select **Next**.</span></span>
1. <span data-ttu-id="e76c4-125">En el panel **Revise su configuración** , seleccione **crear la etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-125">In the **Review your settings** pane, select **Create the label**.</span></span>
1. <span data-ttu-id="e76c4-126">Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="e76c4-126">Repeat steps 3-7 for additional labels with these names:</span></span>
  - <span data-ttu-id="e76c4-127">Private</span><span class="sxs-lookup"><span data-stu-id="e76c4-127">Private</span></span>
  - <span data-ttu-id="e76c4-128">Confidencial</span><span class="sxs-lookup"><span data-stu-id="e76c4-128">Sensitive</span></span>
  - <span data-ttu-id="e76c4-129">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="e76c4-129">Highly Confidential</span></span>
1. <span data-ttu-id="e76c4-130">En el panel **etiquetas de retención** , seleccione **publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-130">In the **Retention labels** pane, select **Publish labels**.</span></span>
1. <span data-ttu-id="e76c4-131">En el panel **elegir etiquetas para publicar** , seleccione **elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-131">In the **Choose labels to publish** pane, select **Choose labels to publish**.</span></span>
1. <span data-ttu-id="e76c4-132">En el panel **elegir etiquetas** , seleccione **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="e76c4-132">In the **Choose labels** pane, select **Add** and select all four labels.</span></span>
1. <span data-ttu-id="e76c4-133">Seleccione **Agregar**y, a continuación, haga clic en **listo**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-133">Select **Add**, and then select **Done**.</span></span>
1. <span data-ttu-id="e76c4-134">En el panel **elegir etiquetas para publicar** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-134">On the **Choose labels to publish** pane, select **Next**.</span></span>
1. <span data-ttu-id="e76c4-135">En el panel **elegir ubicaciones** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-135">On the **Choose locations** pane, select **Next**.</span></span>
1. <span data-ttu-id="e76c4-136">En el panel escriba **un nombre para la Directiva** , escriba **organización de ejemplo** en **nombre**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-136">On the **Name your policy** pane, enter **Example organization** in **Name**, and then select **Next**.</span></span>
1. <span data-ttu-id="e76c4-137">En el panel **Revise su configuración** , seleccione **publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-137">On the **Review your settings** pane, select **Publish labels**.</span></span>
 
<span data-ttu-id="e76c4-138">La publicación de las etiquetas de retención puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="e76c4-138">It might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-retention-labels-to-documents"></a><span data-ttu-id="e76c4-139">Fase 3: aplicar etiquetas de retención a los documentos</span><span class="sxs-lookup"><span data-stu-id="e76c4-139">Phase 3: Apply retention labels to documents</span></span>

<span data-ttu-id="e76c4-140">En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención para los archivos de la carpeta documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.</span><span class="sxs-lookup"><span data-stu-id="e76c4-140">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="e76c4-141">En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:</span><span class="sxs-lookup"><span data-stu-id="e76c4-141">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="e76c4-142">Con una instancia privada del explorador, inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) mediante su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e76c4-142">Using a private instance of your browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using your global admin account.</span></span>
1. <span data-ttu-id="e76c4-143">En la lista de mosaicos, seleccione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-143">In the list of tiles, select **SharePoint**.</span></span>
1. <span data-ttu-id="e76c4-144">En la nueva pestaña de **SharePoint** del explorador, seleccione **crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-144">On the new **SharePoint** tab in your browser, select **Create site**.</span></span>
1. <span data-ttu-id="e76c4-145">En la página **Crear un sitio**, seleccione **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-145">On the **Create a site** page, select **Team site**.</span></span>
1. <span data-ttu-id="e76c4-146">En el cuadro **nombre del sitio de grupo** , escriba **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-146">In the **Team site name** box, enter **SensitiveFiles**.</span></span>
1. <span data-ttu-id="e76c4-147">En el cuadro **Descripción del sitio de grupo** , escriba **sitio de SharePoint para los archivos confidenciales**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-147">In the **Team site description** box, enter **SharePoint site for sensitive files**.</span></span>
1. <span data-ttu-id="e76c4-148">En **configuración de privacidad**, seleccione **privado: solo los miembros pueden acceder a este sitio**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-148">In **Privacy settings**, select **Private - only members can access this site**, and then select **Next**.</span></span>
1. <span data-ttu-id="e76c4-149">En el panel **¿quién desea agregar?** , seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-149">In the **Who do you want to add?** pane, select **Finish**.</span></span>
    
<span data-ttu-id="e76c4-150">A continuación, configure la carpeta documentos del sitio de grupo de SensitiveFiles para la etiqueta retención confidencial.</span><span class="sxs-lookup"><span data-stu-id="e76c4-150">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="e76c4-151">En la pestaña **SensitiveFiles** del explorador, seleccione **documentos**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-151">In the **SensitiveFiles** tab of your browser, select **Documents**.</span></span>
1. <span data-ttu-id="e76c4-152">Seleccione el icono de **configuración** y, a continuación, seleccione **configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-152">Select the **Settings** icon, and then select **Library settings**.</span></span>
1. <span data-ttu-id="e76c4-153">En **permisos y administración**, seleccione **Aplicar etiqueta a los elementos de esta lista o biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-153">Under **Permissions and Management**, select **Apply label to items in this list or library**.</span></span> <span data-ttu-id="e76c4-154">Si esta opción no aparece, las etiquetas de retención aún no se publican.</span><span class="sxs-lookup"><span data-stu-id="e76c4-154">If this option doesn't appear, your retention labels aren't yet published.</span></span> <span data-ttu-id="e76c4-155">Pruebe este paso más tarde.</span><span class="sxs-lookup"><span data-stu-id="e76c4-155">Try this step at a later time.</span></span>
1. <span data-ttu-id="e76c4-156">En **Configuración: aplicar etiqueta**, seleccione **confidencial** en el cuadro desplegable y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-156">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then select **Save**.</span></span>

<span data-ttu-id="e76c4-157">A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambie su etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="e76c4-157">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="e76c4-158">En la carpeta documentos, seleccione **nuevo**  >  **documento de Word**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-158">In the documents folder, select **New** > **Word document**.</span></span>
1. <span data-ttu-id="e76c4-159">Escriba texto en el documento en blanco.</span><span class="sxs-lookup"><span data-stu-id="e76c4-159">Enter some text in the blank document.</span></span> <span data-ttu-id="e76c4-160">Espere a que se guarde el texto.</span><span class="sxs-lookup"><span data-stu-id="e76c4-160">Wait for the text to be saved.</span></span>
1. <span data-ttu-id="e76c4-161">En la barra de menús, seleccione **documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-161">On the menu bar, select **Shared Documents**.</span></span>
1. <span data-ttu-id="e76c4-162">Junto al nombre de archivo **Document.docx** , seleccione los puntos suspensivos verticales y, a continuación, seleccione **detalles**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-162">Next to the **Document.docx** file name, select the vertical ellipsis, and then select **Details**.</span></span>
1. <span data-ttu-id="e76c4-163">En el panel derecho, en la sección **propiedades** , en **Aplicar etiqueta de retención**, tenga en cuenta que se ha aplicado automáticamente la etiqueta retención **sensible** al documento.</span><span class="sxs-lookup"><span data-stu-id="e76c4-163">In the right pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
1. <span data-ttu-id="e76c4-164">Haga clic en **Editar todo**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-164">Click **Edit all**.</span></span>
1. <span data-ttu-id="e76c4-165">En el panel de **Document.docx** , en **Aplicar etiqueta de retención**, seleccione la etiqueta **extremadamente confidencial** y, después, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e76c4-165">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then select **Save**.</span></span>

## <a name="next-step"></a><span data-ttu-id="e76c4-166">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e76c4-166">Next step</span></span>

<span data-ttu-id="e76c4-167">Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="e76c4-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e76c4-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="e76c4-168">See also</span></span>

[<span data-ttu-id="e76c4-169">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e76c4-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e76c4-170">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e76c4-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e76c4-171">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e76c4-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
