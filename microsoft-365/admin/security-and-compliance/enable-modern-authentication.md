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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Aprenda a establecer claves del Registro para habilitar la autenticación moderna para dispositivos que Microsoft Office 2013 instalados.
ms.openlocfilehash: c5af8daa0538a1eb89521b12d1c85c310df6d012
ms.sourcegitcommit: 7e59802f251da96ec639fb09534aa96acf5d6ce7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2021
ms.locfileid: "61071881"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar autenticación moderna para Office 2013 en dispositivos Windows

Para habilitar la autenticación moderna para los dispositivos con Windows que tienen Office 2013 instalado, debe configurar claves del registro específicas.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar la autenticación moderna para los clientes de Office 2013

> [!NOTE]
> La autenticación moderna ya está habilitada para los clientes de Office 2016, no necesita configurar claves del registro para Office 2016. 
  
Para habilitar la autenticación moderna para cualquier dispositivo con Windows (por ejemplo, en portátiles y tabletas), que tienen Microsoft Office 2013 instalado, debe configurar las siguientes claves del registro. Las claves deben establecerse en cada dispositivo que quieras habilitar para la autenticación moderna:
  
|**Clave del registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Una vez establecidas las claves del Registro, puede establecer Office aplicaciones de dispositivos de 2013 para que usen la autenticación [multifactor (MFA)](set-up-multi-factor-authentication.md) con Microsoft 365. 
  
Si ha iniciado sesión actualmente con cualquiera de las aplicaciones de cliente, tendrá que cerrar sesión y volver a iniciarla para que el cambio surta efecto. De lo contrario, la configuración de MRU y itinerancia no estará disponible hasta que se establezca la identidad.
  
## <a name="disable-modern-authentication-on-devices"></a>Deshabilitar la autenticación moderna en los dispositivos

Para deshabilitar la autenticación moderna en un dispositivo, establezca las siguientes claves del registro en el dispositivo:
  
|**Clave del registro**|**Tipo**|**Valor**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Contenido relacionado

[Inicie sesión en Office 2013 con un segundo](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) método de comprobación (artículo)\
[Outlook solicita contraseña](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) y no usa la autenticación moderna para conectarse a Office 365 (artículo)

