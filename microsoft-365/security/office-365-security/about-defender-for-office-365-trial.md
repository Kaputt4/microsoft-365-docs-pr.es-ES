---
title: Acerca de la prueba de Microsoft Defender para Office 365
f1.keywords: ''
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdo
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden obtener información sobre el modo de prueba de Microsoft Defender para Office 365
ms.openlocfilehash: 883e91227ccf99835d85ea5253f89d765c3693df
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481380"
---
# <a name="about-the-microsoft-defender-for-office-365-trial"></a>Acerca de la prueba de Microsoft Defender para Office 365

> [!IMPORTANT]
> Comience rápidamente con nuestro cuaderno de estrategias de prueba fácil de usar [para Microsoft Defender para Office 365](trial-playbook-defender-for-office-365.md). Este cuaderno de estrategias le ayudará a sacar el máximo partido a su evaluación gratuita mostrando cómo proteger su organización con Microsoft Defender para Office 365.

Microsoft Defender para Office 365 protege a su organización frente a amenazas malintencionadas que representan los mensajes de correo electrónico, los vínculos (DIRECCIONES URL) y las herramientas de colaboración. Microsoft Defender para Office 365 incluye:

- **Directivas de protección contra amenazas**: defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización.
- **Informes**: vea informes en tiempo real para supervisar el rendimiento de Microsoft Defender para Office 365 en la organización.
- **Investigación de amenazas y capacidades de respuesta**: use las herramientas más avanzadas para investigar, entender, simular y evitar las amenazas.
- **Investigación y respuestas automáticas**: ahorre tiempo y esfuerzo al investigar y mitigar amenazas.

Una evaluación Microsoft Defender para Office 365 es una manera fácil de probar las funcionalidades de Defender para Office 365 Plan 2 de forma gratuita, después de unos pocos clics. Estas funcionalidades de alto nivel se describen en la tabla siguiente:

|Característica|Descripción|
|---|---|
|[Configuración exclusiva en las directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)|Obtenga la protección de suplantación de usuario, la protección de suplantación de dominio, la inteligencia de buzones de correo y los umbrales avanzados de suplantación de identidad.|
|[Archivos adjuntos seguros](safe-attachments.md)|Inspeccione los datos adjuntos del correo electrónico y otros archivos en un entorno de detonación controlado para detectar malware nuevo y evasivo.|
|[Vínculos seguros](safe-links.md)|Realice comprobaciones de tiempo de clic para asegurarse de que las direcciones URL que podrían haber pasado la inspección inicial no se han armado.|
|[Seguimientos de amenazas](threat-trackers.md)<sup>\*</sup>|Use widgets informativos y vistas para identificar problemas de ciberseguridad que podrían afectar a su organización.|
|[Explorador de amenazas](threat-explorer.md)<sup>\*</sup>|Busque información casi en tiempo real sobre amenazas en el correo electrónico Office 365.|
|[Investigación y respuesta automatizadas (AIR)](office-365-air.md)<sup>\*</sup>|Busque y corrija automáticamente los objetos de amenaza a medida que se desencadenen alertas.|
|[Entrenamiento de simulación de ataque](attack-simulation-training.md)<sup>\*</sup>|Entrene a los usuarios para que identifiquen los ataques de suplantación de identidad (phishing) y respondan correctamente.|
|[Vistas de campaña](campaigns.md)<sup>\*</sup>|Investigue y responda a la actividad de correo electrónico malintencionado a gran escala.|
|[Informes con funcionalidades de Defender para Office 365](view-reports-for-mdo.md)|Vea los informes, incluido el estado de protección contra amenazas, la protección contra amenazas url, la latencia de correo, etc.|
|[Protección de cuenta prioritaria](/microsoft-365/admin/setup/priority-accounts)<sup>\*</sup>|Los usuarios que identifica como cuentas de prioridad se etiquetan en alertas, informes e investigaciones para que se destaquen. También puede usar la etiqueta Prioridad en los filtros.|

<sup>\*</sup>Esta característica es exclusiva de Defender para Office 365 plan 2.

## <a name="set-up-a-defender-for-office-365-trial"></a>Configuración de una prueba de Defender para Office 365

Una prueba permite a las organizaciones configurar y configurar fácilmente las funcionalidades de Defender para Office 365. Durante la instalación, las directivas exclusivas de Defender para Office 365 (en concreto, [Datos adjuntos seguros para mensajes de correo electrónico](safe-attachments.md), [Vínculos seguros para mensajes de correo electrónico y Microsoft Teams](safe-links.md) y [protección contra suplantación en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)) se aplican mediante la plantilla Estándar para [directivas de seguridad preestablecidas](preset-security-policies.md).

De forma predeterminada, estas directivas se limitan a todos los usuarios de la organización, pero durante o después de la configuración de la prueba, puede cambiar la asignación de directivas a usuarios específicos.

> [!NOTE]
> Es probable que las directivas antispam existentes estén configuradas con la **acción Mover mensaje a la carpeta de correo no deseado Email** para el veredicto de spam de alta confianza en las directivas contra correo no deseado. La plantilla Estándar para directivas de seguridad preestablecidas usa el **mensaje de cuarentena** de acción para el correo no deseado de alta confianza, y las directivas de seguridad preestablecidas siempre se aplican antes que las directivas de antispam personalizadas o la directiva de antispam predeterminada. Para obtener más información sobre la configuración predeterminada, estándar y estricta, consulte [Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md).

Otras cargas de trabajo también están disponibles para la protección (por ejemplo, [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md) y [vínculos seguros para aplicaciones de Office compatibles](safe-links.md#safe-links-settings-for-office-apps).

Durante la configuración de la prueba, la funcionalidad de respuesta exclusiva de Defender para Office 365 plan 2 (por ejemplo, [AIR](office-365-air.md) y [el Explorador de amenazas](threat-explorer.md) también se configuran para toda la organización. No se requiere ningún ámbito de directiva.

## <a name="licensing"></a>Licencias

Como parte de la configuración de prueba, las licencias de Defender para Office 365 se aplican automáticamente a la organización. Las licencias son gratuitas durante los primeros 90 días.

La tarjeta de licencia de la prueba muestra la siguiente información:

:::image type="content" source="../../media/mdo-trial-licensing-card.png" alt-text="La tarjeta de licencia de la versión de prueba de Microsoft Defender para Office 365" lightbox="../../media/mdo-trial-licensing-card.png":::

- **Sección Tipo de uso** :
  - **Prueba**: el número de licencias de prueba Defender para Office 365 que está disponible para su uso.

    > [!NOTE]
    > En otras ubicaciones, es posible que vea el valor 300 para el número de licencias de prueba disponibles. Este valor es incorrecto (a menos que la organización tenga exactamente 300 usuarios). El número de licencias de prueba que están disponibles para usted corresponde al tamaño de la organización, no al valor arbitrario 300.

  - **Pagado**: el número de licencias de Defender para Office 365 de pago (si las hay).

- **Sección uso**: cuántos de los usuarios están cubiertos por las directivas de Defender para Office 365.
  - **Solo la detección & respuesta**: el número total de usuarios que se incluyen en los escenarios siguientes:
    - Durante la prueba, ha limitado las directivas a usuarios específicos.
    - Tiene directivas personalizadas que se limitan a usuarios específicos.
  - **Protección completa**: el número total de usuarios protegidos por Defender para Office 365 características del plan 2 (AIR, Explorador de amenazas, Entrenamiento de simulación de ataque, etc.).

Para obtener información sobre los precios, consulte [Microsoft Defender para Office 365](https://www.microsoft.com/security/business/siem-and-xdr/microsoft-defender-office-365).

## <a name="permissions"></a>Permisos

Para iniciar o finalizar la prueba, debe ser miembro de los roles **Administrador global** o Administrador de **seguridad** en Azure Active Directory. Para más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="additional-information"></a>Información adicional

Después de iniciar la prueba, los cambios y las actualizaciones pueden tardar hasta 2 horas en estar disponibles. Además, los administradores deben cerrar la sesión y volver a iniciar sesión para ver los cambios.

## <a name="availability"></a>Disponibilidad

La prueba de Defender para Office 365 se está implementando gradualmente para los clientes existentes que cumplen criterios específicos y que no tienen licencias de Defender para Office 365 Plan 2 existentes (incluidas en su suscripción o como complemento).

## <a name="terms-and-conditions"></a>Términos y condiciones

Para obtener más información, consulte [Microsoft Defender para Office 365 Términos de prueba & Condiciones](defender-for-office-365-trial-terms-and-conditions.md).

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="q-how-do-i-extend-the-trial"></a>P: Cómo ampliar la prueba?

R: Consulte [Ampliación de la prueba](/microsoft-365/commerce/try-or-buy-microsoft-365#extend-your-trial).

### <a name="q-what-happens-to-my-data-after-the-trial-expires"></a>P: ¿Qué ocurre con mis datos después de que expire la prueba?

R: Una vez que expire la prueba, tendrá acceso a los datos de prueba (datos de características de Defender para Office 365 que no tenía anteriormente) durante 30 días. Después de este período de 30 días, se eliminarán todas las directivas y datos asociados a la Defender para Office 365 prueba.

### <a name="q-how-many-times-can-i-use-the-defender-for-office-365-trial-in-my-organization"></a>P: ¿Cuántas veces puedo usar la prueba de Defender para Office 365 en mi organización?

R: Un máximo de 2 veces. Si la primera prueba expira, debe esperar al menos 30 días después de la fecha de expiración para poder inscribirse de nuevo en la Defender para Office 365 prueba. Después de la segunda prueba, no puede inscribirse en otra prueba.

## <a name="learn-more-about-defender-for-office-365"></a>Más información sobre Defender para Office 365

Defender para Office 365 ayuda a las organizaciones a proteger su empresa al ofrecer una lista completa de funcionalidades.

También puede obtener más información sobre Defender para Office 365 en esta [guía interactiva](https://aka.ms/MS365D.InteractiveGuide).

:::image type="content" source="../../media/microsoft-defender-for-office-365.png" alt-text="Diagrama conceptual Microsoft Defender para Office 365" lightbox="../../media/microsoft-defender-for-office-365.png":::

### <a name="prevention"></a>Prevención

Una pila de filtrado sólida evita una amplia variedad de ataques basados en volúmenes y dirigidos, como el riesgo de correo electrónico empresarial, la suplantación de identidad de credenciales, el ransomware y el malware avanzado.

- [Directivas contra phishing: configuración exclusiva en Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Archivos adjuntos seguros](safe-attachments.md)
- [Vínculos seguros](safe-links.md)

### <a name="detection"></a>Detección

La inteligencia artificial líder del sector detecta contenido malintencionado y sospechoso y correlaciona patrones de ataque para identificar campañas diseñadas para eludir la protección.

- [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md)

### <a name="investigation-and-hunting"></a>Investigación y búsqueda

Las experiencias eficaces ayudan a identificar, priorizar e investigar amenazas, con funcionalidades avanzadas de búsqueda para realizar un seguimiento de los ataques en Office 365.

- [Explorador de amenazas y detecciones en tiempo real](threat-explorer.md)
- [Informes en tiempo real en Defender para Office 365](view-reports-for-mdo.md)
- [Rastreadores de amenazas: nuevos y destacables](threat-trackers.md)
- Integración con [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

### <a name="response-and-remediation"></a>Respuesta y corrección

Las amplias capacidades de automatización y respuesta a incidentes amplían la eficacia y la eficacia del equipo de seguridad.

- [Investigación y respuesta automatizadas (AIR) en Microsoft Defender para Office 365](office-365-air.md)

### <a name="awareness-and-training"></a>Sensibilización y entrenamiento

Las funcionalidades enriquecidas de simulación y entrenamiento, junto con las experiencias integradas dentro de las aplicaciones cliente, crean conocimientos sobre el usuario.

- [Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

### <a name="security-posture"></a>Posición de seguridad

Las plantillas recomendadas y la información de configuración ayudan a los clientes a obtener y mantener la seguridad.

- [Directivas de seguridad preestablecidas en Exchange Online Protection y Microsoft Defender para Office 365](preset-security-policies.md)
- [Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md).

## <a name="give-feedback"></a>Enviar comentarios

Sus comentarios nos ayudan a mejorar la protección de su entorno frente a ataques avanzados. Comparta su experiencia e impresiones de las funcionalidades del producto y los resultados de la prueba.
