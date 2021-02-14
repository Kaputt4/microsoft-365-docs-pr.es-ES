---
title: Optimizar el rendimiento de Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Este artículo contiene sugerencias generales y vínculos a otros recursos que le dicen cómo mejorar el rendimiento de Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694065"
---
# <a name="tune-exchange-online-performance"></a>Optimizar el rendimiento de Exchange Online

Este artículo contiene sugerencias generales y vínculos a otros recursos que le dicen cómo mejorar el rendimiento de Exchange Online, especialmente antes de una migración. Este artículo forma parte del plan de red y el ajuste [del rendimiento para el proyecto de Office 365.](https://aka.ms/tune)
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Aspectos que se deben tener en cuenta para mejorar el rendimiento de Exchange Online

Para mejorar la velocidad de migración y reducir las restricciones de ancho de banda de su organización para Exchange Online, tenga en cuenta lo siguiente:
  
- **Reduzca los tamaños de los buzones.** Un tamaño de buzón más pequeño mejora la velocidad de migración. 
    
- **Use las capacidades de movimiento de buzones con una implementación híbrida de Exchange.** Con una implementación híbrida de Exchange, correo sin conexión (en forma de . Archivos OST) no requiere volver a descargar al migrar a Exchange Online. Esto reduce significativamente los requisitos de ancho de banda de descarga. 
    
- **Programar movimientos de buzones para que se produzcan durante períodos de poco tráfico de Internet y bajo uso de Exchange local.** Al programar movimientos, las solicitudes de migración se envían al proxy de replicación de buzones de correo y es posible que no se lleve a cabo inmediatamente. 
    
- **Use ventanas emergentes inclinadas para Outlook en la Web.** Los elementos emergentes lean proporcionan versiones más pequeñas y con menos memoria de determinados mensajes de correo electrónico en Microsoft Edge o Internet Explorer mediante la representación de algunos componentes en el servidor. Para obtener más información, [vea Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Consejos generales

- Asegúrese de que la búsqueda de DNS outlook.office.com en el centro de datos MS en una ubicación de entrada lógica para su ubicación.

- Investigue el almacenamiento en caché del buzón y elija las opciones adecuadas (re. período de almacenamiento en caché, almacenamiento en caché de buzones compartidos, etc.

- Evitar que los datos de Outlook pasen por conexiones VPN (a una oficina central) antes de pasar por Internet.

- Asegúrese de que los datos del buzón cumplen las limitaciones de las cantidades de carpetas y elementos.
    
Para obtener más información sobre el rendimiento de la migración de Exchange, vea el rendimiento de la migración de [Office 365 y los procedimientos recomendados.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
  

