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
ms.openlocfilehash: 39d6bc975ecd4b49ae29705c0b52ab154801a8e6
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588209"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Plan de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá

En este artículo se incluyen las principales recomendaciones del equipo de Cybersecurity de Microsoft para implementar las funciones de seguridad para proteger el entorno de Microsoft 365. Este artículo se ha adaptado desde una sesión de Encendemiento de Microsoft: [proteja a microsoft 365 como un Cybersecurity Pro: principales prioridades para los primeros 30 días, 90 días más allá](https://www.youtube.com/watch?v=luignzNyR-o). Esta sesión fue desarrollada y presentada por Mark Simos y Matt Kemelhar, Enterprise Cybersecurity Architects.

En este artículo:

- [Resultados del plan de desarrollo](security-roadmap.md#Roadmap)

- [30 días: ganada rapidez eficaz](security-roadmap.md#Thirdaydays)

- [90 días: protecciones mejoradas](security-roadmap.md#Ninetydays)

- [Más allá](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>Resultados del plan de desarrollo
<a name="Roadmap"> </a>

Estas recomendaciones de plan de desarrollo se almacenan en tres fases en un orden lógico con los siguientes objetivos.

|||
|:-----|:-----|
| |Resultados
|30 días|Configuración rápida:  <br/> * Protecciones de administración básicas  <br/> * Registro y análisis  <br/> * Protecciones de identidad básicas  <br/> Configuración de inquilino  <br/>  Preparar las partes interesadas|
|90 días|Protecciones avanzadas:  <br/> * Cuentas de administrador  <br/>  * Cuentas de usuario de datos &amp;  <br/>  Visibilidad del cumplimiento, la amenaza y las necesidades de los usuarios  <br/>  Adaptación e implementación de directivas y protecciones predeterminadas|
|Más allá|Ajustar y refinar directivas y controles clave  <br/> Ampliar las protecciones a las dependencias locales  <br/> Integración con procesos de seguridad y negocios (legal, amenaza interna, etc.)|



## <a name="30-days--powerful-quick-wins"></a>30 días: ganada rapidez eficaz
<a name="Thirdaydays"> </a>

Estas tareas pueden realizarse rápidamente y tienen un impacto menor para los usuarios.

|||
|:-----|:-----|
|Área|Tareas|
|Administración de seguridad|* Compruebe la puntuación segura y tome nota del resultado actual ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Active el registro de auditoría para Office 365. Consulte [Buscar en el registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).  <br/> * [Configure Microsoft 365 para aumentar la seguridad](tenant-wide-setup-for-increased-security.md) .  <br/>  * Revise de forma regular los paneles e informes en el centro de seguridad y la seguridad de aplicaciones de nube de Microsoft 365.|
|Protección contra amenazas|[Conecte microsoft 365 a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) para iniciar la supervisión con las directivas de detección de amenazas predeterminadas para comportamientos anómalos. Se necesitan siete días para crear una línea base para la detección de anomalías.  <br><br/>  Implemente la protección de las cuentas de administrador:  <br/> * Use cuentas de administrador dedicadas para la actividad de administración.  <br/>  * Exigir multi-factor Authentication (MFA) para las cuentas de administrador.  <br/>  * Use un [dispositivo de Windows 10 muy seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) para la actividad de administración.|
|Administración de identidad y acceso|* [Habilitar Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> * Para entornos de identidades federadas, exija la seguridad de la cuenta (longitud de la contraseña, antigüedad, complejidad, etc.).|
|Protección de la información| Revise los ejemplos de recomendaciones de protección de la información. La protección de la información requiere coordinación en toda la organización. Empiece con estos recursos:  <br/> * [Office 365 Information Protection para RGPD](https://aka.ms/o365gdpr) <br/> * [Proteger los archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md) (incluidos el uso compartido, la clasificación, la prevención de pérdida de datos y Azure Information Protection)|

## <a name="90-days--enhanced-protections"></a>90 días: protecciones mejoradas
<a name="Ninetydays"> </a>

Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero aumentan considerablemente el nivel de seguridad.

|||
|:-----|:-----|
|Área|Task|
|Administración de seguridad|* Compruebe la puntuación segura de las acciones recomendadas para su entorno ( [https://securescore.office.com](https://securescore.office.com) ).  <br/>  * Continúe revisando regularmente los paneles e informes en las herramientas Microsoft 365 Security Center, Cloud App Security y SIEM. <br/> * Busque e implemente actualizaciones de software. <br/> * Realice simulaciones de ataque para ataques de contraseñas de "Spear-phishing", aerosoles y de fuerza bruta mediante [simulador de ataques](attack-simulator.md) (incluido en la [inteligencia sobre amenazas de Office 365](office-365-ti.md)).  <br/> * Busque el riesgo de uso compartido mediante la revisión de los informes integrados en Cloud App Security (en la pestaña investigar). <br/> * Compruebe la [puntuación de cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/compliance-score) para revisar el estado de las regulaciones que se aplican a su organización (como RGPD, NIST 800-171).|
|Protección contra amenazas| Implementar protecciones mejoradas para cuentas de administrador: <br/> * Configurar [estaciones de trabajo de acceso privilegiado](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (huellas) para la actividad de administración. <br/> * Configurar [Azure ad privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure). <br/> * Configurar una herramienta de administración de eventos e información de seguridad (SIEM) para recopilar datos de registro de Office 365, Cloud App Security y otros servicios, incluido AD FS. El registro de auditoría almacena los datos de solo 90 días. La captura de estos datos en la herramienta SIEM le permite almacenar datos durante un período más largo.|
|Administración de identidad y acceso|* Habilitar y aplicar MFA para todos los usuarios. <br/> * Implementar un conjunto de [acceso condicional y directivas relacionadas](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Protección de la información| Adaptar e implementar directivas de protección de la información. Estos recursos incluyen ejemplos: <br/> * [Office 365 Information Protection para RGPD](https://aka.ms/o365gdpr) <br/> * [Proteger los archivos y sitios de SharePoint Online](secure-sharepoint-online-sites-and-files.md) <br/> <br> Use las directivas de prevención de pérdida de datos y las herramientas de supervisión en Microsoft 365 para los datos almacenados en Microsoft 365 (en lugar de Cloud App Security). <br><br>Use Cloud App Security con Microsoft 365 para obtener características de alerta avanzadas (distintas de la prevención de pérdida de datos).|

## <a name="beyond"></a>Más allá
<a name="Beyond"> </a>

Se trata de medidas de seguridad importantes que se basan en el trabajo anterior.

|||
|:-----|:-----|
|Área|Task|
|Administración de seguridad|* Continuar la planeación de las acciones siguientes mediante calificación segura ( [https://securescore.office.com](https://securescore.office.com) ). <br/> * Continúe revisando regularmente los paneles e informes en las herramientas Microsoft 365 Security Center, Cloud App Security y SIEM. <br/> * Seguir buscando e implementando actualizaciones de software. <br/> * Integre la exhibición de documentos electrónicos en sus procesos de respuesta legal y amenaza.|
|Protección contra amenazas|* Implemente el [acceso con privilegios seguros](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (Spa) para los componentes de identidad de local (AD, AD FS). <br/> * Use Cloud App Security para supervisar las amenazas internas. <br/> * Descubra el uso de SaaS de TI mediante Cloud App Security.|
|Administración de identidad y acceso|* Refinar las directivas y los procesos operativos. <br/> * Use Azure AD Identity Protection para identificar amenazas de Insider.|
|Protección de la información| Refinar directivas de protección de la información: <br/> * Etiquetas de confidencialidad de Microsoft 365 y Office 365, prevención de pérdida de datos (DLP) o Azure Information Protection. <br/> * Directivas y alertas de Cloud App Security.|

Consulte también: [Cómo mitigar la cyberattacks rápida como Petya y WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/).
