---
title: Registre nuevos dispositivos usted mismo
description: Registrar dispositivos usted mismo para que puedan ser administrados por Microsoft Managed Desktop
ms.service: m365-md
author: tiaraquan
f1.keywords:
  - NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
---

# <a name="register-new-devices-yourself"></a>Registre nuevos dispositivos usted mismo

Microsoft Managed Desktop puede funcionar con dispositivos nuevos o puede reutilizar los dispositivos que ya tenga (lo que requerirá que los vuelva a crear). Puede registrar dispositivos con Microsoft Managed Desktop en el portal Microsoft Endpoint Manager web.

> [!NOTE]
> ¿Trabaja con un partner para obtener dispositivos? Si es así, no tiene que preocuparse por obtener los hashes de hardware; se ocuparán de eso por usted. Asegúrese de que su partner establece una relación con usted en el [Centro de partners](https://partner.microsoft.com/dashboard). El partner puede obtener más información en la [ayuda del Centro de partners](/partner-center/request-a-relationship-with-a-customer). Una vez establecida esta relación, el partner simplemente registrará dispositivos en su nombre, sin que sea necesario realizar ninguna acción adicional. Si quieres ver los detalles o tu partner tiene preguntas, consulta Pasos para que [los partners registren dispositivos](register-devices-partner.md). Una vez registrados los dispositivos, puedes continuar con [la comprobación de la imagen](#check-the-image) y la [entrega de los dispositivos](#deliver-the-device) a los usuarios.

## <a name="prepare-to-register-brand-new-devices"></a>Prepararse para registrar dispositivos nuevos

Una vez que tenga los nuevos dispositivos en la mano, seguirá estos pasos:

1. [Obtener el hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Combinar los datos hash](#merge-hash-data)
3. [Registrar los dispositivos en Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Compruebe que la imagen es correcta.](#check-the-image)
5. [Entregar el dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obtener el hash de hardware

Microsoft Managed Desktop identifica cada dispositivo de forma única haciendo referencia a su hash de hardware. Tiene tres opciones para obtener esta información:

- Pida a su proveedor OEM el archivo de registro de AutoPilot, que incluirá los hashes de hardware.
- Ejecuta un [Windows PowerShell script en](#powershell-script-method) cada dispositivo y recopila los resultados en un archivo.
- Inicie cada dispositivo, pero no complete la Windows de configuración y recopile los [hashes en una unidad flash extraíble](#flash-drive-method).

#### <a name="powershell-script-method"></a>Método de script de PowerShell

Puede usar [ el scriptGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell en el sitio web de la Galería de PowerShell. Para obtener más información acerca de la identificación de dispositivos y el hash de hardware, [consulta Agregar dispositivos a Windows Autopilot](/mem/autopilot/add-devices#device-identification).

1. Abra un símbolo del sistema de PowerShell con derechos administrativos.
2. Ejecute `Install-Script -Name Get-WindowsAutoPilotInfo`
3. Ejecute `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. Ejecute para `powershell -ExecutionPolicy restricted` evitar que se ejecuten los scripts no restringidos posteriores.

#### <a name="flash-drive-method"></a>Método de unidad flash

1. En un dispositivo que no sea el que está registrando, inserte una unidad USB.
2. Abra un símbolo del sistema de PowerShell con derechos administrativos.
3. Ejecute `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Activa el dispositivo que estás registrando, pero *no inicies la experiencia de configuración*. Si inicias accidentalmente la experiencia de configuración, tendrás que restablecer o volver a crear una imagen del dispositivo.
5. Inserte la unidad USB y, a continuación, presione MAYÚS + F10.
6. Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>`.
7. Ejecute `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ejecute `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Quitar la unidad USB y, a continuación, apagar el dispositivo ejecutando `shutdown -s -t 0`

> [!IMPORTANT]
> No enciendas el dispositivo que estás registrando de nuevo hasta que hayas completado el registro para él.

### <a name="merge-hash-data"></a>Combinar datos hash

Tendrás que combinar los datos de los archivos CSV en un solo archivo para completar el registro. Este es un script de PowerShell de ejemplo para que sea fácil:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

> [!NOTE]
> No se admiten columnas adicionales. No se admiten las comillas. Solo se pueden usar archivos de texto con formato ANSI (no Unicode). Los encabezados distinguen mayúsculas de minúsculas. Editar el archivo en Excel guardarlo como un archivo CSV no generará un archivo utilizable debido a estos requisitos. Asegúrese de conservar los ceros iniciales en los números de serie del dispositivo.

### <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos mediante el Portal de administración

En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), seleccione **Dispositivos** en el panel de navegación izquierdo. Busque la sección Escritorio administrado de Microsoft del menú y seleccione **Dispositivos**. En el área de trabajo Dispositivos de escritorio administrados de Microsoft, seleccione **+ Registrar** dispositivos, que abre un control remoto para registrar nuevos dispositivos.

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

Siga estos pasos:

1. En **Carga de archivos**, proporcione una ruta de acceso al archivo CSV que creó anteriormente.
2. Selecciona un [perfil de dispositivo](../service-description/profiles.md) en el menú desplegable.
3. Selecciona **Registrar dispositivos**. El sistema agregará los dispositivos a la lista de dispositivos en **dispositivos**, marcados como **Pendientes de registro**. El registro suele demorar menos de 10 minutos y, cuando se realiza correctamente,  el dispositivo se muestra como Listo para el usuario, lo que significa que está listo y a la espera de que un usuario empiece a usarlo.

> [!NOTE]
> Si cambias manualmente la pertenencia Azure Active Directory (AAD) de un dispositivo, se reasignará automáticamente al grupo para su perfil de dispositivo y se quitará de cualquier grupo en conflicto.

Puedes supervisar el progreso del registro del dispositivo en la página principal. Entre los posibles estados notificados se incluyen:

| Estado | Descripción |
|---------------|-------------|
| Registro pendiente | El registro aún no se ha realizado. Vuelva más tarde. |
| Error de registro | No se pudo completar el registro. Consulte [Troubleshooting device registration para](#troubleshooting-device-registration) obtener más información. |
| Listo para el usuario | El registro se ha registrado correctamente y el dispositivo ya está listo para entregarse al usuario. El Escritorio administrado de Microsoft los guiará a través de la configuración por primera vez, por lo que no es necesario realizar ninguna preparación adicional. |
| Activa | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Este estado también indica que usan regularmente el dispositivo. |
| Inactivo | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  |

#### <a name="troubleshooting-device-registration"></a>Solución de problemas de registro de dispositivos

| Mensaje de error | Detalles |
|---------------|-------------|
| Dispositivo no encontrado | No pudimos registrar este dispositivo porque no pudimos encontrar una coincidencia para el fabricante, modelo o número de serie proporcionado. Confirme estos valores con el proveedor de dispositivos. |
| El hash de hardware no es válido | El hash de hardware que proporcionaste para este dispositivo no se formateó correctamente. Compruebe el hash de hardware y vuelva a enviar. |
| Dispositivo ya registrado | Este dispositivo ya está registrado en la organización. No se requiere ninguna acción adicional. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor de dispositivos. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud: \<requestId\> |

### <a name="check-the-image"></a>Comprobar la imagen

Si el dispositivo procede de un proveedor de partners de Escritorio administrado de Microsoft, la imagen debe ser correcta.

También puedes aplicar la imagen por tu cuenta si lo prefieres. Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionarán la ubicación y los pasos para aplicar la imagen.

### <a name="autopilot-group-tag"></a>Etiqueta de grupo Autopilot

Cuando usas el portal de administración para registrar dispositivos, asignamos automáticamente la etiqueta de grupo Autopilot asociada al perfil de dispositivo que aparece en Registrar dispositivos mediante [el Centro de partners](register-devices-partner.md#register-devices-by-using-partner-center).
El servicio supervisa todos los dispositivos de Escritorio administrado de Microsoft diariamente y asigna la etiqueta de grupo a cualquiera que aún no la tenga.

### <a name="deliver-the-device"></a>Entregar el dispositivo

> [!IMPORTANT]
> Antes de entregar el dispositivo al usuario, asegúrese de haber obtenido y aplicado las licencias [adecuadas para ese](../get-ready/prerequisites.md) usuario.

Si se aplican todas las licencias, puedes preparar a los usuarios para usar dispositivos [y,](get-started-devices.md) a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia de configuración Windows usuario.
