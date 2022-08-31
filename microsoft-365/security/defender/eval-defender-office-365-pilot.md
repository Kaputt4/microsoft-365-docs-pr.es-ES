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
ms.openlocfilehash: 9202923afc7e86e15a03b03e053e86590f4fae60
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482700"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365 piloto

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 3 del 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-office-365-overview.md).

Siga estos pasos para configurar y configurar el piloto para Microsoft Defender para Office 365.

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Pasos para crear el piloto en el portal de Microsoft Defender para Office 365" lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [Paso 1: Creación de grupos piloto](#step-1-create-pilot-groups)
- [Paso 2: Configurar la protección](#step-2-configure-protection)
- [Paso 3: Probar funcionalidades: familiarizarse con la simulación, la supervisión y las métricas](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Al evaluar Microsoft Defender para Office 365, puede optar por probar usuarios específicos antes de habilitar y aplicar directivas para toda la organización. La creación de grupos de distribución puede ayudar a administrar los procesos de implementación. Por ejemplo, cree grupos como *Defender para Office 365 Users - Standard Protection*, *Defender para Office 365 Users - Strict Protection*, *Defender para Office 365 Users - Custom Protection* o *Defender para Office 365 Usuarios: excepciones*.

Puede que no sea evidente por qué "Estándar" y "Estricto" son los términos que se usan para estos grupos, pero eso quedará claro cuando explore más sobre Defender para Office 365 valores preestablecidos de seguridad. Los grupos de nombres "personalizados" y "excepciones" hablan por sí mismos, y aunque la mayoría de los usuarios deben estar bajo *estándares* y *estrictos*, los grupos personalizados y de excepciones recopilarán datos valiosos para usted con respecto a la administración de riesgos.

## <a name="step-1-create-pilot-groups"></a>Paso 1: Creación de grupos piloto

Los grupos de distribución se pueden crear y definir directamente en Exchange Online o sincronizarse desde Active Directory local.

1. Inicie sesión en el Centro de Administración de Exchange (EAC) con una cuenta a la que se le haya concedido el rol de administrador de destinatarios o que tenga permisos de administración de grupos delegados.
2. En el menú de navegación, expanda *Destinatarios* y seleccione *Grupos*.

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" Elemento de menú Grupos en el que se va a hacer clic" lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. En el panel Grupos, seleccione "Agregar un grupo".

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="La opción Agregar un grupo en la que se va a hacer clic" lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. En Tipo de grupo, seleccione *Distribución* y haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" La sección Elegir un tipo de grupo" lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. Asigne al grupo un nombre y una descripción y, a continuación, haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="La sección Configuración de los conceptos básicos" lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

## <a name="step-2-configure-protection"></a>Paso 2: Configurar la protección

Algunas funcionalidades de Defender para Office 365 están configuradas y activadas de forma predeterminada, pero es posible que las operaciones de seguridad quieran aumentar el nivel de protección del valor predeterminado.

Algunas funcionalidades *aún no* están configuradas. Tiene tres opciones para configurar la protección:

- **Asignar directivas de seguridad preestablecidas automáticamente**: [las directivas de seguridad preestablecidas](../office-365-security/preset-security-policies.md) se proporcionan como método para asignar rápidamente un nivel uniforme de protección en todas las funcionalidades. Puede elegir entre **_standard_*_ o _*_strict_**. Un buen enfoque consiste en empezar con directivas de seguridad preestablecidas y, a continuación, ajustar las directivas a medida que obtenga más información sobre las funcionalidades y su propio entorno de amenazas único. La ventaja aquí es que protege grupos de usuarios lo más rápido posible, con la capacidad de ajustar la protección posteriormente. (Se recomienda este método).
- **Configurar la protección de línea base manualmente**: si prefiere configurar el entorno usted mismo, puede lograr rápidamente una *línea base* de protección siguiendo las instrucciones de [Protección contra amenazas](../office-365-security/protect-against-threats.md). Con este enfoque, obtendrá más información sobre la configuración que se puede configurar. Además, puede ajustar las directivas más adelante.
- **Configurar directivas de protección *personalizadas***: también puede crear y asignar directivas de protección personalizadas como parte de la evaluación. Antes de empezar a personalizar las directivas, es importante comprender la prioridad en la que se aplican y aplican estas directivas de protección. Las operaciones de seguridad tendrán que crear algunas directivas aunque se aplique el valor preestablecido, en concreto para definir directivas de seguridad para vínculos seguros y datos adjuntos seguros.
> [!IMPORTANT]
> **Si necesita configurar directivas de protección personalizadas**, debe examinar los valores que componen las definiciones de seguridad **estándar** y **estricta** aquí: *[Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](../office-365-security/recommended-settings-for-eop-and-office365.md)*. También se muestran los valores predeterminados, como se ve antes de que se produzca cualquier configuración. Mantenga una hoja de cálculo en la que se desvía la compilación personalizada.

### <a name="assign-preset-security-policies"></a>Asignación de directivas de seguridad preestablecidas

Se recomienda comenzar con las *directivas de línea base recomendadas* al evaluar MDO y, a continuación, refinarlas según sea necesario durante el período de evaluación.

Puede habilitar las directivas de protección de Defender para Office 365 y EOP recomendadas rápidamente y asignarlas a usuarios piloto específicos o grupos definidos como parte de la evaluación. Las directivas preestablecidas ofrecen una plantilla de protección **estándar** de línea base o una plantilla de protección **estricta** más agresiva, que se puede asignar de forma independiente o combinada.

Estas son las [directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](../office-365-security/preset-security-policies.md) artículo que describe los pasos.

1. Inicie sesión en el inquilino de Microsoft 365. Use una cuenta con acceso al portal de Microsoft 365 Defender, agregada al rol Administración de la organización en Office 365 o al rol Administrador de seguridad en Microsoft 365.
2. En el menú de navegación, seleccione *Directivas & reglas* en Colaboración Email &.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text=" El elemento de menú Directivas & reglas en el que se va a hacer clic" lightbox="../../media/mdo-eval/5_mdo-eval-pilot-policies.png":::

3. En el panel Reglas de & de directivas, haga clic en *Directivas de amenazas*.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text=" Elemento de menú Directivas de amenazas en el que se va a hacer clic" lightbox="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png":::

4. En el portal de Microsoft 365 Defender, expanda Administración de amenazas en el menú de navegación y, a continuación, seleccione Directiva en el submenú.
5. En el panel Directiva, haga clic en *Directivas de seguridad predefinidas*.

   :::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="Tipos de directivas de amenazas" lightbox="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png":::

6. Haga clic en *Editar* para configurar y asignar la directiva Estándar o La directiva estricta.

   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="Las distintas opciones de configuración aplicadas a varias directivas en la página Directivas de seguridad preestablecidas" lightbox="../../media/mdo-eval/8-mdo-eval-pilot-preset.png":::

7. Agregue condiciones para aplicar protecciones ***EOP** _ de línea base a usuarios piloto específicos o grupos de usuarios, según sea necesario, y seleccione _Next* para continuar.

   Por ejemplo, se podría aplicar una condición de Defender para Office 365 para las evaluaciones piloto si los destinatarios son *miembros* de un grupo definido *Defender para Office 365 Standard Protection* y, a continuación, se administran agregando cuentas al grupo o quitando la cuenta del mismo.

   :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="Las directivas que se consideran protecciones de EOP" lightbox="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png":::

8. Agregue condiciones para aplicar protecciones de línea base ***MDO** _ a usuarios piloto específicos o grupos de usuarios, según sea necesario. Haga clic en _Next* para continuar.

   Por ejemplo, se podría aplicar una condición de Defender para Office 365 para las evaluaciones piloto si los destinatarios son *miembros* de un grupo definido *Defender para Office 365 Standard Protection* y, a continuación, se administran agregando o quitando cuentas a través del grupo.

   :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Las directivas consideradas defensivas de la protección Office 365" lightbox="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png":::

9. Revise y confirme los cambios para asignar directivas de seguridad preestablecidas.
10. Las directivas de protección preestablecidas se pueden administrar (volver a configurar, volver a aplicar, deshabilitar, etc.) volviendo al portal de Microsoft 365 Defender > Directivas & reglas > directivas de amenazas > y haciendo clic en el icono *Directivas de seguridad preestablecidas*.

### <a name="configure-custom-protection-policies"></a>Configuración de directivas de protección personalizadas

Las plantillas de directiva de Defender para Office 365 *estándar* o *estricta* predefinida proporcionan a los usuarios piloto la protección de línea base recomendada. Sin embargo, también puede crear y asignar directivas de protección personalizadas como parte de la evaluación.

Es *importante* tener en cuenta la precedencia que tienen estas directivas de protección cuando se aplican y aplican, como se explica en [Orden y prioridad de la protección por correo electrónico Office 365](../office-365-security/how-policies-and-protections-are-combined.md).

En la tabla siguiente se proporcionan referencias y más instrucciones para configurar y asignar directivas de protección personalizadas:

<br>

****

|Policy|Descripción|Referencia|
|:---:|---|---|
|Filtrado de la conexión|Identifique los servidores de correo electrónico de origen correctos o incorrectos por sus direcciones IP.|[Configuración de la directiva de filtro de conexión predeterminada en EOP](../office-365-security/configure-the-connection-filter-policy.md)|
|Antimalware|Proteja a los usuarios del malware de correo electrónico, incluidas las acciones que se deben realizar y a quién notificar si se detecta malware.|[Configuración de directivas antimalware en EOP](../office-365-security/configure-anti-malware-policies.md)|
|Protección contra la suplantación de identidad|Proteja a los usuarios de los intentos de suplantación de identidad mediante la inteligencia suplantada y la información de inteligencia de suplantación de identidad.|[Configuración de la inteligencia de suplantación de identidad en Defender para Office 365](../office-365-security/learn-about-spoof-intelligence.md)|
|Antispam|Proteja a los usuarios del correo no deseado de correo electrónico, incluidas las acciones que se realizarán si se detecta correo no deseado.|[Configuración de directivas contra correo no deseado en Defender para Office 365](../office-365-security/configure-your-spam-filter-policies.md)|
|Anti-Phishing|Protección de los usuarios frente a ataques de suplantación de identidad (phishing) y configuración de sugerencias de seguridad en mensajes sospechosos|[Configurar directivas contra suplantación de identidad (phishing) en Defender para Office 365](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|Datos adjuntos seguros|Proteja a los usuarios de contenido malintencionado en archivos y datos adjuntos de correo electrónico en SharePoint, OneDrive y Teams.|[Configuración de directivas de datos adjuntos seguros en Defender para Office 365](../office-365-security/set-up-safe-attachments-policies.md)|
|Vínculos seguros|Proteja a los usuarios de abrir y compartir vínculos malintencionados en mensajes de correo electrónico o aplicaciones de escritorio de Office.|[Configuración de directivas de vínculos seguros en Defender para Office 365](../office-365-security/set-up-safe-links-policies.md)|
|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>Paso 3: Probar las funcionalidades y familiarizarse con la simulación, la supervisión y las métricas

Ahora que el piloto está configurado y configurado, resulta útil familiarizarse con las herramientas de generación de informes, supervisión y simulación de ataques que son exclusivas de Microsoft Defender para Microsoft 365.

<br>

****

|Funcionalidad|Descripción|Más información|
|---|---|---|
|Explorador de amenazas|El Explorador de amenazas es una herramienta eficaz casi en tiempo real para ayudar a los equipos de operaciones de seguridad a investigar y responder a las amenazas y muestra información sobre el malware sospechoso y el phish en el correo electrónico y los archivos de Office 365, así como otras amenazas y riesgos de seguridad para su organización.|[Vistas en el explorador de amenazas y detecciones en tiempo real](../office-365-security/threat-explorer-views.md)|
|Simulador de ataques|Puede usar el entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en su organización, lo que le ayudará a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a su entorno.|[Introducción al uso de aprendizaje de simulación de ataques](../office-365-security/attack-simulation-training-get-started.md)|
|Panel informes|En el menú de navegación izquierdo, haga clic en Informes y expanda el encabezado Email & colaboración. Los informes de colaboración Email & se tratan de detectar tendencias de seguridad, algunas de las cuales le permitirán realizar acciones (a través de botones como "Ir a envíos") y otras que mostrarán tendencias, como resumen de estado de Flujo de correo, Top Malware, detecciones de suplantación de identidad, usuarios en peligro, latencia de correo, vínculos seguros e informes de datos adjuntos seguros. Estas métricas se generan automáticamente.|[Ver informes](../office-365-security/view-email-security-reports.md)|
|

## <a name="next-steps"></a>Pasos siguientes

[Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)

Vuelva a la introducción para [Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
