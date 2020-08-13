---
title: Centro de administración de Exchange en EOP independiente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la interfaz de administración web en la protección independiente de Exchange Online (EOP).
ms.openlocfilehash: d5753f687461a5495c2431db687263d7211bcbf5
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652914"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="eb522-103">Centro de administración de Exchange en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="eb522-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="eb522-104">El centro de administración de Exchange (EAC) es una consola de administración basada en web para la protección independiente de Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="eb522-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="eb522-105">¿Está buscando la versión de Exchange Online de este tema?</span><span class="sxs-lookup"><span data-stu-id="eb522-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="eb522-106">Vea [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="eb522-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="eb522-107">Abrir el EAC en EOP</span><span class="sxs-lookup"><span data-stu-id="eb522-107">Open the EAC in EOP</span></span>

<span data-ttu-id="eb522-108">Los clientes de EOP independientes pueden tener acceso al EAC mediante los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="eb522-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="eb522-109">**En el centro de administración de Microsoft 365**:</span><span class="sxs-lookup"><span data-stu-id="eb522-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="eb522-110">Vaya a <https://admin.microsoft.com> y haga clic en **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="eb522-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Haga clic en Mostrar todo en el centro de administración de Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="eb522-112">En la sección **centros de administración** que aparece, haga clic en **todos los centros de administración**.</span><span class="sxs-lookup"><span data-stu-id="eb522-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Haga clic en todos los centros de administración en el centro de administración de Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="eb522-114">En la página **todos los centros de administración** que aparece, haga clic en **protección en línea de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="eb522-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="eb522-115">Ir directamente a `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="eb522-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="eb522-116">Elementos comunes de la interfaz de usuario en el EAC en EOP</span><span class="sxs-lookup"><span data-stu-id="eb522-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="eb522-117">En esta sección se describen los elementos de la interfaz de usuario del EAC.</span><span class="sxs-lookup"><span data-stu-id="eb522-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP: AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="eb522-119">Panel de características</span><span class="sxs-lookup"><span data-stu-id="eb522-119">Feature Pane</span></span>

<span data-ttu-id="eb522-p102">Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.</span><span class="sxs-lookup"><span data-stu-id="eb522-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="eb522-122">**Destinatarios**: aquí es donde se ven los grupos y los contactos externos.</span><span class="sxs-lookup"><span data-stu-id="eb522-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="eb522-123">**Permisos**: aquí donde podrá administrar los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="eb522-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="eb522-124">**Administración de cumplimiento**: aquí es donde encontrará el informe de grupo de roles de administrador y el registro de auditoría de administrador.</span><span class="sxs-lookup"><span data-stu-id="eb522-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="eb522-125">**Protección**: aquí puede administrar las directivas antimalware, la Directiva de filtro de conexión predeterminada y DKIM.</span><span class="sxs-lookup"><span data-stu-id="eb522-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="eb522-126">Debe administrar las directivas antimalware y la Directiva de filtro de conexión predeterminada en el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="eb522-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="eb522-127">Para obtener más información, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) y [Configure Connection Filtering in EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="eb522-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="eb522-128">**Flujo de correo**: aquí es donde administrará las reglas de flujo de correo (también conocidas como reglas de transporte), dominios aceptados y conectores, así como donde puede ir a ejecutar seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="eb522-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="eb522-129">**Híbrido**: aquí puede ejecutar el [Asistente para la configuración híbrida](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)y donde puede instalar el [módulo de PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="eb522-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="eb522-130">Pestañas</span><span class="sxs-lookup"><span data-stu-id="eb522-130">Tabs</span></span>

<span data-ttu-id="eb522-131">Las pestañas son el segundo nivel de navegación.</span><span class="sxs-lookup"><span data-stu-id="eb522-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="eb522-132">Las áreas de características contienen varias pestañas y cada área representa a una característica.</span><span class="sxs-lookup"><span data-stu-id="eb522-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="eb522-133">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="eb522-133">Toolbar</span></span>

<span data-ttu-id="eb522-p105">Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.</span><span class="sxs-lookup"><span data-stu-id="eb522-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="eb522-137">Icon</span><span class="sxs-lookup"><span data-stu-id="eb522-137">Icon</span></span>|<span data-ttu-id="eb522-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="eb522-138">Name</span></span>|<span data-ttu-id="eb522-139">Acción</span><span class="sxs-lookup"><span data-stu-id="eb522-139">Action</span></span>|
|---|---|---|
|![Agregar icono](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="eb522-141">Agregar, nuevo</span><span class="sxs-lookup"><span data-stu-id="eb522-141">Add, New</span></span>|<span data-ttu-id="eb522-p106">Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.</span><span class="sxs-lookup"><span data-stu-id="eb522-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Icono Editar](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="eb522-145">Editar</span><span class="sxs-lookup"><span data-stu-id="eb522-145">Edit</span></span>|<span data-ttu-id="eb522-146">Utilice este icono para editar un objeto.</span><span class="sxs-lookup"><span data-stu-id="eb522-146">Use this icon to edit an object.</span></span>|
|![Eliminar icono](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="eb522-148">Eliminar</span><span class="sxs-lookup"><span data-stu-id="eb522-148">Delete</span></span>|<span data-ttu-id="eb522-p107">Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="eb522-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![icono de Buscar](../../media/ITPro-EAC-.gif)|<span data-ttu-id="eb522-152">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="eb522-152">Search</span></span>|<span data-ttu-id="eb522-153">Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.</span><span class="sxs-lookup"><span data-stu-id="eb522-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Icono Actualizar](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="eb522-155">Actualizar</span><span class="sxs-lookup"><span data-stu-id="eb522-155">Refresh</span></span>|<span data-ttu-id="eb522-156">Utilice este icono para actualizar la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="eb522-156">Use this icon to refresh the list view.</span></span>|
|![Icono Más opciones](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="eb522-158">Más opciones</span><span class="sxs-lookup"><span data-stu-id="eb522-158">More options</span></span>|<span data-ttu-id="eb522-p108">Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  </span><span class="sxs-lookup"><span data-stu-id="eb522-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="eb522-163">Flecha hacia arriba y flecha hacia abajo</span><span class="sxs-lookup"><span data-stu-id="eb522-163">Up arrow and down arrow</span></span>|<span data-ttu-id="eb522-164">Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="eb522-164">Use these icons to move an object's priority up or down.</span></span>|
|![Icono de quitar](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="eb522-166">Quitar</span><span class="sxs-lookup"><span data-stu-id="eb522-166">Remove</span></span>|<span data-ttu-id="eb522-167">Utilice este icono para quitar objetos de la lista.</span><span class="sxs-lookup"><span data-stu-id="eb522-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="eb522-168">Vista de lista</span><span class="sxs-lookup"><span data-stu-id="eb522-168">List View</span></span>

<span data-ttu-id="eb522-p109">Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.</span><span class="sxs-lookup"><span data-stu-id="eb522-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="eb522-172">panel Detalles</span><span class="sxs-lookup"><span data-stu-id="eb522-172">Details Pane</span></span>

<span data-ttu-id="eb522-p110">Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="eb522-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="eb522-175">Mosaico Yo y Ayuda</span><span class="sxs-lookup"><span data-stu-id="eb522-175">Me tile and Help</span></span>

<span data-ttu-id="eb522-p111">El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](../../media/ITPro-EAC-HelpIcon.gif), puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="eb522-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="eb522-178">**Ayuda**: haga clic en ![ el icono ayuda ](../../media/ITPro-EAC-HelpIcon.gif) para ver el contenido de la ayuda en línea.</span><span class="sxs-lookup"><span data-stu-id="eb522-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="eb522-179">**Comentarios**: dejar comentarios.</span><span class="sxs-lookup"><span data-stu-id="eb522-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="eb522-180">**Comunidad**: publique una pregunta para encontrar respuestas en los foros de la comunidad.</span><span class="sxs-lookup"><span data-stu-id="eb522-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="eb522-181">**Deshabilitar la burbuja de ayuda**: la burbuja de ayuda muestra la ayuda contextual de los campos cuando se crea o edita un objeto.</span><span class="sxs-lookup"><span data-stu-id="eb522-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="eb522-182">Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="eb522-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="eb522-183">**Mostrar registro de comandos**: se abre una nueva ventana que muestra los comandos de PowerShell equivalentes en función de lo que haya configurado en el EAC.</span><span class="sxs-lookup"><span data-stu-id="eb522-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="eb522-184">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="eb522-184">Supported Browsers</span></span>

<span data-ttu-id="eb522-185">Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb522-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="eb522-186">También le recomendamos que instale las actualizaciones de software cuando estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb522-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="eb522-187">Para obtener más información acerca de los exploradores compatibles y los requisitos del sistema para el servicio, vea [System Requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="eb522-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="eb522-188">Idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="eb522-188">Supported languages</span></span>

<span data-ttu-id="eb522-189">Los siguientes idiomas son compatibles y están disponibles para el EAC en un EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="eb522-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="eb522-190">Amhárico</span><span class="sxs-lookup"><span data-stu-id="eb522-190">Amharic</span></span>
- <span data-ttu-id="eb522-191">Árabe</span><span class="sxs-lookup"><span data-stu-id="eb522-191">Arabic</span></span>
- <span data-ttu-id="eb522-192">Vasco (Euskera)</span><span class="sxs-lookup"><span data-stu-id="eb522-192">Basque (Basque)</span></span>
- <span data-ttu-id="eb522-193">Bengalí (India)</span><span class="sxs-lookup"><span data-stu-id="eb522-193">Bengali (India)</span></span>
- <span data-ttu-id="eb522-194">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="eb522-194">Bulgarian</span></span>
- <span data-ttu-id="eb522-195">Catalán</span><span class="sxs-lookup"><span data-stu-id="eb522-195">Catalan</span></span>
- <span data-ttu-id="eb522-196">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="eb522-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="eb522-197">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="eb522-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="eb522-198">Croata</span><span class="sxs-lookup"><span data-stu-id="eb522-198">Croatian</span></span>
- <span data-ttu-id="eb522-199">Checo</span><span class="sxs-lookup"><span data-stu-id="eb522-199">Czech</span></span>
- <span data-ttu-id="eb522-200">Danés</span><span class="sxs-lookup"><span data-stu-id="eb522-200">Danish</span></span>
- <span data-ttu-id="eb522-201">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="eb522-201">Dutch</span></span>
- <span data-ttu-id="eb522-202">Inglés</span><span class="sxs-lookup"><span data-stu-id="eb522-202">English</span></span>
- <span data-ttu-id="eb522-203">Estonio</span><span class="sxs-lookup"><span data-stu-id="eb522-203">Estonian</span></span>
- <span data-ttu-id="eb522-204">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="eb522-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="eb522-205">Finés</span><span class="sxs-lookup"><span data-stu-id="eb522-205">Finnish</span></span>
- <span data-ttu-id="eb522-206">Francés</span><span class="sxs-lookup"><span data-stu-id="eb522-206">French</span></span>
- <span data-ttu-id="eb522-207">Gallego</span><span class="sxs-lookup"><span data-stu-id="eb522-207">Galician</span></span>
- <span data-ttu-id="eb522-208">Alemán</span><span class="sxs-lookup"><span data-stu-id="eb522-208">German</span></span>
- <span data-ttu-id="eb522-209">Griego</span><span class="sxs-lookup"><span data-stu-id="eb522-209">Greek</span></span>
- <span data-ttu-id="eb522-210">Gujarati</span><span class="sxs-lookup"><span data-stu-id="eb522-210">Gujarati</span></span>
- <span data-ttu-id="eb522-211">Hebreo</span><span class="sxs-lookup"><span data-stu-id="eb522-211">Hebrew</span></span>
- <span data-ttu-id="eb522-212">Hindi</span><span class="sxs-lookup"><span data-stu-id="eb522-212">Hindi</span></span>
- <span data-ttu-id="eb522-213">Húngaro</span><span class="sxs-lookup"><span data-stu-id="eb522-213">Hungarian</span></span>
- <span data-ttu-id="eb522-214">Islandés</span><span class="sxs-lookup"><span data-stu-id="eb522-214">Icelandic</span></span>
- <span data-ttu-id="eb522-215">Indonesio</span><span class="sxs-lookup"><span data-stu-id="eb522-215">Indonesian</span></span>
- <span data-ttu-id="eb522-216">Italiano</span><span class="sxs-lookup"><span data-stu-id="eb522-216">Italian</span></span>
- <span data-ttu-id="eb522-217">Japonés</span><span class="sxs-lookup"><span data-stu-id="eb522-217">Japanese</span></span>
- <span data-ttu-id="eb522-218">Kannada</span><span class="sxs-lookup"><span data-stu-id="eb522-218">Kannada</span></span>
- <span data-ttu-id="eb522-219">Kazajo</span><span class="sxs-lookup"><span data-stu-id="eb522-219">Kazakh</span></span>
- <span data-ttu-id="eb522-220">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="eb522-220">Kiswahili</span></span>
- <span data-ttu-id="eb522-221">Coreano</span><span class="sxs-lookup"><span data-stu-id="eb522-221">Korean</span></span>
- <span data-ttu-id="eb522-222">Letón</span><span class="sxs-lookup"><span data-stu-id="eb522-222">Latvian</span></span>
- <span data-ttu-id="eb522-223">Lituano</span><span class="sxs-lookup"><span data-stu-id="eb522-223">Lithuanian</span></span>
- <span data-ttu-id="eb522-224">Malayo (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="eb522-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="eb522-225">Malayo (Malasia)</span><span class="sxs-lookup"><span data-stu-id="eb522-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="eb522-226">Malayalam</span><span class="sxs-lookup"><span data-stu-id="eb522-226">Malayalam</span></span>
- <span data-ttu-id="eb522-227">Maratí</span><span class="sxs-lookup"><span data-stu-id="eb522-227">Marathi</span></span>
- <span data-ttu-id="eb522-228">Noruego (Bokmal)</span><span class="sxs-lookup"><span data-stu-id="eb522-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="eb522-229">Noruego (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="eb522-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="eb522-230">Odia</span><span class="sxs-lookup"><span data-stu-id="eb522-230">Oriya</span></span>
- <span data-ttu-id="eb522-231">Persa</span><span class="sxs-lookup"><span data-stu-id="eb522-231">Persian</span></span>
- <span data-ttu-id="eb522-232">Polaco</span><span class="sxs-lookup"><span data-stu-id="eb522-232">Polish</span></span>
- <span data-ttu-id="eb522-233">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="eb522-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="eb522-234">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="eb522-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="eb522-235">Rumano</span><span class="sxs-lookup"><span data-stu-id="eb522-235">Romanian</span></span>
- <span data-ttu-id="eb522-236">Ruso</span><span class="sxs-lookup"><span data-stu-id="eb522-236">Russian</span></span>
- <span data-ttu-id="eb522-237">Serbio (cirílico, Serbia)</span><span class="sxs-lookup"><span data-stu-id="eb522-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="eb522-238">Serbio (latino)</span><span class="sxs-lookup"><span data-stu-id="eb522-238">Serbian (Latin)</span></span>
- <span data-ttu-id="eb522-239">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="eb522-239">Slovak</span></span>
- <span data-ttu-id="eb522-240">Esloveno</span><span class="sxs-lookup"><span data-stu-id="eb522-240">Slovenian</span></span>
- <span data-ttu-id="eb522-241">Español</span><span class="sxs-lookup"><span data-stu-id="eb522-241">Spanish</span></span>
- <span data-ttu-id="eb522-242">Sueco</span><span class="sxs-lookup"><span data-stu-id="eb522-242">Swedish</span></span>
- <span data-ttu-id="eb522-243">Tamil</span><span class="sxs-lookup"><span data-stu-id="eb522-243">Tamil</span></span>
- <span data-ttu-id="eb522-244">Telugu</span><span class="sxs-lookup"><span data-stu-id="eb522-244">Telugu</span></span>
- <span data-ttu-id="eb522-245">Tailandés</span><span class="sxs-lookup"><span data-stu-id="eb522-245">Thai</span></span>
- <span data-ttu-id="eb522-246">Turco</span><span class="sxs-lookup"><span data-stu-id="eb522-246">Turkish</span></span>
- <span data-ttu-id="eb522-247">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="eb522-247">Ukrainian</span></span>
- <span data-ttu-id="eb522-248">Urdu</span><span class="sxs-lookup"><span data-stu-id="eb522-248">Urdu</span></span>
- <span data-ttu-id="eb522-249">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="eb522-249">Vietnamese</span></span>
- <span data-ttu-id="eb522-250">Galés</span><span class="sxs-lookup"><span data-stu-id="eb522-250">Welsh</span></span>
