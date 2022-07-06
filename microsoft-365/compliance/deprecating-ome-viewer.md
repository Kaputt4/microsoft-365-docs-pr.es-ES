---
title: Aplicación visor de OME en desuso
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
description: La aplicación visor Office 365 Message Encryption (OME) se quitó de las tiendas Android y Apple en 2018.
ms.openlocfilehash: 2e1e0ead7d34761a3159b4b51368ea4460acb596
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630089"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Aplicación de visor de cifrado de mensajes en desuso

El 15 de agosto de 2018, quitamos la aplicación móvil del Visor de cifrado de mensajes (OME) Office 365 de las tiendas de Android y Apple. La aplicación móvil Office 365 Message Encryption Viewer era necesaria para leer los mensajes de correo electrónico y los datos adjuntos cifrados con la versión anterior de OME en teléfonos Apple y Android. Además de quitar la aplicación Visor de OME, no vamos a realizar ningún otro cambio en la versión anterior de OME.
  
## <a name="changes-from-august-2018"></a>Cambios desde agosto de 2018

Como se anunció en septiembre de 2017, hemos lanzado una nueva versión de [Office 365 Cifrado](https://aka.ms/ome2017) de mensajes para que los usuarios puedan enviar mensajes cifrados y protegidos a cualquier persona dentro o fuera de la organización sin el requisito de la aplicación móvil. Desde entonces, hemos agregado funcionalidades adicionales:
  
- [Plantilla de solo cifrado](https://aka.ms/encryptonly)

- [Control para descifrar datos adjuntos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

Con este cambio, los usuarios ya no podrán descargar la aplicación móvil Office 365 Visor de cifrado de mensajes a partir del 1 de agosto. Como resultado, es posible que los destinatarios de correo no puedan leer mensajes cifrados con la versión anterior de OME en algunos dispositivos móviles Android y Apple. Sin embargo, seguirán siendo capaces de leer estos mensajes en equipos personales (a través de exploradores de escritorio). Los usuarios que ya hayan descargado la aplicación seguirán pudiendo usarla.
  
## <a name="why-this-change-was-made"></a>Por qué se realizó este cambio

La nueva versión de OME ya no requiere una aplicación móvil para leer los mensajes de correo electrónico protegidos y los datos adjuntos. Los clientes que usan Cifrado de mensajes de Microsoft Purview pueden ver el mensaje protegido en Outlook mobile y los que no son clientes pueden ver mensajes protegidos en un explorador.
  
Exigir a los usuarios que descarguen una aplicación móvil es otro obstáculo para que los clientes vean los mensajes protegidos. Cifrado de mensajes de Microsoft Purview proporciona una mejor experiencia móvil.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>¿Puedo seguir usando la versión anterior de Office 365 cifrado de mensajes?

La versión anterior de Office 365 Cifrado de mensajes no estará en desuso en este momento, sin embargo, hemos realizado mejoras significativas en Cifrado de mensajes de Microsoft Purview, lo que facilita el cifrado y los derechos de protección de datos confidenciales para cualquier usuario y en cualquier dispositivo, incluida la capacidad de los usuarios para leer mensajes protegidos directamente en Outlook (escritorio,  móvil y web).
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>¿Qué debo hacer para prepararme para este cambio?

Si su organización envía actualmente datos adjuntos cifrados a destinatarios que requieren la aplicación Visor de OME, debe actualizar la documentación y los recursos de entrenamiento.
  
Se recomienda actualizar las reglas de flujo de correo de Exchange existentes para usar Cifrado de mensajes de Microsoft Purview para que su organización pueda aprovechar las nuevas y mejoradas funcionalidades. Una vez que haya configurado Cifrado de mensajes de Microsoft Purview, los destinatarios no necesitarán la aplicación Visor de OME para leer mensajes cifrados en dispositivos móviles.
  
Microsoft recomienda que realice un plan para pasar a Cifrado de mensajes de Microsoft Purview tan pronto como sea razonable para su organización. Para obtener instrucciones, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). Si quiere obtener más información sobre cómo funciona primero el cifrado de mensajes, consulte [Cifrado de](ome.md) mensajes.
