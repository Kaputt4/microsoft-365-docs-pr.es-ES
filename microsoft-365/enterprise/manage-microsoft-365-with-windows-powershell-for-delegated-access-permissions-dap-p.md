---
title: Administrar Microsoft 365 con Windows PowerShell socios de DAP
ms.author: kvice
author: kelleyvice-msft
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
ms.openlocfilehash: be32c1c8f6a71e45c8f0176c037f7ca6f28f5c31
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220958"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a>Cómo administrar Microsoft 365 con Windows PowerShell para asociados de permisos de acceso delegado

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Los asociados con permiso de acceso delegado (DAP) son asociados de sindicación y proveedor de soluciones en la nube (CSP). Muchos son proveedores de redes o telecomunicaciones. Agrupan Microsoft 365 suscripciones en sus ofertas de servicio. Cuando venden una suscripción Microsoft 365, se les conceden automáticamente permisos Administrar en nombre de (AOBO) a las tenencias del cliente para que puedan administrar e informar sobre esas tenencias. Estas tareas son difíciles de realizar en el Centro de administración de Microsoft 365. Es mucho más fácil usar PowerShell para Microsoft 365 tareas administrativas como:
- Enumerar todos los **TenantIds del cliente** y sus dominios 
- Identificar todos los usuarios de un arrendamiento de cliente y sus licencias asignadas
> [!NOTE]
> Algunas tareas administrativas solo se pueden realizar en PowerShell.

En los siguientes artículos se muestra cómo los partners de Syndication y CSP usan PowerShell para administrar las tenencias de sus clientes:
  
- [Administrar Microsoft 365 inquilinos con Windows PowerShell para asociados de permisos de acceso delegado (DAP)](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [Agregar un dominio a un arrendamiento de cliente con Windows PowerShell para asociados con permiso de acceso delegado (DAP)](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
