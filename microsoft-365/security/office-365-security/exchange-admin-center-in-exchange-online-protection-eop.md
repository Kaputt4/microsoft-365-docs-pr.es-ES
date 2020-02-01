---
title: 'Centro de administración de Exchange en Exchange Online Protection '
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
description: El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 3a00b6b259c94e1446b6d6dc49b0f5daa9178cbd
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599407"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="8226b-103">Centro de administración de Exchange en Exchange Online Protection </span><span class="sxs-lookup"><span data-stu-id="8226b-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="8226b-104">El Centro de administración de Exchange (EAC) es la consola de administración basada en web para Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="8226b-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="8226b-105">¿Está buscando la versión de Exchange Server de este tema?</span><span class="sxs-lookup"><span data-stu-id="8226b-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="8226b-106">Consulte [centro de administración de Exchange en Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8226b-106">See [Exchange admin center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span></span>

<span data-ttu-id="8226b-107">¿Está buscando la versión de Exchange Online de este tema?</span><span class="sxs-lookup"><span data-stu-id="8226b-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="8226b-108">Vea [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8226b-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="8226b-109">Acceso a EAC</span><span class="sxs-lookup"><span data-stu-id="8226b-109">Accessing the EAC</span></span>

<span data-ttu-id="8226b-110">En la mayoría de los casos, los clientes de EOP obtendrán acceso al EAC a través del centro de administración 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8226b-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="8226b-111">Encontrará un vínculo a EOP en el menú desplegable del icono **Administrador**, que está al lado del icono **Yo**.</span><span class="sxs-lookup"><span data-stu-id="8226b-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="8226b-112">Haga clic en el icono **Administrador** y seleccione **Protección en línea de Exchange** en el menú desplegable para ir al EAC.</span><span class="sxs-lookup"><span data-stu-id="8226b-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span>

<span data-ttu-id="8226b-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span><span class="sxs-lookup"><span data-stu-id="8226b-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="8226b-116">Elementos comunes de la interfaz de usuario en EAC</span><span class="sxs-lookup"><span data-stu-id="8226b-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="8226b-117">En esta sección se describen los elementos de la interfaz de usuario del EAC.</span><span class="sxs-lookup"><span data-stu-id="8226b-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP: AdminCenter](../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="8226b-119">Panel de características</span><span class="sxs-lookup"><span data-stu-id="8226b-119">Feature Pane</span></span>

<span data-ttu-id="8226b-p105">Este es el primer nivel de navegación para la mayoría de las tareas que realizará en el EAC. El panel de características se organiza por áreas.</span><span class="sxs-lookup"><span data-stu-id="8226b-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="8226b-122">**Destinatarios**: aquí es donde podrá ver los usuarios internos y los contactos externos.</span><span class="sxs-lookup"><span data-stu-id="8226b-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="8226b-123">**Permisos**: aquí donde podrá administrar los roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="8226b-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="8226b-124">**Administración de cumplimiento**: aquí es donde se encuentran los registros de auditoría y los informes, como el informe de grupo de roles de administrador.</span><span class="sxs-lookup"><span data-stu-id="8226b-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="8226b-125">**Protección**: aquí es donde se administra la protección antimalware y contra correo no deseado para la organización, así como para administrar los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="8226b-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="8226b-126">**Flujo de correo**: aquí es donde se administran las reglas, los dominios aceptados y los conectores, así como el lugar en el que se realizará el seguimiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8226b-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="8226b-127">Pestañas</span><span class="sxs-lookup"><span data-stu-id="8226b-127">Tabs</span></span>

<span data-ttu-id="8226b-128">Las pestañas son el segundo nivel de navegación.</span><span class="sxs-lookup"><span data-stu-id="8226b-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="8226b-129">Las áreas de características contienen varias pestañas y cada área representa a una característica.</span><span class="sxs-lookup"><span data-stu-id="8226b-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="8226b-130">Barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="8226b-130">Toolbar</span></span>

<span data-ttu-id="8226b-p107">Al hacer clic en la mayoría de las pestañas, verá una barra de herramientas. La barra de herramientas tiene iconos que realizan una acción específica. La siguiente tabla describe los iconos y sus acciones.</span><span class="sxs-lookup"><span data-stu-id="8226b-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="8226b-134">**Icono**</span><span class="sxs-lookup"><span data-stu-id="8226b-134">**Icon**</span></span>|<span data-ttu-id="8226b-135">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="8226b-135">**Name**</span></span>|<span data-ttu-id="8226b-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="8226b-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Agregar icono](../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="8226b-138">Agregar, nuevo</span><span class="sxs-lookup"><span data-stu-id="8226b-138">Add, New</span></span>|<span data-ttu-id="8226b-p108">Utilice este icono para crear un nuevo objeto. Algunos de estos iconos tienen una flecha hacia abajo asociada donde puede hacer clic para mostrar objetos adicionales que puede crear.</span><span class="sxs-lookup"><span data-stu-id="8226b-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Icono Editar](../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="8226b-142">Editar</span><span class="sxs-lookup"><span data-stu-id="8226b-142">Edit</span></span>|<span data-ttu-id="8226b-143">Utilice este icono para editar un objeto.</span><span class="sxs-lookup"><span data-stu-id="8226b-143">Use this icon to edit an object.</span></span>|
|![Eliminar icono](../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="8226b-145">Eliminar</span><span class="sxs-lookup"><span data-stu-id="8226b-145">Delete</span></span>|<span data-ttu-id="8226b-p109">Utilice este icono para eliminar un objeto. Algunos iconos eliminados tienen una flecha hacia abajo donde puede hacer clic para mostrar opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="8226b-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![icono de Buscar](../media/ITPro-EAC-.gif)|<span data-ttu-id="8226b-149">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="8226b-149">Search</span></span>|<span data-ttu-id="8226b-150">Usar este icono para abrir una casilla de búsqueda donde puede escribir una frase de búsqueda para el objeto que desee encontrar.</span><span class="sxs-lookup"><span data-stu-id="8226b-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Icono Actualizar](../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="8226b-152">Actualizar</span><span class="sxs-lookup"><span data-stu-id="8226b-152">Refresh</span></span>|<span data-ttu-id="8226b-153">Utilice este icono para actualizar la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="8226b-153">Use this icon to refresh the list view.</span></span>|
|![Icono Más opciones](../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="8226b-155">Más opciones</span><span class="sxs-lookup"><span data-stu-id="8226b-155">More options</span></span>|<span data-ttu-id="8226b-p110">Use este icono para ver más acciones que puede realizar para los objetos de la pestaña. Por ejemplo, al hacer clic en este icono en **Destinatarios \> Usuarios**, se muestra la opción para realizar una **Búsqueda avanzada**.  </span><span class="sxs-lookup"><span data-stu-id="8226b-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Icono flecha arriba](../media/ITPro-EAC-UpArrowIcon.gif)![Icono flecha abajo](../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="8226b-160">Flecha hacia arriba y flecha hacia abajo</span><span class="sxs-lookup"><span data-stu-id="8226b-160">Up arrow and down arrow</span></span>|<span data-ttu-id="8226b-161">Utilice estos iconos para mover la prioridad de un objeto hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="8226b-161">Use these icons to move an object's priority up or down.</span></span>|
|![Icono de quitar](../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="8226b-163">Quitar</span><span class="sxs-lookup"><span data-stu-id="8226b-163">Remove</span></span>|<span data-ttu-id="8226b-164">Utilice este icono para quitar objetos de la lista.</span><span class="sxs-lookup"><span data-stu-id="8226b-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="8226b-165">Vista de lista</span><span class="sxs-lookup"><span data-stu-id="8226b-165">List View</span></span>

<span data-ttu-id="8226b-p111">Cuando seleccione una pestaña, en la mayoría de los casos verá la vista de lista. El límite de visualización de la vista de lista del EAC es de 10.000 objetos aproximadamente. Además, la paginación se incluye para que pueda paginar los resultados.</span><span class="sxs-lookup"><span data-stu-id="8226b-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="8226b-169">panel Detalles</span><span class="sxs-lookup"><span data-stu-id="8226b-169">Details Pane</span></span>

<span data-ttu-id="8226b-p112">Cuando seleccione un objeto de la vista de lista, la información acerca del objeto se muestra en el panel de detalles. En algunos casos, el panel de detalles incluye tareas de administración.</span><span class="sxs-lookup"><span data-stu-id="8226b-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="8226b-172">Mosaico Yo y Ayuda</span><span class="sxs-lookup"><span data-stu-id="8226b-172">Me tile and Help</span></span>

<span data-ttu-id="8226b-p113">El mosaico **Yo** permite cerrar sesión en el EAC e iniciar sesión como un usuario diferente. Desde el menú desplegable en **Ayuda**![Icono de ayuda](../media/ITPro-EAC-HelpIcon.gif), puede realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8226b-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="8226b-175">**Ayuda**: haga ![clic en](../media/ITPro-EAC-HelpIcon.gif) el icono ayuda para ver el contenido de la ayuda en línea.</span><span class="sxs-lookup"><span data-stu-id="8226b-175">**Help**: Click ![Help Icon](../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="8226b-176">**Deshabilitar la burbuja de ayuda**: la burbuja de ayuda muestra la ayuda contextual de los campos cuando se crea o edita un objeto.</span><span class="sxs-lookup"><span data-stu-id="8226b-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="8226b-177">Puede desactivar el globo de Ayuda o activarlo si estaba deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="8226b-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="8226b-178">**Copyright**: haga clic en este vínculo para leer el aviso de copyright de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="8226b-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="8226b-179">**Privacidad**: haga clic para leer la Directiva de privacidad de Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="8226b-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="8226b-180">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="8226b-180">Supported Browsers</span></span>

<span data-ttu-id="8226b-181">Para conseguir la mejor experiencia con EAC, le recomendamos que use siempre la versión más actualizada de los exploradores, clientes de Office y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8226b-181">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="8226b-182">También le recomendamos que instale las actualizaciones de software cuando estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="8226b-182">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="8226b-183">Para obtener más información acerca de los exploradores compatibles y los requisitos del sistema para el servicio, vea [System Requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="8226b-183">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="8226b-184">Idiomas admitidos en EOP</span><span class="sxs-lookup"><span data-stu-id="8226b-184">Supported languages in EOP</span></span>

<span data-ttu-id="8226b-185">Los siguientes idiomas están disponibles y son compatibles con Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="8226b-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="8226b-186">Amhárico</span><span class="sxs-lookup"><span data-stu-id="8226b-186">Amharic</span></span>

- <span data-ttu-id="8226b-187">Árabe</span><span class="sxs-lookup"><span data-stu-id="8226b-187">Arabic</span></span>

- <span data-ttu-id="8226b-188">Vasco (Euskera)</span><span class="sxs-lookup"><span data-stu-id="8226b-188">Basque (Basque)</span></span>

- <span data-ttu-id="8226b-189">Bengalí (India)</span><span class="sxs-lookup"><span data-stu-id="8226b-189">Bengali (India)</span></span>

- <span data-ttu-id="8226b-190">Búlgaro</span><span class="sxs-lookup"><span data-stu-id="8226b-190">Bulgarian</span></span>

- <span data-ttu-id="8226b-191">Catalán</span><span class="sxs-lookup"><span data-stu-id="8226b-191">Catalan</span></span>

- <span data-ttu-id="8226b-192">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="8226b-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="8226b-193">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="8226b-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="8226b-194">Croata</span><span class="sxs-lookup"><span data-stu-id="8226b-194">Croatian</span></span>

- <span data-ttu-id="8226b-195">Checo</span><span class="sxs-lookup"><span data-stu-id="8226b-195">Czech</span></span>

- <span data-ttu-id="8226b-196">Danés</span><span class="sxs-lookup"><span data-stu-id="8226b-196">Danish</span></span>

- <span data-ttu-id="8226b-197">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="8226b-197">Dutch</span></span>

- <span data-ttu-id="8226b-198">Neerlandés</span><span class="sxs-lookup"><span data-stu-id="8226b-198">Dutch</span></span>

- <span data-ttu-id="8226b-199">Inglés</span><span class="sxs-lookup"><span data-stu-id="8226b-199">English</span></span>

- <span data-ttu-id="8226b-200">Estonio</span><span class="sxs-lookup"><span data-stu-id="8226b-200">Estonian</span></span>

- <span data-ttu-id="8226b-201">Filipino (Filipinas)</span><span class="sxs-lookup"><span data-stu-id="8226b-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="8226b-202">Finés</span><span class="sxs-lookup"><span data-stu-id="8226b-202">Finnish</span></span>

- <span data-ttu-id="8226b-203">Francés</span><span class="sxs-lookup"><span data-stu-id="8226b-203">French</span></span>

- <span data-ttu-id="8226b-204">Gallego</span><span class="sxs-lookup"><span data-stu-id="8226b-204">Galician</span></span>

- <span data-ttu-id="8226b-205">Alemán</span><span class="sxs-lookup"><span data-stu-id="8226b-205">German</span></span>

- <span data-ttu-id="8226b-206">Griego</span><span class="sxs-lookup"><span data-stu-id="8226b-206">Greek</span></span>

- <span data-ttu-id="8226b-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="8226b-207">Gujarati</span></span>

- <span data-ttu-id="8226b-208">Hebreo</span><span class="sxs-lookup"><span data-stu-id="8226b-208">Hebrew</span></span>

- <span data-ttu-id="8226b-209">Hindi</span><span class="sxs-lookup"><span data-stu-id="8226b-209">Hindi</span></span>

- <span data-ttu-id="8226b-210">Húngaro</span><span class="sxs-lookup"><span data-stu-id="8226b-210">Hungarian</span></span>

- <span data-ttu-id="8226b-211">Islandés</span><span class="sxs-lookup"><span data-stu-id="8226b-211">Icelandic</span></span>

- <span data-ttu-id="8226b-212">Indonesio</span><span class="sxs-lookup"><span data-stu-id="8226b-212">Indonesian</span></span>

- <span data-ttu-id="8226b-213">Italiano</span><span class="sxs-lookup"><span data-stu-id="8226b-213">Italian</span></span>

- <span data-ttu-id="8226b-214">Japonés</span><span class="sxs-lookup"><span data-stu-id="8226b-214">Japanese</span></span>

- <span data-ttu-id="8226b-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="8226b-215">Kannada</span></span>

- <span data-ttu-id="8226b-216">Kazajo</span><span class="sxs-lookup"><span data-stu-id="8226b-216">Kazakh</span></span>

- <span data-ttu-id="8226b-217">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="8226b-217">Kiswahili</span></span>

- <span data-ttu-id="8226b-218">Coreano</span><span class="sxs-lookup"><span data-stu-id="8226b-218">Korean</span></span>

- <span data-ttu-id="8226b-219">Letón</span><span class="sxs-lookup"><span data-stu-id="8226b-219">Latvian</span></span>

- <span data-ttu-id="8226b-220">Lituano</span><span class="sxs-lookup"><span data-stu-id="8226b-220">Lithuanian</span></span>

- <span data-ttu-id="8226b-221">Malayo (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="8226b-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="8226b-222">Malayo (Malasia)</span><span class="sxs-lookup"><span data-stu-id="8226b-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="8226b-223">Malayalam</span><span class="sxs-lookup"><span data-stu-id="8226b-223">Malayalam</span></span>

- <span data-ttu-id="8226b-224">Maratí</span><span class="sxs-lookup"><span data-stu-id="8226b-224">Marathi</span></span>

- <span data-ttu-id="8226b-225">Noruego (Bokmal)</span><span class="sxs-lookup"><span data-stu-id="8226b-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="8226b-226">Noruego (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="8226b-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="8226b-227">Odia</span><span class="sxs-lookup"><span data-stu-id="8226b-227">Oriya</span></span>

- <span data-ttu-id="8226b-228">Persa</span><span class="sxs-lookup"><span data-stu-id="8226b-228">Persian</span></span>

- <span data-ttu-id="8226b-229">Polaco</span><span class="sxs-lookup"><span data-stu-id="8226b-229">Polish</span></span>

- <span data-ttu-id="8226b-230">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="8226b-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="8226b-231">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="8226b-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="8226b-232">Rumano</span><span class="sxs-lookup"><span data-stu-id="8226b-232">Romanian</span></span>

- <span data-ttu-id="8226b-233">Ruso</span><span class="sxs-lookup"><span data-stu-id="8226b-233">Russian</span></span>

- <span data-ttu-id="8226b-234">Serbio (cirílico, Serbia)</span><span class="sxs-lookup"><span data-stu-id="8226b-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="8226b-235">Serbio (latino)</span><span class="sxs-lookup"><span data-stu-id="8226b-235">Serbian (Latin)</span></span>

- <span data-ttu-id="8226b-236">Eslovaco</span><span class="sxs-lookup"><span data-stu-id="8226b-236">Slovak</span></span>

- <span data-ttu-id="8226b-237">Esloveno</span><span class="sxs-lookup"><span data-stu-id="8226b-237">Slovenian</span></span>

- <span data-ttu-id="8226b-238">Español</span><span class="sxs-lookup"><span data-stu-id="8226b-238">Spanish</span></span>

- <span data-ttu-id="8226b-239">Sueco</span><span class="sxs-lookup"><span data-stu-id="8226b-239">Swedish</span></span>

- <span data-ttu-id="8226b-240">Tamil</span><span class="sxs-lookup"><span data-stu-id="8226b-240">Tamil</span></span>

- <span data-ttu-id="8226b-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="8226b-241">Telugu</span></span>

- <span data-ttu-id="8226b-242">Tailandés</span><span class="sxs-lookup"><span data-stu-id="8226b-242">Thai</span></span>

- <span data-ttu-id="8226b-243">Turco</span><span class="sxs-lookup"><span data-stu-id="8226b-243">Turkish</span></span>

- <span data-ttu-id="8226b-244">Ucraniano</span><span class="sxs-lookup"><span data-stu-id="8226b-244">Ukrainian</span></span>

- <span data-ttu-id="8226b-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="8226b-245">Urdu</span></span>

- <span data-ttu-id="8226b-246">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="8226b-246">Vietnamese</span></span>

- <span data-ttu-id="8226b-247">Galés</span><span class="sxs-lookup"><span data-stu-id="8226b-247">Welsh</span></span>


