---
title: Caso práctico-contoso configura rápidamente una directiva de lenguaje ofensivo para Microsoft Teams, Exchange y Yammer Communications
description: Un caso práctico para contoso y cómo configuran rápidamente una directiva de cumplimiento de comunicaciones para supervisar un lenguaje ofensivo en Microsoft Teams, Exchange Online y Yammer Communications.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 9c20b322d4da0339d7c8711abcee38f19f556423
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289393"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Caso práctico-contoso configura rápidamente una directiva de lenguaje ofensivo para Microsoft Teams, Exchange y Yammer Communications

El cumplimiento de la comunicación en Microsoft 365 ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y actuar en mensajes inapropiados de la organización. Las directivas predefinidas y personalizadas le permiten analizar las comunicaciones internas y externas de las coincidencias de directivas para que puedan examinarlas los revisores designados. Los revisores pueden investigar el correo electrónico explorado, Microsoft Teams, Yammer o las comunicaciones de terceros de la organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen con los estándares de mensajes de la organización.

Contoso Corporation es una organización ficticia que necesita configurar rápidamente una directiva para supervisar el idioma ofensivo. Han estado usando Microsoft 365 principalmente para el correo electrónico, Microsoft Teams y la compatibilidad con Yammer para sus usuarios, pero tienen nuevos requisitos para aplicar la Directiva de la empresa alrededor del acoso del lugar de trabajo. Los administradores de TI de Contoso y los especialistas de cumplimiento tienen un conocimiento básico de los conceptos básicos del trabajo con Microsoft 365 y buscan una guía de un extremo a otro para empezar rápidamente con el cumplimiento de la comunicación.

Este caso práctico cubrirá los conceptos básicos para configurar rápidamente una directiva de cumplimiento de comunicaciones para supervisar las comunicaciones para un lenguaje ofensivo. Esta guía incluye:

- Paso 1: Planeación del cumplimiento de la comunicación
- Paso 2: acceso a la compatibilidad de la comunicación en Microsoft 365
- Paso 3: configurar los requisitos previos y crear una directiva de cumplimiento de la comunicación
- Paso 4: investigación y corrección de alertas

## <a name="step-1-planning-for-communication-compliance"></a>Paso 1: Planeación del cumplimiento de la comunicación

Los administradores de TI de Contoso y los especialistas en línea se han asistido por webinar en línea sobre soluciones de cumplimiento en Microsoft 365 y decidido que las directivas de cumplimiento de comunicaciones les ayudarán a cumplir los requisitos de la Directiva corporativa actualizada para reducir el acoso del lugar de trabajo. Juntos, han desarrollado un plan para crear y habilitar una directiva de cumplimiento de comunicaciones que supervisará el lenguaje ofensivo para los chats enviados en Microsoft Teams, mensajes privados y conversaciones de la comunidad en Yammer y en mensajes de correo electrónico enviados en Exchange Online. Su plan incluye identificación:

- Los administradores de ti que necesitan tener acceso a las características de cumplimiento de comunicaciones.
- Los especialistas en cumplimiento que necesitan crear y administrar directivas de comunicación.
- Los especialistas en cumplimiento y otros compañeros de otros departamentos (recursos humanos, legales, etc.) que necesitan investigar y corregir las alertas de cumplimiento de comunicaciones.
- Los usuarios que estarán en el ámbito de la Directiva de lenguaje ofensivo para la conformidad con la comunicación.

### <a name="licensing"></a>Licencias

El primer paso es confirmar que la licencia de Microsoft 365 de Contoso incluye soporte para la solución de cumplimiento de comunicaciones. Para acceder y usar el cumplimiento de la comunicación, los administradores de TI de Contoso necesitan comprobar que Contoso tiene uno de los siguientes elementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + complemento Microsoft 365 E5 del servicio de administración de riesgos de Insider
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 a3 + complemento de cumplimiento A5 de Microsoft 365
- Suscripción a Microsoft 365 a3 + complemento de administración de riesgos de la A5 del Insider de Microsoft 365
- Suscripción a Microsoft 365 G5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 G5 + complemento de cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 G5 + complemento de administración de riesgos de Insider de Microsoft 365 G5
- Suscripción a Office 365 Enterprise E5 (versión de pago o de prueba)
- Office 365 Enterprise E3 subscription + el complemento Office 365 Advanced Compliance (ya no está disponible para las nuevas suscripciones, vea note)

También deben confirmar que los usuarios incluidos en las directivas de cumplimiento de comunicaciones deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>Office 365 Advanced Compliance ya no se vende como una suscripción independiente. Cuando expiren las suscripciones actuales, los clientes deben pasar a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o más.

Los administradores de TI de Contoso deben seguir estos pasos para comprobar la compatibilidad con licencias de Contoso:

1. Los administradores de ti inician sesión en el **centro de administración de 365 de Microsoft** [( https://admin.microsoft.com) ](https://admin.microsoft.com) y navegan a las licencias de facturación del **centro de administración de Microsoft 365**  >  **Billing**  >  **Licenses**.

2. Aquí se confirma que tienen una de las [Opciones de licencia](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure?view=o365-worldwide#before-you-begin) que incluye la compatibilidad con el cumplimiento de la comunicación.

![Licencias de cumplimiento de comunicaciones](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Permisos para el cumplimiento de la comunicación

Hay cinco grupos de roles usados para configurar los permisos para administrar las características de cumplimiento de comunicaciones. Para que el cumplimiento de la **comunicación** esté disponible como una opción de menú en el centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, los administradores de Contoso tienen asignado el rol de administrador de *cumplimiento de comunicaciones* .

Contoso decide usar el grupo de funciones *cumplimiento de comunicaciones* para asignar todos los administradores de cumplimiento de comunicaciones, analistas, investigadores y visores al grupo. De este modo, es más fácil para contoso empezar rápidamente y se ajusta mejor a sus requisitos de administración de cumplimiento.

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de la comunicación** | Use este grupo de roles para administrar el cumplimiento de la comunicación de su organización en un único grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un único grupo. Este grupo de roles contiene todos los roles de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de la comunicación y es una buena opción para las organizaciones que no necesitan permisos separados definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de comunicaciones y posteriormente para separar los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar las directivas de cumplimiento de la comunicación, la configuración global y las asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver los mensajes de alerta. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que van a actuar como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver las directivas en las que se asignan como revisores, ver los metadatos de los mensajes (no el contenido del mensaje), remitir a otros revisores o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de la comunicación** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de la comunicación. Los usuarios asignados a este grupo de roles pueden ver el contenido y los metadatos de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que van a administrar los informes de comunicación. Los usuarios asignados a este grupo de roles pueden tener acceso a todos los widgets de informes en la página de inicio de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

1. Los administradores de TI de Contoso inician sesión en la página de permisos del **centro de seguridad & cumplimiento de Office 365** [( https://protection.office.com/permissions) ](https://protection.office.com/permissions) usando credenciales para una cuenta de administrador global y seleccionan el vínculo para ver y administrar roles en Microsoft 365.
2. En el **centro de seguridad & cumplimiento**, van a **permisos** y seleccionan el vínculo para ver y administrar roles en Office 365.
3. Los administradores seleccionan el grupo de funciones *cumplimiento de comunicaciones* y, a continuación, seleccionan **Editar Grupo de roles**.
4. Los administradores seleccionan **elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.
5. Seleccionan **Agregar** y, a continuación, seleccionan la casilla para todos los usuarios de Contoso que administrarán las alertas de cumplimiento de comunicación, investigación y revisión.
6. Los administradores seleccionan **Agregar**y, a continuación, selecciona **listo**.
7. Seleccione **Guardar** para agregar usuarios de Contoso al grupo de roles. Seleccione **cerrar** para completar los pasos.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Paso 2: obtener acceso al cumplimiento de la comunicación en Microsoft 365

Después de configurar los permisos para el cumplimiento de la comunicación, los administradores de TI de Contoso y los especialistas en cumplimiento asignados al grupo de funciones de cumplimiento de comunicaciones pueden acceder a la solución de cumplimiento de comunicaciones en Microsoft 365. Los administradores de TI de Contoso y los especialistas de cumplimiento tienen varias formas de obtener acceso al cumplimiento de la comunicación y empezar a crear una nueva Directiva:

- Comenzar directamente desde la solución de cumplimiento de comunicaciones
- Inicio desde el centro de cumplimiento de Microsoft 365
- Inicio desde el catálogo de soluciones de Microsoft 365
- Inicio desde el centro de administración de 365 de Microsoft

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Comenzar directamente desde la solución de cumplimiento de comunicaciones

La forma más rápida de tener acceso a la solución es iniciar sesión directamente en la solución de cumplimiento de la **comunicación** ( <https://compliance.microsoft.com/supervisoryreview> ). Mediante este vínculo, los administradores de TI de Contoso y los especialistas de cumplimiento se dirigirán al panel de información general sobre cumplimiento de comunicaciones, donde podrá revisar rápidamente el estado de las alertas y crear nuevas directivas a partir de las plantillas predefinidas.

![Información general sobre el cumplimiento de comunicaciones](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>Inicio desde el centro de cumplimiento de Microsoft 365

Otra forma sencilla para que los administradores de TI de Contoso y los especialistas en cumplimiento tengan acceso a la solución de cumplimiento de la comunicación es iniciar sesión directamente en el **centro de cumplimiento de Microsoft 365** [ https://compliance.microsoft.com) (](https://compliance.microsoft.com). Después de iniciar sesión, los usuarios simplemente deben seleccionar el control **Mostrar todos** los controles para mostrar todas las soluciones de cumplimiento y, a continuación, seleccionar la solución de cumplimiento de la **comunicación** para empezar.

![Centro de cumplimiento](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>Inicio desde el catálogo de soluciones de Microsoft 365

Los administradores de TI de Contoso y los especialistas de cumplimiento también podrían elegir el acceso a la solución de cumplimiento de comunicaciones seleccionando el catálogo de soluciones de Microsoft 365. Al seleccionar **Catalog** en la sección de **soluciones** del panel de navegación izquierdo en el **centro de cumplimiento de Microsoft 365**, pueden abrir el catálogo de soluciones en el que se enumeran todas las soluciones de cumplimiento de Microsoft 365. Al desplazarse hasta la sección **Administración de riesgos de Insider** , los administradores de TI de Contoso pueden seleccionar el cumplimiento de la comunicación para empezar. Contoso los administradores de ti también deciden usar Mostrar en el control de navegación para anclar la solución de cumplimiento de comunicaciones en el panel de navegación izquierdo para obtener un acceso más rápido cuando inicien sesión en el futuro.

![Catálogo de soluciones](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>Inicio desde el centro de administración de 365 de Microsoft

Para obtener acceso al cumplimiento de la comunicación al empezar desde el centro de administración de Microsoft 365, los administradores de TI de Contoso y los especialistas de cumplimiento inician sesión en el centro de administración de Microsoft 365 [( https://admin.microsoft.com) ](https://admin.microsoft.com) y navegan hasta el cumplimiento del **centro de administración de Microsoft 365**  >  **Compliance**.

![Vínculo de cumplimiento de comunicaciones](../media/communication-compliance-case-compliance-link.png)

Esta acción abre el **centro de seguridad y cumplimiento de Office 365**y debe seleccionar el vínculo al **centro de cumplimiento de Microsoft 365** incluido en el encabezado de la parte superior de la página.

![Centro de seguridad y cumplimiento de Office 365](../media/communication-compliance-case-scc.png)

Una vez en el **centro de cumplimiento de Microsoft 365**, los administradores de TI de Contoso seleccionan **Mostrar todo** para mostrar la lista completa de soluciones de cumplimiento.

![Menú de cumplimiento de comunicaciones](../media/communication-compliance-case-show-all.png)

Después de seleccionar **Mostrar todo**, los administradores de TI de Contoso pueden tener acceso a la solución de cumplimiento de comunicaciones.

![Información general sobre el cumplimiento de comunicaciones](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Paso 3: configurar los requisitos previos y crear una directiva de cumplimiento de la comunicación

Para empezar a trabajar con una directiva de cumplimiento de comunicaciones, hay varios requisitos previos que los administradores de TI de Contoso deben configurar antes de configurar la nueva Directiva para supervisar el lenguaje ofensivo. Una vez completados estos requisitos previos, los administradores de TI de Contoso y los especialistas de cumplimiento pueden configurar los nuevos especialistas de directivas y cumplimiento pueden iniciar la investigación y corregir las alertas generadas.

### <a name="enabling-auditing-in-microsoft-365"></a>Habilitación de la auditoría en Microsoft 365

El cumplimiento de la comunicación requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva de organización definida o cada vez que hay un cambio en una directiva de cumplimiento de la comunicación.

Contoso los administradores de ti revisan y rellenan las [instrucciones paso a paso](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) para activar la auditoría. Después de activar la auditoría, se muestra un mensaje que indica que se está preparando el registro de auditoría y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Los administradores de TI de Contoso solo tienen que realizar esta acción una vez.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configuración del espacio empresarial de Yammer para el modo nativo

El cumplimiento de la comunicación requiere que el inquilino de Yammer para una organización esté en modo nativo para supervisar el lenguaje ofensivo en mensajes privados y conversaciones públicas de la comunidad.

Contoso los administradores de ti Asegúrese de que revisan la información de la información [General del modo nativo de Yammer en el artículo 365 de Microsoft](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) y siga los pasos para ejecutar la herramienta de migración en el artículo [configurar su red de Yammer para el modo nativo para Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode) .

### <a name="setting-up-a-group-for-in-scope-users"></a>Configuración de un grupo para usuarios en el ámbito

Los especialistas de cumplimiento de Contoso quieren agregar todos los usuarios a la Directiva de comunicación que va a supervisar en busca de lenguaje ofensivo. Podrían decidir agregar cada cuenta de usuario a la Directiva por separado, pero han decidido que es mucho más fácil y ahorra tiempo a usar un grupo de distribución de **todos los usuarios** para los usuarios de esta Directiva.

Deben crear un nuevo grupo para incluir a todos los usuarios de Contoso, por lo que deben seguir estos pasos:

1. Contoso administradores de ti inicie sesión en el **centro de administración de 365** de Microsoft [( https://admin.microsoft.com) ](https://admin.microsoft.com) y vaya a la 365 grupos del centro de administración de **Microsoft**)  >  **Groups**  >  **Groups**.
2. Seleccionan **Agregar un grupo** y completan el Asistente para crear un nuevo grupo de *Microsoft 365* o grupo de *distribución*.

    ![Grupos](../media/communication-compliance-case-all-employees.png)

3. Una vez creado el nuevo grupo, tiene que agregar todos los usuarios de Contoso al nuevo grupo. Abren el **centro de administración de Exchange** [ https://outlook.office365.com/ecp) (](https://outlook.office365.com/ecp) y navegan a los grupos de **Exchange admin center**  >  **destinatarios**del centro de administración de Exchange  >  **groups**. Los administradores de TI de Contoso seleccionan el área pertenencia y el nuevo grupo *todos los empleados* que han creado y seleccionan el control **Editar** para agregar todos los usuarios de Contoso al nuevo grupo en el asistente.

    ![Centro de administración de Exchange](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Crear la Directiva para supervisar el lenguaje ofensivo

Una vez completados todos los requisitos previos, los administradores de ti y los especialistas de cumplimiento de Contoso estarán preparados para configurar la Directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo. Mediante la nueva plantilla de directiva de lenguaje ofensivo, la configuración de esta directiva es sencilla y rápida.

1. Los administradores de TI de Contoso y los especialistas de cumplimiento inician sesión en el **centro de cumplimiento de Microsoft 365** y seleccionan cumplimiento de la **comunicación** en el panel de navegación izquierdo. Esta acción abre el panel de **información general** que contiene vínculos rápidos para plantillas de directiva de cumplimiento de comunicaciones. Para elegir la plantilla **supervisar para lenguaje ofensivo** **, seleccione Introducción a la** plantilla.

    ![Plantilla de lenguaje ofensivo de conformidad con la comunicación](../media/communication-compliance-case-template.png)

2. En el Asistente para plantillas de directivas, los administradores de ti y los especialistas de cumplimiento de Contoso trabajan juntos para completar los tres campos obligatorios: **nombre de directiva**, **usuarios o grupos para supervisar**y **revisores**.
3. Dado que el Asistente para directivas ya ha sugerido un nombre para la Directiva, los administradores de ti y los especialistas en cumplimiento deciden mantener el nombre sugerido y centrarse en los campos restantes. Seleccionan el grupo *todos los usuarios* para el campo **usuarios o grupos para supervisar** y seleccionan los especialistas de cumplimiento que deben investigar y corregir las alertas de directiva para el campo **Reviewers** . El último paso para configurar la Directiva e iniciar la recopilación de información de alertas consiste en seleccionar **crear Directiva**.

    ![Asistente para lenguaje ofensivo para cumplimiento de comunicaciones](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Paso 4: investigar y corregir las alertas

Ahora que la Directiva de cumplimiento de la comunicación para supervisar el lenguaje ofensivo está configurada, el siguiente paso para los especialistas de cumplimiento de Contoso será investigar y corregir cualquier alerta generada por la Directiva. La Directiva tardará hasta 24 horas en procesar completamente las comunicaciones en todos los canales de origen de comunicación y para que las alertas aparezcan en el **Panel de alertas**.

Una vez generadas las alertas, los especialistas de cumplimiento de Contoso seguirán las [instrucciones de flujo de trabajo](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-investigate-remediate) para investigar y corregir problemas de idiomas ofensivos.