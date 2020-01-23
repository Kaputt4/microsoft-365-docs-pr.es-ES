---
title: Introducción a la administración de riesgos de Insider (versión preliminar)
description: Configure la administración de riesgos de Insiders en su organización.
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5d32e28d53fccbb16d935bbd9348ad7c12bac365
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259848"
---
# <a name="get-started-with-insider-risk-management-preview"></a>Introducción a la administración de riesgos de Insider (versión preliminar)

Use directivas de administración de riesgos de Insider para identificar actividades arriesgadas y las herramientas de administración para emprender acciones en las alertas de riesgos de la organización. Para obtener más información sobre cómo las directivas de riesgos de Insider pueden ayudarle a administrar el riesgo en su organización, consulte [Administración de riesgos de Insider en Microsoft 365](insider-risk-management.md).

>[!IMPORTANT]
>La solución de administración de riesgos de Insider de Microsoft 365 proporciona una opción de nivel de inquilino para ayudar a los clientes a facilitar el control interno en el nivel de usuario. Los administradores de nivel de inquilino pueden configurar permisos para proporcionar acceso a esta solución a los miembros de la organización y configurar conectores de datos en el centro de cumplimiento de Microsoft 365 para importar los datos relevantes para admitir la identificación de nivel de usuario de posibles actividad arriesgada. Los clientes reconocen la información relacionada con el comportamiento, el personaje o el rendimiento de los usuarios individuales relacionados con el empleo que el administrador puede calcular y poner a disposición de otros usuarios de la organización.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar con la administración de riesgos de Insider, debe confirmar la suscripción a Microsoft 365. Los usuarios incluidos en las directivas de administración de riesgos de internación deben tener una licencia de cumplimiento de Microsoft 365 E5 o estar incluidas en una suscripción a Microsoft 365 E5.

Si no tiene un plan de Microsoft 365 Enterprise E5 existente y desea probar la administración de riesgos de Insider, puede [Agregar microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) a su suscripción existente de Office 365 o [registrarse para obtener una versión de prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 Enterprise E5.

Complete estos pasos para configurar y usar la administración de riesgos de Insider en la organización de Microsoft 365:

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Paso 1 (obligatorio): habilitar permisos para la administración de riesgos de Insider

Hay cuatro roles de permisos que se usan para configurar y administrar la administración de riesgos de Insider. Para continuar con estos pasos de configuración, los administradores de espacios empresariales deben asignarle primero el rol de **Administrador de administración de riesgos de Insider** .

| **Rol** | **Permisos de funciones** |
| ---- | ---------------- |
| **Administrador de administración de riesgos de Insider** | Crear, leer, actualizar y eliminar directivas de administración de riesgos de Insider <br> Crear, leer, actualizar y eliminar roles y permisos de administración de riesgos de Insider |
| **Analistas de administración de riesgos de Insider** | Acceso a todas las alertas, casos y avisos de administración de riesgos de Insider |
| **Investigadores de administración de riesgos de Insider** | Acceso a todas las alertas de administración de riesgos de Insider, casos, avisos y el explorador de contenido para todos los casos |
| **Visor de administración de riesgos de Insider** | Acceso de solo lectura a todas las alertas de administración de riesgos de Insider, casos, avisos y el explorador de contenido para todos los casos |

En función de la estructura del equipo de administración del cumplimiento, tiene dos opciones de permiso para configurar funciones para administrar las características de administración de riesgos de Insider. Elija una de estas opciones de administración de roles al configurar la administración de riesgos de Insider:

1. **Use el grupo de roles predeterminado de administración de riesgos de Insider**: Use este grupo de roles para administrar la administración de riesgos de Insider en su organización agregando todas las cuentas de usuario para los administradores, analistas e investigadores designados en un único grupo. Este grupo de roles contiene todos los roles de permisos de administración de riesgos de Insider. Esta es la forma más sencilla de empezar rápidamente con la administración de riesgos de Insider y es una buena opción para las organizaciones que no necesitan permisos separados definidos para grupos de usuarios independientes.
2. **Crear grupos distintos para diferentes roles de administración**: para las organizaciones que necesitan separar permisos para configurar y administrar la administración de riesgos de Insider, deberá crear nuevos grupos de roles y asignar los roles y usuarios adecuados a los nuevos grupos. Por ejemplo, si desea tener distintos permisos para el análisis e investigaciones de administración de riesgos de Insider, deberá crear un grupo para los analistas y un grupo independiente para los investigadores. Para cada grupo, asignará las funciones necesarias para estas responsabilidades y, a continuación, agregará los usuarios que se deben asignar al grupo.

Si decide configurar grupos diferentes para diferentes roles, use la tabla siguiente para asignar las funciones necesarias a cada grupo de roles:

| **Ejemplo de grupo** | **Roles necesarios** |
| ---- | ---------------- |
| **Administradores** | Rol de *Administrador de administración de riesgos del Insider* |
| **Analistas** | Rol de *analistas de administración de riesgos de Insider* <br> Rol de *Administración de casos* |
| **Investigadores** | Rol de *investigadores de administración de riesgos de Insider* <br> Rol de *Administración de casos* |

### <a name="option-1-add-users-to-the-insider-risk-management-role-group"></a>Opción 1: agregar usuarios al grupo de funciones de administración de riesgos de Insider

Si desea usar un grupo de roles para todos los usuarios que configuran y administran la administración de riesgos de Insider, siga los pasos que se indican a continuación para agregar usuarios al grupo de funciones predeterminado de **Administración de riesgos de Insider** :

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de seguridad y cumplimiento de Microsoft Office 365, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo de roles *Administración de riesgos de Insider* y seleccione **Editar Grupo de roles**.

4. Seleccione **elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, marque la casilla de verificación para todos los usuarios que desee agregar al grupo de roles.

6. Seleccione **Agregar**y haga clic en **listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **cerrar** para completar los pasos.

### <a name="option-2-create-a-new-role-group"></a>Opción 2: crear un nuevo grupo de roles

Si necesita crear grupos de roles independientes para diferentes roles de administración, realice los siguientes pasos para crear cada grupo:

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de seguridad y cumplimiento de Microsoft Office 365, vaya a **permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione **Crear**.

4. En el campo **nombre** , asigne un nombre descriptivo al nuevo grupo de roles. Seleccione **Siguiente**.

5. Seleccione **elegir roles** y, después, haga clic en **Agregar**. Marque la casilla de verificación de los roles que necesita asignar. Por ejemplo, si este grupo es para analistas de riesgos de Insider, seleccione el rol *analistas de administración de riesgos de Insider* y el rol de *Administración de casos* y, a continuación, seleccione **Agregar** y **listo**. Seleccione **Siguiente**.

6. Seleccione **elegir miembros** y, a continuación, seleccione **Agregar**. Marque la casilla de verificación para todos los usuarios y grupos que desee que creen directivas y administre los mensajes con coincidencias de directivas y, a continuación, seleccione **Agregar** y **listo**. Seleccione **Siguiente**.

7. Seleccione **Crear grupo de funciones** para finalizar.

Para obtener más información acerca de los grupos de roles y los permisos, consulte [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-optional-configure-the-microsoft-365-human-resources-data-connector"></a>Paso 2 (opcional): configurar el conector de datos de recursos humanos de Microsoft 365

La administración de riesgos de Insider admite la importación de datos de usuario y registro importados de plataformas de administración de riesgos y recursos humanos de terceros. El conector de datos de recursos humanos de Microsoft 365 (HR) le permite extraer datos de recursos humanos de archivos. CSV, incluidos la finalización del usuario y las fechas del último empleo. Estos datos ayudan a impulsar los indicadores de alerta en las directivas de administración de riesgos de Insider y es una parte importante de la configuración de la cobertura completa de administración de riesgos en la organización.

Consulte el tema sobre [Cómo configurar un conector para importar datos de recursos humanos](import-hr-data.md) para obtener una guía paso a paso sobre cómo configurar el conector de Microsoft 365 para la organización. Una vez que haya configurado el conector de recursos humanos, vuelva a estos pasos de configuración.

>[!IMPORTANT]
>Si tiene previsto configurar una Directiva mediante la plantilla de *robo de datos de empleados* , tendrá que configurar el conector de recursos humanos para que use las características de detección de señal completa de la plantilla de directiva. Si configura más de un conector de recursos humanos para su organización, la administración de riesgos de Insider extrae automáticamente los indicadores de todos los conectores de recursos humanos.

## <a name="step-3-optional-configure-data-loss-prevention-dlp-policies"></a>Paso 3 (opcional): configurar directivas de prevención de pérdida de datos (DLP)

La administración de riesgos de Insider admite el uso de directivas de DLP para ayudar a identificar la exposición intencionada o accidental de información confidencial a partes no deseadas. Al configurar una directiva de administración de riesgos de Insiders con la plantilla de *fugas de datos* , tiene que asignar una directiva de DLP específica a la Directiva. Esta directiva ayuda a impulsar los indicadores de alerta de información confidencial es una parte importante de la configuración de la cobertura de administración de riesgos completa en la organización.

Consulte el tema [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso sobre la configuración de directivas de DLP para la organización. Una vez que haya configurado una directiva de DLP, vuelva a estos pasos de configuración.

>[!IMPORTANT]
>Si tiene previsto configurar una Directiva mediante la plantilla de *fugas de datos* , tendrá que configurar al menos una directiva DLP para usar las características de detección de señal completa de la plantilla de directiva. Si configura más de una directiva de DLP para su organización, deberá asignar una directiva de administración de riesgos de Insider por directiva de DLP.

## <a name="step-4-required-create-an-insider-risk-management-policy"></a>Paso 4 (obligatorio): crear una directiva de administración de riesgos de Insider

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
8. En la página **elegir indicadores de alerta** , verá los indicadores que se incluyen en la plantilla que ha elegido para esta Directiva. Si seleccionó la plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** .
9. En la página **seleccionar ventana de supervisión** , definirá las [condiciones](insider-risk-management-policies.md#monitoring-windows) de la ventana de supervisión para la Directiva. Configure las ventanas de supervisión según corresponda.
10. Seleccione **siguiente** para continuar.
11. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para crear y activar la Directiva.

Una vez que haya completado estos pasos para crear su primera Directiva de administración de riesgos de Insider, empezará a recibir alertas de los indicadores de actividad después de aproximadamente 24 horas. Configure directivas adicionales según sea necesario siguiendo las instrucciones del paso 4 de este tema o los pasos en [crear una nueva Directiva de riesgos de Insider](insider-risk-management-policies.md#create-a-new-policy).
