---
title: Pila paso a paso de protección contra amenazas en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
description: Siga la ruta de acceso de un mensaje entrante a través de la pila de filtrado de amenazas en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 96e7fb9a4e774b51b1d2138cd72ea468bc23ee7b
ms.sourcegitcommit: e6595be36bbaba244439bd59dbae935e2b258ded
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2022
ms.locfileid: "67450155"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Protección contra amenazas paso a paso en Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La pila de protección o filtrado de Microsoft Defender para Office 365 se puede dividir en 4 fases, como en este artículo. En términos generales, el correo entrante pasa por todas estas fases antes de la entrega, pero la ruta de acceso real que toma el correo electrónico está sujeta a la configuración Defender para Office 365 de una organización.

> [!TIP]
> Manténgase atento hasta el final de este artículo para obtener un gráfico *unificado* de las 4 fases de Defender para Office 365 protección!

## <a name="phase-1---edge-protection"></a>Fase 1: Protección perimetral

Desafortunadamente, los bloques perimetrales que antes eran *críticos* ahora son relativamente sencillos de superar para los actores incorrectos. Con el tiempo, se bloquea menos tráfico aquí, pero sigue siendo una parte importante de la pila.  

Los bloques perimetrales están diseñados para ser automáticos. En el caso de falsos positivos, se notificará a los remitentes y se les informará de cómo solucionar su problema. Los conectores de asociados de confianza con una reputación limitada pueden garantizar la entrega o se pueden implementar invalidaciones temporales al incorporar nuevos puntos de conexión.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Filtrado de fase 1 en Defender para Office 365" lightbox="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png":::

1. **La limitación de red** protege Office 365 infraestructura y clientes frente a ataques de denegación de servicio (DOS) limitando el número de mensajes que puede enviar un conjunto específico de infraestructura.

2. **La reputación y limitación de IP** bloquearán los mensajes que se envían desde direcciones IP de conexión incorrecta conocidas. Si una dirección IP específica envía muchos mensajes en un breve período de tiempo, se limitarán.

3. **La reputación del dominio** bloqueará los mensajes que se envían desde un dominio incorrecto conocido.

4. **Filtro perimetral basado en directorios** bloquea los intentos de recopilar información de directorio de una organización a través de SMTP.

5. **Detección de devolución de correo no enviado** impide que una organización sea atacada a través de informes de no entrega (NDR) no válidos.

6. **El filtrado mejorado de conectores** conserva la información de autenticación incluso cuando el tráfico pasa a través de otro dispositivo antes de que llegue a Office 365. Esto mejora la precisión de la pila de filtrado, incluidos los modelos de agrupación en clústeres heurísticas, contra la suplantación de identidad y el aprendizaje automático anti phishing, incluso en escenarios de enrutamiento complejos o híbridos.

## <a name="phase-2---sender-intelligence"></a>Fase 2: Inteligencia del remitente

Las características de la inteligencia del remitente son fundamentales para detectar mensajes de correo no deseado, masivos, suplantación y suplantación no autorizados, además de tener en cuenta la detección de phish. La mayoría de estas características se pueden configurar individualmente.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="La fase 2 del filtrado en Defender para Office 365 es la inteligencia del remitente" lightbox="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png":::

1. Los desencadenadores y alertas **de detección de riesgos** de cuenta se generan cuando una cuenta tiene un comportamiento anómalo, coherente con el riesgo. En algunos casos, la cuenta de usuario se bloquea y no se puede enviar más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de una organización resuelva el problema.

2. **Email La autenticación** implica tanto métodos configurados por el cliente como métodos configurados en la nube, con el objetivo de garantizar que los remitentes estén autorizados y sean auténticos. Estos métodos resisten la suplantación de identidad.
    - **SPF** puede rechazar los correos basados en registros TXT de DNS que enumeran las direcciones IP y los servidores que pueden enviar correo en nombre de la organización.
    - **DKIM** proporciona una firma cifrada que autentica al remitente.
    - **DMARC** permite a los administradores marcar SPF y DKIM según sea necesario en su dominio y exige la alineación entre los resultados de estas dos tecnologías.
    - **ARC** se basa en DMARC para trabajar con el reenvío en listas de correo mientras se registra una cadena de autenticación.

3. **La inteligencia de suplantación** de identidad es capaz de filtrar aquellos a los que se les permite "suplantar" (es decir, aquellos que envían correo en nombre de otra cuenta o reenvía para una lista de correo) desde remitentes malintencionados que imitan dominios externos conocidos o de la organización. Separa el correo legítimo "en nombre de" de los remitentes que suplantan para entregar mensajes de spam y phishing.

    **Inteligencia contra la suplantación de identidad dentro de la organización** detecta y bloquea los intentos de suplantación de identidad de un dominio dentro de la organización.

4. **Inteligencia contra la suplantación de identidad entre dominios** detecta y bloquea los intentos de suplantación de identidad de un dominio fuera de la organización.

5. **El filtrado masivo** permite a los administradores configurar un nivel de confianza masivo (BCL) que indica si el mensaje se envió desde un remitente masivo. Los administradores pueden usar el control deslizante masivo en la directiva antispam para decidir qué nivel de correo masivo tratar como correo no deseado.

6. **Inteligencia de buzones** aprende de los comportamientos estándar del correo electrónico del usuario. Aprovecha el gráfico de comunicación de un usuario para detectar cuándo un remitente solo parece ser alguien con el que el usuario suele comunicarse, pero en realidad es malintencionado. Este método detecta la suplantación.

7. **La suplantación de inteligencia de buzones** habilita o deshabilita los resultados de suplantación mejorados en función del mapa de remitente individual de cada usuario. Cuando está habilitada, esta característica ayuda a identificar la suplantación.

8. **La suplantación de usuario** permite a un administrador crear una lista de destinos de alto valor que probablemente se suplantarán. Si llega un correo donde el remitente solo parece tener el mismo nombre y dirección que la cuenta de alto valor protegida, el correo se marca o etiqueta. (Por ejemplo, *trα cye@contoso.com* para *tracye@contoso.com*).

9. **La suplantación de dominio** detecta dominios que son similares al dominio del destinatario y que intentan parecerse a un dominio interno. Por ejemplo, esta suplantación *tracye@liw α re.com* para *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Fase 3: Filtrado de contenido

En esta fase, la pila de filtrado comienza a controlar el contenido específico del correo, incluidos sus hipervínculos y datos adjuntos.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="El filtrado de fase 3 en MDO es filtrado de contenido" lightbox="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png":::

1. **Las reglas de transporte** (también conocidas como reglas de flujo de correo o reglas de transporte de Exchange) permiten a un administrador realizar una amplia gama de acciones cuando se cumple una gama igualmente amplia de condiciones para un mensaje. Todos los mensajes que fluyen a través de la organización se evalúan en función de las reglas de flujo de correo o las reglas de transporte habilitadas.

2. **Antivirus de Microsoft Defender** y dos *motores antivirus de terceros* se usan para detectar todo el malware conocido en los datos adjuntos.

3. Los motores antivirus (AV) también se usan para aplicar el tipo verdadero a todos los datos adjuntos, de modo que el **bloqueo de tipos** pueda bloquear todos los datos adjuntos de los tipos que especifica el administrador.

4. Cada vez que Microsoft Defender para Office 365 detecta datos adjuntos malintencionados, el hash del archivo y un hash de su contenido activo se agregan a Exchange Online Protection reputación (EOP). **El bloqueo de la reputación de los datos adjuntos** bloqueará ese archivo en todos los Office 365, y en los puntos de conexión, a través de llamadas en la nube de MSAV.

5. **Agrupación heurística** puede determinar que un archivo es sospechoso en función de la heurística de entrega. Cuando se encuentra un archivo adjunto sospechoso, toda la campaña se pausa y el archivo está en espacio aislado. Si se detecta que el archivo es malintencionado, se bloquea toda la campaña.

6. **Modelo de aprendizaje automático** actúa sobre el encabezado, el contenido del cuerpo y las direcciones URL de un mensaje para detectar intentos de suplantación de identidad.

7. Microsoft usa una determinación de la reputación del espacio aislado de direcciones URL, así como la reputación de direcciones URL de fuentes de terceros en **el bloqueo de reputación de direcciones URL**, para bloquear cualquier mensaje con una dirección URL malintencionada conocida.

8. **Los heurísticos de contenido** pueden detectar mensajes sospechosos en función de la estructura y la frecuencia de palabras dentro del cuerpo del mensaje, mediante modelos de aprendizaje automático.

9. **Los espacios aislados de datos adjuntos seguros** de cada dato adjunto para Defender para Office 365 clientes, mediante el análisis dinámico para detectar amenazas nunca antes vistas.

10. **Detonación de contenido vinculado** trata todas las direcciones URL que se vinculan a un archivo de un correo electrónico como datos adjuntos, creando de forma asincrónica un espacio aislado en el archivo en el momento de la entrega.

11. **Detonación URL** se produce cuando la tecnología antiphishing ascendente detecta que un mensaje o una dirección URL son sospechosos. La detonación de direcciones URL espacio aislado las direcciones URL del mensaje en el momento de la entrega.

## <a name="phase-4---post-delivery-protection"></a>Fase 4: Protección posterior a la entrega

La última fase tiene lugar después de la entrega de correo o archivo, actuando en el correo que se encuentra en varios buzones y archivos y vínculos que aparecen en clientes como Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="El filtrado de fase 4 en Defender para Office 365 es protección posterior a la entrega" lightbox="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png":::

1. **Vínculos seguros** es la protección de tiempo de clic de Defender para Office 365. Cada dirección URL de cada mensaje se ajusta para que apunte a los servidores de Vínculos seguros de Microsoft. Cuando se hace clic en una dirección URL, se comprueba la reputación más reciente, antes de que se redirija al usuario al sitio de destino. La dirección URL está en espacio aislado asincrónicamente para actualizar su reputación.

2. **La purga automática de cero horas (ZAP) para phishing** detecta y neutraliza de forma retroactiva los mensajes de phishing malintencionados que ya se han entregado a Exchange Online buzones.

3. **ZAP para malware** detecta y neutraliza de forma retroactiva los mensajes malintencionados malware que ya se han entregado a buzones de Exchange Online.

4. **ZAP para correo no deseado** detecta y neutraliza de forma retroactiva los mensajes malintencionados correo no deseado que ya se han entregado a los buzones de Exchange Online.

5. **Las vistas de campaña** permiten a los administradores ver el panorama general de un ataque, más rápido y completamente, de lo que cualquier equipo podría sin automatización. Microsoft aprovecha las grandes cantidades de datos anti-phishing, antispam y antimalware en todo el servicio para ayudar a identificar las campañas y, a continuación, permite a los administradores investigarlas de principio a fin, incluidos los destinos, los impactos y los flujos, que también están disponibles en una escritura de campaña descargable.

6. **Los complementos de mensaje** de informe permiten a los usuarios notificar fácilmente falsos positivos (buen correo electrónico, marcados erróneamente como *incorrectos*) o falsos negativos (correo electrónico incorrecto marcado como *bueno*) a Microsoft para su posterior análisis.

7. **Vínculos seguros para clientes de Office** ofrece la misma protección de tiempo de clic de Vínculos seguros, de forma nativa, dentro de aplicaciones de Office compatibles como Word, PowerPoint y Excel.

8. **La protección para OneDrive, SharePoint y Teams** ofrece la misma protección de datos adjuntos seguros contra archivos malintencionados, de forma nativa, dentro de OneDrive, SharePoint y Microsoft Teams.

9. Cuando se selecciona una dirección URL que apunta a un archivo después de la entrega, la **detonación de contenido vinculado** muestra una página de advertencia hasta que se completa el espacio aislado del archivo y se detecta que la dirección URL es segura.

## <a name="the-filtering-stack-diagram"></a>Diagrama de pila de filtrado

El diagrama final (como sucede con todas las partes del diagrama que lo componen) *está sujeto a cambios a medida que el producto crece y se desarrolla*. Marque esta página y use la opción **de comentarios** que encontrará en la parte inferior si necesita preguntar después de las actualizaciones. Para los registros, esta es la pila con todas las fases en orden:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Todas las fases de filtrado en Defender para Office 365 en orden, de 1 a 4" lightbox="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png":::

## <a name="more-information"></a>Más información

¿Necesita configurar Microsoft Defender para Office 365 ***en este momento** _? Use esta pila, _now*, con [este paso a paso](protect-against-threats.md) para empezar a proteger su organización.

*Gracias especiales de MSFTTracyP y el equipo de redacción de documentos a Giulian Garruba por este contenido*.
