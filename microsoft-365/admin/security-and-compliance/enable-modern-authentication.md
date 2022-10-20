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
ms.openlocfilehash: 8223b2efb88cd29e57353098ab014b76f52251f2
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68629974"
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

>[!IMPORTANT]
> La autenticación básica está desactivada para Exchange Online buzones en Microsoft 365. Esto significa que si Outlook 2013 no está configurado para usar la autenticación moderna, pierde la capacidad de conectarse. Para obtener más información, consulte [Autenticación básica en exchange online](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437).

## <a name="software-requirements"></a>Requisitos de software

Para habilitar MFA para aplicaciones cliente de Office 2013, debe tener instalado el siguiente software (la versión que se muestra a continuación o una versión posterior) en función de si tiene una [instalación basada en hacer clic y ejecutar](http://howtomicrosoftofficetutorials.blogspot.com/2016/12/plan-for-multi-factor-authentication.html#bk_clicktorun) o una [instalación basada en MSI](http://howtomicrosoftofficetutorials.blogspot.com/2016/12/plan-for-multi-factor-authentication.html#bk_msi).

Para determinar si la instalación de Office está basada en hacer clic y ejecutar o en MSI:

1.  Inicie Outlook 2013.
2.  En el menú **Archivo** , seleccione **Cuenta de Office**.
3.  Para las instalaciones de Hacer clic y ejecutar de Outlook 2013, se muestra un elemento **Opciones de actualización** . En el caso de las instalaciones basadas en MSI, no se muestra un elemento **Opciones** de actualización.

      :::image type="content" source="../../security/defender-endpoint/images/office-2013-run-installation.png" alt-text="Captura de pantalla de office 2013":::

### <a name="click-to-run-installations"></a>Instalaciones de clic y ejecución

Para las instalaciones click-to-run, debe tener instalados los siguientes archivos. Si la versión del archivo no es igual o mayor que la versión del archivo enumerada, siga estos pasos para actualizarla.

|Nombre de archivo|Ruta de instalación en el equipo|Versión de archivo|
|---|---|---|
|MSO.DLL|C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL|15.0.4753.1001|
|Csi. DLLL|CSI.DLL C:\Archivos de programa\Microsoft Office 15\root\office15\csi.dll|15.0.4753.1000|
|Groove.EXE|C:\Archivos de programa\Microsoft Office 15\root\office15\GROOVE.exe|15.0.4763.1000|
|Outlook.exe|C:\Archivos de programa\Microsoft Office 15\root\office15\OUTLOOK.exe|15.0.4753.1002|
|ADAL.DLL|C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL|1.0.2016.624|
|Iexplore.exe|C:\Archivos de programa\Internet Explorer|Varía|

### <a name="msi-based-installations"></a>Instalaciones basadas en MSI

Para las instalaciones basadas en MSI, debe tener instalados los siguientes archivos. Si la versión del archivo no es igual o mayor que la versión del archivo que aparece, use el vínculo de la columna Where para obtener la actualización para actualizarla.

|Nombre de archivo|Ruta de instalación en el equipo|Dónde obtener la actualización|Versión|
|---|---|---|---|
|MSO.DLL|C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL|[KB3085480](https://support.microsoft.com/en-us/topic/description-of-the-security-update-for-office-2013-september-10-2019-0d171ba2-2eba-a2ca-a54d-c0f568de6bcc)|15.0.4753.1001|
|Csi. DLLL|CSI.DLL C:\Archivos de programa\Microsoft Office 15\root\office15\csi.dll|[KB3172545](https://support.microsoft.com/en-us/topic/july-11-2017-update-for-office-2013-kb3172545-d6b47054-04d5-5154-40ba-3436d1e0efdb)|15.0.4753.1000|
|Groove.EXE|C:\Archivos de programa\Microsoft Office 15\root\office15\GROOVE.exe|[KB4022226](https://support.microsoft.com/en-us/topic/august-7-2018-update-for-onedrive-for-business-for-office-2013-kb4022226-6163bb26-cbde-eb16-ac42-abfda7afbf68)|15.0.4763.1000|
|Outlook.exe|C:\Archivos de programa\Microsoft Office 15\root\office15\OUTLOOK.exe|[KB4484096](https://support.microsoft.com/en-us/topic/october-1-2019-update-for-outlook-2013-kb4484096-6513145a-cc75-1cd1-72b7-78cb62d8476b)|15.0.4753.1002|
|ADAL.DLL|C:\Archivos de programa\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL|[KB3085565](https://support.microsoft.com/en-us/topic/july-5-2016-update-for-office-2013-kb3085565-1d1a6d24-fbd4-1bae-242f-a35e0e2aba40)|1.0.2016.624|
|Iexplore.exe|C:\Archivos de programa\Internet Explorer|[MS14-052](https://support.microsoft.com/en-us/topic/ms14-052-cumulative-security-update-for-internet-explorer-september-9-2014-17d29b71-9e78-0bc1-8961-7b812d04e4e1)|No aplicable|

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

4. Abra फाइल अन्वेषक (anteriormente conocido como Explorador de Windows), vaya a la ubicación del archivo .reg que acaba de guardar y haga doble clic en él.

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
