---
title: Prepare su cuenta de Microsoft Defender para punto de conexión
description: Preparar la aprobación de las partes interesadas, las escalas de tiempo, las consideraciones del entorno y el orden de adopción para implementar Microsoft Defender para punto de conexión
keywords: implementar, preparar, partes interesadas, escala de tiempo, entorno, punto de conexión, servidor, administración, adopción
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-endpointprotect
- m365solution-scenario
- highpri
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 5511570e9714b7abe6b289421b517052639a277e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628145"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Prepare su cuenta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La implementación de Defender para punto de conexión es un proceso de tres fases:

|![fase de implementación: preparación.](images/phase-diagrams/prepare.png)<br>Fase 1: Preparación|[![fase de implementación: configuración](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: Configuración](production-deployment.md)|[![fase de implementación: incorporación](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Fase 3: Incorporación](onboarding.md)|
|---|---|---|
|*¡Estás aquí!*|||

Actualmente se encuentra en la fase de preparación.

La preparación es clave para cualquier implementación correcta. En este artículo, se le guiará sobre los puntos que deberá tener en cuenta a medida que se prepare para implementar Defender para punto de conexión.

## <a name="stakeholders-and-approval"></a>Partes interesadas y aprobación

La sección siguiente sirve para identificar a todas las partes interesadas que participan en el proyecto y necesitan aprobar, revisar o mantenerse informados.

Agregue las partes interesadas a la tabla siguiente según corresponda para su organización.

- SO = Aprobar proyecto
- R = Revisar este proyecto y proporcionar entrada
- I = Informado de este proyecto

<br>

****

|Nombre|Rol|Acción|
|---|---|---|
|Escriba el nombre y el correo electrónico.|**Director de Seguridad de la Información (CISO)** *Representante ejecutivo que actúa como patrocinador dentro de la organización para la nueva implementación de tecnología.*|SO|
|Escriba el nombre y el correo electrónico.|**Jefe del Centro de operaciones de ciberdefensa (CDOC)** *Representante del equipo de CDOC encargado de definir cómo se alinea este cambio con los procesos del equipo de operaciones de seguridad de los clientes.*|SO|
|Escriba el nombre y el correo electrónico.|**Arquitecto de seguridad** *Un representante del equipo de seguridad encargado de definir cómo se alinea este cambio con la arquitectura de seguridad principal de la organización.*|R|
|Escriba el nombre y el correo electrónico.|**Workplace Architect** *Un representante del equipo de TI encargado de definir cómo se alinea este cambio con la arquitectura básica del área de trabajo de la organización.*|R|
|Escriba el nombre y el correo electrónico.|**Analista de seguridad** *Un representante del equipo de CDOC que puede proporcionar información sobre las funcionalidades de detección, la experiencia del usuario y la utilidad general de este cambio desde la perspectiva de las operaciones de seguridad.*|I|
||||

## <a name="environment"></a>Entorno

Esta sección se usa para garantizar que las partes interesadas entiendan profundamente el entorno, lo que ayudará a identificar posibles dependencias o cambios necesarios en las tecnologías o procesos.

<br>

****

|Qué|Descripción|
|---|---|
|Recuento de puntos de conexión|Recuento total de puntos de conexión por sistema operativo.|
|Recuento de servidores|Recuento total de servidores por versión del sistema operativo.|
|Motor de administración|Nombre y versión del motor de administración (por ejemplo, System Center Configuration Manager rama actual 1803).|
|Distribución de CDOC|Estructura CDOC de alto nivel (por ejemplo, nivel 1 subcontratado a Contoso, nivel 2 y nivel 3 distribuidos internamente en Europa y Asia).|
|Información de seguridad y eventos (SIEM)|Tecnología SIEM en uso.|
|||

## <a name="role-based-access-control"></a>Control de acceso basado en roles

Microsoft recomienda usar el concepto de mínimo privilegio. Defender para punto de conexión aprovecha los roles integrados en Azure Active Directory. Microsoft recomienda [revisar los diferentes roles disponibles](/azure/active-directory/roles/permissions-reference) y elegir el adecuado para resolver las necesidades de cada persona de esta aplicación. Es posible que algunos roles deban aplicarse temporalmente y quitarse una vez completada la implementación.

<br>

****

|Personas|Funciones|Rol de Azure AD (si es necesario)|Asignar a|
|---|---|---|---|
|Administrador de seguridad||||
|Analista de seguridad||||
|Administrador de puntos de conexión||||
|Administrador de infraestructura||||
|Propietario de la empresa/Parte interesada||||
|

Microsoft recomienda usar [Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) para administrar los roles a fin de proporcionar auditoría, control y revisión de acceso adicionales para los usuarios con permisos de directorio.

Defender for Endpoint admite dos maneras de administrar permisos:

- **Administración básica de permisos**: establezca los permisos en acceso completo o de solo lectura. Los usuarios con roles de administrador global o administrador de seguridad en Azure Active Directory tienen acceso completo. El rol Lector de seguridad tiene acceso de solo lectura y no concede acceso para ver el inventario de máquinas o dispositivos.

- **Control de acceso basado en rol (RBAC):** establezca permisos granulares mediante la definición de roles, la asignación de grupos de usuarios de Azure AD a los roles y la concesión de acceso a los grupos de usuarios a los grupos de dispositivos. Para obtener más información, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

Microsoft recomienda aprovechar RBAC para asegurarse de que solo los usuarios que tengan una justificación empresarial puedan acceder a Defender para punto de conexión.

Puede encontrar detalles sobre las directrices de permisos aquí: [Crear roles y asignar el rol a un grupo de Azure Active Directory](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group).

La tabla de ejemplo siguiente sirve para identificar la estructura del Centro de operaciones de Cyber Defense en el entorno que le ayudará a determinar la estructura de RBAC necesaria para su entorno.

<br>

****

|Nivel|Descripción|Permiso requerido|
|---|---|---|
|Nivel 1|**Equipo de operaciones de seguridad local/equipo de TI** <p> Este equipo suele evaluar e investigar las alertas contenidas en su geolocalización y se escala al nivel 2 en los casos en los que se requiere una corrección activa.||
|Nivel 2|**Equipo de operaciones de seguridad regional** <p> Este equipo puede ver todos los dispositivos de su región y realizar acciones de corrección.|Ver datos|
|Nivel 3|**Equipo de operaciones de seguridad global** <p> Este equipo está formado por expertos en seguridad y está autorizado para ver y realizar todas las acciones desde el portal.|Ver datos <p> Investigación de alertas Acciones de corrección activas <p> Investigación de alertas Acciones de corrección activas <p> Administración de la configuración del sistema del portal <p> Administrar la configuración de seguridad|
||||

## <a name="adoption-order"></a>Orden de adopción

En muchos casos, las organizaciones tendrán productos de seguridad de punto de conexión existentes. El mínimo de todas las organizaciones debería haber sido una solución antivirus. Pero en algunos casos, es posible que una organización también haya implantado ya una solución EDR.

Históricamente, reemplazar cualquier solución de seguridad solía ser mucho tiempo y difícil de lograr debido a los enlaces estrechos en la capa de aplicación y las dependencias de infraestructura. Sin embargo, dado que Defender para punto de conexión está integrado en el sistema operativo, reemplazar soluciones de terceros ahora es fácil de lograr.

Elija el componente de Defender para punto de conexión que se va a usar y quite los que no se aplican. La siguiente tabla indica el orden que Microsoft recomienda sobre cómo se debería habilitar el conjunto de seguridad de puntos de conexión.

<br>

****

|Componente|Descripción|Orden de adopción|
|---|---|---|
|Detección y respuesta en puntos de conexión (EDR)|Las funcionalidades de detección y respuesta de puntos de conexión de Defender para punto de conexión proporcionan detecciones avanzadas de ataques casi en tiempo real y accionables. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. <p> [Obtenga más información](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response).|1|
|Administración de vulnerabilidades de Microsoft Defender (MDVM)|La administración de vulnerabilidades de Defender es un componente de Microsoft Defender para punto de conexión y proporciona a los administradores de seguridad y a los equipos de operaciones de seguridad un valor único, entre los que se incluyen: <ul><li>Información de detección y respuesta en puntos de conexión (EDR) en tiempo real correlacionada con las vulnerabilidades de los puntos de conexión.</li><li>Contexto de vulnerabilidad de dispositivo invaluable durante las investigaciones de incidentes</li><li>Procesos de corrección integrados mediante Microsoft Intune y Microsoft System Center Configuration Manager</li></ul> <p> [Obtenga más información](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).|2|
|Protección de última generación (NGP)|Microsoft Defender Antivirus es una solución antimalware integrada que proporciona protección de última generación para equipos de escritorio, equipos portátiles y servidores. El Antivirus de Microsoft Defender incluye: <ul><li>Protección en la nube para detectar y bloquear amenazas nuevas y emergentes de forma casi instantánea. Junto con Intelligent Security Graph y el aprendizaje automático, la protección en la nube forma parte de las tecnologías de última generación utilizadas por el Antivirus de Microsoft Defender.</li><li>Análisis siempre activado mediante la supervisión avanzada del comportamiento de archivos y procesos y otras heurísticas (también conocida como "protección en tiempo real").</li><li>Actualizaciones de protección dedicadas basadas en el aprendizaje automático, el análisis de macrodatos humanos y automatizados, y la investigación en profundidad de la resistencia a amenazas.</li></ul> <p> [Obtenga más información](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).|3|
|Reducción de la superficie expuesta a ataques (ASR)|Las funcionalidades de reducción de superficie expuesta a ataques en Microsoft Defender para punto de conexión ayudan a proteger los dispositivos y las aplicaciones de la organización frente a amenazas nuevas y emergentes. <br> [Obtenga más información](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction).|4|
|Corrección de & de investigación automática (AIR)|Microsoft Defender para punto de conexión usa investigaciones automatizadas para reducir significativamente el volumen de alertas que deben investigarse individualmente. La característica de investigación automatizada aprovecha varios algoritmos de inspección y los procesos utilizados por los analistas (como cuadernos de estrategias) para examinar alertas y tomar medidas de corrección inmediatas para resolver infracciones. Esto reduce considerablemente el volumen de alertas, lo que facilita que los expertos de operaciones de seguridad puedan centrarse en amenazas más complejas y otras iniciativas de alto valor. <p> [Obtenga más información](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).|No aplicable|
|Expertos en amenazas de Microsoft (MTE)|Expertos en amenazas de Microsoft es un servicio de búsqueda administrado que proporciona centros de operaciones de seguridad (SOC) con supervisión y análisis de nivel experto para ayudarles a garantizar que las amenazas críticas en sus entornos únicos no se pierdan. <p> [Obtenga más información](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts).|No aplicable|

## <a name="next-step"></a>Paso siguiente

![Fase 2: Configuración.](images/setup.png) <br> [Fase 2: Configuración](production-deployment.md)

Configurar Microsoft Defender para punto de conexión implementación.
