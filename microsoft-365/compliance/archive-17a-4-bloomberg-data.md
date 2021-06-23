---
title: Configurar un conector para archivar datos de Bloomberg en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Obtenga información sobre cómo configurar y usar un conector DataParser de Bloomberg de 17a-4 para importar y archivar datos de Bloomberg en Microsoft 365.
ms.openlocfilehash: 7fcc02384ce7bea6b9903fddef1256b97b8e340c
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096487"
---
# <a name="set-up-a-connector-to-archive-bloomberg-data-preview"></a><span data-ttu-id="3b48f-103">Configurar un conector para archivar datos de Bloomberg (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3b48f-103">Set up a connector to archive Bloomberg data (preview)</span></span>

<span data-ttu-id="3b48f-104">Use [Bloomberg DataParser](https://www.17a-4.com/Bloomberg-dataparser/) de 17a-4 LLC para importar y archivar datos de Bloomberg a buzones de usuario de su Microsoft 365 organización.</span><span class="sxs-lookup"><span data-stu-id="3b48f-104">Use the [Bloomberg DataParser](https://www.17a-4.com/Bloomberg-dataparser/) from 17a-4 LLC to import and archive data from Bloomberg to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3b48f-105">DataParser incluye un conector de Bloomberg configurado para capturar elementos de un origen de datos de terceros e importar esos elementos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b48f-105">The DataParser includes a Bloomberg connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="3b48f-106">El conector DataParser de Bloomberg convierte los datos de Bloomberg en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b48f-106">The Bloomberg DataParser connector converts Bloomberg data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="3b48f-107">Una vez que los datos de Bloomberg se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b48f-107">After Bloomberg data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="3b48f-108">El uso de un conector de Bloomberg para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.</span><span class="sxs-lookup"><span data-stu-id="3b48f-108">Using a Bloomberg connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-bloomberg-data"></a><span data-ttu-id="3b48f-109">Información general sobre el archivado de datos de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3b48f-109">Overview of archiving Bloomberg data</span></span>

<span data-ttu-id="3b48f-110">En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar datos de Bloomberg en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b48f-110">The following overview explains the process of using a data connector to archive Bloomberg data in Microsoft 365.</span></span>

![Flujo de trabajo de archivado para datos de Bloomberg de 17a-4](../media/BloombergDataParserConnectorWorkflow.png)

1. <span data-ttu-id="3b48f-112">Su organización trabaja con 17a-4 para configurar el DataParser de Bloomberg.</span><span class="sxs-lookup"><span data-stu-id="3b48f-112">Your organization works with 17a-4 to set up and configure the Bloomberg DataParser.</span></span>

2. <span data-ttu-id="3b48f-113">El DataParser recopila los elementos de Bloomberg de forma regular.</span><span class="sxs-lookup"><span data-stu-id="3b48f-113">On a regular basis, Bloomberg items are collected by the DataParser.</span></span> <span data-ttu-id="3b48f-114">DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3b48f-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="3b48f-115">El conector DataParser de Bloomberg que crea en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación Azure Storage segura en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b48f-115">The Bloomberg DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3b48f-116">Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Bloomberg DataParser** en los buzones de usuario y los elementos de Bloomberg se importan a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="3b48f-116">A subfolder in the Inbox folder named **Bloomberg DataParser** is created in the user mailboxes, and the Bloomberg items are imported to that folder.</span></span> <span data-ttu-id="3b48f-117">El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.*</span><span class="sxs-lookup"><span data-stu-id="3b48f-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="3b48f-118">Cada elemento de Bloomberg contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.</span><span class="sxs-lookup"><span data-stu-id="3b48f-118">Every Bloomberg item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="3b48f-119">Antes de configurar un conector</span><span class="sxs-lookup"><span data-stu-id="3b48f-119">Before you set up a connector</span></span>

- <span data-ttu-id="3b48f-120">Crear una cuenta dataParser para conectores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b48f-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="3b48f-121">Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="3b48f-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="3b48f-122">Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="3b48f-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3b48f-123">El usuario que crea el conector DataParser de Bloomberg en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De exportación de importación de buzones en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b48f-123">The user who creates the Bloomberg DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3b48f-124">Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b48f-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3b48f-125">De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b48f-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="3b48f-126">Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3b48f-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3b48f-127">O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros.</span><span class="sxs-lookup"><span data-stu-id="3b48f-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3b48f-128">Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="3b48f-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-bloomberg-dataparser-connector"></a><span data-ttu-id="3b48f-129">Paso 1: Configurar un conector DataParser de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3b48f-129">Step 1: Set up a Bloomberg DataParser connector</span></span>

<span data-ttu-id="3b48f-130">El primer paso es obtener acceso a la página Conectores de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para los datos de Bloomberg.</span><span class="sxs-lookup"><span data-stu-id="3b48f-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Bloomberg data.</span></span>

1. <span data-ttu-id="3b48f-131">Vaya a <https://compliance.microsoft.com> y, a continuación, haga clic **en Conectores de datos**  >  **Bloomberg DataParser**.</span><span class="sxs-lookup"><span data-stu-id="3b48f-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Bloomberg DataParser**.</span></span>

2. <span data-ttu-id="3b48f-132">En la página de descripción del producto **DataParser de Bloomberg,** haga clic **en Agregar conector**.</span><span class="sxs-lookup"><span data-stu-id="3b48f-132">On the **Bloomberg DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3b48f-133">En la **página Términos de** servicio, haga clic **en Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3b48f-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3b48f-134">Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3b48f-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="3b48f-135">Inicia sesión en tu cuenta de 17a-4 y completa los pasos del Asistente para la conexión de Bloomberg DataParser.</span><span class="sxs-lookup"><span data-stu-id="3b48f-135">Sign in to your 17a-4 account and complete the steps in the Bloomberg DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-bloomberg-dataparser-connector"></a><span data-ttu-id="3b48f-136">Paso 2: Configurar el conector DataParser de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3b48f-136">Step 2: Configure the Bloomberg DataParser connector</span></span>

<span data-ttu-id="3b48f-137">Trabaje con la compatibilidad de 17a-4 para configurar el conector DataParser de Bloomberg.</span><span class="sxs-lookup"><span data-stu-id="3b48f-137">Work with 17a-4 Support to configure the Bloomberg DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="3b48f-138">Paso 3: Asignar usuarios</span><span class="sxs-lookup"><span data-stu-id="3b48f-138">Step 3: Map users</span></span>

<span data-ttu-id="3b48f-139">El conector DataParser de Bloomberg asignará automáticamente a los usuarios a sus Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b48f-139">The Bloomberg DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-bloomberg-dataparser-connector"></a><span data-ttu-id="3b48f-140">Paso 4: Supervisar el conector DataParser de Bloomberg</span><span class="sxs-lookup"><span data-stu-id="3b48f-140">Step 4: Monitor the Bloomberg DataParser connector</span></span>

<span data-ttu-id="3b48f-141">Después de crear un conector DataParser de Bloomberg, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b48f-141">After you create a Bloomberg DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3b48f-142">Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="3b48f-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3b48f-143">Haga **clic** en la pestaña Conectores y, a continuación, seleccione el conector DataParser de Bloomberg que creó para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.</span><span class="sxs-lookup"><span data-stu-id="3b48f-143">Click the **Connectors** tab and then select the Bloomberg DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3b48f-144">En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector.</span><span class="sxs-lookup"><span data-stu-id="3b48f-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3b48f-145">Este registro contiene datos que se han importado a la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b48f-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3b48f-146">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="3b48f-146">Known issues</span></span>

<span data-ttu-id="3b48f-147">En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB.</span><span class="sxs-lookup"><span data-stu-id="3b48f-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="3b48f-148">La compatibilidad con elementos más grandes estará disponible en una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="3b48f-148">Support for larger items will be available at a later date.</span></span>
