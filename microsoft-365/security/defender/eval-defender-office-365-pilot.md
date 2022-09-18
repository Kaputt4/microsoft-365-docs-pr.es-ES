---
title: Microsoft Defender para Office 365 piloto, use la evaluación en el entorno de producción.
description: Pasos para probar la evaluación con grupos de usuarios activos y existentes con el fin de probar correctamente las características de Microsoft Defender para Office 365.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/25/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.custom: admindeeplinkEXCHANGE
ms.topic: how-to
ms.openlocfilehash: 72197d6543a297bf5b17c48e5d26fb29059e9d64
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67798987"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365 piloto

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 3 del 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-office-365-overview.md).

Siga estos pasos para configurar y configurar el piloto para Microsoft Defender para Office 365.

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Pasos para crear el piloto en el portal de Microsoft Defender para Office 365." lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [Paso 1: Creación de grupos piloto](#step-1-create-pilot-groups)
- [Paso 2: Configurar la protección](#step-2-configure-protection)
- [Paso 3: Probar funcionalidades: familiarizarse con la simulación, la supervisión y las métricas](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Al evaluar Microsoft Defender para Office 365, puede optar por probar usuarios específicos antes de habilitar y aplicar directivas para toda la organización. La creación de grupos de distribución puede ayudar a administrar los procesos de implementación. Por ejemplo, cree grupos como *Defender para Office 365 Users - Standard Protection*, *Defender para Office 365 Users - Strict Protection*, *Defender para Office 365 Users - Custom Protection* o *Defender para Office 365 Usuarios: excepciones*.

Es posible que no sea evidente por qué "Estándar" y "Estricto" son los términos usados para estos grupos, pero eso quedará claro cuando explore más sobre Defender para Office 365 valores preestablecidos de seguridad. Los grupos de nombres "personalizados" y "excepciones" hablan por sí mismos, y aunque la mayoría de los usuarios deben estar bajo *estándares* y *estrictos*, los grupos personalizados y de excepciones recopilarán datos valiosos para usted con respecto a la administración de riesgos.

## <a name="step-1-create-pilot-groups"></a>Paso 1: Creación de grupos piloto

Los grupos de distribución se pueden crear y definir directamente en Exchange Online o sincronizarse desde Active Directory local.

1. Inicie sesión en el Centro de Administración de Exchange (EAC) con <https://admin.exchange.microsoft.com> una cuenta a la que se le haya concedido el rol de administrador de destinatarios o que tenga permisos de administración de grupos delegados.
2. Vaya a **Grupos de destinatarios**\>.

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" Elemento de menú Grupos en el que se va a hacer clic." lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. En la página **Grupos** , seleccione ![Agregar un icono de grupo.](../../media/m365-cc-sc-add-internal-icon.png) **Agregue un grupo**.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="La opción Agregar un grupo en la que se va a hacer clic." lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. En Tipo de grupo, seleccione **Distribución** y, a continuación, haga clic en **Siguiente**.

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" La sección Elegir un tipo de grupo." lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. Asigne al grupo un **nombre** y una **descripción** opcional y, a continuación, haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="La sección Configurar los conceptos básicos." lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

6. En las páginas restantes, asigne un propietario, agregue miembros al grupo, establezca la dirección de correo electrónico, las restricciones de unirse a la salida y otras configuraciones.

## <a name="step-2-configure-protection"></a>Paso 2: Configurar la protección

Algunas funcionalidades de Defender para Office 365 están configuradas y activadas de forma predeterminada, pero es posible que las operaciones de seguridad quieran aumentar el nivel de protección del valor predeterminado.

Algunas funcionalidades *aún no* están configuradas. Tiene las siguientes opciones para configurar la protección:

- **Asignar usuarios a directivas de seguridad preestablecidas**: las [directivas de seguridad preestablecidas](../office-365-security/preset-security-policies.md) se proporcionan como método para asignar rápidamente un nivel uniforme de protección en todas las funcionalidades. Puede elegir entre **Protección estándar** o **estricta** . La ventaja aquí es que protege grupos de usuarios lo más rápido posible. Esta desventaja aquí es que no puede personalizar la mayoría de la configuración en las directivas de seguridad preestablecidas (por ejemplo, no puede cambiar una acción de **Entregar a carpetas de Email no deseado de destinatarios** a **Cuarentena** o viceversa). Tenga en cuenta también que las directivas de seguridad preestablecidas *siempre* se aplican antes que las directivas personalizadas. Por lo tanto, si desea crear y usar directivas personalizadas, deberá excluir a los usuarios de esas directivas personalizadas de las directivas de seguridad preestablecidas.

- **Configurar directivas de protección *personalizadas***: si prefiere configurar el entorno usted mismo, puede lograr rápidamente una *línea base* de protección siguiendo las instrucciones de [Protección contra amenazas](../office-365-security/protect-against-threats.md). Con este enfoque, obtendrá más información sobre la configuración que se puede configurar. Además, puede ajustar las directivas más adelante.

  También puede crear y asignar directivas de protección personalizadas como parte de la evaluación. Antes de empezar a personalizar las directivas, es importante comprender la prioridad en la que se aplican y aplican estas directivas de protección. Las operaciones de seguridad tendrán que crear o configurar algunas directivas, incluso si se aplica el valor preestablecido.

- **Asignar directivas de seguridad preestablecidas automáticamente**: las [directivas de seguridad preestablecidas](../office-365-security/preset-security-policies.md) se proporcionan como método para asignar rápidamente un nivel uniforme de protección en todas las funcionalidades. Puede elegir entre **_Standard_*_ o _*_Strict_**. Un buen enfoque consiste en empezar con directivas de seguridad preestablecidas y, a continuación, ajustar las directivas a medida que obtenga más información sobre las funcionalidades y su propio entorno de amenazas único. La ventaja aquí es que protege grupos de usuarios lo más rápido posible, con la capacidad de ajustar la protección posteriormente. (Se recomienda este método).
- **Configurar la protección de línea base manualmente**: si prefiere configurar el entorno usted mismo, puede lograr rápidamente una *línea base* de protección siguiendo las instrucciones de [Protección contra amenazas](../office-365-security/protect-against-threats.md). Con este enfoque, obtendrá más información sobre la configuración que se puede configurar. Además, puede ajustar las directivas más adelante.
- **Configurar directivas de protección *personalizadas***: también puede crear y asignar directivas de protección personalizadas como parte de la evaluación. Antes de empezar a personalizar las directivas, es importante comprender la prioridad en la que se aplican y aplican estas directivas de protección. Las operaciones de seguridad tendrán que crear algunas directivas aunque se aplique el valor preestablecido, en concreto para definir directivas de seguridad para vínculos seguros y datos adjuntos seguros.

> [!IMPORTANT]
> **Si necesita configurar directivas de protección personalizadas**, debe examinar los valores que componen las definiciones de seguridad **estándar** y **estricta** aquí: [Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](../office-365-security/recommended-settings-for-eop-and-office365.md). También se muestran los valores predeterminados, como se ve antes de que se produzca cualquier configuración. Mantenga una hoja de cálculo en la que se desvía la compilación personalizada.

### <a name="assign-preset-security-policies"></a>Asignación de directivas de seguridad preestablecidas

Se recomienda comenzar con las *directivas de línea base recomendadas* al evaluar MDO y, a continuación, refinarlas según sea necesario durante el período de evaluación.

Puede habilitar directivas de seguridad preestablecidas en EOP y Defender para Office 365 rápidamente, y asignarlas a usuarios piloto específicos o grupos definidos como parte de la evaluación. Las directivas preestablecidas ofrecen una plantilla de protección **estándar** de línea base o una plantilla de protección **estricta** más agresiva, que se puede asignar de forma independiente.

Por ejemplo, se podría aplicar una condición EOP para las evaluaciones piloto si los destinatarios son *miembros* de un grupo de *protección estándar de EOP* definido y, a continuación, se administran agregando cuentas al grupo o quitando la cuenta del mismo.

Del mismo modo, se podría aplicar una condición Defender para Office 365 para las evaluaciones piloto si los destinatarios son *miembros* de un grupo definido *Defender para Office 365 Protección estándar* y, a continuación, se administran agregando o quitando cuentas a través del grupo.

Para obtener instrucciones completas, consulte [Uso del portal de Microsoft 365 Defender para asignar directivas de seguridad preestablecidas estándar y estricta a los usuarios](../office-365-security/preset-security-policies.md#use-the-microsoft-365-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

### <a name="configure-custom-protection-policies"></a>Configuración de directivas de protección personalizadas

Las plantillas de directiva de Defender para Office 365 *estándar* o *estricta* predefinida proporcionan a los usuarios piloto la protección de línea base recomendada. Sin embargo, también puede crear y asignar directivas de protección personalizadas como parte de la evaluación.

Es *importante* tener en cuenta la precedencia que tienen estas directivas de protección cuando se aplican y aplican, como se explica en [Orden y prioridad de la protección por correo electrónico: Office 365](../office-365-security/how-policies-and-protections-are-combined.md) y [Orden de precedencia para las directivas de seguridad preestablecidas y otras directivas](../office-365-security/preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies).

En la tabla siguiente se proporcionan referencias y más instrucciones para configurar y asignar directivas de protección personalizadas:

|Policy|Descripción|Incluido en el valor preestablecido<br>directivas de seguridad?|Directiva predeterminada<br>¿Disponible?|Referencia|
|---|---|:---:|:---:|---|
|Directivas de filtro de conexión|Identifique los servidores de correo electrónico de origen correctos o incorrectos por dirección IP.|No|Sí|[Configuración de la directiva de filtro de conexión predeterminada en EOP](../office-365-security/configure-the-connection-filter-policy.md)|
|Directivas de filtro de correo no deseado saliente|Especifique los límites de velocidad de mensajes salientes y controle el reenvío de correo electrónico externo.|No|Sí|[Configuración del filtrado de correo no deseado saliente en EOP](../office-365-security/configure-the-outbound-spam-policy.md)|
|Directivas antimalware|Proteja a los usuarios del malware de correo electrónico, incluidas las acciones que se deben realizar y a quién notificar si se detecta malware.|Sí|Sí|[Configuración de directivas antimalware en EOP](../office-365-security/configure-anti-malware-policies.md)|
|Directivas contra correo electrónico no deseado|Proteja a los usuarios del correo no deseado de correo electrónico, incluidas las acciones que se realizarán si se detecta correo no deseado.|Sí|Sí|[Configuración de directivas contra correo no deseado en Defender para Office 365](../office-365-security/configure-your-spam-filter-policies.md)|
|Protección contra la suplantación de identidad|Proteja a los usuarios de los intentos de suplantación de identidad mediante la inteligencia suplantada y la información de inteligencia de suplantación de identidad.|Sí|Sí|[Configuración de la inteligencia de suplantación de identidad en Defender para Office 365](../office-365-security/learn-about-spoof-intelligence.md) <br><br> [Configuración de directivas contra phishing en EOP](../office-365-security/configure-anti-phishing-policies-eop.md)|
|Protección contra suplantación|Protección de los usuarios frente a ataques de suplantación de identidad (phishing) y configuración de sugerencias de seguridad en mensajes sospechosos|Sí, pero se requiere alguna configuración.|Sí, pero se requiere alguna configuración.|[Configuración de suplantación en directivas contra suplantación de identidad en Microsoft Defender para Office 365](../office-365-security/set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <br><br> [Información de suplantación en Defender para Office 365](../office-365-security/impersonation-insight.md) <br><br> [Configuración de directivas contra phishing en Microsoft Defender para Office 365](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|Directivas de datos adjuntos seguros|Proteja a los usuarios de contenido malintencionado en archivos y datos adjuntos de correo electrónico en SharePoint, OneDrive y Teams.|Yes|De forma eficaz, a través de la protección integrada|[Configuración de directivas de datos adjuntos seguros en Defender para Office 365](../office-365-security/set-up-safe-attachments-policies.md)|
|Directivas de vínculos seguros|Proteja a los usuarios de la apertura y el uso compartido de vínculos malintencionados en mensajes de correo electrónico o aplicaciones de Office compatibles.|Yes|De forma eficaz, a través de la protección integrada|[Configurar directivas de Vínculos seguros en Microsoft Defender para Office 365](../office-365-security/set-up-safe-links-policies.md)|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>Paso 3: Probar las funcionalidades y familiarizarse con la simulación, la supervisión y las métricas

Ahora que el piloto está configurado y configurado, resulta útil familiarizarse con las herramientas de generación de informes, supervisión y simulación de ataques que son exclusivas de Microsoft Defender para Microsoft 365.

|Funcionalidad|Descripción|Más información|
|---|---|---|
|Explorador de amenazas|El Explorador de amenazas es una herramienta eficaz casi en tiempo real para ayudar a los equipos de operaciones de seguridad a investigar y responder a las amenazas y muestra información sobre el malware sospechoso y el phish en el correo electrónico y los archivos de Office 365, así como otras amenazas y riesgos de seguridad para su organización.|[Vistas en el explorador de amenazas y detecciones en tiempo real](../office-365-security/threat-explorer-views.md)|
|Aprendizaje de simulación de ataque|Puede usar Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en su organización, lo que le ayudará a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a su entorno.|[Introducción al uso de aprendizaje de simulación de ataques](../office-365-security/attack-simulation-training-get-started.md)|
|Panel informes|En el menú de navegación izquierdo, haga clic en Informes y expanda el encabezado Email & colaboración. Los informes de colaboración Email & se tratan de detectar tendencias de seguridad, algunas de las cuales le permitirán tomar medidas (a través de botones como "Ir a envíos") y otras que mostrarán tendencias. Estas métricas se generan automáticamente.|[Visualización de informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](../office-365-security/view-email-security-reports.md) <br><br> [Ver informes de Defender para Office 365 en el portal de Microsoft 365 Defender](../office-365-security/view-reports-for-mdo.md)|

## <a name="next-steps"></a>Pasos siguientes

[Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)

Vuelva a la introducción para [Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
