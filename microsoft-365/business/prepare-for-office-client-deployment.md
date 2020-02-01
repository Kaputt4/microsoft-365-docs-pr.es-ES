---
title: Prepararse para una implementación del cliente de Office mediante Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas.
ms.openlocfilehash: fa5b2ce1852ebdb1e76c1fa844793fee56af3d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593627"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="06e2e-103">Prepararse para una implementación del cliente de Office mediante Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="06e2e-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="06e2e-104">Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente</span><span class="sxs-lookup"><span data-stu-id="06e2e-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="06e2e-105">Puede usar Microsoft 365 Business para instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas con las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="06e2e-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="06e2e-106">La instalación automática funciona mejor si el equipo del usuario final está en Windows 10 Business y:</span><span class="sxs-lookup"><span data-stu-id="06e2e-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="06e2e-107">No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).</span><span class="sxs-lookup"><span data-stu-id="06e2e-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="06e2e-108">o</span><span class="sxs-lookup"><span data-stu-id="06e2e-108">or</span></span>
    
- <span data-ttu-id="06e2e-109">Tiene instalada una versión existente de Office de Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="06e2e-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="06e2e-110">Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook).</span><span class="sxs-lookup"><span data-stu-id="06e2e-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="06e2e-111">Si ve **actualizaciones de Office** , tal como se muestra en la siguiente figura, la instalación se realizó mediante hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="06e2e-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="06e2e-113">**Quién se beneficia de tener esta característica**</span><span class="sxs-lookup"><span data-stu-id="06e2e-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="06e2e-114">El usuario final cuyo PC:</span><span class="sxs-lookup"><span data-stu-id="06e2e-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="06e2e-115">**Tenga** una licencia de usuario de Windows 10 Business, una licencia activa de Microsoft 365 Business, Windows 10 Creators Update y se haya unido a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06e2e-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="06e2e-116">**No tiene** aplicaciones de Office de 64 bits (por ejemplo: Word, Excel y PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="06e2e-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="06e2e-117">Si se necesitan aplicaciones de Office de 64-bit, esta característica no es una buena opción porque no se admite la activación de una versión de Office de 64 bits 2016 de hacer clic y ejecutar desde la consola de administración empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06e2e-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="06e2e-118">**No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project).</span><span class="sxs-lookup"><span data-stu-id="06e2e-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="06e2e-119">Microsoft 365 Business actualiza Office a la versión de hacer clic y ejecutar de Office 2016 y no funciona con aplicaciones independientes MSI de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="06e2e-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="06e2e-120">En la tabla siguiente se muestra la acción que los usuarios finales o administradores deben realizar, en función de su estado de inicio, para tener una versión de hacer clic y ejecutar de la implementación de Office de 32 bits satisfactoria desde la consola del Administrador corporativo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="06e2e-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="06e2e-121">**Estado inicial de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="06e2e-121">**Starting Office install status**</span></span>|<span data-ttu-id="06e2e-122">**Acción que se realiza antes de que se instale Microsoft 365 Business Office**</span><span class="sxs-lookup"><span data-stu-id="06e2e-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="06e2e-123">**Estado final**</span><span class="sxs-lookup"><span data-stu-id="06e2e-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06e2e-124">Ningún conjunto de aplicaciones de Office instalado</span><span class="sxs-lookup"><span data-stu-id="06e2e-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="06e2e-125">Ninguno</span><span class="sxs-lookup"><span data-stu-id="06e2e-125">None</span></span>  <br/> |<span data-ttu-id="06e2e-126">Office 2016 32-bit se instala mediante hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="06e2e-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="06e2e-127">Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente</span><span class="sxs-lookup"><span data-stu-id="06e2e-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="06e2e-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="06e2e-128">None</span></span>  <br/> |<span data-ttu-id="06e2e-129">Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\***</span><span class="sxs-lookup"><span data-stu-id="06e2e-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="06e2e-130">La versión existente de hacer clic y ejecutar de 32 bits de Office y de aplicaciones independientes de Office de hacer clic y ejecutar de 32 bits o de 64 (por ejemplo, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="06e2e-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="06e2e-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="06e2e-131">None</span></span>  <br/> |<span data-ttu-id="06e2e-132">Las aplicaciones independientes no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="06e2e-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="06e2e-133">El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="06e2e-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="06e2e-134">Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)</span><span class="sxs-lookup"><span data-stu-id="06e2e-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="06e2e-135">Ninguno</span><span class="sxs-lookup"><span data-stu-id="06e2e-135">None</span></span>  <br/> |<span data-ttu-id="06e2e-136">Las aplicaciones independientes no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="06e2e-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="06e2e-137">El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="06e2e-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="06e2e-138">Cualquier versión de Hacer clic y ejecutar de 64 bits de Office</span><span class="sxs-lookup"><span data-stu-id="06e2e-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="06e2e-139">Desinstalar las aplicaciones de Office de 64 bits, si es correcto reemplazarlas por aplicaciones de Office de 32 bits</span><span class="sxs-lookup"><span data-stu-id="06e2e-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="06e2e-140">Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="06e2e-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="06e2e-141">Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="06e2e-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="06e2e-142">Desinstalar MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="06e2e-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="06e2e-p106">La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="06e2e-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="06e2e-145">Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office</span><span class="sxs-lookup"><span data-stu-id="06e2e-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="06e2e-146">Ninguno</span><span class="sxs-lookup"><span data-stu-id="06e2e-146">None</span></span>  <br/> |<span data-ttu-id="06e2e-147">La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo</span><span class="sxs-lookup"><span data-stu-id="06e2e-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="06e2e-148">**(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido.</span><span class="sxs-lookup"><span data-stu-id="06e2e-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="06e2e-149">Hay una corrección en curso.</span><span class="sxs-lookup"><span data-stu-id="06e2e-149">A fix is in progress.</span></span> 
  