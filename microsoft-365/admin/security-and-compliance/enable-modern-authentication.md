---
title: Habilitar la autenticación moderna para Office 2013 en Windows dispositivos
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
ms.openlocfilehash: 468658c3b346c7923937ff9595699a20306ed6a9
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754191"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar la autenticación moderna para Office 2013 en Windows dispositivos

Microsoft Office 2013 en Microsoft Windows equipos admiten la autenticación moderna. Pero, para activarlo, debe configurar las siguientes claves del Registro:

|Clave del Registro|Tipo|Valor|
|:---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

> [!NOTE]
> La autenticación moderna ya está habilitada Office 2016 o posterior. No es necesario establecer estas claves del Registro para versiones posteriores de Office.

## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar la autenticación moderna para los clientes de Office 2013

1. Cierre Outlook.

2. Copie y pegue el siguiente texto en Bloc de notas:

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

4. Abra el Explorador de archivos (anteriormente conocido como Windows Explorer), vaya a la ubicación del archivo .reg que acaba de guardar y, a continuación, haga doble clic en él.

5. En el **cuadro de diálogo Control de cuenta** de usuario que aparece, haz clic en **Sí** para permitir que la aplicación realice cambios en el dispositivo.

6. En el **cuadro de diálogo de advertencia del Editor** del Registro que aparece, haga clic **en Sí** para aceptar los cambios.

Una vez establecidas las claves del Registro, puede establecer Office aplicaciones de 2013 para que usen la autenticación multifactor (MFA) con Microsoft 365. Para obtener más información, vea [Configurar la autenticación multifactor](set-up-multi-factor-authentication.md).

Si actualmente has iniciado sesión en cualquiera de las Office cliente, debes cerrar sesión y volver a iniciar sesión para que el cambio suba a efecto. De lo contrario, la configuración de MRU y itinerancia no estará disponible hasta que se establezca la identidad.

## <a name="disable-modern-authentication-on-devices"></a>Deshabilitar la autenticación moderna en los dispositivos

El procedimiento para deshabilitar la autenticación moderna en un dispositivo es muy similar, pero se requieren menos claves del Registro y debes establecer sus valores en 0.

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
