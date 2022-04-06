---
title: 'Microsoft 365 plan de seguridad: prioridades principales'
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
description: Recomendaciones principales del equipo de ciberseguridad de Microsoft para implementar funcionalidades de seguridad para proteger su Microsoft 365 de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ffdcb8e6f1a3cb167ec3ce8d7ac5a9225b05356
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683239"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Hoja de ruta de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se incluyen las recomendaciones principales del equipo de ciberseguridad de Microsoft para implementar capacidades de seguridad para proteger su entorno Microsoft 365 seguridad. Este artículo se ha adaptado a partir de una sesión de Microsoft Ignite: Secure [Microsoft 365 like a cybersecurity pro: Top priorities for the first 30 days, 90 days, and beyond](https://www.youtube.com/watch?v=luignzNyR-o). Esta sesión fue desarrollada y presentada por Mark Simos y Matt Kemelhar, Enterprise Cybersecurity Architects.

En este artículo:

- [Resultados de la guía básica](security-roadmap.md#Roadmap)
- [30 días: ganancias rápidas eficaces](security-roadmap.md#Thirdaydays)
- [90 días: protecciones mejoradas](security-roadmap.md#Ninetydays)
- [Más allá](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados de la guía básica
<a name="Roadmap"> </a>

Estas recomendaciones de guía básica se programan en tres fases en un orden lógico con los siguientes objetivos.

|Marco de tiempo|Resultados|
|---|---|
|30 días|Configuración rápida: <ul><li>Protecciones de administración básicas.</li><li>Registro y análisis.</li><li>Protecciones básicas de identidad.</li></ul> <p> Configuración del espacio empresarial. <p> Preparar a las partes interesadas.|
|90 días|Protecciones avanzadas: <ul><li>Cuentas de administrador.</li><li>Datos y cuentas de usuario.</li></ul> <p> Visibilidad de las necesidades de cumplimiento, amenazas y usuarios. <p> Adaptar e implementar directivas y protecciones predeterminadas.|
|Más allá|Ajustar y refinar los controles y directivas clave. <p> Extender las protecciones a dependencias locales. <p> Integre con procesos empresariales y de seguridad (legales, amenazas de insider, etc.).|

## <a name="30-days--powerful-quick-wins"></a>30 días: ganancias rápidas eficaces
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.

|Área|Tareas|
|---|---|
|Administración de seguridad|<ul><li>Comprueba Puntuación segura y toma nota de la puntuación actual (<https://security.microsoft.com/securescore>).</li><li>Active el registro de auditoría para Office 365. Consulte [Buscar en el registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).</li><li>[Configure Microsoft 365 para aumentar la seguridad](tenant-wide-setup-for-increased-security.md).</li><li>Revise periódicamente los paneles y los informes en el portal de Microsoft 365 Defender y Defender para aplicaciones en la nube.</li></ul>|
|Protección contra amenazas|[Conectar Microsoft 365 a Microsoft Defender para aplicaciones en](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) la nube para iniciar la supervisión mediante las directivas de detección de amenazas predeterminadas para comportamientos anómalos. Se tardan siete días en crear una línea base para la detección de anomalías. <p>  Implementar la protección para cuentas de administrador:<ul><li>Usa cuentas de administrador dedicadas para la actividad de administración.</li><li>Exigir la autenticación multifactor (MFA) para cuentas de administrador.</li><li>Usa un [dispositivo de Windows altamente seguro para](/windows-hardware/design/device-experiences/oem-highly-secure) la actividad de administración.</li></ul>|
|Administración de acceso e identidad  |<ul><li>[Habilite Azure Active Directory de identidad.](/azure/active-directory/active-directory-identityprotection-enable)</li><li>Para entornos de identidad federada, aplique la seguridad de la cuenta (longitud de contraseña, antigüedad, complejidad, etc.).</li></ul>|
|Protección de la información|Revise recomendaciones de protección de información de ejemplo. La protección de la información requiere coordinación en toda la organización. Empiece con estos recursos:<ul><li>[Information Protection de Office 365 para RGPD](/compliance/regulatory/gdpr)</li><li>[Configurar Teams con tres niveles de](../../solutions/configure-teams-three-tiers-protection.md) protección (incluye uso compartido, clasificación, prevención de pérdida de datos y Azure Information Protection)</li></ul>|

## <a name="90-days--enhanced-protections"></a>90 días: protecciones mejoradas
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad.

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Compruebe Puntuación segura para las acciones recomendadas para su entorno (<https://security.microsoft.com/securescore>).</li><li>Continúe revisando periódicamente los paneles y los informes en el portal de Microsoft 365 Defender, Defender para aplicaciones en la nube y herramientas SIEM.</li><li>Busque e implemente actualizaciones de software.</li><li>Realice simulaciones de ataques para ataques de suplantación de identidad (phishing), spray de contraseña y contraseñas de fuerza bruta mediante el entrenamiento de simulación de [ataques (](attack-simulation-training.md)incluido con [Office 365 inteligencia de amenazas).](office-365-ti.md)</li><li>Busque el riesgo de uso compartido revisando los informes integrados en Defender para aplicaciones en la nube (en la pestaña Investigar).</li><li>Compruebe [el Administrador de cumplimiento](../../compliance/compliance-manager.md) para revisar el estado de las normativas que se aplican a su organización (como RGPD, NIST 800-171).</li></ul>|
|Protección contra amenazas|Implementar protecciones mejoradas para cuentas de administrador: <ul><li>Configurar [estaciones de trabajo de acceso privilegiado](/security/compass/privileged-access-devices) (PAW) para la actividad de administración.</li><li>Configure [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</li><li>Configure una herramienta de administración de eventos y información de seguridad (SIEM) para recopilar datos de registro de Office 365, Defender para aplicaciones en la nube y otros servicios, incluido AD FS. El registro de auditoría almacena datos solo durante 90 días. Capturar estos datos en la herramienta SIEM permite almacenar datos durante un período más largo.</li></ul>|
|Administración de acceso e identidad  |<ul><li>Habilitar y aplicar MFA para todos los usuarios.</li><li>Implementar un conjunto de [directivas relacionadas y de acceso condicional](microsoft-365-policies-configurations.md).</li></ul>|
|Protección de la información| Adaptar e implementar directivas de protección de la información. Estos recursos incluyen ejemplos: <ul><li>[Information Protection de Office 365 para RGPD](/compliance/regulatory/gdpr)</li><li>[Configurar Teams con tres niveles de protección](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Usa directivas de prevención de pérdida de datos y herramientas de supervisión en Microsoft 365 para los datos almacenados en Microsoft 365 (en lugar de Defender para aplicaciones en la nube). <p> Usa Defender para aplicaciones en la nube con Microsoft 365 para características avanzadas de alertas (aparte de la prevención de pérdida de datos).|

## <a name="beyond"></a>Más allá
<a name="Beyond"> </a>

Estas son medidas de seguridad importantes que se basa en el trabajo anterior.

|Área|Task|
|---|---|
|Administración de seguridad|<ul><li>Siga planeando las siguientes acciones mediante puntuación segura (<https://security.microsoft.com/securescore>).</li><li>Continúe revisando periódicamente los paneles y los informes en el portal de Microsoft 365 Defender, Defender para aplicaciones en la nube y herramientas SIEM.</li><li>Siga buscando e implementando actualizaciones de software.</li><li>Integre la exhibición de documentos electrónicos en los procesos legales y de respuesta a amenazas.</li></ul>|
|Protección contra amenazas|<ul><li>Implementar [acceso con privilegios seguros](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) para componentes de identidad locales (AD, AD FS).</li><li>Usa Defender para aplicaciones en la nube para supervisar las amenazas internas.</li><li>Descubra el uso de SaaS de TI de sombra mediante Defender para aplicaciones en la nube.</li></ul>|
|Administración de acceso e identidad  |<ul><li>Refinar directivas y procesos operativos.</li><li>Use Azure AD Identity Protection para identificar las amenazas internas.</li></ul>|
|Protección de la información|Refinar directivas de protección de la información: <ul><li>Microsoft 365 y Office 365 de confidencialidad y prevención de pérdida de datos (DLP) o Azure Information Protection.</li><li>Directivas y alertas de Defender para Aplicaciones en la nube.</li></ul>|

Vea también: [Cómo mitigar ataques cibernéticos rápidos como Petya y WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
