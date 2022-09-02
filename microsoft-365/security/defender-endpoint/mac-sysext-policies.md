---
title: Nuevos perfiles de configuración para macOS Catalina y versiones más recientes de macOS
description: En este tema se describen los cambios que se deben realizar para beneficiarse de las extensiones del sistema, que son un reemplazo de las extensiones de kernel en macOS Catalina y versiones más recientes de macOS.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-security-compliance
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.subservice: mde
ms.openlocfilehash: 1bf949f66e525504a9ef499a034093115d7f6db5
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67521573"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a>Nuevos perfiles de configuración para macOS Catalina y versiones más recientes de macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En consonancia con la evolución de macOS, estamos preparando un Microsoft Defender para punto de conexión en la actualización de macOS que aprovecha las extensiones del sistema en lugar de las extensiones del kernel. Esta actualización solo se aplicará a macOS Catalina (10.15.4) y a las versiones más recientes de macOS.

Si ha implementado Microsoft Defender para punto de conexión en macOS en un entorno administrado (a través de JAMF, Intune u otra solución MDM), debe implementar nuevos perfiles de configuración. Si no se realizan estos pasos, los usuarios recibirán solicitudes de aprobación para ejecutar estos nuevos componentes.

## <a name="jamf"></a>JAMF

### <a name="jamf-system-extensions-policy"></a>Directiva de extensiones del sistema JAMF

Para aprobar las extensiones del sistema, cree la siguiente carga:

1. En **Equipos > perfiles de configuración** , seleccione **Opciones > Extensiones del sistema**.
2. Seleccione **Extensiones de sistema permitidas** en la lista desplegable **Tipos de extensión del sistema** .
3. Use **UBF8T346G9** para el id. de equipo.
4. Agregue los siguientes identificadores de agrupación a la lista **Extensiones de sistema permitidas** :

    - **com.microsoft.wdav.epsext**
    - **com.microsoft.wdav.netext**

    :::image type="content" source="images/mac-approved-system-extensions.png" alt-text=" Página Extensiones del sistema aprobadas" lightbox="images/mac-approved-system-extensions.png":::

### <a name="privacy-preferences-policy-control"></a>Control de directivas de preferencias de privacidad

Agregue la siguiente carga de JAMF para conceder acceso completo al disco a la extensión de seguridad de punto de conexión de Microsoft Defender para punto de conexión. Esta directiva es un requisito previo para ejecutar la extensión en el dispositivo.

1. Seleccione **Opciones** \> **Control de directivas de preferencias de privacidad**.
2. Use `com.microsoft.wdav.epsext` como **identificador** y `Bundle ID` como **tipo de agrupación**.
3. Establecer requisito de código en `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
4. Establezca **Aplicación o servicio** en **SystemPolicyAllFiles** y acceso a **Permitir**.

   :::image type="content" source="images/mac-system-extension-privacy.png" alt-text=" Elemento de menú Control de directivas de preferencias de privacidad" lightbox="images/mac-system-extension-privacy.png":::

### <a name="network-extension-policy"></a>Directiva de extensión de red

Como parte de las funcionalidades de detección y respuesta de puntos de conexión, Microsoft Defender para punto de conexión en macOS inspecciona el tráfico de socket e informa de esta información al portal de Microsoft 365 Defender. La siguiente directiva permite que la extensión de red realice esta funcionalidad.

> [!NOTE]
> JAMF no tiene compatibilidad integrada con las directivas de filtrado de contenido, que son un requisito previo para habilitar las extensiones de red que Microsoft Defender para punto de conexión en macOS se instala en el dispositivo. Además, JAMF a veces cambia el contenido de las directivas que se implementan.
> Por lo tanto, los pasos siguientes proporcionan una solución alternativa que implica firmar el perfil de configuración.

1. Guarde el siguiente contenido en el dispositivo como `com.microsoft.network-extension.mobileconfig` mediante un editor de texto:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. Compruebe que el archivo anterior se copió correctamente ejecutando la `plutil` utilidad en el terminal:

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    Por ejemplo, si el archivo se almacenó en Documentos:

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```

    Compruebe que el comando genera `OK`.

    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```

3. Siga las instrucciones de [esta página](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) para crear un certificado de firma mediante la entidad de certificación integrada de JAMF.

4. Una vez creado e instalado el certificado en el dispositivo, ejecute el siguiente comando desde terminal para firmar el archivo:

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```

    Por ejemplo, si el nombre del certificado es **SigningCertificate** y el archivo firmado se va a almacenar en Documentos:

    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```

5. En el portal de JAMF, vaya a **Perfiles de configuración** y haga clic en el botón **Cargar** . Seleccione `com.microsoft.network-extension.signed.mobileconfig` cuando se le solicite el archivo.

## <a name="intune"></a>Intune

### <a name="intune-system-extensions-policy"></a>Directiva de extensiones del sistema de Intune

Para aprobar las extensiones del sistema:

1. En Intune, abra **Administrar** \> **configuración del dispositivo**. Seleccione **Administrar** \> **perfiles** \> **Crear perfil**.
2. Elija un nombre para el perfil. Cambie **Platform=macOS** a **Profile type=Extensions**. Seleccione **Crear**.
3. En la `Basics` pestaña , asigne un nombre a este nuevo perfil.
4. En la `Configuration settings` pestaña , agregue las siguientes entradas en la `Allowed system extensions` sección :

   <br>

   ****

   |Identificador de agrupación|Identificador de equipo|
   |---|---|
   |com.microsoft.wdav.epsext|UBF8T346G9|
   |com.microsoft.wdav.netext|UBF8T346G9|
   |||

   :::image type="content" source="images/mac-system-extension-intune2.png" alt-text=" Página Perfiles de configuración del sistema" lightbox="images/mac-system-extension-intune2.png":::

5. En la `Assignments` pestaña , asigne este perfil a **Todos los usuarios & Todos los dispositivos**.
6. Revise y cree este perfil de configuración.

### <a name="create-and-deploy-the-custom-configuration-profile"></a>Creación e implementación del perfil de configuración personalizada

El siguiente perfil de configuración habilita la extensión de red y concede acceso en disco completo a la extensión del sistema Endpoint Security.

Guarde el siguiente contenido en un archivo denominado **sysext.xml**:

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

Compruebe que el archivo anterior se copió correctamente. Desde terminal, ejecute el siguiente comando y compruebe que genera `OK`:

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

Para implementar este perfil de configuración personalizado:

1. En Intune, abra **Administrar** \> **configuración del dispositivo**. Seleccione **Administrar** \> **perfiles** \> **Crear perfil**.
2. Elija un nombre para el perfil. Cambie **Platform=macOS** y **Profile type=Custom**. Seleccione **Configurar**.
3. Abra el perfil de configuración y cargue **sysext.xml**. Este archivo se creó en el paso anterior.
4. Seleccione **Aceptar**.

   :::image type="content" source="images/mac-system-extension-intune.png" alt-text="La extensión del sistema en Intune página" lightbox="images/mac-system-extension-intune.png":::

5. En la `Assignments` pestaña , asigne este perfil a **Todos los usuarios & Todos los dispositivos**.
6. Revise y cree este perfil de configuración.
