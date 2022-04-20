---
title: 'Caso práctico: Contoso configura una directiva de texto inapropiada'
description: Un caso práctico para Contoso y cómo configuran rápidamente una directiva de cumplimiento de comunicaciones para supervisar el texto inadecuado en las comunicaciones de Microsoft Teams, Exchange Online y Yammer.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.custom:
- admindeeplinkMAC
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 756c6dfdafb6329fa2df6a4231e9630647d9d11e
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64971933"
---
# <a name="case-study---contoso-quickly-configures-an-inappropriate-text-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Caso práctico: Contoso configura rápidamente una directiva de texto inapropiada para las comunicaciones de Microsoft Teams, Exchange y Yammer

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

El cumplimiento de comunicación de Microsoft Purview ayuda a minimizar los riesgos de comunicación, ya que le ayuda a detectar, capturar y actuar en los mensajes con texto inadecuado en su organización. texto inadecuado puede incluir palabras soeces, amenazas, acoso e imágenes inapropiadas. Las directivas personalizadas y predefinidas le permiten examinar las comunicaciones internas y externas para ver las coincidencias de directivas y que los revisores designados puedan examinarlas. Los revisores pueden investigar el correo electrónico examinado, Microsoft Teams, Yammer o comunicaciones de terceros en su organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen los estándares de mensajes de su organización.

Contoso Corporation es una organización ficticia que necesita configurar rápidamente una directiva para supervisar el texto inadecuado. Han estado usando Microsoft 365 principalmente para el correo electrónico, Microsoft Teams y Yammer soporte técnico para sus usuarios, pero tienen nuevos requisitos para aplicar la directiva de la empresa en torno al acoso en el lugar de trabajo. Los administradores de TI de Contoso y los especialistas en cumplimiento tienen una comprensión básica de los aspectos básicos del trabajo con Microsoft 365 y buscan instrucciones integrales para empezar a trabajar rápidamente con el cumplimiento de las comunicaciones.

En este caso práctico se tratarán los conceptos básicos para configurar rápidamente una directiva de cumplimiento de comunicaciones con el fin de supervisar las comunicaciones en busca de texto inadecuado. Esta guía incluye:

- Paso 1: planificación del cumplimiento de comunicaciones
- Paso 2: Acceso al cumplimiento de la comunicación
- Paso 3: configuración de los requisitos previos y creación de una directiva de cumplimiento de comunicaciones
- Paso 4: investigación y corrección de alertas

## <a name="step-1-planning-for-communication-compliance"></a>Paso 1: Planeamiento del cumplimiento de las comunicaciones

Los administradores de TI y los especialistas en cumplimiento de Contoso asistieron a seminarios web en línea sobre soluciones de cumplimiento en Microsoft 365 y decidieron que las directivas de cumplimiento de comunicaciones les ayudarán a cumplir los requisitos de directivas corporativas actualizados para reducir el acoso en el lugar de trabajo. Trabajando juntos, han desarrollado un plan para crear y habilitar una directiva de cumplimiento de comunicaciones que supervisará el texto inadecuado de los chats enviados en Microsoft Teams, los mensajes privados y las conversaciones de la comunidad en Yammer y en los mensajes de correo electrónico enviados en Exchange Online. Su plan incluye identificar:

- Los administradores de TI que necesitan acceso a las características de cumplimiento de comunicaciones.
- Los especialistas en cumplimiento que necesitan crear y administrar directivas de comunicación.
- Los especialistas en cumplimiento y otros compañeros de otros departamentos (recursos humanos, legales, etc.) que necesitan investigar y corregir las alertas de cumplimiento de comunicaciones.
- Los usuarios que estarán en el ámbito de la directiva de texto inapropiada de cumplimiento de comunicaciones.

### <a name="licensing"></a>Licencias

El primer paso es confirmar que las licencias de Microsoft 365 de Contoso incluyen compatibilidad con la solución de cumplimiento de comunicaciones. Para acceder y usar el cumplimiento de comunicaciones, los administradores de TI de Contoso deben comprobar que Contoso tiene una de las siguientes opciones:

- suscripción Microsoft 365 E5/A5/F5/G5 (versión de pago o de prueba)
- suscripción Microsoft 365 E3/A3/F3/G5 + el complemento de cumplimiento Microsoft 365 E5/A5/F5/G5
- suscripción Microsoft 365 E3/A3/F3/G5 + el complemento Microsoft 365 E5/A5/F5/G5 Insider Risk Management
- Office 365 Enterprise suscripción A5 (versión de pago o de prueba)
- Office 365 A5 suscripción (versión de pago o de prueba)
- Office 365 Enterprise suscripción A3 + el complemento de Cumplimiento avanzado de Office 365 (ya no está disponible para nuevas suscripciones, consulte la nota)

A los usuarios incluidos en las directivas de cumplimiento de comunicaciones se les debe asignar una de las licencias anteriores. Para obtener más información sobre las suscripciones y las licencias, consulte [Microsoft 365 guía para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

> [!IMPORTANT]
> Cumplimiento avanzado de Office 365 ya no se vende como una suscripción independiente. Cuando expiren las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o adicionales.

Los administradores de TI de Contoso realizan los pasos siguientes para comprobar la compatibilidad de licencias con Contoso:

1. Los administradores de TI inician sesión en el Centro de administración de Microsoft 365 <https://admin.microsoft.com> y van a Centro de administración de Microsoft 365 > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">**BillingLicenses**</a> > .

2. Aquí confirman que tienen una de las [opciones de licencia](communication-compliance-configure.md#subscriptions-and-licensing) que incluye compatibilidad con el cumplimiento de comunicaciones.

![Licencias de cumplimiento de comunicaciones.](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Permisos para el cumplimiento de comunicaciones

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que **el cumplimiento de comunicaciones** esté disponible como una opción de menú en el portal de cumplimiento de Microsoft Purview y para continuar con estos pasos de configuración, a los administradores de Contoso se les asigna el rol *Administrador de cumplimiento de comunicaciones* .

Contoso decide usar el grupo de roles *Cumplimiento de comunicaciones* para asignar al grupo todos los administradores, analistas, investigadores y visores de cumplimiento de comunicaciones. Esto facilita que Contoso empiece a trabajar rápidamente y se ajuste mejor a sus requisitos de administración de cumplimiento.

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todos los roles de permiso de cumplimiento de comunicaciones. Esta configuración es la manera más fácil de empezar a trabajar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de comunicaciones y, posteriormente, para separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver las alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver las directivas donde se asignan como revisores, ver los metadatos del mensaje (no el contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver las alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido del mensaje, escalar a revisores adicionales, escalar a un caso de eDiscovery (Premium), enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán los informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

1. Los administradores de TI de Contoso inician sesión en la página permisos del [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com/permissions) con las credenciales de una cuenta de administrador global y seleccionan el vínculo para ver y administrar roles en Microsoft 365.
2. En el portal de cumplimiento de Microsoft Purview, van a <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a> y seleccionan el vínculo para ver y administrar roles en Office 365.
3. Los administradores *seleccionan el grupo de roles Cumplimiento de comunicaciones* y, a continuación, **seleccionan Editar grupo de roles**.
4. Los administradores **seleccionan Elegir miembros** en el panel de navegación izquierdo y, a continuación, **seleccionan Editar**.
5. Seleccionan **Agregar** y, a continuación, seleccionan la casilla para todos los usuarios de Contoso que administrarán el cumplimiento de las comunicaciones, investigarán y revisarán las alertas.
6. Los administradores **seleccionan Agregar** y, después, **Listo**.
7. Seleccionan **Guardar** para agregar usuarios de Contoso al grupo de roles. Seleccionan **Cerrar** para completar los pasos.

## <a name="step-2-accessing-communication-compliance"></a>Paso 2: Acceso al cumplimiento de la comunicación

Después de configurar los permisos para el cumplimiento de comunicaciones, los administradores de TI de Contoso y los especialistas en cumplimiento asignados al grupo de roles cumplimiento de comunicaciones pueden acceder a la solución de cumplimiento de comunicaciones en Microsoft Purview. Los administradores de TI y los especialistas en cumplimiento de Contoso tienen varias maneras de acceder al cumplimiento de las comunicaciones y empezar a crear una nueva directiva:

- Empezando directamente desde la solución de cumplimiento de comunicaciones
- A partir del portal de cumplimiento de Microsoft Purview
- A partir del catálogo de soluciones de Microsoft Purview
- A partir de la Centro de administración de Microsoft 365

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Empezando directamente desde la solución de cumplimiento de comunicaciones

La forma más rápida de acceder a la solución es iniciar sesión directamente en la solución **de cumplimiento de comunicaciones** (<https://compliance.microsoft.com/supervisoryreview>). Con este vínculo, los administradores de TI de Contoso y los especialistas en cumplimiento se dirigirán al panel de información general de cumplimiento de comunicaciones, donde puede revisar rápidamente el estado de las alertas y crear nuevas directivas a partir de las plantillas predefinidas.

![Información general sobre el cumplimiento de comunicaciones.](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-purview-compliance-portal"></a>A partir del portal de cumplimiento de Microsoft Purview

Otra manera fácil de que los administradores de TI y los especialistas de cumplimiento de Contoso accedan a la solución de cumplimiento de comunicaciones es iniciar sesión directamente en el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com). Después de iniciar sesión, los usuarios simplemente necesitan seleccionar el control **Mostrar todo** para que se muestren todas las soluciones de cumplimiento y, después, seleccionar la solución **Cumplimiento de comunicaciones** para empezar.

![Centro de cumplimiento.](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-purview-solution-catalog"></a>A partir del catálogo de soluciones de Microsoft Purview

Los administradores de TI y los especialistas en cumplimiento de Contoso también podrían optar por acceder a la solución de cumplimiento de comunicaciones seleccionando el catálogo de soluciones de Microsoft Purview. Al seleccionar **Catálogo** en la sección **Soluciones** del panel de navegación izquierdo mientras se encuentra en el **portal de cumplimiento de Microsoft Purview**, pueden abrir el catálogo de soluciones que enumera todas las soluciones de Microsoft Purview. Al desplazarse hacia abajo hasta la sección **Administración de riesgos de Insider** , los administradores de TI de Contoso pueden seleccionar Cumplimiento de la comunicación para empezar. Los administradores de TI de Contoso también deciden usar el control de navegación Mostrar en para anclar la solución de cumplimiento de comunicaciones al panel de navegación izquierdo para obtener un acceso más rápido cuando inicien sesión en el futuro.

![Catálogo de soluciones.](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>A partir de la Centro de administración de Microsoft 365

Para acceder al cumplimiento de la comunicación al iniciar desde el Centro de administración de Microsoft 365, los administradores de TI de Contoso y los especialistas en cumplimiento inician sesión en el Centro de administración de Microsoft 365 [(https://admin.microsoft.com)](https://admin.microsoft.com) y van al [portal de cumplimiento de Microsoft Purview).](https://compliance.microsoft.com)

![Vínculo de cumplimiento de comunicaciones.](../media/communication-compliance-case-compliance-link.png)

Esta acción abre el **Centro de seguridad y cumplimiento de Office 365** y debe seleccionar el vínculo al **portal de cumplimiento de Microsoft Purview** que se proporciona en el banner de la parte superior de la página.

![Office 365 centro de seguridad y cumplimiento.](../media/communication-compliance-case-scc.png)

Una vez en el **portal de cumplimiento de Microsoft Purview**, los administradores de TI de Contoso **seleccionan Mostrar todo** para mostrar la lista completa de soluciones de cumplimiento.

![Menú cumplimiento de comunicaciones.](../media/communication-compliance-case-show-all.png)

Después de seleccionar **Mostrar todo**, los administradores de TI de Contoso pueden acceder a la solución de cumplimiento de comunicaciones.

![Información general sobre el cumplimiento de comunicaciones.](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Paso 3: Configuración de requisitos previos y creación de una directiva de cumplimiento de comunicaciones

Para empezar a trabajar con una directiva de cumplimiento de comunicaciones, hay varios requisitos previos que los administradores de TI de Contoso deben configurar antes de configurar la nueva directiva para supervisar el texto inadecuado. Una vez completados estos requisitos previos, los administradores de TI de Contoso y los especialistas de cumplimiento pueden configurar la nueva directiva y los especialistas de cumplimiento pueden iniciar la investigación y la corrección de las alertas generadas.

### <a name="enabling-auditing-in-microsoft-365"></a>Habilitación de la auditoría en Microsoft 365

El Cumplimiento de comunicaciones requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva organizativa definida o los cambios que se realicen en la directiva de cumplimiento de comunicaciones.

Los administradores de TI de Contoso revisan y completan las [instrucciones paso a paso](turn-audit-log-search-on-or-off.md) para activar la auditoría. Después de activar la auditoría, se muestra un mensaje que dice que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Los administradores de TI de Contoso solo tienen que realizar esta acción una vez.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configuración de Yammer inquilino para el modo nativo

El cumplimiento de la comunicación requiere que el inquilino de Yammer de una organización esté en modo nativo para supervisar el texto inadecuado en mensajes privados y conversaciones de la comunidad pública.

Los administradores de TI de Contoso se aseguran de que revisan la información [del artículo Información general sobre Yammer modo nativo en Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode) y siguen los pasos para ejecutar la herramienta de migración en el artículo [Configurar la red de Yammer para el modo nativo para Microsoft 365](/yammer/configure-your-yammer-network/native-mode).

### <a name="setting-up-a-group-for-in-scope-users"></a>Configuración de un grupo para usuarios en el ámbito

Los especialistas en cumplimiento de Contoso quieren agregar todos los usuarios a la directiva de comunicación que supervisará el texto inadecuado. Podrían decidir agregar cada cuenta de usuario a la directiva por separado, pero han decidido que es mucho más fácil y ahorra tiempo para usar un grupo de distribución **Todos los usuarios** para los usuarios para esta directiva.

Deben crear un nuevo grupo para incluir a todos los usuarios de Contoso, por lo que realizan los pasos siguientes:

1. Los administradores de TI de Contoso inician sesión en el Centro de administración de Microsoft 365 [(https://admin.microsoft.com)](https://admin.microsoft.com) y van a Centro de administración de Microsoft 365 > **GruposGrupos** > .<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
2. Seleccionan **Agregar un grupo** y completan el asistente para crear un nuevo *grupo de Microsoft 365* o *grupo de distribución*.

    ![Grupos.](../media/communication-compliance-case-all-employees.png)

3. Una vez creado el nuevo grupo, necesitan agregar todos los usuarios de Contoso al nuevo grupo. Abren el **centro de administración de Exchange** [(https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) y van a **Exchange centro** >  **de administraciónrecipientsGroups** > .<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a> Los administradores de TI de Contoso seleccionan el área Pertenencia y el nuevo grupo *Todos los empleados* que crearon y seleccionan el control **Editar** para agregar todos los usuarios de Contoso al nuevo grupo en el asistente.

    ![Exchange centro de administración.](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-inappropriate-text"></a>Creación de la directiva para supervisar el texto inadecuado

Una vez completados todos los requisitos previos, los administradores de TI y los especialistas en cumplimiento de Contoso están listos para configurar la directiva de cumplimiento de comunicaciones para supervisar el texto inadecuado. Con la nueva plantilla de directiva de texto inadecuado, la configuración de esta directiva es sencilla y rápida.

1. Los administradores de TI de Contoso y los especialistas en cumplimiento inician sesión en el **portal de cumplimiento de Microsoft Purview** y **seleccionan Cumplimiento de comunicaciones** en el panel de navegación izquierdo. Esta acción abre el panel **Información general** que tiene vínculos rápidos para las plantillas de directiva de cumplimiento de comunicaciones. Elija la plantilla **Supervisión de texto inadecuado**; para ello, seleccione **Comenzar** para la plantilla.

    ![Plantilla de texto inadecuado de cumplimiento de comunicaciones.](../media/communication-compliance-case-template.png)

2. En el asistente para plantillas de directiva, los administradores de TI de Contoso y los especialistas de cumplimiento trabajan conjuntamente para completar los tres campos necesarios: **Nombre de directiva**, **Usuarios o grupos para supervisar** y **Revisores**.
3. Dado que el asistente para directivas ya ha sugerido un nombre para la directiva, los administradores de TI y especialistas de cumplimiento deciden mantener el nombre sugerido y centrarse en los campos restantes. Seleccionan el grupo *Todos los usuarios* del campo **Usuarios o grupos para supervisar** y seleccionan los especialistas en cumplimiento que deben investigar y corregir las alertas de directiva para el campo **Revisores** . El último paso para configurar la directiva e iniciar la recopilación de información de alertas es seleccionar **Crear directiva**.

    ![Asistente para texto inadecuado de cumplimiento de comunicaciones.](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Paso 4: Investigar y corregir alertas

Ahora que se ha configurado la directiva de cumplimiento de comunicaciones para supervisar el texto inadecuado, el siguiente paso para los especialistas en cumplimiento de Contoso será investigar y corregir las alertas generadas por la directiva. Pueden ser necesarias hasta 24 horas para que las comunicaciones en todos los canales de origen de la comunicación se procesen por completo y las alertas se muestren en el **Panel de alertas**.

Una vez generadas las alertas, los especialistas en cumplimiento de Contoso seguirán [las instrucciones del flujo de trabajo](communication-compliance-investigate-remediate.md) para investigar y corregir problemas de texto inadecuados.
