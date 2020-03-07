---
title: Registre nuevos dispositivos usted mismo
description: Registrar los dispositivos usted mismo para que el escritorio administrado de Microsoft pueda administrarlos
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d4ca01e7b791dafc952b62a5f5dd59263b31546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557558"
---
# <a name="register-new-devices-yourself"></a>Registre nuevos dispositivos usted mismo

Microsoft Managed Desktop puede trabajar con dispositivos nuevos o puede volver a usar dispositivos que ya tiene (lo que requerirá que vuelva a crear imágenes). Puede registrar dispositivos con Microsoft Managed Desktop en el portal de Azure.

> [!NOTE]
> ¿Está trabajando con un partner para obtener dispositivos? Si es así, no tiene que preocuparse por obtener los hash de hardware; se ocuparán de ello. Asegúrese de que su compañero establece una relación con usted en el [centro de Partners](https://partner.microsoft.com/dashboard) y que incluye privilegios de administración delegados para Azure Active Directory y Office 365. Su socio puede obtener más información en [ayuda del centro de asociados](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer). Una vez que se ha establecido esta relación, el socio simplemente registrará los dispositivos en su nombre; no se requiere ninguna otra acción por parte del usuario. Si desea ver los detalles o su compañero tiene preguntas, consulte [pasos para que los partners registren dispositivos](register-devices-partner.md). Una vez que se hayan registrado los dispositivos, puede continuar con la [comprobación de la imagen](#check-the-image) y [la entrega de los dispositivos](#deliver-the-device) a los usuarios.

## <a name="prepare-to-register-brand-new-devices"></a>Preparar el registro de nuevos dispositivos


Una vez que tenga a mano los nuevos dispositivos, siga estos pasos:

1. [Obtenga el hash de hardware para cada dispositivo.](#obtain-the-hardware-hash)
2. [Combinar los datos hash](#merge-hash-data)
3. [Registre los dispositivos en el escritorio administrado por Microsoft](#register-devices).
4. [Compruebe que la imagen es correcta.](#check-the-image)
5. [Entregar el dispositivo](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>Obtener el hash de hardware

Microsoft Managed Desktop identifica cada dispositivo de manera única haciendo referencia a su hash de hardware. Tiene tres opciones para obtener esta información:

- Solicite al proveedor de OEM el archivo de registro de AutoPilot, que incluirá los hash de hardware.
- Ejecute un [script de Windows PowerShell](#powershell-script-method) en cada dispositivo y recopile los resultados en un archivo.
- Inicie cada dispositivo, pero no complete la experiencia del programa de instalación de Windows y [reúna los valores hash en una unidad Flash extraíble](#flash-drive-method).

#### <a name="powershell-script-method"></a>Método de script de PowerShell

1.  Abra un símbolo del sistema de PowerShell con derechos administrativos.
2.  Realizar`Install-Script -Name Get-MMDRegistrationInfo`
3.  Realizar`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`

#### <a name="flash-drive-method"></a>Método Flash Drive

1. Inserte una unidad USB en un dispositivo que no sea el que está registrando.
2. Abra un símbolo del sistema de PowerShell con derechos administrativos.
3. Realizar`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`
4. Activa el dispositivo que estás registrando, pero *no inicia la experiencia de instalación*. Si inicia de forma accidental la experiencia del programa de instalación, tendrá que restablecer o volver a crear una imagen del dispositivo.
5. Inserte la unidad USB y, a continuación, presione Mayús + F10.
6. Abra un símbolo del sistema de PowerShell con derechos administrativos y `cd <pathToUsb>`, a continuación, ejecute.
7. Realizar`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Realizar`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`
9. Quite la unidad USB y, a continuación, apague el dispositivo ejecutando`shutdown -s -t 0`

>[!IMPORTANT]
>No encienda el dispositivo de nuevo hasta que haya completado el registro para él. 


### <a name="merge-hash-data"></a>Combinar datos hash

Necesitará tener los datos de los archivos CSV combinados en un único archivo para completar el registro. Este es un script de PowerShell de ejemplo para facilitar esta tarea:

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a>Registrar dispositivos

El archivo CSV debe tener un formato en particular para el registro. Si ha recopilado los datos personalmente en los pasos anteriores, el archivo ya debe estar en el formato correcto; Si obtiene el archivo de un proveedor, es posible que deba ajustar el formato.

>[!NOTE]
>Para su comodidad, puede descargar un [archivo CSV de muestra](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).

El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas. Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Si olvida cambiar alguno de los datos de muestra, se producirá un error en el registro.

#### <a name="register-devices-by-using-the-azure-portal"></a>Registrar dispositivos con Azure portal

En el portal de Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal), seleccione **dispositivos** en el panel de navegación izquierdo. Seleccione **+ registrar dispositivos**; se abre el repaso:

[![Paso a paso después de seleccionar los dispositivos de registro, enumerar los dispositivos con columnas para los usuarios asignados, el número de serie, el estado, la fecha de última visualización y la antigüedad.](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)


[//]: # (Por desgracia, esto no es cierto. Podemos quitar esta nota, pero dejarla ahora hasta que podamos conversar sobre ella.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estos pasos:

1. En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.
2. Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento. No hay ningún requisito de formato para estos valores.
3. Seleccione **registrar dispositivos**. El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**. El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.


Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** . Los posibles Estados que se notifican incluyen:

| Estado | Descripción |
|---------------|-------------|
| Registro pendiente | Aún no se ha realizado el registro. Vuelva a comprobarla más tarde. |
| Error en el registro | No se pudo completar el registro. Consulte [solución de problemas del registro de dispositivos](#troubleshooting-device-registration) para obtener más información. |
| Listo para el usuario | El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final. El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional. |
| Activo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Esto también indica que los usuarios usan el dispositivo con regularidad. |
| Inactivo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  | 

#### <a name="troubleshooting-device-registration"></a>Solución de problemas de registro de dispositivos

| Mensaje de error | Detalles |
|---------------|-------------|
| No se encontró el dispositivo | No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado. Confirma estos valores con el proveedor del dispositivo. |
| Hash de hardware no válido | El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto. Compruebe el hash de hardware y vuelva a enviarlo. |
| El dispositivo ya está registrado | Este dispositivo ya está registrado en su organización. No se requiere ninguna otra acción. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor del dispositivo. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud:<requestId> |

### <a name="check-the-image"></a>Comprobar la imagen

Si el dispositivo proviene de un proveedor de asociados de escritorio administrado por Microsoft, la imagen debe ser correcta.

También tiene la bienvenida de aplicar la imagen por su cuenta si lo prefiere. Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionará la ubicación y los pasos para aplicar la imagen.

### <a name="deliver-the-device"></a>Entregar el dispositivo

> [!IMPORTANT]
> Antes de entregar el dispositivo al usuario, asegúrese de que ha obtenido y aplicado las [licencias adecuadas](../get-ready/prerequisites.md) para ese usuario.

Si se aplican todas las licencias, puede preparar a los [usuarios para que usen dispositivos](get-started-devices.md)y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia del programa de instalación de Windows.






