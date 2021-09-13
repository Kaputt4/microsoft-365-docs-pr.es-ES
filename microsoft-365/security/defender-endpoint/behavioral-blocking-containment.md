---
title: Bloqueo y contención de comportamientos
description: Obtenga información sobre las capacidades de contención y bloqueo de comportamiento en Microsoft Defender para endpoint
keywords: Microsoft Defender para endpoint, EDR en modo de bloqueo, bloqueo de modo pasivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 7d9dad6b2f2f1b37525faf0a4a90d143650c49d1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212370"
---
# <a name="behavioral-blocking-and-containment"></a>Bloqueo y contención de comportamientos

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Información general

El panorama de amenazas actual está saturado por [malware](/windows/security/threat-protection/intelligence/fileless-threats) sin archivos y que vive fuera de la tierra, amenazas altamente polimórficas que mutan más rápido que las soluciones tradicionales pueden mantenerse al día y ataques operados por humanos que se adaptan a lo que los adversarios encuentran en dispositivos en peligro. Las soluciones de seguridad tradicionales no son suficientes para detener estos ataques; necesitas inteligencia artificial (IA) y capacidades de aprendizaje de dispositivos (ML), como el bloqueo y la contención del comportamiento, incluidos [en Defender for Endpoint](/windows/security).

Las capacidades de bloqueo y contención del comportamiento pueden ayudar a identificar y detener las amenazas, en función de sus comportamientos y de los árboles de proceso incluso cuando la amenaza ha comenzado a ejecutarse. Las características y los componentes de protección de última generación, EDR y Defender para endpoint funcionan juntos en las capacidades de contención y bloqueo de comportamiento.

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="Bloqueo y contención de comportamiento.":::

Las capacidades de bloqueo de comportamiento y contención funcionan con varios componentes y características de Defender para endpoint para detener los ataques inmediatamente e impedir que los ataques progresen.

- [La protección de última](microsoft-defender-antivirus-in-windows-10.md) generación (que incluye Antivirus de Microsoft Defender) puede detectar amenazas mediante el análisis de comportamientos y detener las amenazas que se han empezado a ejecutar.

- [La detección y respuesta de](overview-endpoint-detection-response.md) puntos de conexión (EDR) recibe señales de seguridad en toda la red, dispositivos y comportamiento del kernel. A medida que se detectan las amenazas, se crean alertas. Varias alertas del mismo tipo se agregan a incidentes, lo que facilita al equipo de operaciones de seguridad investigar y responder.

- [Defender for Endpoint](overview-endpoint-detection-response.md) tiene una amplia gama de ópticas entre identidades, correo electrónico, datos y aplicaciones, además de las señales de comportamiento de red, punto de conexión y kernel recibidas a través de EDR. Un componente de [Microsoft 365 Defender](../defender/microsoft-365-defender.md), Defender for Endpoint procesa y correlaciona estas señales, genera alertas de detección y conecta alertas relacionadas en incidentes.

Con estas capacidades, se pueden evitar o bloquear más amenazas, incluso si comienzan a ejecutarse. Cada vez que se detecta un comportamiento sospechoso, se contiene la amenaza, se crean alertas y se detienen las amenazas en sus seguimientos.

En la siguiente imagen se muestra un ejemplo de una alerta que se desencadenó mediante funciones de bloqueo de comportamiento y contención:

:::image type="content" alt-text="Ejemplo de alerta a través del bloqueo y la contención del comportamiento." source="images/blocked-behav-alert.png" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>Componentes del bloqueo y la contención del comportamiento

- Reglas de reducción de superficie de **[ataques](attack-surface-reduction.md)** controladas por directivas en el cliente Los comportamientos de ataque comunes predefinidos no se pueden ejecutar, de acuerdo con las reglas de reducción de superficie de ataque. Cuando estos comportamientos intentan ejecutarse, se pueden ver en el portal de Microsoft 365 Defender( ) como [https://security.microsoft.com](https://security.microsoft.com) alertas informativos. Las reglas de reducción de superficie de ataque no están habilitadas de forma predeterminada; configure las directivas en el [portal de Microsoft 365 Defender](microsoft-defender-security-center.md).

- **[Bloqueo de comportamiento del cliente](client-behavioral-blocking.md)** Las amenazas en los puntos de conexión se detectan a través del aprendizaje automático y, a continuación, se bloquean y corrigen automáticamente. (El bloqueo de comportamiento del cliente está habilitado de forma predeterminada).

- **[Bloqueo de bucle de comentarios](feedback-loop-blocking.md)** (también denominado protección rápida) Las detecciones de amenazas se observan a través de la inteligencia de comportamiento. Las amenazas se detienen e impiden que se ejecuten en otros puntos de conexión. (El bloqueo de bucle de comentarios está habilitado de forma predeterminada).

- **[Detección y respuesta de puntos de conexión (EDR) en modo de bloqueo](edr-in-block-mode.md)** Los artefactos o comportamientos malintencionados que se observan a través de la protección posterior a la infracción se bloquean y contienen. EDR en modo de bloqueo funciona incluso si Antivirus de Microsoft Defender no es la solución antivirus principal. (EDR en modo de bloque no está habilitado de forma predeterminada; se activa en Microsoft 365 Defender).

Espere más en el área del bloqueo y la contención del comportamiento, ya que Microsoft sigue mejorando las características y capacidades de protección contra amenazas. Para ver lo que se planea y se está implementando ahora, visite el mapa [Microsoft 365 ruta de trabajo](https://www.microsoft.com/microsoft-365/roadmap).

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>Ejemplos de bloqueo de comportamiento y contención en la acción

Las capacidades de contención y bloqueo de comportamiento han bloqueado técnicas de atacante, como las siguientes:

- Volcado de credenciales desde LSASS
- Inyección entre procesos
- Acobado de procesos
- Omisión del control de cuentas de usuario
- Manipulación de antivirus (como deshabilitarlo o agregar el malware como exclusión)
- Ponerse en contacto con el comando y el control (C&C) para descargar cargas
- Minería de monedas
- Modificación del registro de arranque
- Ataques pass-the-hash
- Instalación del certificado raíz
- Intento de explotación para varias vulnerabilidades

A continuación se muestran dos ejemplos reales de bloqueo y contención del comportamiento en acción.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>Ejemplo 1: Ataque de robo de credenciales contra 100 organizaciones

Como se describe en In [hot pursuit of elusive threats: AI-driven behavior-based blocking stops attacks in their tracks](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks), a credential theft attack against 100 organizations around the world was stopped by behavioral blocking and containment capabilities. Los mensajes de correo electrónico de suplantación de identidad (phishing) que contenían un documento de señuelo se enviaron a las organizaciones de destino. Si un destinatario abrió los datos adjuntos, un documento remoto relacionado pudo ejecutar código en el dispositivo del usuario y cargar malware Lokibot, que robaba credenciales, exfiltró datos robados y esperaba instrucciones adicionales de un servidor de comandos y control.

Los modelos de aprendizaje de dispositivos basados en comportamiento en Defender for Endpoint capturaron y detuvieron las técnicas del atacante en dos puntos de la cadena de ataques:

- La primera capa de protección detectó el comportamiento de vulnerabilidad. Los clasificadores de aprendizaje de dispositivos en la nube identificaron correctamente la amenaza e indicaron inmediatamente al dispositivo cliente que bloqueara el ataque.
- La segunda capa de protección, que ayudó a detener los casos en los que el ataque se atravó más allá de la primera capa, detectó el vacío del proceso, detuvo ese proceso y quitó los archivos correspondientes (como Lokibot).

Mientras se detectó y detuvo el ataque, las alertas, como una "alerta de acceso inicial", se desencadenaron y aparecieron en [el portal Microsoft 365 Defender .](microsoft-defender-security-center.md)

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="Alerta de acceso inicial en el Microsoft 365 Defender portal.":::

En este ejemplo se muestra cómo los modelos de aprendizaje de dispositivos basados en comportamientos en la nube agregan nuevas capas de protección contra ataques, incluso después de que se han empezado a ejecutar.

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>Ejemplo 2: retransmisión NTLM: variante de malware de la camote jugosa

Tal como se describe en la entrada de blog reciente, Bloqueo y contención del comportamiento: Transformar la óptica en protección , en enero de 2020, Defender for Endpoint detectó una actividad de escalamiento de [privilegios](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)en un dispositivo de una organización. Se desencadenó una alerta denominada "Posible escalada de privilegios mediante retransmisión NTLM".

:::image type="content" alt-text="Alerta NTLM para malware Despúes juicy." source="images/NTLMalertjuicypotato.png" lightbox="images/NTLMalertjuicypotato.png":::

La amenaza resultó ser malware; era una nueva variante no vista antes de una herramienta de piratería notoria llamada Juicy Potato, que los atacantes usan para obtener la escalación de privilegios en un dispositivo.

Minutos después de que se desencadenó la alerta, se analizó el archivo y se confirmó que era malintencionado. Su proceso se detuvo y bloqueó, como se muestra en la siguiente imagen:

:::image type="content" alt-text="Artefacto bloqueado." source="images/Artifactblockedjuicypotato.png" lightbox="images/Artifactblockedjuicypotato.png":::

Unos minutos después de bloquear el artefacto, se bloquearon varias instancias del mismo archivo en el mismo dispositivo, lo que impidió que se implementara más atacantes u otro malware en el dispositivo.

En este ejemplo se muestra que, con las capacidades de contención y bloqueo de comportamiento, las amenazas se detectan, contienen y bloquean automáticamente.

## <a name="next-steps"></a>Siguientes pasos

- [Más información sobre Defender for Endpoint](overview-endpoint-detection-response.md)

- [Configurar las reglas de reducción de superficie de ataque](attack-surface-reduction.md)

- [Habilitar EDR en modo de bloque](edr-in-block-mode.md)

- [Ver la actividad de amenazas globales reciente](https://www.microsoft.com/wdsi/threats)

- [Obtenga información general sobre Microsoft 365 Defender](../defender/microsoft-365-defender.md)
