---
title: Introducción a la administración de riesgos internos
description: Configurar la administración de riesgos de insider en la organización.
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
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
ms.openlocfilehash: ab9f52e2e8376f20bb56aa4389bdaa417826eca1
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007362"
---
# <a name="get-started-with-insider-risk-management"></a>Introducción a la administración de riesgos internos

Use directivas de administración de riesgos internas para identificar las actividades de riesgo y las herramientas de administración para actuar en alertas de riesgo en su organización. Complete los siguientes pasos para configurar los requisitos previos y configurar una directiva de administración de riesgos insider.

>[!IMPORTANT]
>La Microsoft 365 de administración de riesgos de insider proporciona una opción de nivel de inquilino para ayudar a los clientes a facilitar el gobierno interno en el nivel de usuario. Los administradores de nivel de inquilino pueden configurar permisos para proporcionar acceso a esta solución para los miembros de su organización y configurar conectores de datos en el Centro de cumplimiento de Microsoft 365 para importar datos relevantes para admitir la identificación a nivel de usuario de actividades potencialmente arriesgadas. Los clientes reconocen que los conocimientos relacionados con el comportamiento, el carácter o el rendimiento del usuario individual relacionados materialmente con el empleo pueden ser calculados por el administrador y puestos a disposición de otros usuarios de la organización. Además, los clientes reconocen que deben llevar a cabo su propia investigación completa relacionada con el comportamiento, el carácter o el rendimiento del usuario individual relacionado materialmente con el empleo, y no solo confiar en los conocimientos del servicio de administración de riesgos de insider. Los clientes son los únicos responsables de usar el servicio de administración de riesgos de Microsoft 365 insider y cualquier característica o servicio asociado de acuerdo con todas las leyes aplicables, incluidas las leyes relacionadas con la identificación de usuarios individuales y las acciones de corrección.

Para obtener más información acerca de cómo las directivas de riesgo de insider pueden ayudarle a administrar los riesgos en su organización, consulte [Insider risk management in Microsoft 365](insider-risk-management.md).

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con la administración de riesgos de insider, debes confirmar la [Microsoft 365 suscripción y](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) los complementos. Para obtener acceso y usar la administración de riesgos de insider, la organización debe tener una de las siguientes suscripciones o complementos:

- Microsoft 365 E5 suscripción (versión de pago o de prueba)
- Microsoft 365 E3 suscripción + el Cumplimiento de Microsoft 365 E5 complemento
- Microsoft 365 E3 suscripción + el Microsoft 365 E5 de Administración de riesgos de Insider
- Microsoft 365 A5 suscripción (versión de pago o de prueba)
- Microsoft 365 A3 suscripción + el complemento Microsoft 365 A5 cumplimiento
- Microsoft 365 A3 suscripción + el Microsoft 365 A5 de administración de riesgos de Insider
- Microsoft 365 Suscripción de G5 (versión de pago o de prueba)
- Microsoft 365 G3 suscripción + el Microsoft 365 de cumplimiento de G5
- Microsoft 365 G3 suscripción + el complemento Microsoft 365 G5 Insider Risk Management
- Office 365 E3 suscripción + Enterprise Mobility and Security E3 + Cumplimiento de Microsoft 365 E5 add-on

Los usuarios incluidos en las directivas de administración de riesgos de insider deben tener asignada una de las licencias anteriores.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de insider, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a su suscripción existente o registrarse para una prueba de Microsoft 365 Enterprise E5. [](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Paso 1: Habilitar permisos para la administración de riesgos de insider

>[!Important]
>Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay cuatro grupos de roles que se usan para configurar permisos para administrar características de administración de riesgos de insider. Para continuar con estos pasos de configuración, los administradores de inquilinos deben asignarle primero al grupo de roles Administración de riesgos de **Insider** o Administración de riesgos de **Insider.** Para obtener acceso y administrar las características de administración de riesgos de insider después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de administración de riesgos insider.

Dependiendo de la estructura de su equipo de administración de cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de administración de riesgos internos. Para ver  la pestaña Permisos en el Centro de cumplimiento de Office 365 Seguridad & y administrar  grupos de roles, debe estar asignado al grupo de roles Administración de la organización o debe tener asignado el rol Administración de *roles.* Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :------------- | :------------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos internos para su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y auditores designados, puede configurar los permisos de administración de riesgos de insider en un solo grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos insider y los permisos asociados. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de insider y es una buena opción para organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. Al usar esta configuración, debe asegurarse de tener siempre al menos un usuario asignado a este grupo de roles para asegurarse de que las directivas funcionan según lo esperado y para que el usuario pueda crear y editar directivas, configurar la configuración de la solución y revisar las advertencias de estado de la directiva.|
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de insider y posteriormente para separar a los administradores de riesgos de insider en un grupo definido. Los usuarios de este grupo de roles pueden habilitar y ver información de análisis y crear, leer, actualizar y eliminar directivas de administración de riesgos internas, configuración global y asignaciones de grupos de roles. Al usar esta configuración, debe asegurarse de tener siempre al menos un usuario asignado a este grupo de roles para asegurarse de que las directivas funcionan según lo esperado y para que el usuario pueda crear y editar directivas, configurar la configuración de la solución y revisar las advertencias de estado de la directiva. |
| **Analistas de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de casos de administración de riesgos internos. Los usuarios de este grupo de roles pueden acceder y ver todas las alertas de administración de riesgos, casos, información de análisis y plantillas de avisos. No pueden acceder al explorador de contenido de riesgo interno. |
| **Investigadores de administración de riesgos internos** | Use este grupo para asignar permisos a usuarios que actúen como investigadores de datos de riesgos internos. Los usuarios de este grupo de roles pueden tener acceso a todas las alertas de administración de riesgos, casos, plantillas de avisos y el explorador de contenido para todos los casos. |
| **Auditores de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que auditarán las actividades de administración de riesgos internas. Los usuarios de este grupo de roles pueden tener acceso al registro de auditoría de riesgos de insider. |

> [!NOTE]
> Estos grupos de roles actualmente no se admiten en Administración de identidades con privilegios (PIM). Para obtener más información sobre PIM, vea [Asignar roles de Azure AD en Administración de identidades con privilegios](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Agregar usuarios a un grupo de roles de administración de riesgos interno

Siga estos pasos para agregar usuarios a un grupo de roles de administración de riesgos interno:

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de roles de administración de riesgos interno al que desea agregar usuarios y, a continuación, **seleccione Editar grupo de roles**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y, después, **Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Paso 2: Habilitar el registro Microsoft 365 auditoría

La administración de riesgos de Insider Microsoft 365 registros de auditoría para información del usuario y actividades identificadas en las directivas y las perspectivas de análisis. Los Microsoft 365 de auditoría son un resumen de todas las actividades de la organización y las directivas de administración de riesgos internas pueden usar estas actividades para generar información sobre directivas.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del [registro de auditoría.](turn-audit-log-search-on-or-off.md) Después de activar la auditoría, se muestra un mensaje que dice que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información acerca del uso del Microsoft 365 de auditoría, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Paso 3: Habilitar y ver información de análisis de riesgos insider (opcional)

El análisis de administración de riesgos de Insider le permite realizar una evaluación de los posibles riesgos de insider en su organización sin configurar directivas de riesgo de insider. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar. Esta evaluación también puede ayudarle a determinar las necesidades de licencias adicionales o la optimización futura de las directivas existentes. Los resultados del examen de análisis pueden tardar hasta 48 horas antes de que la información esté disponible como informes para su revisión. Para obtener más información sobre las perspectivas de análisis, consulte Configuración de administración de riesgos de [Insider: Analytics (versión preliminar)](insider-risk-management-settings.md#analytics-preview) y consulte el vídeo Análisis de administración de riesgos de [Insider](https://www.youtube.com/watch?v=5c0P5MCXNXk) para comprender cómo el análisis puede ayudar a acelerar la identificación de posibles riesgos de insider y ayudarle a tomar medidas rápidamente.

Para habilitar análisis de riesgos de *insider,* debe ser miembro del grupo de roles de administración global Insider Risk Management , *Insider Risk Management Admin* o Microsoft 365 Global *admin.*

Siga estos pasos para habilitar el análisis de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider**.
2. Seleccione **Ejecutar examen en** la pestaña Examinar los riesgos de **insider en** la tarjeta de la organización en la pestaña Información general sobre la administración de riesgos de insider.  Esta acción activa el análisis de análisis de la organización. También puede activar el examen en su organización navegando a Configuración de riesgos de **Insider**  >  **Analytics (versión preliminar)** y habilitando Examinar la actividad del usuario del inquilino para identificar posibles riesgos de **insider**.
3. En el **panel de detalles de Analytics,** seleccione Ejecutar examen para iniciar el examen de su **organización.** Los resultados del examen de análisis pueden tardar hasta 24 horas antes de que la información esté disponible como informes para su revisión.

Después de revisar las perspectivas de análisis, elija las directivas de riesgo de insider y configure los requisitos previos asociados que mejor se adapten a la estrategia de mitigación de riesgos internas de su organización.

## <a name="step-4-configure-prerequisites-for-policies"></a>Paso 4: Configurar requisitos previos para directivas

La mayoría de las directivas de administración de riesgos internas tienen requisitos previos que deben configurarse para que los indicadores de directiva generen alertas de actividad relevantes. Configure los requisitos previos adecuados en función de las directivas que planee configurar para su organización.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar Microsoft 365 de recursos humanos

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados desde plataformas de recursos humanos y administración de riesgos de terceros. El conector de datos de recursos humanos (RRHH) de Microsoft 365 permite extraer datos de recursos humanos de archivos CSV, incluidas las fechas de terminación del usuario, las últimas fechas de empleo, las notificaciones del plan de mejora de rendimiento, las acciones de revisión de rendimiento y el estado de cambio de nivel de trabajo. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internos y es una parte importante de la configuración de cobertura completa de la administración de riesgos en su organización. Si configura más de un conector de recursos humanos para su organización, la administración de riesgos de insider extraerá automáticamente indicadores de todos los conectores de RRHH.

El Microsoft 365 de recursos humanos es necesario al usar las siguientes plantillas de directiva:

- Robo de datos de usuario de salida
- Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización
- Infracciones de la directiva de seguridad por parte de usuarios inconformes
- Filtraciones de datos por parte de usuarios inconformes

Consulte el [artículo Configurar un conector](import-hr-data.md) para importar datos de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización. Después de configurar el conector de recursos humanos, vuelva a estos pasos de configuración.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar directivas de prevención de pérdida de datos (DLP)

La administración de riesgos de Insider admite el uso de directivas DLP para ayudar a identificar la exposición intencional o accidental de información confidencial a partes no deseadas para alertas DLP de nivel de gravedad alta. Al configurar una directiva de administración de riesgos de insider con cualquiera de las plantillas de pérdida **de** datos, debe asignar una directiva DLP específica a la directiva.

Las directivas DLP ayudan a identificar a los usuarios para activar la puntuación de riesgos en la administración de riesgos internas para alertas DLP de alta gravedad para información confidencial y son una parte importante de la configuración de la cobertura de administración de riesgos completa en su organización. Para obtener más información sobre la administración de riesgos de insider y las consideraciones de planeación y integración de directivas DLP, vea [Insider risk management policies](insider-risk-management-policies.md#general-data-leaks).

>[!IMPORTANT]
>Asegúrese de que ha completado lo siguiente:
>
>- Comprenderá y configurará correctamente los usuarios del ámbito en las directivas de administración de riesgos de DLP e insider para producir la cobertura de directivas que espera.
>- Asegúrese de que la configuración **de informes de** incidentes en la directiva DLP para la administración de riesgos insider usada con estas plantillas esté configurada para *alertas* de nivel de gravedad alta. Las alertas de administración de riesgos de Insider no se generarán a partir de directivas DLP con el campo **Informes** de incidentes establecido en *Bajo* o *Medio*.

Se requiere una directiva DLP al usar las siguientes plantillas de directiva:

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

>[!IMPORTANT]
>Para que las directivas de administración de riesgos internas usen y correlacionan los datos de señal relacionados con los usuarios que salen y terminan con los datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de Recursos humanos de Microsoft 365. Si habilita el conector de protección física sin habilitar el conector de Recursos humanos de Microsoft 365, las directivas de administración de riesgos internas solo procesarán eventos para el acceso físico no autorizado para los usuarios de la organización.

Consulte el [artículo Configurar](import-physical-badging-data.md) un conector para importar datos de mal estado físicos para obtener instrucciones paso a paso para configurar el conector de badging físico para su organización. Después de configurar el conector, vuelva a estos pasos de configuración.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Configurar Microsoft Defender para el extremo (opcional)

[Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) es una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de las infracciones de seguridad en su organización, puede importar y filtrar alertas de Defender para puntos de conexión para las actividades que se usan en las directivas creadas a partir de plantillas de directiva de infracción de seguridad de la administración de riesgos insider.

Si crea directivas de infracción de seguridad, tendrá que configurar Microsoft Defender para endpoint en su organización y habilitar Defender for Endpoint para la integración de la administración de riesgos internas en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información acerca de los requisitos, consulte [el artículo Requisitos mínimos de Microsoft Defender para puntos de conexión.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

Consulte el [artículo Configurar características avanzadas](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) en Defender para endpoint para obtener instrucciones paso a paso para configurar Defender for Endpoint para la integración de la administración de riesgos de insider. Después de configurar Microsoft Defender para endpoint, vuelve a estos pasos de configuración.

## <a name="step-5-configure-insider-risk-settings"></a>Paso 5: Configurar las opciones de riesgo de insider

[La configuración de riesgos de Insider](insider-risk-management-settings.md) se aplica a todas las directivas de administración de riesgos de insider, independientemente de la plantilla que elija al crear una directiva. La configuración se ajusta con el control de la **Configuración de riesgos internos** que se encuentra en la parte superior de todas las pestañas de administración de riesgos internos. Estas opciones controlan la privacidad, los indicadores, la supervisión de períodos y las detecciones inteligentes.

Antes de configurar una directiva, defina las siguientes opciones de configuración de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider** en la esquina superior derecha de cualquier página.
2. En la **página Privacidad,** seleccione una configuración de privacidad para mostrar nombres de usuario para alertas de directiva.
3. En la **página Indicadores,** seleccione los indicadores de alerta que desea aplicar a todas las directivas de riesgo de insider.

    >[!IMPORTANT]
    >Para recibir alertas de actividad de riesgo definidas en las directivas, debe seleccionar uno o más indicadores. Si los indicadores no están configurados en Configuración, los indicadores no se podrán seleccionar en las directivas de riesgo de insider.

4. En la **página Períodos de tiempo** de directiva, seleccione los [períodos](insider-risk-management-settings.md#policy-timeframes) de tiempo de la directiva para que entren en vigor para un usuario cuando desencadene una coincidencia para una directiva de riesgo de insider.
5. En la **página Detecciones inteligentes,** configure las siguientes opciones para las directivas de riesgo de insider:
    - [Exclusiones de tipos de archivo](insider-risk-management-settings.md#file-type-exclusions)
    - [Umbrales de actividad de archivo inusual](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Nivel de volumen de alerta](insider-risk-management-settings.md#alert-volume)
    - [Estado de alerta de Microsoft Defender para endpoint](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Configuración de dominio](insider-risk-management-settings.md#domains-preview)
6. En la **página Exportar alertas,** habilite la exportación de información de alertas de riesgo de información interna mediante las API de administración de Office 365 si es necesario.
7. En la **página Grupos de usuarios prioritarios,** cree un grupo de usuarios de prioridad y agregue usuarios si no se crean en el paso **3**.
8. En la **página Flujos de Power Automate,** configure un flujo de plantillas de flujo de riesgo interno o cree un nuevo flujo. Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#power-automate-flows-preview) para obtener instrucciones paso a paso.
9. En la **página Activos de** prioridad, configure los activos de prioridad para que usen datos de su plataforma de control físico y acceso importada por el conector de protección física. Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#priority-physical-assets-preview) para obtener instrucciones paso a paso.
10. En la **página Microsoft Teams,** habilite la integración de Microsoft Teams con la administración de riesgos de insider para crear automáticamente un equipo para la colaboración de casos o usuarios. Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#microsoft-teams-preview) para obtener instrucciones paso a paso.
11. Seleccione **Guardar para** habilitar esta configuración para las directivas de riesgo de insider.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Paso 6: Crear una directiva de administración de riesgos de insider

Las directivas de administración de riesgos internos incluyen usuarios asignados y definen los tipos de indicadores de riesgo que se configuran para las alertas. Para que las actividades puedan desencadenar alertas, es necesario configurar una directiva. Use el Asistente para directivas para crear nuevas directivas de administración de riesgos de insider.

1. En [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya **Administración de riesgos internos** y seleccione la pestaña **Directivas**.
2. Seleccione **Crear directiva** para abrir el asistente de directivas.
3. En la página **Plantilla de directiva**, elija una categoría de directiva y luego seleccione la plantilla para la nueva directiva. Estas plantillas están compuestas por condiciones y señales que definen las actividades de riesgo que desea detectar e investigar. Revise los requisitos previos de la plantilla, los eventos desencadenantes y las actividades detectadas para confirmar que esta plantilla de directiva se ajusta a sus necesidades.

    >[!IMPORTANT]
    >Algunas plantillas de directivas tienen requisitos previos que deben configurarse para que la directiva genere las alertas relevantes. Si no ha configurado los requisitos previos de la directiva aplicable, vea el **Paso 4** anterior.

4. Seleccione **Siguiente** para continuar.
5. En la página **Nombre y descripción**, siga los siguientes campos:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la directiva. Este nombre no se puede cambiar después de crear la directiva.
    - **Descripción (opcional)**: escriba una descripción para la directiva.

6. Seleccione **Siguiente** para continuar.
7. En la página **Usuarios y grupos**, seleccione **Incluir todos los usuarios y grupos** o **Incluir usuarios y grupos específicos** para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios; seleccione **Agregar o editar grupos de usuarios prioritarios**. Si se selecciona **Incluir a todos los usuarios y grupos**, se buscarán los eventos desencadenantes de todos los usuarios y grupos de su organización para empezar a asignar puntuaciones de riesgo para la directiva. Seleccionar **Incluir usuarios y grupos específicos** permite definir qué usuarios y grupos se asignan a la directiva.
8. Seleccione **Siguiente** para continuar.
9. En la página **Contenido a priorizar**, puede asignar (si es necesario) las fuentes a priorizar, lo que aumenta la posibilidad de generar una alerta de alta gravedad para estas fuentes. Seleccione una de las siguientes opciones:

    - **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad, y/o tipos de información confidencial como contenido prioritario**. Al seleccionar esta opción se habilitarán las páginas de detalles del asistente para configurar estos canales.
    - **No deseo especificar el contenido prioritario en este momento (podrá hacerlo una vez que se haya creado la directiva)**. Al seleccionar esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si ha seleccionado **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario** en el paso anterior, verá las páginas de detalles de los *sitios de SharePoint*, *Tipos de información confidencial* y *Etiquetas de confidencialidad*. Use estas páginas detalladas para definir el SharePoint, los tipos de información confidencial y las etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione los sitios de SharePoint a los que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar tipo de información confidencial** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"Número de cuenta bancaria de EE. UU."* y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiquetas de confidencialidad** y seleccionar las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto"*.

12. Seleccione **Siguiente** para continuar.
13. En la página **Indicadores y eventos desencadenantes**, verá los [indicadores](insider-risk-management-settings.md#indicators)que ha definido como disponibles en la página **Configuración de riesgos internos** > **Indicadores**. Si ha seleccionado una plantilla de *Filtración de datos* al principio del asistente, deberá seleccionar una directiva DLP de la lista desplegable de **directivas DLP** para activar los indicadores de activación de la directiva o seleccionar el evento desencadenante incorporado.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, tendrá que seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Habilitar indicadores** del asistente o seleccionar los indicadores en la página **Administración de riesgos internos** > **Configuración** > **Indicadores de directiva**.

    Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración del umbral de la directiva predeterminada para estos indicadores, desactive la opción **Usar umbrales predeterminados recomendados por Microsoft** y escriba los valores del umbral para cada indicador seleccionado.

    - Si ha seleccionado al menos un indicador de *Office* o *Dispositivo*, seleccione los **Impulsores de la puntuación de riesgo** según corresponda. Los impulsores de la puntuación de riesgo solo se aplican a los indicadores seleccionados.
    - Si ha seleccionado una plantilla de directiva de *Robo de datos* o *Filtración de datos*, seleccione uno o más métodos de **Detección de Secuencia** y un método de **Detección de filtración acumulada** para aplicar a la directiva.

14. Seleccione **Siguiente** para continuar.
15. En la página **Umbrales de los indicadores**, seleccione la opción de usar los umbrales de los indicadores predeterminados o de especificar umbrales personalizados para los indicadores individuales. Para cada indicador, elija el nivel adecuado para generar el nivel deseado de alertas de actividad.
16. Seleccione **Siguiente** para continuar.
17. En la página **Revisión**, revise la configuración que ha elegido para la directiva y cualquier sugerencia o advertencia sobre sus selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de la directiva o seleccione **Enviar** para crear y activar la directiva.

## <a name="next-steps"></a>Siguientes pasos

Después de completar estos pasos para crear la primera directiva de administración de riesgos de insider, empezará a recibir alertas de indicadores de actividad después de unas 24 horas. Configure directivas adicionales según sea necesario con las instrucciones del paso 4 de este artículo o los pasos descritos en [Create a new insider risk policy](insider-risk-management-policies.md#create-a-new-policy).

Para obtener más información sobre cómo investigar alertas de riesgo de insider y el **panel de** alertas, consulte [Insider risk management alerts](insider-risk-management-alerts.md).
