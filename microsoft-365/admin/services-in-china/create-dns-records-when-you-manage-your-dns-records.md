---
title: Crear registros DNS para Office 365 administrar los registros DNS
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Aprenda a crear registros DNS para Office 365 operados por 21Vianet cuando administre los registros DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: b1254ed341fb73f17f457798f14d01d89063f920
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313460"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a>Crear registros DNS para Office 365 administrar los registros DNS

Para obtener instrucciones detalladas sobre cómo crear registros DNS para Office 365 operados por 21Vianet, incluido el registro MX necesario para el enrutamiento de correo, vea [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). 
  
  
Más opciones y algunas cosas que debe tener en cuenta:
      
-  Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md). Para obtener descripciones de lo que hacen los registros DNS, consulte [Conceptos básicos de DNS](../get-help-with-domains/dns-basics.md).
    
-  Algunos proveedores de hospedaje DNS no permiten crear todos los tipos de registro necesarios, lo que provoca limitaciones de servicio cuando el proveedor de hospedaje no admite [SRV, CNAME, TXT o redirección](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). Si el proveedor no admite registros SRV, TXT o CNAME, se recomienda transferir el dominio a un [](../get-help-with-domains/buy-a-domain-name.md) proveedor que admita todos los tipos [de registros necesarios](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77). 
    
- Para ver qué registros DNS son necesarios y encontrar los valores que se van a usar para cada registro, incluido el registro MX para correo electrónico, vea Recopilar la información que necesita para crear registros [DNS Office 365 DNS](../get-help-with-domains/information-for-dns-records.md). Para obtener descripciones de lo que hacen los registros DNS, consulte [Conceptos básicos de DNS](../get-help-with-domains/dns-basics.md).
