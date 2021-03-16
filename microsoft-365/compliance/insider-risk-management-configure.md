---
title: Introducción a la administración de riesgos internos
description: Configurar la administración de riesgos de insider en la organización.
keywords: Microsoft 365, administración de riesgos insider, administración de riesgos, cumplimiento
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
ms.openlocfilehash: d1ac0bd289185f47fc5eb0bbe34c16fbe28bba84
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819896"
---
# <a name="get-started-with-insider-risk-management"></a>Introducción a la administración de riesgos internos

Use directivas de administración de riesgos internas para identificar las actividades de riesgo y las herramientas de administración para actuar en alertas de riesgo en su organización. Complete los siguientes pasos para configurar los requisitos previos y configurar una directiva de administración de riesgos insider.

>[!IMPORTANT]
>La solución de administración de riesgos insider de Microsoft 365 proporciona una opción de nivel de inquilino para ayudar a los clientes a facilitar el gobierno interno en el nivel de usuario. Los administradores de nivel de inquilino pueden configurar permisos para proporcionar acceso a esta solución para los miembros de su organización y configurar conectores de datos en el Centro de cumplimiento de Microsoft 365 para importar datos relevantes que admitan la identificación de nivel de usuario de actividades potencialmente arriesgadas. Los clientes reconocen que los conocimientos relacionados con el comportamiento, el carácter o el rendimiento del usuario individual relacionados materialmente con el empleo pueden ser calculados por el administrador y puestos a disposición de otros usuarios de la organización. Además, los clientes reconocen que deben llevar a cabo su propia investigación completa relacionada con el comportamiento, el carácter o el rendimiento del usuario individual relacionado materialmente con el empleo, y no solo confiar en los conocimientos del servicio de administración de riesgos de insider. Los clientes son los únicos responsables de usar el servicio de administración de riesgos insider de Microsoft 365 y cualquier característica o servicio asociado de acuerdo con todas las leyes aplicables, incluidas las leyes relacionadas con la identificación de usuarios individuales y las acciones de corrección.

Para obtener más información acerca de cómo las directivas de riesgo de insider pueden ayudarle a administrar los riesgos en su organización, vea [Insider risk management in Microsoft 365](insider-risk-management.md).

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar con la administración de riesgos de insider, debe confirmar su suscripción a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y los complementos. Para obtener acceso y usar la administración de riesgos de insider, la organización debe tener una de las siguientes suscripciones o complementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + el complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + el complemento microsoft 365 E5 Insider Risk Management
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 A3 + el complemento de cumplimiento de Microsoft 365 A5
- Suscripción a Microsoft 365 A3 + el complemento microsoft 365 A5 Insider Risk Management
- Suscripción a Microsoft 365 G5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 G3 + el complemento de cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 G3 + el complemento microsoft 365 G5 Insider Risk Management
- Suscripción a Office 365 E3 + Enterprise Mobility and Security E3 + el complemento de cumplimiento de Microsoft 365 E5

Los usuarios incluidos en las directivas de administración de riesgos de insider deben tener asignada una de las licencias anteriores.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de insider, puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una versión de prueba de Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Paso 1: Habilitar permisos para la administración de riesgos de insider

>[!Important]
>Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay cuatro grupos de roles que se usan para configurar permisos para administrar características de administración de riesgos de insider. Para continuar con estos pasos de configuración, los administradores de inquilinos deben asignarle primero al grupo de roles Administración de riesgos de **Insider** o Administración de riesgos de **Insider.** Para obtener acceso y administrar las características de administración de riesgos de insider después de la configuración inicial, los usuarios deben ser miembros de al menos un grupo de roles de administración de riesgos insider.

Según la estructura del equipo de administración de cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de administración de riesgos insider. Para ver  la pestaña Permisos en el Centro de cumplimiento de Office 365 Security &  y administrar grupos de roles, debe estar asignado al grupo de roles Administración de la organización o debe tener asignado el rol Administración de *roles.* Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :------------- | :------------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos de insider para su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y auditores designados, puede configurar los permisos de administración de riesgos de insider en un solo grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos insider y los permisos asociados. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de insider y es una buena opción para organizaciones que no necesitan permisos independientes definidos para grupos independientes de usuarios. |
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de insider y posteriormente para segregar los administradores de riesgos de insider en un grupo definido. Los usuarios de este grupo de roles pueden habilitar y ver información de análisis y crear, leer, actualizar y eliminar directivas de administración de riesgos internas, configuración global y asignaciones de grupos de roles. |
| **Analistas de administración de riesgos internos** | Use este grupo para asignar permisos a usuarios que actuarán como analistas de casos de riesgo interno. Los usuarios de este grupo de roles pueden acceder y ver todas las alertas de administración de riesgos, casos, información de análisis y plantillas de avisos. No pueden acceder al explorador de contenido de riesgo interno. |
| **Investigadores de administración de riesgos internos** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de datos de riesgo interno. Los usuarios de este grupo de roles pueden tener acceso a todas las alertas de administración de riesgos, casos, plantillas de avisos y el explorador de contenido para todos los casos. |
| **Auditores de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que auditarán las actividades de administración de riesgos internas. Los usuarios de este grupo de roles pueden tener acceso al registro de auditoría de riesgos de insider. |

> [!NOTE]
> Estos grupos de roles actualmente no se admiten en Privileged Identity Management (PIM). Para obtener más información sobre PIM, vea [Asignar roles de Azure AD en Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Agregar usuarios a un grupo de roles de administración de riesgos interno

Siga estos pasos para agregar usuarios a un grupo de roles de administración de riesgos interno:

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en su organización de Microsoft 365.

2. En el Centro &amp; de cumplimiento de seguridad, vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de roles de administración de riesgos interno al que desea agregar usuarios y, a continuación, **seleccione Editar grupo de roles**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar** y, a continuación, **Seleccione Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Paso 2: Habilitar el registro de auditoría de Microsoft 365

La administración de riesgos de Insider usa registros de auditoría de Microsoft 365 para obtener información de usuario y actividades identificadas en directivas e información de análisis. Los registros de auditoría de Microsoft 365 son un resumen de todas las actividades de la organización y las directivas de administración de riesgos internas pueden usar estas actividades para generar información sobre directivas.

Para obtener instrucciones paso a paso para activar la auditoría, vea Activar o desactivar la búsqueda del [registro de auditoría.](turn-audit-log-search-on-or-off.md) Después de activar la auditoría, se muestra un mensaje que indica que se está preparando el registro de auditoría y que puede ejecutar una búsqueda en un par de horas después de completar la preparación. Solo tienes que hacer esta acción una vez. Para obtener más información acerca del uso del registro de auditoría de Microsoft 365, vea [Search the audit log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Paso 3: Habilitar y ver información de análisis de riesgos insider (opcional)

El análisis de administración de riesgos de Insider le permite realizar una evaluación de los posibles riesgos de insider en su organización sin configurar directivas de riesgo de insider. Esta evaluación puede ayudar a su organización a identificar posibles áreas de mayor riesgo para el usuario y ayudar a determinar el tipo y el ámbito de las directivas de administración de riesgos internas que puede considerar la configuración. Esta evaluación también puede ayudarle a determinar las necesidades de licencias adicionales o la optimización futura de las directivas existentes. Los resultados del examen de análisis pueden tardar hasta 48 horas antes de que la información esté disponible como informes para su revisión. Para obtener más información sobre las perspectivas de análisis, consulte Configuración de administración de riesgos [de Insider: Analytics (versión preliminar).](insider-risk-management-settings.md#analytics-preview)

Para habilitar análisis de riesgos de *insider,* debe ser miembro del grupo de roles de administración global de Insider Risk Management , *Insider Risk Management Admin* o Microsoft 365 *Global.*

Siga estos pasos para habilitar el análisis de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider**.
2. Seleccione **Ejecutar examen en** la pestaña Examinar los riesgos de **insider en** la tarjeta de la organización en la pestaña Información general sobre la administración de riesgos de insider.  Esta acción activa el análisis de análisis de la organización. También puede activar el examen en su organización navegando a Configuración de riesgos de **Insider**  >  **Analytics (versión preliminar)** y habilitando Examinar la actividad del usuario del inquilino para identificar posibles riesgos de **insider**.
3. En el **panel de detalles de Analytics,** seleccione Ejecutar examen para iniciar el examen de su **organización.** Los resultados del examen de análisis pueden tardar hasta 24 horas antes de que la información esté disponible como informes para su revisión.

Después de revisar las perspectivas de análisis, elija las directivas de riesgo de insider y configure los requisitos previos asociados que mejor se adapten a la estrategia de mitigación de riesgos internas de su organización.

## <a name="step-4-configure-prerequisites-for-policies"></a>Paso 4: Configurar requisitos previos para directivas

La mayoría de las directivas de administración de riesgos internas tienen requisitos previos que deben configurarse para que los indicadores de directiva generen alertas de actividad relevantes. Configure los requisitos previos adecuados en función de las directivas que planee configurar para su organización.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar el conector de Microsoft 365 HR

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados desde plataformas de recursos humanos y administración de riesgos de terceros. El conector de datos de Recursos Humanos (HR) de Microsoft 365 le permite extraer datos de recursos humanos de archivos CSV, incluidas las fechas de terminación del usuario, las últimas fechas de empleo, las notificaciones del plan de mejora de rendimiento, las acciones de revisión de rendimiento y el estado de cambio de nivel de trabajo. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internas y es una parte importante de la configuración de la cobertura de administración de riesgos completa en su organización. Si configura más de un conector de recursos humanos para su organización, la administración de riesgos de insider extraerá automáticamente indicadores de todos los conectores de RRHH.

El conector de RRHH de Microsoft 365 es necesario al usar las siguientes plantillas de directiva:

- Robo de datos de usuario de salida
- Infracciones de directivas de seguridad por parte de los usuarios que salen
- Infracciones de directivas de seguridad por parte de usuarios inconformes
- Pérdidas de datos de usuarios inconformes

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

- Pérdidas de datos generales
- Pérdidas de datos por usuarios prioritarios

Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización. Después de configurar una directiva DLP, vuelva a estos pasos de configuración.

### <a name="configure-priority-user-groups"></a>Configurar grupos de usuarios prioritarios

La administración de riesgos de Insider incluye compatibilidad para asignar grupos de usuarios prioritarios a directivas para ayudar a identificar actividades de riesgo únicas para usuarios con posiciones críticas, altos niveles de datos y acceso a la red, o un historial de comportamiento de riesgo pasado. Crear un grupo de usuarios prioritario y asignar usuarios a las directivas de ámbito de ayuda del grupo a las circunstancias únicas que presentan estos usuarios.

Se requiere un grupo de usuarios de prioridad al usar las siguientes plantillas de directiva:

- Infracciones de directivas de seguridad por parte de usuarios prioritarios
- Pérdidas de datos por usuarios prioritarios

Consulte el artículo Introducción a la configuración de administración de riesgos [insider](insider-risk-management-settings.md#priority-user-groups-preview) para obtener instrucciones paso a paso para crear un grupo de usuarios prioritario. Después de configurar un grupo de usuarios prioritario, vuelva a estos pasos de configuración.

### <a name="configure-physical-badging-connector-optional"></a>Configurar el conector de badging físico (opcional)

La administración de riesgos de Insider admite la importación de datos de usuario y registro desde plataformas de control físico y acceso. El conector de protección física permite extraer datos de acceso de archivos JSON, incluidos los id. de usuario, los id. de punto de acceso, la hora y las fechas de acceso y el estado de acceso. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos internas y es una parte importante de la configuración de la cobertura de administración de riesgos completa en su organización. Si configura más de un conector de badging físico para su organización, la administración de riesgos de insider extrae automáticamente los indicadores de todos los conectores de badging físicos. La información del conector de badging físico complementa otras señales de riesgo de insider cuando se usan todas las plantillas de directiva de riesgo de insider.

>[!IMPORTANT]
>Para que las directivas de administración de riesgos internas usen y correlacionan los datos de señal relacionados con los usuarios que salen y terminan con los datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de Recursos humanos de Microsoft 365. Si habilita el conector de protección física sin habilitar el conector de Recursos humanos de Microsoft 365, las directivas de administración de riesgos internas solo procesarán eventos para el acceso físico no autorizado para los usuarios de la organización.

Consulte el [artículo Configurar](import-physical-badging-data.md) un conector para importar datos de mal estado físicos para obtener instrucciones paso a paso para configurar el conector de badging físico para su organización. Después de configurar el conector, vuelva a estos pasos de configuración.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Configurar Microsoft Defender para el extremo (opcional)

[Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) es una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de las infracciones de seguridad en su organización, puede importar y filtrar alertas de Defender para puntos de conexión para las actividades que se usan en las directivas creadas a partir de plantillas de directiva de infracción de seguridad de la administración de riesgos insider.

Si crea directivas de infracción de seguridad, tendrá que configurar Microsoft Defender para endpoint en su organización y habilitar Defender for Endpoint para la integración de la administración de riesgos internas en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información acerca de los requisitos, consulte [el artículo Requisitos mínimos de Microsoft Defender para puntos de conexión.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

Consulte el [artículo Configurar características avanzadas](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) en Defender para endpoint para obtener instrucciones paso a paso para configurar Defender for Endpoint para la integración de la administración de riesgos de insider. Después de configurar Microsoft Defender para endpoint, vuelve a estos pasos de configuración.

## <a name="step-5-configure-insider-risk-settings"></a>Paso 5: Configurar las opciones de riesgo de insider

[La configuración de riesgos de Insider](insider-risk-management-settings.md) se aplica a todas las directivas de administración de riesgos de insider, independientemente de la plantilla que elija al crear una directiva. La configuración se configura mediante el control de configuración de riesgos **de Insider** ubicado en la parte superior de todas las pestañas de administración de riesgos de insider. Esta configuración controla la privacidad, los indicadores, las ventanas de supervisión y las detecciones inteligentes.

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

Las directivas de administración de riesgos de Insider incluyen usuarios asignados y definen qué tipos de indicadores de riesgo están configurados para las alertas. Para que las actividades puedan desencadenar alertas, se debe configurar una directiva. Use el Asistente para directivas para crear nuevas directivas de administración de riesgos de insider.

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. Seleccione **Crear directiva** para abrir el asistente para directivas.
3. En la **página Plantilla de** directiva, elija una categoría de directiva y, a continuación, seleccione la plantilla para la nueva directiva. Estas plantillas están hechas de condiciones e indicadores que definen las actividades de riesgo que desea detectar e investigar. Revise los requisitos previos de la plantilla, desencadenar eventos y actividades detectadas para confirmar que esta plantilla de directiva se ajusta a sus necesidades.

    >[!IMPORTANT]
    >Algunas plantillas de directiva tienen requisitos previos que deben configurarse para que la directiva genere alertas relevantes. Si no ha configurado los requisitos previos de directiva aplicables, consulte **el paso 4** anterior.

4. Seleccione **Siguiente** para continuar.
5. En la **página Nombre y descripción,** complete los siguientes campos:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para la directiva. Este nombre no se puede cambiar después de crear la directiva.
    - **Descripción (opcional):** escriba una descripción para la directiva.

6. Seleccione **Siguiente** para continuar.
7. En la página Usuarios  y grupos, seleccione  Incluir todos los usuarios y grupos o Incluir usuarios y grupos específicos para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios;  seleccione **Agregar o editar grupos de usuarios prioritarios**. Al seleccionar **Incluir todos los usuarios y** grupos, se buscarán eventos desencadenados para que todos los usuarios y grupos de la organización comiencen a asignar puntuaciones de riesgo para la directiva. Si selecciona **Incluir usuarios y** grupos específicos, puede definir qué usuarios y grupos asignar a la directiva.
8. Seleccione **Siguiente** para continuar.
9. En la **página Contenido** para priorizar, puede asignar (si es necesario) los orígenes a priorizar, lo que aumenta la probabilidad de generar una alerta de gravedad alta para estos orígenes. Seleccione una de las siguientes opciones:

    - **Quiero especificar sitios de SharePoint, etiquetas de confidencialidad** o tipos de información confidencial como contenido prioritario. Si selecciona esta opción, se habilitarán las páginas detalladas del asistente para configurar estos canales.
    - **No quiero especificar contenido de** prioridad en este momento (podrá hacerlo después de crear la directiva). Si selecciona esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si seleccionó Quiero especificar sitios de **SharePoint,** etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario en el paso anterior, verá las páginas de detalles de sitios de *SharePoint,* tipos de información confidencial y etiquetas de confidencialidad.  Use estas páginas de detalles para definir sharepoint, tipos de información confidencial y etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint:** seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint a las que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial:** selecciona **Agregar tipo de información confidencial** y selecciona los tipos de confidencialidad que quieres priorizar. Por ejemplo, *"Número de cuenta* bancaria de ESTADOS UNIDOS" y *"Número de tarjeta de crédito".*
    - **Etiquetas de confidencialidad:** seleccione Agregar etiqueta **de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto".*

12. Seleccione **Siguiente** para continuar.
13. En la **página Indicadores** y eventos desencadenantes, verá los indicadores que ha definido como disponibles en la página Indicadores de configuración de riesgo [](insider-risk-management-settings.md#indicators) de **Insider.**  >   Si seleccionó una plantilla de pérdida *de* datos al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable directiva **DLP** para habilitar los indicadores desencadenantes de la directiva o seleccionar el evento de activación integrado.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, deberá seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Activar indicadores** en el asistente o seleccionar indicadores en la página Indicadores de directiva de configuración de administración de riesgos de   >    >   Insider.

    Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración predeterminada del umbral de directiva para estos indicadores, deshabilite los umbrales predeterminados de uso **recomendados** por Microsoft e introduzca los valores de umbral para cada indicador seleccionado.

    - Si ha seleccionado al menos un indicador de *Office* *o Dispositivo,* seleccione los impulsores de puntuación de **riesgo** según corresponda. Los impulsores de puntuación de riesgo solo se aplican a indicadores seleccionados.
    - Si ha seleccionado  una plantilla de directiva Robo de datos  o Pérdida de datos, seleccione uno o varios *métodos* de detección de secuencia y un método de detección de **exfiltración** acumulativa para aplicar a la directiva.

14. Seleccione **Siguiente** para continuar.
15. En la **página Umbrales de** indicador, seleccione la opción para usar umbrales de indicador predeterminados o para especificar umbrales personalizados para indicadores individuales. Para cada indicador, elija el nivel adecuado para generar el nivel deseado de alertas de actividad.
16. Seleccione **Siguiente** para continuar.
17. En la **página Revisar,** revise la configuración que ha elegido para la directiva y las sugerencias o advertencias para las selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de directiva o **seleccione Enviar** para crear y activar la directiva.

## <a name="next-steps"></a>Pasos siguientes

Después de completar estos pasos para crear la primera directiva de administración de riesgos de insider, empezará a recibir alertas de indicadores de actividad después de unas 24 horas. Configure directivas adicionales según sea necesario con las instrucciones del paso 4 de este artículo o los pasos descritos en [Create a new insider risk policy](insider-risk-management-policies.md#create-a-new-policy).

Para obtener más información sobre cómo investigar alertas de riesgo de insider y el **panel de** alertas, consulte [Insider risk management alerts](insider-risk-management-alerts.md).
