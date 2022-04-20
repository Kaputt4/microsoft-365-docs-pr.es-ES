---
title: 'Microsoft 365 hoja de ruta de seguridad: prioridades principales'
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 08/20/2021
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Recomendaciones principales del equipo de ciberseguridad de Microsoft para implementar funcionalidades de seguridad para proteger el entorno de Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e6174da5a9cbac779c147fb0ea091080bf4338a
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64945437"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Hoja de ruta de seguridad: prioridades principales para los primeros 30 días, 90 días y posteriores

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se incluyen las principales recomendaciones del equipo de ciberseguridad de Microsoft para implementar funcionalidades de seguridad para proteger el entorno de Microsoft 365. Este artículo está adaptado a partir de una sesión de Microsoft Ignite: [Microsoft 365 segura como un profesional de ciberseguridad: prioridades principales para los primeros 30 días, 90 días y posteriores](https://www.youtube.com/watch?v=luignzNyR-o). Esta sesión fue desarrollada y presentada por Mark Simos y Matt Kemelhar, Enterprise Cybersecurity Architects.

En este artículo:

- [Resultados de la hoja de ruta](security-roadmap.md#Roadmap)
- [30 días: potentes victorias rápidas](security-roadmap.md#Thirdaydays)
- [90 días: protecciones mejoradas](security-roadmap.md#Ninetydays)
- [Más allá](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados de la hoja de ruta
<a name="Roadmap"> </a>

Estas recomendaciones de hoja de ruta se almacenan provisionalmente en tres fases en un orden lógico con los siguientes objetivos.

|Período de tiempo|Resultados|
|---|---|
|30 días|Configuración rápida: <ul><li>Protecciones básicas para administradores.</li><li>Registro y análisis.</li><li>Protecciones de identidad básicas.</li></ul> <p> Configuración del inquilino. <p> Preparar a las partes interesadas.|
|90 días|Protecciones avanzadas: <ul><li>Cuentas de administrador.</li><li>Cuentas de datos y de usuario.</li></ul> <p> Visibilidad del cumplimiento, las amenazas y las necesidades del usuario. <p> Adaptar e implementar directivas y protecciones predeterminadas.|
|Más allá|Ajuste y refine los controles y directivas clave. <p> Amplíe las protecciones a las dependencias locales. <p> Integración con procesos empresariales y de seguridad (legales, amenazas internas, etc.).|

## <a name="30-days--powerful-quick-wins"></a>30 días: potentes victorias rápidas
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.

|Área|Tareas|
|---|---|
|Administración de seguridad|<ul><li>Compruebe La puntuación de seguridad y tome nota de la puntuación actual (<https://security.microsoft.com/securescore>).</li><li>Active el registro de auditoría para Office 365. Consulte [Búsqueda en el registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configure Microsoft 365 para aumentar la seguridad](tenant-wide-setup-for-increased-security.md).</li><li>Revise periódicamente los paneles e informes en el portal de Microsoft 365 Defender y Defender for Cloud Apps.</li></ul>|
|Protección contra amenazas|[Conectar Microsoft 365 a Microsoft Defender for Cloud Apps](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar la supervisión mediante las directivas de detección de amenazas predeterminadas para comportamientos anómalo. La detección de anomalías tarda siete días en crear una línea base. <p>  Implemente la protección para las cuentas de administrador:<ul><li>Use cuentas de administrador dedicadas para la actividad de administrador.</li><li>Aplicar la autenticación multifactor (MFA) para las cuentas de administrador.</li><li>Use un [dispositivo de Windows altamente seguro](/windows-hardware/design/device-experiences/oem-highly-secure) para la actividad de administración.</li></ul>|
|Administración de identidad y acceso|<ul><li>[Habilite Azure Active Directory Identity Protection](/azure/active-directory/active-directory-identityprotection-enable).</li><li>Para entornos de identidad federada, aplique la seguridad de la cuenta (longitud de la contraseña, antigüedad, complejidad, etc.).</li></ul>|
|Protección de la información|Revise las recomendaciones de protección de la información de ejemplo. La protección de la información requiere coordinación en toda la organización. Empiece con estos recursos:<ul><li>[Information Protection de Office 365 para RGPD](/compliance/regulatory/gdpr)</li><li>[Configuración de Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md) (incluido el uso compartido, la clasificación, la prevención de pérdida de datos de Microsoft Purview y Azure Information Protection)</li></ul>|

## <a name="90-days--enhanced-protections"></a>90 días: protecciones mejoradas
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad.

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Compruebe La puntuación de seguridad para ver las acciones recomendadas para su entorno (<https://security.microsoft.com/securescore>).</li><li>Continúe revisando periódicamente los paneles e informes en el portal de Microsoft 365 Defender, las aplicaciones de Defender for Cloud y las herramientas SIEM.</li><li>Busque e implemente actualizaciones de software.</li><li>Realice simulaciones de ataque para ataques de phishing de lanza, difusión de contraseñas y ataques de contraseña por fuerza bruta mediante [el entrenamiento de simulación de ataques](attack-simulation-training.md) (incluido con [Office 365 Inteligencia sobre amenazas](office-365-ti.md).</li><li>Busque el riesgo de uso compartido revisando los informes integrados en Defender for Cloud Apps (en la pestaña Investigar).</li><li>Compruebe [el Administrador de cumplimiento](../../compliance/compliance-manager.md) para revisar el estado de las regulaciones que se aplican a su organización (como RGPD, NIST 800-171).</li></ul>|
|Protección contra amenazas|Implemente protecciones mejoradas para las cuentas de administrador: <ul><li>Configure [estaciones de trabajo de acceso con privilegios](/security/compass/privileged-access-devices) (PAW) para la actividad de administración.</li><li>Configurar [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configure una herramienta de administración de eventos e información de seguridad (SIEM) para recopilar datos de registro de Office 365, aplicaciones de Defender for Cloud y otros servicios, incluido AD FS. El registro de auditoría almacena los datos durante solo 90 días. La captura de estos datos en la herramienta SIEM permite almacenar datos durante un período más largo.</li></ul>|
|Administración de identidad y acceso|<ul><li>Habilite y aplique MFA para todos los usuarios.</li><li>Implemente un conjunto de [directivas relacionadas y de acceso condicional](microsoft-365-policies-configurations.md).</li></ul>|
|Protección de la información| Adaptar e implementar directivas de protección de la información. Estos recursos incluyen ejemplos: <ul><li>[Information Protection de Office 365 para RGPD](/compliance/regulatory/gdpr)</li><li>[Configurar Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Use las directivas de prevención de pérdida de datos y las herramientas de supervisión en Microsoft Purview para los datos almacenados en Microsoft 365 (en lugar de Defender for Cloud Apps). <p> Use Defender for Cloud Apps con Microsoft 365 para las características avanzadas de alertas (que no sean la prevención de pérdida de datos).|

## <a name="beyond"></a>Más allá
<a name="Beyond"> </a>

Estas son medidas de seguridad importantes que se basan en el trabajo anterior.

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Continúe planeando las siguientes acciones mediante puntuación segura (<https://security.microsoft.com/securescore>).</li><li>Continúe revisando periódicamente los paneles e informes en el portal de Microsoft 365 Defender, las aplicaciones de Defender for Cloud y las herramientas SIEM.</li><li>Continúe buscando e implementando actualizaciones de software.</li><li>Integre eDiscovery en los procesos legales y de respuesta a amenazas.</li></ul>|
|Protección contra amenazas|<ul><li>Implemente [el acceso con privilegios seguros](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) para los componentes de identidad locales (AD, AD FS).</li><li>Use Defender for Cloud Apps para supervisar las amenazas internas.</li><li>Descubra el uso de SaaS de TI alternativo mediante aplicaciones Defender for Cloud.</li></ul>|
|Administración de identidad y acceso|<ul><li>Refinar las directivas y los procesos operativos.</li><li>Use Azure AD Identity Protection para identificar amenazas internas.</li></ul>|
|Protección de la información|Refinar las directivas de protección de la información: <ul><li>Microsoft 365 y Office 365 etiquetas de confidencialidad y prevención de pérdida de datos (DLP) o Azure Information Protection.</li><li>Defender for Cloud directivas y alertas de Aplicaciones.</li></ul>|

Vea también: [Cómo mitigar ciberataques rápidos como Petya y WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
