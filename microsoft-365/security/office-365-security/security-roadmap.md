---
title: Plan de seguridad 365 de Microsoft-principales prioridades
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Las principales recomendaciones del equipo de Cybersecurity de Microsoft para implementar las funciones de seguridad para proteger el entorno de Microsoft 365. '
ms.openlocfilehash: 452ce2a303f02cadfcdcbe12310f2538d33a24e7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615809"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Plan de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se incluyen las principales recomendaciones del equipo de Cybersecurity de Microsoft para implementar las funciones de seguridad para proteger el entorno de Microsoft 365. Este artículo se ha adaptado desde una sesión de Encendemiento de Microsoft: [proteja a microsoft 365 como un Cybersecurity Pro: principales prioridades para los primeros 30 días, 90 días más allá](https://www.youtube.com/watch?v=luignzNyR-o). Esta sesión fue desarrollada y presentada por Mark Simos y Matt Kemelhar, Enterprise Cybersecurity Architects.

En este artículo:

- [Resultados del plan de desarrollo](security-roadmap.md#Roadmap)
- [30 días: ganada rapidez eficaz](security-roadmap.md#Thirdaydays)
- [90 días: protecciones mejoradas](security-roadmap.md#Ninetydays)
- [Más allá](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados del plan de desarrollo
<a name="Roadmap"> </a>

Estas recomendaciones de plan de desarrollo se almacenan en tres fases en un orden lógico con los siguientes objetivos.

****

|Período de tiempo|Resultados|
|---|---|
|30 días|Configuración rápida: <ul><li>Protecciones básicas de administración.</li><li>Registro y análisis.</li><li>Protecciones de identidad básicas.</li></ul> <p> Configuración del espacio empresarial. <p> Prepare las partes interesadas.|
|90 días|Protecciones avanzadas: <ul><li>Cuentas de administrador.</li><li>Datos y cuentas de usuario.</li></ul> <p> Visibilidad del cumplimiento, la amenaza y las necesidades de los usuarios. <p> Adapte y implemente directivas y protecciones predeterminadas.|
|Más allá|Ajustar y refinar directivas y controles clave. <p> Ampliar las protecciones a las dependencias locales. <p> Integración con procesos de seguridad y negocios (legal, amenaza interna, etc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 días: ganada rapidez eficaz
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.

****

|Área|Tareas|
|---|---|
|Administración de seguridad|<ul><li>Compruebe la puntuación segura y tome nota del resultado actual ( <https://securescore.office.com> ).</li><li>Active el registro de auditoría para Office 365. Consulte [Buscar en el registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configure Microsoft 365 para aumentar la seguridad](tenant-wide-setup-for-increased-security.md).</li><li>Revise de forma regular los paneles e informes en el centro de seguridad y la seguridad de aplicaciones de nube de Microsoft 365.</li></ul>|
|Protección contra amenazas|[Conecte microsoft 365 a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar la supervisión con las directivas de detección de amenazas predeterminadas para comportamientos anómalos. Se necesitan siete días para crear una línea base para la detección de anomalías. <p>  Implemente la protección de las cuentas de administrador:<ul><li>Use cuentas de administrador dedicadas para la actividad de administración.</li><li>Exigir la autenticación multifactor (MFA) para las cuentas de administrador.</li><li>Use un [dispositivo de Windows 10 muy seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) para la actividad de administración.</li></ul>|
|Administración de identidad y acceso|<ul><li>[Habilitar Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</li><li>Para entornos de identidades federadas, exija la seguridad de la cuenta (longitud de la contraseña, antigüedad, complejidad, etc.).</li></ul>|
|Protección de la información|Revise los ejemplos de recomendaciones de protección de la información. La protección de la información requiere coordinación en toda la organización. Empiece con estos recursos:<ul><li>[Information Protection de Office 365 para RGPD](https://aka.ms/o365gdpr)</li><li>[Configurar Microsoft Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md) (incluye uso compartido, clasificación, prevención de pérdida de datos y Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 días: protecciones mejoradas
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad.

****

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Compruebe la puntuación segura de las acciones recomendadas para su entorno ( <https://securescore.office.com> ).</li><li>Continúe revisando regularmente los paneles e informes en el centro de seguridad 365 de Microsoft, la seguridad de aplicaciones en la nube y las herramientas SIEM.</li><li>Busque e implemente actualizaciones de software.</li><li>Realizar simulaciones de ataque para ataques de suplantación de identidad (phishing), rociado por contraseña y fuerza bruta mediante [simulador de ataques](attack-simulator.md) (incluido en la [inteligencia sobre amenazas de Office 365](office-365-ti.md)).</li><li>Busque el riesgo de uso compartido mediante la revisión de los informes integrados en Cloud App Security (en la pestaña investigar).</li><li>Compruebe el [Administrador de cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) para revisar el estado de las regulaciones que se aplican a su organización (como RGPD, NIST 800-171).</li></ul>|
|Protección contra amenazas|Implementar protecciones mejoradas para cuentas de administrador: <ul><li>Configure las [estaciones de acceso con privilegios](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (huellas) para la actividad de administración.</li><li>Configurar [Azure ad privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configure una herramienta de administración de eventos e información de seguridad (SIEM) para recopilar datos de registro de Office 365, Cloud App Security y otros servicios, incluido AD FS. El registro de auditoría almacena los datos de solo 90 días. La captura de estos datos en la herramienta SIEM le permite almacenar datos durante un período más largo.</li></ul>|
|Administración de identidad y acceso|<ul><li>Habilitar y aplicar MFA para todos los usuarios.</li><li>Implementar un conjunto de [acceso condicional y directivas relacionadas](microsoft-365-policies-configurations.md).</li></ul>|
|Protección de la información| Adaptar e implementar directivas de protección de la información. Estos recursos incluyen ejemplos: <ul><li>[Information Protection de Office 365 para RGPD](https://aka.ms/o365gdpr)</li><li>[Configurar Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Use las directivas de prevención de pérdida de datos y las herramientas de supervisión en Microsoft 365 para los datos almacenados en Microsoft 365 (en lugar de Cloud App Security). <p> Use Cloud App Security con Microsoft 365 para obtener características de alerta avanzadas (distintas de la prevención de pérdida de datos).|
|

## <a name="beyond"></a>Más allá
<a name="Beyond"> </a>

Se trata de medidas de seguridad importantes que se basan en el trabajo anterior.

****

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Continúe planificando las acciones siguientes mediante la calificación segura ( <https://securescore.office.com> ).</li><li>Continúe revisando regularmente los paneles e informes en el centro de seguridad 365 de Microsoft, la seguridad de aplicaciones en la nube y las herramientas SIEM.</li><li>Seguir buscando e implementando actualizaciones de software.</li><li>Integre la exhibición de documentos electrónicos en sus procesos de respuesta legal y amenaza.</li></ul>|
|Protección contra amenazas|<ul><li>Implemente el [acceso con privilegios seguros](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) para los componentes de identidad de local (AD, AD FS).</li><li>Use Cloud App Security para supervisar las amenazas de Insider.</li><li>Descubra el uso de SaaS de TI mediante Cloud App Security.</li></ul>|
|Administración de identidad y acceso|<ul><li>Refinar las directivas y los procesos operativos.</li><li>Use Azure AD Identity Protection para identificar las amenazas internas.</li></ul>|
|Protección de la información|Refinar directivas de protección de la información: <ul><li>Microsoft 365 y Office 365 las etiquetas de confidencialidad y prevención de pérdida de datos (DLP), o Azure Information Protection.</li><li>Directivas y alertas de Cloud App Security.</li></ul>|
|

Consulte también: [Cómo mitigar la cyberattacks rápida como Petya y WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
