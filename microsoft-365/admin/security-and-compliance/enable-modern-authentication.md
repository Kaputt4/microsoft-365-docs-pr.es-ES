---
title: Habilitar autenticación moderna para Office 2013 en dispositivos Windows
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Aprenda a establecer claves del Registro para habilitar la autenticación moderna para dispositivos que tienen instalado Microsoft Office 2013.
ms.openlocfilehash: d358cb2ffb4284a51779e5a7c1dc894052b9ebc0
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572290"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar autenticación moderna para Office 2013 en dispositivos Windows

Para habilitar la autenticación moderna para los dispositivos con Windows que tienen Office 2013 instalado, debe configurar claves del registro específicas.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar la autenticación moderna para los clientes de Office 2013

> [!NOTE]
> La autenticación moderna ya está habilitada para los clientes de Office 2016, no necesita configurar claves del registro para Office 2016. 
  
Para habilitar la autenticación moderna para cualquier dispositivo con Windows (por ejemplo, en portátiles y tabletas), que tienen Microsoft Office 2013 instalado, debe configurar las siguientes claves del registro. Las claves se tienen que establecer en cada dispositivo en el que quiera habilitar la autenticación moderna:
  
|**Clave del registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Una vez que haya establecido las claves del Registro, puede establecer Office aplicaciones de dispositivos de 2013 para usar [la autenticación multifactor (MFA)](set-up-multi-factor-authentication.md) con Microsoft 365. 
  
Si ha iniciado sesión actualmente con cualquiera de las aplicaciones de cliente, tendrá que cerrar sesión y volver a iniciarla para que el cambio surta efecto. En caso contrario, la configuración usada recientemente y de itinerancia no estará disponible hasta que se establezca la identidad ADAL.
  
## <a name="disable-modern-authentication-on-devices"></a>Deshabilitar la autenticación moderna en los dispositivos

Para deshabilitar la autenticación moderna en un dispositivo, establezca las siguientes claves del registro en el dispositivo:
  
|**Clave del registro**|**Tipo**|**Valor**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Contenido relacionado

[Inicie sesión en Office 2013 con un segundo método de verificación](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artículo)

[Outlook solicita contraseña y no usa autenticación moderna para conectarse a Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (artículo)

