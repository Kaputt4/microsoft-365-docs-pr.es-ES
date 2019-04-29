---
title: Registrar dispositivos en el escritorio administrado por Microsoft para partners
description: Cómo pueden los socios registrar los dispositivos para que puedan ser administrados por el escritorio administrado por Microsoft
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: d743092fdd309c1afd748afa7523f0cc0c6a2fd0
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400014"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a>Registrar dispositivos en el escritorio administrado por Microsoft para partners


En este tema se describen los pasos que deben seguir los socios para registrar los dispositivos. El proceso para registrar los dispositivos usted mismo está documentado en [registrar los dispositivos en el escritorio administrado por Microsoft](register-devices-self.md).



## <a name="prepare-for-registration"></a>Preparar el registro 
Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [centro de Partners](https://partner.microsoft.com/dashboard). Para obtener más información, vea [ayuda del centro de asociados](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).

Para completar el registro del cliente, cree primero un archivo CSV.

>[!NOTE]
>Para su comodidad, puede descargar una [plantilla](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) para esta *versión de asociado* del archivo CSV.

El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas. Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores. 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,
  
  
  ```


>[!NOTE]
>Este formato es solo para el proceso asociado. El proceso de registro automático está documentado en los [dispositivos de registro del escritorio administrado por Microsoft](register-devices-self.md).

>[!IMPORTANT]
>Estos valores deben coincidir exactamente con los valores de fabricante de SMBIOS. También debe incluir el *hash de hardware* en la primera fila (pero no el valor de la segunda fila) la coma final después del valor de *número de serie* de la segunda fila.

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
| Registro pendiente | Aún no se ha realizado el registro. Vuelva a comProbarla más tarde. |
| Error en el registro | No se pudo completar el registro. Consulte [solución de problemas](register-devices-self.md#troubleshooting) para obtener más información. |
| Listo para el usuario | El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final. El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional. |
| Activo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Esto también indica que los usuarios usan el dispositivo con regularidad. |
| Inactivo | El dispositivo se entregó al usuario final y se registró en su espacio empresarial. Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).  |

## <a name="register-devices-by-using-an-api"></a>Registrar dispositivos con una API

El registro mediante la API es el mismo que el de autoservicio, excepto que la propiedad de hash de hardware de la colección Device es opcional, tal y como se describe en la sección CSV. 

## <a name="troubleshooting"></a>Solución de problemas

| Mensaje de error | Detalles |
|---------------|-------------|
| No se encontró el dispositivo | No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado. Confirma estos valores con el proveedor del dispositivo. |
| No se encontró el dispositivo | No pudimos anular el registro de este dispositivo porque no existe en la organización. No se requiere ninguna otra acción. |
| Hash de hardware no válido | El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto. Compruebe el hash de hardware y vuelva a enviarlo. |
| El dispositivo ya está registrado | Este dispositivo ya está registrado en su organización. No se requiere ninguna otra acción. |
| Dispositivo reclamado por otra organización | Este dispositivo ya ha sido reclamado por otra organización. Consulta con el proveedor del dispositivo. |
| Error inesperado | La solicitud no se pudo procesar automáticamente. Póngase en contacto<support link>con el soporte técnico () y proporcione el identificador de solicitud:<requestId> |