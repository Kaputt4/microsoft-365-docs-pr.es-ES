---
title: Administrar Microsoft 365 con Windows PowerShell socios de DAP
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
description: Cómo los partners de distribución y Proveedor de soluciones en la nube (CSP) pueden usar Windows PowerShell para administrar Microsoft 365 inquilinos de clientes.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909531"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="efe9e-103">Cómo administrar Microsoft 365 con Windows PowerShell para asociados de permisos de acceso delegado</span><span class="sxs-lookup"><span data-stu-id="efe9e-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="efe9e-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="efe9e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="efe9e-105">Los asociados con permiso de acceso delegado (DAP) son asociados de sindicación y proveedor de soluciones en la nube (CSP).</span><span class="sxs-lookup"><span data-stu-id="efe9e-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="efe9e-106">Muchos son proveedores de redes o telecomunicaciones.</span><span class="sxs-lookup"><span data-stu-id="efe9e-106">Many are network or telecom providers.</span></span> <span data-ttu-id="efe9e-107">Agrupan Microsoft 365 suscripciones en sus ofertas de servicio.</span><span class="sxs-lookup"><span data-stu-id="efe9e-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="efe9e-108">Cuando venden una suscripción Microsoft 365, se les conceden automáticamente permisos Administrar en nombre de (AOBO) a las tenencias del cliente para que puedan administrar e informar sobre esas tenencias.</span><span class="sxs-lookup"><span data-stu-id="efe9e-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="efe9e-109">Estas tareas son difíciles de realizar en el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="efe9e-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="efe9e-110">Es mucho más fácil usar PowerShell para Microsoft 365 tareas administrativas como:</span><span class="sxs-lookup"><span data-stu-id="efe9e-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="efe9e-111">Enumerar todos los **TenantIds del cliente** y sus dominios</span><span class="sxs-lookup"><span data-stu-id="efe9e-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="efe9e-112">Identificar todos los usuarios de un arrendamiento de cliente y sus licencias asignadas</span><span class="sxs-lookup"><span data-stu-id="efe9e-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="efe9e-113">Algunas tareas administrativas solo se pueden realizar en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efe9e-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="efe9e-114">En los siguientes artículos se muestra cómo los partners de Syndication y CSP usan PowerShell para administrar las tenencias de sus clientes:</span><span class="sxs-lookup"><span data-stu-id="efe9e-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="efe9e-115">Administrar Microsoft 365 inquilinos con Windows PowerShell para asociados de permisos de acceso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="efe9e-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="efe9e-116">Agregar un dominio a un arrendamiento de cliente con Windows PowerShell para asociados con permiso de acceso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="efe9e-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="efe9e-117">Conectarse al PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="efe9e-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="efe9e-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span><span class="sxs-lookup"><span data-stu-id="efe9e-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
