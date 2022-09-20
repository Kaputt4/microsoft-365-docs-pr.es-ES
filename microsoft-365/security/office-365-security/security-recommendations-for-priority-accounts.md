---
title: Recomendaciones de seguridad para cuentas de prioridad en Microsoft 365, cuentas de prioridad, cuentas de prioridad en Office 365, cuentas de prioridad en Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
- highpri
ms.custom: ''
description: Los administradores pueden aprender a elevar la configuración de seguridad y usar informes, alertas e investigaciones para las cuentas de prioridad en sus organizaciones de Microsoft 365.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 61a8dd68635c3ef71ca8573ce4d08451a581ba95
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67811338"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Recomendaciones de seguridad para cuentas prioritarias en Microsoft 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

No todas las cuentas de usuario tienen acceso a la misma información de la empresa. Algunas cuentas tienen acceso a información confidencial, como datos financieros, información de desarrollo de productos, acceso de asociados a sistemas de compilación críticos, etc. Si se pone en peligro, las cuentas que tienen acceso a información altamente confidencial suponen una amenaza grave. Llamamos a estos tipos de _cuentas cuentas prioritarias_. Las cuentas de prioridad incluyen (pero no están limitadas a) directores ejecutivos, CEO, CFO, cuentas de administrador de infraestructura, cuentas de sistema de compilación y mucho más.

En el caso de los atacantes, los ataques de phishing normales que convierten una red aleatoria para usuarios normales o desconocidos son ineficaces. Por otro lado, los ataques de _phishing_ o _caza de lanzas_ que tienen como destino cuentas prioritarias son muy gratificantes para los atacantes. Por lo tanto, las cuentas de prioridad requieren una protección más fuerte que la normal para ayudar a evitar el riesgo de la cuenta.

Microsoft 365 y Microsoft Defender para Office 365 contienen varias características clave que proporcionan capas de seguridad adicionales para las cuentas de prioridad. En este artículo se describen estas funcionalidades y cómo usarlas.

:::image type="content" source="../../media/security-recommendations-for-priority-users.png" alt-text="Resumen de las recomendaciones de seguridad en el formulario de icono" lightbox="../../media/security-recommendations-for-priority-users.png":::

|Tarea|Todos los planes de Office 365 Enterprise|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Aumento de la seguridad de inicio de sesión para las cuentas de prioridad](#increase-sign-in-security-for-priority-accounts)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Uso de directivas de seguridad preestablecidas estrictas para cuentas de prioridad](#use-strict-preset-security-policies-for-priority-accounts)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Aplicación de etiquetas de usuario a cuentas de prioridad](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Supervisión de cuentas de prioridad en alertas, informes y detecciones](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Entrenar a los usuarios](#train-users)|![Incluido.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

> [!NOTE]
> Para obtener información sobre cómo proteger _cuentas con privilegios_ (cuentas de administrador), consulte [este tema](/security/compass/critical-impact-accounts).

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aumento de la seguridad de inicio de sesión para las cuentas de prioridad

Las cuentas de prioridad requieren una mayor seguridad de inicio de sesión. Puede aumentar su seguridad de inicio de sesión mediante la necesidad de autenticación multifactor (MFA) y la deshabilitación de protocolos de autenticación heredados.

Para obtener instrucciones, consulte [el paso 1. Aumente la seguridad de inicio de sesión para los trabajadores remotos con MFA](../../solutions/empower-people-to-work-remotely-secure-sign-in.md). Aunque este artículo trata sobre los trabajos remotos, los mismos conceptos se aplican a los usuarios prioritarios.

**Nota**: Se recomienda encarecidamente deshabilitar globalmente los protocolos de autenticación heredados para todos los usuarios prioritarios, como se describe en el artículo anterior. Si los requisitos empresariales le impiden hacerlo, Exchange Online ofrece los siguientes controles para ayudar a limitar el ámbito de los protocolos de autenticación heredados:

- Puede usar [directivas de autenticación](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) y [reglas de acceso de cliente](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) en Exchange Online para bloquear o permitir la autenticación básica y los protocolos de autenticación heredados como POP3, IMAP4 y SMTP autenticado para usuarios específicos.

- Puede deshabilitar el acceso POP3 e IMAP4 en buzones individuales. Puede deshabilitar SMTP autenticado en el nivel organizativo y habilitarlo en buzones específicos que aún lo requieran. Para obtener instrucciones, consulte los artículos siguientes:
  - [Habilitar o deshabilitar el acceso POP3 o IMAP4 para un usuario](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Habilitar o deshabilitar el envío SMTP de cliente autenticado (SMTP AUTH)](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

También merece la pena tener en cuenta que la autenticación básica está en desuso en Exchange Online para Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 y PowerShell remoto. Para obtener más información, consulte esta [entrada de blog](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Uso de directivas de seguridad preestablecidas estrictas para cuentas de prioridad

Los usuarios prioritarios requieren acciones más estrictas para las distintas protecciones disponibles en Exchange Online Protection (EOP) y Defender para Office 365.

Por ejemplo, en lugar de entregar mensajes que se clasificaron como correo no deseado en la carpeta junk Email, debe poner en cuarentena esos mismos mensajes si están destinados a cuentas de prioridad.

Puede implementar este enfoque estricto para las cuentas de prioridad mediante el perfil Strict en las directivas de seguridad preestablecidas.

Las directivas de seguridad preestablecidas son una ubicación cómoda y central para aplicar nuestra configuración de directiva estricta recomendada para todas las protecciones de EOP y Defender para Office 365. Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

Para obtener más información sobre cómo la configuración de directiva estricta difiere de la configuración de directiva estándar y predeterminada, consulte [Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md).

## <a name="apply-user-tags-to-priority-accounts"></a>Aplicación de etiquetas de usuario a cuentas de prioridad

Las etiquetas de usuario de Microsoft Defender para Office 365 Plan 2 (como parte de Microsoft 365 E5 o una suscripción de complemento) son una manera de identificar y clasificar rápidamente usuarios o grupos específicos de usuarios en informes e investigaciones de incidentes.

**Las cuentas de prioridad** son un tipo de etiqueta de usuario integrada (conocida como _etiqueta del sistema_) que puede usar para identificar incidentes y alertas que implican cuentas de prioridad. Para obtener más información sobre **las cuentas de prioridad**, consulte [Administración y supervisión de cuentas de prioridad](../../admin/setup/priority-accounts.md).

También puede crear etiquetas personalizadas para identificar y clasificar aún más las cuentas de prioridad. Para obtener más información, consulte [Etiquetas de usuario](user-tags.md). Puede administrar **cuentas de prioridad** (etiquetas del sistema) en la misma interfaz que las etiquetas de usuario personalizadas.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Supervisión de cuentas de prioridad en alertas, informes y detecciones

Después de proteger y etiquetar los usuarios prioritarios, puede usar los informes, alertas e investigaciones disponibles en EOP y Defender para Office 365 para identificar rápidamente incidentes o detecciones que implican cuentas prioritarias. Las características que admiten etiquetas de usuario se describen en la tabla siguiente.

|Característica|Descripción|
|---|---|
|Alertas|Las etiquetas de usuario de los usuarios afectados están visibles y están disponibles como filtros en la página **Alertas** del portal de Microsoft 365 Defender. Para obtener más información, consulte [Visualización de alertas](../../compliance/alert-policies.md#view-alerts).|
|Explorador <p> Detecciones en tiempo real|En **explorer** (Defender para Office 365 plan 2) o **detecciones en tiempo real** (Defender para Office 365 plan 1), las etiquetas de usuario son visibles en la vista de cuadrícula de Email y el control flotante de detalles de Email. Las etiquetas de usuario también están disponibles como una propiedad filtrable. Para obtener más información, vea  [Etiquetas en el Explorador](threat-explorer.md#tags-in-threat-explorer).|
|Vistas de campañas|Las etiquetas de usuario son una de las muchas propiedades filtrables en Vistas de campaña en Microsoft Defender para Office 365 Plan 2. Para obtener más información, consulte [Vistas de campaña](campaigns.md).|
|Informe de estado de protección contra amenazas|En prácticamente todas las vistas y tablas de detalles del **informe de estado de protección contra amenazas**, puede filtrar los resultados por **cuentas de prioridad**. Para obtener más información, consulte [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).|
|informe de problemas de Email de cuentas prioritarias|El **informe de problemas de Email para las cuentas de prioridad** en el Centro de administración de Exchange (EAC) contiene información sobre los mensajes no entregados y retrasados para **las cuentas de prioridad**. Para obtener más información, consulte [el informe problemas de Email para cuentas de prioridad](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|

## <a name="train-users"></a>Entrenar a los usuarios

Entrenar a los usuarios con cuentas prioritarias puede ayudar a ahorrar a esos usuarios y al equipo de operaciones de seguridad mucho tiempo y frustración. Los usuarios conocedores tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos.

El [Manual de campañas de ciberseguridad](https://www.belfercenter.org/CyberPlaybook) de la Escuela Kennedy de Harvard proporciona una excelente guía para establecer una sólida cultura de conciencia de seguridad dentro de su organización, incluido el entrenamiento de usuarios para identificar ataques de phishing.

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

|Concepto|Recursos|Descripción|
|---|---|---|
|Microsoft 365|[Caminos de aprendizaje personalizables](/office365/customlearning/)|Estos recursos pueden ayudarle a organizar el entrenamiento para los usuarios de su organización.|
|Centro de seguridad de Microsoft 365|[Módulo de aprendizaje: Protección de la organización con seguridad inteligente integrada de Microsoft 365](/training/modules/security-with-microsoft-365)|Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y articular las ventajas de estas características de seguridad.|
|Autenticación multifactor|[Verificación en dos pasos: ¿Cuál es la página de comprobación adicional?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.|
|Aprendizaje de simulación de ataque|[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)|Entrenamiento de simulación de ataque en Microsoft Defender para Office 365 Plan 2 permite al administrador configurar, iniciar y realizar un seguimiento de ataques de suplantación de identidad simulados contra grupos específicos de usuarios.|

Además, Microsoft recomienda que los usuarios realicen las acciones descritas en este artículo: [Proteger su cuenta y dispositivos de hackers y malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Entre estas acciones se incluyen:

- Uso de contraseñas seguras
- Protección de dispositivos
- Habilitación de características de seguridad en equipos Windows y Mac (para dispositivos no administrados)

## <a name="see-also"></a>Vea también

[Anuncio de la protección de cuenta prioritaria en Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
