---
title: Optimizar el rendimiento de Exchange Online
ms.author: krowley
author: tracyp
manager: scotv
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Este artículo contiene sugerencias generales y vínculos a otros recursos que le indican cómo mejorar el rendimiento de Exchange Online.
ms.openlocfilehash: dccd592c15f19229d968fd3585f1760e35ae617f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68170209"
---
# <a name="tune-exchange-online-performance"></a>Optimizar el rendimiento de Exchange Online

Este artículo contiene sugerencias generales y vínculos a otros recursos que le indican cómo mejorar el rendimiento de Exchange Online, especialmente delante de una migración. Este artículo forma parte del [plan de red y el ajuste del rendimiento para Office 365](./network-planning-and-performance.md) proyecto.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Aspectos a tener en cuenta para mejorar el rendimiento Exchange Online

Para mejorar la velocidad de la migración y reducir las restricciones de ancho de banda de la organización para Exchange Online, tenga en cuenta lo siguiente:
  
- **Reduzca los tamaños de buzón de correo.** Un tamaño de buzón más pequeño mejora la velocidad de migración. 
    
- **Use las funcionalidades de movimiento del buzón con una implementación híbrida de Exchange.** Con una implementación híbrida de Exchange, correo sin conexión (en forma de . Archivos OST) no requiere volver a descargar al migrar a Exchange Online. Esto reduce significativamente los requisitos de ancho de banda de descarga. 
    
- **Programar que los movimientos de buzón de correo se produzcan durante períodos de poco tráfico de Internet y bajo uso de Exchange local.** Al programar movimientos, las solicitudes de migración se envían al proxy de replicación del buzón y es posible que no se produzcan inmediatamente. 
    
- **Use elementos emergentes lean para Outlook en la Web.** Los elementos emergentes lean proporcionan versiones más pequeñas y con menos memoria de determinados mensajes de correo electrónico en Microsoft Edge o Internet Explorer mediante la representación de algunos componentes en el servidor. Para obtener más información, consulte [Uso de elementos emergentes lean para reducir la memoria usada al leer mensajes de correo](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Consejos generales

- Asegúrese de que la búsqueda dns de outlook.office.com entra en el centro de datos MS en una ubicación de entrada lógica para su ubicación.

- Investigue el almacenamiento en caché del buzón de correo y elija las opciones adecuadas (re. período de almacenamiento en caché, almacenamiento en caché de buzones compartidos, et cetera).

- Impedir que los datos de Outlook pasen conexiones VPN (a una oficina central) antes de que pasen por Internet.

- Asegúrese de que los datos del buzón cumplen las limitaciones de las cantidades de carpetas y elementos.
    
Para obtener más información sobre el rendimiento de la migración de Exchange, consulte [Office 365 rendimiento de migración y procedimientos recomendados](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
