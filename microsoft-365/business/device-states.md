---
title: Estados de dispositivo
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Obtenga información sobre los Estados de dispositivos en Microsoft 365 empresarial.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871387"
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
   
