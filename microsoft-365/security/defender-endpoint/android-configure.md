---
title: Configurar Microsoft Defender para punto de conexión en funciones de Android
description: Describe cómo configurar Microsoft Defender para punto de conexión en Android
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mde, android, configuration
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 8f2d1200d3d703e89959dbe8446838f266d1731a
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67703376"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Configurar Defender para punto de conexión en características de Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Acceso condicional con Defender para punto de conexión en Android

Microsoft Defender para punto de conexión en Android, junto con Microsoft Intune y Azure Active Directory, permite aplicar las directivas de cumplimiento de dispositivos y acceso condicional en función de los niveles de riesgo del dispositivo. Defender para punto de conexión es una solución de Mobile Threat Defense (MTD) que puede implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información sobre cómo configurar Defender para punto de conexión en Android y acceso condicional, consulte [Defender para punto de conexión y Intune](/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Configuración de indicadores personalizados

> [!NOTE]
> Defender para punto de conexión en Android solo admite la creación de indicadores personalizados para direcciones IP y direcciones URL o dominios.

Defender para punto de conexión en Android permite a los administradores configurar indicadores personalizados para admitir también dispositivos Android. Para obtener más información sobre cómo configurar indicadores personalizados, consulte [Administración de indicadores](manage-indicators.md).

## <a name="configure-web-protection"></a>Configuración de la protección web
Defender para punto de conexión en Android permite a los administradores de TI configurar la característica de protección web. Esta funcionalidad está disponible en el Centro de Endpoint Manager Administración de Microsoft.

La [protección web](web-protection-overview.md) ayuda a proteger los dispositivos frente a las amenazas web y a los usuarios frente a ataques de suplantación de identidad. Tenga en cuenta que los indicadores personalizados y contra la suplantación de identidad (URL y direcciones IP) se admiten como parte de la protección web. El filtrado de contenido web no se admite actualmente en plataformas móviles.

> [!NOTE]
> Defender para punto de conexión en Android usaría una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.
> Para obtener más información, consulte [Configuración de la protección web en dispositivos que ejecutan Android](/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="network-protection"></a>Protección de red
>[!NOTE]
>La protección de red en Microsoft Defender para punto de conexión está ahora en versión preliminar pública. La siguiente información se refiere al producto preliminar que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Esta característica proporciona protección contra amenazas no autorizadas Wi-Fi relacionadas y certificados no autorizados que son el vector de ataque principal para las redes Wi-Fi. Los administradores pueden enumerar los certificados de entidad de certificación (CA) raíz y entidad de certificación raíz privada en el Centro de microsoft Endpoint Manager Administración y establecer la confianza con los puntos de conexión. Proporciona al usuario una experiencia guiada para conectarse a redes seguras y también le notifica si se detecta una amenaza relacionada. 

Incluye varios controles de administración para ofrecer flexibilidad, como la capacidad de configurar la característica desde el centro de microsoft Endpoint Manager Administración, así como agregar certificados de confianza. Los administradores también pueden habilitar [los controles de privacidad](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) para configurar los datos enviados por Defender para punto de conexión desde dispositivos Android.

La protección de red en Microsoft Defender para punto de conexión está habilitada de forma predeterminada. Los administradores pueden usar los pasos siguientes para **configurar la protección de red en dispositivos Android.**

1. En Microsoft Endpoint Manager Administración, vaya a Aplicaciones > Directivas de configuración de aplicaciones. Cree una nueva directiva de configuración de aplicaciones.
    > [!div class="mx-imgBorder"]
    > ![Imagen de cómo crear una directiva.](images/android-mem.png)
1. Proporcione un nombre y una descripción para identificar de forma única la directiva. Seleccione **"Android Enterprise"** como plataforma y **"Solo perfil de trabajo de propiedad personal"** como tipo de perfil y **"Microsoft Defender"** como aplicación de destino.
    > [!div class="mx-imgBorder"]
    > ![Imagen de los detalles de la directiva.](images/appconfigdetails.png)
1. En la página Configuración, seleccione **"Usar diseñador de configuración"** y agregue **"Habilitar protección de red en Microsoft Defender"** como clave y valor como **"0"** para deshabilitar la protección de red. (La protección de red está habilitada de forma predeterminada)
    > [!div class="mx-imgBorder"]
    > ![Imagen de cómo seleccionar habilitar la directiva de protección de red](images/selectnp.png)
    
    > [!div class="mx-imgBorder"]
    > ![Imagen de agregar directiva de configuración.](images/npvalue.png)
1. Si su organización usa entidades de certificación raíz que podrían ser privadas por naturaleza, es preciso establecer una confianza explícita entre Intune (solución MDM) y los dispositivos del usuario para que defender no los detecte como certificados no autorizados.  

    Para establecer la confianza para las ENTIDADes de certificación raíz, use **"Lista de certificados de entidad de certificación de confianza para protección de red (versión preliminar)"** como clave y, en valor, agregue la **"lista separada por comas de huellas digitales de certificado"**.
    > [!div class="mx-imgBorder"]
    > ![Imagen del certificado de entidad de certificación de confianza.](images/trustca.png)

1. Para otras configuraciones relacionadas con la protección de red, agregue las siguientes claves y el valor correspondiente correspondiente.
<br>

    | Clave de configuración| Descripción|
    |---|---|
    |Habilitación de la privacidad de protección de red|1 - Habilitar , 0 - Deshabilitar ; Esta configuración la administran los administradores de TI para habilitar o deshabilitar la privacidad en la protección de red.|
    |Permitir que los usuarios confíen en redes y certificados|1 - Habilitar , 0 - Deshabilitar ; Los administradores de TI usan esta configuración para habilitar o deshabilitar la experiencia de usuario final en la aplicación para confiar y desconfiar de las redes no seguras y sospechosas y los certificados malintencionados.|
    |Corrección automática de alertas de protección de red|1 - Habilitar , 0 - Deshabilitar ; Los administradores de TI usan esta configuración para habilitar o deshabilitar las alertas de corrección que se envían cuando un usuario realiza actividades de corrección, como cambiar a un Wi-Fi puntos de acceso más seguro o eliminar certificados sospechosos detectados por Defender.|
1. Agregue los grupos necesarios en los que se tendrá que aplicar la directiva. Revise y cree la directiva.

## <a name="privacy-controls"></a>Controles de privacidad

Los siguientes controles de privacidad están disponibles para configurar los datos enviados por Defender para punto de conexión desde dispositivos Android:

|Informe de amenazas     |Detalles      |
|--------------------|-------------|
|Informe de malware |Los administradores pueden configurar el control de privacidad para el informe de malware: si la privacidad está habilitada, Defender para punto de conexión no enviará el nombre de la aplicación de malware ni otros detalles de la aplicación como parte del informe de alertas de malware. |
|Informe de phish |Los administradores pueden configurar el control de privacidad para el informe de phish: si la privacidad está habilitada, Defender para punto de conexión no enviará el nombre de dominio ni los detalles del sitio web no seguro como parte del informe de alertas de phish. |
|Evaluación de vulnerabilidades de aplicaciones (solo Android) |De forma predeterminada, solo se envía información sobre las aplicaciones instaladas en el perfil de trabajo para la evaluación de vulnerabilidades. Los administradores pueden deshabilitar la privacidad para incluir aplicaciones personales|
|Protección de red (versión preliminar)| Los administradores pueden habilitar o deshabilitar la privacidad en la protección de red: si están habilitados, Defender no enviará detalles de red.|

### <a name="configure-privacy-alert-report"></a>Configurar el informe de alertas de privacidad
Los administradores ahora pueden habilitar el control de privacidad para el informe de phish, el informe de malware y el informe de red enviados por Microsoft Defender para punto de conexión en Android. Esto garantizará que el nombre de dominio, los detalles de la aplicación y los detalles de red respectivamente no se envíen como parte de la alerta cada vez que se detecte una amenaza correspondiente.

Administración Controles de privacidad (MDM) Siga estos pasos para habilitar la privacidad.

1. En el Centro de administración de Microsoft Endpoint Manager, vaya a **Aplicaciones > Directivas de configuración de aplicaciones > Agregar dispositivos administrados >**.

2. Asigne un nombre a la directiva **, Platform > Android Enterprise, seleccione el tipo de perfil**.

3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.

4. En la página Configuración, seleccione **Usar diseñador de configuración** y haga clic en **Agregar**. 
5. Seleccione la configuración de privacidad necesaria:
    - Ocultar direcciones URL en el informe
    - Ocultar direcciones URL en el informe para el perfil personal
    - Ocultar los detalles de la aplicación en el informe
    - Ocultar los detalles de la aplicación en el informe para el perfil personal
    - Habilitación de la privacidad de protección de red

6. Para habilitar la privacidad, escriba el valor entero como 1 y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en 0 para MDE en el perfil de trabajo y 1 para MDE en perfil personal.

7. Revise y asigne este perfil a los dispositivos o usuarios de destino.

**Controles de privacidad del usuario final**

Estos controles ayudan al usuario final a configurar la información compartida con su organización.

1. En el **caso del perfil de trabajo de Android Enterprise**, los controles de usuario final no estarán visibles. Los administradores controlan esta configuración.
2. Para el **perfil personal de Android Enterprise**, el control se muestra en **Configuración> privacidad**.
3. Los usuarios verán un botón de alternancia para información de sitio no seguro, aplicaciones malintencionadas y protección de red.

Estos alternancias solo estarán visibles si el administrador lo habilita. Los usuarios pueden decidir si quieren enviar la información a su organización o no.

La habilitación o deshabilitación de los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.


## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>Configuración de la evaluación de vulnerabilidades de aplicaciones para dispositivos BYOD

A partir de la versión 1.0.3425.0303 de Microsoft Defender para punto de conexión en Android, podrá ejecutar evaluaciones de vulnerabilidades del sistema operativo y las aplicaciones instaladas en los dispositivos móviles incorporados.

> [!NOTE]
> La evaluación de vulnerabilidades forma parte de [Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/defender-vulnerability-management.md) en Microsoft Defender para punto de conexión. 

**Notas sobre la privacidad relacionada con las aplicaciones de dispositivos personales (BYOD):**

- Para Android Enterprise con un perfil de trabajo, solo se admitirán las aplicaciones instaladas en el perfil de trabajo.
- Para otros modos BYOD, de forma predeterminada, **no** se habilitará la evaluación de vulnerabilidades de las aplicaciones. Sin embargo, cuando el dispositivo está en modo de administrador, los administradores pueden habilitar explícitamente esta característica a través de Microsoft Endpoint Manager para obtener la lista de aplicaciones instaladas en el dispositivo. Para obtener más información, consulte los detalles siguientes.

### <a name="configure-privacy-for-device-administrator-mode"></a>Configuración de la privacidad para el modo de administrador de dispositivos

Siga estos pasos para **habilitar la evaluación de vulnerabilidades de las aplicaciones desde** dispositivos en modo **de administrador de dispositivos** para los usuarios de destino. 

> [!NOTE]
> De forma predeterminada, esta opción está desactivada para los dispositivos inscritos con el modo de administración de dispositivos.

1. En [El Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) , vaya a **Perfiles** >  de configuración de **dispositivos** > **Crear perfil** y escriba la siguiente configuración:

   - **Plataforma**: seleccione Administrador de dispositivos Android
   - **Perfil**: seleccione "Personalizado" y haga clic en Crear.

2. En la sección **Aspectos básicos** , especifique un nombre y una descripción del perfil.

3. En **Configuración**, seleccione Agregar **configuración de OMA-URI** :

   - **Nombre**: escriba un nombre y una descripción únicos para esta configuración de OMA-URI para que pueda encontrarla fácilmente más adelante.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - Tipo de datos: seleccione Entero en la lista desplegable.
   - Valor: escriba 0 para deshabilitar la configuración de privacidad (de forma predeterminada, el valor es 1)

4. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>Configuración de la privacidad para el perfil de trabajo de Android Enterprise

Defender for Endpoint admite la evaluación de vulnerabilidades de las aplicaciones en el perfil de trabajo. Sin embargo, en caso de que quiera desactivar esta característica para los usuarios de destino, puede usar los pasos siguientes:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.
2. Asigne un nombre a la directiva; **Plataforma > Android Enterprise**; seleccione el tipo de perfil.
3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
4. En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderTVMPrivacyMode** como tipo de clave y valor como **Entero**.
   - Para deshabilitar la vulnerabilidad de las aplicaciones en el perfil de trabajo, escriba el valor como `1` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `0`.
   - Para los usuarios con un conjunto de claves como `0`, Defender for Endpoint enviará la lista de aplicaciones desde el perfil de trabajo al servicio back-end para la evaluación de vulnerabilidades.
5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-privacy-for-phishing-alert-report"></a>Configuración de la privacidad para el informe de alertas de suplantación de identidad (phishing)

El control de privacidad del informe phish se puede usar para deshabilitar la recopilación de información de nombre de dominio o sitio web en el informe de amenazas de phish. Esto proporciona a las organizaciones la flexibilidad de elegir si quieren recopilar el nombre de dominio cuando Defender para punto de conexión detecta y bloquea un sitio web malintencionado o de phish.

### <a name="configure-privacy-for-phishing-alert-report-on-android-device-administrator-enrolled-devices"></a>Configure la privacidad para el informe de alertas de suplantación de identidad (phishing) en dispositivos inscritos en Android Device Administrator:

Siga estos pasos para activarlo para los usuarios de destino:

1. En [El Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) , vaya a **Perfiles** >  de configuración de **dispositivos** > **Crear perfil** y escriba la siguiente configuración:

   - **Plataforma**: seleccione Administrador de dispositivos Android.
   - **Perfil**: seleccione "Personalizado" y haga clic en **Crear**.

2. En la sección **Aspectos básicos** , especifique un nombre y una descripción del perfil.

3. En **Configuración**, seleccione Agregar **configuración de OMA-URI** :

   - **Nombre**: escriba un nombre y una descripción únicos para esta configuración de OMA-URI para que pueda encontrarla fácilmente más adelante.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeURLInReport**
   - Tipo de datos: seleccione Entero en la lista desplegable.
   - Valor: escriba 1 para habilitar la configuración de privacidad. El valor predeterminado es 0.

4. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

### <a name="configure-privacy-for-phishing-alert-report-on-android-enterprise-work-profile"></a>Configuración de la privacidad para el informe de alertas de suplantación de identidad (phishing) en el perfil de trabajo de Android Enterprise

Siga estos pasos para activar la privacidad de los usuarios de destino en el perfil de trabajo:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.
2. Asigne un nombre a la directiva, **Platform > Android Enterprise**, seleccione el tipo de perfil.
3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
4. En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderExcludeURLInReport** como tipo de clave y valor como **Integer**.
   - Escriba **1 para habilitar la privacidad**. El valor predeterminado es 0.
5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-privacy-for-malware-threat-report"></a>Configurar la privacidad para el informe de amenazas de malware

El control de privacidad para el informe de amenazas de malware se puede usar para deshabilitar la recopilación de detalles de la aplicación (nombre e información del paquete) del informe de amenazas de malware. Esto proporciona a las organizaciones la flexibilidad de elegir si quieren recopilar el nombre de la aplicación cuando se detecta una aplicación malintencionada.

### <a name="configure-privacy-for-malware-alert-report-on-android-device-administrator-enrolled-devices"></a>Configure la privacidad para el informe de alertas de malware en dispositivos inscritos en Android Device Administrator:

Siga estos pasos para activarlo para los usuarios de destino:

1. En [El Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) , vaya a **Perfiles** >  de configuración de **dispositivos** > **Crear perfil** y escriba la siguiente configuración:

   - **Plataforma**: seleccione Administrador de dispositivos Android.
   - **Perfil**: seleccione "Personalizado" y haga clic en **Crear**.

2. En la sección **Aspectos básicos** , especifique un nombre y una descripción del perfil.

3. En **Configuración**, seleccione Agregar **configuración de OMA-URI** :

   - **Nombre**: escriba un nombre y una descripción únicos para esta configuración de OMA-URI para que pueda encontrarla fácilmente más adelante.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - Tipo de datos: seleccione Entero en la lista desplegable.
   - Valor: escriba 1 para habilitar la configuración de privacidad. El valor predeterminado es 0.

4. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional. Por ejemplo, los dispositivos con una aplicación malintencionada siempre tendrán un nivel de riesgo de "Medio".

### <a name="configure-privacy-for-malware-alert-report-on-android-enterprise-work-profile"></a>Configuración de la privacidad para el informe de alertas de malware en el perfil de trabajo de Android Enterprise

Siga estos pasos para activar la privacidad de los usuarios de destino en el perfil de trabajo:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **Directivas** >  de **configuración** >  de aplicaciones **Agregar** > **dispositivos administrados**.
2. Asigne un nombre a la directiva, **Platform > Android Enterprise**, seleccione el tipo de perfil.
3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
4. En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderExcludeAppInReport** como tipo de clave y valor como **Entero**.
   - Escriba **1 para habilitar la privacidad**. El valor predeterminado es 0.
5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional. Por ejemplo, los dispositivos con una aplicación malintencionada siempre tendrán un nivel de riesgo de "Medio".

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
