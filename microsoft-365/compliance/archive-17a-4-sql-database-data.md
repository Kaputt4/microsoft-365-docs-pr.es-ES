---
title: Configurar un conector para archivar SQL datos en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector DataParser de 17a-4 SQL para importar y archivar SQL datos en Microsoft 365.
ms.openlocfilehash: 51fd433ad072ba5afe0b314d7b61041728337240
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137672"
---
# <a name="set-up-a-connector-to-archive-sql-data-preview"></a><span data-ttu-id="3447e-103">Configurar un conector para archivar SQL datos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="3447e-103">Set up a connector to archive SQL data (preview)</span></span>

<span data-ttu-id="3447e-104">Use [el SQL DataParser](https://www.17a-4.com/sql-dataparser/) de 17a-4 LLC para importar y archivar datos de una base de datos de SQL a buzones de usuario de su Microsoft 365 organización.</span><span class="sxs-lookup"><span data-stu-id="3447e-104">Use the [SQL DataParser](https://www.17a-4.com/sql-dataparser/) from 17a-4 LLC to import and archive data from a SQL database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3447e-105">DataParser incluye un conector SQL que está configurado para capturar elementos de un origen de datos de terceros e importar esos elementos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3447e-105">The DataParser includes a SQL connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="3447e-106">El SQL DataParser convierte los SQL a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3447e-106">The SQL DataParser connector converts SQL data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="3447e-107">Después SQL datos se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="3447e-107">After SQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="3447e-108">El uso de un SQL para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.</span><span class="sxs-lookup"><span data-stu-id="3447e-108">Using a SQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-sql-data"></a><span data-ttu-id="3447e-109">Información general sobre el archivado SQL datos</span><span class="sxs-lookup"><span data-stu-id="3447e-109">Overview of archiving SQL data</span></span>

<span data-ttu-id="3447e-110">En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar SQL datos en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3447e-110">The following overview explains the process of using a data connector to archive SQL data in Microsoft 365.</span></span>

![Flujo de trabajo de archivado SQL datos de 17a-4](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. <span data-ttu-id="3447e-112">Su organización funciona con 17a-4 para configurar y configurar el SQL DataParser.</span><span class="sxs-lookup"><span data-stu-id="3447e-112">Your organization works with 17a-4 to set up and configure the SQL DataParser.</span></span>

2. <span data-ttu-id="3447e-113">El DataParser recopila SQL elementos de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="3447e-113">On a regular basis, SQL items are collected by the DataParser.</span></span> <span data-ttu-id="3447e-114">DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3447e-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="3447e-115">El SQL DataParser que crea en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3447e-115">The SQL DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3447e-116">Una subcarpeta de la carpeta Bandeja de entrada denominada **SQL DataParser** se crea en los buzones de usuario y los elementos SQL se importan a esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="3447e-116">A subfolder in the Inbox folder named **SQL DataParser** is created in the user mailboxes, and the SQL items are imported to that folder.</span></span> <span data-ttu-id="3447e-117">El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.*</span><span class="sxs-lookup"><span data-stu-id="3447e-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="3447e-118">Cada SQL contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.</span><span class="sxs-lookup"><span data-stu-id="3447e-118">Every SQL item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="3447e-119">Antes de configurar un conector</span><span class="sxs-lookup"><span data-stu-id="3447e-119">Before you set up a connector</span></span>

- <span data-ttu-id="3447e-120">Crear una cuenta dataParser para conectores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3447e-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="3447e-121">Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="3447e-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="3447e-122">Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="3447e-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3447e-123">El usuario que crea el conector dataParser de SQL en el paso 1 (y lo completa en el paso 3) debe asignarse al rol De exportación de importación de buzones en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3447e-123">The user who creates the SQL DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3447e-124">Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3447e-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3447e-125">De forma predeterminada, este rol no se asigna a un grupo de roles en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3447e-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="3447e-126">Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3447e-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3447e-127">O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros.</span><span class="sxs-lookup"><span data-stu-id="3447e-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3447e-128">Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="3447e-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-sql-dataparser-connector"></a><span data-ttu-id="3447e-129">Paso 1: Configurar un conector SQL DataParser</span><span class="sxs-lookup"><span data-stu-id="3447e-129">Step 1: Set up a SQL DataParser connector</span></span>

<span data-ttu-id="3447e-130">El primer paso es obtener acceso a la página Conectores de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para SQL datos.</span><span class="sxs-lookup"><span data-stu-id="3447e-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for SQL data.</span></span>

1. <span data-ttu-id="3447e-131">Vaya a y, a continuación, haga clic <https://compliance.microsoft.com> en   >  **Conectores SQL DataParser**.</span><span class="sxs-lookup"><span data-stu-id="3447e-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **SQL DataParser**.</span></span>

2. <span data-ttu-id="3447e-132">En la página SQL descripción del **producto DataParser,** haga clic **en Agregar conector**.</span><span class="sxs-lookup"><span data-stu-id="3447e-132">On the **SQL DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3447e-133">En la **página Términos de** servicio, haga clic **en Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3447e-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3447e-134">Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3447e-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="3447e-135">Inicie sesión en su cuenta de 17a-4 y complete los pasos del asistente para la conexión SQL DataParser.</span><span class="sxs-lookup"><span data-stu-id="3447e-135">Sign in to your 17a-4 account and complete the steps in the SQL DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-sql-dataparser-connector"></a><span data-ttu-id="3447e-136">Paso 2: Configurar el conector SQL DataParser</span><span class="sxs-lookup"><span data-stu-id="3447e-136">Step 2: Configure the SQL DataParser connector</span></span>

<span data-ttu-id="3447e-137">Trabaje con la compatibilidad de 17a-4 para configurar el SQL DataParser.</span><span class="sxs-lookup"><span data-stu-id="3447e-137">Work with 17a-4 Support to configure the SQL DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="3447e-138">Paso 3: Asignar usuarios</span><span class="sxs-lookup"><span data-stu-id="3447e-138">Step 3: Map users</span></span>

<span data-ttu-id="3447e-139">El SQL DataParser asigna automáticamente a los usuarios a sus direcciones Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3447e-139">The SQL DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-sql-dataparser-connector"></a><span data-ttu-id="3447e-140">Paso 4: Supervisar el conector SQL DataParser</span><span class="sxs-lookup"><span data-stu-id="3447e-140">Step 4: Monitor the SQL DataParser connector</span></span>

<span data-ttu-id="3447e-141">Después de crear un SQL DataParser, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3447e-141">After you create a SQL DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3447e-142">Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="3447e-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3447e-143">Haga clic en la pestaña **Conectores** y, a continuación, seleccione el SQL DataParser que creó para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.</span><span class="sxs-lookup"><span data-stu-id="3447e-143">Click the **Connectors** tab and then select the SQL DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3447e-144">En **Estado del conector con origen,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector.</span><span class="sxs-lookup"><span data-stu-id="3447e-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3447e-145">Este registro contiene datos que se han importado a la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3447e-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3447e-146">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="3447e-146">Known issues</span></span>

<span data-ttu-id="3447e-147">En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB.</span><span class="sxs-lookup"><span data-stu-id="3447e-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="3447e-148">La compatibilidad con elementos más grandes estará disponible en una fecha posterior.</span><span class="sxs-lookup"><span data-stu-id="3447e-148">Support for larger items will be available at a later date.</span></span>
