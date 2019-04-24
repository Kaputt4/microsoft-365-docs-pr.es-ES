---
title: Registrar los dispositivos en el escritorio administrado de Microsoft personalmente
description: Registrar los dispositivos usted mismo para que el escritorio administrado de Microsoft pueda administrarlos
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289142"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a>Registrar dispositivos en el escritorio administrado por Microsoft

>[!NOTE]
>En este tema se describen los pasos para registrar los dispositivos por su cuenta. El proceso para socios está documentado en [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).

Microsoft manAged Desktop puede trabajar con dispositivos nuevos o puede volver a usar dispositivos que ya tiene (lo que requerirá que vuelva a crear imágenes). Puede registrar dispositivos con Microsoft manAged Desktop en el portal de Azure o ganar flexibilidad usando una API.

## <a name="prepare-to-register-devices"></a>Preparar el registro de dispositivos

Si todavía no obtuvo los dispositivos que desea usar, compruebe los [dispositivos de escritorio administrados por Microsoft](../service-description/device-list.md) y trabaje con un partner de dispositivos para obtener los dispositivos compatibles.

Si está trabajando con dispositivos completamente nuevos o vuelve a usar los existentes, para registrarlos con el escritorio administrado de Microsoft, deberá preparar un **archivo delimitado por comas (CSV)**. Este archivo debe incluir la siguiente información para cada dispositivo:

>[!NOTE]
>Este formato es solo para el registro de autoservicio. El formato que usan los asociados se documenta en [registrar dispositivos en escritorio administrado de Microsoft para partners](register-devices-partner.md).

Estos valores se usan con fines de presentación y no es necesario que coincidan exactamente con las propiedades del dispositivo.
- Fabricante del dispositivo (ejemplo: SpiralOrbit) 
- Modelo de dispositivo (ejemplo: ContosoABC)
- Número de serie del dispositivo

El hash de hardware debe ser una coincidencia exacta.
- Hash de hardware

Para obtener el hash de hardware, puede solicitar ayuda a su OEM o Partner, o bien siga estos pasos para cada dispositivo:

1.  Abra un símbolo del sistema de PowerShell con derechos administrativos.
2.  Realizar`Install-Script -Name Get-WindowsAutoPilotInfo`
3.  Realizar`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`


Como alternativa, puede seguir estos pasos en un dispositivo nuevo (antes de pasar por la OOBE por primera vez):

1. En otro dispositivo, inserte una unidad USB.
2. Abra un símbolo del sistema de PowerShell con derechos administrativos.
3. Realizar`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`
4. Encienda el dispositivo de destino, pero no inicie la instalación. Si inicia de forma accidental la experiencia del programa de instalación, tendrá que restablecer o volver a crear una imagen del dispositivo.
5. Inserte la unidad USB y, a continuación, presione Mayús + F10.
6. Abra un símbolo del sistema de PowerShell con derechos administrativos y `cd <pathToUsb>`, a continuación, ejecute.
7. Realizar`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`
8. Realizar`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`
3. Quite la unidad USB y, a continuación, apague el dispositivo ejecutando`shutdown -s -t 0`

>[!IMPORTANT]
>No vuelva a encender el dispositivo de destino hasta que haya completado el registro para él. 

>[!NOTE]
>Para su comodidad, puede descargar una [plantilla](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) para este archivo CSV.

El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas. Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
>Si olvida cambiar alguno de los datos de muestra, se producirá un error en el registro.   


## <a name="register-devices-by-using-the-azure-portal"></a>Registrar dispositivos con Azure portal

En el portal de Microsoft manAged Desktop [Azure](https://aka.ms/mmdportal), seleccione **dispositivos** en el panel de navegación izquierdo. Seleccione **+ registrar dispositivos**; se abre el repaso:

[![Volar después de seleccionar dispositivos de registro](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)


[//]: # (Por desGracia, esto no es cierto. Podemos quitar esta nota, pero dejarla ahora hasta que podamos conversar sobre ella.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


Siga estos pasos:

1. En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.
2. Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento. No hay ningún requisito de formato para estos valores.
3. Seleccione **registrar dispositivos**. El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**. El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.


Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** . Los posibles Estados que se notifican incluyen:

| Estado | Descripción |
|---------------|-------------|
| Registro pendiente | Aún no se ha realizado el registro. Vuelva a comProbarla más tarde. |
| Error en el registro | No se pudo completar el registro. Consulte [solución de problemas](register-devices-self.md#troubleshooting) para obtener más información. |
| Listo para el usuario | El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final. El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional. |
| Active | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Esto también indica que los usuarios usan el dispositivo con regularidad. |
| Inactivo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  | 


## <a name="register-devices-by-using-an-api"></a>Registrar dispositivos con una API

Hay disponible una API de REST para permitir una mayor flexibilidad y repetibilidad con registros de dispositivos independientes y frecuentes. Actualmente, para usar la API, pida ayuda al contacto de Microsoft para unirse a una versión preliminar de esta funcionalidad.



## <a name="troubleshooting"></a>Solución de problemas

| Mensaje de error | Detalles |
|---------------|-------------|
| No se encontró el dispositivo | No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado. Confirma estos valores con el proveedor del dispositivo. |
| No se encontró el dispositivo | No pudimos anular el registro de este dispositivo porque no existe en la organización. No se requiere ninguna otra acción. |
| Hash de hardware no válido | El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto. Compruebe el hash de hardware y vuelva a enviarlo. |
| El dispositivo ya está registrado | Este dispositivo ya está registrado en su organización. No se requiere ninguna otra acción. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor del dispositivo. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud:<requestId> |




