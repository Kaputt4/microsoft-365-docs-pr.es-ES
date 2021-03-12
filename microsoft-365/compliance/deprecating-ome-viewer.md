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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: La aplicación Visor de cifrado de mensajes (OME) de Office 365 se quitó de las tiendas De Android y Apple en 2018.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741527"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Desuso de la aplicación visor de cifrado de mensajes

El 15 de agosto de 2018, quitamos la aplicación móvil Visor de cifrado de mensajes (OME) de Office 365 de las tiendas De Android y Apple. La aplicación móvil visor de cifrado de mensajes de Office 365 era necesaria para leer mensajes de correo electrónico y datos adjuntos cifrados con la versión anterior de OME en teléfonos Apple y Android. Además de quitar la aplicación Visor de OME, no estamos realizando ningún otro cambio en la versión anterior de OME.
  
## <a name="changes-from-august-2018"></a>Cambios de agosto de 2018

Como se anunció en septiembre de 2017, hemos publicado una nueva versión del cifrado de mensajes de [Office 365](https://aka.ms/ome2017) para que los usuarios puedan enviar mensajes cifrados y protegidos a cualquier persona dentro o fuera de la organización sin el requisito de la aplicación móvil. Desde entonces, hemos agregado funcionalidades adicionales:
  
- [Plantilla de solo cifrado](https://aka.ms/encryptonly)

- [Control para descifrar datos adjuntos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

Con este cambio, los usuarios ya no podrán descargar la aplicación móvil visor de cifrado de mensajes de Office 365 a partir del 1 de agosto. Como resultado, es posible que los destinatarios de correo no puedan leer mensajes cifrados con la versión anterior de OME en algunos dispositivos móviles Android y Apple. Sin embargo, todavía podrán leer estos mensajes en equipos personales (a través de exploradores de escritorio). Los usuarios que ya han descargado la aplicación seguirán siendo capaces de usarlo.
  
## <a name="why-this-change-was-made"></a>Por qué se realizó este cambio

La nueva versión de OME ya no requiere que una aplicación móvil lea los mensajes de correo electrónico protegidos y los datos adjuntos. Los clientes que usan las nuevas funcionalidades de OME pueden ver el mensaje protegido en Outlook mobile y los que no son clientes pueden ver mensajes protegidos en un explorador.
  
Requerir que los usuarios descarguen una aplicación móvil es otro obstáculo para que los clientes puedan ver mensajes protegidos. Las nuevas funcionalidades de cifrado de mensajes de Office 365 proporcionan una mejor experiencia móvil.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>¿Puedo seguir utilizando la versión anterior del cifrado de mensajes de Office 365?

La versión anterior del cifrado de mensajes de Office 365 no estará en desuso en este momento, sin embargo, hemos realizado mejoras significativas en la nueva versión del cifrado de mensajes de Office 365, que facilita el cifrado y protege los derechos de los datos confidenciales para cualquier usuario y en cualquier dispositivo, incluida la capacidad de los usuarios para leer mensajes protegidos directamente en Outlook (escritorio, móvil, móvil , y web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué debo hacer para prepararme para este cambio?

Si tu organización envía actualmente datos adjuntos cifrados a destinatarios que requieren la aplicación Visor de OME, debes actualizar la documentación y los recursos de aprendizaje.
  
Se recomienda actualizar las reglas de flujo de correo de Exchange existentes para usar la versión actual de OME para que su organización pueda aprovechar las nuevas y mejoradas capacidades. Una vez configuradas las nuevas funcionalidades de OME, los destinatarios no necesitarán la aplicación Visor de OME para leer mensajes cifrados en dispositivos móviles.
  
Microsoft recomienda realizar un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización. Para obtener instrucciones, vea [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo funcionan primero las nuevas funcionalidades, vea Cifrado de mensajes de [Office 365](ome.md).
  

