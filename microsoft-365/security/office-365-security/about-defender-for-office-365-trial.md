---
title: Acerca de la versión de prueba de Microsoft Defender para Office 365
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX
description: Los administradores pueden obtener información sobre el modo de prueba de Microsoft Defender para Office 365
ms.openlocfilehash: f5ab0b0cd4ef5c2bf1a799043af94a0938a53783
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114900"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Acerca de la versión de prueba de Microsoft Defender para Office 365

Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. Microsoft Defender para Office 365 incluye:

- **Directivas de protección contra amenazas**: defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización.
- **Informes:** ver informes en tiempo real para supervisar el rendimiento de Defender para Office 365 en su organización.
- **Investigación de amenazas y capacidades de respuesta**: use las herramientas más avanzadas para investigar, entender, simular y evitar las amenazas.
- **Investigación y respuestas automáticas**: ahorre tiempo y esfuerzo al investigar y mitigar amenazas.

Una prueba de Microsoft Defender para Office 365 es la forma más sencilla de probar las funcionalidades de Defender para Office 365 y configurarla solo requiere un par de clics. Una vez completada la configuración de prueba, todas las funcionalidades de Defender para Office 365 Plan 1 y Plan 2 estarán disponibles en la organización durante un máximo de 90 días.

> [!NOTE]
> La configuración automatizada que se describe en este artículo se encuentra actualmente en la versión preliminar pública y es posible que no esté disponible en su ubicación.

## <a name="terms-and-conditions"></a>Términos y condiciones

La versión de prueba de Defender para Office 365 está disponible durante 90 días y se puede iniciar para todos los usuarios. Para obtener más información, vea los términos de uso de la versión de prueba de [Microsoft Defender para Office 365.](terms-of-use-defender-for-office-365-trial.md)

## <a name="set-up-a-defender-for-office-365-trial"></a>Configurar una versión de prueba de Defender para Office 365

Una prueba permite a las organizaciones configurar y configurar fácilmente las funcionalidades de Defender para Office 365. Durante la instalación, las directivas que son exclusivas de [](atp-safe-attachments.md)Defender para Office 365 (específicamente, datos adjuntos [seguros,](atp-safe-links.md)vínculos seguros y protección de suplantación en directivas contra correo no [deseado)](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)se aplican con la plantilla Estándar para las directivas de seguridad preestablecidas. [](preset-security-policies.md)

De forma predeterminada, estas directivas se aplican a todos los usuarios de la organización, pero los administradores pueden personalizar las directivas durante o después de la instalación para que se apliquen solo a usuarios específicos.

Durante la instalación, la funcionalidad de respuesta de MDO (que se encuentra en MDO P2 o equivalente) también se configura para toda la organización. No se requiere ningún ámbito de directiva.

## <a name="licensing"></a>Licencias

Como parte de la configuración de prueba, las licencias de Defender para Office 365 se aplican automáticamente a la organización. Las licencias son gratuitas durante los primeros 90 días.

## <a name="permissions"></a>Permisos

Para iniciar o finalizar la prueba, debe ser miembro de los **roles** Administrador **global** o Administrador de seguridad en Azure Active Directory. Para obtener más información, consulte [Acerca de los roles de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

## <a name="additional-information"></a>Información adicional

Después de inscribirte en la versión de prueba, los cambios y las actualizaciones pueden tardar hasta 2 horas en estar disponibles. Además, los administradores deben cerrar sesión y volver a iniciarla para ver los cambios.

Los administradores pueden deshabilitar la versión de prueba en cualquier momento yendo a la <> usuario.

## <a name="availability"></a>Disponibilidad

La versión de prueba de Defender para Office 365 se está implementando gradualmente para los clientes existentes que cumplen criterios específicos (incluida la zona geográfica) y que no tienen licencias existentes de Defender para Office 365 Plan 1 o Plan 2 (incluidas en su suscripción o como complemento).

## <a name="learn-more-about-defender-for-office-365"></a>Más información sobre Defender para Office 365

Defender para Office 365 ayuda a las organizaciones a proteger su empresa al ofrecer una amplia gama de funcionalidades.

También puede obtener más información sobre Defender para Office 365 en esta [guía interactiva.](https://techcommunity.microsoft.com/t5/video-hub/protect-your-organization-with-microsoft-365-defender/m-p/1671189)

![Diagrama conceptual de Microsoft Defender para Office 365](../../media/microsoft-defender-for-office-365.png)

### <a name="prevention"></a>Prevención

Una sólida pila de filtrado evita una amplia variedad de ataques basados en volumen y dirigidos, incluidos el peligro del correo electrónico empresarial, la suplantación de identidad de credenciales, el ransomware y el malware avanzado.

- [Directivas contra la suplantación de identidad: configuración exclusiva en Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Archivos adjuntos seguros](atp-safe-attachments.md)
- [Vínculos seguros](atp-safe-links.md)

### <a name="detection"></a>Detección

La inteligencia artificial líder del sector detecta contenido malintencionado y sospechoso y correlaciona los patrones de ataque para identificar campañas diseñadas para eludir la protección.

- [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Investigación y búsqueda

Las experiencias eficaces ayudan a identificar, priorizar e investigar amenazas, con capacidades avanzadas de búsqueda para realizar un seguimiento de los ataques en Office 365.

- [Explorador de amenazas y detecciones en tiempo real](threat-explorer.md)
- [Informes en tiempo real en Defender para Office 365](view-reports-for-atp.md)
- [Rastreadores de amenazas: nuevos y destacables](threat-trackers.md)
- Integración con [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)

### <a name="response-and-remediation"></a>Respuesta y corrección

Las amplias capacidades de automatización y respuesta a incidentes amplían la eficacia y la eficacia de su equipo de seguridad.

- [Investigación y respuesta automatizada (AIR) en Microsoft Defender para Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Sensibilización y entrenamiento

Las completas capacidades de simulación y aprendizaje, junto con las experiencias integradas dentro de las aplicaciones cliente, crean el conocimiento de los usuarios.

- [Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

### <a name="secure-posture"></a>Posición segura

Las plantillas recomendadas y las conclusiones de configuración ayudan a los clientes a obtener y mantener la seguridad.

- [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md)
- [Analizador de configuración para las directivas de protección en EOP y Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md).

## <a name="give-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección de su entorno frente a ataques avanzados. Comparta su experiencia e impresiones de las capacidades del producto y los resultados de la prueba.
