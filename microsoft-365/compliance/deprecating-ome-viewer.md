---
title: Desuso de la aplicación del visor de cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
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
description: La aplicación del visor de cifrado de mensajes de Office 365 (OME) se ha quitado de Android y de las tiendas de Apple en 2018.
ms.openlocfilehash: 9aca6fa2c0e9b276b666ffa187e3d18f061e7224
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817869"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Desuso de la aplicación del visor de cifrado de mensajes

El 15 de agosto de 2018, hemos quitado la aplicación móvil del visor de cifrado de mensajes de Office 365 (OME) de Android y las tiendas de Apple. Se necesita la aplicación móvil del visor de cifrado de mensajes de Office 365 para leer mensajes de correo electrónico y datos adjuntos que se han cifrado con la versión anterior de OME en Apple y teléfonos Android. Además de quitar la aplicación Visor OME, no se realizan otros cambios en la versión anterior de OME.
  
## <a name="changes-from-august-2018"></a>Cambios a partir del 2018 de agosto

Como se anunció en septiembre de 2017, hemos lanzado una nueva versión de [Office 365 Message Encryption](https://aka.ms/ome2017) para que los usuarios puedan enviar mensajes cifrados y protegidos a cualquier persona dentro o fuera de la organización sin necesidad de la aplicación móvil. Desde entonces, hemos agregado capacidades adicionales:
  
- [Plantilla de solo cifrado](https://aka.ms/encryptonly)

- [Control para descifrar datos adjuntos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Con este cambio, los usuarios ya no podrán descargar la aplicación móvil del visor de cifrado de mensajes de Office 365 a partir del 1 de agosto. Como resultado, es posible que los destinatarios de correo no puedan leer mensajes cifrados con la versión anterior de OME en algunos dispositivos móviles Android y Apple. Sin embargo, seguirán pudiendo leer estos mensajes en equipos personales (a través de exploradores de escritorio). Los usuarios que ya hayan descargado la aplicación seguirán pudiendo usarla.
  
## <a name="why-this-change-was-made"></a>Por qué se ha realizado este cambio

La nueva versión de OME ya no requiere una aplicación móvil para leer mensajes de correo electrónico protegidos y datos adjuntos. Los clientes que usan las nuevas funciones OME pueden ver el mensaje protegido en Outlook Mobile y los que no son clientes pueden ver los mensajes protegidos en un explorador.
  
Solicitar a los usuarios que descarguen una aplicación móvil es otro obstáculo para que los clientes vean los mensajes protegidos. Las nuevas capacidades de cifrado de mensajes de Office 365 proporcionan una mejor experiencia móvil.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>¿Puedo seguir usando la versión anterior del cifrado de mensajes de Office 365

La versión anterior de Office 365 el cifrado de mensajes no estará en desuso en este momento, pero hemos realizado mejoras considerables en la nueva versión del cifrado de mensajes de Office 365, que facilitan el cifrado y los derechos para proteger los datos confidenciales para cualquier usuario y en cualquier dispositivo, incluida la capacidad de que los usuarios lean mensajes protegidos directamente en Outlook (escritorio, móvil y Web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué debo hacer para prepararse para este cambio?

Si su organización envía actualmente datos adjuntos cifrados a los destinatarios que requieren la aplicación Visor OME, debe actualizar la documentación y los recursos de aprendizaje.
  
Se recomienda actualizar las reglas de flujo de correo de Exchange existentes para que usen la versión actual de OME de modo que su organización pueda aprovechar las funciones nuevas y mejoradas. Una vez que haya configurado las nuevas capacidades de OME, los destinatarios no necesitan la aplicación de visor OME para leer mensajes cifrados en dispositivos móviles.
  
Microsoft recomienda que cree un plan para cambiar a las nuevas funciones de OME en cuanto sea razonable para su organización. Para obtener instrucciones, vea [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md). Si desea obtener más información sobre cómo funcionan las nuevas funciones en primer lugar, consulte [Office 365 Message Encryption](ome.md).
  

