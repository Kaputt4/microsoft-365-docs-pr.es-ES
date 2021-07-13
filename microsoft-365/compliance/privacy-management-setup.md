---
title: Introducción a la administración de privacidad de Microsoft (versión preliminar)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo configurar la administración de privacidad para su organización, establecer roles y permisos y configurar opciones importantes.
ms.openlocfilehash: 5199cf96e9ede3287dc9ac33e26388c065189748
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378548"
---
# <a name="get-started-with-privacy-management-preview"></a>Introducción a la administración de privacidad (versión preliminar)

En este artículo: obtenga  información sobre cómo configurar el  acceso a la administración de privacidad de su organización, cómo empezar a evaluar los datos y cómo controlar la configuración **importante.**

## <a name="sign-up"></a>Registrarse

La administración de privacidad estará disponible en el Centro de cumplimiento de Microsoft 365. La versión preliminar pública de la administración de privacidad está disponible para las organizaciones con licencias de empresa Office 365 Microsoft 365 E1, E3 y E5. Tras la disponibilidad general de la administración de privacidad, las organizaciones tendrán que obtener una nueva licencia.

Tenga en cuenta que la versión preliminar pública de la administración de privacidad no estará disponible para los clientes del Departamento de Defensa (DoD) Community (GCC) moderados, GCC altos o del Departamento de Defensa ( DoD).

Para empezar con la vista previa pública, obtén la suscripción de vista previa desde el Centro de administración. Si aún no tiene la licencia cuando selecciona por primera vez la administración de privacidad en el centro de cumplimiento, se le dirigirá al Centro de administración para empezar. Se recomienda que el administrador global inicie sesión y establezca los permisos de usuario como se describe a continuación al visitar la administración de privacidad por primera vez. Si no tienes el rol necesario para obtener la suscripción o el consentimiento a los términos de uso de la administración de privacidad, se te pedirá que te contactes con el administrador global para obtener ayuda.

Confirmando que le gustaría empezar a usar señales de administración de privacidad que acepta los términos y el proceso de evaluación de datos personales. Puede revisar los vínculos proporcionados en su totalidad antes de continuar.

## <a name="set-user-permissions-and-assign-roles"></a>Establecer permisos de usuario y asignar roles

La administración de privacidad usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se asigna un rol pueden acceder a la administración de privacidad y las acciones permitidas por cada usuario están restringidas por tipo de función.

Los permisos y asignaciones de roles para la administración de privacidad se pueden controlar en el Centro de cumplimiento de Microsoft 365, como se muestra a continuación. Tenga en cuenta que los roles específicos de la administración de privacidad no aparecerán en Azure Active Directory.

### <a name="in-the-microsoft-365-compliance-center"></a>En el Centro de cumplimiento de Microsoft 365

- Seleccione Permisos en la navegación izquierda.
- Expanda Centro de cumplimiento y seleccione Roles. Aparecerá la lista completa de grupos de roles. 
- Desplácese para buscar los grupos de administración de privacidad o busque por palabra clave, por ejemplo ,"privacidad".
- Seleccione el grupo de funciones relevante para ver una descripción, los roles asignados y una lista de miembros.
- Use el vínculo Editar junto a estas secciones para agregar o cambiar usuarios o editar la configuración.

### <a name="learn-about-role-groups-and-roles"></a>Más información sobre los grupos de roles y los roles

En esta sección se describen los grupos de roles y los roles relevantes para la administración de privacidad. Los miembros deben ser asignados a grupos de roles por el administrador de nivel superior en función de las tareas que necesiten realizar y el nivel de acceso a archivos adecuado. Cada grupo de roles incluye uno o más roles. Estos roles pueden pertenecer a tareas específicas de administración de privacidad o pueden corresponder a funciones clave habilitadas o restringidas para los miembros de ese grupo.

Los grupos de roles se pueden personalizar si es necesario. Para evitar la pérdida accidental de acceso, se recomienda crear una copia del grupo de roles existente que desee personalizar, asignar a la copia un nombre identificable, realizar y comprobar los cambios realizados en el nuevo grupo y asignarle personas según corresponda.

**Administración de privacidad:** este grupo contiene todos los roles de permisos de administración de privacidad en un solo grupo. Esta es la forma más sencilla de empezar rápidamente con la administración de privacidad y administrar el control de acceso para otros grupos que usarán la administración de privacidad. También es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes.

Administradores de administración de **privacidad:** los miembros de este grupo de roles se centran en tareas de configuración y administración y tienen un amplio acceso a las funciones de administración de privacidad, como crear, leer, actualizar y eliminar directivas de administración de privacidad, solicitudes de derechos de sujeto, permisos de administración de privacidad y configuración de administración de privacidad.

**Analistas de administración de privacidad:** los miembros de este grupo de roles actúan como analistas de casos de administración de privacidad. Pueden investigar coincidencias de directivas, ver metadatos de archivos y realizar acciones de corrección. Este grupo no puede tener acceso a archivos completos a través del Explorador de contenido.

**Investigadores de administración de privacidad:** los miembros de este grupo actúan como investigadores de datos de administración de privacidad. Pueden investigar coincidencias de directivas, ver el contenido del archivo asociado y realizar acciones de corrección. Este grupo puede tener acceso a los archivos a través del Explorador de contenido.

**Visor de administración de privacidad:** los miembros de este grupo pueden ver información analítica en la administración de privacidad, como información general, perfil de datos e informes de solicitudes de sujeto.

**Administradores de solicitudes de derechos de** sujeto: los miembros de este grupo tienen acceso total para administrar y crear solicitudes de derechos de sujeto.

**Colaboradores de administración de privacidad:** los miembros de este grupo tienen acceso de colaborador a solicitudes de derechos de sujeto.

Para ver los roles específicos incluidos en cada grupo de roles, consulte la tabla siguiente.

| **Grupo de funciones**      | **Roles incluidos**                        |
|:-- |:--|
| Administración de privacidad  | Administración de casos                           |
|                     | Visor de contenido de clasificación de datos        |
|                     | Visor de listas de clasificación de datos           |
|                     | Administrador de administración de privacidad                  |
|                     | Análisis de administración de privacidad               |
|                     | Investigación de administración de privacidad          |
|                     | Contribución permanente de administración de privacidad |
|                     | Contribución temporal de administración de privacidad |
|                     | Visor de administración de privacidad                 |
|                     | Administrador de solicitudes de derechos de sujeto              |
|                     | View-Only case                            |
| Administrador de administración de privacidad | Administración de casos                      |
|                          | Administrador de administración de privacidad             |
|                          | View-Only case                       |
| Analistas de administración de privacidad | Administración de casos                   |
|                             | Visor de listas de clasificación de datos   |
|                             | Análisis de administración de privacidad       |
|                             | View-Only case                    |
| Investigadores de administración de privacidad | Administración de casos              |
|                                  | Visor de contenido de clasificación de datos |
|                                  | Visor de listas de clasificación de datos    |
|                                  | Investigación de administración de privacidad   |
|                                  | View-Only case                     |
| Visor de administración de privacidad        | Visor de administración de privacidad          |
| Administrador de solicitudes de derechos de sujeto | Administrador de solicitudes de derechos de sujeto   |
|Colaboradores de administración de privacidad       | Contribución temporal de administración de privacidad |
|                                      | Contribución permanente de administración de privacidad |

## <a name="configure-settings"></a>Definir la configuración

Se puede Configuración la página a través del engranaje de la esquina superior derecha de las páginas principales de la administración de privacidad. Permite a los administradores de administración de privacidad configurar propiedades esenciales en la administración de privacidad. Las opciones incluyen lo siguiente.

### <a name="anonymization"></a>Anonimización

Esta característica permite mostrar versiones anónimas de nombres de usuario dentro de las características de administración de privacidad a los usuarios en determinados roles. Esto reemplazará nombres para mostrar identificables como "Grace Taylor" con una etiqueta genérica como "AnonyIS8-988" con el fin de ayudar a enmascarar las identidades de los usuarios al revisar los datos confidenciales. Esta opción no se aplica al módulo de solicitud de derechos del sujeto.

### <a name="user-notification-emails"></a>Mensajes de correo electrónico de notificación de usuario

Cuando detectamos una coincidencia para sus directivas de tratamiento de datos, la administración de privacidad puede enviar un correo electrónico a los usuarios afectados con las acciones correctivas que se deben tomar y un vínculo a la formación en privacidad. En Configuración, puede habilitar o deshabilitar la funcionalidad de notificación de correo electrónico de la administración de privacidad en su conjunto. Puede activar notificaciones individuales, establecer la frecuencia del correo electrónico y especificar una dirección URL de aprendizaje al crear o editar una directiva. Si la funcionalidad de notificación está desactivada en Configuración, se deshabilitará cualquier configuración de nivel de directiva para correos de notificación específicos. Para obtener más información sobre las directivas, vea [Create and manage policies](privacy-management-policies.md).

### <a name="teams-collaboration"></a>Colaboración de Teams

Integre Microsoft Teams con la administración de privacidad para mejorar la colaboración con las partes interesadas. Cada vez que se crea una solicitud de derechos de sujeto, se creará un equipo asociado. Los usuarios se pueden agregar a un equipo desde la pestaña Colaboradores de la solicitud. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

### <a name="power-automate-flows"></a>Power Automate flujos

Use Power Automate para administrar automáticamente procesos y tareas relacionados con la privacidad. Puede crear flujos en la sección Configuración con plantillas de administración de privacidad integradas o usar la consola Power Automate para crear flujos personalizados. Para obtener más información sobre Power Automate, consulte la [Power Automate](/power-automate/) documentación.

### <a name="data-matching"></a>Coincidencia de datos

Use esta sección para cargar esquemas de datos que describen los atributos de los interesados, lo que le ayudará a identificar al interesado correcto al buscar datos personales en su entorno Microsoft 365 datos. Los esquemas y paquetes de reglas se crean y cargan en formato XML. En Carga de datos personales, también puede enviar datos personales que coincidan con un esquema proporcionado. Puede crear y cargar su propio archivo o elegir cargar datos personales de Azure. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

### <a name="data-retention-periods"></a>Períodos de retención de datos

Para las solicitudes de derechos de sujeto, elija cuánto tiempo desea conservar los datos finales recopilados e informar después de cerrar una solicitud. Puede seleccionar entre 30 o 90 días. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

### <a name="data-review-tags"></a>Etiquetas de revisión de datos

Administre las etiquetas que usará para marcar los archivos recuperados en una solicitud de derechos de sujeto. En esta sección, puede editar los nombres y descripciones de las etiquetas personalizadas. También puede editar las descripciones de etiquetas de las etiquetas integradas proporcionadas por el sistema. Los nombres de las etiquetas del sistema no se pueden cambiar. Para obtener más información acerca de las solicitudes de derechos de sujeto, vea [Manage subject rights requests](privacy-management-subject-rights-requests.md).

## <a name="get-initial-data-insights"></a>Obtener información de datos inicial

Después de iniciar sesión en la administración de privacidad, llegarás a la página **Información** general. Esta página proporciona información dinámica sobre los datos personales almacenados en su entorno de Microsoft 365 para ayudarle a detectar rápidamente problemas, identificar indicadores de riesgo y tomar medidas para solucionar problemas. Su información general debe rellenarse con información inicial en las primeras 24 horas de registrarse. A medida que siga usando la administración de privacidad, la página de información general se actualizará para continuar con la información actual.

Para obtener más información sobre los  datos a lo largo del tiempo, la página perfil de datos proporcionará más visualizaciones y análisis y le proporcionará una vista de alto nivel de los datos de su organización por ubicación geográfica y por Microsoft 365 servicio.

Para obtener más información sobre estas páginas, vea [Buscar y visualizar los datos](privacy-management-data-profile.md).
