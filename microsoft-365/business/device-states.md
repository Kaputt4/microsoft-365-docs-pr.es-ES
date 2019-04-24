---
title: Estados de dispositivo
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Obtenga información sobre los Estados de dispositivos en Microsoft 365 Business.
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276997"
---
# <a name="device-states"></a>Estados de dispositivo

## <a name="device-states"></a>Estados de dispositivo

Los dispositivos de la lista **Acciones de dispositivo** (página principal del administrador \> **Acciones de dispositivo**) pueden tener los estados siguientes.
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Estado**|**Descripción**|
|:-----|:-----|
|Administrado por Intune  <br/> |Administrado por Microsoft 365 Business.  <br/> |
|Pendiente de retirada  <br/> |Microsoft 365 Business está en preparación para quitar los datos de la compañía del dispositivo.  <br/> |
|Retirada en curso  <br/> |Microsoft 365 Business está quitando actualmente los datos de la compañía del dispositivo.  <br/> |
|Error de retirada  <br/> | No se pudo completar la acción para quitar los datos de la compañía.  <br/> |
|Retirada cancelada  <br/> |Se canceló la acción de retirar.  <br/> |
|Borrado pendiente  <br/> |Esperando a que se inicie el restablecimiento de fábrica.  <br/> |
|Borrado en curso  <br/> |Se emitió el restablecimiento de fábrica.  <br/> |
|No se pudo completar el borrado  <br/> |No se pudo realizar el restablecimiento de fábrica.  <br/> |
|Borrado cancelado  <br/> |Se canceló el borrado de fábrica.  <br/> |
|Incorrecto  <br/> |Esto quiere decir que hay una acción pendiente (o en curso), pero el dispositivo no se registró en más de 30 días.  <br/> |
|Pendiente de eliminación  <br/> |La acción de eliminación está pendiente.  <br/> |
|Detectado  <br/> |Microsoft 365 Business detectó el dispositivo.  <br/> |
   
