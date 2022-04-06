---
title: 'Capacidades de respuesta & investigación de amenazas: Microsoft Defender para Office 365 plan 2'
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre las capacidades de investigación y respuesta de amenazas en Microsoft Defender para Office 365 Plan.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 53f1077d4ef32c6dc5698aae74de51dd5a421510
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474913"
---
# <a name="threat-investigation-and-response"></a>Investigación y respuesta de amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplicación**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)


Las capacidades de investigación y respuesta de amenazas en [Microsoft Defender](defender-for-office-365.md) para Office 365 los analistas de seguridad y los administradores protegen los Microsoft 365 de su organización para los usuarios empresariales:

- Facilitar la identificación, supervisión y comprender los ciberataques.
- Ayudar a solucionar rápidamente las amenazas en Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
- Proporcionar información y conocimientos para ayudar a las operaciones de seguridad a evitar ataques cibernéticos contra su organización.
- Usar la [investigación automatizada y la respuesta en Office 365](automated-investigation-response-office.md) amenazas críticas basadas en correo electrónico.

Las capacidades de investigación y respuesta de amenazas proporcionan información sobre amenazas y acciones de respuesta relacionadas que están disponibles en el portal Microsoft 365 Defender amenazas. Estos conocimientos pueden ayudar al equipo de seguridad de su organización a proteger a los usuarios de ataques basados en archivos o correo electrónico. Las funcionalidades ayudan a supervisar las señales y recopilar datos de varios orígenes, como la actividad del usuario, la autenticación, el correo electrónico, los equipos en peligro y los incidentes de seguridad. Los responsables de la toma de decisiones empresariales y el equipo de operaciones de seguridad pueden usar esta información para comprender y responder a las amenazas contra su organización y proteger su propiedad intelectual.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Familiarizarse con las herramientas de investigación y respuesta de amenazas

Las capacidades de investigación y respuesta de amenazas en Microsoft 365 Defender portal <https://security.microsoft.com> son un conjunto de herramientas y flujos de trabajo de respuesta que incluyen:

- [Explorador](#explorer)
- [Incidentes](#incidents)
- [Aprendizaje de simulación de ataque](attack-simulation-training.md)
- [Investigación y respuesta automatizadas](automated-investigation-response-office.md)

### <a name="explorer"></a>Explorador

Usa [el Explorador (y](threat-explorer.md) detecciones en tiempo real) para analizar amenazas, ver el volumen de ataques a lo largo del tiempo y analizar datos por familias de amenazas, infraestructura de atacantes y mucho más. Explorer (también conocido como Explorador de amenazas) es el punto de partida del flujo de trabajo de investigación de cualquier analista de seguridad.

:::image type="content" source="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png" alt-text="La página Explorador de amenazas" lightbox="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png":::

Para ver y usar este informe en el portal de Microsoft 365 Defender, <https://security.microsoft.com>vaya a **Correo electrónico & explorador de colaboración**\>. O bien, para ir directamente a la **página Explorador** , use <https://security.microsoft.com/threatexplorer>.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 de inteligencia de amenazas

Esta característica solo está disponible si tienes una suscripción Office 365 E5 o el complemento de inteligencia de amenazas. Para obtener más información, vea la Office 365 Enterprise de producto de E5.

Al activar esta característica, podrás incorporar datos de Microsoft Defender para Office 365 en Microsoft 365 Defender para llevar a cabo una investigación de seguridad completa en buzones de correo y dispositivos Office 365 Windows.

> [!NOTE]
> Tendrás que tener la licencia adecuada para habilitar esta característica.

Para recibir la integración contextual de dispositivos en Office 365 inteligencia de amenazas, deberás habilitar la configuración de Defender for Endpoint en el panel Seguridad & cumplimiento.

### <a name="incidents"></a>Incidentes

Use la lista Incidentes (esto también se denomina Investigaciones) para ver una lista de incidentes de seguridad piloto. Los incidentes se usan para realizar un seguimiento de amenazas, como mensajes de correo electrónico sospechosos, y para llevar a cabo una investigación y corrección adicionales.

:::image type="content" source="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png" alt-text="La lista de incidentes de amenazas actuales en Office 365" lightbox="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png":::

Para ver la lista de incidentes actuales de su organización en el portal <https://security.microsoft.com>de Microsoft 365 Defender en , vaya a **Incidentes & alertas incidentes**\>. O bien, para ir directamente a la **página Incidentes** , use <https://security.microsoft.com/incidents>.

:::image type="content" source="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png" alt-text="La página Revisar del Centro de seguridad & cumplimiento" lightbox="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png":::

### <a name="attack-simulation-training"></a>Aprendizaje de simulación de ataque

Usa el entrenamiento de simulación de ataques para configurar y ejecutar ciberataques realistas en tu organización e identificar personas vulnerables antes de que un ataque cibernético real afecte a tu empresa. Para obtener más información, consulta [Simular un ataque de phishing](attack-simulation-training.md).

Para ver y usar esta característica en el portal de Microsoft 365 Defender, <https://security.microsoft.com>vaya **a Correo electrónico & aprendizaje** de simulación **collaborationAttack** > . O bien, para ir directamente a la página **de aprendizaje de simulación de** ataque, use <https://security.microsoft.com/attacksimulator?viewid=overview>.

### <a name="automated-investigation-and-response"></a>Investigación y respuesta de amenazas

Use las capacidades de investigación y respuesta automatizadas (AIR) para ahorrar tiempo y esfuerzo correlacionando contenido, dispositivos y personas en riesgo de amenazas en su organización. Los procesos de AIR pueden comenzar cuando se desencadenan determinadas alertas o cuando se inician por el equipo de operaciones de seguridad. Para obtener más información, vea [automated investigation and response in Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Widgets de inteligencia de amenazas

Como parte de la oferta del Plan 2 de Microsoft Defender para Office 365, los analistas de seguridad pueden revisar detalles sobre una amenaza conocida. Esto es útil para determinar si hay medidas o pasos preventivos adicionales que se pueden tomar para mantener a los usuarios seguros.

:::image type="content" source="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png" alt-text="El panel Tendencias de seguridad que muestra información sobre las amenazas recientes" lightbox="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png":::

## <a name="how-do-we-get-these-capabilities"></a>¿Cómo se obtienen estas capacidades?

Microsoft 365 capacidades de investigación y respuesta de amenazas se incluyen en Microsoft Defender para Office 365 Plan 2, que se incluye en Enterprise E5 o como complemento de determinadas suscripciones. Para obtener más información, vea [Defender for Office 365 Plan 1 y Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Permisos y roles necesarios

Microsoft Defender para Office 365 usa control de acceso basado en roles. Los permisos se asignan a través de determinados roles Azure Active Directory, el Centro de administración de Microsoft 365 o el portal Microsoft 365 Defender usuario.

> [!TIP]
> Aunque algunos roles, como el administrador de seguridad, se pueden asignar en el portal de Microsoft 365 Defender, considere la posibilidad de usar el Centro de administración de Microsoft 365 o Azure Active Directory en su lugar. Para obtener información sobre roles, grupos de roles y permisos, vea los siguientes recursos:
>
> - [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
> - [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)

|Actividad|Roles y permisos|
|---|---|
|Usar el panel de & de administración de vulnerabilidades (o el nuevo panel [de seguridad](security-dashboard.md)) <p> Ver información sobre amenazas recientes o actuales|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad**</li><li>**Lector de seguridad**</li></ul> <p> Estos roles se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>).|
|Usar [el Explorador (y detecciones en tiempo real)](threat-explorer.md) para analizar amenazas|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad**</li><li>**Lector de seguridad**</li></ul> <p> Estos roles se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>).|
|Ver incidentes (también denominados Investigaciones) <p> Agregar mensajes de correo electrónico a un incidente|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad**</li><li>**Lector de seguridad**</li></ul> <p> Estos roles se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>).|
|Desencadenar acciones de correo electrónico en un incidente <p> Buscar y eliminar mensajes de correo electrónico sospechosos|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad** más el **rol Buscar y** purgar</li></ul> <p> Los **roles Administrador global** y **Administrador de** seguridad se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>). <p> El **rol Buscar y purgar** debe asignarse en los roles de colaboración **&** correo electrónico en el portal de Microsoft 36 Defender (<https://security.microsoft.com>).|
|Integrar Microsoft Defender para Office 365 Plan 2 con Microsoft Defender para endpoint <p> Integrar Microsoft Defender para Office 365 Plan 2 con un servidor SIEM|El rol **Administrador global o** **administrador de** seguridad asignado Azure Active Directory (<https://portal.azure.com>) o el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>). <p> --- **más** --- <p> Un rol adecuado asignado en aplicaciones adicionales (como [Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/user-roles) o el servidor SIEM).|

## <a name="next-steps"></a>Siguientes pasos

- [Más información sobre los rastreadores de amenazas: nuevos y notables](threat-trackers.md)
- [Buscar e investigar el correo electrónico malintencionado que se entregó (Office 365 de amenazas y respuesta)](investigate-malicious-email-that-was-delivered.md)
- [Integrar Office 365 investigación y respuesta de amenazas con Microsoft Defender para endpoint](integrate-office-365-ti-with-mde.md)
- [Simular un ataque de suplantación de identidad](attack-simulation-training.md)
