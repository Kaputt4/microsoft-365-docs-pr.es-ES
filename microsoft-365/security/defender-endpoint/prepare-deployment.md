---
title: Prepare su cuenta de Microsoft Defender para punto de conexión
description: Preparar la aprobación de las partes interesadas, las escalas de tiempo, las consideraciones del entorno y el orden de adopción para implementar Microsoft Defender para endpoint
keywords: implementar, preparar, partes interesadas, escala de tiempo, entorno, punto de conexión, servidor, administración, adopción
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2fe6fa150967973cce58dec9cc47c625305462fc
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611140"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Prepare su cuenta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La implementación de Defender for Endpoint es un proceso de tres fases:

|![fase de implementación: preparar.](images/phase-diagrams/prepare.png)<br>Fase 1: Preparación|[![fase de implementación: configuración](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: Configuración](production-deployment.md)|[![fase de implementación: incorporación](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fase 3: Incorporación](onboarding.md)|
|---|---|---|
|*¡Estás aquí!*|||

Actualmente se encuentra en la fase de preparación.

La preparación es clave para cualquier implementación correcta. En este artículo, se le guiará sobre los puntos que tendrá que tener en cuenta mientras se prepara para implementar Defender for Endpoint.

## <a name="stakeholders-and-approval"></a>Partes interesadas y aprobación

La siguiente sección sirve para identificar a todas las partes interesadas que participan en el proyecto y necesitan aprobar, revisar o mantenerse informados.

Agregue partes interesadas a la tabla siguiente según corresponda para su organización.

- SO = Aprobar proyecto
- R = Revisar este proyecto y proporcionar entrada
- I = Informado de este proyecto

<br>

****

|Nombre|Rol|Acción|
|---|---|---|
|Escriba el nombre y el correo electrónico|**Director de seguridad de la información (CISO)** Un representante ejecutivo que actúa como patrocinador dentro de *la organización para la nueva implementación de tecnología.*|SO|
|Escriba el nombre y el correo electrónico|Jefe del Centro de operaciones **de Ciberdefensa (CDOC)** Un representante del equipo CDOC encargado de definir cómo se alinea este cambio con los procesos del equipo de operaciones de *seguridad de clientes.*|SO|
|Escriba el nombre y el correo electrónico|**Arquitecto de** seguridad Un representante del equipo de seguridad encargado de definir cómo se alinea este cambio con la arquitectura *de seguridad principal de la organización.*|R|
|Escriba el nombre y el correo electrónico|**Workplace Architect** Un representante del equipo de IT encargado de definir cómo se alinea este cambio con la arquitectura básica del lugar de *trabajo de la organización.*|R|
|Escriba el nombre y el correo electrónico|**Analista de** seguridad Un representante del equipo de CDOC que puede proporcionar información sobre las capacidades de detección, la experiencia del usuario y la utilidad general de este cambio desde una perspectiva *de operaciones de seguridad.*|I|
||||

## <a name="environment"></a>Entorno

Esta sección se usa para garantizar que las partes interesadas entiendan profundamente su entorno, lo que ayudará a identificar posibles dependencias o cambios necesarios en tecnologías o procesos.

<br>

****

|Qué|Descripción|
|---|---|
|Recuento de extremos|Recuento total de puntos de conexión por sistema operativo.|
|Recuento de servidores|Recuento total de servidores por versión del sistema operativo.|
|Motor de administración|Nombre y versión del motor de administración (por ejemplo, System Center Configuration Manager rama actual 1803).|
|Distribución de CDOC|Estructura CDOC de alto nivel (por ejemplo, nivel 1 subcontratado a Contoso, nivel 2 y nivel 3 internamente distribuidos en Europa y Asia).|
|Información de seguridad y evento (SIEM)|Tecnología SIEM en uso.|
|||

## <a name="role-based-access-control"></a>Control de acceso basado en roles

Microsoft recomienda usar el concepto de privilegios mínimos. Defender for Endpoint aprovecha roles integrados dentro de Azure Active Directory. Microsoft recomienda [revisar los diferentes roles disponibles](/azure/active-directory/roles/permissions-reference) y elegir el adecuado para resolver sus necesidades para cada persona de esta aplicación. Es posible que algunos roles deba aplicarse temporalmente y quitarse una vez completada la implementación.

<br>

****

|Personas|Funciones|Rol de Azure AD (si es necesario)|Asignar a|
|---|---|---|---|
|Administrador de seguridad||||
|Analista de seguridad||||
|Administrador de extremos||||
|Administrador de infraestructura||||
|Propietario/interesado de la empresa||||
|

Microsoft recomienda usar [Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) administrar los roles para proporcionar auditoría, control y revisión de acceso adicionales para los usuarios con permisos de directorio.

Defender for Endpoint admite dos formas de administrar permisos:

- **Administración de permisos básicos:** establezca los permisos en acceso completo o de solo lectura. En el caso de los usuarios de administración de permisos básicos con el rol Administrador de Globa o Administrador de seguridad en Azure Active Directory tienen acceso completo mientras que el rol lector de seguridad tiene acceso de solo lectura.

- Control de acceso basado en roles **(RBAC):** establezca permisos granulares definiendo roles, asignando grupos de usuarios de Azure AD a los roles y concediendo a los grupos de usuarios acceso a grupos de dispositivos. Para obtener más información. vea [Manage portal access using role-based access control](rbac.md).

Microsoft recomienda aprovechar RBAC para asegurarse de que solo los usuarios que tienen una justificación empresarial puedan acceder a Defender for Endpoint.

Puede encontrar detalles sobre las directrices de permisos aquí: [Crear roles y asignar el](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)rol a un Azure Active Directory grupo .

La siguiente tabla de ejemplo sirve para identificar la estructura del Centro de operaciones de Cyber Defense en su entorno que le ayudará a determinar la estructura RBAC necesaria para su entorno.

<br>

****

|Nivel|Descripción|Permiso necesario|
|---|---|---|
|Nivel 1|**Equipo de operaciones de seguridad local/equipo de TI** <p> Este equipo normalmente realiza una triage e investiga las alertas contenidas en su geolocalización y escala al nivel 2 en los casos en los que se requiere una corrección activa.||
|Nivel 2|**Equipo de operaciones de seguridad regional** <p> Este equipo puede ver todos los dispositivos de su región y realizar acciones de corrección.|Ver datos|
|Nivel 3|**Equipo de operaciones de seguridad global** <p> Este equipo está formado por expertos en seguridad y está autorizado a ver y realizar todas las acciones desde el portal.|Ver datos <p> Investigación de alertas Acciones de corrección activas <p> Investigación de alertas Acciones de corrección activas <p> Administrar la configuración del sistema del portal <p> Administrar la configuración de seguridad|
||||

## <a name="adoption-order"></a>Orden de adopción

En muchos casos, las organizaciones tendrán los productos de seguridad de puntos de conexión existentes en su lugar. El mínimo mínimo que cada organización debería haber sido una solución antivirus. Pero en algunos casos, una organización también podría haber implantado una EDR ya.

Históricamente, la sustitución de cualquier solución de seguridad que solía ser intensiva en tiempo y difícil de lograr debido a los estrechos enlaces a las dependencias de la infraestructura y la capa de aplicaciones. Sin embargo, dado que Defender para endpoint está integrado en el sistema operativo, ahora es fácil reemplazar soluciones de terceros.

Elija el componente de Defender para endpoint que se va a usar y quite los que no se aplican. En la tabla siguiente se indica el orden que Microsoft recomienda para la habilitación del conjunto de seguridad de puntos de conexión.

<br>

****

|Componente|Descripción|Clasificación de orden de adopción|
|---|---|---|
|Respuesta de & de detección de puntos de conexión (EDR)|Las capacidades de defender para detección y respuesta de puntos de conexión endpoint proporcionan detecciones avanzadas de ataques que son casi en tiempo real y que pueden actuar. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. <p> [Aprende más.](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)|1|
|Administración & vulnerabilidad de amenazas (TVM)|Threat & Vulnerability Management es un componente de Microsoft Defender para endpoint y proporciona a los administradores de seguridad y a los equipos de operaciones de seguridad un valor único, incluidos: <ul><li>Información de detección y respuesta de puntos de conexión (EDR) en tiempo real correlacionada con las vulnerabilidades de los puntos de conexión.</li><li>Contexto de vulnerabilidad de dispositivos inestimable durante las investigaciones de incidentes</li><li>Procesos de corrección integrados a Microsoft Intune y Microsoft System Center Configuration Manager</li></ul> <p> [Más información](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).|2|
|Protección de última generación (NGP)|Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona protección de última generación para escritorios, equipos portátiles y servidores. El Antivirus de Microsoft Defender incluye: <ul><li>Protección en la nube para detectar y bloquear amenazas nuevas y emergentes de forma casi instantánea. Junto con Intelligent Security Graph y el aprendizaje automático, la protección en la nube forma parte de las tecnologías de última generación utilizadas por el Antivirus de Microsoft Defender.</li><li>Análisis siempre continuo mediante la supervisión avanzada del comportamiento de procesos y archivos y otras heurísticas (también conocida como "protección en tiempo real").</li><li>Actualizaciones de protección dedicadas basadas en el aprendizaje automático, análisis de macrodatos realizados de forma automatizada y por personas, e investigación exhaustiva de la resistencia ante amenazas.</li></ul> <p> [Más información](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).|3 |
|Reducción de superficie de ataque (ASR)|Las capacidades de reducción de superficie de ataque en Microsoft Defender para endpoint ayudan a proteger los dispositivos y aplicaciones de la organización frente a amenazas nuevas y emergentes. <br> [Aprende más.](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)|4 |
|Auto Investigation & Remediation (AIR)|Microsoft Defender para endpoint usa investigaciones automatizadas para reducir significativamente el volumen de alertas que deben investigarse individualmente. La característica de investigación automatizada aprovecha varios algoritmos de inspección y procesos usados por analistas (como playbooks) para examinar alertas y tomar medidas de corrección inmediatas para resolver infracciones. Esto reduce considerablemente el volumen de alertas, lo que facilita que los expertos de operaciones de seguridad puedan centrarse en amenazas más complejas y otras iniciativas de alto valor. <p> [Aprende más.](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)|No aplicable|
|Expertos en amenazas de Microsoft (MTE)|Expertos en amenazas de Microsoft es un servicio de búsqueda administrado que proporciona a los Centros de operaciones de seguridad (SOC) supervisión y análisis de nivel de experto para ayudarles a garantizar que las amenazas críticas en sus entornos únicos no se pierden. <p> [Aprende más.](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)|No aplicable|

## <a name="next-step"></a>Paso siguiente

![Fase 2: Configuración.](images/setup.png) <br> [Fase 2: Configuración](production-deployment.md)

Configurar Microsoft Defender para la implementación de puntos de conexión.
