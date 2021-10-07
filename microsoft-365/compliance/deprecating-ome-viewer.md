---
title: Desuso de la aplicación visor de cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: La aplicación Cifrado de mensajes de Office 365 Visor de Cifrado de mensajes de Office 365 (OME) se quitó de las tiendas De Android y Apple en 2018.
ms.openlocfilehash: 0eded17f4da5347e1f1a88031a780cee5f8b1dee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152987"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Desuso de la aplicación visor de cifrado de mensajes

El 15 de agosto de 2018, quitamos la aplicación móvil visor de Cifrado de mensajes de Office 365 (OME) de las tiendas Android y Apple. La Visor de cifrado de mensajes de Office 365 móvil era necesaria para leer mensajes de correo electrónico y datos adjuntos cifrados con la versión anterior de OME en teléfonos Apple y Android. Además de quitar la aplicación Visor de OME, no estamos realizando ningún otro cambio en la versión anterior de OME.
  
## <a name="changes-from-august-2018"></a>Cambios de agosto de 2018

Como se anunció en septiembre de 2017, hemos lanzado una nueva versión de [Cifrado de mensajes de Office 365](https://aka.ms/ome2017) para que los usuarios puedan enviar mensajes cifrados y protegidos a cualquier persona dentro o fuera de la organización sin el requisito de la aplicación móvil. Desde entonces, hemos agregado funcionalidades adicionales:
  
- [Plantilla de solo cifrado](https://aka.ms/encryptonly)

- [Control para descifrar datos adjuntos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

Con este cambio, los usuarios ya no podrán descargar la aplicación Visor de cifrado de mensajes de Office 365 móvil a partir del 1 de agosto. Como resultado, es posible que los destinatarios de correo no puedan leer mensajes cifrados con la versión anterior de OME en algunos dispositivos móviles Android y Apple. Sin embargo, todavía podrán leer estos mensajes en equipos personales (a través de exploradores de escritorio). Los usuarios que ya han descargado la aplicación seguirán siendo capaces de usarlo.
  
## <a name="why-this-change-was-made"></a>Por qué se realizó este cambio

La nueva versión de OME ya no requiere que una aplicación móvil lea los mensajes de correo electrónico protegidos y los datos adjuntos. Los clientes que usan las nuevas funcionalidades de OME pueden ver el mensaje protegido en Outlook móviles y no clientes pueden ver mensajes protegidos en un explorador.
  
Requerir que los usuarios descarguen una aplicación móvil es otro obstáculo para que los clientes puedan ver mensajes protegidos. Las nuevas Cifrado de mensajes de Office 365 proporcionan una mejor experiencia móvil.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>¿Puedo seguir utilizando la versión anterior de Cifrado de mensajes de Office 365

La versión anterior de Cifrado de mensajes de Office 365 no estará en desuso en este momento, sin embargo, hemos realizado mejoras significativas en la nueva versión de Cifrado de mensajes de Office 365, que facilitan el cifrado y los derechos protegen los datos confidenciales para cualquier usuario y en cualquier dispositivo, incluida la capacidad de los usuarios para leer proteger Mensajes de ed directamente en Outlook (escritorio, móvil y web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué debo hacer para prepararme para este cambio?

Si tu organización envía actualmente datos adjuntos cifrados a destinatarios que requieren la aplicación Visor de OME, debes actualizar la documentación y los recursos de aprendizaje.
  
Se recomienda actualizar las Exchange de flujo de correo existentes para usar la versión actual de OME para que su organización pueda aprovechar las nuevas y mejoradas capacidades. Una vez configuradas las nuevas funcionalidades de OME, los destinatarios no necesitarán la aplicación Visor de OME para leer mensajes cifrados en dispositivos móviles.
  
Microsoft recomienda realizar un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización. Para obtener instrucciones, vea [Set up new Cifrado de mensajes de Office 365 capabilities](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo funcionan primero las nuevas funcionalidades, [vea Cifrado de mensajes de Office 365](ome.md).
  

