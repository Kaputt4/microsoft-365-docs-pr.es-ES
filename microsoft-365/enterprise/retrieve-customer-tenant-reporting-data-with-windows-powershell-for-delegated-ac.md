---
title: Recuperar datos de informes de inquilinos de clientes con Windows PowerShell para partners de DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Resumen: use el modo remoto de Windows PowerShell para Microsoft Exchange Online para recuperar informes de espacios empresariales de clientes individuales.'
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927221"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Use el Windows PowerShell remoto para Microsoft Exchange Online para recuperar informes de inquilinos de clientes individuales.
  
Los partners de distribución Proveedor de soluciones en la nube (CSP) pueden tener acceso a los datos que forma parte de los informes de inquilino del cliente directamente a través de Windows PowerShell remoto para Exchange Online PowerShell. Esto permite a los asociados recopilar y guardar los datos de los informes para luego realizar otras operaciones con ellos. Después de abrir una conexión remota, recuperar datos de informes sobre un arrendamiento de cliente es igual que ejecutar cualquier cmdlet en un arrendamiento de cliente..
  
En este artículo, se usa Windows PowerShell remoto para Exchange Online conectarse a un solo arrendamiento de cliente y recuperar un informe. De forma predeterminada, Windows PowerShell no admite agregar datos de informes de varios arrendamientos de cliente. Los informes que recupera con este procedimiento son solo para el  _DelegatedOrg_ al que se conecta.
  
 
## <a name="before-you-begin"></a>Antes de empezar

- Debe conectarse a su inquilino de Exchange Online mediante el modo remoto de Windows PowerShell. Para obtener instrucciones, consulte [Conectarse a los inquilinos de Exchange Online con el modo remoto de Windows PowerShell para asociados con permiso de acceso delegado (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Ejecutar Get-StaleMailboxReport a modo de ejemplo

Después de abrir una sesión remota en Exchange Online, ejecute este comando para recuperar el elemento **Get-StaleMailboxReport** del intervalo de fechas entre el 25/03/2015 y el 31/03/2015.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Existen muchos otros cmdlets de informes disponibles para Exchange Online, Lync Online y SharePoint Online, así como otros para el seguimiento de mensajes. Para obtener más información sobre los cmdlets de informes disponibles y el servicio web de informes de Office 365, consulte los temas en la sección siguiente.
  
## <a name="see-also"></a>Consulte también

#### 

[Servicio web de informes de Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))
  
[Cmdlets de informes en Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[Ayuda para socios](https://go.microsoft.com/fwlink/p/?LinkID=533477)