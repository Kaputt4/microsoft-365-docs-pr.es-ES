---
title: Entorno de prueba de clasificación de datos para la empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para crear y usar Office 365 etiquetas en documentos en el entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871773"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6cb1a-103">Entorno de prueba de clasificación de datos para la empresa de 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6cb1a-103">Data classification for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6cb1a-104">Con las instrucciones de este artículo, configure una clasificación de datos mediante las etiquetas de Office 365 en su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-104">With the instructions in this article, you configure data classification using Office 365 labels in your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6cb1a-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6cb1a-107">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6cb1a-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6cb1a-108">Si desea configurar las etiquetas de Office 365 en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6cb1a-108">If you just want to configure Office 365 labels in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6cb1a-109">Si desea configurar las etiquetas de Office 365 en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6cb1a-109">If you want to configure Office 365 labels in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cb1a-p101">Probar Office 365 etiquetas no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-p101">Testing Office 365 labels does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-create-office-365-labels"></a><span data-ttu-id="6cb1a-112">Fase 2: Crear etiquetas de Office 365</span><span class="sxs-lookup"><span data-stu-id="6cb1a-112">Phase 2: Create Office 365 labels</span></span>

<span data-ttu-id="6cb1a-113">En esta fase, cree las etiquetas para los diferentes niveles de seguridad para las carpetas de documentos de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-113">In this phase, you create the labels for the different levels of security for SharePoint Online documents folders.</span></span>
  
1. <span data-ttu-id="6cb1a-p102">Si es necesario, use una instancia privada de su explorador de Internet e inicie sesión el portal de Office 365 con su cuenta de administrador global. Para obtener ayuda, consulte [Where iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="6cb1a-p102">If needed, use a private instance of your Internet browser and sign in to the Office 365 portal with your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="6cb1a-116">En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-116">From the **Microsoft Office Home** tab, click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="6cb1a-117">En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración Seguridad &amp; Cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-117">From the new **Office Admin center** tab of your browser, click **Admin centers > Security &amp; Compliance**.</span></span>
    
4. <span data-ttu-id="6cb1a-118">En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-118">From the new **Home - Security &amp; Compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
5. <span data-ttu-id="6cb1a-119">En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-119">From the **Home > Labels** pane, click **Create a label**.</span></span>
    
6. <span data-ttu-id="6cb1a-120">En el panel **Nombre de la etiqueta**, escriba **Interno público** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-120">On the **Name your label** pane, type **Internal Public**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="6cb1a-121">En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-121">On the **Label settings** pane, click **Next**.</span></span>
    
8. <span data-ttu-id="6cb1a-122">En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-122">On the **Review your settings** pane, click **Create this label**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="6cb1a-123">Repita los pasos del 5 al 8 para estas etiquetas adicionales:</span><span class="sxs-lookup"><span data-stu-id="6cb1a-123">Repeat steps 5-8 for these additional labels:</span></span>
    
  - <span data-ttu-id="6cb1a-124">Private</span><span class="sxs-lookup"><span data-stu-id="6cb1a-124">Private</span></span>
    
  - <span data-ttu-id="6cb1a-125">Confidencial</span><span class="sxs-lookup"><span data-stu-id="6cb1a-125">Sensitive</span></span>
    
  - <span data-ttu-id="6cb1a-126">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="6cb1a-126">Highly Confidential</span></span>
    
10. <span data-ttu-id="6cb1a-127">En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).</span><span class="sxs-lookup"><span data-stu-id="6cb1a-127">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
11. <span data-ttu-id="6cb1a-128">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-128">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
12. <span data-ttu-id="6cb1a-129">En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-129">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
13. <span data-ttu-id="6cb1a-130">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-130">Click **Done**.</span></span>
    
14. <span data-ttu-id="6cb1a-131">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-131">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="6cb1a-132">En el panel **Seleccionar ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-132">On the **Choose locations** pane, click **Next**.</span></span>
    
16. <span data-ttu-id="6cb1a-133">En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-133">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
17. <span data-ttu-id="6cb1a-134">En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-134">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

<span data-ttu-id="6cb1a-135">Tenga en cuenta que puede tardar unos minutos para las etiquetas que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-135">Note that it might take a few minutes for the labels to be published.</span></span>

## <a name="phase-3-apply-office-365-labels-to-documents"></a><span data-ttu-id="6cb1a-136">Fase 3: Aplicar etiquetas de Office 365 a los documentos</span><span class="sxs-lookup"><span data-stu-id="6cb1a-136">Phase 3: Apply Office 365 labels to documents</span></span>

<span data-ttu-id="6cb1a-137">En esta fase, detectar el comportamiento de la etiqueta predeterminada para los archivos en la carpeta de documentos de un sitio de SharePoint Online y cambiar manualmente la etiqueta de un documento.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-137">In this phase, you discover the default label behavior for files in the Documents folder of a SharePoint Online site and manually change the label of a document.</span></span>

<span data-ttu-id="6cb1a-138">En primer lugar, cree un sitio de grupo de SharePoint Online confidenciales nivel:</span><span class="sxs-lookup"><span data-stu-id="6cb1a-138">First, create a sensitive-level SharePoint Online team site:</span></span>
  
1. <span data-ttu-id="6cb1a-p103">Abra un explorador en el equipo local e inicie sesión en el portal de Office 365 con la cuenta de administrador global. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="6cb1a-p103">Using a browser on your local computer, sign in to the Office 365 portal using your global administrator account. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="6cb1a-141">En la lista de iconos, haga clic en **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-141">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="6cb1a-142">En la ficha nuevo de **SharePoint** en el explorador, haga clic en **Crear sitio**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-142">On the new **SharePoint** tab in your browser, click **Create site**.</span></span>
    
4. <span data-ttu-id="6cb1a-143">En la página **Crear un sitio**, haga clic en **Sitio de grupo**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-143">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="6cb1a-144">En **nombre del sitio del equipo**, escriba **SensitiveFiles**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-144">In **Team site name**, type **SensitiveFiles**.</span></span>
    
6. <span data-ttu-id="6cb1a-145">En **Descripción del sitio del equipo**, escriba el **sitio de SharePoint para archivos confidenciales**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-145">In **Team site description**, type **SharePoint site for sensitive files**.</span></span>
    
7.  <span data-ttu-id="6cb1a-146">En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-146">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="6cb1a-147">En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-147">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="6cb1a-148">A continuación, configure la carpeta de documentos del sitio del equipo de SensitiveFiles para la etiqueta confidencial.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-148">Next, configure the Documents folder of the SensitiveFiles team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="6cb1a-149">En la ficha **SensitiveFiles** del explorador, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-149">In the **SensitiveFiles** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="6cb1a-150">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-150">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="6cb1a-151">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="6cb1a-151">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="6cb1a-152">En **Aplicar a la configuración de etiqueta**, seleccione **confidencial** en el cuadro de lista desplegable y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-152">In **Settings-Apply Label**, select **Sensitive** in the drop-down box, and then click **Save**.</span></span>

<span data-ttu-id="6cb1a-153">A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambiar su etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-153">Next, create a new document in the SensitiveFiles site and change its label.</span></span>
    
1. <span data-ttu-id="6cb1a-154">En la carpeta de documentos, haga clic en **Nuevo > documento de Word**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-154">In the documents folder, click **New > Word document**.</span></span>
    
2. <span data-ttu-id="6cb1a-p104">Escriba algún texto en el documento en blanco. Espere a que el texto que se va a guardar.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-p104">Type some text in the blank document. Wait for the text to be saved.</span></span>
    
3. <span data-ttu-id="6cb1a-157">En la barra de menús, haga clic en **Documentos compartidos**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-157">In the menu bar, click **Shared Documents**.</span></span>
    
4. <span data-ttu-id="6cb1a-158">Haga clic en el icono de Word junto al nombre de archivo **Document.docx** .</span><span class="sxs-lookup"><span data-stu-id="6cb1a-158">Click the Word icon next to the **Document.docx** file name.</span></span>
    
5. <span data-ttu-id="6cb1a-159">En el panel derecho, en la sección de **Propiedades** , en **Aplicar etiqueta**, tenga en cuenta que el documento ha tenido la etiqueta **confidencial** aplica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-159">In the right-hand pane, in the **Properties** section, under **Apply label**, note that the document has had the **Sensitive** label automatically applied.</span></span>
    
6. <span data-ttu-id="6cb1a-160">Haga clic en **Editar todos**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-160">Click **Edit all**.</span></span>
    
7. <span data-ttu-id="6cb1a-161">En el panel de **Document.docx** , en **Aplicar etiqueta**, seleccione la etiqueta **Altamente confidencial** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-161">In the **Document.docx** pane, under **Apply label**, select the **Highly Confidential** label, and then click **Save**.</span></span>

<span data-ttu-id="6cb1a-162">En la fase de **protección de la información** para obtener información y vínculos a las etiquetas de Office 365 en producción, vea el paso [Configurar clasificación para su entorno](data-classification-microsoft-365-enterprise-dev-test-environment.md) .</span><span class="sxs-lookup"><span data-stu-id="6cb1a-162">See the [Configure classification for your environment](data-classification-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to Office 365 labels in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="6cb1a-163">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6cb1a-163">Next step</span></span>

<span data-ttu-id="6cb1a-164">Explorar las características adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="6cb1a-164">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cb1a-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cb1a-165">See also</span></span>

[<span data-ttu-id="6cb1a-166">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6cb1a-166">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6cb1a-167">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6cb1a-167">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6cb1a-168">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6cb1a-168">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

 