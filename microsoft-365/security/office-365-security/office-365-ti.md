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
description: Obtenga información sobre las funcionalidades de investigación y respuesta de amenazas en Microsoft Defender para Office 365 Plan.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c972a42730f4d21b73227a8b8a9900223109d590
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972043"
---
# <a name="threat-investigation-and-response"></a>Investigación y respuesta de amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplicación**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

Las funcionalidades de investigación y respuesta de amenazas en [Microsoft Defender para Office 365](defender-for-office-365.md) ayudar a los analistas y administradores de seguridad a proteger la Microsoft 365 de su organización para los usuarios empresariales mediante:

- Facilitando la identificación, supervisión y comprensión de los ciberataques.
- Ayudar a abordar rápidamente las amenazas en Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.
- Proporcionar información y conocimientos para ayudar a las operaciones de seguridad a evitar ciberataques contra su organización.
- Emplear la [investigación y la respuesta automatizadas en Office 365](automated-investigation-response-office.md) para amenazas críticas basadas en correo electrónico.

Las funcionalidades de investigación y respuesta de amenazas proporcionan información sobre las amenazas y las acciones de respuesta relacionadas que están disponibles en el portal de Microsoft 365 Defender. Estas conclusiones pueden ayudar al equipo de seguridad de su organización a proteger a los usuarios frente a ataques basados en correo electrónico o archivos. Las funcionalidades ayudan a supervisar las señales y recopilar datos de varios orígenes, como la actividad del usuario, la autenticación, el correo electrónico, los equipos en peligro y los incidentes de seguridad. Los responsables de la toma de decisiones empresariales y el equipo de operaciones de seguridad pueden usar esta información para comprender y responder a las amenazas contra su organización y proteger su propiedad intelectual.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Familiarizarse con las herramientas de investigación y respuesta de amenazas

Las funcionalidades de investigación y respuesta de amenazas en el portal <https://security.microsoft.com> de Microsoft 365 Defender en son un conjunto de flujos de trabajo de herramientas y respuesta que incluyen:

- [Explorador](#explorer)
- [Incidentes](#incidents)
- [Aprendizaje de simulación de ataque](attack-simulation-training.md)
- [Investigación y respuesta automatizadas](automated-investigation-response-office.md)

### <a name="explorer"></a>Explorador

Use [el Explorador (y las detecciones en tiempo real)](threat-explorer.md) para analizar amenazas, ver el volumen de ataques a lo largo del tiempo y analizar datos por familias de amenazas, infraestructura de atacantes, etc. El Explorador (también conocido como Explorador de amenazas) es el punto de partida para el flujo de trabajo de investigación de cualquier analista de seguridad.

:::image type="content" source="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png" alt-text="Página Explorador de amenazas" lightbox="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png":::

Para ver y usar este informe en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya al **Explorador** de **colaboración** \> & correo electrónico. O bien, para ir directamente a la página **Explorador** , use <https://security.microsoft.com/threatexplorer>.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 conexión de Inteligencia sobre amenazas

Esta característica solo está disponible si tiene una suscripción Office 365 E5 activa o el complemento Threat Intelligence. Para obtener más información, consulte la página del producto Office 365 Enterprise E5.

Al activar esta característica, podrá incorporar datos de Microsoft Defender para Office 365 en Microsoft 365 Defender para llevar a cabo una investigación de seguridad completa en Office 365 buzones y dispositivos Windows.

> [!NOTE]
> Tendrá que tener la licencia adecuada para habilitar esta característica.

Para recibir la integración contextual de dispositivos en Office 365 Threat Intelligence, deberá habilitar la configuración de Defender para punto de conexión en el panel Seguridad & cumplimiento.

### <a name="incidents"></a>Incidentes

Use la lista Incidentes (esto también se denomina Investigaciones) para ver una lista de incidentes de seguridad de vuelos. Los incidentes se usan para realizar un seguimiento de amenazas, como mensajes de correo electrónico sospechosos, y para realizar más investigaciones y correcciones.

:::image type="content" source="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png" alt-text="Lista de incidentes de amenazas actuales en Office 365" lightbox="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png":::

Para ver la lista de incidentes actuales de su organización en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Incidentes & alertas** \> **Incidentes**. O bien, para ir directamente a la página **Incidentes** , use <https://security.microsoft.com/incidents>.

:::image type="content" source="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png" alt-text="La página Revisar del Centro de cumplimiento de seguridad &" lightbox="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png":::

### <a name="attack-simulation-training"></a>Aprendizaje de simulación de ataque

Use el entrenamiento de simulación de ataques para configurar y ejecutar ciberataques realistas en su organización e identificar a las personas vulnerables antes de que un ciberataque real afecte a su negocio. Para obtener más información, consulte [Simulación de un ataque de suplantación de identidad (phishing).](attack-simulation-training.md)

Para ver y usar esta característica en el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico & entrenamiento** de **simulación de collaborationAttack** > . O bien, para ir directamente a la página **de entrenamiento Simulación de ataque** , use <https://security.microsoft.com/attacksimulator?viewid=overview>.

### <a name="automated-investigation-and-response"></a>Investigación y respuesta de amenazas

Use funcionalidades automatizadas de investigación y respuesta (AIR) para ahorrar tiempo y esfuerzo en la correlación de contenido, dispositivos y personas en riesgo de amenazas en su organización. Los procesos de AIR pueden comenzar siempre que se desencadenen ciertas alertas o cuando lo inicie el equipo de operaciones de seguridad. Para más información, consulte [investigación y respuesta automatizadas en Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Widgets de inteligencia sobre amenazas

Como parte de la oferta Microsoft Defender para Office 365 Plan 2, los analistas de seguridad pueden revisar los detalles sobre una amenaza conocida. Esto es útil para determinar si hay medidas o pasos preventivos adicionales que se pueden tomar para mantener a los usuarios seguros.

:::image type="content" source="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png" alt-text="El panel Tendencias de seguridad muestra información sobre amenazas recientes" lightbox="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png":::

## <a name="how-do-we-get-these-capabilities"></a>¿Cómo obtenemos estas funcionalidades?

Microsoft 365 funcionalidades de investigación y respuesta de amenazas se incluyen en Microsoft Defender para Office 365 Plan 2, que se incluye en Enterprise E5 o como complemento para determinadas suscripciones. Para más información, consulte [Defender para Office 365 Plan 1 y Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Permisos y roles necesarios

Microsoft Defender para Office 365 usa el control de acceso basado en rol. Los permisos se asignan a través de determinados roles en Azure Active Directory, el Centro de administración de Microsoft 365 o el portal de Microsoft 365 Defender.

> [!TIP]
> Aunque algunos roles, como Administrador de seguridad, se pueden asignar en el portal de Microsoft 365 Defender, considere la posibilidad de usar el Centro de administración de Microsoft 365 o Azure Active Directory en su lugar. Para obtener información sobre roles, grupos de roles y permisos, consulte los siguientes recursos:
>
> - [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md)
> - [Azure AD roles integrados](/azure/active-directory/roles/permissions-reference)

|Actividad|Roles y permisos|
|---|---|
|Use el panel Administración de vulnerabilidades de & amenazas (o el nuevo [panel seguridad).](security-dashboard.md) <p> Visualización de información sobre amenazas recientes o actuales|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad**</li><li>**Lector de seguridad**</li></ul> <p> Estos roles se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>).|
|Uso [del Explorador (y detecciones en tiempo real)](threat-explorer.md) para analizar amenazas|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad**</li><li>**Lector de seguridad**</li></ul> <p> Estos roles se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>).|
|Ver incidentes (también conocidos como investigaciones) <p> Adición de mensajes de correo electrónico a un incidente|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad**</li><li>**Lector de seguridad**</li></ul> <p> Estos roles se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>).|
|Desencadenar acciones de correo electrónico en un incidente <p> Búsqueda y eliminación de mensajes de correo electrónico sospechosos|Uno de los siguientes: <ul><li>**Administrador global**</li><li>**Administrador de seguridad** más el rol **Buscar y purgar**</li></ul> <p> Los roles **administrador global** y **administrador de seguridad** se pueden asignar en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>). <p> El rol **Buscar y purgar** debe asignarse en el **correo electrónico & roles de colaboración** en el portal de Microsoft 36 Defender (<https://security.microsoft.com>).|
|Integración de Microsoft Defender para Office 365 Plan 2 con Microsoft Defender para punto de conexión <p> Integración de Microsoft Defender para Office 365 Plan 2 con un servidor SIEM|El **rol Administrador global** o **Administrador de seguridad** asignado en Azure Active Directory (<https://portal.azure.com>) o en el Centro de administración de Microsoft 365 (<https://admin.microsoft.com>). <p> --- **Más** --- <p> Un rol adecuado asignado en aplicaciones adicionales (como [Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/user-roles) o el servidor SIEM).|

## <a name="next-steps"></a>Siguientes pasos

- [Más información sobre los seguimientos de amenazas: nuevos y destacados](threat-trackers.md)
- [Búsqueda e investigación de correo electrónico malintencionado que se entregó (Office 365 investigación y respuesta de amenazas)](investigate-malicious-email-that-was-delivered.md)
- [Integración de Office 365 investigación y respuesta de amenazas con Microsoft Defender para punto de conexión](integrate-office-365-ti-with-mde.md)
- [Simulación de un ataque de suplantación de identidad](attack-simulation-training.md)
