---
title: Estados de dispositivo
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Obtenga información sobre los distintos estados del dispositivo en la lista Acciones de dispositivo en la página principal de administración de Microsoft 365 para empresas.
ms.openlocfilehash: 72a923b366d73d0ceb708abfb6ab96e2562b6e49
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095199"
---
# <a name="device-states"></a>Estados de dispositivo

Este artículo aplica a Microsoft 365 Empresa Premium.

> [!NOTE]
> Microsoft Defender para Empresas se está implementando para los clientes de Microsoft 365 Empresa Premium desde el 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../security/defender-business/mdb-overview.md).

Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.
  
![In the Device actions list, you can see the Devices states.](./../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Estado**|**Descripción**|
|:-----|:-----|
|Administrado por Intune  |Administrado por Microsoft 365 Empresa Premium.  |
|Pendiente de retirada  |Microsoft 365 Empresa Premium se está preparando para quitar los datos de la empresa del dispositivo.  |
|Retirada en curso  |Microsoft 365 Empresa Premium está quitando los datos de la empresa del dispositivo.  |
|Error de retirada  | No se pudo completar la acción para quitar los datos de la compañía.  |
|Retirada cancelada  |Se ha cancelado la acción de retirar.  |
|Borrado pendiente  |Esperando a que se inicie el restablecimiento de fábrica.  |
|Borrado en curso  |Se emitió el restablecimiento de fábrica.  |
|No se pudo completar el borrado  |No se ha podido realizar el restablecimiento de fábrica.  |
|Borrado cancelado  |Se ha cancelado el borrado de fábrica.  |
|Incorrecto  |Hay una acción pendiente (o en curso), pero el dispositivo no se ha comprobado en más de 30 días.  |
|Pendiente de eliminación  |La acción de eliminación está pendiente.  |
|Detectado  |Microsoft 365 Empresa Premium ha detectado el dispositivo.  |
   

## <a name="see-also"></a>Vea también

[10 formas de proteger con planes de Microsoft 365 para empresas](../admin/security-and-compliance/secure-your-business-data.md)