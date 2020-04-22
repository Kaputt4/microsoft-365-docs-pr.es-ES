---
title: Configuración de la puntuación de cumplimiento de Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo configurar y empezar a usar la puntuación de cumplimiento de Microsoft, que ayuda a simplificar y automatizar las evaluaciones de riesgos.
ms.openlocfilehash: 4ccd89647540aeda8ba6253f6e5eefab1dc81791
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632395"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Configuración de la puntuación de cumplimiento de Microsoft (versión preliminar)

## <a name="before-you-begin"></a>Antes de empezar

El administrador global de Microsoft 365 para su organización probablemente será el primer usuario para obtener acceso a la puntuación de cumplimiento. Le recomendamos que inicie sesión en el administrador global y establezca los permisos de usuario como se describe a continuación cuando visite la puntuación de cumplimiento por primera vez.

## <a name="sign-in"></a>Iniciar sesión

1. Vaya al [centro de cumplimiento de microsoft 365](https://compliance.microsoft.com/) e **inicie sesión** con su cuenta de administrador global de Microsoft 365.
2. Seleccione **puntuación de cumplimiento** en el panel de navegación izquierdo. A continuación, debería ver el [Panel de puntuación de cumplimiento con su puntuación](#understand-the-compliance-score-dashboard).

El vínculo directo para obtener la puntuación de cumplimiento [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore)es:.

## <a name="set-user-permissions-and-assign-roles"></a>Establecimiento de permisos de usuario y asignación de roles

La puntuación de cumplimiento usa un modelo de permisos de control de acceso basado en roles (RBAC). Solo los usuarios a los que se les asigna un rol pueden obtener acceso a la puntuación de cumplimiento y las acciones permitidas por cada usuario están restringidas por el tipo de función.

### <a name="where-to-set-permissions"></a>Dónde establecer permisos

El administrador global de su organización puede establecer permisos de usuario en el centro de cumplimiento de Microsoft 365 o en Azure Active Directory (Azure AD). Una vez que las funciones se establecen en cualquiera de estas ubicaciones, los usuarios pueden acceder a la puntuación de cumplimiento y al administrador de cumplimiento.

Tenga en cuenta que los roles del administrador de cumplimiento **existentes no se** transfieren a la puntuación de cumplimiento. Si tiene un rol en el administrador de cumplimiento y es nuevo en la puntuación de cumplimiento, el rol de administrador de cumplimiento no le concederá acceso a la puntuación de cumplimiento. El administrador global tendrá que establecer permisos y un rol para usted en el centro de cumplimiento de Microsoft 365 o en Azure AD para que pueda obtener acceso a la puntuación de cumplimiento.

### <a name="role-types"></a>Tipos de funciones

En la tabla siguiente se muestra cómo cada rol del centro de cumplimiento de Microsoft 365 se asigna a los roles del administrador de cumplimiento existentes y las funciones permitidas por cada rol.


| El usuario puede: | Rol del centro de cumplimiento de 365 de Microsoft | Rol de administrador de cumplimiento | 
| :------------- | :-------------: | :------------: |
| **Leer los datos pero no modificarlos**| Lector global de Azure AD  | Lector global de Azure AD | 
| **Leer los datos pero no modificarlos**| Lector de seguridad | Lector del administrador de cumplimiento  | 
| **Editar datos**| Administrador de cumplimiento | Colaborador del administrador de cumplimiento | 
| **Editar los resultados de la prueba**| Administrador de cumplimiento | Asesor del administrador de cumplimiento | 
| **Administrar evaluaciones y datos de plantilla y espacio empresarial**| Administrador de cumplimiento<br>Administrador de datos de cumplimiento<br>Administrador de seguridad | Administrador del administrador de cumplimiento | 
| **Asignar usuarios**| Administrador global | Administrador del portal | 

> [!NOTE]
> Cuando pase de la puntuación de cumplimiento al administrador de cumplimiento para completar una tarea (por ejemplo, para administrar las evaluaciones), el explorador abrirá una nueva pestaña y aparecerá un cuadro de diálogo. En la sección superior con el encabezado, "¿ya es un cliente de Microsoft Cloud Services? Inicie sesión en su cuenta, "seleccione **iniciar sesión** para obtener acceso al administrador de cumplimiento; no tendrá que volver a escribir sus credenciales.

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>Cómo establecer permisos y roles en el centro de cumplimiento de Microsoft 365

Para establecer permisos en el centro de cumplimiento de Microsoft 365:

1. Vaya al [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) e inicie sesión con su cuenta de administrador global.
2. Seleccione **permisos** en el panel de navegación izquierdo. Desde aquí, puede ver roles y asignar permisos.

## <a name="configure-automatic-secure-score-updates"></a>Configurar actualizaciones de calificación segura automáticas

De forma predeterminada, todos los nuevos inquilinos tienen activada la opción actualizaciones automáticas de [puntuación segura](../security/mtp/microsoft-secure-score.md) . Todas las acciones que se supervisan con calificación segura actualizarán automáticamente el estado de la misma acción en la puntuación de cumplimiento.

El administrador global puede administrar esta configuración para desactivar las actualizaciones automáticas para todas las acciones, o bien establecer actualizaciones para las acciones de forma individual.

Durante la versión preliminar pública, tendrá que ir al portal de confianza del servicio de Microsoft (donde está ubicado el administrador de cumplimiento) para administrar las actualizaciones de puntuación segura.

Para administrar las actualizaciones de calificaciones seguras automáticas, siga estos pasos:

1. Inicie sesión en el [portal de confianza de servicios](https://servicetrust.microsoft.com) con su cuenta de administrador global.

2. En la barra de menús del portal de confianza del servicio superior, en **más**, seleccione **Administrador** y, después, seleccione **configuración**.

3. En la ficha **puntuación segura** , seleccione el botón correspondiente para **activar todas las acciones**, **desactivar para todas las acciones**o **establecer por acción.**

Si elige **establecer por acción,** siga estos pasos adicionales para activar las actualizaciones de puntuación segura para acciones individuales:

4. Seleccione **Administrador de cumplimiento** en el menú superior (no seleccione "Administrador de cumplimiento (clásico)", que es un producto heredado).

5. Seleccione **Administración de inquilinos** en la esquina superior derecha de la pantalla.

6. En el panel **acciones del cliente** , busque la acción prevista con puntos suspensivos (**...**) en la columna **acciones afectadas** . Haga clic en los puntos suspensivos y seleccione **Editar.**

7. Cambie el conmutador de alternancia de **actualización continua de puntuación segura** a **activado.**

8. Seleccione **Guardar.** Puntuación segura la supervisión continua ahora está activada para esa acción.

**Nota:** Solo el administrador global puede activar o desactivar las actualizaciones automáticas para todas las acciones. El administrador del administrador de cumplimiento puede activar actualizaciones automáticas para acciones individuales, pero no para todas las acciones de forma global.

Obtenga más información sobre la [Administración de actualizaciones de calificaciones seguras](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Descripción del panel de calificaciones de cumplimiento

El panel de calificaciones de cumplimiento está diseñado para proporcionar una vista inmediata de la postura de cumplimiento actual.

![Puntuación de cumplimiento: panel](../media/compliance-score-dashboard.png "Panel de calificaciones de cumplimiento")

### <a name="overall-compliance-score"></a>Puntuación de cumplimiento general

La puntuación de cumplimiento se presenta destacadamente en la parte superior. Muestra un porcentaje basado en puntos que se alcanzan para completar acciones de mejora que abordan los estándares y regulaciones clave de protección de datos.

Cuando llega a la puntuación de cumplimiento por primera vez, su puntuación inicial se basa en la línea de base de protección de datos de Microsoft 365 integrada: un conjunto de controles que incluye normas y estándares comunes de la industria. Como la puntuación de cumplimiento examina el sistema de soluciones de Microsoft 365 existentes, ofrece una evaluación inicial de su postura de cumplimiento según la configuración de privacidad y seguridad que la organización habilita actualmente.

A medida que agregue evaluaciones relevantes para su organización, su puntuación será incluso más significativa. Obtenga más información sobre [cómo se calcula su puntuación](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Acciones para la mejora de claves

En esta sección se enumeran las acciones de mejora más importantes que puede realizar ahora para hacer el mayor impacto positivo en la puntuación de cumplimiento general.

### <a name="solutions-that-affect-your-score"></a>Soluciones que afectan a su calificación

En esta sección se muestran soluciones que contienen acciones con la mayor oportunidad de afectar positivamente su puntuación y el número de acciones de mejora pendientes en cada solución.

### <a name="compliance-score-breakdown"></a>Desglose de puntuación de cumplimiento

En esta sección se ofrece una vista más detallada de su puntuación de dos maneras diferentes:

- **Categorías**: muestra el porcentaje de la puntuación general dentro de las categorías de protección de datos, como "proteger la información" o "administrar dispositivos".
- **Evaluaciones**: muestra el porcentaje de su progreso en la administración de las evaluaciones para normas, regulaciones o leyes de protección de datos y cumplimiento en particular, como RGPD o NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrar la vista del panel

Puede filtrar la vista del panel para ver solo los elementos relacionados con las normativas y normas particulares, las soluciones, el tipo de acción, los [grupos de evaluaciones que configure](working-with-compliance-manager.md#groups)o las categorías de protección de datos. Filtrar la vista de esta manera también filtrará la puntuación en el panel, indicando cuántos puntos ha obtenido del total de puntos posibles en función de los criterios del filtro.

Para aplicar filtros:

1. Seleccione **filtrar** en la parte superior derecha del panel.
2. Seleccione los criterios de filtro en el panel desplegable **filtros** y, después, seleccione **aplicar**.

Después de aplicar un filtro, verá su puntuación ajustada en tiempo real. El porcentaje de puntuación de cumplimiento e información desglosada, y las acciones y soluciones de mejora, ahora solo pertenecen a los datos cubiertos por los criterios de filtro. Si sale de la puntuación de cumplimiento, la vista filtrada permanecerá cuando vuelva a iniciar sesión.

Para quitar filtros:

- En el encabezado de **filtros aplicados** encima de la puntuación de cumplimiento, seleccione la **X** junto al filtro individual que quiera quitar; o
- Seleccione **filtrar** en la parte superior derecha del panel y, a continuación, seleccione **Borrar filtros**.

## <a name="next-step"></a>Siguiente paso

Visite [trabajar con la puntuación de cumplimiento](working-with-compliance-score.md) para comprender el flujo de trabajo de cómo emprender acciones para mejorar su puntuación.