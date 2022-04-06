---
title: Piloto de Microsoft Defender para Office 365, use la evaluación en el entorno de producción
description: Pasos para probar la evaluación con grupos de usuarios activos y existentes para probar correctamente las características de Microsoft Defender para Office 365.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: d8cd0132c8b02ae29cf49c9a700a868fa3a93554
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64501363"
---
# <a name="pilot-microsoft-defender-for-office-365"></a>Piloto de Microsoft Defender para Office 365

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 3 de 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-office-365-overview.md).

Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para Office 365.

:::image type="content" source="../../media/defender/m365-defender-office-pilot.png" alt-text="Los pasos para crear el piloto en el portal de Microsoft Defender para Office 365 web" lightbox="../../media/defender/m365-defender-office-pilot.png":::

- [Paso 1: Crear grupos piloto](#step-1-create-pilot-groups)
- [Paso 2: Configurar la protección](#step-2-configure-protection)
- [Paso 3: Probar capacidades: familiarizarse con la simulación, la supervisión y las métricas](#step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics)

Al evaluar Microsoft Defender para Office 365, puede elegir piloto de usuarios específicos antes de habilitar y aplicar directivas para toda la organización. La creación de grupos de distribución puede ayudar a administrar los procesos de implementación. Por ejemplo, cree grupos como Defender para usuarios de *Office 365 - Protección* estándar, Defender para usuarios de *Office 365 - Protección* estricta, Defender para usuarios *de Office 365 -* Protección personalizada o Defender para usuarios de *Office 365 - Excepciones*.

Puede que no sea evidente por qué "Standard" y "Strict" son los términos usados para estos grupos, pero eso se aclarará cuando explores más acerca de Defender para Office 365 de seguridad. Los grupos de nombres "personalizados" y "excepciones" hablan por sí solos, y aunque la mayoría de  los usuarios deben estar bajo los estándares y estrictos *, los* grupos personalizados y de excepciones recopilarán datos valiosos para usted en relación con la administración de riesgos.

## <a name="step-1-create-pilot-groups"></a>Paso 1: Crear grupos piloto

Los grupos de distribución se pueden crear y definir directamente en Exchange Online o sincronizarse desde Active Directory local.

1. Inicie sesión en el Centro Exchange administración (EAC) con una cuenta a la que se le haya concedido el rol De administrador de destinatarios o se le hayan delegado permisos de administración de grupos.
2. En el menú de navegación, expanda *Destinatarios y* seleccione *Grupos*.

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-pilot.png" alt-text=" Elemento de menú Grupos en el que se va a hacer clic" lightbox="../../media/mdo-eval/1_mdo-eval-pilot.png":::

3. En el panel Grupos, seleccione "Agregar un grupo".

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png" alt-text="La opción Agregar un grupo para hacer clic en" lightbox="../../media/mdo-eval/2_mdo-eval-pilot-add-group.png":::

4. Para el tipo de grupo, seleccione *Distribución* y haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png" alt-text=" Sección Elegir un tipo de grupo" lightbox="../../media/mdo-eval/3-mdo-eval-pilot-group-type.png":::

5. Asigne al grupo un nombre y una descripción y, a continuación, haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png" alt-text="La sección Configurar los conceptos básicos" lightbox="../../media/mdo-eval/4_mdo-eval-pilot-set-up-basics.png":::

## <a name="step-2-configure-protection"></a>Paso 2: Configurar la protección

Algunas funcionalidades de Defender para Office 365 están configuradas y activadas de forma predeterminada, pero es posible que las operaciones de seguridad quieran aumentar el nivel de protección del valor predeterminado.

Algunas funcionalidades *aún no están configuradas* . Tiene tres opciones para configurar la protección:

- **Asignar directivas de seguridad** preestablecidas [automáticamente: las](../office-365-security/preset-security-policies.md) directivas de seguridad preestablecidas se proporcionan como método para asignar rápidamente un nivel uniforme de protección en todas las funcionalidades. Puede elegir entre **_standard_*_ o _*_strict_**. Un buen enfoque es empezar con directivas de seguridad preestablecidas y, a continuación, ajustar las directivas a medida que obtenga más información sobre las capacidades y su propio entorno de amenazas único. La ventaja aquí es que proteges grupos de usuarios lo antes posible, con la capacidad de ajustar la protección después. (Se recomienda este método).
- **Configurar la protección de** línea base manualmente: si prefiere configurar el entorno usted mismo, puede alcanzar rápidamente una línea  base de protección siguiendo las instrucciones de [Proteger contra amenazas](../office-365-security/protect-against-threats.md). Con este enfoque, podrá obtener más información sobre la configuración que se puede configurar. Además, puede ajustar las directivas más adelante.
- **Configurar *directivas* de protección personalizadas**: también puede crear y asignar directivas de protección personalizadas como parte de la evaluación. Antes de empezar a personalizar directivas, es importante comprender la prioridad en la que se aplican y aplican estas directivas de protección. Las operaciones de seguridad tendrán que crear algunas directivas incluso si se aplica el valor preestablecido, en concreto para definir directivas de seguridad para Caja fuerte vínculos y Caja fuerte datos adjuntos.
> [!IMPORTANT]
> **Si necesita configurar directivas** de protección personalizadas, debe examinar los valores que configuran las definiciones  de seguridad  estándar y estricta aquí: Configuración recomendada para *[EOP y Microsoft Defender](../office-365-security/recommended-settings-for-eop-and-office365.md)* para la seguridad Office 365 seguridad. También se enumeran los valores predeterminados, como se ve antes de que se lleve a cabo cualquier configuración. Mantenga una hoja de cálculo de dónde se desvía la compilación personalizada.

### <a name="assign-preset-security-policies"></a>Asignar directivas de seguridad preestablecidas

Se recomienda comenzar con las directivas de línea  base recomendadas al evaluar MDO y luego refinarlas según sea necesario durante el período de evaluación.

Puede habilitar EOP y Defender recomendados para Office 365 de protección rápida y asignarlas a usuarios piloto específicos o grupos definidos como parte de la evaluación. Las directivas preestablecidas ofrecen una **plantilla de protección** estándar de línea base o una plantilla de protección **estricta** más agresiva, que se puede asignar de forma independiente o combinada.

Este es el [artículo Preestablecidas directivas de seguridad en EOP y Microsoft Defender para Office 365](../office-365-security/preset-security-policies.md) que describe los pasos.

1. Inicie sesión en su Microsoft 365 inquilino. Use una cuenta con acceso al portal de Microsoft 365 Defender, agregado al rol Administración de la organización en Office 365 o al rol Administrador de seguridad en Microsoft 365.
2. En el menú de navegación, seleccione *Policías & reglas en* Correo & colaboración.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-pilot-policies.png" alt-text=" El elemento de menú & reglas que se va a hacer clic en" lightbox="../../media/mdo-eval/5_mdo-eval-pilot-policies.png":::

3. En el panel Reglas de &, haga clic en *Directivas de amenazas*.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png" alt-text=" El elemento de menú Directivas de amenazas que se va a hacer clic en" lightbox="../../media/mdo-eval/6-mdo-eval-pilot-threat-policies.png":::

4. En el portal Microsoft 365 Defender, expanda Administración de amenazas desde el menú de navegación y, a continuación, seleccione Directiva en el submenú.
5. En el panel Directiva, haga clic en *Preestablecidas directivas de seguridad*.

   :::image type="content" source="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png" alt-text="Los tipos de directivas de amenazas" lightbox="../../media/mdo-eval/7-mdo-eval-pilot-template-policies.png":::

6. Haga *clic en* Editar para configurar y asignar la directiva estándar o la directiva Estricta.

   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-pilot-preset.png" alt-text="Las distintas configuraciones aplicadas a varias directivas en la página Directivas de seguridad preestablecidas" lightbox="../../media/mdo-eval/8-mdo-eval-pilot-preset.png":::

7. Agregue condiciones para aplicar protecciones ***EOP** _ de línea base a usuarios piloto específicos o grupos de usuarios, según sea necesario, y seleccione _Next* para continuar.

   Por ejemplo, se podría aplicar una condición defender para Office 365 para evaluaciones piloto si los destinatarios son miembros de un  grupo definido defender para protección estándar y, *Office 365 a* continuación, se administra agregando cuentas al grupo o quitando una cuenta del grupo.

   :::image type="content" source="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png" alt-text="Las directivas que se consideran protecciones de EOP" lightbox="../../media/mdo-eval/9-mdo-eval-pilot-eop-protections.png":::

8. Agregue condiciones para aplicar protecciones ***MDO** _ de línea base a usuarios piloto específicos o grupos de usuarios, según sea necesario. Haga clic _Next* para continuar.

   Por ejemplo, se podría aplicar una condición defender para Office 365 para evaluaciones piloto si los destinatarios son miembros de un  grupo de Defender para protección estándar definido y *, Office 365* continuación, se administra agregando o quitando cuentas a través del grupo.

   :::image type="content" source="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png" alt-text="Las directivas consideradas defensivos de Office 365 protección" lightbox="../../media/mdo-eval/10-mdo-eval-pilot-mdo-protections.png":::

9. Revise y confirme los cambios para asignar directivas de seguridad preestablecidas.
10. Las directivas de protección predefinidas se pueden administrar (reconfigurar, volver a aplicar, deshabilitar, etc.) volviendo al portal de Microsoft 365 Defender > Directivas & reglas > Directivas de amenazas > y haciendo clic en el icono Directivas de seguridad preestablecidas *.*

### <a name="configure-custom-protection-policies"></a>Configurar directivas de protección personalizadas

Las plantillas de directiva *Standard* o *Strict* Defender predefinidas para Office 365 a los usuarios piloto la protección de línea base recomendada. Sin embargo, también puede crear y asignar directivas de protección personalizadas como parte de la evaluación.

Es importante tener *en cuenta la* prioridad que estas directivas de protección tienen cuando se aplican y se aplican, como orden y prioridad de la protección de correo electrónico [- Office 365](../office-365-security/how-policies-and-protections-are-combined.md) explica.

En la tabla siguiente se proporcionan referencias y más instrucciones para configurar y asignar directivas de protección personalizadas:

<br>

****

|Policy|Descripción|Referencia|
|:---:|---|---|
|Filtrado de la conexión|Identifique los servidores de correo electrónico de origen buenos o malos por sus direcciones IP.|[Configurar la directiva de filtro de conexión predeterminada en EOP](../office-365-security/configure-the-connection-filter-policy.md)|
|Antimalware|Proteger a los usuarios de malware de correo electrónico, incluidas las acciones que se deben realizar y a quién notificar si se detecta malware.|[Configurar directivas antimalware en EOP](../office-365-security/configure-anti-malware-policies.md)|
|Anti-Spoofing|Proteger a los usuarios de intentos de suplantación de suplantación de secretos y suplantación de información de inteligencia.|[Configurar la inteligencia de suplantación de seguridad en Defender para Office 365](../office-365-security/learn-about-spoof-intelligence.md)|
|Contra correo no deseado|Proteger a los usuarios contra correo no deseado de correo electrónico, incluidas las acciones que se deben realizar si se detecta correo no deseado.|[Configurar directivas contra correo no deseado en Defender para Office 365](../office-365-security/configure-your-spam-filter-policies.md)|
|Anti-Phishing|Proteger a los usuarios de ataques de suplantación de identidad (phishing) y configurar sugerencias de seguridad en mensajes sospechosos|[Configurar directivas contra suplantación de identidad (phishing) en Defender para Office 365](../office-365-security/configure-mdo-anti-phishing-policies.md)|
|Archivos adjuntos seguros|Proteger a los usuarios de contenido malintencionado en archivos adjuntos de correo electrónico en SharePoint, OneDrive y Teams.|[Configurar directivas de datos adjuntos seguros en Defender para Office 365](../office-365-security/set-up-safe-attachments-policies.md)|
|Vínculos seguros|Proteja a los usuarios de abrir y compartir vínculos malintencionados en mensajes de correo electrónico o Office aplicaciones de escritorio.|[Configurar directivas de vínculos seguros en Defender para Office 365](../office-365-security/set-up-safe-links-policies.md)|
|

## <a name="step-3-try-out-capabilities-and-get-familiar-with-simulation-monitoring-and-metrics"></a>Paso 3: Probar las capacidades y familiarizarse con la simulación, la supervisión y las métricas

Ahora que el piloto está configurado y configurado, resulta útil familiarizarse con las herramientas de simulación de informes, supervisión y ataques que son exclusivas de Microsoft Defender para Microsoft 365.

<br>

****

|Funcionalidad|Descripción|Más información|
|---|---|---|
|Explorador de amenazas|El Explorador de amenazas es una eficaz herramienta casi en tiempo real que ayuda a los equipos de operaciones de seguridad a investigar y responder a las amenazas y muestra información sobre el malware y la suplantación de identidad (phish) sospechosos en el correo electrónico y los archivos de Office 365, así como otras amenazas y riesgos de seguridad para su organización.|[Vistas en el explorador de amenazas y detecciones en tiempo real](../office-365-security/threat-explorer-views.md)|
|Simulador de ataque|Puedes usar el aprendizaje de simulación de ataques en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en tu organización, lo que te ayudará a identificar y encontrar usuarios vulnerables antes de que un ataque real impacte en tu entorno.|[Introducción al uso de aprendizaje de simulación de ataques](../office-365-security/attack-simulation-training-get-started.md)|
|Panel de informes|En el menú de navegación izquierdo, haga clic en Informes y expanda el encabezado De & de colaboración. Los informes de colaboración de email & se trata de detectar tendencias de seguridad, algunas de las cuales le permitirán tomar medidas (a través de botones como "Ir a envíos"), y otras que mostrarán tendencias, como el resumen de estado de flujo de correo, top malware, detecciones de suplantación de dominio, usuarios comprometidos, latencia de correo, vínculos de Caja fuerte e informes de datos adjuntos de Caja fuerte. Estas métricas se generan automáticamente.|[Ver informes](../office-365-security/view-email-security-reports.md)|
|

## <a name="next-steps"></a>Pasos siguientes

[Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)

Vuelva a la introducción a [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
