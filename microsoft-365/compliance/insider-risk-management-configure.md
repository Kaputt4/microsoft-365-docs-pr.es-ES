---
title: Introducción a la administración de riesgos internos
description: Configurar la administración de riesgos de insider en la organización.
keywords: Microsoft 365, administración de riesgos interno, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3a88c48e6915b03316b29d80d2a0f7550d4b5d32
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105167"
---
# <a name="get-started-with-insider-risk-management"></a>Introducción a la administración de riesgos internos

Use directivas de administración de riesgos internas para identificar actividades de riesgo y herramientas de administración para actuar en alertas de riesgo en su organización. Complete los siguientes pasos para configurar requisitos previos y configurar una directiva de administración de riesgos interno.

>[!IMPORTANT]
>La solución de administración de riesgos internos de Microsoft 365 proporciona una opción de nivel de inquilino para ayudar a los clientes a facilitar el gobierno interno en el nivel de usuario. Los administradores de nivel de inquilino pueden configurar permisos para proporcionar acceso a esta solución a los miembros de su organización y configurar conectores de datos en el Centro de cumplimiento de Microsoft 365 para importar datos relevantes a fin de admitir la identificación de nivel de usuario de actividad potencialmente arriesgada. Los clientes reconocen que el administrador puede calcular información relacionada con el comportamiento, el carácter o el rendimiento del usuario individual relacionado materialmente con el empleo y estar a disposición de otras personas de la organización. Además, los clientes reconocen que deben llevar a cabo su propia investigación completa relacionada con el comportamiento, el carácter o el rendimiento del usuario individual relacionado materialmente con el empleo, y no solo confiar en la información del servicio de administración de riesgos de Insider. Los clientes son los únicos responsables de usar el servicio de administración de riesgos de Insider de Microsoft 365 y cualquier característica o servicio asociado de conformidad con todas las leyes aplicables, incluidas las leyes relacionadas con la identificación de usuarios individuales y las acciones correctivas.

Para obtener más información acerca de cómo las directivas de riesgo interno pueden ayudarle a administrar los riesgos en su organización, consulte Administración de riesgos de [Insider en Microsoft 365.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con la administración de riesgos de Insider, debe confirmar su suscripción a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y cualquier complemento. Para acceder y usar la administración de riesgos de Insider, la organización debe tener una de las siguientes suscripciones o complementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + el complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + el complemento De administración de riesgos de Microsoft 365 E5 Insider
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 A3 + el complemento de cumplimiento de Microsoft 365 A5
- Suscripción a Microsoft 365 A3 + el complemento De administración de riesgos de Microsoft 365 A5 Insider
- Suscripción a Microsoft 365 G5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 G5 + el complemento de cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 G5 + el complemento De administración de riesgos de Microsoft 365 G5 Insider

Los usuarios incluidos en las directivas de administración de riesgos internas deben tener asignada una de las licencias anteriores.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos interno, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una prueba de Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Paso 1: Habilitar permisos para la administración de riesgos interno

>[!Important]
>Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay cuatro grupos de roles que se usan para configurar permisos para administrar las características de administración de riesgos interno. Para continuar con estos pasos de configuración, los administradores de inquilinos deben asignarle primero al grupo de roles Administración de riesgos de **Insider** o Administración de riesgos de **Insider.** Para obtener acceso a las características de administración de riesgos de Insider y administrarlas después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de administración de riesgos de Insider.

Según la estructura del equipo de administración de cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de administración de riesgos interno. Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de Insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :---- | :---------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos interno de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas e investigadores designados, puede configurar los permisos de administración de riesgos de Insider en un solo grupo. Este grupo de roles contiene todas las funciones de permisos de administración de riesgos de Insider. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de Insider y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes.|
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de insider y posteriormente para segregar a los administradores de riesgos de insider en un grupo definido.  Los usuarios de este grupo de roles pueden crear, leer, actualizar y eliminar directivas de administración de riesgos internas, configuraciones globales y asignaciones de grupos de roles. |
| **Analistas de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de casos de riesgo interno. Los usuarios de este grupo de roles pueden acceder a todas las alertas, casos y plantillas de avisos de administración de riesgos interno. No pueden acceder al Explorador de contenido de riesgo interno. |
| **Investigadores de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de datos de riesgo interno. Los usuarios de este grupo de roles pueden acceder a todas las alertas, casos, plantillas de avisos y el Explorador de contenido de insider risk management. |

> [!NOTE]
> Actualmente, estos grupos de roles no se admiten en Privileged Identity Management (PIM). Para obtener más información sobre PIM, vea [Asignar roles de Azure AD en Privileged Identity Management.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Agregar usuarios a un grupo de roles de administración de riesgos interno

Complete los siguientes pasos para agregar usuarios a un grupo de roles de administración de riesgos interno:

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador de su organización de Microsoft 365.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos.** Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de roles de administración de riesgos de Insider al que desea agregar usuarios y, a continuación, **seleccione Editar grupo de roles.**

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y, a continuación, **seleccione Listo.**

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="step-2-enable-the-audit-log"></a>Paso 2: Habilitar el registro de auditoría

La administración de riesgos de Insider usa registros de auditoría para la información de los usuarios y las actividades configuradas en las directivas. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva de administración de riesgos internas o cada vez que se cambia una directiva.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del registro [de auditoría.](turn-audit-log-search-on-or-off.md) Después de activar la auditoría, se muestra un mensaje que indica que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información acerca del uso del registro de auditoría, vea [Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-configure-prerequisites-for-templates"></a>Paso 3: Configurar requisitos previos para plantillas

La mayoría de las plantillas de administración de riesgos de Insider tienen requisitos previos que deben configurarse para que los indicadores de directiva generen alertas de actividad relevantes. Configure los requisitos previos adecuados en función de las directivas que planee configurar para su organización.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar el conector de Recursos Humanos de Microsoft 365

La administración de riesgos de Insider admite la importación de datos de usuarios y registros importados desde plataformas de recursos humanos y administración de riesgos de terceros. El conector de datos de Recursos Humanos (RRHH) de Microsoft 365 le permite extraer datos de recursos humanos de archivos CSV, incluidas las fechas de terminación del usuario, las fechas de último empleo, las notificaciones del plan de mejora del rendimiento, las acciones de revisión del rendimiento y el estado de cambio en el nivel de trabajo. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internas y son una parte importante de la configuración de la cobertura de administración de riesgos completa en la organización. Si configura más de un conector de RECURSOS humanos para su organización, la administración de riesgos interno extraerá automáticamente indicadores de todos los conectores de RECURSOS.

El conector de Recursos Humanos de Microsoft 365 es necesario al usar las siguientes plantillas de directiva:

- Robo de datos de usuario de salida
- Infracciones de la directiva de seguridad al abandonar usuarios
- Infracciones de la directiva de seguridad por parte de usuarios descontentos
- Pérdidas de datos de usuarios descontentos

Consulte el [artículo Configurar un](import-hr-data.md) conector para importar datos de recursos humanos para obtener instrucciones paso a paso para configurar el conector de Recursos Humanos de Microsoft 365 para su organización. Después de configurar el conector de RECURSOS humanos, vuelva a estos pasos de configuración.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar directivas de prevención de pérdida de datos (DLP)

La administración de riesgos de Insider admite el uso de directivas DLP para ayudar a identificar la exposición intencionada o accidental de información confidencial a partes no deseadas para alertas DLP de nivel de gravedad alta. Al configurar una directiva de administración de riesgos interno con cualquiera de las plantillas de pérdida **de** datos, debe asignar una directiva DLP específica a la directiva.

Las directivas DLP ayudan a identificar a los usuarios para activar la puntuación de riesgo en la administración de riesgos interno para alertas DLP de gravedad alta para información confidencial y son una parte importante de la configuración de la cobertura de administración de riesgos completa en su organización. Para obtener más información acerca de la administración de riesgos internas y las consideraciones de planeación y integración de directivas DLP, consulte Directivas de administración [de riesgos de Insider.](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Asegúrese de que ha completado lo siguiente:
>
>- Comprende y configura correctamente los usuarios en el ámbito en las directivas de administración de riesgos de DLP y insider para producir la cobertura de directiva que espera.
>- Asegúrese de que la configuración **de informes de** incidentes en la  directiva DLP para la administración de riesgos interno que se usa con estas plantillas está configurada para alertas de nivel de gravedad alta. Las alertas de administración de riesgos de Insider no se generarán a partir de directivas DLP con el campo **Informes** de incidentes establecido en *Bajo* o *Medio.*

Se requiere una directiva DLP al usar las siguientes plantillas de directiva:

- Pérdidas de datos generales
- Pérdidas de datos por usuarios prioritarios

Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización. Después de configurar una directiva DLP, vuelva a estos pasos de configuración.

### <a name="configure-priority-user-groups"></a>Configurar grupos de usuarios de prioridad

La administración de riesgos de Insider incluye compatibilidad para asignar grupos de usuarios prioritarios a directivas para ayudar a identificar actividades de riesgo únicas para los usuarios con posiciones críticas, altos niveles de datos y acceso a la red, o un historial anterior de comportamiento de riesgo. La creación de un grupo de usuarios de prioridad y la asignación de usuarios al grupo ayudan a las directivas de ámbito a las circunstancias únicas que presentan estos usuarios.

Se requiere un grupo de usuarios de prioridad al usar las siguientes plantillas de directiva:

- Infracciones de directivas de seguridad por parte de usuarios prioritarios
- Pérdidas de datos por usuarios prioritarios

Consulte el [artículo Introducción a la configuración de](insider-risk-management-settings.md#priority-user-groups-preview) administración de riesgos interno para obtener instrucciones paso a paso para crear un grupo de usuarios con prioridad. Después de configurar un grupo de usuarios de prioridad, vuelva a estos pasos de configuración.

### <a name="configure-physical-badging-connector-optional"></a>Configurar el conector de badging físico (opcional)

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados desde plataformas de control físico y acceso. El conector de protección física le permite extraer datos de acceso de archivos JSON, incluidos los id. de usuario, los id. de punto de acceso, la hora y las fechas de acceso y el estado de acceso. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internas y son una parte importante de la configuración de la cobertura de administración de riesgos completa en la organización. Si configura más de un conector de administración de daños físicos para su organización, la administración de riesgos de Insider extrae automáticamente indicadores de todos los conectores de administración de daños físicos. La información del conector de señalización física complementa otras señales de riesgo de Insider al usar todas las plantillas de directiva de riesgos de Insider.

>[!IMPORTANT]
>Para que las directivas de administración de riesgos internas usen y correlacionan los datos de señal relacionados con los usuarios que salen y terminan con los datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de Recursos Humanos de Microsoft 365. Si habilita el conector de protección física sin habilitar el conector de Recursos Humanos de Microsoft 365, las directivas de administración de riesgos internas solo procesarán eventos para el acceso físico no autorizado para los usuarios de su organización.

Consulte el [artículo Configurar un](import-physical-badging-data.md) conector para importar datos de daños físicos para obtener instrucciones paso a paso para configurar el conector de protección física para su organización. Después de configurar el conector, vuelva a estos pasos de configuración.

## <a name="step-4-configure-insider-risk-settings"></a>Paso 4: Configurar las opciones de riesgo interno

[La configuración de riesgos de Insider](insider-risk-management-settings.md) se aplica a todas las directivas de administración de riesgos de Insider, independientemente de la plantilla que elijas al crear una directiva. Las opciones se configuran mediante el control de configuración de riesgos de **Insider** que se encuentra en la parte superior de todas las pestañas de administración de riesgos de Insider. Esta configuración controla la privacidad, los indicadores, las ventanas de supervisión y las detecciones inteligentes.

Antes de configurar una directiva, defina las siguientes opciones de riesgo interno:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider** en la esquina superior derecha de cualquier página.
2. En la **página Privacidad,** seleccione una configuración de privacidad para mostrar nombres de usuario para las alertas de directiva.
3. En la **página Indicadores,** selecciona los indicadores de alerta que quieras aplicar a todas las directivas de riesgo de Insider.

    >[!IMPORTANT]
    >Para recibir alertas de actividad de riesgo definida en las directivas, debes seleccionar uno o más indicadores.

4. En la **página Períodos de tiempo** de directiva, selecciona los [períodos](insider-risk-management-settings.md#policy-timeframes) de tiempo de la directiva para que entren en vigor para un usuario cuando desencadene una coincidencia para una directiva de riesgo interno.
5. En la **página Detecciones inteligentes,** configura las siguientes opciones para las directivas de riesgo interno:
    - [Detecciones de anomalías](insider-risk-management-settings.md#anomaly-detections)
    - [Nivel de volumen de alerta](insider-risk-management-settings.md#alert-volume)
    - [Estado de alerta de Microsoft Defender para puntos de conexión](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Configuración de dominio](insider-risk-management-settings.md#domains-preview)
6. En la **página Exportar alertas,** habilite la exportación de información de alertas de riesgo interno mediante las API de administración de Office 365 si es necesario.
7. En la **página Grupos de usuarios de** prioridad, cree un grupo de usuarios de prioridad y agregue usuarios si no se creó en el paso **3.**
8. En la **página Flujos de Power Automate,** configure un flujo de plantillas de flujo de riesgo interno o cree un flujo nuevo. Consulte el artículo Introducción a la configuración de administración de riesgos de [Insider](insider-risk-management-settings.md#power-automate-flows-preview) para obtener instrucciones paso a paso.
9. En la **página Activos de** prioridad, configure los activos de prioridad para usar los datos de su plataforma de control físico y acceso importadas por el conector de protección física. Consulte el artículo Introducción a la configuración de administración de riesgos de [Insider](insider-risk-management-settings.md#priority-physical-assets-preview) para obtener instrucciones paso a paso.
10. En la **página de Microsoft Teams,** habilite la integración de Microsoft Teams con la administración de riesgos de Insider para crear automáticamente un equipo para la colaboración de casos o usuarios. Consulte el artículo Introducción a la configuración de administración de riesgos de [Insider](insider-risk-management-settings.md#microsoft-teams-preview) para obtener instrucciones paso a paso.
11. Seleccione **Guardar para** habilitar esta configuración para las directivas de riesgos internas.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Paso 5: Crear una directiva de administración de riesgos interno

Las directivas de administración de riesgos de Insider incluyen usuarios asignados y definen qué tipos de indicadores de riesgo están configurados para las alertas. Para que las actividades puedan desencadenar alertas, debe configurarse una directiva.

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. Seleccione **Crear directiva** para abrir el asistente para directivas.
3. En la **página Nueva directiva de riesgo interno,** complete los siguientes campos:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para la directiva.
    - **Descripción (opcional):** escriba una descripción para la directiva.
    - **Elija la plantilla de directiva (necesaria):** seleccione una de las plantillas de directiva para definir los tipos de indicadores de riesgo que supervisa la directiva. [](insider-risk-management-policies.md#policy-templates)

    >[!IMPORTANT]
    >La mayoría de las plantillas de directiva tienen requisitos previos que deben configurarse para que la directiva genere alertas relevantes. Si no ha configurado los requisitos previos de directiva aplicables, consulte el **paso 3** anterior.

4. Seleccione **Siguiente** para continuar.
5. En **la** página  Usuarios, seleccione  Agregar usuario o grupo o Elegir grupos de usuarios prioritarios para definir qué usuarios o grupos de usuarios de prioridad se incluyen en la directiva, en función de la plantilla de directiva que haya seleccionado. Active la casilla Todos los usuarios y grupos **habilitados** para correo si procede (si no ha seleccionado una plantilla basada en usuarios de prioridad). Seleccione **Siguiente** para continuar.
6. En la **página Especificar qué contenido se debe priorizar (opcional),** puede asignar los orígenes para priorizar para obtener puntuaciones de riesgo más altas. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados o se haya especificado como prioridad en esta página:
    - **Sitios de SharePoint:** seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1".*
    - **Tipo de información confidencial:** selecciona **Agregar tipo de información confidencial** y selecciona los tipos de confidencialidad que quieres priorizar. Por ejemplo, *"Número de cuenta* bancaria de ESTADOS UNIDOS" y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad:** seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto".*
7. Seleccione **Siguiente** para continuar.
8. En la **página Seleccionar** indicadores de [](insider-risk-management-settings.md#indicators) directiva, verás los indicadores que has definido como disponibles en la página Indicadores de configuración de riesgo de **Insider.**  >   Si seleccionó una *plantilla de* pérdida de datos al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable de directivas **DLP** para habilitar los indicadores desencadenantes de la directiva. Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración de umbral de directiva predeterminada para estos indicadores, deshabilite los umbrales de uso predeterminados **recomendados** por Microsoft y escriba los valores de umbral para cada indicador seleccionado. Si ha seleccionado al menos un indicador de *Office* *o dispositivo,* seleccione los indicadores de puntuación **de riesgo** según corresponda. Los indicadores de puntuación de riesgo solo se aplican a los indicadores seleccionados.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, deberás seleccionar los indicadores que quieras habilitar para todas las directivas en la página Indicadores de directiva de configuración de administración de riesgos   >    >  **de** Insider.

9. Seleccione **Siguiente** para continuar.
10. En la **página Períodos de** tiempo [](insider-risk-management-settings.md#policy-timeframes) de directiva, verás las condiciones de la ventana de activación de la directiva que se encuentra en la página Períodos de tiempo de la directiva de configuración de riesgos de **Insider.**  >  
11. Seleccione **Siguiente** para continuar.
12. En la **página** Revisar, revisa la configuración que has elegido para la directiva. Selecciona **Editar** para cambiar cualquiera de los valores de directiva o **selecciona** Enviar para crear y activar la directiva.

## <a name="next-steps"></a>Pasos siguientes

Después de completar estos pasos para crear la primera directiva de administración de riesgos de Insider, empezarás a recibir alertas de indicadores de actividad después de unas 24 horas. Configure directivas adicionales según sea necesario con las instrucciones del paso 4 de este artículo o los pasos de Crear una nueva directiva de [riesgo interno.](insider-risk-management-policies.md#create-a-new-policy)

Para obtener más información sobre cómo investigar alertas de riesgo interno y el panel **alertas,** consulta Alertas de administración de riesgos [de Insider.](insider-risk-management-alerts.md)
