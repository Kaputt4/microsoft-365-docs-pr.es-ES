---
title: Registre nuevos dispositivos usted mismo
description: Registre los dispositivos usted mismo para que puedan ser administrados por escritorio administrado de Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840686"
---
# <a name="register-new-devices-yourself"></a>Registre nuevos dispositivos usted mismo

Escritorio administrado de Microsoft puede funcionar con dispositivos nuevos o puede volver a usar los dispositivos que ya tenga (lo que requerirá que los vuelva a crear una imagen). Puedes registrar dispositivos con escritorio administrado de Microsoft en el portal de Microsoft Endpoint Manager.

> [!NOTE]
> Trabajar con un partner para obtener dispositivos Si es así, no es necesario preocuparse por obtener los hash de hardware; se ocuparán de eso por usted. Asegúrate de que tu partner establezca una relación contigo en el [Centro de partners.](https://partner.microsoft.com/dashboard) Tu partner puede obtener más información en la [ayuda del Centro de partners.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer) Una vez establecida esta relación, tu partner simplemente registrará dispositivos en tu nombre, sin que sea necesario realizar ninguna otra acción por tu parte. Si quieres ver los detalles o tu partner tiene preguntas, consulta pasos para que [los partners registren dispositivos.](register-devices-partner.md) Una vez registrados los dispositivos, puedes continuar con la comprobación de [la imagen](#check-the-image) y [la entrega de los dispositivos](#deliver-the-device) a los usuarios.

## <a name="prepare-to-register-brand-new-devices"></a>Prepararse para registrar dispositivos nuevos


Una vez que tenga los nuevos dispositivos a mano, siga estos pasos:

1. [Obtener el hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Combinar los datos hash](#merge-hash-data)
3. [Registre los dispositivos en el Escritorio administrado de Microsoft.](#register-devices-by-using-the-admin-portal)
4. [Compruebe de nuevo que la imagen es correcta.](#check-the-image)
5. [Entregar el dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obtener el hash de hardware

Escritorio administrado de Microsoft identifica cada dispositivo de forma única haciendo referencia a su hash de hardware. Tiene tres opciones para obtener esta información:

- Pide a tu proveedor oem el archivo de registro de AutoPilot, que incluirá los hash de hardware.
- Ejecuta un [Windows PowerShell script en](#powershell-script-method) cada dispositivo y recopila los resultados en un archivo.
- Inicie cada dispositivo, pero no complete la experiencia de configuración de Windows, y recopile los [hash en una unidad flash extraíble.](#flash-drive-method)

#### <a name="powershell-script-method"></a>Método de script de PowerShell

Puede usar el [ script ](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)Get-WindowsAutoPilotInfo.ps1PowerShell en el sitio web de la Galería de PowerShell. Para obtener más información sobre la identificación de dispositivos y el hash de hardware, consulta [Agregar dispositivos a Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)

1.  Abra un símbolo del sistema de PowerShell con derechos administrativos.
2.  Ejecutar `Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Ejecutar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4.  Ejecutar `powershell -ExecutionPolicy restricted` para evitar que se ejecuten scripts sin restricciones posteriores.


#### <a name="flash-drive-method"></a>Método de unidad flash

1. En un dispositivo distinto del que registras, inserta una unidad USB.
2. Abra un símbolo del sistema de PowerShell con derechos administrativos.
3. Ejecutar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Activa el dispositivo que estás registrando, pero *no inicies la experiencia de configuración.* Si inicias accidentalmente la experiencia de configuración, tendrás que restablecer o volver a crear una imagen del dispositivo.
5. Inserta la unidad USB y, a continuación, presiona MAYÚS + F10.
6. Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>` .
7. Ejecutar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ejecutar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Quitar la unidad USB y, a continuación, apagar el dispositivo ejecutando `shutdown -s -t 0`

>[!IMPORTANT]
>No enciendas el dispositivo que estás registrando de nuevo hasta que hayas completado el registro para él. 


### <a name="merge-hash-data"></a>Combinar datos hash

Deberá combinar los datos de los archivos CSV en un único archivo para completar el registro. Este es un script de PowerShell de ejemplo para que sea fácil:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos mediante el Portal de administración

En [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/)selecciona **Dispositivos** en el panel de navegación izquierdo. Busque la sección Escritorio administrado de Microsoft del menú y seleccione **Dispositivos.** En el área de trabajo Dispositivos de escritorio administrados de Microsoft, seleccione **+ Registrar** dispositivos, que abre un control remoto para registrar nuevos dispositivos.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estos pasos:

1. En **Carga de archivos,** proporcione una ruta de acceso al archivo CSV que creó anteriormente.
3. Seleccione **Registrar dispositivos.** El sistema agregará los dispositivos a tu lista de dispositivos en **Dispositivos,** marcados como **Registro pendiente.** El registro normalmente tarda menos de 10 minutos  y, cuando se realiza correctamente, el dispositivo se mostrará como Listo para el usuario, lo que significa que está listo y esperando a que un usuario empiece a usarlo.


Puedes supervisar el progreso del registro de dispositivos en la página principal. Entre los posibles estados notificados se incluyen:

| Estado | Descripción |
|---------------|-------------|
| Registro pendiente | El registro aún no se ha realizado. Vuelva a consultar más adelante. |
| Error de registro | No se pudo completar el registro. Consulta El registro [de dispositivos para](#troubleshooting-device-registration) solucionar problemas para obtener más información. |
| Listo para el usuario | El registro se ha registrado correctamente y el dispositivo ya está listo para entregarse al usuario. El Escritorio administrado de Microsoft les guiará a través de la configuración por primera vez, por lo que no es necesario realizar ninguna preparación adicional. |
| Activo | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Este estado también indica que usan el dispositivo con regularidad. |
| Inactivo | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  | 

#### <a name="troubleshooting-device-registration"></a>Solución de problemas del registro de dispositivos

| Mensaje de error | Detalles |
|---------------|-------------|
| No se encontró el dispositivo | No pudimos registrar este dispositivo porque no pudimos encontrar una coincidencia para el fabricante, modelo o número de serie proporcionado. Confirma estos valores con el proveedor de dispositivos. |
| El hash de hardware no es válido | El hash de hardware que proporcionaste para este dispositivo no tenía el formato correcto. Vuelva a comprobar el hash de hardware y, a continuación, vuelva a enviar. |
| Dispositivo ya registrado | Este dispositivo ya está registrado en la organización. No es necesario realizar ninguna otra acción. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor de dispositivos. |
| Error inesperado | No se pudo procesar automáticamente la solicitud. Póngase en contacto con el soporte técnico y proporcione el id. de solicitud: <requestId> |

### <a name="check-the-image"></a>Comprobar la imagen

Si el dispositivo procede de un proveedor de partners de Escritorio administrado de Microsoft, la imagen debe ser correcta.

También puedes aplicar la imagen por tu cuenta si lo prefieres. To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.

### <a name="deliver-the-device"></a>Entregar el dispositivo

> [!IMPORTANT]
> Antes de entregar el dispositivo al usuario, asegúrate de que has obtenido y aplicado las licencias adecuadas [para](../get-ready/prerequisites.md) ese usuario.

Si se aplican todas las [](get-started-devices.md)licencias, puedes preparar a los usuarios para usar dispositivos y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia de configuración de Windows.





