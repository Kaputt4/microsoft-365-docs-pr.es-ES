---
title: 'Migrar archivos de Google a Microsoft 365 para empresas '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo migrar archivos de Google a Microsoft 365 para empresas mediante Mover.
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928203"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="a114d-103">Migrar archivos de Google a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a114d-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="a114d-104">Cuando te muevas a Microsoft 365 para empresas, querrás migrar los archivos desde Google Drive.</span><span class="sxs-lookup"><span data-stu-id="a114d-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="a114d-105">Puedes usar la aplicación Mover para mover archivos de unidades personales y compartidas.</span><span class="sxs-lookup"><span data-stu-id="a114d-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="a114d-106">Para obtener más información, vea [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="a114d-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="a114d-107">Mover realizará una copia de los archivos y moverá las copias a Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="a114d-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="a114d-108">Los archivos originales también permanecerán en Google Drives.</span><span class="sxs-lookup"><span data-stu-id="a114d-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a114d-109">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a114d-109">Before you start</span></span>

<span data-ttu-id="a114d-110">Todos los usuarios deben haber iniciado sesión en Microsoft 365 para empresas y configurar su OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="a114d-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="a114d-111">Para ello, vaya a [office.com,](https://office.com)inicie sesión con sus credenciales de Microsft 365 para empresas y, a continuación, elija OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a114d-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="a114d-112">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="a114d-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="a114d-113">Instalar Mover</span><span class="sxs-lookup"><span data-stu-id="a114d-113">Install Mover</span></span>

1. <span data-ttu-id="a114d-114">Inicie sesión en la consola de administración de Google Workspace [en admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="a114d-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="a114d-115">Elija **Aplicaciones,** **Aplicaciones de Google Workspace Marketplace** y, a continuación, Agregar aplicación a la lista de instalación de **dominio.**</span><span class="sxs-lookup"><span data-stu-id="a114d-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="a114d-116">Busque Mover y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="a114d-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="a114d-117">Elija **Instalar dominio** y, a **continuación, continuar.**</span><span class="sxs-lookup"><span data-stu-id="a114d-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="a114d-118">Revise los permisos, active la casilla para aceptar los términos y, a continuación, seleccione Permitir **,** elija **Siguiente** y, a continuación, **Listo.**</span><span class="sxs-lookup"><span data-stu-id="a114d-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="a114d-119">Crear conectores y ejecutar la migración</span><span class="sxs-lookup"><span data-stu-id="a114d-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="a114d-120">Vuelva a las **aplicaciones de Google Workspace Marketplace.**</span><span class="sxs-lookup"><span data-stu-id="a114d-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="a114d-121">Actualice el explorador y seleccione la **aplicación Mover.**</span><span class="sxs-lookup"><span data-stu-id="a114d-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="a114d-122">Desplácese hacia abajo y elija el vínculo de navegación universal.</span><span class="sxs-lookup"><span data-stu-id="a114d-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="a114d-123">Seleccione **Autorizar nuevo conector,** **busque G Suite (administrador)** y elija **Autorizar.**</span><span class="sxs-lookup"><span data-stu-id="a114d-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="a114d-124">Cambie el **nombre para mostrar,** si lo desea, seleccione **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="a114d-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="a114d-125">Elija una cuenta de administrador de Google, revise los permisos y, a continuación, **seleccione Permitir.**</span><span class="sxs-lookup"><span data-stu-id="a114d-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="a114d-126">Mover muestra el número de unidades de equipo y las unidades de usuario que ha detectado.</span><span class="sxs-lookup"><span data-stu-id="a114d-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="a114d-127">En **Seleccionar destino,** elija **Autorizar nuevo conector,** **busque Office 365** y seleccione **Autorizar.**</span><span class="sxs-lookup"><span data-stu-id="a114d-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="a114d-128">Para conceder permisos a la aplicación Mover en Azure Active Directory, vaya a [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="a114d-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="a114d-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span><span class="sxs-lookup"><span data-stu-id="a114d-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="a114d-130">Elija su cuenta, revise los permisos y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a114d-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="a114d-131">Elija **Propiedades** y compruebe que **la asignación de usuario necesaria está** activada.</span><span class="sxs-lookup"><span data-stu-id="a114d-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="a114d-132">Vuelva a la aplicación Mover, cambie **el** nombre para mostrar, si lo desea, elija **Autorizar** y, a continuación, seleccione una cuenta de administrador de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a114d-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="a114d-133">Mover le informará sobre el número de sitios de SharePoint Online (o SPO) y los usuarios que ha detectado.</span><span class="sxs-lookup"><span data-stu-id="a114d-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="a114d-134">Elija **Continuar configuración de migración,** agregar **usuarios** y, a continuación, detectar y agregar **usuarios automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="a114d-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="a114d-135">La aplicación Mover intentará asignar unidades de la ruta de origen de Google a la ruta de destino en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a114d-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="a114d-136">Si una unidad no se asigna automáticamente, agregue su ruta de destino a un archivo CSV, que usaremos más adelante para migrar la unidad compartida a una biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a114d-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="a114d-137">En este caso, hemos agregado un sitio de SharePoint denominado Archivos migrados y hemos tomado nota de la dirección URL de la página de documentos.</span><span class="sxs-lookup"><span data-stu-id="a114d-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="a114d-138">A continuación, creamos un archivo CSV con el formato ruta de origen, ruta de destino y etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a114d-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="a114d-139">Para obtener más [información, aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="a114d-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="a114d-140">Al agregar la dirección URL de la ruta de destino, quite todo después de Documentos compartidos, por ejemplo, esta dirección URL completa no funcionará: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="a114d-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="a114d-141">Cambie el valor a `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`.</span><span class="sxs-lookup"><span data-stu-id="a114d-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="a114d-142">Una vez que el archivo CSV esté listo, seleccione **Acciones de migración,** **Agregar** a migración, Elija un archivo **para cargar.**</span><span class="sxs-lookup"><span data-stu-id="a114d-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="a114d-143">Navegue hasta el archivo CSV, selecciónelo y, a continuación, **elija Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a114d-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="a114d-144">Seleccione las unidades de usuario cuyos archivos desea migrar y, a continuación, elija **Iniciar migración de usuarios.**</span><span class="sxs-lookup"><span data-stu-id="a114d-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="a114d-145">Revise la información de migración, elija cuándo iniciar la migración, acepte los Términos y **condiciones** y, a continuación, **seleccione Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a114d-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="a114d-146">La aplicación Mover le informará cuando se complete el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="a114d-146">The Mover app will inform you when the migration process is complete.</span></span>