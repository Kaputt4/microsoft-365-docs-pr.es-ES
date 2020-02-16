---
title: Clasificación de datos para su entorno de prueba de Microsoft 365 Enterprise
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
description: Use esta guía del laboratorio de pruebas para crear y usar las etiquetas de retención de Office 365 en documentos de su entorno de prueba empresarial de Microsoft 365.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067997"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6f943-103">Clasificación de datos para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f943-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6f943-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6f943-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6f943-105">Con las instrucciones de este artículo, podrá configurar la clasificación de datos con las etiquetas de retención de Office 365 en su entorno de prueba empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f943-105">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6f943-107">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6f943-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6f943-108">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f943-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6f943-109">Si solo quiere configurar las etiquetas de retención de Office 365 de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6f943-109">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6f943-110">Si desea configurar las etiquetas de retención de Office 365 en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6f943-110">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f943-111">La prueba de las etiquetas de retención de Office 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6f943-111">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6f943-112">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="6f943-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="6f943-113">Fase 2: crear etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f943-113">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="6f943-114">En esta fase, creará las etiquetas de retención para los distintos niveles de retención para las carpetas de documentos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f943-114">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="6f943-115">Inicie sesión en el [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6f943-115">Sign in to the [Microsoft 365 security center](https://security.microsoft.com/homepage) with your global admin account.</span></span>
    
2. <span data-ttu-id="6f943-116">En la pestaña **Inicio-seguridad de Microsoft 365** del explorador, haga clic en **clasificación > etiquetas de retención**.</span><span class="sxs-lookup"><span data-stu-id="6f943-116">From the **Home - Microsoft 365 security** tab of your browser, click **Classification > Retention labels**.</span></span>
    
3. <span data-ttu-id="6f943-117">Haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6f943-117">Click **Create a label**.</span></span>
    
4. <span data-ttu-id="6f943-118">En el panel **nombre de la etiqueta** , escriba **Internal Public** en **nombre de la etiqueta**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-118">In the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="6f943-119">En el panel **descriptores del plan de archivos** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-119">In the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="6f943-120">En el **panel Configuración de etiqueta** , si es necesario, establezca **retenciones** en **activado**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-120">In the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="6f943-121">En el panel **Revise su configuración** , haga clic en **crear la etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6f943-121">In the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="6f943-122">Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:</span><span class="sxs-lookup"><span data-stu-id="6f943-122">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="6f943-123">Private</span><span class="sxs-lookup"><span data-stu-id="6f943-123">Private</span></span>
    
  - <span data-ttu-id="6f943-124">Confidencial</span><span class="sxs-lookup"><span data-stu-id="6f943-124">Sensitive</span></span>
    
  - <span data-ttu-id="6f943-125">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="6f943-125">Highly Confidential</span></span>
  
9. <span data-ttu-id="6f943-126">En el panel **etiquetas de retención** , haga clic en **publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="6f943-126">In the **Retention labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="6f943-127">En el panel **elegir etiquetas para publicar** , haga clic en **elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="6f943-127">In the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="6f943-128">En el panel **elegir etiquetas** , haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="6f943-128">In the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="6f943-129">Haga clic en **Agregar**y, a continuación, en **listo**.</span><span class="sxs-lookup"><span data-stu-id="6f943-129">Click **Add**, and then click **Done**.</span></span>
    
13. <span data-ttu-id="6f943-130">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-130">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="6f943-131">En el panel **Seleccionar ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-131">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="6f943-132">En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-132">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="6f943-133">En el panel **Revise su configuración** , haga clic en **publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="6f943-133">On the **Review your settings** pane, click **Publish labels**.</span></span>
 
<span data-ttu-id="6f943-134">Tenga en cuenta que la publicación de las etiquetas de retención puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="6f943-134">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="6f943-135">Fase 3: aplicar las etiquetas de retención de Office 365 a los documentos</span><span class="sxs-lookup"><span data-stu-id="6f943-135">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="6f943-136">En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención para los archivos de la carpeta documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.</span><span class="sxs-lookup"><span data-stu-id="6f943-136">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="6f943-137">En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:</span><span class="sxs-lookup"><span data-stu-id="6f943-137">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="6f943-138">Con una instancia privada del explorador, inicie sesión en el [portal de Office 365](https://portal.office.com) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6f943-138">Using a private instance of your browser, sign in to the [Office 365 portal](https://portal.office.com) using your global admin account.</span></span>
    
2. <span data-ttu-id="6f943-139">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6f943-139">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="6f943-140">En la nueva pestaña de **SharePoint** del explorador, haga clic en **crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="6f943-140">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="6f943-141">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="6f943-141">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="6f943-142">En **nombre del sitio de grupo**, escriba **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="6f943-142">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="6f943-143">En **Descripción del sitio de grupo**, escriba **sitio de SharePoint para archivos confidenciales**.</span><span class="sxs-lookup"><span data-stu-id="6f943-143">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="6f943-144">En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6f943-144">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="6f943-145">En el panel **¿quién desea agregar?** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6f943-145">In the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="6f943-146">A continuación, configure la carpeta documentos del sitio de grupo de SensitiveFiles para la etiqueta retención confidencial.</span><span class="sxs-lookup"><span data-stu-id="6f943-146">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="6f943-147">En la pestaña **SensitiveFiles** del explorador, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="6f943-147">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="6f943-148">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6f943-148">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="6f943-149">En **permisos y administración**, haga clic en **Aplicar etiqueta a los elementos de esta lista o biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6f943-149">Under **Permissions and Management**, click **Apply label to items in this list or library**.</span></span> <span data-ttu-id="6f943-150">Si esta opción no aparece, las etiquetas de retención aún no se publican.</span><span class="sxs-lookup"><span data-stu-id="6f943-150">If this option does not appear, your retention labels are not yet published.</span></span> <span data-ttu-id="6f943-151">Pruebe este paso más tarde.</span><span class="sxs-lookup"><span data-stu-id="6f943-151">Try this step at a later time.</span></span>
    
4. <span data-ttu-id="6f943-152">En **Configuración: aplicar etiqueta**, seleccione **confidencial** en el cuadro desplegable y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f943-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="6f943-153">A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambie su etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="6f943-153">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="6f943-154">En la carpeta documentos, haga clic en **nuevo > documento de Word**.</span><span class="sxs-lookup"><span data-stu-id="6f943-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="6f943-155">Escriba texto en el documento en blanco.</span><span class="sxs-lookup"><span data-stu-id="6f943-155">Type some text in the blank document.</span></span> <span data-ttu-id="6f943-156">Espere a que se guarde el texto.</span><span class="sxs-lookup"><span data-stu-id="6f943-156">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="6f943-157">En la barra de menús, haga clic en **documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="6f943-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="6f943-158">Haga clic en los puntos suspensivos verticales junto al nombre del archivo **. docx del documento** y, a continuación, haga clic en **detalles**.</span><span class="sxs-lookup"><span data-stu-id="6f943-158">Click the vertical ellipsis next to the **Document.docx** file name, and then click **Details**.</span></span>
    
5. <span data-ttu-id="6f943-159">En el panel derecho, en la sección **propiedades** , en **Aplicar etiqueta de retención**, tenga en cuenta que se ha aplicado automáticamente la etiqueta retención **sensible** al documento.</span><span class="sxs-lookup"><span data-stu-id="6f943-159">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** retention label automatically applied.</span></span>
    
6. <span data-ttu-id="6f943-160">Haga clic en **Editar todo**.</span><span class="sxs-lookup"><span data-stu-id="6f943-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="6f943-161">En el panel **Document. docx** , en **Aplicar etiqueta de retención**, seleccione la etiqueta **extremadamente confidencial** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f943-161">In the **Document.docx** pane, under **Apply retention label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="6f943-162">Consulte el paso [configurar la clasificación del entorno](infoprotect-configure-classification.md) en la fase de protección de la **información** para obtener información y vínculos sobre cómo implementar las etiquetas de retención de Office 365 en producción.</span><span class="sxs-lookup"><span data-stu-id="6f943-162">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="6f943-163">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6f943-163">Next step</span></span>

<span data-ttu-id="6f943-164">Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="6f943-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f943-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f943-165">See also</span></span>

[<span data-ttu-id="6f943-166">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f943-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6f943-167">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f943-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6f943-168">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f943-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 
