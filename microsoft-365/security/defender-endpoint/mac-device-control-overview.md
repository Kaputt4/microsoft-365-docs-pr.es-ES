---
title: Control de dispositivo para macOS
description: Obtenga información sobre cómo configurar Microsoft Defender para punto de conexión en Mac para reducir las amenazas del almacenamiento extraíble, como los dispositivos USB.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, dispositivo, control, usb, extraíble, multimedia
ms.service: microsoft-365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 947fd5b5a490bcd8041c05632ad11ae98fb47ec8
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226677"
---
# <a name="device-control-for-macos"></a>Control de dispositivo para macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a>Requisitos

El control de dispositivo para macOS tiene los siguientes requisitos previos:

> [!div class="checklist"]
>
> - Microsoft Defender para punto de conexión derecho (puede ser de prueba)
> - Versión mínima del sistema operativo: macOS 11 o posterior
> - Versión mínima del producto: 101.34.20

## <a name="device-control-policy"></a>Directiva de control de dispositivos

Para configurar el control de dispositivos para macOS, debe crear una directiva que describa las restricciones que quiere aplicar en su organización.

La directiva de control de dispositivos se incluye en el perfil de configuración que se usa para configurar el resto de opciones de producto. Para obtener más información, vea [Estructura de perfil de configuración](mac-preferences.md#configuration-profile-structure).

Dentro del perfil de configuración, la directiva de control de dispositivos se define en la sección siguiente:

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|deviceControl|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

La directiva de control de dispositivos se puede usar para:

- [Personalización del destino de dirección URL para las notificaciones que genera el control de dispositivo](#customize-url-target-for-notifications-raised-by-device-control)
- [Permitir o bloquear dispositivos extraíbles](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a>Personalización del destino de dirección URL para las notificaciones que genera el control de dispositivo

Cuando se aplica la directiva de control de dispositivos que ha implementado en un dispositivo (por ejemplo, el acceso a un dispositivo multimedia extraíble está restringido), se muestra una notificación al usuario.

:::image type="content" source="images/mac-device-control-notification.png" alt-text="Notificación de control de dispositivo" lightbox="images/mac-device-control-notification.png":::

Cuando los usuarios finales hacen clic en esta notificación, se abre una página web en el explorador predeterminado. Puede configurar la dirección URL que se abre cuando los usuarios finales hacen clic en la notificación.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|navigationTarget|
|**Tipo de datos**|Cadena|
|**Comentarios**|Si no se define, el producto usa una dirección URL predeterminada que apunta a una página genérica que explica la acción realizada por el producto.|
|

### <a name="allow-or-block-removable-devices"></a>Permitir o bloquear dispositivos extraíbles

La sección de medios extraíbles de la directiva de control de dispositivos se usa para restringir el acceso a los medios extraíbles.

> [!NOTE]
> Actualmente se admiten los siguientes tipos de medios extraíbles que se pueden incluir en la directiva: dispositivos de almacenamiento USB.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|removableMediaPolicy|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

Esta sección de la directiva es jerárquica, lo que permite la máxima flexibilidad y abarca una amplia gama de casos de uso. En el nivel superior están los proveedores, identificados por un identificador de proveedor. Para cada proveedor, hay productos identificados por un identificador de producto. Por último, para cada producto hay números de serie que indican dispositivos específicos.

```text
|-- policy top level
    |-- vendor 1
        |-- product 1
            |-- serial number 1
            ...
            |-- serial number N
        ...
        |-- product N
    ...
    |-- vendor N
```

Para obtener información sobre cómo buscar los identificadores de dispositivo, consulte [Buscar identificadores de dispositivo](#look-up-device-identifiers).

La directiva se evalúa de la entrada más específica a la más general. Es decir, cuando un dispositivo está conectado, el producto intenta encontrar la coincidencia más específica en la directiva para cada dispositivo multimedia extraíble y aplicar los permisos en ese nivel. Si no hay ninguna coincidencia, se aplica la siguiente mejor coincidencia, hasta el permiso especificado en el nivel superior, que es el valor predeterminado cuando un dispositivo no coincide con ninguna otra entrada de la directiva.

#### <a name="policy-enforcement-level"></a>Nivel de cumplimiento de directivas

En la sección de medios extraíbles, hay una opción para establecer el nivel de cumplimiento, que puede tomar uno de los siguientes valores:

- `audit` - En este nivel de cumplimiento, si el acceso a un dispositivo está restringido, se muestra una notificación al usuario, pero el dispositivo todavía se puede usar. Este nivel de cumplimiento puede ser útil para evaluar la eficacia de una directiva.
- `block` - En este nivel de cumplimiento, las operaciones que el usuario puede realizar en el dispositivo se limitan a lo que se define en la directiva. Además, se genera una notificación al usuario.

> [!NOTE]
> De forma predeterminada, el nivel de cumplimiento se establece en `audit`.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|enforcementLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|audit (valor predeterminado) <p> Bloquear|
|

#### <a name="default-permission-level"></a>Nivel de permisos predeterminado

En el nivel superior de la sección de medios extraíbles, puede configurar el nivel de permiso predeterminado para los dispositivos que no coincidan con nada más en la directiva.

Esta configuración se puede establecer en:

- `none` - No se puede realizar ninguna operación en el dispositivo
- Combinación de los valores siguientes:
  - `read` - Las operaciones de lectura se permiten en el dispositivo
  - `write` - Las operaciones de escritura se permiten en el dispositivo
  - `execute` - Las operaciones de ejecución se permiten en el dispositivo

> [!NOTE]
> Si `none` está presente en el nivel de permiso, se omitirá cualquier otro permiso (`read`, `write`o `execute`).
>
> El `execute` permiso solo hace referencia a la ejecución de archivos binarios de Mach-O. No incluye la ejecución de scripts u otros tipos de cargas.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|ninguno <p> read <p> write <p> Ejecutar|
|

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a>Restricción de medios extraíbles por proveedor, producto y número de serie

Como se describe en [Permitir o bloquear dispositivos extraíbles](#allow-or-block-removable-devices), los medios extraíbles, como los dispositivos USB, se pueden identificar mediante el identificador de proveedor, el identificador de producto y el número de serie.

En el nivel superior de la directiva de medios extraíbles, opcionalmente puede definir restricciones más granulares en el nivel de proveedor.

El `vendors` diccionario contiene una o varias entradas, con cada entrada identificada por el identificador de proveedor.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Proveedores|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|

Para cada proveedor, puede especificar el nivel de permiso deseado para los dispositivos de ese proveedor.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|Igual que el [nivel de permiso predeterminado](#default-permission-level)|
|

Además, puede especificar opcionalmente el conjunto de productos que pertenecen a ese proveedor para el que se definen permisos más granulares. El `products` diccionario contiene una o varias entradas, con cada entrada identificada por el identificador de producto.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Productos|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|

Para cada producto, puede especificar el nivel de permiso deseado para ese producto.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|Igual que el [nivel de permiso predeterminado](#default-permission-level)|
|

Además, puede especificar un conjunto opcional de números de serie para los que se definen permisos más granulares.

El `serialNumbers` diccionario contiene una o varias entradas, con cada entrada identificada por el número de serie.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|serialNumbers|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|

Para cada número de serie, puede especificar el nivel de permiso deseado.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Permiso|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|Igual que el [nivel de permiso predeterminado](#default-permission-level)|
|

#### <a name="example-device-control-policy"></a>Ejemplo de directiva de control de dispositivos

En el ejemplo siguiente se muestra cómo se pueden combinar todos los conceptos anteriores en una directiva de control de dispositivos. En el ejemplo siguiente, observe la naturaleza jerárquica de la directiva de medios extraíbles.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>deviceControl</key>
    <dict>
        <key>navigationTarget</key>
        <string>[custom URL for notifications]</string>
        <key>removableMediaPolicy</key>
        <dict>
            <key>enforcementLevel</key>
            <string>[enforcement level]</string> <!-- audit / block -->
            <key>permission</key>
            <array>
                <string>[permission]</string> <!-- none / read / write / execute -->
                <!-- other permissions -->
            </array>
            <key>vendors</key>
            <dict>
                <key>[vendor id]</key>
                <dict>
                    <key>permission</key>
                    <array>
                        <string>[permission]</string> <!-- none / read / write / execute -->
                        <!-- other permissions -->
                    </array>
                    <key>products</key>
                    <dict>
                        <key>[product id]</key>
                        <dict>
                            <key>permission</key>
                            <array>
                                <string>[permission]</string> <!-- none / read / write / execute -->
                                <!-- other permissions -->
                            </array>
                            <key>serialNumbers</key>
                            <dict>
                                <key>[serial-number]</key>
                                <array>
                                    <string>[permission]</string> <!-- none / read / write / execute -->
                                    <!-- other permissions -->
                                </array>
                                <!-- other serial numbers -->
                            </dict>
                        </dict>
                        <!-- other products -->
                    </dict>
                </dict>
                <!-- other vendors -->
            </dict>
        </dict>
    </dict>
</dict>
</plist>
```

Hemos incluido más ejemplos de directivas de control de dispositivos en los documentos siguientes:

- [Ejemplos de directivas de control de dispositivos para Intune](mac-device-control-intune.md)
- [Ejemplos de directivas de control de dispositivos para JAMF](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a>Buscar identificadores de dispositivo

Para buscar el identificador de proveedor, el identificador de producto y el número de serie de un dispositivo USB:

1. Inicie sesión en un dispositivo Mac.
1. Conecte el dispositivo USB para el que desea buscar los identificadores.
1. En el menú de nivel superior de macOS, seleccione **Acerca de este Equipo Mac**.

   :::image type="content" source="images/mac-device-control-lookup-1.png" alt-text="La página Acerca de este equipo Mac" lightbox="images/mac-device-control-lookup-1.png":::

1. Seleccione **Informe del sistema**.

   :::image type="content" source="images/mac-device-control-lookup-2.png" alt-text="Informe del sistema" lightbox="images/mac-device-control-lookup-2.png":::

1. En la columna izquierda, seleccione **USB**.

   :::image type="content" source="images/mac-device-control-lookup-3.png" alt-text="Vista de todos los dispositivos USB" lightbox="images/mac-device-control-lookup-3.png":::
    

1. En **Árbol de dispositivos USB**, vaya al dispositivo USB que enchufó.

   :::image type="content" source="images/mac-device-control-lookup-4.png" alt-text="Detalles de un dispositivo USB" lightbox="images/mac-device-control-lookup-4.png":::

1. Se muestran el identificador de proveedor, el identificador de producto y el número de serie. Al agregar el identificador de proveedor y el identificador de producto a la directiva de medios extraíbles, solo debe agregar el elemento después de `0x`. Por ejemplo, en la imagen siguiente, el identificador de proveedor es `1000` y el identificador de producto es `090c`.

#### <a name="discover-usb-devices-in-your-organization"></a>Detección de dispositivos USB en la organización

Puede ver los eventos de montaje, desmontaje y cambio de volumen que se originan desde dispositivos USB en Microsoft Defender para punto de conexión búsqueda avanzada. Estos eventos pueden ser útiles para identificar actividades de uso sospechosas o realizar investigaciones internas.

```bash
DeviceEvents
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a>Implementación de directivas de control de dispositivos

La directiva de control de dispositivos debe incluirse junto a la otra configuración del producto, como se describe en [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md).

Este perfil se puede implementar mediante las instrucciones enumeradas en [Implementación del perfil de configuración](mac-preferences.md#configuration-profile-deployment).

## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas

Después de insertar el perfil de configuración a través de Intune o JAMF, puede comprobar si el producto lo recogió correctamente mediante la ejecución del siguiente comando desde el terminal:

```bash
mdatp device-control removable-media policy list
```

Este comando imprimirá en la salida estándar la directiva de control de dispositivos que usa el producto. En caso de que esto imprima `Policy is empty`, asegúrese de que (a) el perfil de configuración se ha insertado en el dispositivo desde la consola de administración y (b) es una directiva de control de dispositivos válida, como se describe en este documento.

En un dispositivo donde la directiva se ha entregado correctamente y donde hay uno o varios dispositivos conectados, puede ejecutar el siguiente comando para enumerar todos los dispositivos y los permisos efectivos que se les han aplicado.

```bash
mdatp device-control removable-media devices list
```

Ejemplo de resultado:

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

En el ejemplo anterior, solo hay un dispositivo multimedia extraíble conectado y tiene `read` y `execute` permisos, según la directiva de control de dispositivos que se entregó al dispositivo.

## <a name="related-topics"></a>Temas relacionados

- [Ejemplos de directivas de control de dispositivos para Intune](mac-device-control-intune.md)
- [Ejemplos de directivas de control de dispositivos para JAMF](mac-device-control-jamf.md)
