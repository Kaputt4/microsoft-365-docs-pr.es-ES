---
title: Introducción a la administración de riesgos internos
description: Configure la administración de riesgos de Insiders en su organización.
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: ace04c61b8bb26661201b3a2616799f0dc4ea87e
ms.sourcegitcommit: 9ffa2fd25776726475e10148940987fa076bbd91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44162682"
---
# <a name="get-started-with-insider-risk-management"></a>Introducción a la administración de riesgos internos

Use las directivas de administración de riesgos internos para identificar las actividades de riesgo y las herramientas de administración para tomar medidas en las alertas de riesgos de su organización. Complete los siguientes pasos para configurar los requisitos previos y configurar una directiva de administración de riesgos de Insider.

>[!IMPORTANT]
>La solución de administración de riesgos de Insider de Microsoft 365 proporciona una opción de nivel de inquilino para ayudar a los clientes a facilitar el control interno en el nivel de usuario. Los administradores de nivel de inquilino pueden configurar permisos para proporcionar acceso a esta solución a los miembros de la organización y configurar conectores de datos en el centro de cumplimiento de Microsoft 365 para importar los datos relevantes para admitir la identificación de nivel de usuario de actividad potencialmente arriesgada. Los clientes reconocen la información relacionada con el comportamiento, el personaje o el rendimiento de los usuarios individuales relacionados con el empleo que el administrador puede calcular y poner a disposición de otros usuarios de la organización.

Para obtener más información sobre cómo las directivas de riesgos de Insider pueden ayudarle a administrar el riesgo en su organización, consulte [Administración de riesgos de Insider en Microsoft 365](insider-risk-management.md).

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar con la administración de riesgos de Insider, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y los complementos. Para acceder y usar la administración de riesgos de Insider, su organización debe tener una de las siguientes suscripciones o complementos:

- Suscripción a Microsoft 365 E5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 E3 + complemento de cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 E3 + complemento Microsoft 365 E5 del servicio de administración de riesgos de Insider
- Suscripción a Microsoft 365 A5 (versión de pago o de prueba)
- Suscripción a Microsoft 365 a3 + complemento de cumplimiento A5 de Microsoft 365
- Suscripción a Microsoft 365 a3 + complemento de administración de riesgos de la A5 del Insider de Microsoft 365

Los usuarios incluidos en las directivas de administración de riesgos de internación deben tener asignada una de las licencias anteriores.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de Insider, puede [Agregar microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a la suscripción existente o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Paso 1 (obligatorio): habilitar permisos para la administración de riesgos de Insider

Hay cuatro grupos de roles que se usan para configurar los permisos para administrar las características de administración de riesgos de Insider. Para continuar con estos pasos de configuración, los administradores de espacios empresariales deben asignarle primero al grupo de roles **Administración de riesgos de Insider** o **Administrador de administración de riesgos de Insider** . Para acceder a y administrar las características de administración de riesgos de Insider después de la configuración inicial, los usuarios deben pertenecer al menos a un grupo de roles de administración de riesgos de Insider.

En función de la estructura del equipo de administración del cumplimiento, tiene opciones para asignar usuarios a grupos de roles específicos para administrar distintos conjuntos de características de administración de riesgos de Insider. Elija entre estas opciones de grupo de roles al configurar la administración de riesgos de Insider:

| **Grupo de funciones** | **Permisos de funciones** |
| :---- | :---------------- |
| **Administración de riesgos de Insider** | Use este grupo de roles para administrar la administración de riesgos de internación para su organización en un único grupo. Al agregar todas las cuentas de usuario para los administradores, analistas e investigadores designados, puede configurar los permisos de administración de riesgos de Insider en un único grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos de Insider. Esta configuración es la forma más sencilla de empezar rápidamente con la administración de riesgos de Insider y es una buena opción para las organizaciones que no necesitan permisos separados definidos para grupos de usuarios independientes.|
| **Administrador de administración de riesgos de Insider** | Use este grupo de roles para configurar inicialmente la administración de riesgos de Insiders y más adelante para separar los administradores de riesgos de Insider en un grupo definido.  Los usuarios de este grupo de roles pueden crear, leer, actualizar y eliminar directivas de administración de riesgos de Insider, la configuración global y las asignaciones de grupos de roles. |
| **Analistas de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de casos de riesgo de Insider. Los usuarios de este grupo de roles pueden obtener acceso a todas las plantillas de alertas de administración de riesgos de Insider, casos y notificaciones. No pueden acceder al explorador de contenido de riesgo de Insider. |
| **Investigadores de administración de riesgos de Insider** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de datos de riesgo de Insider. Los usuarios de este grupo de roles pueden tener acceso a todas las alertas de administración de riesgos de Insider, casos, plantillas y el explorador de contenido para todos los casos. |

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Adición de usuarios a un grupo de roles de administración de riesgos de Insider

Complete los siguientes pasos para agregar usuarios a un grupo de roles de administración de riesgos de Insider:

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización de Microsoft 365. "" "" "" ""

2. En el centro &amp; de seguridad y cumplimiento, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de funciones de administración de riesgos de Insider al que desea agregar usuarios y, a continuación, seleccione **Editar Grupo de roles**.

4. Seleccione **elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, marque la casilla de verificación para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar**y haga clic en **listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **cerrar** para completar los pasos.

## <a name="step-2-required-enable-the-audit-log"></a>Paso 2 (obligatorio): habilitar el registro de auditoría

La administración de riesgos de Insiders usa registros de auditoría para las actividades y visiones del usuario configuradas en las directivas. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva de administración de riesgos de Insider o cada vez que cambia una directiva.

Para obtener instrucciones paso a paso para activar la auditoría, vea [activar o desactivar la búsqueda de registros de auditoría](turn-audit-log-search-on-or-off.md). Después de activar la auditoría, se muestra un mensaje que indica que se está preparando el registro de auditoría y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información acerca del uso del registro de auditoría, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-configure-prerequisites-for-templates"></a>Paso 3 (opcional): configurar los requisitos previos para las plantillas

Algunas plantillas de administración de riesgos de Insider tienen requisitos previos que deben configurarse para que los indicadores de directiva generen alertas de actividad relevantes. Configure los requisitos previos adecuados en función de las directivas que tenga previsto configurar para su organización.

### <a name="configure-microsoft-365-hr-connector"></a>Configuración del conector de 365 de RRHH de Microsoft

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados de plataformas de administración de riesgos y recursos humanos de terceros. El conector de datos de recursos humanos de Microsoft 365 (HR) le permite extraer datos de recursos humanos de archivos. CSV, incluidos la finalización del usuario y las fechas del último empleo. Estos datos ayudan a impulsar indicadores de alertas en las directivas de administración de riesgos de Insider y es una parte importante de la configuración de la cobertura completa de administración de riesgos en la organización.

Consulte el tema sobre [Cómo configurar un conector para importar datos de recursos humanos](import-hr-data.md) para obtener una guía paso a paso sobre cómo configurar el conector de Microsoft 365 para la organización. Una vez que haya configurado el conector de recursos humanos, vuelva a estos pasos de configuración.

>[!IMPORTANT]
>Si configura una Directiva mediante la plantilla de *robo de datos de empleados* , tendrá que configurar el conector de recursos humanos para que use las características de detección de señal completa de la plantilla de directiva. Si configura más de un conector de recursos humanos para su organización, la administración de riesgos de Insider extrae automáticamente los indicadores de todos los conectores de recursos humanos.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar directivas de prevención de pérdida de datos (DLP)

La administración de riesgos de Insider admite el uso de directivas de DLP para ayudar a identificar la exposición intencionada o accidental de información confidencial a partes no deseadas. Al configurar una directiva de administración de riesgos de Insiders con la plantilla de *fugas de datos* , tiene que asignar una directiva de DLP específica a la Directiva.

Esta directiva ayuda a impulsar los indicadores de administración de riesgos de Insider para alertas de DLP de gravedad alta para información confidencial y es una parte importante de la configuración de la cobertura de administración de riesgos completa en la organización. Si configura más de una directiva de DLP para su organización, deberá asignar una directiva de administración de riesgos de Insider por directiva de DLP.

Consulte el tema [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso sobre la configuración de directivas de DLP para la organización. Una vez que haya configurado una directiva de DLP, vuelva a estos pasos de configuración.

>[!IMPORTANT]
>Asegúrese de que la configuración de **informes de incidentes** en la Directiva DLP para la administración de riesgos de Insiders usada con esta plantilla está configurada para alertas de nivel de gravedad *alto* . No se generarán alertas de administración de riesgos de Insider a partir de directivas de DLP con el campo **informes de incidentes** establecido en *bajo* o *medio*.

## <a name="step-4-required-configure-insider-risk-settings"></a>Paso 4 (obligatorio): configurar las opciones de riesgo de Insider

La configuración de los [riesgos de Insider](insider-risk-management-policies.md#policy-settings) se aplica a todas las directivas de administración de riesgos de Insider, independientemente de la plantilla que elija al crear una directiva. La configuración se configura con el control de **configuración de riesgos de Insider** ubicado en la parte superior de todas las pestañas de administración de riesgos de Insider. Esta configuración controla la privacidad, los indicadores, las ventanas de supervisión y las detecciones inteligentes.

Antes de configurar una directiva, defina las siguientes opciones de riesgo de Insider:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider** en la esquina superior derecha de cualquier página.
2. En la página **privacidad** , seleccione una configuración de privacidad para mostrar los nombres de usuario de las alertas de directiva.
3. En la página **indicadores** , seleccione los indicadores de alerta que desea aplicar a todas las directivas de riesgo de Insider.

    >[!IMPORTANT]
    >Para recibir alertas de actividad arriesgada definida en las directivas, debe seleccionar uno o más indicadores.

4. En la página **plazos** de la Directiva, seleccione los [plazos](insider-risk-management-policies.md#policy-timeframes) de la Directiva para que se apliquen a un usuario cuando desencadenen una coincidencia para una directiva de riesgos de Insider.
5. En la página **detecciones inteligentes** , configure las [detecciones de idiomas ofensivos y anomalías](insider-risk-management-policies.md#intelligent-detections) para las directivas de riesgos de Insider.
6. Seleccione **Guardar** para habilitar esta configuración para las directivas de riesgos de Insider.

## <a name="step-5-required-create-an-insider-risk-management-policy"></a>Paso 5 (obligatorio): crear una directiva de administración de riesgos de Insider

Las directivas de administración de riesgos de Insider incluyen usuarios asignados y definen qué tipos de indicadores de riesgo se configuran para las alertas. Antes de que las actividades puedan desencadenar alertas, debe configurarse una directiva.

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. Seleccione **crear Directiva** para abrir el Asistente para directivas
3. En la página **nueva Directiva de riesgo de Insider** , complete los campos siguientes:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la Directiva.
    - **Descripción (opcional)**: escriba una descripción para la Directiva.
    - **Elegir plantilla de directiva (obligatorio)**: Seleccione una de las [plantillas de directiva](insider-risk-management-policies.md#policy-templates) para definir los tipos de indicadores de riesgo que se supervisan mediante la Directiva.

    >[!IMPORTANT]
    >Si selecciona la plantilla de *fugas de datos* , tendrá que configurar al menos una directiva DLP que asignará más adelante en el asistente. Si selecciona la plantilla de *robo de datos de empleado* de la que se descargan, tendrá que configurar el conector de recursos humanos para que use las características de detección de señal completa de la plantilla de directiva.

4. Seleccione **siguiente** para continuar.
5. En la página **usuarios** , seleccione **Agregar usuario o grupo** para definir los usuarios que se incluirán en la Directiva o Active la casilla de verificación **todos los usuarios y grupos con correo habilitado** . Seleccione **siguiente** para continuar.
6. En la página **especificar el contenido que va a priorizar (opcional)** , puede asignar los orígenes para priorizar las actividades de usuario arriesgadas:
    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar información confidencial escriba** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
7. Seleccione **siguiente** para continuar.
8. En la **Página indicadores de alerta** , verá los indicadores que ha definido en la página**indicadores** de configuración > de **riesgos de Insider**. Si seleccionó la plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** .
9. En la página **seleccionar ventana de supervisión** , verá las condiciones de la [ventana de supervisión](insider-risk-management-policies.md#policy-timeframes) para la Directiva que se encuentra en la página intervalos de tiempo de la**Directiva** de configuración > de **riesgo del Insider**. Si ha seleccionado la plantilla de directiva de *robo de datos de empleado* de cancelación, puede seleccionar la casilla comprobar la *interrupción posterior* a la actividad para detectar la actividad después de la fecha de finalización importada desde el conector de 365 de RRHH de Microsoft.
10. Seleccione **siguiente** para continuar.
11. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para crear y activar la Directiva.

Una vez que haya completado estos pasos para crear su primera Directiva de administración de riesgos de Insider, empezará a recibir alertas de los indicadores de actividad después de aproximadamente 24 horas. Configure directivas adicionales según sea necesario siguiendo las instrucciones del paso 4 de este tema o los pasos en [crear una nueva Directiva de riesgos de Insider](insider-risk-management-policies.md#create-a-new-policy).
