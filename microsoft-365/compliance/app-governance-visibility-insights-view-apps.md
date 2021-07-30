---
title: Ver sus aplicaciones
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Ver sus aplicaciones.
ms.openlocfilehash: 5a11e161fb7b37405b61866599a616874ad4a190
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "53623031"
---
# <a name="view-your-apps"></a>Ver sus aplicaciones

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La gobernanza de aplicaciones de Microsoft le permite obtener rápidamente información detallada sobre las aplicaciones de Microsoft 365 de su espacio empresarial. Por ejemplo, puede ver:

- Una lista de aplicaciones habilitadas para OAuth en el usuario que usa la API de Microsoft Graph, junto con los metadatos de aplicación y los datos de uso pertinentes.
- Detalles de las aplicaciones con enfoques e información más detallados al seleccionar una aplicación en la lista.

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>Obtener una lista de todas las aplicaciones de su usuario

Para obtener un resumen de las aplicaciones de su usuario, diríjase a **Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Aplicaciones**.

![La página de resumen de la aplicación MAPG en el centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> Su cuenta de inicio de sesión debe tener uno de los [estos roles](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.
>

Verá una lista de aplicaciones y esta información:

- Nombre de la aplicación
- Editorial
- Certificación M365

  Indica si la aplicación es compatible con las tecnologías de Microsoft, cumple con los procedimientos recomendados de seguridad de aplicaciones en la nube, y es compatible con Microsoft.

- Última modificación

  Muestra la fecha en que se instaló la gobernanza de aplicaciones en el cliente si esa fecha es más reciente que la fecha de la última modificación de la aplicación.

- Fecha de instalación
- Nivel de privilegio
- Número de usuarios
- Acceso a datos

  La suma de la carga y descarga de datos de esta aplicación en el usuario durante el último día, junto con el cambio respecto al día anterior.

La gobernanza de aplicaciones ordena la lista de aplicaciones por **nombre de aplicación** de forma predeterminada. Para ordenar la lista por otro atributo de una aplicación, seleccione el nombre del atributo. 

También puede seleccionar **Buscar** para buscar una aplicación por nombre.

## <a name="getting-detailed-information-on-an-app"></a>Obtener información detallada sobre una aplicación

Para obtener información detallada sobre una aplicación específica de su usuario, vaya a **Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Página de aplicaciones > *nombre de la aplicación***.

![El panel de detalles de aplicaciones de gobernanza de aplicaciones en el Cetro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

El panel de detalles de la aplicación proporciona información adicional sobre estas pestañas:

| Nombre de la pestaña | Descripción |
|:-------|:-----|
| Detalles | Vea datos adicionales en la aplicación, como la fecha en que se consiente por primera vez y el identificador de la aplicación. Para ver las propiedades de la aplicación como registrada en Azure AD, seleccione **Ver aplicación en Azure AD**. |
| Uso |Vea los datos a los que accede la aplicación en el espacio empresarial y trace el uso de datos para los recursos de SharePoint y Exchange. |
| Usuarios | Vea una lista de los usuarios que usan la aplicación, si son una cuenta prioritaria y la cantidad de datos descargados y cargados. |
| Permisos | Vea un resumen de los permisos concedidos y usados por la aplicación y la lista de permisos específicos. Vea la [referencia de los permisos de Microsoft Graph](/graph/permissions-reference)para obtener más información. |
|||

Para una aplicación habilitada, también puede usar el control **Deshabilitar la aplicación** para deshabilitar el uso de la aplicación seleccionada o el control **Habilitar la aplicación** para habilitar el uso de una aplicación deshabilitada. Estas acciones requieren los siguientes roles de administrador:

- Administrador de cumplimiento
- Administrador global
- Administrador de seguridad
- Operador de seguridad

## <a name="next-step"></a>Paso siguiente

[Determine la posición general de cumplimiento de la aplicación](app-governance-visibility-insights-compliance-posture.md).
