---
title: Habilitar la autenticación moderna para Office 2013 en dispositivos Windows
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
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
description: Aprenda a establecer claves del Registro para habilitar la autenticación moderna para los dispositivos que tienen instalado Microsoft Office 2013.
ms.openlocfilehash: 3643db4b8d255809fc0ad125b76173b7d3b1a3d3
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188337"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar la autenticación moderna para Office 2013 en dispositivos Windows

Microsoft Office 2013 en equipos de Microsoft Windows admite la autenticación moderna. Pero, para activarlo, debe configurar las siguientes claves del Registro:

|Clave del Registro|Tipo|Valor|
|:---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

> [!NOTE]
> La autenticación moderna ya está habilitada en Office 2016 o posterior. No es necesario establecer estas claves del Registro para versiones posteriores de Office.

## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar la autenticación moderna para los clientes de Office 2013

1. Cierre Outlook.

2. Copie y pegue el texto siguiente en el Bloc de notas:

   ```text
   Windows Registry Editor Version 5.00

   [HKEY_CURRENT_USER\Software\Microsoft\Exchange]
   "AlwaysUseMSOAuthForAutoDiscover"=dword:00000001

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
   "EnableADAL"=dword:00000001
   "Version"=dword:00000001
   ```

3. Guarde el archivo con la extensión de archivo .reg en lugar de .txt en una ubicación que sea fácil de encontrar. Por ejemplo, `C:\Data\Office2013_Enable_ModernAuth.reg`.

4. Abra Explorador de archivos (anteriormente conocido como Explorador de Windows), vaya a la ubicación del archivo .reg que acaba de guardar y haga doble clic en él.

5. En el cuadro de diálogo **Control de cuentas** de usuario que aparece, haga clic en **Sí** para permitir que la aplicación realice cambios en el dispositivo.

6. En el cuadro **de diálogo de advertencia del Editor del Registro** que aparece, haga clic en **Sí** para aceptar los cambios.

Una vez que haya establecido las claves del Registro, puede establecer aplicaciones de Office 2013 para usar la autenticación multifactor (MFA) con Microsoft 365. Para obtener más información, consulte [Configuración de la autenticación multifactor](set-up-multi-factor-authentication.md).

Si ha iniciado sesión actualmente en cualquiera de las aplicaciones cliente de Office, debe cerrar la sesión y volver a iniciar sesión para que el cambio surta efecto. De lo contrario, la configuración de MRU y itinerancia no estará disponible hasta que se establezca la identidad.

## <a name="disable-modern-authentication-on-devices"></a>Deshabilitar la autenticación moderna en los dispositivos

El procedimiento para deshabilitar la autenticación moderna en un dispositivo es muy similar, pero se requieren menos claves del Registro y debe establecer sus valores en 0.

|Clave del Registro|Tipo|Valor|
|---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|0|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|

```text
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Exchange]
"AlwaysUseMSOAuthForAutoDiscover"=dword:00000000

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
"EnableADAL"=dword:00000000
```

## <a name="related-content"></a>Contenido relacionado

[Inicie sesión en Office 2013 con un segundo método de verificación](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[Outlook solicita contraseña y no usa la autenticación moderna para conectarse a Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)
