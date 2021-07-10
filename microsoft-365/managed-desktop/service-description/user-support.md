---
title: Soporte al usuario
description: Explica las opciones de soporte técnico dirigido por el cliente y dirigido por asociados.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8cb1b30da84ece597235d8eef674a12208ab6456
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362683"
---
# <a name="user-support"></a>Soporte al usuario

Los Escritorio administrado de Microsoft usuarios pueden obtener soporte técnico de su organización (lo llamamos soporte técnico "dirigido por el cliente") o de un partner seleccionado ("soporte técnico dirigido por partners"). Nuestro objetivo es proporcionar una experiencia coherente para los usuarios y mantener los dispositivos seguros con ambas opciones de soporte técnico. Independientemente de la opción que elija, se aplican estos mismos principios: 

- Integración flexible de Escritorio administrado de Microsoft dispositivos con los procesos de soporte técnico existentes. 
- Borrar roles y responsabilidades entre el proveedor de soporte técnico, los administradores de TI y Escritorio administrado de Microsoft 
- [Rutas de escalación definidas](#workflow-for-support-providers)
- Documentación proporcionada por Escritorio administrado de Microsoft, junto con un portal donde puede solicitar acceso elevado a dispositivos y escalamiento a nuestro personal de soporte técnico, si es necesario.
- Supervisión y mitigación de amenazas proporcionadas por Escritorio administrado de Microsoft todos los días

## <a name="roles-and-responsibilities"></a>Roles y responsabilidades

Para garantizar la calidad del servicio sin poner en peligro la seguridad, el proveedor de soporte técnico, los administradores de TI y Escritorio administrado de Microsoft tienen roles y responsabilidades diferentes.

### <a name="support-provider"></a>Proveedor de soporte técnico

El responsable de estos elementos es quien proporciona soporte técnico (ya sea usted para soporte técnico dirigido por el cliente o un partner dirigido por un partner):

- Proporcionar toda la asistencia técnica y soporte técnico del usuario desde el primer contacto hasta la resolución del usuario
- Cumplir todos los acuerdos de nivel de servicio para el soporte de usuario establecidos por su organización o en asociación con el proveedor de soporte técnico elegido
- Realizar acciones de solución de problemas específicas, como solicitar privilegios elevados de dispositivo, como se describe en [Obtener ayuda para los usuarios](../working-with-managed-desktop/end-user-support.md)
- Solución de problemas de usuario y corrección, incluidos:
    - Sistema operativo (Windows)
    - Microsoft Apps para empresas
    - Características del explorador
    - Problemas de dispositivos
    - Problemas con la infraestructura, como impresoras, controladores y VPN
    - Aplicaciones de línea de negocio

### <a name="it-admin"></a>Administrador de TI

El administrador de TI es responsable de estos elementos:

- Trabajar con el proveedor de soporte técnico para establecer y administrar contratos de nivel de servicio para la compatibilidad con usuarios
- Administrar privilegios de acceso elevado para el personal de soporte técnico aprobado. Para obtener más información, vea [Enable user support features](../get-started/enable-support.md)
- Si hay problemas de dispositivos que afectan a varios usuarios, el aumento de los usuarios mediante el Escritorio administrado de Microsoft de soporte técnico del administrador. Para obtener más información, vea [Admin support for Escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).
- Enrutar problemas relacionados con el hardware al proveedor o proveedor adecuado
- Mantener y proteger la configuración de directiva de seguridad de dispositivos Escritorio administrado de Microsoft dispositivos evitando que se cambien las directivas que establecemos.

### <a name="microsoft-managed-desktop"></a>Escritorio administrado de Microsoft

Como proveedor de servicios, somos responsables de estos elementos:

- Proporcionar los medios para el acceso elevado a dispositivos y la escalación de problemas, incluida la documentación
- Mantener esta información sobre las funciones y responsabilidades actuales
- Responder a solicitudes de soporte técnico de administrador de acuerdo con las definiciones de gravedad
- Proporcionar supervisión y mitigación de amenazas para todos los dispositivos inscritos todos los días

## <a name="workflow-for-support-providers"></a>Flujo de trabajo para proveedores de soporte técnico

Tanto si el soporte técnico está dirigido por el cliente como si está dirigido por un partner, el flujo de actividad de una solicitud de soporte técnico de usuario sigue esta ruta:

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="Cuando un usuario se pone en contacto con él, funcionará a través del sistema de personal en niveles tal como lo haya diseñado. Es importante designar un grupo de personal de soporte técnico al que se le darán las capacidades de elevación y escalamiento, conocido como equipo de escalamiento de soporte técnico. Para problemas Escritorio administrado de Microsoft específicos, pueden escalar a nuestro equipo de operaciones. O para otros problemas de Microsoft, pueden enrutar al canal de soporte técnico existente, unificado o premier. Los problemas de hardware siempre se deben enrutar al proveedor o proveedor establecido":::

La integración de los procesos existentes con este flujo de trabajo Escritorio administrado de Microsoft dispositivos es flexible, por lo que los detalles podrían ser diferentes. Por lo general, el proveedor de soporte técnico sigue un enfoque existente basado en niveles o entrega, designando usuarios específicos que tienen la capacidad de elevar los permisos o escalar problemas a Escritorio administrado de Microsoft Operations. Es mejor mantener este grupo más pequeño que el equipo de soporte técnico más amplio.

Si un problema de usuario debe escalarse a Escritorio administrado de Microsoft, es útil identificar a qué equipo debe dirigirse el problema. Podemos transferir casos correctamente, pero ahorra tiempo para enrutarlos al lugar correcto desde el principio.

- Problemas específicos de Escritorio administrado de Microsoft (por ejemplo, una directiva o una configuración que implementa el propio servicio): escala directamente al equipo de operaciones. Para obtener más información, consulta [Obtener ayuda para los usuarios.](../working-with-managed-desktop/end-user-support.md)
- Problemas de hardware: directos a su proveedor o proveedor de hardware
- Otros problemas: escala a través de los canales de soporte técnico existentes, ya sea una suscripción unificada o Premier.

## <a name="provided-support-framework"></a>Marco de soporte técnico proporcionado


### <a name="elevation-portal"></a>Portal de elevación 

Dado que Escritorio administrado de Microsoft dispositivos se ejecutan en el usuario estándar de forma predeterminada, algunas tareas requieren la elevación de privilegios. (Para obtener más información acerca del control de cuentas de usuario, vea [Control de cuentas de usuario](/windows/security/identity-protection/user-account-control/user-account-control-overview)) Para que el personal de [](../working-with-managed-desktop/end-user-support.md#elevation-requests) soporte técnico pueda realizar tareas mientras se solucionan problemas para los usuarios, proporcionamos acceso "justo a tiempo" a una cuenta de administrador. Esta contraseña a la que acceden de forma segura solo las personas que designe y gira cada par de horas.  

Para obtener instrucciones sobre cómo configurar usuarios para el acceso a este portal, vea [Habilitar características de soporte técnico de usuario](../get-started/enable-support.md).

Para ver los pasos para enviar una solicitud de elevación, vea [Elevation requests](../working-with-managed-desktop/end-user-support.md#elevation-requests).

### <a name="escalation-portal"></a>Portal de escalación 

Si un problema requiere una escalación Escritorio administrado de Microsoft equipo de operaciones, el personal de soporte técnico designado podría dirigirse de forma similar a una solicitud de soporte técnico de administración de TI.  

> [!NOTE]
> Solo se pueden presentar solicitudes de soporte técnico de Sev C de esta manera. Para un problema que coincida con la descripción de otras gravedades, se recomienda ponerse en contacto con el administrador de TI correspondiente para que lo archivo. Para obtener más información, consulta [Definiciones de gravedad de solicitud de soporte técnico.](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)

Para obtener instrucciones sobre cómo configurar usuarios para el acceso a este portal, vea [Habilitar características de soporte técnico de usuario](../get-started/enable-support.md).

Para ver los pasos para enviar una solicitud de escalación, vea [Solicitudes de escalación](../working-with-managed-desktop/end-user-support.md#escalation-requests).
