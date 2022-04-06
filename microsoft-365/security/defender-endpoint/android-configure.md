---
title: Configurar Microsoft Defender para punto de conexión en funciones de Android
description: Describe cómo configurar Microsoft Defender para punto de conexión en Android
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mde, android, configuration
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 0e0a8a99444f09d58a43502edd1c94e4cce52301
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664686"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Configuración de características de Defender para punto de conexión en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Acceso condicional con Defender para punto de conexión en Android

Microsoft Defender para punto de conexión en Android junto con Microsoft Intune y Azure Active Directory permite aplicar las directivas de cumplimiento de dispositivos y acceso condicional en función de los niveles de riesgo del dispositivo. Defender para punto de conexión es una solución de Mobile Threat Defense (MTD) que puede implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información sobre cómo configurar Defender para punto de conexión en Android y acceso condicional, consulte [Defender para punto de conexión y Intune](/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Configuración de indicadores personalizados

> [!NOTE]
> Defender para punto de conexión en Android solo admite la creación de indicadores personalizados para direcciones IP y direcciones URL o dominios.

Defender para punto de conexión en Android permite a los administradores configurar indicadores personalizados para admitir también dispositivos Android. Para obtener más información sobre cómo configurar indicadores personalizados, consulte [Administración de indicadores](manage-indicators.md).

## <a name="configure-web-protection"></a>Configuración de la protección web
Defender para punto de conexión en Android permite a los administradores de TI configurar la característica de protección web. Esta funcionalidad está disponible en el centro de administración de Microsoft Endpoint Manager.

> [!NOTE]
> Defender para punto de conexión en Android usaría una VPN para proporcionar la característica de protección web. No es una VPN normal y es una VPN local o de bucle automático que no toma tráfico fuera del dispositivo.
> Para obtener más información, consulte [Configuración de la protección web en dispositivos que ejecutan Android](/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="privacy-controls"></a>Controles de privacidad

> [!IMPORTANT]
> Los controles de privacidad para Microsoft Defender para punto de conexión en Android están en versión preliminar. La siguiente información se refiere al producto preliminar que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Los siguientes controles de privacidad están disponibles para configurar los datos enviados por Defender para punto de conexión desde dispositivos Android:

|Informe de amenazas     |Detalles      |
|--------------------|-------------|
|Informe de malware |Los administradores pueden configurar el control de privacidad para el informe de malware: si la privacidad está habilitada, Defender para punto de conexión no enviará el nombre de la aplicación de malware ni otros detalles de la aplicación como parte del informe de alertas de malware. |
|Informe de phish |Los administradores pueden configurar el control de privacidad para el informe de phish: si la privacidad está habilitada, Defender para punto de conexión no enviará el nombre de dominio ni los detalles del sitio web no seguro como parte del informe de alertas de phish. |
|Evaluación de vulnerabilidades de aplicaciones (solo Android) |De forma predeterminada, solo se envía información sobre las aplicaciones instaladas en el perfil de trabajo para la evaluación de vulnerabilidades. Los administradores pueden deshabilitar la privacidad para incluir aplicaciones personales|

## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>Configuración de la evaluación de vulnerabilidades de aplicaciones para dispositivos BYOD

A partir de la versión 1.0.3425.0303 de Microsoft Defender para punto de conexión en Android, podrá ejecutar evaluaciones de vulnerabilidades del sistema operativo y las aplicaciones instaladas en los dispositivos móviles incorporados.

> [!NOTE]
> La evaluación de vulnerabilidades forma parte de [la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md) en Microsoft Defender para punto de conexión. 

**Notas sobre la privacidad relacionada con las aplicaciones de dispositivos personales (BYOD):**

- Para Android Enterprise con un perfil de trabajo, solo se admitirán las aplicaciones instaladas en el perfil de trabajo.
- Para otros modos BYOD, de forma predeterminada, **no** se habilitará la evaluación de vulnerabilidades de las aplicaciones. Sin embargo, cuando el dispositivo está en modo de administrador, los administradores pueden habilitar explícitamente esta característica a través de Microsoft Endpoint Manager para obtener la lista de aplicaciones instaladas en el dispositivo. Para obtener más información, consulte los detalles siguientes.

### <a name="configure-privacy-for-device-administrator-mode"></a>Configuración de la privacidad para el modo de administrador de dispositivos

Siga estos pasos para **habilitar la evaluación de vulnerabilidades de las aplicaciones desde** dispositivos en modo **de administrador de dispositivos** para los usuarios de destino. 

> [!NOTE]
> De forma predeterminada, esta opción está desactivada para los dispositivos inscritos con el modo de administración de dispositivos.

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **DispositivosPerfiles** >  >  **de** **configuraciónCrear perfil** y escriba la siguiente configuración:

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

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **AplicacionesDirectivas** >  de configuración de **aplicacionesAgregarDispositivos** >  >  **administrados**.
2. Asigne un nombre a la directiva; **Platform > Android Enterprise**; seleccione el tipo de perfil.
3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
4. En Configuración página, seleccione **Usar diseñador de configuración** y agregue **DefenderTVMPrivacyMode** como tipo de clave y valor como **Entero**.
   - Para deshabilitar la vulnerabilidad de las aplicaciones en el perfil de trabajo, escriba el valor como `1` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `0`.
   - Para los usuarios con un conjunto de claves como `0`, Defender for Endpoint enviará la lista de aplicaciones desde el perfil de trabajo al servicio back-end para la evaluación de vulnerabilidades.
5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-privacy-for-phishing-alert-report"></a>Configuración de la privacidad para el informe de alertas de suplantación de identidad (phishing)

El control de privacidad del informe phish se puede usar para deshabilitar la recopilación de información de nombre de dominio o sitio web en el informe de amenazas de phish. Esto proporciona a las organizaciones la flexibilidad de elegir si quieren recopilar el nombre de dominio cuando Defender para punto de conexión detecta y bloquea un sitio web malintencionado o de phish.

### <a name="configure-privacy-for-phishing-alert-report-on-android-device-administrator-enrolled-devices"></a>Configure la privacidad para el informe de alertas de suplantación de identidad (phishing) en dispositivos inscritos en Android Device Administrator:

Siga estos pasos para activarlo para los usuarios de destino:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **DispositivosPerfiles** >  >  **de** **configuraciónCrear perfil** y escriba la siguiente configuración:

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

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **AplicacionesDirectivas** >  de configuración de **aplicacionesAgregarDispositivos** >  >  **administrados**.
2. Asigne un nombre a la directiva, **Platform > Android Enterprise**, seleccione el tipo de perfil.
3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
4. En Configuración página, seleccione **Usar diseñador de configuración** y agregue **DefenderExcludeURLInReport** como clave y tipo de valor como **Integer**.
   - Escriba **1 para habilitar la privacidad**. El valor predeterminado es 0.
5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-privacy-for-malware-threat-report"></a>Configurar la privacidad para el informe de amenazas de malware

El control de privacidad para el informe de amenazas de malware se puede usar para deshabilitar la recopilación de detalles de la aplicación (nombre e información del paquete) del informe de amenazas de malware. Esto proporciona a las organizaciones la flexibilidad de elegir si quieren recopilar el nombre de la aplicación cuando se detecta una aplicación malintencionada.

### <a name="configure-privacy-for-malware-alert-report-on-android-device-administrator-enrolled-devices"></a>Configure la privacidad para el informe de alertas de malware en dispositivos inscritos en Android Device Administrator:

Siga estos pasos para activarlo para los usuarios de destino:

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **DispositivosPerfiles** >  >  **de** **configuraciónCrear perfil** y escriba la siguiente configuración:

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

1. En [Microsoft Endpoint Manager centro de administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a **AplicacionesDirectivas** >  de configuración de **aplicacionesAgregarDispositivos** >  >  **administrados**.
2. Asigne un nombre a la directiva, **Platform > Android Enterprise**, seleccione el tipo de perfil.
3. Seleccione **Microsoft Defender para punto de conexión** como la aplicación de destino.
4. En Configuración página, seleccione **Usar diseñador de configuración** y agregue **DefenderExcludeAppInReport** como clave y tipo de valor como **Entero**.
   - Escriba **1 para habilitar la privacidad**. El valor predeterminado es 0.
5. Haga clic en **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional. Por ejemplo, los dispositivos con una aplicación malintencionada siempre tendrán un nivel de riesgo de "Medio".

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
