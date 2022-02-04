---
title: Registre dispositivos existentes usted mismo
description: Registrar dispositivos reutilizados que quizás ya tenga usted mismo para que puedan ser administrados por Microsoft Managed Desktop
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

# <a name="register-existing-devices-yourself"></a>Registre dispositivos existentes usted mismo

>[!NOTE]
>En este artículo se describen los pasos para volver a usar los dispositivos que ya tiene y registrarlos en Microsoft Managed Desktop. Si está trabajando con dispositivos nuevos, siga los pasos descritos en Registrar nuevos dispositivos [en Microsoft Managed Desktop usted mismo](register-devices-self.md) . <br> <br> El proceso para partners se documenta en [Pasos para que los partners registren dispositivos](register-devices-partner.md).

Microsoft Managed Desktop puede funcionar con dispositivos nuevos o puede reutilizar los dispositivos que ya tenga. Si reutiliza dispositivos, debe volver a crear una imagen de ellos. Puedes registrar dispositivos con Microsoft Managed Desktop en el portal Microsoft Endpoint Manager web.

## <a name="prepare-to-register-existing-devices"></a>Prepararse para registrar dispositivos existentes

**Para registrar dispositivos existentes:**

1. [Obtener el hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Combinar los datos hash](#merge-hash-data).
3. [Registrar los dispositivos en Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).
4. [Compruebe que la imagen es correcta.](#check-the-image)
5. [Entrega el dispositivo](#deliver-the-device).

### <a name="obtain-the-hardware-hash"></a>Obtener el hash de hardware

**Para obtener el hash de hardware:**

Microsoft Managed Desktop identifica cada dispositivo de forma única haciendo referencia a su hash de hardware. Tienes cuatro opciones para obtener esta información de los dispositivos que ya estás usando:

- Pida a su proveedor OEM el archivo de registro de AutoPilot, que incluirá los hashes de hardware.
- Recopilar información en [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).
- Ejecute un script Windows PowerShell mediante [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) en cada dispositivo y recopile los resultados en un archivo.
- Inicie cada dispositivo, pero no complete la Windows de configuración y recopile los [hashes en una unidad flash extraíble](#flash-drive-method).

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Puede usar Microsoft Endpoint Configuration Manager para recopilar los hashes de hardware de los dispositivos existentes que desea registrar con Microsoft Managed Desktop. Si ha cumplido todos estos requisitos previos, está listo para recopilar la información.

> [!IMPORTANT]
> Los dispositivos para los que quiera obtener esta información deben ejecutarse Windows 10 versión 1703 o posterior.

**Para recopilar la información de hash de hardware:**

1. En la consola de Configuration Manager, seleccione **Supervisión**.
2. En el área de trabajo Supervisión, expanda el **nodo Informes** , expanda **Informes** y seleccione el **nodo Hardware - General** .
3. Ejecute el informe, **Windows información del dispositivo de Autopilot** y vea los resultados.
4. En el visor de informes, seleccione el **icono Exportar** y seleccione la opción **CSV (** delimitada por comas).
5. Después de guardar el archivo, tendrás que filtrar los resultados a solo los dispositivos que planeas registrar con Microsoft Managed Desktop. A continuación, cargue los datos en Microsoft Managed Desktop.
    - Abra Microsoft Endpoint Manager y vaya al **menú Dispositivos**.
    - En la sección Escritorio administrado de Microsoft, seleccione **Dispositivos**.
    - Selecciona **+ Registrar dispositivos**, que abre un fly-in para registrar nuevos dispositivos.

Para obtener más información, consulta [Registrar dispositivos mediante el Portal de administración a](#register-devices-by-using-the-admin-portal) continuación.

#### <a name="active-directory-powershell-script-method"></a>Método de script de PowerShell de Active Directory

En un entorno de Active Directory, puede `Get-WindowsAutoPilotInfo` usar el cmdlet de PowerShell para recopilar de forma remota la información de dispositivos en grupos de Active Directory mediante WinRM. También puede usar el cmdlet y `Get-AD Computer` obtener resultados filtrados para un nombre de modelo de hardware específico incluido en el catálogo. Antes de continuar, confirme estos requisitos previos y, a continuación, continúe.

**Para usar el método de script de PowerShell de Active Directory:**

1. Asegúrese de que WinRM está habilitado.
1. Los dispositivos que desea registrar están activos en la red. Es decir, no están desconectados ni desactivados.
1. Asegúrese de que tiene un parámetro de credenciales de dominio que tiene permiso para ejecutarse de forma remota en los dispositivos.
1. Asegúrese de que Windows firewall permite el acceso a WMI. Para ello, sigue estos pasos:

    - Abra el **panel Windows Defender control Firewall** y seleccione **Permitir una aplicación o característica a través Windows Defender Firewall**.
    - Busque **Windows Instrumental de administración (WMI)** en la lista, habilite Private **y Public** y, a continuación, seleccione **Aceptar**.
1. Abra un símbolo del sistema de PowerShell con derechos administrativos.
1. Ejecute *cualquiera de* estos scripts:

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

1. Accede a los directorios en los que pueda haber entradas para los dispositivos. Quita las entradas de cada dispositivo de *todos los* directorios, incluidos Windows Server Active Directory servicios de dominio y Azure Active Directory. Podría tardar unas horas en procesarse por completo.
1. Acceder a los servicios de administración en los que puede haber entradas para los dispositivos. Quita las entradas de cada dispositivo de  todos los servicios de administración, incluidos Microsoft Endpoint Configuration Manager, Microsoft Intune y Windows Autopilot. Podría tardar unas horas en procesarse por completo.

Ahora puede continuar con el [registro de dispositivos](#register-devices-by-using-the-admin-portal).

#### <a name="manual-powershell-script-method"></a>Método de script manual de PowerShell

**Para usar el método de script manual de Powershell:**

1. Abra un símbolo del sistema de PowerShell con derechos administrativos.
2. Ejecute `Install-Script -Name Get-WindowsAutoPilotInfo`.
3. Ejecute `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`.
4. [Combinar los datos hash.](#merge-hash-data)

#### <a name="flash-drive-method"></a>Método de unidad flash

**Para usar el método de unidad flash:**

1. En un dispositivo que no sea el que está registrando, inserte una unidad USB.
2. Abra un símbolo del sistema de PowerShell con derechos administrativos.
3. Ejecute `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`.
4. Activa el dispositivo que estás registrando, pero *no inicies la experiencia de configuración*. Si inicias accidentalmente la experiencia de configuración, tendrás que restablecer o volver a crear una imagen del dispositivo.
5. Inserte la unidad USB y, a continuación, presione MAYÚS + F10.
6. Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>`.
7. Ejecute `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`.
8. Ejecute `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`.
9. Quita la unidad USB y, a continuación, apaga el dispositivo ejecutando `shutdown -s -t 0`.
10. [Combinar los datos hash.](#merge-hash-data)

> [!IMPORTANT]
> No enciendas el dispositivo que estás registrando de nuevo hasta que hayas completado el registro para él.

### <a name="merge-hash-data"></a>Combinar datos hash

Si recopiló los datos de hash de hardware mediante los métodos manuales de PowerShell o unidad flash, debe combinar los datos de los dos archivos CSV en un solo archivo para completar el registro. Este es un script de PowerShell de ejemplo para que sea fácil:

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

Con los datos hash combinados en un archivo CSV, ahora puedes proceder a [registrar los dispositivos](#register-devices-by-using-the-admin-portal).

## <a name="register-devices-by-using-the-admin-portal"></a>Registrar dispositivos mediante el Portal de administración

En [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), seleccione **Dispositivos** en el panel de navegación izquierdo. En la sección Escritorio administrado de Microsoft, seleccione **Dispositivos**. En el área de trabajo Dispositivos de escritorio administrados de Microsoft, seleccione **+ Registrar** dispositivos, que abre un control remoto para registrar nuevos dispositivos.

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

**Para registrar dispositivos con el Portal de administración:**

1. En **Carga de archivos**, proporcione una ruta de acceso al archivo CSV que creó anteriormente.
2. Selecciona un [perfil de dispositivo](../service-description/profiles.md) en el menú desplegable.
3. Selecciona **Registrar dispositivos**. El sistema agregará los dispositivos a la lista de dispositivos de la **hoja Dispositivos**. Los dispositivos se marcan como **Pendientes de registro**. El registro suele demorar menos de 10 minutos y, cuando se realiza correctamente, el dispositivo se mostrará **como Listo para el usuario**. **Listo para el** usuario significa que está listo y a la espera de que un usuario empiece a usarlo.

> [!NOTE]
> Si cambias manualmente la pertenencia Azure Active Directory (AAD) de un dispositivo, se reasignará automáticamente al grupo para su perfil de dispositivo y se quitará de cualquier grupo en conflicto.

Puedes supervisar el progreso del registro del dispositivo en la página principal. Entre los estados posibles notificados se incluyen:

| Estado | Descripción |
| ----- | ----- |
| Registro pendiente | El registro aún no se ha completado. Vuelva más tarde. |
| Error de registro | No se pudo completar el registro. Para obtener más información, consulte [Troubleshooting device registration](#troubleshooting-device-registration). |
| Listo para el usuario | El registro se ha registrado correctamente. El dispositivo ya está listo para entregarse al usuario. El Escritorio administrado de Microsoft los guiará a través de la configuración por primera vez, por lo que no es necesario realizar ninguna preparación adicional. |
| Activa | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Este estado también indica que usan regularmente el dispositivo. |
| Inactivo | El dispositivo se ha entregado al usuario y se ha registrado con el inquilino. Sin embargo, el usuario no ha usado el dispositivo recientemente (en los últimos siete días). |

### <a name="troubleshooting-device-registration"></a>Solución de problemas de registro de dispositivos

| Mensaje de error | Detalles |
| ----- | ----- |
| Dispositivo no encontrado | No pudimos registrar este dispositivo porque no pudimos encontrar una coincidencia para el fabricante, modelo o número de serie proporcionado. Confirme estos valores con el proveedor de dispositivos. |
| El hash de hardware no es válido | El hash de hardware que proporcionaste para este dispositivo no se formateó correctamente. Compruebe el hash de hardware y vuelva a enviar. |
| Dispositivo ya registrado | Este dispositivo ya está registrado en la organización. No se requiere ninguna acción adicional. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor de dispositivos. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud: `<requestId>` |

## <a name="check-the-image"></a>Comprobar la imagen

Si el dispositivo procede de un proveedor de partners de Escritorio administrado de Microsoft, la imagen debe ser correcta.

También puedes aplicar la imagen por tu cuenta si lo prefieres. Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionará la ubicación y los pasos para aplicar la imagen.

## <a name="deliver-the-device"></a>Entregar el dispositivo

> [!IMPORTANT]
> Antes de entregar el dispositivo al usuario, asegúrese de haber obtenido y aplicado las licencias [adecuadas para ese](../get-ready/prerequisites.md) usuario.

Si se aplican todas las licencias, puede preparar [a los usuarios para usar los dispositivos](get-started-devices.md). A continuación, el usuario puede iniciar el dispositivo y continuar con la Windows de configuración.
