---
title: 'Caso práctico: Contoso configura rápidamente una directiva de lenguaje ofensivo para las comunicaciones de Microsoft Teams, Exchange y Yammer'
description: Un caso práctico para Contoso y cómo configuran rápidamente una directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo en las comunicaciones de Microsoft Teams, Exchange Online y Yammer.
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
ms.openlocfilehash: 1b9bef180fed9c3afa3b3d8d2319a1fa0260ed14
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126599"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Caso práctico: Contoso configura rápidamente una directiva de lenguaje ofensivo para las comunicaciones de Microsoft Teams, Exchange y Yammer

El cumplimiento de las comunicaciones en Microsoft 365 ayuda a minimizar los riesgos de comunicación al ayudarle a detectar, capturar y actuar sobre mensajes inapropiados en su organización. Las directivas predefinidas y personalizadas permiten examinar las comunicaciones internas y externas en busca de coincidencias de directivas para que puedan ser examinadas por revisores designados. Los revisores pueden investigar el correo electrónico examinado, Microsoft Teams, Yammer o las comunicaciones de terceros en su organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen con los estándares de mensajes de su organización.

Contoso Corporation es una organización ficticia que necesita configurar rápidamente una directiva para supervisar el lenguaje ofensivo. Han estado usando Microsoft 365 principalmente para el correo electrónico, Microsoft Teams y el soporte técnico de Yammer para sus usuarios, pero tienen nuevos requisitos para aplicar la directiva de la empresa en torno al acoso en el lugar de trabajo. Los administradores de TI y los especialistas en cumplimiento de Contoso tienen conocimientos básicos de los conceptos básicos de trabajar con Microsoft 365 y buscan instrucciones de un extremo a otro para empezar rápidamente con el cumplimiento de las comunicaciones.

En este caso práctico se tratarán los conceptos básicos para configurar rápidamente una directiva de cumplimiento de comunicaciones para supervisar las comunicaciones en busca de lenguaje ofensivo. Estas instrucciones incluyen:

- Paso 1: Planeación del cumplimiento de las comunicaciones
- Paso 2: Obtener acceso al cumplimiento de comunicaciones en Microsoft 365
- Paso 3: Configuración de requisitos previos y creación de una directiva de cumplimiento de comunicaciones
- Paso 4: Investigación y corrección de alertas

## <a name="step-1-planning-for-communication-compliance"></a>Paso 1: Planeación del cumplimiento de las comunicaciones

Los administradores de TI y especialistas en cumplimiento de Contoso han asistido a seminarios web en línea sobre soluciones de cumplimiento en Microsoft 365 y han decidido que las directivas de cumplimiento de comunicaciones les ayudarán a cumplir los requisitos de directivas corporativas actualizados para reducir el acoso en el lugar de trabajo. En colaboración, han desarrollado un plan para crear y habilitar una directiva de cumplimiento de comunicaciones que supervisará el lenguaje ofensivo para los chats enviados en Microsoft Teams, los mensajes privados y las conversaciones de la comunidad en Yammer, y en los mensajes de correo electrónico enviados en Exchange Online. Su plan incluye identificar:

- Los administradores de TI que necesitan tener acceso a las características de cumplimiento de comunicaciones.
- Los especialistas en cumplimiento que necesitan crear y administrar directivas de comunicación.
- Los especialistas en cumplimiento y otros compañeros de otros departamentos (Recursos Humanos, Jurídicos, etc.) que necesitan investigar y corregir las alertas de cumplimiento de comunicaciones.
- Los usuarios que estarán en el ámbito de la directiva de lenguaje ofensivo de cumplimiento de comunicaciones.

### <a name="licensing"></a>Licencias

El primer paso es confirmar que la licencia de Microsoft 365 de Contoso incluye compatibilidad con la solución de cumplimiento de comunicaciones. Para obtener acceso y usar el cumplimiento de las comunicaciones, los administradores de TI de Contoso deben comprobar que Contoso tiene uno de los siguientes elementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + el complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + el complemento De administración de riesgos de Microsoft 365 E5 Insider
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 A3 + el complemento de cumplimiento de Microsoft 365 A5
- Suscripción a Microsoft 365 A3 + el complemento De administración de riesgos de Microsoft 365 A5 Insider
- Suscripción a Microsoft 365 G5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 G5 + el complemento de cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 G5 + el complemento De administración de riesgos de Microsoft 365 G5 Insider
- Suscripción a Office 365 Enterprise E5 (versión de pago o de prueba)
- Suscripción a Office 365 Enterprise E3 + el complemento de cumplimiento avanzado de Office 365 (ya no está disponible para nuevas suscripciones, vea la nota)

También deben confirmar que los usuarios incluidos en las directivas de cumplimiento de comunicaciones deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>El cumplimiento avanzado de Office 365 ya no se vende como suscripción independiente. Cuando expiran las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o características adicionales.

Los administradores de TI de Contoso toman los siguientes pasos para comprobar la compatibilidad con licencias de Contoso:

1. Los administradores de TI inician sesión en el Centro de administración de **Microsoft 365** [(y https://admin.microsoft.com)](https://admin.microsoft.com) navegan a licencias de facturación del Centro de administración de Microsoft **365).**  >    >  

2. Aquí confirman que tienen una de las opciones de [licencia](communication-compliance-configure.md#subscriptions-and-licensing) que incluye compatibilidad para el cumplimiento de las comunicaciones.

![Licencias de cumplimiento de comunicaciones](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Permisos para el cumplimiento de las comunicaciones

Hay cinco grupos de roles que se usan para configurar permisos para administrar las características de cumplimiento de comunicaciones. Para que **el** cumplimiento de las comunicaciones esté disponible como opción de menú en el Centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, a los administradores de Contoso se les asigna el rol de administrador de cumplimiento *de* comunicaciones.

Contoso decide usar  el grupo de roles Cumplimiento de comunicaciones para asignar al grupo todos los administradores de cumplimiento de comunicaciones, analistas, investigadores y visores. Esto facilita a Contoso empezar a trabajar rápidamente y se adapta mejor a sus requisitos de administración de cumplimiento.

|**Rol**|**Permisos de funciones**|
|:-----|:-----|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todas las funciones de permisos de cumplimiento de comunicaciones. Esta configuración es la forma más sencilla de empezar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. |
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de las comunicaciones y, posteriormente, separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuraciones globales y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. |
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver directivas donde se asignan como revisores, ver metadatos de mensajes (no contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido de los mensajes, escalar a revisores adicionales, escalar a un caso de eDiscovery avanzado, enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y ver todos los informes de cumplimiento de comunicaciones. |

1. Los administradores de TI de Contoso inician sesión en la página de permisos del Centro de seguridad y cumplimiento de **Office 36 & 5** [(con https://protection.office.com/permissions)](https://protection.office.com/permissions) las credenciales de una cuenta de administrador global y seleccionan el vínculo para ver y administrar roles en Microsoft 365).
2. En el **Centro de & cumplimiento,** van a **Permisos** y seleccionan el vínculo para ver y administrar roles en Office 365.
3. Los administradores seleccionan el grupo de roles *Cumplimiento* de comunicaciones y, a continuación, **seleccionan Editar grupo de roles.**
4. Los administradores **seleccionan Elegir miembros** en el panel de navegación izquierdo y, a continuación, **seleccionan Editar**.
5. Seleccionan **Agregar y,** a continuación, seleccionan la casilla para todos los usuarios de Contoso que administrarán el cumplimiento de las comunicaciones, investigarán y revisarán las alertas.
6. Los administradores **seleccionan Agregar** y, a continuación, **seleccionan Listo.**
7. Seleccionan **Guardar para** agregar usuarios de Contoso al grupo de roles. Seleccionan **Cerrar** para completar los pasos.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Paso 2: Obtener acceso al cumplimiento de comunicaciones en Microsoft 365

Después de configurar los permisos para el cumplimiento de las comunicaciones, los administradores de TI y especialistas en cumplimiento de Contoso asignados al grupo de roles Cumplimiento de comunicaciones pueden acceder a la solución de cumplimiento de comunicaciones de Microsoft 365. Los administradores de TI y los especialistas en cumplimiento de Contoso tienen varias formas de obtener acceso al cumplimiento de las comunicaciones y empezar a crear una nueva directiva:

- Empezando directamente desde la solución de cumplimiento de comunicaciones
- A partir del Centro de cumplimiento de Microsoft 365
- A partir del catálogo de soluciones de Microsoft 365
- A partir del Centro de administración de Microsoft 365

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Empezando directamente desde la solución de cumplimiento de comunicaciones

La forma más rápida de obtener acceso a la solución es iniciar sesión directamente en la solución de cumplimiento de **comunicaciones** ( <https://compliance.microsoft.com/supervisoryreview> ). Con este vínculo, los administradores de TI y los especialistas en cumplimiento de Contoso se dirigirán al panel de información general sobre cumplimiento de comunicaciones, donde puede revisar rápidamente el estado de las alertas y crear nuevas directivas a partir de las plantillas predefinidas.

![Introducción al cumplimiento de comunicaciones](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>A partir del Centro de cumplimiento de Microsoft 365

Otra forma sencilla para que los administradores de TI y especialistas en cumplimiento de Contoso accedan a la solución de cumplimiento de comunicaciones es iniciar sesión directamente en el Centro de cumplimiento de **Microsoft 365** [( . https://compliance.microsoft.com)](https://compliance.microsoft.com) Después de iniciar sesión, los usuarios simplemente necesitan seleccionar el **control**  Mostrar todo para mostrar todas las soluciones de cumplimiento y, a continuación, seleccionar la solución de cumplimiento de comunicaciones para empezar.

![Centro de cumplimiento](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>A partir del catálogo de soluciones de Microsoft 365

Los administradores de TI y los especialistas en cumplimiento de Contoso también podían elegir acceder a la solución de cumplimiento de comunicaciones seleccionando el catálogo de soluciones de Microsoft 365. Al seleccionar  Catálogo  en la sección Soluciones del panel de navegación izquierdo en el Centro de cumplimiento de **Microsoft 365,** pueden abrir el catálogo de soluciones que enumera todas las soluciones de cumplimiento de Microsoft 365. Desplazándose hacia abajo hasta la sección de administración de riesgos **de Insider,** los administradores de TI de Contoso pueden seleccionar el cumplimiento de comunicaciones para empezar. Los administradores de TI de Contoso también deciden usar el control Mostrar en navegación para anclar la solución de cumplimiento de comunicaciones al panel de navegación izquierdo para obtener un acceso más rápido cuando inicien sesión en el futuro.

![Catálogo de soluciones](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>A partir del Centro de administración de Microsoft 365

Para obtener acceso al cumplimiento de comunicaciones cuando se inicia desde el Centro de administración de Microsoft 365, los administradores de TI y los especialistas en cumplimiento de Contoso inician sesión en el Centro de administración de Microsoft 365 [ https://admin.microsoft.com) (y](https://admin.microsoft.com) navegan al Centro de administración de **Microsoft 365**  >  Cumplimiento).

![Vínculo de cumplimiento de comunicaciones](../media/communication-compliance-case-compliance-link.png)

Esta acción abre el Centro de seguridad y cumplimiento de **Office 365** y deben seleccionar el vínculo al Centro de cumplimiento de **Microsoft 365** que se proporciona en el banner de la parte superior de la página.

![Centro de seguridad y cumplimiento de Office 365](../media/communication-compliance-case-scc.png)

Una vez en el Centro de cumplimiento de  **Microsoft 365,** los administradores de TI de Contoso seleccionan Mostrar todo para mostrar la lista completa de soluciones de cumplimiento.

![Menú de cumplimiento de comunicaciones](../media/communication-compliance-case-show-all.png)

Después de seleccionar **Mostrar todo,** los administradores de TI de Contoso pueden tener acceso a la solución de cumplimiento de comunicaciones.

![Introducción al cumplimiento de comunicaciones](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Paso 3: Configurar requisitos previos y crear una directiva de cumplimiento de comunicaciones

Para empezar a usar una directiva de cumplimiento de comunicaciones, hay varios requisitos previos que los administradores de TI de Contoso deben configurar antes de configurar la nueva directiva para supervisar el lenguaje ofensivo. Una vez completados estos requisitos previos, los administradores de TI y los especialistas en cumplimiento de Contoso pueden configurar la nueva directiva y los especialistas en cumplimiento pueden iniciar la investigación y la corrección de las alertas generadas.

### <a name="enabling-auditing-in-microsoft-365"></a>Habilitar la auditoría en Microsoft 365

El cumplimiento de las comunicaciones requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas a una directiva organizativa definida o en cualquier momento en que se haya cambiado una directiva de cumplimiento de comunicaciones.

Los administradores de TI de Contoso revisan y completan las [instrucciones paso a paso](turn-audit-log-search-on-or-off.md) para activar la auditoría. Después de activar la auditoría, se muestra un mensaje que indica que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Los administradores de TI de Contoso solo tienen que realizar esta acción una vez.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configuración del espacio empresarial de Yammer para el modo nativo

El cumplimiento de las comunicaciones requiere que el inquilino de Yammer de una organización esté en modo nativo para supervisar el lenguaje ofensivo en mensajes privados y conversaciones de la comunidad pública.

Los administradores de TI de Contoso se asegura de que revisan la información del artículo Información general sobre el modo nativo de Yammer en [Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode) y siguen los pasos para ejecutar la herramienta de migración en el artículo Configurar la red de Yammer para modo nativo para [Microsoft 365.](/yammer/configure-your-yammer-network/native-mode)

### <a name="setting-up-a-group-for-in-scope-users"></a>Configuración de un grupo para usuarios en el ámbito

Los especialistas en cumplimiento de Contoso desean agregar todos los usuarios a la directiva de comunicación que supervisará el lenguaje ofensivo. Podrían decidir agregar cada cuenta de usuario a la directiva por separado, pero han  decidido que es mucho más fácil y ahorra tiempo para usar un grupo de distribución Todos los usuarios para los usuarios de esta directiva.

Deben crear un nuevo grupo para incluir a todos los usuarios de Contoso, por lo que deben realizar los siguientes pasos:

1. Contoso IT administrators IT sign in to the **Microsoft 365 admin center** [ https://admin.microsoft.com) (](https://admin.microsoft.com) and navigate to Microsoft **365 admin center**  >  **Groups**  >  .
2. Seleccionan **Agregar un grupo y** completan el asistente para crear un nuevo grupo de Microsoft *365* o *grupo de distribución.*

    ![Grupos](../media/communication-compliance-case-all-employees.png)

3. Después de crear el nuevo grupo, deben agregar todos los usuarios de Contoso al nuevo grupo. Abren el Centro **de administración de Exchange** [ https://outlook.office365.com/ecp) (](https://outlook.office365.com/ecp) y navegan a los grupos de destinatarios del Centro de administración de   >    >  Exchange. Los administradores de TI de Contoso  seleccionan el área Pertenencia y el nuevo grupo Todos los empleados que crearon y seleccionan el **control** Editar para agregar todos los usuarios de Contoso al nuevo grupo en el asistente.

    ![Centro de administración de Exchange](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Creación de la directiva para supervisar el lenguaje ofensivo

Una vez completados todos los requisitos previos, los administradores de TI y los especialistas en cumplimiento de Contoso están listos para configurar la directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo. Con la nueva plantilla de directiva de lenguaje ofensivo, la configuración de esta directiva es sencilla y rápida.

1. Los administradores de TI y los especialistas en cumplimiento de  Contoso inician sesión en el Centro de cumplimiento de **Microsoft 365** y seleccionan el cumplimiento de comunicaciones en el panel de navegación izquierdo. Esta acción abre el **panel** Información general que tiene vínculos rápidos para las plantillas de directiva de cumplimiento de comunicaciones. Para elegir la **plantilla Monitor para lenguaje** ofensivo, **seleccionan Introducción** a la plantilla.

    ![Plantilla de lenguaje ofensivo de cumplimiento de comunicaciones](../media/communication-compliance-case-template.png)

2. En el Asistente para plantillas de directivas, los administradores de TI y los especialistas en cumplimiento de Contoso trabajan conjuntamente para completar los tres campos obligatorios: nombre de **directiva,** usuarios o grupos que se supervisarán y **Revisores.**
3. Dado que el asistente para directivas ya ha sugerido un nombre para la directiva, los administradores de TI y los especialistas en cumplimiento deciden mantener el nombre sugerido y centrarse en los campos restantes. Seleccionan el grupo *Todos* los usuarios para que los usuarios o grupos supervisen el campo y seleccionan los especialistas en cumplimiento que deben investigar y corregir las alertas de directiva para el **campo Revisores.**  El último paso para configurar la directiva y empezar a recopilar información de alerta es seleccionar **Crear directiva.**

    ![Asistente para lenguaje ofensivo de cumplimiento de comunicaciones](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Paso 4: Investigar y corregir alertas

Ahora que la directiva de cumplimiento de comunicaciones para supervisar el lenguaje ofensivo está configurada, el siguiente paso para los especialistas en cumplimiento de Contoso será investigar y corregir las alertas generadas por la directiva. La directiva puede tardar hasta 24 horas en procesar completamente las comunicaciones en todos los canales de origen de comunicación y que las alertas se muestren en el panel **alerta.**

Una vez generadas las alertas, [](communication-compliance-investigate-remediate.md) los especialistas en cumplimiento de Contoso seguirán las instrucciones de flujo de trabajo para investigar y corregir problemas ofensivos de idioma.