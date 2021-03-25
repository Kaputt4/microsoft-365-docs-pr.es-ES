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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la interfaz de administración web en Exchange Online Protection (EOP) independiente.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207478"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="b04ff-103">Centro de administración de Exchange en EOP independiente</span><span class="sxs-lookup"><span data-stu-id="b04ff-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b04ff-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="b04ff-104">**Applies to**</span></span>
-  [<span data-ttu-id="b04ff-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="b04ff-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="b04ff-106">El Centro de administración de Exchange (EAC) es una consola de administración basada en web para Exchange Online Protection (EOP) independiente.</span><span class="sxs-lookup"><span data-stu-id="b04ff-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="b04ff-107">¿Está buscando la versión de Exchange Online de este tema?</span><span class="sxs-lookup"><span data-stu-id="b04ff-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="b04ff-108">Vea [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b04ff-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="b04ff-109">Abrir el EAC en EOP</span><span class="sxs-lookup"><span data-stu-id="b04ff-109">Open the EAC in EOP</span></span>

<span data-ttu-id="b04ff-110">Los clientes independientes de EOP pueden tener acceso al EAC mediante los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b04ff-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="b04ff-111">**Desde el Centro de administración de Microsoft 365**:</span><span class="sxs-lookup"><span data-stu-id="b04ff-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="b04ff-112">Vaya a <https://admin.microsoft.com> y haga clic en Mostrar **todo**.</span><span class="sxs-lookup"><span data-stu-id="b04ff-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Haga clic en Mostrar todo en el Centro de administración de Microsoft 365](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="b04ff-114">En la **sección Centros de administración** que aparece, haga clic en Todos los centros de **administración.**</span><span class="sxs-lookup"><span data-stu-id="b04ff-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Haga clic en Todos los centros de administración en el Centro de administración de Microsoft 365](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="b04ff-116">En la **página Todos los centros de administración** que aparece, haga clic en Exchange Online **Protection**.</span><span class="sxs-lookup"><span data-stu-id="b04ff-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="b04ff-117">Vaya directamente a `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="b04ff-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="b04ff-118">Elementos comunes de la interfaz de usuario en el EAC en EOP</span><span class="sxs-lookup"><span data-stu-id="b04ff-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="b04ff-119">En esta sección se describen los elementos de la interfaz de usuario del EAC.</span><span class="sxs-lookup"><span data-stu-id="b04ff-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Centro de administración de Exchange en Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="b04ff-121">Panel de características</span><span class="sxs-lookup"><span data-stu-id="b04ff-121">Feature Pane</span></span>

<span data-ttu-id="b04ff-p102">Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.</span><span class="sxs-lookup"><span data-stu-id="b04ff-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="b04ff-124">**Destinatarios:** aquí es donde verá grupos y contactos externos.</span><span class="sxs-lookup"><span data-stu-id="b04ff-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="b04ff-125">**Permisos:** aquí donde administrará los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="b04ff-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="b04ff-126">**Administración de cumplimiento:** aquí es donde encontrará el informe de grupo de roles de administrador y el informe de registro de auditoría de administrador.</span><span class="sxs-lookup"><span data-stu-id="b04ff-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="b04ff-127">**Protección:** aquí es donde puede administrar directivas antimalware, la directiva de filtro de conexión predeterminada y DKIM.</span><span class="sxs-lookup"><span data-stu-id="b04ff-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b04ff-128">Debe administrar directivas antimalware y la directiva de filtro de conexión predeterminada en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b04ff-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="b04ff-129">Para obtener más información, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) y [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b04ff-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="b04ff-130">**Flujo de** correo: aquí es donde administrará las reglas de flujo de correo (también conocidas como reglas de transporte), los dominios aceptados y los conectores, así como dónde puede ir para ejecutar el seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b04ff-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="b04ff-131">**Híbrido:** aquí es donde puede ejecutar [el](/Exchange/hybrid-configuration-wizard)Asistente para configuración híbrida y donde puede instalar el módulo [de PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell)de Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="b04ff-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="b04ff-132">Pestañas</span><span class="sxs-lookup"><span data-stu-id="b04ff-132">Tabs</span></span>

<span data-ttu-id="b04ff-133">Las pestañas son el segundo nivel de navegación.</span><span class="sxs-lookup"><span data-stu-id="b04ff-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="b04ff-134">Las áreas de características contienen varias pestañas y cada área representa a una característica.</span><span class="sxs-lookup"><span data-stu-id="b04ff-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="b04ff-135">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="b04ff-135">Toolbar</span></span>

<span data-ttu-id="b04ff-p105">Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.</span><span class="sxs-lookup"><span data-stu-id="b04ff-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="b04ff-139">Icon</span><span class="sxs-lookup"><span data-stu-id="b04ff-139">Icon</span></span>|<span data-ttu-id="b04ff-140">Nombre</span><span class="sxs-lookup"><span data-stu-id="b04ff-140">Name</span></span>|<span data-ttu-id="b04ff-141">Acción</span><span class="sxs-lookup"><span data-stu-id="b04ff-141">Action</span></span>|
|---|---|---|
|![Agregar icono](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="b04ff-143">Agregar, nuevo</span><span class="sxs-lookup"><span data-stu-id="b04ff-143">Add, New</span></span>|<span data-ttu-id="b04ff-p106">Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.</span><span class="sxs-lookup"><span data-stu-id="b04ff-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Icono Editar](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="b04ff-147">Editar</span><span class="sxs-lookup"><span data-stu-id="b04ff-147">Edit</span></span>|<span data-ttu-id="b04ff-148">Utilice este icono para editar un objeto.</span><span class="sxs-lookup"><span data-stu-id="b04ff-148">Use this icon to edit an object.</span></span>|
|![Eliminar icono](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="b04ff-150">Eliminar</span><span class="sxs-lookup"><span data-stu-id="b04ff-150">Delete</span></span>|<span data-ttu-id="b04ff-p107">Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="b04ff-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![icono de Buscar](../../media/ITPro-EAC-.gif)|<span data-ttu-id="b04ff-154">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="b04ff-154">Search</span></span>|<span data-ttu-id="b04ff-155">Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.</span><span class="sxs-lookup"><span data-stu-id="b04ff-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Icono Actualizar](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="b04ff-157">Actualizar</span><span class="sxs-lookup"><span data-stu-id="b04ff-157">Refresh</span></span>|<span data-ttu-id="b04ff-158">Utilice este icono para actualizar la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="b04ff-158">Use this icon to refresh the list view.</span></span>|
|![Icono Más opciones](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="b04ff-160">Más opciones</span><span class="sxs-lookup"><span data-stu-id="b04ff-160">More options</span></span>|<span data-ttu-id="b04ff-p108">Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  </span><span class="sxs-lookup"><span data-stu-id="b04ff-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Icono flecha arriba](../../media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="b04ff-165">Flecha hacia arriba y flecha hacia abajo</span><span class="sxs-lookup"><span data-stu-id="b04ff-165">Up arrow and down arrow</span></span>|<span data-ttu-id="b04ff-166">Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="b04ff-166">Use these icons to move an object's priority up or down.</span></span>|
|![Icono de quitar](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="b04ff-168">Quitar</span><span class="sxs-lookup"><span data-stu-id="b04ff-168">Remove</span></span>|<span data-ttu-id="b04ff-169">Utilice este icono para quitar objetos de la lista.</span><span class="sxs-lookup"><span data-stu-id="b04ff-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="b04ff-170">Vista de lista</span><span class="sxs-lookup"><span data-stu-id="b04ff-170">List View</span></span>

<span data-ttu-id="b04ff-p109">Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.</span><span class="sxs-lookup"><span data-stu-id="b04ff-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="b04ff-174">panel Detalles</span><span class="sxs-lookup"><span data-stu-id="b04ff-174">Details Pane</span></span>

<span data-ttu-id="b04ff-p110">Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="b04ff-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="b04ff-177">Mosaico Yo y Ayuda</span><span class="sxs-lookup"><span data-stu-id="b04ff-177">Me tile and Help</span></span>

<span data-ttu-id="b04ff-178">El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente.</span><span class="sxs-lookup"><span data-stu-id="b04ff-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="b04ff-179">En el **menú** ![ desplegable Icono de ](../../media/ITPro-EAC-HelpIcon.gif) ayuda, puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b04ff-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="b04ff-180">**Ayuda:** haga ![ clic en Icono de ayuda para ver el contenido de la ayuda en ](../../media/ITPro-EAC-HelpIcon.gif) línea.</span><span class="sxs-lookup"><span data-stu-id="b04ff-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="b04ff-181">**Comentarios:** deje comentarios.</span><span class="sxs-lookup"><span data-stu-id="b04ff-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="b04ff-182">**Comunidad:** publique una pregunta para buscar respuestas en los foros de la comunidad.</span><span class="sxs-lookup"><span data-stu-id="b04ff-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="b04ff-183">**Deshabilitar burbuja de ayuda:** la burbuja de ayuda muestra ayuda contextual para los campos al crear o editar un objeto.</span><span class="sxs-lookup"><span data-stu-id="b04ff-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="b04ff-184">Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="b04ff-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="b04ff-185">**Mostrar registro de comandos:** se abre una nueva ventana que muestra los comandos equivalentes de PowerShell en función de lo que configuró en EAC.</span><span class="sxs-lookup"><span data-stu-id="b04ff-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="b04ff-186">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="b04ff-186">Supported Browsers</span></span>

<span data-ttu-id="b04ff-187">Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b04ff-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="b04ff-188">También le recomendamos que instale las actualizaciones de software cuando estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="b04ff-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="b04ff-189">Para obtener más información acerca de los exploradores compatibles y los requisitos del sistema para el servicio, vea [Requisitos del sistema para Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="b04ff-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="b04ff-190">Idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="b04ff-190">Supported languages</span></span>

<span data-ttu-id="b04ff-191">Los siguientes idiomas son compatibles y están disponibles para el EAC en EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="b04ff-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="b04ff-192">Amhárico</span><span class="sxs-lookup"><span data-stu-id="b04ff-192">Amharic</span></span>
- <span data-ttu-id="b04ff-193">Árabe</span><span class="sxs-lookup"><span data-stu-id="b04ff-193">Arabic</span></span>
- <span data-ttu-id="b04ff-194">Vasco (Euskera)</span><span class="sxs-lookup"><span data-stu-id="b04ff-194">Basque (Basque)</span></span>
- <span data-ttu-id="b04ff-195">Bengalí (India)</span><span class="sxs-lookup"><span data-stu-id="b04ff-195">Bengali (India)</span></span>
- <span data-ttu-id="b04ff-196">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="b04ff-196">Bulgarian</span></span>
- <span data-ttu-id="b04ff-197">Catalán</span><span class="sxs-lookup"><span data-stu-id="b04ff-197">Catalan</span></span>
- <span data-ttu-id="b04ff-198">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="b04ff-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="b04ff-199">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="b04ff-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="b04ff-200">Croata</span><span class="sxs-lookup"><span data-stu-id="b04ff-200">Croatian</span></span>
- <span data-ttu-id="b04ff-201">Checo</span><span class="sxs-lookup"><span data-stu-id="b04ff-201">Czech</span></span>
- <span data-ttu-id="b04ff-202">Danés</span><span class="sxs-lookup"><span data-stu-id="b04ff-202">Danish</span></span>
- <span data-ttu-id="b04ff-203">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="b04ff-203">Dutch</span></span>
- <span data-ttu-id="b04ff-204">Inglés</span><span class="sxs-lookup"><span data-stu-id="b04ff-204">English</span></span>
- <span data-ttu-id="b04ff-205">Estonio</span><span class="sxs-lookup"><span data-stu-id="b04ff-205">Estonian</span></span>
- <span data-ttu-id="b04ff-206">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="b04ff-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="b04ff-207">Finés</span><span class="sxs-lookup"><span data-stu-id="b04ff-207">Finnish</span></span>
- <span data-ttu-id="b04ff-208">Francés</span><span class="sxs-lookup"><span data-stu-id="b04ff-208">French</span></span>
- <span data-ttu-id="b04ff-209">Gallego</span><span class="sxs-lookup"><span data-stu-id="b04ff-209">Galician</span></span>
- <span data-ttu-id="b04ff-210">Alemán</span><span class="sxs-lookup"><span data-stu-id="b04ff-210">German</span></span>
- <span data-ttu-id="b04ff-211">Griego</span><span class="sxs-lookup"><span data-stu-id="b04ff-211">Greek</span></span>
- <span data-ttu-id="b04ff-212">Gujarati</span><span class="sxs-lookup"><span data-stu-id="b04ff-212">Gujarati</span></span>
- <span data-ttu-id="b04ff-213">Hebreo</span><span class="sxs-lookup"><span data-stu-id="b04ff-213">Hebrew</span></span>
- <span data-ttu-id="b04ff-214">Hindi</span><span class="sxs-lookup"><span data-stu-id="b04ff-214">Hindi</span></span>
- <span data-ttu-id="b04ff-215">Húngaro</span><span class="sxs-lookup"><span data-stu-id="b04ff-215">Hungarian</span></span>
- <span data-ttu-id="b04ff-216">Islandés</span><span class="sxs-lookup"><span data-stu-id="b04ff-216">Icelandic</span></span>
- <span data-ttu-id="b04ff-217">Indonesio</span><span class="sxs-lookup"><span data-stu-id="b04ff-217">Indonesian</span></span>
- <span data-ttu-id="b04ff-218">Italiano</span><span class="sxs-lookup"><span data-stu-id="b04ff-218">Italian</span></span>
- <span data-ttu-id="b04ff-219">Japonés</span><span class="sxs-lookup"><span data-stu-id="b04ff-219">Japanese</span></span>
- <span data-ttu-id="b04ff-220">Kannada</span><span class="sxs-lookup"><span data-stu-id="b04ff-220">Kannada</span></span>
- <span data-ttu-id="b04ff-221">Kazajo</span><span class="sxs-lookup"><span data-stu-id="b04ff-221">Kazakh</span></span>
- <span data-ttu-id="b04ff-222">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="b04ff-222">Kiswahili</span></span>
- <span data-ttu-id="b04ff-223">Coreano</span><span class="sxs-lookup"><span data-stu-id="b04ff-223">Korean</span></span>
- <span data-ttu-id="b04ff-224">Letón</span><span class="sxs-lookup"><span data-stu-id="b04ff-224">Latvian</span></span>
- <span data-ttu-id="b04ff-225">Lituano</span><span class="sxs-lookup"><span data-stu-id="b04ff-225">Lithuanian</span></span>
- <span data-ttu-id="b04ff-226">Malayo (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="b04ff-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="b04ff-227">Malayo (Malasia)</span><span class="sxs-lookup"><span data-stu-id="b04ff-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="b04ff-228">Malayalam</span><span class="sxs-lookup"><span data-stu-id="b04ff-228">Malayalam</span></span>
- <span data-ttu-id="b04ff-229">Maratí</span><span class="sxs-lookup"><span data-stu-id="b04ff-229">Marathi</span></span>
- <span data-ttu-id="b04ff-230">Noruego (Bokmal)</span><span class="sxs-lookup"><span data-stu-id="b04ff-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="b04ff-231">Noruego (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="b04ff-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="b04ff-232">Odia</span><span class="sxs-lookup"><span data-stu-id="b04ff-232">Oriya</span></span>
- <span data-ttu-id="b04ff-233">Persa</span><span class="sxs-lookup"><span data-stu-id="b04ff-233">Persian</span></span>
- <span data-ttu-id="b04ff-234">Polaco</span><span class="sxs-lookup"><span data-stu-id="b04ff-234">Polish</span></span>
- <span data-ttu-id="b04ff-235">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="b04ff-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="b04ff-236">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="b04ff-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="b04ff-237">Rumano</span><span class="sxs-lookup"><span data-stu-id="b04ff-237">Romanian</span></span>
- <span data-ttu-id="b04ff-238">Ruso</span><span class="sxs-lookup"><span data-stu-id="b04ff-238">Russian</span></span>
- <span data-ttu-id="b04ff-239">Serbio (cirílico, Serbia)</span><span class="sxs-lookup"><span data-stu-id="b04ff-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="b04ff-240">Serbio (latino)</span><span class="sxs-lookup"><span data-stu-id="b04ff-240">Serbian (Latin)</span></span>
- <span data-ttu-id="b04ff-241">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="b04ff-241">Slovak</span></span>
- <span data-ttu-id="b04ff-242">Esloveno</span><span class="sxs-lookup"><span data-stu-id="b04ff-242">Slovenian</span></span>
- <span data-ttu-id="b04ff-243">Español</span><span class="sxs-lookup"><span data-stu-id="b04ff-243">Spanish</span></span>
- <span data-ttu-id="b04ff-244">Sueco</span><span class="sxs-lookup"><span data-stu-id="b04ff-244">Swedish</span></span>
- <span data-ttu-id="b04ff-245">Tamil</span><span class="sxs-lookup"><span data-stu-id="b04ff-245">Tamil</span></span>
- <span data-ttu-id="b04ff-246">Telugu</span><span class="sxs-lookup"><span data-stu-id="b04ff-246">Telugu</span></span>
- <span data-ttu-id="b04ff-247">Tailandés</span><span class="sxs-lookup"><span data-stu-id="b04ff-247">Thai</span></span>
- <span data-ttu-id="b04ff-248">Turco</span><span class="sxs-lookup"><span data-stu-id="b04ff-248">Turkish</span></span>
- <span data-ttu-id="b04ff-249">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="b04ff-249">Ukrainian</span></span>
- <span data-ttu-id="b04ff-250">Urdu</span><span class="sxs-lookup"><span data-stu-id="b04ff-250">Urdu</span></span>
- <span data-ttu-id="b04ff-251">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="b04ff-251">Vietnamese</span></span>
- <span data-ttu-id="b04ff-252">Galés</span><span class="sxs-lookup"><span data-stu-id="b04ff-252">Welsh</span></span>