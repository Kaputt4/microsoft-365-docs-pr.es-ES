---
title: Estados de dispositivo
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre los distintos estados del dispositivo en la lista Acciones de dispositivo en la página principal de administración de Microsoft 365 para empresas.
ms.openlocfilehash: ed11ec8d9f043a04960e6d2ffc2bc9adf10bc6d3
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "67611593"
---
# <a name="device-states-in-microsoft-365-for-business"></a>Estados de dispositivos en Microsoft 365 para empresas

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

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)