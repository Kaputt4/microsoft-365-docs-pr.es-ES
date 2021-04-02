---
title: Configurar las directivas de ATP de Microsoft Defender para macOS en Jamf Pro
description: Obtenga información sobre cómo configurar las directivas de ATP de Microsoft Defender para macOS en Jamf Pro
keywords: policies, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be01d5908e4c79f642cdbbddd75115f6ebc2c713
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499637"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a>Configurar Microsoft Defender para endpoint para directivas de macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Defender para Endpoint para Mac](microsoft-defender-endpoint-mac.md)

Esta página le guiará a través de los pasos que debe seguir para configurar directivas de macOS en Jamf Pro.

Deberá seguir los pasos siguientes:

1. [Obtener el paquete de incorporación de Microsoft Defender para endpoint](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Crear un perfil de configuración en Jamf Pro con el paquete de incorporación](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Configurar Microsoft Defender para la configuración del punto de conexión](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Configurar Microsoft Defender para la configuración de notificación de extremo](#step-4-configure-notifications-settings)

5. [Configurar Microsoft AutoUpdate (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Conceder acceso en disco completo a Microsoft Defender para endpoint](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Aprobar extensión de kernel para Microsoft Defender para endpoint](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Aprobar extensiones del sistema para Microsoft Defender para endpoint](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Configurar extensión de red](#step-9-configure-network-extension)

10. [Programar exámenes con Microsoft Defender para endpoint para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Implementar Microsoft Defender para endpoint para macOS](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Paso 1: Obtener el paquete de incorporación de Microsoft Defender para endpoint

1. En [el Centro de seguridad de Microsoft Defender,](https://securitycenter.microsoft.com )vaya a Configuración > **incorporación**. 

2. Seleccione macOS como sistema operativo y Administración de dispositivos móviles /Microsoft Intune como método de implementación.

    ![Imagen del Centro de seguridad de Microsoft Defender](images/onboarding-macos.png)

3. Seleccione **Descargar paquete de incorporación** (WindowsDefenderATPOnboardingPackage.zip).

4. Extraer `WindowsDefenderATPOnboardingPackage.zip` .

5. Copie el archivo en su ubicación preferida. Por ejemplo, `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Paso 2: Crear un perfil de configuración en Jamf Pro con el paquete de incorporación

1. Busque el archivo `WindowsDefenderATPOnboarding.plist` de la sección anterior.

   ![Imagen del archivo WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. En el panel de Jamf Pro, seleccione **Nuevo**.

    ![Imagen de creación de un nuevo panel de Jamf Pro](images/jamf-pro-configure-profile.png)

3. Escriba los siguientes detalles:

   **General**
   - Nombre: incorporación de MDATP para macOS
   - Descripción: incorporación de MDATP EDR para macOS
   - Categoría: Ninguna
   - Método distribution: Install Automatically
   - Nivel: Nivel de equipo

4. En **Configuración & configuración personalizada,** seleccione **Configurar**.

    ![Imagen de configuración de la aplicación y la configuración personalizada](images/jamfpro-mac-profile.png)

5. Seleccione **Cargar archivo (archivo PLIST) y,** a continuación, en **Dominio de preferencia** escriba: `com.microsoft.wdav.atp` . 

    ![Imagen del archivo de carga de jamfpro plist](images/jamfpro-plist-upload.png)

    ![Imagen de la propiedad de archivo de carga Archivo de lista](images/jamfpro-plist-file.png)

7. Seleccione **Abrir** y seleccione el archivo de incorporación.

    ![Imagen del archivo de incorporación](images/jamfpro-plist-file-onboard.png)

8. Seleccione **Cargar**. 

    ![Imagen de la carga del archivo plist](images/jamfpro-upload-plist.png)


9. Seleccione la **pestaña** Ámbito.

    ![Imagen de la pestaña ámbito](images/jamfpro-scope-tab.png)

10. Seleccione los equipos de destino.

    ![Imagen de los equipos de destino](images/jamfpro-target-computer.png)

    ![Imagen de los destinos](images/jamfpro-targets.png) 

11. Seleccione **Guardar**.

    ![Imagen de los equipos de destino de implementación](images/jamfpro-deployment-target.png)

    ![Imagen de los equipos de destino seleccionados](images/jamfpro-target-selected.png)

12. Seleccione **Listo**.

    ![Imagen de los equipos de grupo de destino](images/jamfpro-target-group.png)

    ![Lista de perfiles de configuración](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Paso 3: Configurar Microsoft Defender para la configuración del punto de conexión

1.  Use las siguientes opciones de configuración de Microsoft Defender para puntos de conexión:

    - enableRealTimeProtection
    - passiveMode
    
    >[!NOTE]
    >No activado de forma predeterminada, si está planeando ejecutar un ANTIVIRUS de terceros para macOS, estafórlo en `true` .

    - exclusiones
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats
    
    >[!NOTE]
    >EICAR está en la muestra, si está pasando por una prueba de concepto, quítela especialmente si está probando EICAR.
        
    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon
    
     Para obtener información, vea [Lista de propiedades para el perfil de configuración de Jamf](mac-preferences.md#property-list-for-jamf-configuration-profile).

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. Guarde el archivo como `MDATP_MDAV_configuration_settings.plist` .


3.  En el panel de Jamf Pro, seleccione **General**.

    ![Imagen del nuevo panel de Jamf Pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Escriba los siguientes detalles:

    **General**
    
    - Nombre: opciones de configuración de MDATP MDAV
    - Descripción:\<blank\>
    - Categoría: Ninguno (predeterminado)
    - Método distribution: Install Automatically (default)
    - Nivel: Nivel del equipo (predeterminado)

    ![Imagen de las opciones de configuración de MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. En **Configuración & configuración personalizada,** seleccione **Configurar**.

    ![Imagen de la aplicación y la configuración personalizada](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Seleccione **Cargar archivo (archivo PLIST).**

    ![Imagen del archivo plist de configuración](images/6f85269276b2278eca4bce84f935f87b.png)

7. En **Dominio de preferencias,** escriba `com.microsoft.wdav` y, a continuación,  **seleccione Cargar archivo PLIST**.

    ![Imagen del dominio de preferencias de configuración](images/db15f147dd959e872a044184711d7d46.png)

8. Seleccione **Elegir archivo**.

    ![Imagen de las opciones de configuración elija archivo](images/526e978761fc571cca06907da7b01fd6.png)

9. Seleccione el **MDATP_MDAV_configuration_settings.plist** y, a continuación, **seleccione Abrir**.

    ![Imagen de las opciones de configuración de mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. Seleccione **Cargar**.

    ![Imagen de la carga de configuración](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Imagen de la imagen de carga de opciones de configuración](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Si se carga el archivo de Intune, se producirá el siguiente error:<br>
    >![Imagen de la carga de archivos de Intune de configuración](images/8e69f867664668796a3b2904896f0436.png)


11. Seleccione **Guardar**. 

    ![Imagen de configuración Guardar imagen](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. El archivo se carga.

    ![Imagen de la imagen cargada del archivo de configuración](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Imagen del archivo de configuración cargado](images/a422e57fe8d45689227e784443e51bd1.png)

13. Seleccione la **pestaña** Ámbito.

    ![Imagen del ámbito de configuración](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Seleccione **Grupo de máquinas de Contoso**. 

15. Seleccione **Agregar** y, a continuación, **seleccione Guardar**.

    ![Imagen de configuración addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Imagen de las opciones de configuración guardar agregar](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Seleccione **Listo**. Verá el nuevo perfil **de configuración**.

    ![Imagen de la imagen de perfil de configuración de configuración](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a>Paso 4: Configurar la configuración de notificaciones

Estos pasos son aplicables a macOS 10.15 (Catalina) o versiones posteriores.

1. En el panel de Jamf Pro, seleccione **Equipos** y, a continuación, **Perfiles de configuración.**

2. Haga **clic en** Nuevo y escriba los siguientes detalles para **Opciones:**
    
    - Ficha **General**: 
        - **Nombre:** configuración de notificación MDATP MDAV
        - **Descripción:** macOS 10.15 (Catalina) o posterior
        - **Categoría**: None *(valor predeterminado)*
        - **Método Distribution:** Instalar automáticamente *(predeterminado)*
        - **Nivel:** Nivel de equipo *(predeterminado)*

        ![Imagen de las opciones de configuración mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - Tab **Notifications**, click **Add** y escriba los siguientes valores:
        - **Id. de agrupación:**`com.microsoft.wdav.tray`
        - **Alertas críticas:** haga clic **en Deshabilitar**
        - **Notificaciones:** haga clic en **Habilitar**
        - **Tipo de alerta de banner:** Seleccione **Incluir** y **Temporal** *(predeterminado)*
        - **Notificaciones en la pantalla de bloqueo:** Haga clic **en Ocultar**
        - **Notificaciones en el Centro de notificaciones:** haga clic en **Mostrar**
        - **Icono de aplicación de distintivo:** Haga clic en **Mostrar**

        ![Imagen de la bandeja de notificaciones mdatpmdav de configuración](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**
        - **Id. de agrupación:**`com.microsoft.autoupdate2`
        - Configure el resto de la configuración en los mismos valores anteriores

        ![Imagen de las notificaciones mdatpmdav de configuración mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Ten en cuenta que ahora tienes dos "tablas" con configuraciones de notificación, una para id. de **agrupación: com.microsoft.wdav.tray** y otra para id. de **lote: com.microsoft.autoupdate2**. Aunque puede configurar la configuración de alertas según sus **requisitos,** los IDs de agrupación deben ser exactamente los mismos que se han descrito anteriormente y el modificador **Include** debe estar **En** para notificaciones.

3. Seleccione la **pestaña Ámbito** y, a continuación, **seleccione Agregar**.

    ![Imagen de la adición de ámbito de configuración](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Seleccione **Grupo de máquinas de Contoso**. 

5. Seleccione **Agregar** y, a continuación, **seleccione Guardar**.
    
    ![Imagen de configuración de configuración de contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Imagen de las opciones de configuración agregar guardar](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Seleccione **Listo**. Verá el nuevo perfil **de configuración**.
    ![Imagen de la configuración realizada img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Paso 5: Configurar Microsoft AutoUpdate (MAU)

1. Use las siguientes opciones de configuración de Microsoft Defender para puntos de conexión:

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. Guárdelo como `MDATP_MDAV_MAU_settings.plist` .

3. En el panel de Jamf Pro, seleccione **General**. 

    ![Imagen de la imagen general de configuración](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Escriba los siguientes detalles:

    **General** 
    
    - Nombre: configuración de MDATP MDAV MAU
    - Descripción: Configuración de Microsoft AutoUpdate para MDATP para macOS
    - Categoría: Ninguno (predeterminado)
    - Método distribution: Install Automatically (default)
    - Nivel: Nivel del equipo (predeterminado)

5. En **Configuración & configuración personalizada,** seleccione **Configurar**.

    ![Imagen de la aplicación de configuración y la configuración personalizada](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Seleccione **Cargar archivo (archivo PLIST).**

    ![Imagen de la configuración plist](images/1213872db5833aa8be535da57653219f.png)  

7. En **Dominio de preferencia** escriba: , luego seleccione Cargar archivo `com.microsoft.autoupdate2` **PLIST**.

    ![Imagen del dominio de configuración previa a la configuración](images/1213872db5833aa8be535da57653219f.png)

8. Seleccione **Elegir archivo**.

    ![Imagen de choosefile de configuración de configuración](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Seleccione **MDATP_MDAV_MAU_settings.plist**.

    ![Imagen de la configuración mdatpmdavmau settings](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Seleccione **Cargar**.
    ![Imagen de configuración de configuración uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Imagen de configuración de configuración uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Seleccione **Guardar**.

    ![Imagen de la configuración saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Seleccione la **pestaña** Ámbito.
   
     ![Imagen de la tabla de ámbito de configuración](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Elija **Agregar**.
    
    ![Imagen de la configuración addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Imagen de la configuración addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Imagen de la configuración addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Seleccione **Listo**.
    
    ![Imagen de configuración doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Paso 6: Conceder acceso en disco completo a Microsoft Defender para endpoint

1. En el panel de Jamf Pro, seleccione **Perfiles de configuración**.

    ![Imagen del perfil de configuración de configuración](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Seleccione **+ Nuevo**. 

3. Escriba los siguientes detalles:

    **General** 
    - Nombre: MDATP MDAV: conceder acceso en disco completo a EDR y AV
    - Descripción: en macOS Catalina o versiones posteriores, el nuevo control de directiva de preferencias de privacidad
    - Categoría: Ninguna
    - Método de distribución: Instalar automáticamente
    - Nivel: nivel de equipo


    ![Imagen de la configuración general](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. En **Configurar el control de directiva de preferencias de privacidad,** seleccione **Configurar**.

    ![Imagen del control de directiva de privacidad de configuración](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. En **Control de directiva de preferencias de** privacidad, escriba los siguientes detalles:

    - Identificador: `com.microsoft.wdav`
    - Tipo de identificador: Id. de agrupación
    - Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Imagen de los detalles de control de la directiva de preferencias de privacidad de configuración](images/22cb439de958101c0a12f3038f905b27.png)

6. Seleccione **+ Agregar**.

    ![Imagen de la configuración agregar directiva del sistema todos los archivos](images/bd93e78b74c2660a0541af4690dd9485.png)

    - En Aplicación o servicio: Establecer en **SystemPolicyAllFiles**

    - En "access": Set to **Allow**

7. Seleccione **Guardar** (no el que se encuentra en la parte inferior derecha).

    ![Imagen de configuración de guardar imágenes](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Haga clic `+` en el signo situado junto a App **Access** para agregar una nueva entrada.

    ![Imagen del acceso a la aplicación de configuración](images/tcc-add-entry.png)

9. Escriba los siguientes detalles:

    - Identificador: `com.microsoft.wdav.epsext`
    - Tipo de identificador: Id. de agrupación
    - Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Seleccione **+ Agregar**.

    ![Imagen de la entrada tcc epsext de configuración](images/tcc-epsext-entry.png)

    - En Aplicación o servicio: Establecer en **SystemPolicyAllFiles**

    - En "access": Set to **Allow**

11. Seleccione **Guardar** (no el que se encuentra en la parte inferior derecha).

    ![Imagen de la configuración tcc epsext image2](images/tcc-epsext-entry2.png)

12. Seleccione la **pestaña** Ámbito.

    ![Imagen del ámbito de configuración](images/2c49b16cd112729b3719724f581e6882.png)

13. Seleccione **+ Agregar**.

    ![Imagen de la configuración addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione **MachineGroup de Contoso**. 

    ![Imagen de configuración de configuración contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Elija **Agregar**. 

16. Seleccione **Guardar**. 
    
17. Seleccione **Listo**.
    
    ![Imagen de la configuración de donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Imagen de la configuración de donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

Como alternativa, puede descargar [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) y cargarlo en los perfiles de configuración de JAMF, como se describe en [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Cargar un perfil de configuración en Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Paso 7: Aprobar extensión de kernel para Microsoft Defender para endpoint

> [!CAUTION]
> Los dispositivos Apple Silicon (M1) no son compatibles con KEXT. La instalación de un perfil de configuración que consta de directivas KEXT producirá un error en estos dispositivos.

1. En **perfiles de configuración,** seleccione **+ Nuevo**.

    ![Captura de pantalla de una publicación de redes sociales Descripción generada automáticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Escriba los siguientes detalles:

    **General** 
    
    - Nombre: MDATP MDAV Kernel Extension
    - Descripción: extensión de kernel MDATP (kext)
    - Categoría: Ninguna
    - Método distribution: Install Automatically
    - Nivel: Nivel de equipo

    ![Imagen del kernel mdatpmdav de configuración](images/24e290f5fc309932cf41f3a280d22c14.png)

3. En **Configurar extensiones de kernel aprobadas,** seleccione **Configurar**.

    ![Imagen de configuración de configuración aprobada ext del kernel](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. En **Extensiones de kernel aprobadas,** escriba los siguientes detalles:

    - Nombre para mostrar: Microsoft Corp.
    - Id. de equipo: UBF8T346G9

    ![Imagen de la extensión del kernel de appr de configuración](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Seleccione la **pestaña** Ámbito.

    ![Imagen de la pestaña ámbito de configuración img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Seleccione **+ Agregar**.

7. Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione Grupo de máquinas **de Contoso**.

8. Seleccione **+ Agregar**.

    ![Imagen de las opciones de configuración agregar imágenes](images/0dde8a4c41110dbc398c485433a81359.png)

9. Seleccione **Guardar**.

    ![Imagen de la configuración saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. Seleccione **Listo**.

    ![Imagen de configuración doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

Como alternativa, puede descargar [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) y cargarlo en los perfiles de configuración de JAMF, como se describe en [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Cargar un perfil de configuración en Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Paso 8: Aprobar extensiones de sistema para Microsoft Defender para endpoint

1. En **perfiles de configuración,** seleccione **+ Nuevo**.

    ![Captura de pantalla de una publicación de redes sociales Descripción generada automáticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Escriba los siguientes detalles:

    **General**
    
    - Nombre: MDATP MDAV System Extensions
    - Descripción: extensiones del sistema MDATP
    - Categoría: Ninguna
    - Método distribution: Install Automatically
    - Nivel: Nivel de equipo

    ![Imagen de configuración sysext new prof](images/sysext-new-profile.png)

3. En **Extensiones del sistema,** seleccione **Configurar**.

   ![Imagen de configuración sysext config](images/sysext-configure.png)

4. En **Extensiones del sistema,** escriba los siguientes detalles:

   - Nombre para mostrar: Microsoft Corp. Extensiones del sistema
   - Tipos de extensión del sistema: extensiones de sistema permitidas
   - Identificador de equipo: UBF8T346G9
   - Extensiones de sistema permitidas:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Imagen de las opciones de configuración sysextconfig2](images/sysext-configure2.png)

5. Seleccione la **pestaña** Ámbito.

    ![Imagen del ámbito de configuración de configuraciónimage](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Seleccione **+ Agregar**.

7. Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione Grupo de máquinas **de Contoso**.

8. Seleccione **+ Agregar**.

   ![Imagen de addima de configuración](images/0dde8a4c41110dbc398c485433a81359.png)

9. Seleccione **Guardar**.

   ![Imagen del ámbito sysext de configuración](images/sysext-scope.png)

10. Seleccione **Listo**.

    ![Imagen de las opciones de configuración sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Paso 9: Configurar extensión de red

Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint para Mac inspecciona el tráfico de sockets e informa de esta información al portal del Centro de seguridad de Microsoft Defender. La siguiente directiva permite que la extensión de red realice esta funcionalidad.

Estos pasos son aplicables a macOS 10.15 (Catalina) o versiones posteriores.

1. En el panel de Jamf Pro, seleccione **Equipos** y, a continuación, **Perfiles de configuración.**

2. Haga **clic en** Nuevo y escriba los siguientes detalles para **Opciones:**

    - Ficha **General**: 
        - **Nombre**: Extensión de red atp de Microsoft Defender
        - **Descripción:** macOS 10.15 (Catalina) o posterior
        - **Categoría**: None *(valor predeterminado)*
        - **Método Distribution:** Instalar automáticamente *(predeterminado)*
        - **Nivel:** Nivel de equipo *(predeterminado)*

    - Filtro **de contenido de pestaña**:
        - **Nombre del filtro:** Filtro de contenido de ATP de Microsoft Defender
        - **Identificador**: `com.microsoft.wdav`
        - Dejar **en blanco dirección de** servicio , **organización**, nombre **de** usuario , **contraseña**, **certificado** (**Incluir** *no está* seleccionado)
        - **Orden de filtro:** Inspector
        - **Filtro de sockets**: `com.microsoft.wdav.netext`
        - **Requisito designado del filtro de socket:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Dejar **campos de filtro de** red en blanco (**Incluir** no *está* seleccionado)

        Tenga en cuenta que los valores **exactos identificador**, filtro de **socket** y filtro **de** socket designados como se especifica anteriormente.

        ![Imagen de las opciones de configuración mdatpmdav](images/netext-create-profile.png)

3. Seleccione la **pestaña** Ámbito.

   ![Imagen de la pestaña sco de configuración](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Seleccione **+ Agregar**.

5. Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione Grupo de máquinas **de Contoso**.

6. Seleccione **+ Agregar**.

    ![Imagen de configuración adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. Seleccione **Guardar**.

    ![Imagen de la configuración de savimg netextscop](images/netext-scope.png)

8. Seleccione **Listo**.

    ![Imagen de la configuración netextfinal](images/netext-final.png)

Como alternativa, puede descargar [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) y cargarlo en los perfiles de configuración de JAMF, como se describe en [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Cargar un perfil de configuración en Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a>Paso 10: Programar exámenes con Microsoft Defender para endpoint para Mac
Siga las instrucciones de [Programar exámenes con Microsoft Defender para Endpoint para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a>Paso 11: Implementar Microsoft Defender para endpoint para macOS

1. Navegue hasta donde guardó `wdav.pkg` .

    ![Imagen del explorador de archivos wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Cámbiele el nombre a `wdav_MDM_Contoso_200329.pkg` .

    ![Imagen del explorador de archivos1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Abra el panel de Jamf Pro.

    ![Imagen de la configuración jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Seleccione el equipo y haga clic en el icono de engranaje en la parte superior y, a continuación, seleccione **Administración del equipo**.

    ![Imagen de la configuración compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. En **Paquetes**, seleccione **+ Nuevo**. 
    ![Una imagen que contiene el paquete de descripción de aves generado automáticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. En **Nuevo paquete,** escriba los siguientes detalles:

    **Ficha General**
    - Nombre para mostrar: déjelo en blanco por ahora. Porque se restablecerá al elegir el paquete.
    - Categoría: Ninguno (predeterminado)
    - Filename: Choose File

    ![Imagen de la ficha general de configuración](images/21de3658bf58b1b767a17358a3f06341.png)

    Abra el archivo y apunte a `wdav.pkg` o `wdav_MDM_Contoso_200329.pkg` .
    
    ![Captura de pantalla de una pantalla de equipo Descripción generada automáticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Seleccione **Abrir**. Establece el **nombre para mostrar en** Protección contra amenazas avanzada de Microsoft Defender y Antivirus de Microsoft **Defender**.

    **El archivo de** manifiesto no es necesario. La Protección contra amenazas avanzada de Microsoft Defender funciona sin archivo de manifiesto.
    
    **Pestaña Opciones**<br> Mantenga los valores predeterminados.

    **Pestaña Limitaciones**<br> Mantenga los valores predeterminados.
    
     ![Imagen de la pestaña de limitación de configuración](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. Seleccione **Guardar**. El paquete se carga en Jamf Pro. 

   ![Imagen del paquete de configuración upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   El paquete puede tardar unos minutos en estar disponible para la implementación.
   
   ![Imagen del paquete de configuración upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Vaya a la **página Directivas.**

    ![Imagen de las opciones de configuración](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Seleccione **+ Nuevo** para crear una nueva directiva.

    ![Imagen de la nueva directiva de configuración](images/847b70e54ed04787e415f5180414b310.png)


11. En **General,** escriba los siguientes detalles:

    - Nombre para mostrar: MDATP Onboarding Contoso 200329 v100.86.92 o posterior

    ![Imagen de configuraciónmdatponboard ](images/625ba6d19e8597f05e4907298a454d28.png)

12. Seleccione **Check-in periódico**. 
    
    ![Imagen de la comprobación de la recursividad de las opciones de configuración](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. Seleccione **Guardar**. 
 
14. Seleccione **Paquetes > Configurar**.
 
    ![Imagen de configuración del paquete de configuración configurar](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Selecciona el **botón Agregar** junto a Protección contra amenazas avanzada de Microsoft Defender y Antivirus de **Microsoft Defender.**

    ![Imagen de configuración MDATP y MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Seleccione **Guardar**.

    ![Imagen de configuraciónsavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. Seleccione la **pestaña** Ámbito.  

    ![Imagen de configuración scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Seleccione los equipos de destino.

    ![Imagen de configuración tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Scope**
    
    Elija **Agregar**.
    
    ![Imagen de configuración ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Imagen de las opciones de configuración ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Autoservicio**
    
    ![Imagen de selfservice de configuración](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Seleccione **Listo**. 

    ![Imagen de las opciones de configuración do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Imagen de las opciones de configuración do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




