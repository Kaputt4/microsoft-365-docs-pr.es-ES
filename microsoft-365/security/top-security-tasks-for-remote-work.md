---
title: 12 tareas principales para que los equipos de seguridad admitan el trabajo desde casa
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.prod: m365-security
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
ms.custom: admindeeplinkDEFENDER
description: Proteja el correo electrónico y los datos empresariales frente a amenazas cibernéticas, incluidos ransomware, suplantación de identidad (phishing) y datos adjuntos malintencionados.
ms.openlocfilehash: 8169020e08cd7fd2531089807a29d1f6ac809b22
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67798855"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>12 tareas principales para que los equipos de seguridad admitan el trabajo desde casa

Si es como [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) y, de repente, se encuentra apoyando a una fuerza de trabajo principalmente basada en el hogar, queremos ayudarle a asegurarse de que su organización funciona de la forma más segura posible. En este artículo se priorizan las tareas para ayudar a los equipos de seguridad a implementar las funcionalidades de seguridad más importantes lo antes posible.

:::image type="content" source="../media/security/security-support-remote-work.png" alt-text="Las principales tareas que se deben realizar para admitir el trabajo desde casa" lightbox="../media/security/security-support-remote-work.png":::


Si es una organización pequeña o mediana que usa uno de los planes de negocio de Microsoft, consulte estos recursos en su lugar:

- [Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 para campañas](../business-premium/index.md) (incluye una configuración de seguridad recomendada para Microsoft 365 Empresa)

Para los clientes que usan nuestros planes empresariales, Microsoft recomienda completar las tareas enumeradas en la tabla siguiente que se aplican al plan de servicio. Si, en lugar de comprar un plan empresarial de Microsoft 365, está combinando suscripciones, tenga en cuenta lo siguiente:

- Microsoft 365 E3 incluye Enterprise Mobility + Security (EMS) E3 y Azure AD P1
- Microsoft 365 E5 incluye EMS E5 y Azure AD P2

****

|Paso|Tarea|Todos los planes de Office 365 Enterprise|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Habilitación de Azure AD Multi-Factor Authentication (MFA)](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Protección contra amenazas](#2-protect-against-threats)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Configuración de Microsoft Defender para Office 365](#3-configure-microsoft-defender-for-office-365)|||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Configuración de Microsoft Defender for Identity](#4-configure-microsoft-defender-for-identity)|||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Activar Microsoft 365 Defender](#5-turn-on-microsoft-365-defender)|||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6|[Configuración de Intune protección de aplicaciones móviles para teléfonos y tabletas](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Configuración de MFA y acceso condicional para invitados, incluida Intune protección de aplicaciones](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Inscribir equipos en la administración de dispositivos y requerir equipos compatibles](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Optimización de la red para la conectividad en la nube](#9-optimize-your-network-for-cloud-connectivity)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Entrenar a los usuarios](#10-train-users)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Introducción a Microsoft Defender for Cloud Apps](#11-get-started-with-microsoft-defender-for-cloud-apps)|||![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[Supervisión de amenazas y toma de medidas](#12-monitor-for-threats-and-take-action)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluido.](../media/d238e041-6854-4a78-9141-049224df0795.png)|

Antes de empezar, compruebe la [Puntuación de seguridad de Microsoft 365](./defender/microsoft-secure-score.md) en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. Desde un panel centralizado, puede supervisar y mejorar la seguridad de las identidades, datos, aplicaciones, dispositivos e infraestructura de Microsoft 365. Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad (como ver informes) o abordar recomendaciones con una aplicación o software de terceros. Las tareas recomendadas de este artículo aumentarán la puntuación.

:::image type="content" source="../media/secure-score.png" alt-text="Pantalla Puntuación de seguridad de Microsoft en el portal de Microsoft 365 Defender" lightbox="../media/secure-score.png":::

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: Habilitación de Azure AD Multi-Factor Authentication (MFA)

Lo mejor que puede hacer para mejorar la seguridad de los empleados que trabajan desde casa es activar MFA. Si aún no tiene procesos implementados, trate esto como un piloto de emergencia y asegúrese de que tiene personas de soporte técnico preparadas para ayudar a los empleados que se quedaron atascados. Como probablemente no pueda distribuir dispositivos de seguridad de hardware, use Windows Hello biometría y aplicaciones de autenticación de smartphones como Microsoft Authenticator.

Normalmente, Microsoft recomienda proporcionar a los usuarios 14 días para registrar su dispositivo para Multi-Factor Authentication antes de requerir MFA. Sin embargo, si el personal trabaja de repente desde casa, continúe y requiera MFA como prioridad de seguridad y esté preparado para ayudar a los usuarios que lo necesitan.

La aplicación de estas directivas tardará solo unos minutos, pero estará preparado para admitir a los usuarios en los próximos días.

****

|Plan|Recomendación|
|---|---|
|Planes de Microsoft 365 (sin Azure AD P1 o P2)|[Habilitar los valores predeterminados de seguridad en Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Los valores predeterminados de seguridad en Azure AD incluyen MFA para los usuarios y administradores.|
|Microsoft 365 E3 (con Azure AD P1)|Use [Directivas comunes de acceso condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las directivas siguientes: <br/>- [Requerir MFA para los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [Requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [Bloquear la autenticación heredada](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (con Azure AD P2)|Aprovechando Azure AD Identity Protection, empiece a implementar el [conjunto recomendado de acceso condicional y directivas relacionadas de](./office-365-security/identity-access-policies.md) Microsoft mediante la creación de estas directivas:<br/> - [Exigir la autenticación multifactor (MFA) cuando el riesgo de inicio de sesión es medio o alto](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [Bloquear a los clientes que no sean compatibles con la autenticación moderna](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [Los usuarios de riesgo alto tienen que cambiar la contraseña](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|

## <a name="2-protect-against-threats"></a>2: Protección contra amenazas

Todos los planes de Microsoft 365 incluyen una variedad de características de protección contra amenazas. La protección contra los golpes de estas características tarda unos minutos.

- Protección antimalware
- Protección contra archivos y direcciones URL malintencionados
- Protección contra phishing
- Protección contra correo no deseado

Consulte [Protección contra amenazas en Office 365](office-365-security/protect-against-threats.md) para obtener instrucciones que puede usar como punto de partida.

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Configurar Microsoft Defender para Office 365

Microsoft Defender para Office 365, incluidos con Microsoft 365 E5 y Office 365 E5, protege a su organización frente a amenazas malintencionadas planteadas por mensajes de correo electrónico, vínculos (DIRECCIONES URL) y herramientas de colaboración. Esto puede tardar varias horas en configurarse.

Microsoft Defender para Office 365:

- Protege a su organización frente a amenazas de correo electrónico desconocidas en tiempo real mediante sistemas inteligentes que inspeccionan los datos adjuntos y los vínculos en busca de contenido malintencionado. Estos sistemas automatizados incluyen una sólida plataforma de detonación, heurística y modelos de aprendizaje automático.
- Protege su organización cuando los usuarios colaboran y comparten archivos mediante la identificación y el bloqueo de archivos malintencionados en sitios de equipo y bibliotecas de documentos.
- Aplica modelos de aprendizaje automático y algoritmos avanzados de detección de suplantación para evitar ataques de suplantación de identidad.

Para obtener información general, incluido un resumen de los planes, consulte [Defender para Office 365](./office-365-security/defender-for-office-365.md).

El administrador global puede configurar estas protecciones:

- [Configurar directivas de vínculos seguros](office-365-security/set-up-safe-links-policies.md)
- [Configuración global de vínculos seguros](office-365-security/configure-global-settings-for-safe-links.md)
- [Configurar directivas de datos adjuntos seguros](office-365-security/set-up-safe-attachments-policies.md)

Tendrá que trabajar con el administrador de Exchange Online y el administrador de SharePoint Online para configurar Defender para Office 365 para estas cargas de trabajo:

- [Microsoft Defender para punto de conexión para SharePoint, OneDrive y Microsoft Teams](office-365-security/mdo-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Configurar Microsoft Defender for Identity

[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) es una solución de seguridad basada en la nube que aprovecha las señales locales de Active Directory para identificar, detectar e investigar las amenazas avanzadas, las identidades vulnerables y las acciones internas malintencionadas dirigidas a su organización. Céntrese en esto siguiente porque protege la infraestructura local y en la nube, no tiene dependencias ni requisitos previos y puede proporcionar ventajas inmediatas.

- Consulte [Microsoft Defender for Identity inicios rápidos](/azure-advanced-threat-protection/install-atp-step1) para obtener la configuración rápidamente.
- Ver [vídeo: Introducción a Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Revisar las [tres fases de la implementación de Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Activar Microsoft 365 Defender

Ahora que ha configurado Microsoft Defender para Office 365 y Microsoft Defender for Identity, puede ver las señales combinadas de estas funcionalidades en un panel. [Microsoft 365 Defender](./defender/microsoft-365-defender.md) reúne alertas, incidentes, investigación y respuesta automatizadas y búsqueda avanzada entre cargas de trabajo (Microsoft Defender for Identity, Defender para Office 365, Microsoft Defender para punto de conexión y Microsoft Defender for Cloud Apps) en un único panel del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>.

:::image type="content" source="../media/top-ten-security-remote-work-mtp-dashboard.png" alt-text="Panel de Microsoft 365 Defender" lightbox="../media/top-ten-security-remote-work-mtp-dashboard.png":::

Después de configurar uno o varios de los servicios de Defender para Office 365, active MTP. Las nuevas características se agregan continuamente a MTP; considere la posibilidad de participar para recibir características en versión preliminar.

- [Más información sobre MTP](./defender/microsoft-365-defender.md)
- [Activar MTP](./defender/m365d-enable.md)
- [Participar en las características en versión preliminar](./defender/preview.md)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Configurar Intune protección de aplicaciones móviles para teléfonos y tabletas

Microsoft Intune Mobile Application Management (MAM) le permite administrar y proteger los datos de su organización en teléfonos y tabletas sin administrar estos dispositivos. Aquí se muestra cómo funciona:

- Crea una directiva de Protección de aplicaciones (APP) que determina qué aplicaciones de un dispositivo se administran y qué comportamientos se permiten (por ejemplo, impedir que los datos de una aplicación administrada se copien en una aplicación no administrada). Cree una directiva para cada plataforma (iOS, Android).
- Después de crear las directivas de protección de aplicaciones, las aplica mediante la creación de una regla de acceso condicional en Azure AD para requerir aplicaciones aprobadas y protección de datos de APLICACIONES.

Las directivas de protección de aplicaciones incluyen muchas opciones de configuración. Afortunadamente, no es necesario obtener información sobre cada configuración y sopesar las opciones. Microsoft facilita la aplicación de una configuración de opciones mediante la recomendación de puntos de partida. El [marco de protección de datos que usa directivas de protección](/mem/intune/apps/app-protection-framework) de aplicaciones incluye tres niveles entre los que puede elegir.

Aún mejor, Microsoft coordina este marco de protección de aplicaciones con un conjunto de directivas relacionadas y de acceso condicional que recomendamos que todas las organizaciones usen como punto de partida. Si ha implementado MFA mediante las instrucciones de este artículo, está a mitad de camino.

Para configurar la protección de aplicaciones móviles, use las instrucciones de [Common identity and device access policies (Directivas comunes de acceso a dispositivos e identidades](./office-365-security/identity-access-policies.md)):

 1. Use la guía [Aplicar directivas de protección de datos de aplicaciones](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) para crear directivas para iOS y Android. El nivel 2 (protección de datos mejorada) se recomienda para la protección de línea base.
 2. Cree una regla de acceso condicional para [Requerir aplicaciones aprobadas y protección de aplicaciones](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection).

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Configuración de MFA y acceso condicional para invitados, incluido Intune protección de aplicaciones móviles

A continuación, vamos a asegurarnos de que puede seguir colaborando y trabajando con los invitados. Si usa el plan de Microsoft 365 E3 e implementa MFA para todos los usuarios, está establecido.

Si usa el plan de Microsoft 365 E5 y aprovecha Azure Identity Protection para MFA basado en riesgos, debe realizar un par de ajustes (porque Azure AD Identity Protection no se extiende a los invitados):

- Cree una nueva regla de acceso condicional para requerir MFA siempre para invitados y usuarios externos.
- Actualice la regla de acceso condicional de MFA basada en riesgos para excluir invitados y usuarios externos.

Use las instrucciones de [Actualización de las directivas comunes para permitir y proteger el acceso de invitado y externo](./office-365-security/identity-access-policies-guest-access.md) para comprender cómo funciona el acceso de invitado con Azure AD y actualizar las directivas afectadas.

Las directivas de protección de aplicaciones móviles Intune que creó, junto con la regla de acceso condicional para requerir aplicaciones aprobadas y protección de aplicaciones, se aplican a las cuentas de invitados y le ayudarán a proteger los datos de su organización.

> [!NOTE]
> Si ya ha inscrito equipos en la administración de dispositivos para requerir equipos compatibles, también tendrá que excluir las cuentas de invitado de la regla de acceso condicional que exige el cumplimiento del dispositivo.

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: Inscribir equipos en la administración de dispositivos y requerir equipos compatibles

Hay varios métodos para inscribir los dispositivos del personal. Cada método depende de la propiedad del dispositivo (personal o corporativo), el tipo de dispositivo (iOS, Windows o Android), y los requisitos de administración (restablecimientos, afinidad, bloqueo). Esto puede tardar un poco de tiempo en ordenarse. Consulte: [Inscribir dispositivos en Microsoft Intune](/mem/intune/enrollment/).

La manera más rápida de empezar es configurar la [inscripción automática para dispositivos Windows 10](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

También puede aprovechar estos tutoriales:

- [Use Autopilot para inscribir dispositivos Windows en Intune](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Use las características de inscripción de dispositivos corporativos de Apple en Apple Business Manager (ABM) para inscribir dispositivos iOS/iPadOS en Intune](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Después de inscribir dispositivos, use las instrucciones de [Common identity and device access policies (Directivas comunes de acceso a dispositivos e identidades](./office-365-security/identity-access-policies.md) ) para crear estas directivas:

- [Definir directivas de cumplimiento de dispositivos](./office-365-security/identity-access-policies.md#define-device-compliance-policies): la configuración recomendada para Windows 10 incluye la necesidad de protección antivirus. Si tiene Microsoft 365 E5, use Microsoft Defender para punto de conexión para supervisar el estado de los dispositivos de los empleados. Asegúrese de que las directivas de cumplimiento de otros sistemas operativos incluyen protección antivirus y software de protección de punto final.
- [Requerir equipos compatibles](./office-365-security/identity-access-policies.md#require-compliant-pcs-and-mobile-devices) : esta es la regla de acceso condicional de Azure AD que aplica las directivas de cumplimiento de dispositivos.

Solo una organización puede administrar un dispositivo, por lo que asegúrese de excluir las cuentas de invitado de la regla de acceso condicional en Azure AD. Si no excluye a los usuarios invitados y externos de las directivas que requieren cumplimiento de dispositivos, estas directivas bloquearán a estos usuarios. Para obtener más información, consulte [Actualización de las directivas comunes para permitir y proteger el acceso de invitado y externo](./office-365-security/identity-access-policies-guest-access.md).

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Optimización de la red para la conectividad en la nube

Si está habilitando rápidamente a la mayor parte de sus empleados para que trabajen desde casa, este cambio repentino de patrones de conectividad puede tener un impacto significativo en la infraestructura de red corporativa. Muchas redes se escalaron y diseñaron antes de que se adoptaran los servicios en la nube. En muchos casos, las redes son tolerantes a los trabajadores remotos, pero no se diseñaron para que todos los usuarios lo usaran de forma remota al mismo tiempo.

Los elementos de red, como concentradores VPN, equipos de salida de red central (como servidores proxy y dispositivos de prevención de pérdida de datos), ancho de banda central de Internet, circuitos MPLS de backhaul, capacidad NAT, etc., se ven repentinamente sometidos a una enorme presión debido a la carga de toda la empresa que los usa. El resultado final es un rendimiento y una productividad deficientes, junto con una mala experiencia de usuario para los usuarios que se adaptan al trabajo desde casa.

Algunas de las protecciones que tradicionalmente se han proporcionado mediante el enrutamiento del tráfico a través de una red corporativa las proporcionan las aplicaciones en la nube a las que acceden los usuarios. Si ha alcanzado este paso en este artículo, ha implementado un conjunto de sofisticados controles de seguridad en la nube para los servicios y datos de Microsoft 365. Con estos controles implementados, es posible que esté listo para enrutar el tráfico de los usuarios remotos directamente a Office 365. Si todavía necesita un vínculo VPN para acceder a otras aplicaciones, puede mejorar considerablemente el rendimiento y la experiencia del usuario mediante la implementación de la tunelización dividida. Una vez que haya alcanzado un acuerdo en su organización, un equipo de red bien coordinado puede lograr esto en un día.

Consulte estos recursos en Docs para obtener más información:

- [Información general: Optimización de la conectividad para usuarios remotos mediante la tunelización dividida de VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementación de túnel dividido de VPN en Office 365](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Artículos de blog recientes sobre este tema:

- [Cómo optimizar rápidamente el tráfico del personal remoto & reducir la carga en la infraestructura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Formas alternativas para que los profesionales de seguridad y TI logren controles de seguridad modernos en los escenarios de trabajo remoto únicos de hoy en día](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: Entrenamiento de usuarios

Entrenar a los usuarios puede ahorrar mucho tiempo y frustración a los usuarios y al equipo de operaciones de seguridad. Los usuarios conocedores tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos.

El [Manual de campañas de ciberseguridad](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) de la Escuela Kennedy de Harvard proporciona una excelente guía para establecer una sólida cultura de concienciación de seguridad dentro de su organización, incluido el entrenamiento de usuarios para identificar ataques de suplantación de identidad (phishing).

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

****

|Concepto|Recursos|
|---|---|
|Microsoft 365|[Caminos de aprendizaje personalizables](/office365/customlearning/) <p>Estos recursos pueden ayudarle a organizar el entrenamiento para los usuarios finales de su organización.|
|Centro de seguridad de Microsoft 365|[Módulo de aprendizaje: Protección de la organización con seguridad inteligente integrada de Microsoft 365](/learn/modules/security-with-microsoft-365) <p>Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y articular las ventajas de estas características de seguridad.|
|Autenticación multifactor|[Verificación en dos pasos: ¿Cuál es la página de comprobación adicional?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.|

Además de esta guía, Microsoft recomienda que los usuarios realicen las acciones descritas en este artículo: [Proteger su cuenta y dispositivos de hackers y malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Entre estas acciones se incluyen:

- Uso de contraseñas seguras
- Protección de dispositivos
- Habilitación de características de seguridad en equipos Windows 10 y Mac (para dispositivos no administrados)

Microsoft también recomienda que los usuarios protejan sus cuentas de correo electrónico personales mediante las acciones recomendadas en los artículos siguientes:

- [Ayudar a proteger su cuenta de correo electrónico de Outlook.com](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Protección de su cuenta de Gmail con la verificación en 2 pasos](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-defender-for-cloud-apps"></a>11: Introducción a Microsoft Defender for Cloud Apps

[Microsoft Defender for Cloud Apps](/cloud-app-security) proporciona una visibilidad enriquecida, control sobre los viajes de datos y análisis sofisticados para identificar y combatir las ciberamenazas en todos los servicios en la nube. Una vez que empiece a trabajar con Defender for Cloud Apps, las directivas de detección de anomalías se habilitan automáticamente, pero Defender for Cloud Apps tiene un período de aprendizaje inicial de siete días durante los cuales no se generan todas las alertas de detección de anomalías.

Empiece a trabajar con Defender for Cloud Apps ahora. Más adelante puede configurar controles y supervisión más sofisticados.

- [Inicio rápido: Introducción a Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security)
- [Obtención de análisis de comportamiento instantáneo y detección de anomalías](/cloud-app-security/anomaly-detection-policy)
- [Más información sobre Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [Revisión de nuevas características y funcionalidades](/cloud-app-security/release-notes)
- [Consulte las instrucciones básicas de configuración.](/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Supervisar las amenazas y tomar medidas

Microsoft 365 incluye varias maneras de supervisar el estado y realizar las acciones adecuadas. El mejor punto de partida es el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, donde puede ver la [puntuación segura de Microsoft](./defender/microsoft-secure-score.md) de su organización y las alertas o entidades que requieran su atención.

- [Introducción al portal de Microsoft 365 Defender](./defender/microsoft-365-defender-portal.md)
- [Consulte los portales de seguridad de Microsoft 365.](./defender/portals.md)

## <a name="next-steps"></a>Pasos siguientes

¡Enhorabuena! Ha implementado rápidamente algunas de las protecciones de seguridad más importantes y su organización es mucho más segura. Ahora está listo para ir aún más lejos con las funcionalidades de protección contra amenazas (incluidos los Microsoft Defender para punto de conexión), las funcionalidades de clasificación y protección de datos y la protección de cuentas administrativas. Para obtener un conjunto más profundo y metódico de recomendaciones de seguridad para Microsoft 365, vea [Microsoft 365 Security for Business Decision Makers (BDM)](Microsoft-365-security-for-bdm.md).

Visite también la nueva documentación de Defender for Cloud en [seguridad](/security) de Microsoft.
