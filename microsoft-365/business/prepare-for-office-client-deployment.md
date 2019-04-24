---
title: Prepararse para una implementación del cliente de Office mediante Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas.
ms.openlocfilehash: c8e93746b89925d6b6a928a474fe5736e2834987
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286667"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="658f4-103">Prepararse para una implementación del cliente de Office mediante Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="658f4-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="658f4-104">Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente</span><span class="sxs-lookup"><span data-stu-id="658f4-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="658f4-105">Puede usar Microsoft 365 Business para instalar las aplicaciones de Office de 32 bits en equipos Windows 10 y mantenerlas actualizadas.</span><span class="sxs-lookup"><span data-stu-id="658f4-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="658f4-106">Esto funciona mejor si el equipo del usuario final utiliza Windows 10 Business y:</span><span class="sxs-lookup"><span data-stu-id="658f4-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="658f4-107">No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).</span><span class="sxs-lookup"><span data-stu-id="658f4-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="658f4-108">o</span><span class="sxs-lookup"><span data-stu-id="658f4-108">or</span></span>
    
- <span data-ttu-id="658f4-109">Tiene instalada una versión existente de Office de Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="658f4-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="658f4-p101">Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook). Si ve las actualizaciones de Office como se muestran en la siguiente ilustración, la instalación se ha efectuado mediante Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="658f4-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="658f4-113">**¿Quién se beneficiará de tener esta característica?**</span><span class="sxs-lookup"><span data-stu-id="658f4-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="658f4-114">El usuario final cuyo PC:</span><span class="sxs-lookup"><span data-stu-id="658f4-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="658f4-115">**Tenga** una licencia de usuario de Windows 10 Business, una licencia activa de Microsoft 365 Business, Windows 10 Creators Update y se haya unido a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="658f4-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="658f4-p102">**No tenga** las aplicaciones de Office de 64 bits (ejemplo: Word, Excel o PowerPoint). Si las aplicaciones de Office de 64 bits son necesarias, esta característica no es adecuada porque no se puede desencadenar ninguna versión de 64 bits de Hacer clic y ejecutar de Office 2016 desde la consola de administración de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="658f4-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="658f4-p103">**No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project). Microsoft 365 Business actualiza Office a la versión de Hacer clic y ejecutar de Office 2016 y esto no funciona con aplicaciones independientes de Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="658f4-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="658f4-120">En la siguiente tabla, se detalla qué acción deben realizar los usuarios finales/administradores, según su estado inicial, para tener una versión correcta de Hacer clic y ejecutar de 32 bits de la implementación de Office desde la consola de administración de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="658f4-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="658f4-121">**Estado inicial de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="658f4-121">**Starting Office install status**</span></span>|<span data-ttu-id="658f4-122">**Acción que se realiza antes de que se instale Microsoft 365 Business Office**</span><span class="sxs-lookup"><span data-stu-id="658f4-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="658f4-123">**Estado final**</span><span class="sxs-lookup"><span data-stu-id="658f4-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="658f4-124">Ningún conjunto de aplicaciones de Office instalado</span><span class="sxs-lookup"><span data-stu-id="658f4-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="658f4-125">Ninguno</span><span class="sxs-lookup"><span data-stu-id="658f4-125">None</span></span>  <br/> |<span data-ttu-id="658f4-126">Office 2016 de 32 bits está instalado mediante Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="658f4-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="658f4-127">Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente</span><span class="sxs-lookup"><span data-stu-id="658f4-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="658f4-128">Ninguno</span><span class="sxs-lookup"><span data-stu-id="658f4-128">None</span></span>  <br/> |<span data-ttu-id="658f4-129">Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\***</span><span class="sxs-lookup"><span data-stu-id="658f4-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="658f4-130">Versión existente de Hacer clic y ejecutar de 32 bits de Office y aplicaciones independientes de Office de 32 o 64 bits de Hacer clic y ejecutar (por ejemplo, Visio y Project)</span><span class="sxs-lookup"><span data-stu-id="658f4-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="658f4-131">Ninguno</span><span class="sxs-lookup"><span data-stu-id="658f4-131">None</span></span>  <br/> |<span data-ttu-id="658f4-p104">Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="658f4-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="658f4-134">Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)</span><span class="sxs-lookup"><span data-stu-id="658f4-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="658f4-135">Ninguno</span><span class="sxs-lookup"><span data-stu-id="658f4-135">None</span></span>  <br/> |<span data-ttu-id="658f4-p105">Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="658f4-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="658f4-138">Cualquier versión de Hacer clic y ejecutar de 64 bits de Office</span><span class="sxs-lookup"><span data-stu-id="658f4-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="658f4-139">Se desinstalan las aplicaciones de Office de 64 bits, si no importa reemplazarlas por las de Office de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="658f4-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="658f4-140">Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="658f4-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="658f4-141">Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="658f4-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="658f4-142">Desinstalar MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="658f4-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="658f4-p106">La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="658f4-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="658f4-145">Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office</span><span class="sxs-lookup"><span data-stu-id="658f4-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="658f4-146">Ninguno</span><span class="sxs-lookup"><span data-stu-id="658f4-146">None</span></span>  <br/> |<span data-ttu-id="658f4-147">La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo</span><span class="sxs-lookup"><span data-stu-id="658f4-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="658f4-p107">**(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido. La solución está en curso.</span><span class="sxs-lookup"><span data-stu-id="658f4-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


