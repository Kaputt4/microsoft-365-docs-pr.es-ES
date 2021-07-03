---
title: Registre dispositivos existentes usted mismo
description: Registrar dispositivos reutilizados que quizás ya tenga usted mismo para que puedan administrarse mediante Escritorio administrado de Microsoft
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: ed254234109bc5ff9865ff49ed3fa0fff8770ab0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286914"
---
# <a name="register-existing-devices-yourself"></a>Registre dispositivos existentes usted mismo

>[!NOTE]
>En este tema se describen los pasos para volver a usar los dispositivos que ya tiene y registrarlos en Escritorio administrado de Microsoft. Si está trabajando con dispositivos nuevos, siga los pasos descritos en Registrar nuevos dispositivos [en Escritorio administrado de Microsoft en](register-devices-self.md) su lugar.

El proceso para partners se documenta en [Pasos para que los partners registren dispositivos.](register-devices-partner.md)

Escritorio administrado de Microsoft puede trabajar con dispositivos nuevos o puede reutilizar los dispositivos que ya tenga (lo que requerirá que los vuelva a crear). Puede registrar dispositivos con Escritorio administrado de Microsoft en el portal Microsoft Endpoint Manager web.

## <a name="prepare-to-register-existing-devices"></a>Prepararse para registrar dispositivos existentes


Para registrar dispositivos existentes, siga estos pasos:

1. [Obtener el hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Combinar los datos hash](#merge-hash-data)
3. [Registrar los dispositivos en Escritorio administrado de Microsoft](#register-devices-by-using-the-admin-portal).
4. [Compruebe que la imagen es correcta.](#check-the-image)
5. [Entregar el dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obtener el hash de hardware

Escritorio administrado de Microsoft identifica cada dispositivo de forma única haciendo referencia a su hash de hardware. Tienes cuatro opciones para obtener esta información de los dispositivos que ya estás usando:

- Pida a su proveedor OEM el archivo de registro de AutoPilot, que incluirá los hashes de hardware.
- Recopilar información en [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Ejecute un Windows PowerShell script (ya sea mediante [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) en cada dispositivo) y recopile los resultados en un archivo.
- Inicie cada dispositivo, pero no complete la experiencia de configuración Windows, y recopile los [hashes en una unidad flash extraíble.](#flash-drive-method)

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Puede usar Microsoft Endpoint Configuration Manager para recopilar los hashes de hardware de los dispositivos existentes que desea registrar con Escritorio administrado de Microsoft.

> [!IMPORTANT]
> Los dispositivos para los que quiera obtener esta información deben ejecutarse Windows 10 versión 1703 o posterior. 

Si ha cumplido todos estos requisitos previos, puede recopilar la información siguiendo estos pasos:

1. En la consola de Configuration Manager, seleccione **Supervisión**. 
2. En el área de trabajo Supervisión, expanda el **nodo Informes,** expanda **Informes** y seleccione el **nodo Hardware - General.** 
3. Ejecute el informe, **Windows información del dispositivo de Autopilot** y vea los resultados.
4. En el visor de informes, seleccione el **icono** Exportar y elija la opción **CSV (delimitada por** comas).
5. Después de guardar el archivo, tendrá que filtrar los resultados solo a los dispositivos que tiene previsto registrar con Escritorio administrado de Microsoft cargar los datos en Escritorio administrado de Microsoft. Abra Microsoft Endpoint Manager y vaya al menú **Dispositivos,** busque la Escritorio administrado de Microsoft y seleccione **Dispositivos**. Seleccione **+ Registrar dispositivos**, que abre un fly-in para registrar nuevos dispositivos.


Consulte [Registrar dispositivos mediante el Portal de administración](#register-devices-by-using-the-admin-portal) para obtener más información.


#### <a name="active-directory-powershell-script-method"></a>Método de script de PowerShell de Active Directory

En un entorno de Active Directory, puede usar el cmdlet de PowerShell para recopilar de forma remota la información de dispositivos en grupos de `Get-WindowsAutoPilotInfo` Active Directory mediante WinRM. También puede usar el cmdlet y obtener resultados filtrados para un nombre de modelo de `Get-AD Computer` hardware específico incluido en el catálogo. Antes de continuar, confirme primero estos requisitos previos y, a continuación, siga los pasos siguientes:

- WinRM está habilitado.
- Los dispositivos que desea registrar están activos en la red (es decir, no están desconectados ni desactivados).
- Asegúrese de que tiene un parámetro de credenciales de dominio que tiene permiso para ejecutarse de forma remota en los dispositivos.
- Asegúrese de que Windows firewall permite el acceso a WMI. Para ello, sigue estos pasos:

    1. Abra el **panel Windows Defender** control Firewall y seleccione Permitir una aplicación o característica a través **Windows Defender Firewall**.

    2. Busque **Windows Instrumental de administración (WMI)** en la lista, habilite Private y **Public** y, a continuación, seleccione **Aceptar**.

1. Abra un símbolo del sistema de PowerShell con derechos administrativos.

2. Ejecute *cualquiera de* estos scripts:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. Accede a los directorios en los que pueda haber entradas para los dispositivos. Quita las entradas de cada dispositivo de *todos los* directorios, incluidos Windows Server Active Directory servicios de dominio y Azure Active Directory. Tenga en cuenta que la eliminación podría tardar unas horas en procesarse por completo.

4. Acceder a los servicios de administración en los que puede haber entradas para los dispositivos. Quita las entradas de  cada dispositivo de todos los servicios de administración, incluidos Microsoft Endpoint Configuration Manager, Microsoft Intune y Windows Autopilot. Tenga en cuenta que la eliminación podría tardar unas horas en procesarse por completo.

Ahora puede continuar con el [registro de dispositivos](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Método de script manual de PowerShell

1. Abra un símbolo del sistema de PowerShell con derechos administrativos.
2. Ejecutar `Install-Script -Name Get-WindowsAutoPilotInfo`
3. Ejecutar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
4. [Combinar los datos hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Método de unidad flash

1. En un dispositivo que no sea el que está registrando, inserte una unidad USB.
2. Abra un símbolo del sistema de PowerShell con derechos administrativos.
3. Ejecutar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Activa el dispositivo que estás registrando, pero *no inicies la experiencia de configuración.* Si inicias accidentalmente la experiencia de configuración, tendrás que restablecer o volver a crear una imagen del dispositivo.
5. Inserte la unidad USB y, a continuación, presione MAYÚS + F10.
6. Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>` .
7. Ejecutar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Ejecutar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
9. Quitar la unidad USB y, a continuación, apagar el dispositivo ejecutando `shutdown -s -t 0`
10. [Combinar los datos hash.](#merge-hash-data)

> [!IMPORTANT]
> No enciendas el dispositivo que estás registrando de nuevo hasta que hayas completado el registro para él. 

### <a name="merge-hash-data"></a>Combinar datos hash

Si recopiló los datos de hash de hardware mediante los métodos manuales de PowerShell o unidad flash, ahora debe combinar los datos de los archivos CSV en un solo archivo para completar el registro. Este es un script de PowerShell de ejemplo para que sea fácil:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Con los datos hash combinados en un archivo CSV, ahora puede continuar con [el registro de los dispositivos](#register-devices-by-using-the-admin-portal).

## <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos mediante el Portal de administración

En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), seleccione **Dispositivos** en el panel de navegación izquierdo. Busque la sección Escritorio administrado de Microsoft del menú y seleccione **Dispositivos**. En el área Escritorio administrado de Microsoft de trabajo Dispositivos, Seleccione **+ Registrar** dispositivos , que abre un control fly-in para registrar nuevos dispositivos.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

Siga estos pasos:

1. En **Carga de archivos,** proporcione una ruta de acceso al archivo CSV que creó anteriormente.
2. Selecciona un [perfil de dispositivo](../service-description/profiles.md) en el menú desplegable.
3. Seleccione **Registrar dispositivos**. El sistema agregará los dispositivos a la lista de dispositivos de la hoja **Dispositivos,** marcados como **Registro pendiente.** El registro suele demorar menos de 10 minutos  y, cuando se realiza correctamente, el dispositivo se muestra como Listo para el usuario, lo que significa que está listo y a la espera de que un usuario empiece a usarlo.

> [!NOTE]
> Si cambias manualmente la pertenencia al grupo Azure Active Directory (AAD) de un dispositivo, se reasignará automáticamente al grupo para su perfil de dispositivo y se quitará de cualquier grupo en conflicto.

Puedes supervisar el progreso del registro del dispositivo en la página principal. Entre los posibles estados notificados se incluyen:

| Estado | Descripción |
|---------------|-------------|
| Registro pendiente | El registro aún no se ha realizado. Vuelva más tarde. |
| Error de registro | No se pudo completar el registro. Consulte [Troubleshooting device registration para](#troubleshooting-device-registration) obtener más información. |
| Listo para el usuario | El registro se ha registrado correctamente y el dispositivo ya está listo para entregarse al usuario. Escritorio administrado de Microsoft los guiará a través de la configuración por primera vez, por lo que no es necesario realizar ninguna preparación adicional. |
| Activo | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Esto también indica que usan regularmente el dispositivo. |
| Inactivo | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  | 

### <a name="troubleshooting-device-registration"></a>Solución de problemas de registro de dispositivos

| Mensaje de error | Detalles |
|---------------|-------------|
| Dispositivo no encontrado | No pudimos registrar este dispositivo porque no pudimos encontrar una coincidencia para el fabricante, modelo o número de serie proporcionado. Confirme estos valores con el proveedor de dispositivos. |
| El hash de hardware no es válido | El hash de hardware que proporcionaste para este dispositivo no se formateó correctamente. Compruebe el hash de hardware y vuelva a enviar. |
| Dispositivo ya registrado | Este dispositivo ya está registrado en la organización. No se requiere ninguna acción adicional. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor de dispositivos. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud: <requestId> |

## <a name="check-the-image"></a>Comprobar la imagen

Si el dispositivo procede de un proveedor de partners de Escritorio administrado de Microsoft, la imagen debe ser correcta.

También puedes aplicar la imagen por tu cuenta si lo prefieres. Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionarán la ubicación y los pasos para aplicar la imagen.

## <a name="deliver-the-device"></a>Entregar el dispositivo

> [!IMPORTANT]
> Antes de entregar el dispositivo al usuario, asegúrese de haber obtenido y aplicado las licencias adecuadas [para](../get-ready/prerequisites.md) ese usuario.

Si se aplican todas las [](get-started-devices.md)licencias, puedes preparar a los usuarios para usar dispositivos y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia de configuración de Windows.
