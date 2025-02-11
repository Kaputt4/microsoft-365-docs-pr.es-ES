---
title: Cuotas de almacenamiento de SharePoint en entornos multigeográficos
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Obtenga información sobre las cuotas de almacenamiento de SharePoint en entornos multigeográficos y cómo el administrador de SharePoint Online puede administrar las cuotas.
ms.openlocfilehash: 78f57a13cc04e5f98189624a0c02f8f1b85cdea1
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670231"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>Cuotas de almacenamiento de SharePoint en entornos multigeográficos

De forma predeterminada, todas las ubicaciones geográficas de un entorno multigeográfico comparten la cuota de almacenamiento del espacio empresarial disponible.

Con la configuración de cuota de almacenamiento de SharePoint geográfica, puede administrar la cuota de almacenamiento para cada ubicación geográfica. Al asignar una cuota de almacenamiento de una ubicación geográfica, esta se convierte en la cantidad máxima de almacenamiento disponible para esa ubicación geográfica y se resta de la cuota de almacenamiento disponible por espacio empresarial. Luego, la cuota de almacenamiento disponible por espacio empresarial restante se comparte entre las ubicaciones geográficas configuradas a las que no se ha asignado una cuota de almacenamiento.

La cuota de almacenamiento de SharePoint para cualquier ubicación geográfica puede asignarse por el administrador de SharePoint Online mediante la conexión a la ubicación central. Los administradores geográficos de ubicaciones satélites pueden ver la cuota de almacenamiento, pero no pueden asignarlas.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Configurar una cuota de almacenamiento de una ubicación geográfica

Use el [módulo de Microsoft Office SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588) y conéctese a la ubicación central para asignar la cuota de almacenamiento de una ubicación geográfica.

Para asignar la cuota de almacenamiento de una ubicación, ejecute el cmdlet:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Para ver la cuota de almacenamiento de la ubicación geográfica actual, ejecute:

```powershell
Get-SPOGeoStorageQuota
```

![Captura de pantalla de la ventana de PowerShell que muestra Get-SPOGeoStorageQuota cmdlet.](../media/multi-geo-storage-quota.png)

Para ver la cuota de almacenamiento de todas las ubicaciones geográficas, ejecute:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

Para quitar la cuota de almacenamiento asignada a una ubicación geográfica, establezca `StorageQuota value = 0`:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```
