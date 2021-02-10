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
ms.openlocfilehash: 814ca47ee48e844e313f7d75640643a0b659c527
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166374"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Recomendaciones de seguridad para cuentas de prioridad en Microsoft 365

No todas las cuentas de usuario tienen acceso a la misma información de la compañía. Algunas cuentas tienen acceso a información confidencial, como datos financieros, información de desarrollo de productos, acceso de asociados a sistemas de compilación críticos y mucho más. Si se ponen en peligro, las cuentas que tienen acceso a información extremadamente confidencial representan una amenaza grave. Llamamos a estos tipos de cuentas _cuentas de prioridad._ Las cuentas de prioridad incluyen (pero no están limitadas a) los directores ejecutivos, los CCE, los directores de finanzas, las cuentas de administrador de infraestructura, las cuentas del sistema de compilación y mucho más.

Para los atacantes, los ataques de suplantación de identidad comunes que convierten en una red aleatoria para usuarios comunes o desconocidos son ineficaces. Por otro lado, los ataques de suplantación de identidad _(phishing)_ o _whaling_ que tienen como objetivo cuentas de prioridad son muy recompensados para los atacantes. Por lo tanto, las cuentas de prioridad requieren una protección más sólida que la protección normal para ayudar a evitar que la cuenta se vea comprometida.

Microsoft 365 y Microsoft Defender para Office 365 contienen varias características clave que proporcionan capas adicionales de seguridad para sus cuentas de prioridad. En este artículo se describen estas funcionalidades y cómo usarlas.

![Resumen de las recomendaciones de seguridad en forma de icono](../../media/security-recommendations-for-priority-users.png)

****

|Task|Todos los planes de Office 365 Enterprise|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Aumentar la seguridad de inicio de sesión para las cuentas de prioridad](#increase-sign-in-security-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Usar directivas de seguridad preestablecidas estrictas para cuentas de prioridad](#use-strict-preset-security-policies-for-priority-accounts)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Aplicar etiquetas de usuario a cuentas de prioridad](#apply-user-tags-to-priority-accounts)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Supervisar cuentas de prioridad en alertas, informes y detecciones](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Entrenar a los usuarios](#train-users)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aumentar la seguridad de inicio de sesión para las cuentas de prioridad

Las cuentas de prioridad requieren una mayor seguridad de inicio de sesión. Puede aumentar su seguridad de inicio de sesión si requiere la autenticación multifactor (MFA) y deshabilita los protocolos de autenticación heredados.

Para obtener instrucciones, consulte [el paso 1. Aumente la seguridad de inicio de sesión para los trabajadores remotos con MFA.](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in) Aunque este artículo trata sobre los trabajadores remotos, los mismos conceptos se aplican a los usuarios con prioridad.

**Nota:** Le recomendamos encarecidamente que deshabilite globalmente los protocolos de autenticación heredados para todos los usuarios con prioridad, como se describe en el artículo anterior. Si los requisitos empresariales le impiden hacerlo, Exchange Online ofrece los siguientes controles para ayudar a limitar el ámbito de los protocolos de autenticación heredados:

- Puede usar [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) directivas [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) de autenticación y reglas de acceso de cliente en Exchange Online para bloquear o permitir la autenticación básica y protocolos de autenticación heredados como POP3, IMAP4 y SMTP autenticado para usuarios específicos.

- Puede deshabilitar el acceso a POP3 e IMAP4 en buzones individuales. Puede deshabilitar SMTP autenticado en el nivel organizativo y habilitarlo en buzones específicos que aún lo necesiten. Para obtener instrucciones, consulte los siguientes temas:
  - [Habilitar o deshabilitar el acceso a POP3 o IMAP4 para un usuario](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Habilitar o deshabilitar el envío SMTP del cliente autenticado (AUTH SMTP)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

También cabe destacar que la autenticación básica está en proceso de desuso en Exchange Online para servicios Web Exchange (EWS), Exchange ActiveSync, POP3, IMAP4 y PowerShell remoto. Para obtener más información, consulte esta [entrada de blog.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Usar directivas de seguridad preestablecidas estrictas para cuentas de prioridad

Los usuarios prioritarios requieren acciones más estrictas para las distintas protecciones que están disponibles en Exchange Online Protection (EOP) y Defender para Office 365.

Por ejemplo, en lugar de entregar mensajes clasificados como correo no deseado a la carpeta correo no deseado, debe poner en cuarentena esos mismos mensajes si están destinados a cuentas de prioridad.

Puede implementar este enfoque estricto para las cuentas de prioridad mediante el perfil Estricto en las directivas de seguridad preestablecidas.

Las directivas de seguridad preestablecidas son una ubicación cómoda y central para aplicar la configuración de directiva estricta recomendada para todas las protecciones de EOP y Defender para Office 365. Para obtener más información, vea [Las directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365.](preset-security-policies.md)

Para obtener más información sobre cómo la configuración de directiva Estricta difiere de la configuración de directiva predeterminada y estándar, vea Configuración recomendada para EOP y Microsoft Defender para la seguridad de [Office 365.](recommended-settings-for-eop-and-office365-atp.md)

## <a name="apply-user-tags-to-priority-accounts"></a>Aplicar etiquetas de usuario a cuentas de prioridad

Las etiquetas de usuario en Microsoft Defender para Office 365 Plan 2 (como parte de Microsoft 365 E5 o una suscripción de complemento) son una forma de identificar y clasificar rápidamente usuarios o grupos de usuarios específicos en informes e investigaciones de incidentes.

**Las cuentas** de prioridad son un tipo de etiqueta de usuario integrada (conocida como etiqueta del _sistema)_ que puede usar para identificar incidentes y alertas que implican cuentas de prioridad. Para obtener más información acerca **de las cuentas de prioridad,** vea Administrar y supervisar cuentas de [prioridad.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

También puede crear etiquetas personalizadas para identificar y clasificar aún más las cuentas de prioridad. Para obtener más información, vea [Etiquetas de usuario.](user-tags.md) Tenga en cuenta que puede administrar cuentas **de prioridad** (etiquetas del sistema) en la misma interfaz que las etiquetas de usuario personalizadas.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Supervisar cuentas de prioridad en alertas, informes y detecciones

Después de proteger y etiquetar a los usuarios de prioridad, puede usar los informes, alertas e investigaciones disponibles en EOP y Defender para Office 365 para identificar rápidamente incidentes o detecciones que implican cuentas de prioridad. Las características que admiten etiquetas de usuario se describen en la tabla siguiente.

<br>

****

|Característica|Descripción|
|---|---|
|Alertas|Las etiquetas de usuario de los usuarios  afectados están visibles y disponibles como filtros en la página Ver alertas en el Centro de & cumplimiento. Para obtener más información, vea [Ver alertas.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|Explorador de amenazas <p> Detecciones en tiempo real|En el Explorador de amenazas **(Microsoft** Defender para Office 365 Plan 2) o en detecciones en tiempo real (Microsoft Defender para Office 365 Plan 1), las etiquetas de usuario están **visibles** en la vista cuadrícula de correo electrónico y en el control desplegable Detalles de correo electrónico. Las etiquetas de usuario también están disponibles como una propiedad que se puede filtrar. Para obtener más información, vea [Etiquetas en el Explorador de amenazas.](threat-explorer.md#tags-in-threat-explorer)|
|Vistas de campañas|Las etiquetas de usuario son una de las muchas propiedades que se pueden filtrar en vistas de campaña en Microsoft Defender para Office 365 Plan 2. Para obtener más información, vea [Vistas de la campaña.](campaigns.md)|
|Informe de estado de protección contra amenazas|En prácticamente todas las vistas y tablas de detalles del informe de estado de protección contra **amenazas,** puede filtrar los resultados por **cuentas de prioridad.** Para obtener más información, consulta [el informe de estado de protección contra amenazas.](view-email-security-reports.md#threat-protection-status-report)|
|Informe de problemas de correo electrónico para cuentas de prioridad|El **informe problemas de** correo electrónico para cuentas de prioridad en el Centro de administración de Exchange (EAC) contiene información sobre los mensajes no entregados y retrasados para las cuentas de **prioridad.** Para obtener más información, consulte [Problemas de correo electrónico para el informe de cuentas de prioridad.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)|
|

## <a name="train-users"></a>Entrenar a los usuarios

La formación de usuarios con cuentas de prioridad puede ayudar a ahorrar tiempo y frustración a esos usuarios y al equipo de operaciones de seguridad. Los usuarios expertos tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos.

El Manual [](https://www.belfercenter.org/CyberPlaybook) de campañas de ciberseguridad de la escuela Descluyéndote proporciona una guía excelente para establecer una cultura sólida de reconocimiento de la seguridad dentro de su organización, incluida la formación de los usuarios para identificar ataques de suplantación de identidad.

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

<br>

****

|Concepto|Recursos|Descripción|
|---|---|---|
|Microsoft 365|[Caminos de aprendizaje personalizables](https://docs.microsoft.com/office365/customlearning/)|Estos recursos pueden ayudarle a reunir formación para los usuarios de su organización.|
|Seguridad de Microsoft 365|[Módulo de aprendizaje: proteger su organización con seguridad inteligente integrada de Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365)|Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y para articular las ventajas de estas características de seguridad.|
|Autenticación multifactor|[Comprobación en dos pasos: ¿Cuál es la página de verificación adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.|
|Aprendizaje de simulación de ataques|[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)|La formación de simulación de ataques en Microsoft Defender para Office 365 Plan 2 permite a los administradores configurar, iniciar y realizar un seguimiento de ataques de suplantación de identidad simulados contra grupos específicos de usuarios.|

Además, Microsoft recomienda que los usuarios tomen las acciones descritas en este artículo: Proteger su cuenta y dispositivos [de hackers y malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Entre estas acciones se incluyen:

- Uso de contraseñas seguras
- Protección de dispositivos
- Habilitación de características de seguridad en equipos Windows 10 y Mac (para dispositivos no administrados)

## <a name="see-also"></a>Recursos adicionales

[Anuncio de protección de cuentas de prioridad en Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
