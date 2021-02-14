---
title: Preparar la implementación de cliente de Office con Microsoft 365 para empresas
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470955"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="951dc-103">Preparar la implementación de cliente de Office con Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="951dc-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="951dc-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="951dc-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="951dc-105">Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente</span><span class="sxs-lookup"><span data-stu-id="951dc-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="951dc-106">Puede usar Microsoft 365 Empresa Premium para instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlos actualizados con las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="951dc-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="951dc-107">La instalación automática funciona mejor si el equipo del usuario final está en Windows 10 Business y:</span><span class="sxs-lookup"><span data-stu-id="951dc-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="951dc-108">No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).</span><span class="sxs-lookup"><span data-stu-id="951dc-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="951dc-109">o</span><span class="sxs-lookup"><span data-stu-id="951dc-109">or</span></span>
    
- <span data-ttu-id="951dc-110">Tiene instalada una versión existente de Office de Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="951dc-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="951dc-111">Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook).</span><span class="sxs-lookup"><span data-stu-id="951dc-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="951dc-112">Si ve actualizaciones **de Office como** se muestra en la ilustración siguiente, la instalación se ha realizado con Hacer clic y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="951dc-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="951dc-114">**Quién se beneficia de tener esta característica**</span><span class="sxs-lookup"><span data-stu-id="951dc-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="951dc-115">El usuario final cuyo PC:</span><span class="sxs-lookup"><span data-stu-id="951dc-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="951dc-116">**Tiene**  una licencia de usuario de Windows 10 Business, una licencia activa de Microsoft 365 para empresas, Windows 10 Creators Update y está unido a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="951dc-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="951dc-117">**No tiene aplicaciones de** Office de 64 bits (por ejemplo: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="951dc-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="951dc-118">Si se necesitan aplicaciones de Office de 64 bits, esta característica no es una buena opción porque no hay compatibilidad para desencadenar una versión de Hacer clic y ejecutar de 64 bits de 2016 de Office desde la consola de administración de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="951dc-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="951dc-119">**No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project).</span><span class="sxs-lookup"><span data-stu-id="951dc-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="951dc-120">Microsoft 365 para empresas actualiza Office a la versión hacer clic y ejecutar de Office 2016 y eso no funciona con aplicaciones independientes msi de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="951dc-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="951dc-121">En la siguiente tabla se muestra qué acción pueden necesitar realizar los usuarios o administradores finales, en función de su estado inicial, para tener una versión correcta de Hacer clic y ejecutar de 32 bits de la implementación de Office desde la consola de administración de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="951dc-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="951dc-122">**Estado inicial de instalación de Office**</span><span class="sxs-lookup"><span data-stu-id="951dc-122">**Starting Office install status**</span></span>|<span data-ttu-id="951dc-123">**Acción que debe realizar antes de instalar Microsoft 365 para empresas**</span><span class="sxs-lookup"><span data-stu-id="951dc-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="951dc-124">**Estado final**</span><span class="sxs-lookup"><span data-stu-id="951dc-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="951dc-125">Ningún conjunto de aplicaciones de Office instalado</span><span class="sxs-lookup"><span data-stu-id="951dc-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="951dc-126">Ninguno</span><span class="sxs-lookup"><span data-stu-id="951dc-126">None</span></span>  <br/> |<span data-ttu-id="951dc-127">Office 2016 de 32 bits se instala mediante Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="951dc-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="951dc-128">Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente</span><span class="sxs-lookup"><span data-stu-id="951dc-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="951dc-129">Ninguno</span><span class="sxs-lookup"><span data-stu-id="951dc-129">None</span></span>  <br/> |<span data-ttu-id="951dc-130">Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\***</span><span class="sxs-lookup"><span data-stu-id="951dc-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="951dc-131">Versión existente de Hacer clic y ejecutar de 32 bits de Office y hacer clic y ejecutar aplicaciones de Office independientes de 32 o 64 bits (por ejemplo, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="951dc-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="951dc-132">Ninguno</span><span class="sxs-lookup"><span data-stu-id="951dc-132">None</span></span>  <br/> |<span data-ttu-id="951dc-133">Las aplicaciones independientes no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="951dc-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="951dc-134">El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="951dc-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="951dc-135">Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)</span><span class="sxs-lookup"><span data-stu-id="951dc-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="951dc-136">Ninguno</span><span class="sxs-lookup"><span data-stu-id="951dc-136">None</span></span>  <br/> |<span data-ttu-id="951dc-137">Las aplicaciones independientes no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="951dc-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="951dc-138">El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="951dc-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="951dc-139">Cualquier versión de Hacer clic y ejecutar de 64 bits de Office</span><span class="sxs-lookup"><span data-stu-id="951dc-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="951dc-140">Desinstale las aplicaciones de Office de 64 bits, si está bien reemplazarlas por aplicaciones de Office de 32 bits</span><span class="sxs-lookup"><span data-stu-id="951dc-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="951dc-141">Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.</span><span class="sxs-lookup"><span data-stu-id="951dc-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="951dc-142">Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="951dc-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="951dc-143">Desinstalar MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="951dc-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="951dc-p106">La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes</span><span class="sxs-lookup"><span data-stu-id="951dc-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="951dc-146">Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office</span><span class="sxs-lookup"><span data-stu-id="951dc-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="951dc-147">Ninguno</span><span class="sxs-lookup"><span data-stu-id="951dc-147">None</span></span>  <br/> |<span data-ttu-id="951dc-148">La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo</span><span class="sxs-lookup"><span data-stu-id="951dc-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="951dc-149">**(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido.</span><span class="sxs-lookup"><span data-stu-id="951dc-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="951dc-150">Hay una corrección en curso.</span><span class="sxs-lookup"><span data-stu-id="951dc-150">A fix is in progress.</span></span> 
  
