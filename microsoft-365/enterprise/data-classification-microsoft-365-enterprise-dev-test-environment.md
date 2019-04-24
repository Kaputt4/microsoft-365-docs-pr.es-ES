---
title: Clasificación de datos para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para crear y usar las etiquetas de retención de Office 365 en documentos de su entorno de prueba empresarial de Microsoft 365.
ms.openlocfilehash: 3d64cd245e117813cb4c81a6e9099cd1a0120317
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283543"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d8625-103">Clasificación de datos para su entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d8625-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d8625-104">Con las instrucciones de este artículo, podrá configurar la clasificación de datos con las etiquetas de retención de Office 365 en su entorno de prueba empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8625-104">With the instructions in this article, you configure data classification using Office 365 retention labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d8625-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d8625-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d8625-107">Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d8625-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d8625-108">Si solo quiere configurar las etiquetas de retención de Office 365 de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d8625-108">If you just want to configure Office 365 retention labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d8625-109">Si desea configurar las etiquetas de retención de Office 365 en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d8625-109">If you want to configure Office 365 retention labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8625-110">La prueba de las etiquetas de retención de Office 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="d8625-110">Testing Office 365 retention labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d8625-111">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="d8625-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-retention-labels"></a><span data-ttu-id="d8625-112">Fase 2: crear etiquetas de retención de Office 365</span><span class="sxs-lookup"><span data-stu-id="d8625-112">Phase 2: Create Office 365 retention labels</span></span>

<span data-ttu-id="d8625-113">En esta fase, creará las etiquetas de retención para los distintos niveles de retención para las carpetas de documentos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d8625-113">In this phase, you create the retention labels for the different levels of retention for SharePoint Online documents folders.</span></span>

1. <span data-ttu-id="d8625-114">Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d8625-114">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="d8625-115">En la pestaña **Inicio: cumplimiento de Microsoft 365** del navegador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="d8625-115">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="d8625-116">Haga clic en **Etiquetas de retención > Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="d8625-116">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="d8625-117">En el panel **Nombre de la etiqueta**, escriba **Público interno** en **el espacio provisto**, y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-117">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="d8625-118">En el panel **descriptores de plan de archivos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-118">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="d8625-119">En el panel **Configuración de etiqueta**, si es necesario, marque **Retención** como **Activada** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-119">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="d8625-120">En el panel **Revise su configuración**, haga clic en **Crear la etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="d8625-120">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="d8625-121">Repita los pasos 3-7 para las etiquetas adicionales con estos nombres:</span><span class="sxs-lookup"><span data-stu-id="d8625-121">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="d8625-122">Private</span><span class="sxs-lookup"><span data-stu-id="d8625-122">Private</span></span>
    
  - <span data-ttu-id="d8625-123">Confidencial</span><span class="sxs-lookup"><span data-stu-id="d8625-123">Sensitive</span></span>
    
  - <span data-ttu-id="d8625-124">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="d8625-124">Highly Confidential</span></span>
  
9. <span data-ttu-id="d8625-125">En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).</span><span class="sxs-lookup"><span data-stu-id="d8625-125">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="d8625-126">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="d8625-126">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="d8625-127">En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="d8625-127">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="d8625-128">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="d8625-128">Click **Done**.</span></span>
    
13. <span data-ttu-id="d8625-129">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-129">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="d8625-130">En el panel **Seleccionar ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-130">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="d8625-131">En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-131">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="d8625-132">En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d8625-132">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
 
<span data-ttu-id="d8625-133">Tenga en cuenta que la publicación de las etiquetas de retención puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="d8625-133">Note that it might take a few minutes for the retention labels to be published.</span></span>

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a><span data-ttu-id="d8625-134">Fase 3: aplicar las etiquetas de retención de Office 365 a los documentos</span><span class="sxs-lookup"><span data-stu-id="d8625-134">Phase 3: Apply Office 365 retention labels to documents</span></span>

<span data-ttu-id="d8625-135">En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención para los archivos de la carpeta documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.</span><span class="sxs-lookup"><span data-stu-id="d8625-135">In this phase, you discover the default retention label behavior for files in the Documents folder of a SharePoint Online site and manually change the retention label of a document.</span></span>

<span data-ttu-id="d8625-136">En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:</span><span class="sxs-lookup"><span data-stu-id="d8625-136">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="d8625-137">Abra un explorador en el equipo local e inicie sesión en el [portal de Office 365](https://portal.office.com) con la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d8625-137">Using a browser on your local computer, sign in to the [Office 365 portal](https://portal.office.com) using your global administrator account.</span></span>
    
2. <span data-ttu-id="d8625-138">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="d8625-138">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="d8625-139">En la nueva pestaña de **SharePoint** del explorador, haga clic en **crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="d8625-139">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="d8625-140">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="d8625-140">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="d8625-141">En **nombre del sitio de grupo**, escriba **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="d8625-141">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="d8625-142">En **Descripción del sitio de grupo**, escriba **sitio de SharePoint para archivos confidenciales**.</span><span class="sxs-lookup"><span data-stu-id="d8625-142">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="d8625-143">En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d8625-143">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d8625-144">En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d8625-144">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="d8625-145">A continuación, configure la carpeta documentos del sitio de grupo de SensitiveFiles para la etiqueta retención confidencial.</span><span class="sxs-lookup"><span data-stu-id="d8625-145">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive retention label.</span></span>
  
1. <span data-ttu-id="d8625-146">En la pestaña **SensitiveFiles** del explorador, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="d8625-146">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="d8625-147">Haga clic en el icono de configuración y, después, en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="d8625-147">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="d8625-148">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="d8625-148">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="d8625-149">En **Configuración: aplicar etiqueta**, seleccione **confidencial** en el cuadro desplegable y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d8625-149">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="d8625-150">A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambie su etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="d8625-150">Next, create a new document in the SensitiveFiles site and change its retention label.</span></span>
    
1. <span data-ttu-id="d8625-151">En la carpeta documentos, haga clic en **nuevo documento de Word >**.</span><span class="sxs-lookup"><span data-stu-id="d8625-151">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="d8625-152">Escriba texto en el documento en blanco.</span><span class="sxs-lookup"><span data-stu-id="d8625-152">Type some text in the blank document.</span></span> <span data-ttu-id="d8625-153">Espere a que se guarde el texto.</span><span class="sxs-lookup"><span data-stu-id="d8625-153">Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="d8625-154">En la barra de menús, haga clic en **documentos**compartidos.</span><span class="sxs-lookup"><span data-stu-id="d8625-154">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="d8625-155">Haga clic en el icono de Word junto al nombre del archivo **Document. docx** .</span><span class="sxs-lookup"><span data-stu-id="d8625-155">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="d8625-156">En el panel derecho, en la sección **propiedades** , en **Aplicar etiqueta de retención**, tenga en cuenta que se ha aplicado automáticamente la etiqueta **confidencial** al documento.</span><span class="sxs-lookup"><span data-stu-id="d8625-156">In the right-hand pane, in the **Properties** section, under **Apply retention label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="d8625-157">Haga clic en **Editar todo**.</span><span class="sxs-lookup"><span data-stu-id="d8625-157">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="d8625-158">En el panel **Document. docx** , en **Aplicar etiqueta**, seleccione la etiqueta **extremadamente confidencial** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d8625-158">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="d8625-159">Consulte el paso [configurar la clasificación del entorno](infoprotect-configure-classification.md) en la fase de protección de la **información** para obtener información y vínculos sobre cómo implementar las etiquetas de retención de Office 365 en producción.</span><span class="sxs-lookup"><span data-stu-id="d8625-159">See the [Configure classification for your environment](infoprotect-configure-classification.md) step in the **Information protection** phase for information and links to how to deploy Office 365 retention labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d8625-160">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="d8625-160">Next step</span></span>

<span data-ttu-id="d8625-161">Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="d8625-161">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8625-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8625-162">See also</span></span>

[<span data-ttu-id="d8625-163">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d8625-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d8625-164">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d8625-164">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d8625-165">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d8625-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 