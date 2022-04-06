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
ms.localizationpriority: medium
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
description: Obtén información sobre los distintos estados del dispositivo en la lista Acciones del dispositivo en la página Principal de administración Microsoft 365 para empresas.
ms.openlocfilehash: a0651f0f0b104c243115dc86a72cf3e363bdb9a4
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635473"
---
# <a name="device-states"></a>Estados de dispositivo

Este artículo se aplica a Microsoft 365 Business Premium.

> [!NOTE]
> Microsoft Defender für Unternehmen se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../security/defender-business/mdb-overview.md).

Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.
  
![In the Device actions list, you can see the Devices states.](./../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Estado**|**Descripción**|
|:-----|:-----|
|Administrado por Intune  |Administrado por Microsoft 365 Business Premium.  |
|Pendiente de retirada  |Microsoft 365 Business Premium está preparándose para quitar los datos de la empresa del dispositivo.  |
|Retirada en curso  |Microsoft 365 Business Premium está quitando datos de la compañía del dispositivo.  |
|Error de retirada  | No se pudo completar la acción para quitar los datos de la compañía.  |
|Retirada cancelada  |Se canceló la acción Retirar.  |
|Borrado pendiente  |Esperando a que se inicie el restablecimiento de fábrica.  |
|Borrado en curso  |Se emitió el restablecimiento de fábrica.  |
|No se pudo completar el borrado  |No se pudo restablecer la fábrica.  |
|Borrado cancelado  |Se canceló la eliminación de fábrica.  |
|Incorrecto  |Una acción está pendiente (o en curso), pero el dispositivo no se ha registrado durante más de 30 días.  |
|Pendiente de eliminación  |La acción de eliminación está pendiente.  |
|Detectado  |Microsoft 365 Business Premium ha detectado el dispositivo.  |
   

## <a name="see-also"></a>Vea también

[Principales 10 formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)