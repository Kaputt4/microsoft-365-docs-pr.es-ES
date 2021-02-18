---
title: 'Mapa de ruta de seguridad de Microsoft 365: principales prioridades'
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Recomendaciones principales del equipo de ciberseguridad de Microsoft para implementar capacidades de seguridad para proteger su entorno de Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7d376eb7266975dc7582b83bfd4fa5e930ccea4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288174"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Mapa de ruta de seguridad: principales prioridades para los primeros 30 días, 90 días y posteriores

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se incluyen las principales recomendaciones del equipo de ciberseguridad de Microsoft para implementar capacidades de seguridad para proteger su entorno de Microsoft 365. Este artículo se ha adaptado a partir de una sesión de Microsoft Ignite: Proteger Microsoft 365 como un profesional de ciberseguridad: principales prioridades para los primeros [30 días, 90](https://www.youtube.com/watch?v=luignzNyR-o)días y posteriores. Esta sesión fue desarrollada y presentada por Mark Simos y Matt Kemelhar, arquitectos de ciberseguridad empresariales.

En este artículo:

- [Resultados de la guía básica](security-roadmap.md#Roadmap)
- [30 días: potentes ganancias rápidas](security-roadmap.md#Thirdaydays)
- [90 días: protecciones mejoradas](security-roadmap.md#Ninetydays)
- [Más allá](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados de la guía básica
<a name="Roadmap"> </a>

Estas recomendaciones de plan de desarrollo se disponen por fases en tres fases en un orden lógico con los siguientes objetivos.

****

|Período de tiempo|Resultados|
|---|---|
|30 días|Configuración rápida: <ul><li>Protecciones básicas de administración.</li><li>Registro y análisis.</li><li>Protecciones de identidad básicas.</li></ul> <p> Configuración del espacio empresarial. <p> Preparar a las partes interesadas.|
|90 días|Protecciones avanzadas: <ul><li>Cuentas de administrador.</li><li>Datos y cuentas de usuario.</li></ul> <p> Visibilidad de las necesidades de cumplimiento, amenazas y usuarios. <p> Adaptar e implementar directivas y protecciones predeterminadas.|
|Más allá|Ajustar y refinar directivas y controles clave. <p> Ampliar las protecciones a las dependencias locales. <p> Integración con procesos empresariales y de seguridad (legales, amenazas de insider, etc.).|
|

## <a name="30-days--powerful-quick-wins"></a>30 días: potentes ganancias rápidas
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.

****

|Área|Tareas|
|---|---|
|Administración de seguridad|<ul><li>Compruebe la puntuación de seguridad y tome nota de la puntuación actual ( <https://securescore.office.com> ).</li><li>Active el registro de auditoría para Office 365. Vea [Buscar en el registro de auditoría.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[Configurar Microsoft 365 para aumentar la seguridad.](tenant-wide-setup-for-increased-security.md)</li><li>Revise periódicamente los paneles e informes en el Centro de seguridad de Microsoft 365 y Cloud App Security.</li></ul>|
|Protección contra amenazas|[Conecte Microsoft 365 a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar la supervisión con las directivas de detección de amenazas predeterminadas para comportamientos anómalos. Se necesitan siete días para crear una línea base para la detección de anomalías. <p>  Implementar la protección para cuentas de administrador:<ul><li>Usar cuentas de administrador dedicadas para la actividad de administrador.</li><li>Aplicar la autenticación multifactor (MFA) para las cuentas de administrador.</li><li>Usa un [dispositivo Windows 10 altamente seguro para](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) la actividad de administrador.</li></ul>|
|Administración de identidad y acceso|<ul><li>[Habilite Azure Active Directory Identity Protection.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)</li><li>Para entornos de identidad federada, exija la seguridad de la cuenta (longitud de contraseña, antigüedad, complejidad, etc.).</li></ul>|
|Protección de la información|Revise las recomendaciones de protección de la información de ejemplo. La protección de la información requiere coordinación en toda la organización. Empiece con estos recursos:<ul><li>[Information Protection de Office 365 para RGPD](https://aka.ms/o365gdpr)</li><li>[Configurar Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md) (incluye uso compartido, clasificación, prevención de pérdida de datos y Azure Information Protection)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 días: protecciones mejoradas
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad.

****

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Compruebe la puntuación de seguridad para las acciones recomendadas para su entorno ( <https://securescore.office.com> ).</li><li>Continúe revisando periódicamente los paneles e informes del Centro de seguridad de Microsoft 365, Cloud App Security y las herramientas SIEM.</li><li>Busque e implemente actualizaciones de software.</li><li>Realice simulaciones de ataques para ataques de suplantación de identidad (phishing), espionaje de contraseñas y contraseñas por fuerza bruta mediante el simulador de [ataques](attack-simulator.md) (incluido con inteligencia de amenazas de [Office 365).](office-365-ti.md)</li><li>Busque el riesgo de uso compartido revisando los informes integrados en Cloud App Security (en la pestaña Investigar).</li><li>Compruebe [el Administrador de](../../compliance/compliance-manager.md) cumplimiento para revisar el estado de las normativas que se aplican a su organización (como RGPD, NIST 800-171).</li></ul>|
|Protección contra amenazas|Implementar protecciones mejoradas para cuentas de administrador: <ul><li>Configurar [estaciones de trabajo de acceso con privilegios](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) para la actividad de administración.</li><li>Configurar [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configurar una herramienta de administración de eventos e información de seguridad (SIEM) para recopilar datos de registro de Office 365, Cloud App Security y otros servicios, incluido AD FS. El registro de auditoría almacena datos solo durante 90 días. Capturar estos datos en la herramienta SIEM te permite almacenar datos durante un período más largo.</li></ul>|
|Administración de identidad y acceso|<ul><li>Habilitar y aplicar MFA para todos los usuarios.</li><li>Implementar un conjunto de [directivas relacionadas y de acceso condicional.](microsoft-365-policies-configurations.md)</li></ul>|
|Protección de la información| Adaptar e implementar directivas de protección de la información. Estos recursos incluyen ejemplos: <ul><li>[Information Protection de Office 365 para RGPD](https://aka.ms/o365gdpr)</li><li>[Configurar Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Usar directivas de prevención de pérdida de datos y herramientas de supervisión en Microsoft 365 para los datos almacenados en Microsoft 365 (en lugar de Cloud App Security). <p> Usar Cloud App Security con Microsoft 365 para características de alerta avanzadas (que no son la prevención de pérdida de datos).|
|

## <a name="beyond"></a>Más allá
<a name="Beyond"> </a>

Estas son medidas de seguridad importantes que se basa en el trabajo anterior.

****

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Siga planeando las siguientes acciones mediante puntuación segura ( <https://securescore.office.com> ).</li><li>Continúe revisando periódicamente los paneles e informes del Centro de seguridad de Microsoft 365, Cloud App Security y las herramientas SIEM.</li><li>Siga buscando e implementando actualizaciones de software.</li><li>Integre la exhibición de documentos electrónicos en los procesos de respuesta legal y de amenazas.</li></ul>|
|Protección contra amenazas|<ul><li>Implementar [acceso con privilegios seguros](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) para componentes de identidad locales (AD, AD FS).</li><li>Usa Cloud App Security para supervisar las amenazas internas.</li><li>Descubra el uso de SaaS de IT en la sombra mediante Cloud App Security.</li></ul>|
|Administración de identidad y acceso|<ul><li>Refinar directivas y procesos operativos.</li><li>Use Azure AD Identity Protection para identificar amenazas internas.</li></ul>|
|Protección de la información|Refinar directivas de protección de la información: <ul><li>Etiquetas de confidencialidad de Microsoft 365 y Office 365 y prevención de pérdida de datos (DLP) o Azure Information Protection.</li><li>Alertas y directivas de Cloud App Security.</li></ul>|
|

Vea también: [Cómo mitigar ciberataques rápidos como Petya y WannaCrypt.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
