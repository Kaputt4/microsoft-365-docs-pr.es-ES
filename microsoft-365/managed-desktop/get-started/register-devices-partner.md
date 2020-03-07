---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo pueden los socios registrar los dispositivos para que puedan ser administrados por el escritorio administrado por Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557568"
---
# <a name="steps-for-partners-to-register-devices"></a>Pasos para que los Socios puedan registrar dispositivos


En este tema se describen los pasos que deben seguir los socios para registrar los dispositivos. El proceso para registrar los dispositivos usted mismo está documentado en [registrar los dispositivos en el escritorio administrado por Microsoft](register-devices-self.md).



## <a name="prepare-for-registration"></a>Preparar el registro 
Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [centro de Partners](https://partner.microsoft.com/dashboard). Asegúrese de seleccionar **incluir privilegios de administración delegados para Azure Active Directory y Office 365**. Para obtener más información, vea [ayuda del centro de asociados](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).

Para completar el registro del cliente, cree primero un archivo CSV.

>[!NOTE]
>Para su comodidad, puede descargar un [archivo CSV de ejemplo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) para esta *versión del asociado*.

El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas. Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores. 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
>Este formato es solo para el proceso asociado. El proceso de registro automático está documentado en los [dispositivos de registro del escritorio administrado por Microsoft](register-devices-self.md).

>[!IMPORTANT]
>Estos valores deben coincidir exactamente con los valores de fabricante de SMBIOS, incluidos el carácter de mayúsculas y caracteres especiales. 

- Fabricante del dispositivo (ejemplo: SpiralOrbit) 
- Modelo de dispositivo (ejemplo: ContosoABC)
- Número de serie del dispositivo

## <a name="register-devices-by-using-the-azure-portal"></a>Registrar dispositivos con Azure portal

El registro mediante el portal de Azure es el mismo que para el autoservicio, excepto que se obtiene acceso al portal de manera diferente. Siga estos pasos:

1. Ir al [centro de asociados](https://partner.microsoft.com/dashboard)
2. Seleccione **clientes**.
3. Seleccione el cliente que desea administrar.
4. Seleccione **Administración del servicio**.
5. Seleccione **Intune**.
6. Busque "MMD" en el cuadro de búsqueda superior de Azure portal.
7. Seleccione **dispositivos**.
8. En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.
9. Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento. No hay ningún requisito de formato para estos valores.
10. Seleccione **registrar dispositivos**. El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**. El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.


Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** . Los posibles Estados que se notifican incluyen:

| Estado | Descripción |
|---------------|-------------|
| Registro pendiente | Aún no se ha realizado el registro. Vuelva a comprobarla más tarde. |
| Error en el registro | No se pudo completar el registro. Consulte [solución de problemas del registro de dispositivos](register-devices-self.md#troubleshooting-device-registration) para obtener más información. |
| Listo para el usuario | El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final. El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional. |
| Activo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Esto también indica que los usuarios usan el dispositivo con regularidad. |
| Inactivo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  |



## <a name="troubleshooting"></a>Solución de problemas

| Mensaje de error | Detalles |
|---------------|-------------|
| No se encontró el dispositivo | No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado. Confirma estos valores con el proveedor del dispositivo. |
| Hash de hardware no válido | El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto. Compruebe el hash de hardware y vuelva a enviarlo. |
| El dispositivo ya está registrado | Este dispositivo ya está registrado en su organización. No se requiere ninguna otra acción. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor del dispositivo. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto<support link>con el soporte técnico () y proporcione el identificador de solicitud:<requestId> |
