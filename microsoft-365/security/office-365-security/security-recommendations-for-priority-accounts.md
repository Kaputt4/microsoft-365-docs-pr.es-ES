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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
description: Los administradores pueden aprender a elevar la configuración de seguridad y usar informes, alertas e investigaciones para cuentas de prioridad en sus organizaciones de Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9bb2586c11a22286bde5be01f1e9b3e5e0d981ac
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207382"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Recomendaciones de seguridad para cuentas de prioridad en Microsoft 365

No todas las cuentas de usuario tienen acceso a la misma información de la compañía. Algunas cuentas tienen acceso a información confidencial, como datos financieros, información de desarrollo de productos, acceso de asociados a sistemas de compilación críticos, etc. Si se pone en peligro, las cuentas que tienen acceso a información altamente confidencial representan una amenaza grave. Llamamos a estos tipos de cuentas _cuentas de prioridad._ Las cuentas de prioridad incluyen (pero no están limitadas a) directores ejecutivos, OSC, CFO, cuentas de administrador de infraestructura, crear cuentas del sistema y mucho más.

Para los atacantes, los ataques de phishing normales que convierten una red aleatoria para usuarios normales o desconocidos son ineficaces. Por otra parte, los ataques _de phishing_ o _whaling_ de lanza que apuntan a cuentas de prioridad son muy gratificantes para los atacantes. Por lo tanto, las cuentas de prioridad requieren una protección más sólida que la normal para ayudar a evitar el riesgo de la cuenta.

Microsoft 365 y Microsoft Defender para Office 365 contienen varias características clave que proporcionan capas de seguridad adicionales para las cuentas de prioridad. En este artículo se describen estas funcionalidades y cómo usarlas.

![Resumen de las recomendaciones de seguridad en forma de icono](../../media/security-recommendations-for-priority-users.png)

****

|Tarea|Todos los planes de Office 365 Enterprise|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Aumentar la seguridad de inicio de sesión para cuentas de prioridad](#increase-sign-in-security-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Usar directivas de seguridad preestablecidas estrictas para cuentas de prioridad](#use-strict-preset-security-policies-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Aplicar etiquetas de usuario a cuentas de prioridad](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Supervisar cuentas de prioridad en alertas, informes y detecciones](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Entrenar a los usuarios](#train-users)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aumentar la seguridad de inicio de sesión para cuentas de prioridad

Las cuentas de prioridad requieren una mayor seguridad de inicio de sesión. Puede aumentar su seguridad de inicio de sesión al requerir la autenticación multifactor (MFA) y deshabilitar los protocolos de autenticación heredados.

Para obtener instrucciones, consulte [step 1. Aumentar la seguridad de inicio de sesión para los trabajadores remotos con MFA](../../solutions/empower-people-to-work-remotely-secure-sign-in.md). Aunque este artículo trata sobre los trabajadores remotos, los mismos conceptos se aplican a los usuarios prioritarios.

**Nota:** Se recomienda deshabilitar globalmente los protocolos de autenticación heredados para todos los usuarios prioritarios, tal como se describe en el artículo anterior. Si los requisitos empresariales le impiden hacerlo, Exchange Online ofrece los siguientes controles para ayudar a limitar el ámbito de los protocolos de autenticación heredados:

- Puede usar [](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) directivas [](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) de autenticación y reglas de acceso de cliente en Exchange Online para bloquear o permitir la autenticación básica y los protocolos de autenticación heredados como POP3, IMAP4 y SMTP autenticado para usuarios específicos.

- Puede deshabilitar el acceso a POP3 e IMAP4 en buzones individuales. Puede deshabilitar SMTP autenticado en el nivel organizativo y habilitarlo en buzones específicos que aún lo requieran. Para obtener instrucciones, consulte los temas siguientes:
  - [Habilitar o deshabilitar el acceso POP3 o IMAP4 para un usuario](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Habilitar o deshabilitar el envío SMTP del cliente autenticado (AUTH SMTP)](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

También vale la pena señalar que la autenticación básica está en proceso de desuso en Exchange Online para Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 y PowerShell remoto. Para obtener más información, vea esta [entrada de blog](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Usar directivas de seguridad preestablecidas estrictas para cuentas de prioridad

Los usuarios prioritarios requieren acciones más estrictas para las distintas protecciones disponibles en Exchange Online Protection (EOP) y Defender para Office 365.

Por ejemplo, en lugar de entregar mensajes clasificados como correo no deseado en la carpeta Correo no deseado, debe poner en cuarentena esos mismos mensajes si están destinados a cuentas de prioridad.

Puede implementar este enfoque estricto para las cuentas de prioridad mediante el perfil Estricto en las directivas de seguridad preestablecidas.

Las directivas de seguridad preestablecidas son una ubicación cómoda y central para aplicar nuestra configuración de directiva estricta recomendada para todas las protecciones de EOP y Defender para Office 365. Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

Para obtener más información sobre cómo la configuración de directivas estrictas difiere de la configuración predeterminada y la configuración de directiva estándar, vea Configuración recomendada para EOP y Microsoft Defender para la seguridad de [Office 365](recommended-settings-for-eop-and-office365.md).

## <a name="apply-user-tags-to-priority-accounts"></a>Aplicar etiquetas de usuario a cuentas de prioridad

Las etiquetas de usuario en Microsoft Defender para Office 365 Plan 2 (como parte de Microsoft 365 E5 o una suscripción de complemento) son una forma de identificar y clasificar rápidamente usuarios o grupos específicos de usuarios en informes e investigaciones de incidentes.

**Las cuentas de** prioridad son un tipo de etiqueta de usuario integrada (conocida como etiqueta del _sistema)_ que puede usar para identificar incidentes y alertas que implican cuentas de prioridad. Para obtener más información acerca **de las cuentas de prioridad,** vea Administrar y supervisar cuentas de [prioridad.](../../admin/setup/priority-accounts.md)

También puede crear etiquetas personalizadas para identificar y clasificar aún más sus cuentas de prioridad. Para obtener más información, vea [Etiquetas de usuario](user-tags.md). Tenga en cuenta que puede administrar cuentas **de prioridad** (etiquetas del sistema) en la misma interfaz que las etiquetas de usuario personalizadas.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Supervisar cuentas de prioridad en alertas, informes y detecciones

Después de proteger y etiquetar a los usuarios prioritarios, puede usar los informes, alertas e investigaciones disponibles en EOP y Defender para Office 365 para identificar rápidamente incidentes o detecciones que impliquen cuentas de prioridad. Las características que admiten etiquetas de usuario se describen en la tabla siguiente.

<br>

****

|Característica|Descripción|
|---|---|
|Alertas|Las etiquetas de usuario de los usuarios  afectados están visibles y disponibles como filtros en la página Ver alertas en el Centro de seguridad & cumplimiento. Para obtener más información, vea [Visualización de alertas](../../compliance/alert-policies.md#viewing-alerts).|
|Explorador de amenazas <p> Detecciones en tiempo real|En  el Explorador de amenazas (Microsoft Defender para Office 365 Plan 2) o en detecciones en tiempo real (Plan 1 de Microsoft Defender para Office 365), las etiquetas de usuario están **visibles** en la vista Cuadrícula de correo electrónico y en el control desplegable Detalles de correo electrónico. Las etiquetas de usuario también están disponibles como una propiedad filtrable. Para obtener más información, vea [Etiquetas en el Explorador de amenazas.](threat-explorer.md#tags-in-threat-explorer)|
|Vistas de campañas|Las etiquetas de usuario son una de las muchas propiedades que se pueden filtrar en vistas de campaña en Microsoft Defender para Office 365 Plan 2. Para obtener más información, vea [Vistas de campaña](campaigns.md).|
|Informe de estado de protección contra amenazas|En prácticamente todas las vistas y tablas de detalles del informe **de** estado de protección contra amenazas, puede filtrar los resultados por **cuentas de prioridad.** Para obtener más información, vea [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).|
|Informes de problemas de correo electrónico para cuentas de prioridad|El **informe Problemas de correo** electrónico para cuentas de prioridad en el Centro de administración de Exchange (EAC) contiene información sobre los mensajes no entregados y retrasados para cuentas de **prioridad.** Para obtener más información, vea [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|
|

## <a name="train-users"></a>Entrenar a los usuarios

La formación de usuarios con cuentas de prioridad puede ayudar a ahorrar mucho tiempo y frustración a esos usuarios y al equipo de operaciones de seguridad. Los usuarios expertos tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos.

El Manual [](https://www.belfercenter.org/CyberPlaybook) de la campaña de ciberseguridad de la Escuela Kennedy de Harvard proporciona una guía excelente para establecer una cultura sólida de concienciación de seguridad en su organización, incluida la formación de los usuarios para identificar ataques de suplantación de identidad.

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

<br>

****

|Concepto|Recursos|Descripción|
|---|---|---|
|Microsoft 365|[Caminos de aprendizaje personalizables](/office365/customlearning/)|Estos recursos pueden ayudarle a crear formación para los usuarios de su organización.|
|Seguridad de Microsoft 365|[Módulo de aprendizaje: proteger la organización con seguridad inteligente integrada de Microsoft 365](/learn/modules/security-with-microsoft-365)|Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y para expresar las ventajas de estas características de seguridad.|
|Autenticación multifactor|[Comprobación en dos pasos: ¿Cuál es la página de verificación adicional?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.|
|Aprendizaje de simulación de ataques|[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)|El aprendizaje de simulación de ataques en Microsoft Defender para Office 365 Plan 2 permite al administrador configurar, iniciar y realizar un seguimiento de ataques de suplantación de identidad simulados contra grupos específicos de usuarios.|

Además, Microsoft recomienda que los usuarios tomen las acciones descritas en este artículo: Proteger su cuenta y dispositivos [de los hackers y malware](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Entre estas acciones se incluyen:

- Uso de contraseñas seguras
- Protección de dispositivos
- Habilitar características de seguridad en equipos Windows 10 y Mac (para dispositivos no administrados)

## <a name="see-also"></a>Vea también

[Anuncio de protección de cuentas prioritarias en Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)