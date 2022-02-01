---
title: Configurar Microsoft Defender para punto de conexión en funciones de Android
description: Describe cómo configurar Microsoft Defender para Endpoint en Android
keywords: microsoft, defender, Microsoft Defender para Endpoint, mde, android, configuration
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
ms.openlocfilehash: 92a927bf0cb3a5e568ca2b02d60d641907bc0407
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "62295410"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Configurar Defender para las características de Endpoint en Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Acceso condicional con Defender para endpoint en Android

Microsoft Defender para Endpoint en Android junto con Microsoft Intune y Azure Active Directory permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de los niveles de riesgo del dispositivo. Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.

Para obtener más información sobre cómo configurar Defender para Endpoint en Android y acceso condicional, consulta [Defender for Endpoint e Intune](/mem/intune/protect/advanced-threat-protection).

## <a name="configure-custom-indicators"></a>Configurar indicadores personalizados

> [!NOTE]
> Defender for Endpoint en Android solo admite la creación de indicadores personalizados para direcciones IP y direcciones URL/dominios.

Defender para Endpoint en Android permite a los administradores configurar indicadores personalizados para admitir dispositivos Android también. Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](manage-indicators.md).

## <a name="configure-web-protection"></a>Configurar la protección web
Defender for Endpoint en Android permite a los administradores de TI configurar la característica de protección web. Esta funcionalidad está disponible en el Centro Microsoft Endpoint Manager administración.

> [!NOTE]
> Defender for Endpoint en Android usaría una VPN para proporcionar la característica de Protección web. No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.
> Para obtener más información, consulta [Configurar la protección web en dispositivos que ejecutan Android](/mem/intune/protect/advanced-threat-protection-manage-android).

## <a name="privacy-controls"></a>Controles de privacidad

> [!IMPORTANT]
> Controles de privacidad para Microsoft Defender para Endpoint en Android está en versión preliminar. La siguiente información se refiere al producto predefinido que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Los siguientes controles de privacidad están disponibles para configurar los datos enviados por Defender para endpoint desde dispositivos Android:

|Informe de amenazas     |Detalles      |
|--------------------|-------------|
|Informe de malware |Los administradores pueden configurar el control de privacidad para el informe de malware: si la privacidad está habilitada, Defender for Endpoint no enviará el nombre de la aplicación de malware ni otros detalles de la aplicación como parte del informe de alerta de malware |
|Informe de suplantación de identidad |Los administradores pueden configurar el control de privacidad para el informe de phish: si la privacidad está habilitada, Defender for Endpoint no enviará el nombre de dominio ni los detalles del sitio web no seguro como parte del informe de alerta de phish |
|Evaluación de vulnerabilidades de aplicaciones (solo Android) |De forma predeterminada, solo se envía información sobre las aplicaciones instaladas en el perfil de trabajo para la evaluación de vulnerabilidades. Los administradores pueden deshabilitar la privacidad para incluir aplicaciones personales|

## <a name="configure-vulnerability-assessment-of-apps-for-byod-devices"></a>Configurar la evaluación de vulnerabilidades de aplicaciones para dispositivos BYOD

Desde la versión 1.0.3425.0303 de Microsoft Defender para Endpoint en Android, podrás ejecutar evaluaciones de vulnerabilidades del sistema operativo y las aplicaciones instaladas en los dispositivos móviles incorporados.

**Notas sobre privacidad relacionada con aplicaciones de dispositivos personales (BYOD):**

- En el Enterprise Android con un perfil de trabajo, solo se admiten las aplicaciones instaladas en el perfil de trabajo.
- Para otros modos BYOD, de forma predeterminada, no se habilitará la evaluación de vulnerabilidades **de las** aplicaciones. Sin embargo, cuando el dispositivo está en modo de administrador, los administradores pueden habilitar explícitamente esta característica a través de Microsoft Endpoint Manager para obtener la lista de aplicaciones instaladas en el dispositivo. Para obtener más información, vea los detalles a continuación.

### <a name="configure-privacy-for-device-administrator-mode"></a>Configurar la privacidad para el modo de administrador de dispositivos

Usa los siguientes pasos para habilitar **la evaluación de** vulnerabilidades de aplicaciones de dispositivos en modo **de** administrador de dispositivos para usuarios dirigidos. 

> [!NOTE]
> De forma predeterminada, esta opción está desactivada para los dispositivos inscritos en el modo de administración de dispositivos.

1. En [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Perfiles** **devicesConfigurationCrear** >  >  perfil y escriba la siguiente configuración:

   - **Plataforma**: seleccionar administrador de dispositivos Android
   - **Perfil**: seleccione "Personalizado" y haga clic en Crear

2. En la **sección Conceptos** básicos, especifique un nombre y una descripción del perfil.

3. En configuración **,** seleccione Agregar **configuración de OMA-URI** :

   - **Nombre**: escriba un nombre y una descripción únicos para esta configuración de OMA-URI para que pueda encontrarlo fácilmente más adelante.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderTVMPrivacyMode**
   - Tipo de datos: seleccione Entero en la lista desplegable.
   - Valor: escriba 0 para deshabilitar la configuración de privacidad (de forma predeterminada, el valor es 1)

4. Haz **clic en Siguiente** y asigna este perfil a dispositivos o usuarios dirigidos.

### <a name="configure-privacy-for-android-enterprise-work-profile"></a>Configurar la privacidad para Android Enterprise de trabajo

Defender for Endpoint admite la evaluación de vulnerabilidad de las aplicaciones en el perfil de trabajo. Sin embargo, en caso de que desee desactivar esta característica para usuarios dirigidos, puede seguir los siguientes pasos:

1. En [Microsoft Endpoint Manager de administración y](https://go.microsoft.com/fwlink/?linkid=2109431) vaya a Directivas de configuración **de** >  **AppsAppAddManaged** >  >  devices.
2. Asigne un nombre a la directiva; **Plataforma > Android Enterprise**; seleccione el tipo de perfil.
3. Selecciona **Microsoft Defender para Endpoint** como la aplicación de destino.
4. En Configuración, seleccione **Usar** diseñador de configuraciones y agregue **DefenderTVMPrivacyMode** como clave y tipo de valor como **Integer**
   - Para deshabilitar la vulnerabilidad de las aplicaciones en el perfil de trabajo, escriba el valor como `1` y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en `0`.
   - Para los usuarios con el conjunto de claves como `0`, Defender para endpoint enviará la lista de aplicaciones desde el perfil de trabajo al servicio back-end para la evaluación de vulnerabilidades.
5. Haz **clic en Siguiente** y asigna este perfil a dispositivos o usuarios dirigidos.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-privacy-for-phishing-alert-report"></a>Configurar la privacidad para el informe de alertas de suplantación de identidad

El control de privacidad del informe de suplantación de identidad puede usarse para deshabilitar la colección de nombres de dominio o información del sitio web en el informe de amenazas de phishing. Esto ofrece a las organizaciones la flexibilidad de elegir si desean recopilar el nombre de dominio cuando Defender for Endpoint detecta y bloquea un sitio web malintencionado o de suplantación de identidad.

### <a name="configure-privacy-for-phishing-alert-report-on-android-device-administrator-enrolled-devices"></a>Configurar la privacidad para el informe de alertas de suplantación de identidad (phishing) en dispositivos inscritos por el Administrador de dispositivos Android:

Siga estos pasos para activarlo para los usuarios de destino:

1. En [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Perfiles** **devicesConfigurationCrear** >  >  perfil y escriba la siguiente configuración:

   - **Plataforma**: seleccione Administrador de dispositivos Android.
   - **Perfil**: seleccione "Personalizado" y haga clic en **Crear**.

2. En la **sección Conceptos** básicos, especifique un nombre y una descripción del perfil.

3. En configuración **,** seleccione Agregar **configuración de OMA-URI** :

   - **Nombre**: escriba un nombre y una descripción únicos para esta configuración de OMA-URI para que pueda encontrarlo fácilmente más adelante.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeURLInReport**
   - Tipo de datos: seleccione Entero en la lista desplegable.
   - Valor: escriba 1 para habilitar la configuración de privacidad. El valor predeterminado es 0.

4. Haz **clic en Siguiente** y asigna este perfil a dispositivos o usuarios dirigidos.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

### <a name="configure-privacy-for-phishing-alert-report-on-android-enterprise-work-profile"></a>Configurar la privacidad para el informe de alertas de suplantación de identidad (phishing) Enterprise perfil de trabajo de Android

Siga estos pasos para activar la privacidad de los usuarios dirigidos en el perfil de trabajo:

1. En [Microsoft Endpoint Manager de administración y](https://go.microsoft.com/fwlink/?linkid=2109431) vaya a Directivas de configuración **de** >  **AppsAppAddManaged** >  >  devices.
2. Asigne a la directiva un nombre, **Platform > Android Enterprise**, seleccione el tipo de perfil.
3. Selecciona **Microsoft Defender para Endpoint** como la aplicación de destino.
4. En Configuración, seleccione **Usar** diseñador de configuraciones y agregue **DefenderExcludeURLInReport** como clave y tipo de valor **como Integer**.
   - Escriba **1 para habilitar la privacidad**. El valor predeterminado es 0.
5. Haz **clic en Siguiente** y asigna este perfil a dispositivos o usuarios dirigidos.

Activar o desactivar los controles de privacidad anteriores no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional.

## <a name="configure-privacy-for-malware-threat-report"></a>Configurar la privacidad para el informe de amenazas de malware

El control de privacidad del informe de amenazas de malware se puede usar para deshabilitar la colección de detalles de la aplicación (información de nombre y paquete) del informe de amenazas de malware. Esto ofrece a las organizaciones la flexibilidad de elegir si quieren recopilar el nombre de la aplicación cuando se detecta una aplicación malintencionada.

### <a name="configure-privacy-for-malware-alert-report-on-android-device-administrator-enrolled-devices"></a>Configurar la privacidad para el informe de alertas de malware en dispositivos inscritos por el Administrador de dispositivos Android:

Siga estos pasos para activarlo para los usuarios de destino:

1. En [Microsoft Endpoint Manager de administración](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Perfiles** **devicesConfigurationCrear** >  >  perfil y escriba la siguiente configuración:

   - **Plataforma**: seleccione Administrador de dispositivos Android.
   - **Perfil**: seleccione "Personalizado" y haga clic en **Crear**.

2. En la **sección Conceptos** básicos, especifique un nombre y una descripción del perfil.

3. En configuración **,** seleccione Agregar **configuración de OMA-URI** :

   - **Nombre**: escriba un nombre y una descripción únicos para esta configuración de OMA-URI para que pueda encontrarlo fácilmente más adelante.
   - OMA-URI: **./Vendor/MSFT/DefenderATP/DefenderExcludeAppInReport**
   - Tipo de datos: seleccione Entero en la lista desplegable.
   - Valor: escriba 1 para habilitar la configuración de privacidad. El valor predeterminado es 0.

4. Haz **clic en Siguiente** y asigna este perfil a dispositivos o usuarios dirigidos.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional. Por ejemplo, los dispositivos con una aplicación malintencionada siempre tendrán un nivel de riesgo de "Medium".

### <a name="configure-privacy-for-malware-alert-report-on-android-enterprise-work-profile"></a>Configurar la privacidad para el informe de alertas de malware en el Enterprise de trabajo de Android

Siga estos pasos para activar la privacidad de los usuarios dirigidos en el perfil de trabajo:

1. En [Microsoft Endpoint Manager de administración y](https://go.microsoft.com/fwlink/?linkid=2109431) vaya a Directivas de configuración **de** >  **AppsAppAddManaged** >  >  devices.
2. Asigne a la directiva un nombre, **Platform > Android Enterprise**, seleccione el tipo de perfil.
3. Selecciona **Microsoft Defender para Endpoint** como la aplicación de destino.
4. En Configuración, seleccione **Usar** diseñador de configuraciones y agregue **DefenderExcludeAppInReport** como clave y tipo de valor como **Integer**
   - Escriba **1 para habilitar la privacidad**. El valor predeterminado es 0.
5. Haz **clic en Siguiente** y asigna este perfil a dispositivos o usuarios dirigidos.

El uso de este control de privacidad no afectará a la comprobación de cumplimiento del dispositivo ni al acceso condicional. Por ejemplo, los dispositivos con una aplicación malintencionada siempre tendrán un nivel de riesgo de "Medium".

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
