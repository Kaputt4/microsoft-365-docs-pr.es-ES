---
title: Recuperación de datos de informes de inquilinos de clientes con Windows PowerShell para asociados de DAP
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Resumen: use el modo remoto de Windows PowerShell para Microsoft Exchange Online para recuperar informes de espacios empresariales de clientes individuales.'
ms.openlocfilehash: 88d23874b3dbf3d392937c11365870acc85ea9f7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195531"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Use Windows PowerShell remotas para Microsoft Exchange Online para recuperar informes de inquilinos de clientes individuales.

Los asociados de proveedor de soluciones en la nube (CSP) y de distribución pueden acceder a los datos que componen los informes de inquilinos del cliente directamente a través de Windows PowerShell remotas para Exchange Online PowerShell. Este método permite a los asociados recopilar y guardar los datos de informes y, a continuación, realizar otras operaciones en él. Después de abrir una conexión remota, recuperar datos de informes sobre un arrendamiento de cliente es igual que ejecutar cualquier cmdlet en un arrendamiento de cliente..

En este artículo se describe cómo puede usar Windows PowerShell remotas para Exchange Online conectarse a un único inquilino de cliente y recuperar un informe. De forma predeterminada, Windows PowerShell no admite agregar datos de informes de varios arrendamientos de cliente. Los informes que recupera con este procedimiento son solo para el  _DelegatedOrg_ al que se conecta.

## <a name="before-you-begin"></a>Antes de empezar

- Conéctese al inquilino de Exchange Online mediante Windows PowerShell remotos. Para obtener instrucciones, consulte [Conectarse a los inquilinos de Exchange Online con el modo remoto de Windows PowerShell para asociados con permiso de acceso delegado (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="run-the-get-stalemailboxreport-sample"></a>Ejecutar Get-StaleMailboxReport a modo de ejemplo

Después de abrir una sesión remota para Exchange Online, ejecute el siguiente comando para recuperar **Get-StaleMailboxReport** para el intervalo de fechas del 03/25/2015 al 03/31/2015.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Hay muchos otros cmdlets de informes disponibles para Exchange Online, Lync Online, SharePoint Online y otros servicios para el seguimiento de mensajes que puede usar. Para obtener más información sobre los cmdlets de informes disponibles, consulte los artículos enumerados en la sección siguiente.

## <a name="see-also"></a>Consulte también

[Servicio web de informes de Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Cmdlets de informes en Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)

[Ayuda para socios](https://go.microsoft.com/fwlink/p/?LinkID=533477)
