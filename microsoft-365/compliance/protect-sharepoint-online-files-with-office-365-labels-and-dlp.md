---
title: Proteger archivos de SharePoint Online con DLP y etiquetas de retención
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: c9f837af-8d71-4df1-a285-dedb1c5618b3
description: 'Resumen: Aplique directivas de etiquetas de retención y de prevención de pérdida de datos (DLP) a sitios de grupo de SharePoint Online con distintos niveles de protección de la información.'
ms.openlocfilehash: ad333007b2efdcf577f1c31afc716c525a7abf7e
ms.sourcegitcommit: a53ec6ab7bf59983780ea7187cd5d56b8b1f4b33
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "41855379"
---
# <a name="protect-sharepoint-online-files-with-retention-labels-and-dlp"></a><span data-ttu-id="1c93d-103">Proteger archivos de SharePoint Online con DLP y etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="1c93d-103">Protect SharePoint Online files with retention labels and DLP</span></span>

<span data-ttu-id="1c93d-104">Siga los pasos de este artículo para diseñar e implementar directivas de etiquetas de retención y de prevención de pérdida de datos (DLP) para sitios de grupo de base de referencia, confidenciales y extremadamente confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-104">Use the steps in this article to design and deploy retention labels and DLP policies for baseline, sensitive, and highly confidential SharePoint Online team sites.</span></span> <span data-ttu-id="1c93d-105">Para más información sobre estos tres niveles de protección, vea [Proteger sitios y archivos de SharePoint Online](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1c93d-105">For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="how-this-works"></a><span data-ttu-id="1c93d-106">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="1c93d-106">How this works</span></span>

1. <span data-ttu-id="1c93d-107">Crear las etiquetas de retención deseadas y publicarlas.</span><span class="sxs-lookup"><span data-stu-id="1c93d-107">Create the desired retention labels and publish these.</span></span> <span data-ttu-id="1c93d-108">Su publicación puede tardar hasta 12 horas.</span><span class="sxs-lookup"><span data-stu-id="1c93d-108">It can take up to 12 hours for these to be published.</span></span>
2. <span data-ttu-id="1c93d-109">Para los sitios de SharePoint deseados, edite la configuración de la biblioteca de documentos para aplicar las etiquetas de retención deseadas a los elementos de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1c93d-109">For the desired SharePoint sites, edit the document library settings to apply the desired retention labels to items in the library.</span></span>
3. <span data-ttu-id="1c93d-110">Crear directivas DLP que actúen en función de las etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="1c93d-110">Create DLP policies to take action based on the retention labels.</span></span>

<span data-ttu-id="1c93d-111">Cuando los usuarios agregan un documento a la biblioteca, el documento recibirá la etiqueta de retención asignada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1c93d-111">When users add a document to the library, the document will receive the assigned retention label by default.</span></span> <span data-ttu-id="1c93d-112">Los usuarios pueden cambiar la etiqueta, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="1c93d-112">Users can change the label, if needed.</span></span> <span data-ttu-id="1c93d-113">Cuando un usuario comparte un documento fuera de la organización, DLP comprobará si se le ha asignado una etiqueta y tomará medidas si una directiva DLP coincide con la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="1c93d-113">When a user shares a document outside the organization, DLP will check to see if a label is assigned and take action if a DLP policy matches the label.</span></span> <span data-ttu-id="1c93d-114">DLP buscará otras coincidencias de directivas, como la protección de archivos con números de tarjetas de crédito si se ha configurado este tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="1c93d-114">DLP will look for other policy matches as well, such as protecting files with credit card numbers if this type of policy is configured.</span></span> 

## <a name="retention-labels-for-your-sharepoint-online-sites"></a><span data-ttu-id="1c93d-115">Etiquetas de retención para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1c93d-115">Retention labels for your SharePoint Online sites</span></span>

<span data-ttu-id="1c93d-116">Hay tres fases para crear y luego asignar etiquetas de retención a sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-116">There are three phases to creating and then assigning retention labels to SharePoint Online team sites.</span></span>
  
### <a name="phase-1-determine-the-retention-label-names"></a><span data-ttu-id="1c93d-117">Fase 1: Determinar los nombres de etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="1c93d-117">Phase 1: Determine the retention label names</span></span>

<span data-ttu-id="1c93d-118">En esta fase se determinan los nombres de las etiquetas de retención para los cuatro niveles de protección de la información aplicados a los sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-118">In this phase, you determine the names of your retention labels for the four levels of information protection applied to SharePoint Online team sites.</span></span> <span data-ttu-id="1c93d-119">En la siguiente tabla se indican los nombres recomendados para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="1c93d-119">The following table lists the recommended names for each level.</span></span>
  
|<span data-ttu-id="1c93d-120">**Nivel de protección de sitio de grupo de SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="1c93d-120">**SharePoint Online team site protection level**</span></span>|<span data-ttu-id="1c93d-121">**Nombre de etiqueta**</span><span class="sxs-lookup"><span data-stu-id="1c93d-121">**Label name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1c93d-122">Base de referencia-Público</span><span class="sxs-lookup"><span data-stu-id="1c93d-122">Baseline-Public</span></span>  <br/> |<span data-ttu-id="1c93d-123">Interno público</span><span class="sxs-lookup"><span data-stu-id="1c93d-123">Internal public</span></span>  <br/> |
|<span data-ttu-id="1c93d-124">Base de referencia-Privado</span><span class="sxs-lookup"><span data-stu-id="1c93d-124">Baseline-Private</span></span>  <br/> |<span data-ttu-id="1c93d-125">Private</span><span class="sxs-lookup"><span data-stu-id="1c93d-125">Private</span></span>  <br/> |
|<span data-ttu-id="1c93d-126">Confidencial</span><span class="sxs-lookup"><span data-stu-id="1c93d-126">Sensitive</span></span>  <br/> |<span data-ttu-id="1c93d-127">Confidencial</span><span class="sxs-lookup"><span data-stu-id="1c93d-127">Sensitive</span></span>  <br/> |
|<span data-ttu-id="1c93d-128">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="1c93d-128">Highly Confidential</span></span>  <br/> |<span data-ttu-id="1c93d-129">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="1c93d-129">Highly Confidential</span></span>  <br/> |
   
### <a name="phase-2-create-the-retention-labels"></a><span data-ttu-id="1c93d-130">Fase 2: Crear las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="1c93d-130">Phase 2: Create the retention labels</span></span>

<span data-ttu-id="1c93d-131">En esta fase se crean y luego se publican las etiquetas determinadas para los diferentes niveles de protección de la información.</span><span class="sxs-lookup"><span data-stu-id="1c93d-131">In this phase, you create and then publish your determined labels for the different levels of information protection.</span></span>
  
1. <span data-ttu-id="1c93d-132">Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con una cuenta que tenga el rol de administrador de seguridad o administrador de la empresa.</span><span class="sxs-lookup"><span data-stu-id="1c93d-132">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="1c93d-133">En la pestaña **Inicio: Cumplimiento de Microsoft 365** del explorador, haga clic en **Clasificaciones > Etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-133">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="1c93d-134">Haga clic en **Etiquetas de retención > Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-134">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="1c93d-135">En el panel **Asignar un nombre a la etiqueta**, escriba el nombre de la etiqueta y una descripción para administradores y usuarios, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-135">On the **Name your label** pane, type the name of the label and a description for admins and users, and then click **Next**.</span></span>

5. <span data-ttu-id="1c93d-136">En el panel **Descriptores del plan de archivos**, rellene lo que sea necesario y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-136">On the **File plan descriptors** pane, fill in as needed, and then click **Next**.</span></span>
    
6. <span data-ttu-id="1c93d-137">En el panel **Configuración de etiqueta**, si es necesario, marque **Retención** como **Activado** y establezca la configuración de retención.</span><span class="sxs-lookup"><span data-stu-id="1c93d-137">On the **Label settings** pane, if needed, set **Retention** to **On** and configure retention settings.</span></span> <span data-ttu-id="1c93d-138">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-138">Click **Next**.</span></span>
    
7. <span data-ttu-id="1c93d-139">En el panel **Revise su configuración**, haga clic en **Crear la etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-139">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="1c93d-140">Para las otras etiquetas, haga clic en **Crear una etiqueta**, y, después, repita los pasos del 3 al 7 según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1c93d-140">For your additional labels, click **Create a label**, and then repeat steps 3-7 as needed.</span></span>
    

### <a name="publish-your-new-labels"></a><span data-ttu-id="1c93d-141">Publicar las nuevas etiquetas</span><span class="sxs-lookup"><span data-stu-id="1c93d-141">Publish your new labels</span></span>

<span data-ttu-id="1c93d-142">Luego siga estos pasos para publicar las nuevas etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="1c93d-142">Next, use these steps to publish the new retention labels.</span></span>
  
1. <span data-ttu-id="1c93d-143">En el panel **Etiquetas**, haga clic en la pestaña **Retención** y, después, haga clic en **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-143">From the **Labels** pane, click the **Retention labels** tab, and then click **Publish labels**.</span></span>
    
2. <span data-ttu-id="1c93d-144">En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-144">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
3. <span data-ttu-id="1c93d-145">En el panel **Elección de etiquetas**, haga clic en **Agregar**, seleccione las cuatro etiquetas y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-145">On the **Choose labels** pane, click **Add**, select all four labels, click **Add**.</span></span>
    
4. <span data-ttu-id="1c93d-146">Haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-146">Click **Done**.</span></span>
    
5. <span data-ttu-id="1c93d-147">En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-147">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="1c93d-148">En el panel **Elegir ubicaciones**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-148">On the **Choose locations** pane, click **Next**.</span></span>
    
7. <span data-ttu-id="1c93d-149">En el panel **Escriba un nombre para la directiva**, escriba un nombre para el conjunto de etiquetas en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-149">On the **Name your policy** pane, type a name for your set of labels in **Name**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="1c93d-150">En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-150">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>

    
### <a name="phase-3-apply-the-retention-labels-to-your-sharepoint-online-sites"></a><span data-ttu-id="1c93d-151">Fase 3: Aplicar las etiquetas de retención a los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1c93d-151">Phase 3: Apply the retention labels to your SharePoint Online sites</span></span>

<span data-ttu-id="1c93d-152">Siga estos pasos para aplicar las etiquetas de retención a las carpetas de documentos de los sitios de grupo de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-152">Use these steps to apply the retention labels to the documents folders of your SharePoint Online team sites.</span></span>
  
1. <span data-ttu-id="1c93d-153">Inicie sesión en el [portal de Office 365](https://www.office.com), haga clic en la aplicación **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-153">Sign in to the [Office 365 portal](https://www.office.com), click the **SharePoint** app.</span></span>
    
2. <span data-ttu-id="1c93d-154">En la nueva pestaña **SharePoint** del explorador, haga clic en un sitio al que haya que asignarle una etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="1c93d-154">On the new **SharePoint** tab in your browser, click a site that needs a retention label assigned.</span></span>
    
3. <span data-ttu-id="1c93d-155">En la nueva pestaña del sitio de SharePoint del explorador, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-155">In the new SharePoint site tab of your browser, click **Documents**.</span></span>
    
4. <span data-ttu-id="1c93d-156">Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-156">Click the settings icon, and then click **Library settings**.</span></span>
    
5. <span data-ttu-id="1c93d-157">En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).</span><span class="sxs-lookup"><span data-stu-id="1c93d-157">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
6. <span data-ttu-id="1c93d-158">En **Configuración-Aplicar etiqueta**, seleccione la etiqueta de retención adecuada y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-158">In **Settings-Apply Label**, select the appropriate retention label, and then click **Save**.</span></span>
    
7. <span data-ttu-id="1c93d-159">Cierre la pestaña del sitio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-159">Close the tab for the SharePoint Online site.</span></span>
    
8. <span data-ttu-id="1c93d-160">Repita los pasos del 2 al 8 para asignar etiquetas de retención a otros sitios de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-160">Repeat steps 2-8 to assign retention labels to your additional SharePoint Online sites.</span></span>
    
<span data-ttu-id="1c93d-161">Este es el resultado de la configuración.</span><span class="sxs-lookup"><span data-stu-id="1c93d-161">Here is your resulting configuration.</span></span>
  
![Etiquetas de retención para los cuatro tipos de sitios de grupo de SharePoint Online.](media/e0a4fdd2-1c30-4d93-8af4-a6f0c6c29966.png)
  
## <a name="dlp-policies-for-your-sharepoint-online-sites"></a><span data-ttu-id="1c93d-163">Directivas de DLP para los sitios de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1c93d-163">DLP policies for your SharePoint Online sites</span></span>

<span data-ttu-id="1c93d-164">Siga estos pasos para configurar una directiva de DLP que notifique a los usuarios cada vez que compartan un documento en un sitio de grupo confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="1c93d-164">Use these steps to configure a DLP policy that notifies users when they share a document on a SharePoint Online sensitive team site outside the organization.</span></span>

1. <span data-ttu-id="1c93d-165">Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) con una cuenta que tenga el rol Administrador de seguridad o Administrador de la compañía.</span><span class="sxs-lookup"><span data-stu-id="1c93d-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with an account that has the Security Administrator or Company Administrator role.</span></span>
    
2. <span data-ttu-id="1c93d-166">En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-166">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="1c93d-167">En el panel **Inicio > Prevención de pérdida de datos**, haga clic en **Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-167">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="1c93d-168">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-168">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="1c93d-169">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-169">In the **Name your policy** pane, type the name for the sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="1c93d-170">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-170">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="1c93d-171">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-171">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="1c93d-172">En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-172">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="1c93d-173">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-173">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="1c93d-174">En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-174">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="1c93d-175">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-175">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="1c93d-176">En el panel **Personalizar los tipos de información confidencial que quiere proteger**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-176">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="1c93d-177">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="1c93d-177">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="1c93d-178">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="1c93d-178">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="1c93d-179">En el cuadro de texto, escriba o pegue una de las siguientes sugerencias, dependiendo de si está utilizando etiquetas de confidencialidad opcionales para proteger los archivos confidenciales:</span><span class="sxs-lookup"><span data-stu-id="1c93d-179">In the text box, type or paste in one of the following tips, depending on if you are optionallyusing sensitivity labels to protect sensitive files:</span></span>
    
  - <span data-ttu-id="1c93d-p106">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="1c93d-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
  - <span data-ttu-id="1c93d-p107">Los archivos extremadamente confidenciales están protegidos con cifrado. Solo pueden leerlos aquellos usuarios externos a los que su departamento de TI les ha concedido permiso para acceder a los archivos.</span><span class="sxs-lookup"><span data-stu-id="1c93d-p107">Highly confidential files are protected with encryption. Only external users who are granted permissions to these files by your IT department can read them.</span></span>
    
    <span data-ttu-id="1c93d-185">Otra opción es escribir o pegar una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="1c93d-185">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="1c93d-186">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-186">Click **OK**.</span></span>
    
17. <span data-ttu-id="1c93d-187">En el panel **¿Qué quiere hacer si se detecta información confidencial?**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-187">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="1c93d-188">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-188">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="1c93d-189">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-189">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="1c93d-190">Esta es la configuración resultante para los sitios de grupo confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-190">Here is your resulting configuration for sensitive SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta de retención Confidencial.](media/2ff4cc53-87a8-43e3-b637-3068d88409f3.png)
  
<span data-ttu-id="1c93d-192">Ahora siga estos pasos para configurar una directiva de DLP que impida a los usuarios compartir un documento en un sitio de grupo extremadamente confidencial de SharePoint Online de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="1c93d-192">Next, use these steps to configure a DLP policy that blocks users when they share a document on a SharePoint Online highly confidential team site outside the organization.</span></span>
  
1. <span data-ttu-id="1c93d-193">En la nueva pestaña **cumplimiento de Microsoft 365** del explorador, haga clic en **Directivas  > Prevención de pérdida de datos**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-193">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
2. <span data-ttu-id="1c93d-194">En el panel **Prevención de pérdida de datos**, haga clic en **Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-194">In the **Data loss prevention** pane, click **Create a policy**.</span></span>
    
3. <span data-ttu-id="1c93d-195">En el panel **Start with a template or create a custom policy** (Empezar con una plantilla o crear una directiva personalizada), haga clic en **Personalizada** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-195">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="1c93d-196">En el panel **Escriba un nombre para la directiva**, escriba el nombre de la directiva de DLP de nivel extremadamente confidencial en **Nombre** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-196">In the **Name your policy** pane, type the name for the highly sensitive level DLP policy in **Name**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="1c93d-197">En el panel **Elegir ubicaciones**, haga clic en **Let me choose specific locations** (Permitir elegir ubicaciones concretas) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-197">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="1c93d-198">En la lista de ubicaciones, deshabilite las ubicaciones **Correo electrónico de Exchange**, **Cuentas de OneDrive** y **mensajes de chat y de canal de Teams** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-198">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
7. <span data-ttu-id="1c93d-199">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-199">In the **Customize the types of sensitive info you want to protect** pane, click **Edit**.</span></span>
    
8. <span data-ttu-id="1c93d-200">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Agregar** en el cuadro desplegable y luego en **Etiquetas de retención**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-200">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
9. <span data-ttu-id="1c93d-201">En el panel **Etiquetas de retención**, haga clic en **Agregar**, seleccione la etiqueta **Extremadamente confidencial**, haga clic en **Agregar** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-201">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
10. <span data-ttu-id="1c93d-202">En el panel **Choose the types of content to protect** (Elegir los tipos de contenido que se va a proteger), haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-202">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="1c93d-203">En el panel **Customize the types of sensitive info you want to protect** (Personalizar los tipos de información confidencial que quiere proteger), haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-203">In the **Customize the types of sensitive info you want to protect** pane, click **Next**.</span></span>
    
13. <span data-ttu-id="1c93d-204">En el panel **What do you want to do if we detect sensitive info?** (¿Qué quiere hacer si se detecta información confidencial?), haga clic en **Customize the tip and email** (Personalizar la sugerencia y el correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="1c93d-204">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="1c93d-205">En el panel **Customize policy tips and email notifications** (Personalizar sugerencias de directiva y notificaciones de correo electrónico), haga clic en **Customize the policy tip text** (Personalizar el texto de la sugerencia de directiva).</span><span class="sxs-lookup"><span data-stu-id="1c93d-205">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="1c93d-206">En el cuadro de texto, escriba o pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c93d-206">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="1c93d-p108">Para compartir con un usuario de fuera de la organización, descargue el archivo y luego ábralo. Haga clic en Archivo, Proteger documento y Cifrar con contraseña y, luego, especifique una contraseña segura. Envíe la contraseña en un correo electrónico diferente u otro medio de comunicación.</span><span class="sxs-lookup"><span data-stu-id="1c93d-p108">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
    <span data-ttu-id="1c93d-210">O bien escriba o pegue una sugerencia de directiva propia que indique a los usuarios cómo compartir un archivo fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="1c93d-210">Alternately, type or paste in your own policy tip that instructs users on how to share a file outside your organization.</span></span>
    
16. <span data-ttu-id="1c93d-211">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-211">Click **OK**.</span></span>
    
17. <span data-ttu-id="1c93d-212">En el panel **¿Qué desea hacer si detectamos información confidencial?**, en **Detectar cuando una cantidad específica de información confidencial se comparte al mismo tiempo**, haga clic en **Restringir acceso o encriptar el contenido**, y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-212">In the **What do you want to do if we detect sensitive info?** pane, under **Detect when a specific amount of sensitive info is being shared at one time**, click **Restrict access or encrypt the content**, and then click **Next**.</span></span>
    
18. <span data-ttu-id="1c93d-213">En el panel **Do you want to turn on the policy or test things out first?** (¿Desea activar la directiva o probarla primero?), haga clic en **Yes, turn it on right away** (Sí, activarla inmediatamente) y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-213">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="1c93d-214">En el panel **Revise su configuración**, haga clic en **Crear** y luego en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1c93d-214">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
    
<span data-ttu-id="1c93d-215">Esta es la configuración resultante para los sitios de grupo extremadamente confidenciales de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1c93d-215">Here is your resulting configuration for high confidentiality SharePoint Online team sites.</span></span>
  
![Directiva de DLP de un sitio de grupo aislado de SharePoint Online que utiliza la etiqueta de retención Extremadamente confidencial.](media/f705d3d0-23c9-4333-8b70-ad3b91f835ea.png)
  
## <a name="next-step"></a><span data-ttu-id="1c93d-217">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="1c93d-217">Next step</span></span>

[<span data-ttu-id="1c93d-218">Proteger los archivos de SharePoint Online con DLP y etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="1c93d-218">Protect SharePoint Online files with sensitivity labels</span></span>](protect-sharepoint-online-files-with-sensitivity-label.md)
    
## <a name="see-also"></a><span data-ttu-id="1c93d-219">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c93d-219">See Also</span></span>

[<span data-ttu-id="1c93d-220">Instrucciones de seguridad de Microsoft para campañas políticas, organizaciones sin ánimo de lucro y otras organizaciones ágiles</span><span class="sxs-lookup"><span data-stu-id="1c93d-220">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="1c93d-221">Adopción de la nube y soluciones híbridas</span><span class="sxs-lookup"><span data-stu-id="1c93d-221">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)


