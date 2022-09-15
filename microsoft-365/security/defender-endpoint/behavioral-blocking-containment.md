---
title: Bloqueo y contención de comportamientos
description: Obtenga información sobre las funcionalidades de bloqueo y contención del comportamiento en Microsoft Defender para punto de conexión
keywords: Microsoft Defender para punto de conexión, EDR en modo de bloque, bloqueo de modo pasivo
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
- admindeeplinkDEFENDER
ms.collection: m365-security-compliance
ms.technology: mde
search.appverid: met150
ms.openlocfilehash: 203eaf79058908ff9814cdc0628d1fbe8214b9b0
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698251"
---
# <a name="behavioral-blocking-and-containment"></a>Bloqueo y contención de comportamientos

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Información general

El panorama de amenazas de hoy en día está saturado por [malware sin archivos](/windows/security/threat-protection/intelligence/fileless-threats) y que vive fuera de la tierra, amenazas altamente polimórficas que mutan más rápido de lo que las soluciones tradicionales pueden mantenerse al día, y ataques operados por humanos que se adaptan a lo que los adversarios encuentran en dispositivos en peligro. Las soluciones de seguridad tradicionales no son suficientes para detener estos ataques; necesita funcionalidades respaldadas por inteligencia artificial (IA) y aprendizaje de dispositivos (ML), como el bloqueo y la contención del comportamiento, incluidos en [Defender para punto de conexión](/windows/security).

Las funcionalidades de bloqueo y contención del comportamiento pueden ayudar a identificar y detener amenazas, en función de sus comportamientos y de los árboles de proceso, incluso cuando la amenaza ha comenzado a ejecutarse. Las características y los componentes y características de protección de última generación, EDR y Defender para punto de conexión funcionan conjuntamente en capacidades de bloqueo y contención del comportamiento.

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Bloqueo y contención del comportamiento en el portal de ATP de Microsoft Defender" lightbox="images/mdatp-next-gen-EDR-behavblockcontain.png":::

Las funcionalidades de bloqueo y contención del comportamiento funcionan con varios componentes y características de Defender for Endpoint para detener ataques inmediatamente e impedir que los ataques avancen.

- [La protección de última generación](microsoft-defender-antivirus-in-windows-10.md) (que incluye el Antivirus de Microsoft Defender) puede detectar amenazas mediante el análisis de comportamientos y detener las amenazas que han comenzado a ejecutarse.

- [La detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) (EDR) recibe señales de seguridad en toda la red, los dispositivos y el comportamiento del kernel. A medida que se detectan amenazas, se crean alertas. Varias alertas del mismo tipo se agregan a incidentes, lo que facilita que el equipo de operaciones de seguridad investigue y responda.

- [Defender para punto de conexión](overview-endpoint-detection-response.md) tiene una amplia gama de ópticas entre identidades, correo electrónico, datos y aplicaciones, además de las señales de comportamiento de red, punto de conexión y kernel recibidas a través de EDR. Un componente de [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender para punto de conexión procesa y correlaciona estas señales, genera alertas de detección y conecta alertas relacionadas en incidentes.

Con estas funcionalidades, se pueden evitar o bloquear más amenazas, incluso si empiezan a ejecutarse. Cada vez que se detecta un comportamiento sospechoso, la amenaza está contenida, se crean alertas y las amenazas se detienen en sus seguimientos.

En la imagen siguiente se muestra un ejemplo de una alerta que se desencadenó mediante funcionalidades de bloqueo y contención de comportamiento:

:::image type="content" source="images/blocked-behav-alert.png" alt-text="La página Alertas con una alerta a través del bloqueo y la contención del comportamiento" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Componentes del bloqueo y la contención del comportamiento

- **Reglas de [reducción de la superficie expuesta a ataques](attack-surface-reduction.md) basada en directivas en el cliente** Se impide que se ejecuten comportamientos de ataque comunes predefinidos, según las reglas de reducción de la superficie expuesta a ataques. Cuando estos comportamientos intentan ejecutarse, se pueden ver en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> como alertas informativas. Las reglas de reducción de superficie expuesta a ataques no están habilitadas de forma predeterminada; configure las directivas en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender).

- **[Bloqueo del comportamiento del cliente](client-behavioral-blocking.md)** Las amenazas en los puntos de conexión se detectan a través del aprendizaje automático y, a continuación, se bloquean y corrigen automáticamente. (El bloqueo de comportamiento del cliente está habilitado de forma predeterminada).

- **[Bloqueo de bucles de comentarios](feedback-loop-blocking.md)** (también conocido como protección rápida) Las detecciones de amenazas se observan a través de la inteligencia de comportamiento. Las amenazas se detienen y se impide que se ejecuten en otros puntos de conexión. (El bloqueo de bucles de comentarios está habilitado de forma predeterminada).

- **[Detección y respuesta de puntos de conexión (EDR) en modo de bloque](edr-in-block-mode.md)** Los artefactos malintencionados o los comportamientos que se observan a través de la protección posterior a la infracción se bloquean y contienen. EDR en modo de bloque funciona incluso si Antivirus de Microsoft Defender no es la solución antivirus principal. (EDR en modo de bloque no está habilitado de forma predeterminada; se activa en Microsoft 365 Defender).

Espere más en el área de bloqueo y contención del comportamiento, ya que Microsoft sigue mejorando las características y funcionalidades de protección contra amenazas. Para ver lo que está planeado e implementar ahora, visite la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Ejemplos de bloqueo y contención del comportamiento en acción

Las funcionalidades de bloqueo y contención del comportamiento han bloqueado técnicas de atacante como las siguientes:

- Volcado de credenciales de LSASS
- Inyección entre procesos
- Vaciado de procesos
- Omisión del control de cuentas de usuario
- Manipulación del antivirus (por ejemplo, deshabilitarlo o agregar el malware como exclusión)
- Ponerse en contacto con command and control (C&C) para descargar cargas útiles
- Minería de monedas
- Modificación del registro de arranque
- Ataques de pass-the-hash
- Instalación del certificado raíz
- Intento de explotación de varias vulnerabilidades

A continuación se muestran dos ejemplos reales de bloqueo y contención del comportamiento en acción.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Ejemplo 1: Ataque de robo de credenciales contra 100 organizaciones

Como se describe en [Búsqueda activa de amenazas elusivas: el bloqueo basado en el comportamiento controlado por IA detiene los ataques en sus pistas](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), un ataque de robo de credenciales contra 100 organizaciones de todo el mundo se detuvo mediante funcionalidades de bloqueo y contención del comportamiento. Los mensajes de correo electrónico de phishing de spear que contenían un documento de señuelo se enviaron a las organizaciones de destino. Si un destinatario abrió los datos adjuntos, un documento remoto relacionado pudo ejecutar código en el dispositivo del usuario y cargar el malware Lokibot, que robaba credenciales, filtraba datos robados y esperaba instrucciones adicionales de un servidor de comandos y control.

Los modelos de aprendizaje de dispositivos basados en el comportamiento en Defender para punto de conexión detectaron y detuvieron las técnicas del atacante en dos puntos de la cadena de ataques:

- La primera capa de protección detectó el comportamiento de vulnerabilidad de seguridad. Los clasificadores de aprendizaje de dispositivo en la nube identificaron correctamente la amenaza como e indicaron inmediatamente al dispositivo cliente que bloqueara el ataque.
- La segunda capa de protección, que ayudó a detener los casos en los que el ataque superó la primera capa, detectó el vaciado de procesos, detuvo ese proceso y quitó los archivos correspondientes (como Lokibot).

Mientras se detectó y detuvo el ataque, se desencadenaron alertas, como una "alerta de acceso inicial", y aparecieron en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender).

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Alerta de acceso inicial en el portal de Microsoft 365 Defender" lightbox="images/behavblockcontain-initialaccessalert.png":::

En este ejemplo se muestra cómo los modelos de aprendizaje de dispositivos basados en el comportamiento en la nube agregan nuevas capas de protección contra ataques, incluso después de que hayan empezado a ejecutarse.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Ejemplo 2: Retransmisión NTLM: variante de malware de patata jugosa

Como se describe en la entrada de blog reciente, [Bloqueo de comportamiento y contención: Transformar la óptica en protección](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection), en enero de 2020, Defender for Endpoint detectó una actividad de escalado de privilegios en un dispositivo de una organización. Se desencadenó una alerta denominada "Posible escalación de privilegios mediante la retransmisión NTLM".

:::image type="content" source="images/NTLMalertjuicypotato.png" alt-text="Una alerta NTLM para malware de Patata jugosa" lightbox="images/NTLMalertjuicypotato.png":::

La amenaza resultó ser malware; era una variante nueva, no vista antes de una herramienta de piratería notoria llamada Juicy Potato, que es utilizada por los atacantes para obtener la escalación de privilegios en un dispositivo.

Minutos después de desencadenar la alerta, se analizó el archivo y se confirmó que era malintencionado. Su proceso se detuvo y bloqueó, como se muestra en la siguiente imagen:

:::image type="content" source="images/Artifactblockedjuicypotato.png" alt-text="Artefacto bloqueado"  lightbox="images/Artifactblockedjuicypotato.png":::

Unos minutos después de bloquear el artefacto, se bloquearon varias instancias del mismo archivo en el mismo dispositivo, lo que impidió que más atacantes u otro malware se implementaran en el dispositivo.

En este ejemplo se muestra que, con las funcionalidades de bloqueo y contención de comportamiento, las amenazas se detectan, contienen y bloquean automáticamente.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="next-steps"></a>Pasos siguientes

- [Más información sobre Defender para punto de conexión](overview-endpoint-detection-response.md)

- [Configuración de las reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md)

- [Habilitación de EDR en modo de bloque](edr-in-block-mode.md)

- [Consulte la actividad de amenazas global reciente.](https://www.microsoft.com/wdsi/threats)

- [Obtenga información general sobre Microsoft 365 Defender](../defender/microsoft-365-defender.md)
