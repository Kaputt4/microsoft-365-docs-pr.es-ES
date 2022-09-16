---
title: Introducción a la configuración en profundidad de defensa para la seguridad del correo electrónico
description: Guía de configuración paso a paso sobre cómo obtener el valor de seguridad de Microsoft Defender para Office 365 cuando se tiene filtrado de correo electrónico de terceros.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: benharri
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: abd313dd2e6718d018be42ac0bcdd36f1c149c88
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740850"
---
# <a name="getting-the-best-security-value-from-microsoft-defender-for-office-365-when-you-have-third-party-email-filtering"></a>Obtener el mejor valor de seguridad de Microsoft Defender para Office 365 cuando se tiene filtrado de correo electrónico de terceros

Esta guía es para usted si:

- Tiene licencia para Microsoft Defender para Office 365 y hospedar sus buzones en Office 365
- También usa un tercero para la seguridad del correo electrónico.

La información siguiente detallará cómo sacar el máximo partido a su inversión, desglosada en pasos fáciles de seguir.

## <a name="what-you-will-need"></a>Lo que necesitará
-   Buzones hospedados en Office 365
- Uno o varios de:
  - Microsoft Defender para Office 365 Plan 1 para las características de protección
  - Microsoft Defender para Office 365 plan 2 para la mayoría de las demás características (incluidas en los planes E5)
  - Microsoft Defender para Office 365 prueba (disponible para todos los clientes en aka.ms/tryMDO)
-   Permisos suficientes para configurar las características que se describen a continuación

## <a name="step-1--understand-the-value-you-already-have"></a>Paso 1: Comprender el valor que ya tiene

### <a name="protection-features"></a>Características de protección

-   La protección integrada ofrece un nivel base de protección discreta e incluye malware, día cero (datos adjuntos seguros) y protección de direcciones URL (vínculos seguros) en el correo electrónico (incluido el correo electrónico interno), SharePoint Online, OneDrive y Teams. Tenga en cuenta que la protección de direcciones URL proporcionada en este estado es solo a través de una llamada API. No encapsula ni reescriba direcciones URL, pero requiere un cliente de Outlook compatible. Puede crear sus propias directivas personalizadas para expandir la protección.

**Lea más & vea un vídeo de información general de Vínculos seguros aquí:** [Introducción a los vínculos seguros completos](../safe-links.md)

**Obtenga más información sobre los datos adjuntos seguros aquí:** [Datos adjuntos seguros](../safe-attachments.md)   

### <a name="detection-investigation-response-and-hunting-features"></a>Características de detección, investigación, respuesta y búsqueda

-   Cuando las alertas se activan en Microsoft Defender para Office 365, se correlacionan automáticamente y se combinan en Incidentes para ayudar a reducir la fatiga de alertas en el personal de seguridad. La investigación y respuesta automatizadas (AIR) desencadenará investigaciones para ayudar a corregir y contener amenazas.

**Obtenga más información, vea un vídeo de información general y comience aquí:** [Respuesta a incidentes con Microsoft 365 Defender](/microsoft-365/security/defender/incidents-overview)

-   Threat Analytics es nuestra solución de inteligencia sobre amenazas detallada del producto de expertos investigadores de seguridad de Microsoft, informes detallados diseñados para ponerse al día sobre los grupos de amenazas más recientes, técnicas de ataque, cómo proteger su organización con indicadores de compromiso (IOC) y mucho más.

**Obtenga más información, vea un vídeo de información general y comience aquí:** [Análisis de amenazas en Microsoft 365 Defender](../../defender/threat-analytics.md)

-   El Explorador se puede usar para buscar amenazas, visualizar patrones de flujo de correo, detectar tendencias e identificar el impacto de los cambios realizados durante el ajuste de Defender para Office 365. También puede eliminar rápidamente los mensajes de su organización con unos pocos clics simples.

**Obtenga más información y comience aquí:** [Explorador de amenazas y detecciones en tiempo real](../threat-explorer.md)

## <a name="step-2--enhance-the-value-further-with-these-simple-steps"></a>Paso 2: Mejorar aún más el valor con estos sencillos pasos

### <a name="protection-features"></a>Características de protección

-   Considere la posibilidad de habilitar directivas más allá de la protección integrada. Habilitar la protección de tiempo de clic o la protección contra suplantación, por ejemplo, para agregar capas adicionales o rellenar espacios que faltan en la protección de terceros. Tenga en cuenta que si tiene una regla de transporte o un filtro de conexión que reemplaza los veredictos (esto también se puede conocer como SCL-1), tendrá que solucionarlo antes de activar otras características de protección.

**Obtenga más información aquí:** [Directivas contra suplantación de identidad](../set-up-anti-phishing-policies.md)

-   Si el proveedor de seguridad actual está configurado para modificar los mensajes *de cualquier manera*, es importante tener en cuenta que las señales de autenticación pueden afectar a la capacidad de Defender para Office de protegerle contra ataques como la suplantación de identidad. Si su tercero admite la cadena de recepción autenticada (ARC), habilitar este es un paso muy recomendado en su recorrido hacia el filtrado dual avanzado. Mover cualquier configuración de modificación de mensajes a Defender para Office 365 también es una alternativa.

**Lea más aquí:** [Uso de remitentes arc de confianza para dispositivos y servicios legítimos entre el remitente y el receptor](../use-arc-exceptions-to-mark-trusted-arc-senders.md)

-   El filtrado mejorado para conectores permite conservar la información de dirección IP y remitente a través de terceros. Esto mejora la precisión de la pila de filtrado (protección), después de las funcionalidades de infracción & mejoras de autenticación.

**Obtenga más información aquí:** [Filtrado mejorado para conectores en Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

-   La protección de cuentas prioritarias ofrecerá visibilidad mejorada para las cuentas en herramientas, junto con protección adicional cuando se encuentra en un estado de configuración de defensa avanzada en profundidad.

**Obtenga más información aquí:** [Protección de la cuenta prioritaria](protect-your-c-suite-with-priority-account-protection.md)

-   La entrega avanzada debe configurarse para entregar correctamente cualquier simulación de phish de terceros y, si tiene un buzón de operaciones de seguridad, considere la posibilidad de definirlo como un buzón de SecOps para asegurarse de *que los* correos electrónicos no se quitan del buzón debido a amenazas.

**Más información aquí:** [Entrega avanzada](../configure-advanced-delivery.md)

-   La configuración de correo electrónico notificada por el usuario se puede configurar para permitir que los usuarios notifiquen mensajes, directamente a Microsoft o a su buzón personalizado (para integrarlos con los flujos de trabajo de seguridad actuales) o ambos, también se puede acceder al portal de envíos para evaluar los falsos positivos y los falsos negativos.

**Obtenga más información aquí:** [Implementación y configuración del complemento de mensaje de informe para los usuarios](deploy-and-configure-the-report-message-add-in.md)

### <a name="detection-investigation-response-and-hunting-features"></a>Características de detección, investigación, respuesta y búsqueda

-   La búsqueda avanzada se puede usar para buscar amenazas de forma proactiva en su organización, mediante consultas compartidas de la comunidad para ayudarle a empezar. También puede usar detecciones personalizadas para configurar alertas cuando se cumplan criterios personalizados.

**Obtenga más información, vea un vídeo de información general y comience aquí:** [Información general: Búsqueda avanzada](../../defender/advanced-hunting-overview.md)

### <a name="education-features"></a>Características de educación

- Entrenamiento de simulación de ataque permite ejecutar escenarios de ciberataque realistas pero benignos en su organización. Si aún no tiene funcionalidades de simulación de suplantación de identidad (phishing) del proveedor de seguridad de correo electrónico principal, los ataques simulados de Microsoft pueden ayudarle a identificar y encontrar usuarios, directivas y prácticas vulnerables. Este es un conocimiento importante que debe tener y corregir *antes de* que un ataque real afecte a su organización. Después de la simulación, asignamos un entrenamiento personalizado o de producto para educar a los usuarios sobre las amenazas que han perdido, lo que reduce en última instancia el perfil de riesgo de la organización. Con Entrenamiento de simulación de ataque entregamos mensajes directamente en la bandeja de entrada, por lo que la experiencia del usuario es enriquecida. Esto también significa que no se necesitan cambios de seguridad, como invalidaciones, para que las simulaciones se entreguen correctamente.

**Introducción:** [Introducción al uso de la simulación de ataques](../attack-simulation-training-get-started.md)

**Vaya directamente a la entrega de una simulación aquí:** [Cómo configurar ataques automatizados y entrenamiento dentro de Entrenamiento de simulación de ataque](how-to-setup-attack-simulation-training-for-automated-attacks-and-training.md)

## <a name="step-3-and-beyond-becoming-a-dual-use-hero"></a>Paso 3 y posteriores, convirtiéndose en un héroe de doble uso

- Muchos de los equipos de seguridad deben repetir muchas de las actividades de detección, investigación, respuesta y búsqueda descritas anteriormente. Esta guía ofrece una descripción detallada de las tareas, la cadencia y las asignaciones de equipo que se recomiendan.

**Más información:** [Guía de operaciones de seguridad para Defender para Office 365](../mdo-sec-ops-guide.md)

- Tenga en cuenta experiencias de usuario como el acceso a varias cuarentenas o el envío o informes de falsos positivos y falsos negativos. Puede marcar los mensajes detectados por el servicio de terceros con un encabezado *X* personalizado, por ejemplo, para permitir que Defender para Office 365 los detecte y los ponga en cuarentena a través de reglas de transporte, lo que también proporcionaría a los usuarios un único lugar para acceder al correo en cuarentena.

**Más información:** [Configuración de directivas y permisos de cuarentena](how-to-configure-quarantine-permissions-with-quarantine-policies.md)

- La guía de migración contiene una gran cantidad de instrucciones útiles sobre cómo preparar y ajustar el entorno para prepararlo para una migración. Pero muchos de los pasos *también* se aplican a un escenario de doble uso. Simplemente ignore la guía del conmutador MX en los pasos finales. 

**Léelo aquí:** [Migración de un servicio de protección de terceros a Microsoft Defender para Office 365: Office 365 | Microsoft Docs](../migrate-to-defender-for-office-365.md)

## <a name="more-information"></a>Más información

[Migración de un servicio de protección de terceros a Microsoft Defender para Office 365](../migrate-to-defender-for-office-365.md)

[Guía de operaciones de seguridad para Defender para Office 365](../mdo-sec-ops-guide.md)

[Obtenga más Microsoft Defender para Office 365 con Microsoft 365 Defender](https://www.youtube.com/watch?v=Tdz6KfruDGo)
