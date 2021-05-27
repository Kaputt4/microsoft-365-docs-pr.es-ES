---
title: Pila de protección contra amenazas paso a paso en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Siga la ruta de un mensaje entrante a través de la pila de filtrado de amenazas en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e892ebe04887527cf57e4ea44f67c4aaa775b228
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683300"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Protección contra amenazas paso a paso en Microsoft Defender para Office 365

La pila de protección Office 365 o filtrado de Microsoft Defender se puede dividir en 4 fases, como en este artículo. En general, el correo entrante pasa a través de todas estas fases antes de la entrega, pero la ruta de acceso real que toma el correo electrónico está sujeta a defender de una organización para Office 365 configuración.

> [!TIP]
> Permanece atento hasta el final de este artículo para obtener un *gráfico* unificado de las 4 fases de Defender para Office 365 protección.

## <a name="phase-1---edge-protection"></a>Fase 1: protección perimetral

Desafortunadamente, los bloques perimetrales que antes eran *críticos* ahora son relativamente sencillos para que los actores con problemas superen. Con el tiempo, se bloquea menos tráfico aquí, pero sigue siendo una parte importante de la pila.  

Los bloques perimetrales están diseñados para ser automáticos. En el caso de falso positivo, se notificará a los remitentes y se les indica cómo solucionar su problema. Los conectores de socios de confianza con reputación limitada pueden garantizar la entrega, o se pueden establecer invalidaciones temporales, al incorporar nuevos puntos de conexión.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="La fase 1 del filtrado en Defender para Office 365 es protección perimetral.":::

1. **La limitación de** red protege Office 365 infraestructura y clientes de ataques por denegación de servicio (DOS) limitando el número de mensajes que puede enviar un conjunto específico de infraestructura.

2. **La reputación y la limitación** de IP bloquearán los mensajes que se envían desde direcciones IP de conexión no válidas conocidas. Si una DIRECCIÓN IP específica envía muchos mensajes en un breve período de tiempo, se limitarán.

3. **La reputación** del dominio bloqueará los mensajes que se envíen desde un dominio no conocido.

4. **El filtrado perimetral basado en directorios** bloquea los intentos de obtener información de directorio de una organización a través de SMTP.

5. **La detección de backscatter** impide que una organización sea atacada a través de informes de no entrega (NDR) no válidos.

6. **El filtrado mejorado para conectores** conserva la información de autenticación incluso cuando el tráfico pasa a través de otro dispositivo antes de que llegue a Office 365. Esto mejora la precisión de la pila de filtrado, incluida la agrupación en clústeres heurísticos, la suplantación de identidad y los modelos de aprendizaje automático contra suplantación de identidad (phishing), incluso en escenarios de enrutamiento complejos o híbridos.

## <a name="phase-2---sender-intelligence"></a>Fase 2: Inteligencia del remitente

Las características de la inteligencia del remitente son fundamentales para capturar mensajes de correo no deseado, masivos, suplantación y suplantación no autorizados, y también tienen en cuenta la detección de phish. La mayoría de estas características se pueden configurar individualmente.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="La fase 2 del filtrado en MDO es la inteligencia del remitente.":::

1. **Los desencadenadores y** alertas de detección de riesgo de cuentas se desencadenan cuando una cuenta tiene un comportamiento anómalo, coherente con el riesgo. En algunos casos, la cuenta de usuario se bloquea e impide enviar más mensajes de correo electrónico hasta que el equipo de operaciones de seguridad de una organización resuelva el problema.

2. **La autenticación** de correo electrónico implica métodos y métodos configurados por el cliente configurados en la nube, destinados a garantizar que los remitentes sean remitentes autorizados y auténticos. Estos métodos resisten la suplantación.
    - **SPF** puede rechazar correos basados en registros TXT DNS que enumen direcciones IP y servidores permitidos para enviar correo en nombre de la organización.
    - **DKIM** proporciona una firma cifrada que autentica al remitente.
    - **DMARC** permite a los administradores marcar SPF y DKIM según sea necesario en su dominio y aplica la alineación entre los resultados de estas dos tecnologías.
    - **ARC** no está configurado por el cliente, pero se basa en DMARC para trabajar con el reenvío en listas de correo, mientras se registra una cadena de autenticación.

3.  La inteligencia suplantación de identidad es capaz de filtrar aquellos permitidos para 'suplantar' (es decir, aquellos que envían correo en nombre de otra cuenta o reenviar para una lista de correo) de remitentes malintencionados que imitan dominios externos conocidos o organizativos. Separa el correo legítimo "en nombre de" de los remitentes que suplanta para entregar mensajes de correo no deseado y suplantación de identidad.

    **La inteligencia de suplantación intra** org detecta y bloquea los intentos de suplantación de dominio de un dominio dentro de la organización.

4. **La inteligencia de suplantación entre dominios** detecta y bloquea los intentos de suplantación de dominio de un dominio fuera de la organización.

5. **El filtrado masivo** permite a los administradores configurar un nivel de confianza masivo (BCL) que indica si el mensaje se envió desde un remitente masivo. Los administradores pueden usar el control deslizante masivo en la directiva contra correo no deseado para decidir qué nivel de correo masivo tratar como correo no deseado.

6. **La inteligencia de buzones** de correo aprende de comportamientos de correo electrónico de usuario estándar. Aprovecha el gráfico de comunicación de un usuario para detectar cuándo un remitente solo parece ser alguien con el que el usuario suele comunicarse, pero en realidad es malintencionado. Este método detecta la suplantación.

7. **La suplantación de inteligencia de buzones** habilita o deshabilita los resultados de suplantación mejorados en función de la asignación de remitente individual de cada usuario. Cuando está habilitada, esta característica ayuda a identificar la suplantación.

8. **La suplantación de usuario** permite a un administrador crear una lista de destinos de alto valor que probablemente se suplanten. Si llega un correo donde el remitente solo parece tener el mismo nombre y dirección que la cuenta de valor alto protegida, el correo se marca o etiqueta. (Por ejemplo, *trα cye@contoso.com* para *tracye@contoso.com*).

9. **La suplantación de** dominio detecta dominios que son similares al dominio del destinatario y que intentan parecer un dominio interno. Por ejemplo, esta suplantación *tracye@liw α re.com* para *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Fase 3: filtrado de contenido

En esta fase, la pila de filtrado comienza a controlar el contenido específico del correo, incluidos sus hipervínculos y datos adjuntos.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="La fase 3 del filtrado en MDO es el filtrado de contenido.":::

1. **Las reglas** de transporte (también conocidas como reglas de flujo de correo o reglas de transporte Exchange) permiten que un administrador lleve a cabo una amplia variedad de acciones cuando se cumple una amplia gama de condiciones para un mensaje. Todos los mensajes que fluyen a través de la organización se evalúan con las reglas de flujo de correo /reglas de transporte habilitadas.

2. **Antivirus de Microsoft Defender** y dos *motores antivirus* de terceros se usan para detectar todo el malware conocido en los datos adjuntos.

3. Los motores antivirus (AV) también se usan para escribir en  true todos los datos adjuntos, de modo que el bloqueo de tipos puede bloquear todos los datos adjuntos de los tipos especificados por el administrador.

4. Siempre que Microsoft Defender para Office 365 detecta datos adjuntos malintencionados, el hash del archivo y un hash de su contenido activo se agregan a la reputación de Exchange Online Protection (EOP). **El bloqueo de reputación** de datos adjuntos bloqueará ese archivo en todos los Office 365, y en los puntos de conexión, a través de llamadas en la nube de MSAV.

5. **La agrupación en clústeres heurísticos** puede determinar que un archivo es sospechoso en función de la heurística de entrega. Cuando se encuentra un archivo adjunto sospechoso, toda la campaña se pausa y el archivo está en espacio aislado. Si se encuentra que el archivo es malintencionado, se bloquea toda la campaña.

6. **Los modelos de aprendizaje automático** actúan en el encabezado, el contenido del cuerpo y las direcciones URL de un mensaje para detectar intentos de suplantación de identidad.

7. Microsoft usa la determinación de la reputación del espacio aislado de direcciones URL, así como la reputación de direcciones URL de fuentes de terceros en el bloqueo de reputación de direcciones **URL,** para bloquear cualquier mensaje con una dirección URL malintencionada conocida.

8. **La heurística de contenido** puede detectar mensajes sospechosos en función de la estructura y la frecuencia de palabras dentro del cuerpo del mensaje, mediante modelos de aprendizaje automático.

9. **Caja fuerte attachments** sandboxes todos los datos adjuntos de Defender para Office 365 clientes, mediante análisis dinámico para detectar amenazas nunca antes vistas.

10. **La detonación de** contenido vinculado trata todas las direcciones URL vinculadas a un archivo de un correo electrónico como datos adjuntos, lo que hace que el archivo se en espacio aislado de forma asincrónica en el momento de la entrega.

11. **La detonación de direcciones URL** se produce cuando la tecnología contra suplantación de identidad (phishing) ascendente encuentra que un mensaje o una dirección URL son sospechosos. La detonación de dirección URL espacio aislado las direcciones URL del mensaje en el momento de la entrega.

## <a name="phase-4---post-delivery-protection"></a>Fase 4: Protección posterior a la entrega

La última fase tiene lugar después de la entrega de correo o archivo, actuando en correo que se encuentra en varios buzones y archivos y vínculos que aparecen en clientes como Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="La fase 4 del filtrado en Defender for Office 365 es la protección posterior a la entrega.":::

1. **Caja fuerte links** es Defender para la protección de tiempo de clic de Office 365 de la cuenta. Cada dirección URL de cada mensaje se ajusta para apuntar a servidores de vínculos de Microsoft Caja fuerte. Cuando se hace clic en una dirección URL, se comprueba con la reputación más reciente, antes de redirigir al usuario al sitio de destino. La dirección URL está asincrónicamente en espacio aislado para actualizar su reputación.

2. La purga automática de hora cero (ZAP) para la suplantación de identidad **(phishing)** detecta y neutraliza de forma retroactiva los mensajes de suplantación de identidad malintencionados que ya se han entregado a Exchange Online buzones de correo.

3. **ZAP para malware** detecta y neutraliza retroactivamente los mensajes de malware malintencionados que ya se han entregado a Exchange Online buzones de correo.

4. **ZAP para la suplantación** de identidad (phishing) detecta y neutraliza de forma retroactiva los mensajes de correo no deseado malintencionados que ya se han entregado a Exchange Online buzones de correo.

5. **Las vistas de** campaña permiten a los administradores ver la imagen general de un ataque, más rápido y completamente, de lo que cualquier equipo podría sin automatización. Microsoft aprovecha las grandes cantidades de datos contra suplantación de identidad (phishing), antispam y antimalware en todo el servicio para ayudar a identificar las campañas y, a continuación, permite a los administradores investigarlas de principio a fin, incluidos los destinos, los impactos y los flujos, que también están disponibles en una escritura de campaña descargable.

6. **Los** complementos de mensaje de informe permiten a los usuarios notificar fácilmente falsos positivos (correo electrónico bueno, marcados erróneamente como *negativos)* o falsos negativos (correo electrónico erróneo marcado como *bueno)* a Microsoft para su análisis posterior.

7. **Caja fuerte Links for Office clients** ofrece la misma protección de tiempo de clic de Caja fuerte Links, de forma nativa, dentro de clientes de Office como Word, PowerPoint y Excel.

8. La protección **para OneDrive, SharePoint** y Teams ofrece la misma protección de datos adjuntos de Caja fuerte contra archivos malintencionados, de forma nativa, dentro de OneDrive, SharePoint y Microsoft Teams.

9. Cuando se selecciona una dirección URL que apunta a un archivo después de la entrega, la **detonación de** contenido vinculado muestra una página de advertencia hasta que se completa el espacio aislado del archivo y se encuentra que la dirección URL es segura.

## <a name="the-filtering-stack-diagram"></a>Diagrama de pila de filtrado

El diagrama final (como con todas las partes del diagrama que lo componen) está sujeto a cambios a medida que el producto *crece y se desarrolla*. Marca esta página y usa **la** opción de comentarios que encontrarás en la parte inferior si necesitas preguntar después de las actualizaciones. Para los registros, esta es la pila con todas las fases en orden:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Todas las fases de filtrado en MDO en orden, de 1 a 4.":::

## <a name="more-information"></a>Más información

¿Necesita configurar Microsoft Defender para Office 365 ***en este momento** _? Use esta pila, _now*, con [este paso a paso](protect-against-threats.md) para empezar a proteger su organización.

*Gracias especial de MSFTTracyP y* del equipo de redacción de documentos a Giulian Garruba por este contenido .
