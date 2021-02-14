---
title: Administrar Microsoft 365 con Windows PowerShell para partners de DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Cómo los partners de sindicación y proveedor de soluciones en la nube (CSP) pueden usar Windows PowerShell administrar inquilinos de clientes de Microsoft 365.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429883"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="4ad65-103">Cómo administrar Microsoft 365 con Windows PowerShell para asociados con permisos de acceso delegado</span><span class="sxs-lookup"><span data-stu-id="4ad65-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="4ad65-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4ad65-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4ad65-105">Los asociados con permiso de acceso delegado (DAP) son asociados de sindicación y proveedor de soluciones en la nube (CSP).</span><span class="sxs-lookup"><span data-stu-id="4ad65-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="4ad65-106">Muchos son proveedores de redes o telecomunicaciones.</span><span class="sxs-lookup"><span data-stu-id="4ad65-106">Many are network or telecom providers.</span></span> <span data-ttu-id="4ad65-107">Agrupan suscripciones de Microsoft 365 en sus ofertas de servicio.</span><span class="sxs-lookup"><span data-stu-id="4ad65-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="4ad65-108">Cuando se vende una suscripción de Microsoft 365, se les conceden automáticamente permisos Administrar en nombre de (AOBO) a los tenencias del cliente para que puedan administrar e informar sobre esos tenencias.</span><span class="sxs-lookup"><span data-stu-id="4ad65-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="4ad65-109">Estas tareas son difíciles de realizar en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ad65-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4ad65-110">Es mucho más fácil usar PowerShell para Microsoft 365 para realizar tareas administrativas como:</span><span class="sxs-lookup"><span data-stu-id="4ad65-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="4ad65-111">Enumerar todos los **TenantIds de cliente** y sus dominios</span><span class="sxs-lookup"><span data-stu-id="4ad65-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="4ad65-112">Identificar todos los usuarios de un arrendamiento de cliente y sus licencias asignadas</span><span class="sxs-lookup"><span data-stu-id="4ad65-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="4ad65-113">Algunas tareas administrativas solo se pueden realizar en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad65-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="4ad65-114">En los siguientes artículos se muestra cómo los partners de sindicación y CSP usan PowerShell para administrar los inquilinos de sus clientes:</span><span class="sxs-lookup"><span data-stu-id="4ad65-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="4ad65-115">Administrar inquilinos de Microsoft 365 con Windows PowerShell para asociados con permisos de acceso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4ad65-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="4ad65-116">Agregar un dominio a un arrendamiento de cliente con Windows PowerShell para asociados con permiso de acceso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4ad65-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="4ad65-117">Conectarse a Exchange Online mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ad65-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="4ad65-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span><span class="sxs-lookup"><span data-stu-id="4ad65-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   