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
ms.openlocfilehash: 010dce00762e4e73d21a9da668a7ac9606d731f9
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504743"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar autenticación moderna para Office 2013 en dispositivos Windows

Para habilitar la autenticación moderna para los dispositivos con Windows que tienen Office 2013 instalado, debe configurar claves del registro específicas.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar la autenticación moderna para los clientes de Office 2013

> [!NOTE]
> La autenticación moderna ya está habilitada para los clientes de Office 2016, no necesita configurar claves del registro para Office 2016. 
  
Para habilitar la autenticación moderna para cualquier dispositivo con Windows (por ejemplo, en portátiles y tabletas), que tienen Microsoft Office 2013 instalado, debe configurar las siguientes claves del registro. Las claves deben establecerse en cada dispositivo que quieras habilitar para la autenticación moderna:

<br>

****

|Clave del Registro|Tipo|Valor|
|:---|:---:|---:|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

Cree o modifique las siguientes claves del Registro para forzar Outlook usar un método de autenticación más reciente para servicios web, como EWS y Detección automática. Se recomienda que los usuarios fuerzan Outlook usar la autenticación moderna.

1. Cierre Outlook.

2. Inicie el Editor del Registro mediante uno de los siguientes procedimientos, según corresponda para la versión de Windows:

   - **Windows 10, Windows 8.1 y Windows 8:** presione Windows tecla + R para abrir un **cuadro de** diálogo Ejecutar. Escriba *regedit.exe* y, a continuación, presione **ENTRAR.**
   - **Windows 7: haga** **clic en** Inicio, escriba *regedit.exe* en el cuadro de búsqueda y, a continuación, presione **ENTRAR.**

3. En el Editor del Registro, busque y haga clic en la siguiente subclave del Registro:

   ```console
   HKEY_CURRENT_USER\Software\Microsoft\Exchange\
   ```

4. Si falta *la clave AlwaysUseMSOAuthForAutoDiscover*, en el menú Editar, elija Nuevo y, a continuación, seleccione **Valor DWORD**. Escriba *AlwaysUseMSOAuthForAutoDiscover y*, a continuación, presione **ENTRAR.**

5. Haga clic con el *botón secundario en AlwaysUseMSOAuthForAutoDiscover* y, a continuación, haga clic **en Modificar.**

6. En el **cuadro Datos** de valor, escriba **1** y, a continuación, haga clic en **Aceptar.**

7. En el Editor del Registro, busque y haga clic en la siguiente subclave del Registro:

   ```console
   HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\
   ```

8. Si las claves de la tabla anterior ya existen, modifique los valores si es necesario, salga del Editor del Registro. Si no lo hacen, en el menú Editar, elija **Nuevo** y, a continuación, seleccione **Valor DWORD** para crear las teclas que faltan. 

9. Por ejemplo, si falta *la tecla EnableADAL* , escriba *EnableADAL* y presione **ENTRAR.**

10. Haga clic con el botón *secundario en EnableADAL* y, a continuación, haga clic **en Modificar.**

11. En el **cuadro Datos** de valor, escriba **1** y, a continuación, haga clic en **Aceptar.**

12. Siga el mismo proceso para la clave Version si es necesario. 

13. **Salga del Editor del Registro.**

Una vez que haya establecido las claves del Registro, puede establecer Office aplicaciones de dispositivos de 2013 para que usen la autenticación [multifactor (MFA)](set-up-multi-factor-authentication.md) con Microsoft 365. 
  
Si ha iniciado sesión actualmente con cualquiera de las aplicaciones de cliente, tendrá que cerrar sesión y volver a iniciarla para que el cambio surta efecto. De lo contrario, la configuración de MRU y itinerancia no estará disponible hasta que se establezca la identidad.
  
## <a name="disable-modern-authentication-on-devices"></a>Deshabilitar la autenticación moderna en los dispositivos

Para deshabilitar la autenticación moderna en un dispositivo, establezca las siguientes claves del registro en el dispositivo:

<br>

****

|Clave del Registro|Tipo|Valor|
|:---|:---:|---:|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|
|HKEY_CURRENT_USER\Software\Microsoft\Exchange\AlwaysUseMSOAuthForAutoDiscover|REG_DWORD|0|
   
## <a name="related-content"></a>Contenido relacionado

[Inicie sesión en Office 2013 con un segundo método de comprobación](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artículo)\
[Outlook solicita contraseña y no](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) usa la autenticación moderna para conectarse a Office 365 (artículo)
