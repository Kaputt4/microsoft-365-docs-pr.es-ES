---
title: Introducción a la administración de riesgos internos
description: Configurar la administración de riesgos de insider en la organización.
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 0b26cd34cf38f8f2fbd7a0de96f8e34502054ecf
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283214"
---
# <a name="get-started-with-insider-risk-management"></a>Introducción a la administración de riesgos internos

Use directivas de administración de riesgos internas para identificar las actividades de riesgo y las herramientas de administración para actuar en alertas de riesgo en su organización. Complete los siguientes pasos para configurar los requisitos previos y configurar una directiva de administración de riesgos insider.

> [!IMPORTANT]
> La Microsoft 365 de administración de riesgos de insider proporciona una opción de nivel de inquilino para ayudar a los clientes a facilitar el gobierno interno en el nivel de usuario. Los administradores de nivel de inquilino pueden configurar permisos para proporcionar acceso a esta solución para los miembros de su organización y configurar conectores de datos en el Centro de cumplimiento de Microsoft 365 para importar datos relevantes para admitir la identificación a nivel de usuario de actividades potencialmente arriesgadas. Los clientes reconocen que los conocimientos relacionados con el comportamiento, el carácter o el rendimiento del usuario individual relacionados materialmente con el empleo pueden ser calculados por el administrador y puestos a disposición de otros usuarios de la organización. Además, los clientes reconocen que deben llevar a cabo su propia investigación completa relacionada con el comportamiento, el carácter o el rendimiento del usuario individual relacionado materialmente con el empleo, y no solo confiar en los conocimientos del servicio de administración de riesgos de insider. Los clientes son los únicos responsables de usar el servicio de administración de riesgos de Microsoft 365 insider y cualquier característica o servicio asociado de acuerdo con todas las leyes aplicables, incluidas las leyes relacionadas con la identificación de usuarios individuales y las acciones de corrección.

Para obtener más información acerca de cómo las directivas de riesgo de insider pueden ayudarle a administrar los riesgos en su organización, consulte [Insider risk management in Microsoft 365](insider-risk-management.md).

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con la administración de riesgos de insider, debes confirmar la [Microsoft 365 suscripción y](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) los complementos. Para obtener acceso y usar la administración de riesgos de insider, la organización debe tener una de las siguientes suscripciones o complementos:

- Microsoft 365 E5/A5/G5 (versión de pago o de prueba)
- Microsoft 365 E3/A3/G3 + el complemento de cumplimiento Microsoft 365 E5/A5/G5
- Microsoft 365 E3/A3/G3 + el complemento Microsoft 365 E5/A5/G5 Insider Risk Management
- Suscripción a Office 365 E3 + Enterprise Mobility + Security E3 + el complemento Cumplimiento de Microsoft 365 E5

Los usuarios incluidos en las directivas de administración de riesgos de insider deben tener asignada una de las licencias anteriores.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de insider, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a su suscripción existente o registrarse para una prueba de Microsoft 365 Enterprise E5. [](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="recommended-actions-preview"></a>Acciones recomendadas (versión preliminar)

Las acciones recomendadas pueden ayudar a su organización a empezar rápidamente y a sacar el máximo partido de las capacidades de administración de riesgos de insider. Incluidas en **la** página Información general, las acciones recomendadas ayudan a guiarle a través de los pasos para configurar e implementar directivas y para realizar acciones de investigación para acciones de usuario que generen alertas a partir de coincidencias de directivas.

![Acciones recomendadas para la administración de riesgos internos.](../media/insider-risk-recommended-actions.png)

Las siguientes recomendaciones están disponibles para ayudarle a empezar a usar o maximizar la configuración de administración de riesgos de insider:

- **Activar la auditoría:** cuando está activada, la actividad de usuario y administrador de la organización se registra en el Microsoft 365 auditoría. Las directivas y análisis de riesgos de Insider usan este registro para detectar actividades de riesgo.
- **Obtener permisos para la administración de riesgos** de usuario: el nivel de acceso que tiene a las características de administración de riesgos de insider depende del grupo de roles que se haya asignado. Para obtener acceso y configurar las acciones recomendadas, los usuarios deben estar asignados a los grupos de roles *Insider Risk Management* o *Insider Risk Management Admins.*
- **Elegir indicadores de directiva:** los indicadores son esencialmente las actividades de usuario que desea detectar e investigar. Puede elegir indicadores para realizar un seguimiento de la actividad en varias Microsoft 365 y servicios.
- **Examinar los posibles riesgos de insider:** ejecute un examen de análisis para detectar posibles riesgos de insider que se produzcan en su organización. Después de evaluar los resultados, revise las directivas recomendadas para configurar.
- **Asignar permisos a** otros usuarios: si hay miembros del equipo adicionales que serán responsables de administrar las características de riesgo de insider, deberá asignarlos a los grupos de roles adecuados.
- **Cree la primera** directiva: para recibir alertas sobre actividades potencialmente arriesgadas, debe configurar directivas basadas en plantillas predefinidas que definan las actividades de usuario que desea detectar e investigar.
- **Revisar el** usuario cuya actividad  se está puntuando: el panel Usuarios permite ver los usuarios cuya actividad está asignada actualmente a puntuaciones de riesgo, independientemente de si esa actividad ha cumplido el umbral para generar una alerta.
- **Revisar alertas:** después de que se produzca un evento desencadenante para un usuario, las directivas comienzan a asignar puntuaciones de riesgo a la actividad detectada. Si una puntuación de riesgo cumple los umbrales de una directiva, verá una alerta que contiene un desglose detallado de toda la actividad que se va a puntuar para ese usuario.
- **Investigar un caso:** los casos se crean manualmente a partir de alertas cuando se necesita más investigación para identificar posibles riesgos de información interna. Cada caso está en el ámbito de un único usuario y se pueden agregar varias alertas para el usuario a un caso existente o a un nuevo caso.

Cada acción recomendada incluida en esta experiencia tiene cuatro atributos:

- **Action:** el nombre y la descripción de la acción recomendada.
- **Estado:** el estado de la acción recomendada. Los valores *no se inician*, *en curso*, *guardados para más* adelante o *completados*.
- **Obligatorio u opcional:** si la acción recomendada es necesaria u opcional para que las características de administración de riesgos insider funcionen según lo esperado.
- **Tiempo estimado para completar:** tiempo estimado para completar la acción recomendada en minutos.

Seleccione una recomendación de la lista para empezar a configurar la administración de riesgos internos. Cada acción recomendada le guía por las actividades necesarias para la recomendación, incluidos los requisitos, qué esperar y el impacto de configurar la característica en su organización.   Cada acción recomendada se marca automáticamente como completa cuando se configura o deberá seleccionar manualmente la acción como completa cuando esté configurada.

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Paso 1 (obligatorio): Habilitar permisos para la administración de riesgos internos

> [!IMPORTANT]
> Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay seis grupos de roles que se usan para configurar los permisos iniciales para administrar las características de administración de riesgos de insider. Para que la administración de riesgos de **Insider** esté disponible como una opción de menú en Centro de cumplimiento de Microsoft 365 y para continuar con estos pasos de configuración, debe estar asignado a uno de los siguientes roles o grupos de roles:

- Azure Active Directory de [*administrador global*](/azure/active-directory/roles/permissions-reference#global-administrator)
- Azure Active Directory de [*administrador de cumplimiento normativo*](/azure/active-directory/roles/permissions-reference#compliance-administrator)
- Centro de cumplimiento de Microsoft 365 de [*roles administración de*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) la organización
- Centro de cumplimiento de Microsoft 365 [*de roles administrador de cumplimiento*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)
- *Grupo de roles De administración de riesgos* de Insider
- *Grupo de roles Administración de riesgos* de Insider

Los miembros de los siguientes roles tienen los mismos permisos de solución incluidos en el grupo de roles Administrador de administración de riesgos de *Insider:*

- Azure Active Directory *global*
- Azure Active Directory *de cumplimiento*
- Centro de cumplimiento de Microsoft 365 *administración de la organización*
- Centro de cumplimiento de Microsoft 365 de *cumplimiento*

> [!IMPORTANT]
> Asegúrese de que siempre tiene al menos un usuario en los grupos de roles Administración de riesgos de Insider o Administración de riesgos de *Insider* (según la opción que elija) para que la configuración de administración de riesgos de *insider* no llegue a un escenario de "administrador cero" si determinados usuarios abandonan la organización.

Dependiendo de cómo desee administrar las alertas y directivas de administración de riesgos internas, deberá asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de administración de riesgos internas. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de administración de riesgos de insider. También puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles De administración de riesgos de *Insider.* Use un único grupo de roles o varios grupos de roles para ajustarse mejor a sus requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles de solución al configurar y administrar la administración de riesgos de insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :------------- | :------------------- |
| **Administración de riesgos internos** | Use este grupo de roles para administrar la administración de riesgos internos para su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y auditores designados, puede configurar los permisos de administración de riesgos de insider en un solo grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos insider y los permisos asociados. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de insider y es una buena opción para organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. Al usar esta configuración, debe asegurarse de tener siempre al menos un usuario asignado a este grupo de roles para asegurarse de que las directivas funcionan según lo esperado y para que el usuario pueda crear y editar directivas, configurar la configuración de soluciones y revisar las **_advertencias_** de estado de la directiva .|
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de insider y posteriormente para separar a los administradores de riesgos de insider en un grupo definido. Los usuarios de este grupo de roles pueden habilitar y ver información de análisis y crear, leer, actualizar y eliminar directivas de administración de riesgos internas, configuración global y asignaciones de grupos de roles. Al usar esta configuración, debe asegurarse de tener siempre al menos un usuario asignado a este grupo de roles para asegurarse de que las directivas funcionan según lo esperado y para que el usuario pueda crear y editar directivas, configurar la configuración de soluciones y revisar las **_advertencias_** de estado de la directiva . |
| **Analistas de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de casos de administración de riesgos internos. Los usuarios de este grupo de roles pueden acceder y ver todas las alertas de administración de riesgos, casos, información de análisis y plantillas de avisos. No pueden acceder al explorador de contenido de riesgo interno. |
| **Investigadores de administración de riesgos internos** | Use este grupo para asignar permisos a usuarios que actúen como investigadores de datos de riesgos internos. Los usuarios de este grupo de roles pueden tener acceso a todas las alertas de administración de riesgos, casos, plantillas de avisos y el explorador de contenido para todos los casos. |
| **Auditores de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que auditarán las actividades de administración de riesgos internas. Los usuarios de este grupo de roles pueden tener acceso al registro de auditoría de riesgos de insider. Los usuarios de este grupo de roles no pueden tener acceso a la característica de acciones recomendadas (versión preliminar) ni usarla.|

> [!NOTE]
> Estos grupos de roles actualmente no se admiten en Privileged Identity Management (PIM). Para obtener más información sobre PIM, vea [Asignar Azure AD roles en Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Agregar usuarios a un grupo de roles de administración de riesgos interno

Siga estos pasos para agregar usuarios a un grupo de roles de administración de riesgos interno:

1. Inicie sesión [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de roles de administración de riesgos interno al que desea agregar usuarios y, a continuación, **seleccione Editar grupo de roles**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y, después, **Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="step-2-required-enable-the-microsoft-365-audit-log"></a>Paso 2 (obligatorio): habilitar el registro Microsoft 365 auditoría

La administración de riesgos de Insider Microsoft 365 registros de auditoría para información del usuario y actividades identificadas en las directivas y las perspectivas de análisis. Los Microsoft 365 de auditoría son un resumen de todas las actividades de la organización y las directivas de administración de riesgos internas pueden usar estas actividades para generar información sobre directivas.

La auditoría está habilitada para organizaciones de Microsoft 365 de forma predeterminada. Algunas organizaciones pueden haber deshabilitado la auditoría por motivos específicos. Si la auditoría está deshabilitada para su organización, puede deberse a que otro administrador la ha desactivado. Se recomienda confirmar que es correcto volver a activar la auditoría al completar este paso.

Para obtener instrucciones paso a paso para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría](turn-audit-log-search-on-or-off.md). Después de activar la auditoría, se muestra un mensaje que dice que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información sobre el uso del registro de auditoría de Microsoft 365, consulte [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-enable-and-view-insider-risk-analytics-insights"></a>Paso 3 (opcional): Habilitar y ver información de análisis de riesgos de insider

El análisis de administración de riesgos internos le permiten realizar una evaluación de los posibles riesgos internos en su organización sin necesidad de configurar ninguna directiva de riesgos internos. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar. Esta evaluación también puede ayudarle a determinar las necesidades de licencias adicionales o la optimización futura de las directivas existentes. Los resultados del análisis pueden tardar hasta 48 horas antes de que la información esté disponible como informes para su revisión. Para obtener más información sobre las perspectivas de análisis, consulte Configuración de administración de riesgos de [Insider: Analytics (versión preliminar)](insider-risk-management-settings.md#analytics) y consulte el vídeo Análisis de administración de riesgos de [Insider](https://www.youtube.com/watch?v=5c0P5MCXNXk) para comprender cómo el análisis puede ayudar a acelerar la identificación de posibles riesgos de insider y ayudarle a tomar medidas rápidamente.

Para habilitar análisis de riesgos de *insider,* debe ser miembro del grupo de roles de administración global Insider Risk Management , *Insider Risk Management Admin* o Microsoft 365 Global *admin.*

Siga estos pasos para habilitar el análisis de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider**.
2. Seleccione **Ejecutar examen en** la pestaña Examinar los riesgos de **insider en** la tarjeta de la organización en la pestaña Información general sobre la administración de riesgos de insider.  Esta acción activa el análisis de análisis de la organización. También puede activar el examen en su organización navegando a Configuración de riesgos de **Insider**  >  **Analytics (versión preliminar)** y habilitando Examinar la actividad del usuario del inquilino para identificar posibles riesgos de **insider**.
3. En el **panel de detalles de Analytics,** seleccione Ejecutar examen para iniciar el examen de su **organización.** Los resultados del examen de análisis pueden tardar hasta 24 horas antes de que la información esté disponible como informes para su revisión.

Después de revisar las perspectivas de análisis, elija las directivas de riesgo de insider y configure los requisitos previos asociados que mejor se adapten a la estrategia de mitigación de riesgos internas de su organización.

## <a name="step-4-required-configure-prerequisites-for-policies"></a>Paso 4 (obligatorio): configurar requisitos previos para directivas

La mayoría de las directivas de administración de riesgos internas tienen requisitos previos que deben configurarse para que los indicadores de directiva generen alertas de actividad relevantes. Configure los requisitos previos adecuados en función de las directivas que planee configurar para su organización.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar Microsoft 365 de recursos humanos

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados desde plataformas de recursos humanos y administración de riesgos de terceros. El conector de datos de recursos humanos (RRHH) de Microsoft 365 permite extraer datos de recursos humanos de archivos CSV, incluidas las fechas de terminación del usuario, las últimas fechas de empleo, las notificaciones del plan de mejora de rendimiento, las acciones de revisión de rendimiento y el estado de cambio de nivel de trabajo. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internos y es una parte importante de la configuración de cobertura completa de la administración de riesgos en su organización. Si configura más de un conector de recursos humanos para su organización, la administración de riesgos de insider extraerá automáticamente indicadores de todos los conectores de RRHH.

El Microsoft 365 de recursos humanos es necesario al usar las siguientes plantillas de directiva:

- Filtraciones de datos por parte de usuarios inconformes
- Robo de datos de usuario de salida
- Uso incorrecto de datos de pacientes generales
- Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización
- Infracciones de la directiva de seguridad por parte de usuarios inconformes

Consulte el [artículo Configurar un](import-hr-data.md) conector para importar datos de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de recursos humanos Microsoft 365 para su organización. Después de configurar el conector de recursos humanos, vuelva a estos pasos de configuración.

### <a name="configure--a-healthcare-specific-data-connector"></a>Configurar un conector de datos específico de la salud

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados de terceros en sistemas de registro electrónico de registro médico (EMR) existentes. Los conectores de datos De Microsoft Healthcare y Épico le permiten extraer datos de actividad de su sistema DEA con archivos CSV, incluido el acceso incorrecto a registros de pacientes, actividades de volumen sospechosas y actividades de edición y exportación. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internos y es una parte importante de la configuración de cobertura completa de la administración de riesgos en su organización.

Si configura más de un conector Healthcare o Epic para su organización, la administración de riesgos de insider admite automáticamente las señales de eventos y actividades de todos los conectores Healthcare y Epic.
El Microsoft 365 healthcare o el conector épico es necesario al usar las siguientes plantillas de directiva:

- Uso incorrecto de datos de pacientes generales

Consulte el artículo Configurar un conector para importar datos de atención médica o Configurar un conector para importar datos [de EHR](import-epic-data.md) épico para obtener instrucciones paso [a](import-healthcare-data.md) paso para configurar un conector específico para la salud para su organización. Después de configurar un conector, vuelva a estos pasos de configuración.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar directivas de prevención de pérdida de datos (DLP)

La administración de riesgos de Insider admite el uso de directivas DLP para ayudar a identificar la exposición intencional o accidental de información confidencial a partes no deseadas para alertas DLP de nivel de gravedad alta. Al configurar una directiva de administración de riesgos insider con cualquiera de las plantillas de pérdida **de** datos, tiene la opción de asignar una directiva DLP específica a la directiva para este tipo de alertas.

Las directivas DLP ayudan a identificar a los usuarios para activar la puntuación de riesgos en la administración de riesgos internas para alertas DLP de alta gravedad para información confidencial y son una parte importante de la configuración de la cobertura de administración de riesgos completa en su organización. Para obtener más información sobre la administración de riesgos de insider y las consideraciones de planeación y integración de directivas DLP, vea [Insider risk management policies](insider-risk-management-policies.md#general-data-leaks).

> [!IMPORTANT]
>Asegúrese de que ha completado lo siguiente:
>
>- Comprenderá y configurará correctamente los usuarios del ámbito en las directivas de administración de riesgos de DLP e insider para producir la cobertura de directivas que espera.
>- Asegúrese de que la configuración **de informes de** incidentes en la directiva DLP para la administración de riesgos insider usada con estas plantillas esté configurada para *alertas* de nivel de gravedad alta. Las alertas de administración de riesgos de Insider no se generarán a partir de directivas DLP con el campo **Informes** de incidentes establecido en *Bajo* o *Medio*.

Una directiva DLP es opcional cuando se usan las siguientes plantillas de directiva:

- Filtraciones de datos generales
- Filtraciones de datos por parte de usuarios prioritarios

Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización. Después de configurar una directiva DLP, vuelva a estos pasos de configuración.

### <a name="configure-priority-user-groups"></a>Configurar grupos de usuarios prioritarios

La administración de riesgos de Insider incluye compatibilidad para asignar grupos de usuarios prioritarios a directivas para ayudar a identificar actividades de riesgo únicas para usuarios con posiciones críticas, altos niveles de datos y acceso a la red, o un historial de comportamiento de riesgo pasado. Crear un grupo de usuarios prioritario y asignar usuarios a las directivas de ámbito de ayuda del grupo a las circunstancias únicas que presentan estos usuarios.

Se requiere un grupo de usuarios de prioridad al usar las siguientes plantillas de directiva:

- Infracciones de la directiva de seguridad por parte de los usuarios prioritarios
- Filtraciones de datos por parte de usuarios prioritarios

Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#priority-user-groups-preview) para obtener instrucciones paso a paso para crear un grupo de usuarios prioritario. Después de configurar un grupo de usuarios prioritario, vuelva a estos pasos de configuración.

### <a name="configure-physical-badging-connector-optional"></a>Configurar el conector de badging físico (opcional)

La administración de riesgos de Insider admite la importación de datos de usuario y registro desde plataformas de control físico y acceso. El conector de protección física permite extraer datos de acceso de archivos JSON, incluidos los id. de usuario, los id. de punto de acceso, la hora y las fechas de acceso y el estado de acceso. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internos y es una parte importante de la configuración de cobertura completa de la administración de riesgos en su organización. Si configura más de un conector de badging físico para su organización, la administración de riesgos de insider extrae automáticamente los indicadores de todos los conectores de badging físicos. La información del conector de badging físico complementa otras señales de riesgo de insider cuando se usan todas las plantillas de directiva de riesgo de insider.

> [!IMPORTANT]
> Para que las directivas de administración de riesgos internas usen y correlacionan los datos de señal relacionados con los usuarios que salen y terminan con los datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de Microsoft 365 recursos humanos. Si habilita el conector de protección física sin habilitar el conector de recursos humanos de Microsoft 365, las directivas de administración de riesgos internas solo procesarán eventos para el acceso físico no autorizado para los usuarios de la organización.

Consulte el [artículo Configurar](import-physical-badging-data.md) un conector para importar datos de mal estado físicos para obtener instrucciones paso a paso para configurar el conector de badging físico para su organización. Después de configurar el conector, vuelva a estos pasos de configuración.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Configurar Microsoft Defender para el extremo (opcional)

[Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) es una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de las infracciones de seguridad en su organización, puede importar y filtrar alertas de Defender para puntos de conexión para las actividades que se usan en las directivas creadas a partir de plantillas de directiva de infracción de seguridad de la administración de riesgos insider.

Si crea directivas de infracción de seguridad, tendrá que configurar Microsoft Defender para endpoint en su organización y habilitar Defender for Endpoint para la integración de la administración de riesgos internas en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información acerca de los requisitos, consulte [el artículo Requisitos mínimos para Microsoft Defender para endpoint.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

Consulte el [artículo Configurar características avanzadas](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) en Defender para endpoint para obtener instrucciones paso a paso para configurar Defender for Endpoint para la integración de la administración de riesgos de insider. Después de configurar Microsoft Defender para endpoint, vuelve a estos pasos de configuración.

## <a name="step-5-required-configure-insider-risk-settings"></a>Paso 5 (obligatorio): Configurar las opciones de riesgo de insider

[La configuración de riesgos de Insider](insider-risk-management-settings.md) se aplica a todas las directivas de administración de riesgos de insider, independientemente de la plantilla que elija al crear una directiva. La configuración se ajusta con el control de la **Configuración de riesgos internos** que se encuentra en la parte superior de todas las pestañas de administración de riesgos internos. Estas opciones controlan la privacidad, los indicadores, la supervisión de períodos y las detecciones inteligentes.

Antes de configurar una directiva, defina las siguientes opciones de configuración de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider** en la esquina superior derecha de cualquier página.
2. En la **página Privacidad,** seleccione una configuración de privacidad para mostrar nombres de usuario para alertas de directiva.
3. En la **página Indicadores,** seleccione los indicadores de alerta que desea aplicar a todas las directivas de riesgo de insider.

    > [!IMPORTANT]
    > Para recibir alertas de actividad de riesgo definidas en las directivas, debe seleccionar uno o más indicadores. Si los indicadores no están configurados en Configuración, los indicadores no se podrán seleccionar en las directivas de riesgo de insider.

4. En la **página Períodos de tiempo** de directiva, seleccione los [períodos](insider-risk-management-settings.md#policy-timeframes) de tiempo de la directiva para que entren en vigor para un usuario cuando desencadene una coincidencia para una directiva de riesgo de insider.
5. En la **página Detecciones inteligentes,** configure las siguientes opciones para las directivas de riesgo de insider:
    - [Exclusiones de tipos de archivo](insider-risk-management-settings.md#file-type-exclusions)
    - [Umbrales de actividad de archivo inusual](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Nivel de volumen de alerta](insider-risk-management-settings.md#alert-volume)
    - [Estado de alerta de Microsoft Defender para endpoint](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Configuración de dominio](insider-risk-management-settings.md#domains)
6. En la **página Exportar alertas,** habilite la exportación de información de alertas de riesgo de insider mediante las API de administración Office 365 si es necesario.
7. En la **página Grupos de usuarios prioritarios,** cree un grupo de usuarios de prioridad y agregue usuarios si no se crean en el paso **3**.
8. En la **página Power Automate flujos,** configure un flujo de plantillas de flujo de riesgo interno o cree un nuevo flujo. Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#power-automate-flows-preview) para obtener instrucciones paso a paso.
9. En la **página Activos de** prioridad, configure los activos de prioridad para que usen datos de su plataforma de control físico y acceso importada por el conector de protección física. Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#priority-physical-assets-preview) para obtener instrucciones paso a paso.
10. En la **Microsoft Teams,** habilite la integración Microsoft Teams con la administración de riesgos de insider para crear automáticamente un equipo para la colaboración de casos o usuarios. Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#microsoft-teams-preview) para obtener instrucciones paso a paso.
11. Seleccione **Guardar para** habilitar esta configuración para las directivas de riesgo de insider.

## <a name="step-6-required-create-an-insider-risk-management-policy"></a>Paso 6 (obligatorio): crear una directiva de administración de riesgos de insider

Las directivas de administración de riesgos internos incluyen usuarios asignados y definen los tipos de indicadores de riesgo que se configuran para las alertas. Para que las actividades puedan desencadenar alertas, es necesario configurar una directiva. Use el Asistente para directivas para crear nuevas directivas de administración de riesgos de insider.

1. En [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya **Administración de riesgos internos** y seleccione la pestaña **Directivas**.
2. Seleccione **Crear directiva** para abrir el asistente de directivas.
3. En la página **Plantilla de directiva**, elija una categoría de directiva y luego seleccione la plantilla para la nueva directiva. Estas plantillas están compuestas por condiciones y señales que definen las actividades de riesgo que desea detectar e investigar. Revise los requisitos previos de la plantilla, los eventos desencadenantes y las actividades detectadas para confirmar que esta plantilla de directiva se ajusta a sus necesidades.

    > [!IMPORTANT]
    > Algunas plantillas de directivas tienen requisitos previos que deben configurarse para que la directiva genere las alertas relevantes. Si no ha configurado los requisitos previos de la directiva aplicable, vea el **Paso 4** anterior.

4. Seleccione **Siguiente** para continuar.
5. En la página **Nombre y descripción**, siga los siguientes campos:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la directiva. Este nombre no se puede cambiar después de crear la directiva.
    - **Descripción (opcional)**: escriba una descripción para la directiva.

6. Seleccione **Siguiente** para continuar.
7. En la página **Usuarios y grupos**, seleccione **Incluir todos los usuarios y grupos** o **Incluir usuarios y grupos específicos** para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios; seleccione **Agregar o editar grupos de usuarios prioritarios**. Si se selecciona **Incluir a todos los usuarios y grupos**, se buscarán los eventos desencadenantes de todos los usuarios y grupos de su organización para empezar a asignar puntuaciones de riesgo para la directiva. Seleccionar **Incluir usuarios y grupos específicos** permite definir qué usuarios y grupos se asignan a la directiva. No se admiten cuentas de usuario invitadas.
8. Seleccione **Siguiente** para continuar.
9. En la página **Contenido a priorizar**, puede asignar (si es necesario) las fuentes a priorizar, lo que aumenta la posibilidad de generar una alerta de alta gravedad para estas fuentes. Seleccione una de las siguientes opciones:

    - **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad, y/o tipos de información confidencial como contenido prioritario**. Al seleccionar esta opción se habilitarán las páginas de detalles del asistente para configurar estos canales.
    - **No deseo especificar el contenido prioritario en este momento (podrá hacerlo una vez que se haya creado la directiva)**. Al seleccionar esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si ha seleccionado Quiero especificar sitios de **SharePoint,** etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario en el paso anterior, verá las páginas de detalles de sitios *SharePoint,* tipos de información confidencial y etiquetas de confidencialidad *.* Use estas páginas detalladas para definir el SharePoint, los tipos de información confidencial y las etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione los sitios de SharePoint a los que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar tipo de información confidencial** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"Número de cuenta bancaria de EE. UU."* y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiquetas de confidencialidad** y seleccionar las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto"*.

    >[!NOTE]
    >Los usuarios que configuran la directiva y seleccionan sitios de Share Point prioritarios pueden seleccionar SharePoint a los que tienen permiso de acceso. Si SharePoint sitios no están disponibles para la selección en la directiva por parte del usuario actual, otro usuario con los permisos necesarios puede seleccionar los sitios de la directiva más adelante o el usuario actual debe tener acceso a los sitios necesarios.

12. Seleccione **Siguiente** para continuar.
13. Si ha seleccionado las plantillas Pérdidas generales de datos o Pérdidas de  datos por usuarios *prioritarios,* verá opciones en la página Desencadenadores de esta directiva para eventos de activación personalizada e indicadores de directiva.  Tiene la opción de seleccionar una directiva DLP o indicadores para desencadenar eventos que llevan a los usuarios asignados a la directiva en el ámbito para la puntuación de actividad. Si selecciona la opción Evento de activación de una directiva de prevención de pérdida de datos **(DLP),** debe seleccionar una directiva DLP en la lista desplegable directiva DLP para habilitar los indicadores desencadenantes de la directiva DLP para esta directiva de administración de riesgos de información interna. Si selecciona la opción Evento desencadenante de una actividad de **exfiltración,** debe seleccionar uno o varios de los indicadores enumerados para el evento de desencadenamiento de directivas.
    >[!IMPORTANT]
    >Si no puede seleccionar un indicador enumerado, es porque no están habilitados para su organización. Para que estén disponibles para seleccionar y asignar a la directiva, habilite los indicadores de la administración de riesgos de **Insider**  >  **Configuración**  >  **indicadores de directiva**.

    Si ha seleccionado otras plantillas de directiva, no se admiten eventos de desencadenamiento personalizados. Se aplican los eventos de desencadenamiento de directivas integrados y continuará con el paso 23 sin definir atributos de directiva.

14. Seleccione **Siguiente** para continuar.
15. Si ha seleccionado las plantillas *Pérdidas* de datos generales o *Pérdidas* de datos por usuarios prioritarios y ha seleccionado que el usuario realiza una actividad de exfiltración e indicadores **asociados,** puede elegir umbrales personalizados o predeterminados para los eventos desencadenantes del indicador que haya seleccionado. Elija usar **umbrales predeterminados (recomendados)** o **Usar umbrales personalizados para los eventos desencadenantes.**
16. Seleccione **Siguiente** para continuar.
17. Si ha seleccionado Usar umbrales personalizados para los eventos desencadenantes , para cada indicador de evento desencadenante que seleccionó en el paso 13, elija el nivel adecuado para generar el nivel deseado de **alertas** de actividad.
18. Seleccione **Siguiente** para continuar.
19. En la **página Indicadores de** directiva, verá los indicadores que ha definido como disponibles en la página Indicadores de configuración de riesgos [](insider-risk-management-settings.md#indicators) de **Insider.**  >   Seleccione los indicadores que desea aplicar a la directiva.

    > [!IMPORTANT]
    > Si los indicadores de esta página no se pueden seleccionar, tendrá que seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Habilitar indicadores** del asistente o seleccionar los indicadores en la página **Administración de riesgos internos** > **Configuración** > **Indicadores de directiva**.

    Si ha seleccionado al menos un indicador de *Office* o *Dispositivo*, seleccione los **Impulsores de la puntuación de riesgo** según corresponda. Los impulsores de la puntuación de riesgo solo se aplican a los indicadores seleccionados.
    Si ha seleccionado una plantilla de directiva de *Robo de datos* o *Filtración de datos*, seleccione uno o más métodos de **Detección de Secuencia** y un método de **Detección de filtración acumulada** para aplicar a la directiva.

20. Seleccione **Siguiente** para continuar.
21. En la página Decidir si se usan umbrales de indicadores predeterminados o **personalizados,** elija umbrales personalizados o predeterminados para los indicadores de directiva que haya seleccionado. Elija usar **umbrales predeterminados para todos los** indicadores o Especificar umbrales **personalizados** para los indicadores de directiva seleccionados. Si ha seleccionado Especificar umbrales personalizados, elija el nivel adecuado para generar el nivel deseado de alertas de actividad para cada indicador de directiva.
22. Seleccione **Siguiente** para continuar.
23. En la página **Revisión**, revise la configuración que ha elegido para la directiva y cualquier sugerencia o advertencia sobre sus selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de la directiva o seleccione **Enviar** para crear y activar la directiva.

## <a name="next-steps"></a>Pasos siguientes

Después de completar estos pasos para crear la primera directiva de administración de riesgos de insider, empezará a recibir alertas de indicadores de actividad después de unas 24 horas. Configure directivas adicionales según sea necesario con las instrucciones del paso 4 de este artículo o los pasos descritos en [Create a new insider risk policy](insider-risk-management-policies.md#create-a-new-policy).

Para obtener más información sobre cómo investigar alertas de riesgo de insider y el **panel de** alertas, vea Actividades de administración de riesgos [de Insider](insider-risk-management-activities.md#alert-dashboard).
