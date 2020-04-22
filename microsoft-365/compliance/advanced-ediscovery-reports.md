---
title: Informes avanzados de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 75e376288a85ca6def5cf3c3037f2faee57de63b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632275"
---
# <a name="advanced-ediscovery-reports-preview"></a>Informes avanzados de eDiscovery (versión preliminar)

Los informes avanzados de eDiscovery ayudan a agregar datos de casos en su organización para simplificar el análisis de datos y la creación de informes de la organización. La característica Advanced eDiscovery Reports incluye varios informes integrados que le ayudarán a responder preguntas como las siguientes:

- ¿Cuántos custodios activos hay en todos los casos de mi organización?

- ¿Cuántos orígenes de datos hay en espera para todos los casos de mi organización?

- ¿Cuántas notificaciones de retención se han emitido en el último mes para todos los casos de mi organización?

- ¿Cuántos casos activos y cerrados hay en mi organización?

## <a name="before-you-begin"></a>Antes de empezar

- Para obtener acceso a los informes avanzados de eDiscovery, debe ser miembro del grupo de roles de administración de eDiscovery. Ser miembro de este grupo de roles le proporciona los permisos necesarios para ver, filtrar y exportar los datos de los informes. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

- Los informes avanzados de eDiscovery se actualizan diariamente. Como resultado, es posible que se produzca un retraso cuando se crean nuevos casos, custodios, orígenes de datos y comunicaciones y cuando aparecen en el informe correspondiente.

Para acceder a los informes avanzados de eDiscovery:

1. Vaya a https://protection.office.com
  
2. Inicie sesión con su cuenta profesional o educativa.
  
3. En el centro de seguridad & cumplimiento, haga clic en **ediscovery > eDiscovery avanzado**.
  
   En la Página principal de **EDiscovery avanzado** , se muestran las pestañas caso, custodio, origen de datos y informe de comunicaciones en la parte superior de la página. 
  
   ![Informes avanzados de eDiscovery en la Página principal](../media/report-home.png)

5. Para ver un informe, haga clic en una ficha de informe y, a continuación, si es necesario, puede realizar una de las siguientes acciones:

   ![Puede filtrar o descargar datos de informes](../media/AeDReportsFilterDownload.png)

   a. Haga clic en **filtro** para restringir los datos del informe. Puede filtrar por diferentes propiedades para cada informe.
  
   b. Haga clic en **Descargar a CSV** para exportar los datos del informe a un archivo CSV.

## <a name="case-report"></a>Informe de casos

El informe de caso agrega información sobre los casos de eDiscovery anticipado activo y cerrado de la organización.

|Columna        |Descripción|
|:-------------|:-------------|
|IDENTIFICADOR de caso | Identificador único de cada caso.| 
|Nombre del caso | Nombre definido por el usuario del caso.|
|Estado | Indica si el caso está activo o cerrado.|
|Fecha de creación |Fecha: fecha en la que se creó el caso. Las fechas están en formato UTC.|
|Última modificación |La fecha en la que se cerró o se actualizó por última vez el caso. Las fechas están en formato UTC.| 
|||

## <a name="custodian-report"></a>Informe de custodios

En el flujo de trabajo de eDiscovery, las personas que están sujetas a una investigación o caso legal se denominan *custodios de datos* (o simplemente *custodios*) y se definen como "personas con control administrativo de un documento o un archivo electrónico". El informe de custodios le ayudará a identificar todos los custodios cuyos orígenes de datos se encuentran en espera para todos los casos de su organización.

|Columna         |Descripción|
|:-------------|:-------------|
|Nombre de custodio| El nombre del custodio en Active Directory.|
|UPN de custodio | El nombre principal de usuario del custodio.|
|IDENTIFICADOR de custodio | El identificador único para el custodio en un caso determinado. |
|Nombre del caso | Nombre definido por el usuario del caso.|
|Estado de retención | Indica si el custodio está actualmente en suspensión o si se ha lanzado desde el caso.|
|Identificador de caso | Identificador único del caso.|
|Estado de comunicación |Indica si el custodio ha emitido una notificación de retención legal o no. |
|Custodio agregado | La fecha en que se agregó el custodio al caso. Las fechas están en formato UTC.|
|||

## <a name="data-source-report"></a>Informe de origen de datos

Puede usar un caso de exhibición avanzada de documentos electrónicos para crear suspensiones y conservar el contenido que pueda ser relevante para el caso. Con las funciones avanzadas de conservación de la exhibición de documentos electrónicos, puede realizar suspensiones en custodios y sus orígenes de datos. Además, puede poner una retención no confidencial en buzones y en cuentas de OneDrive para la empresa. Puede usar el informe de orígenes de datos para agregar detalles sobre las ubicaciones de contenido en espera para todos los casos de su organización.

|Columna        |Descripción|
| -------------|-------------|
|IDENTIFICADOR de caso |Identificador único de cada caso. |
|Carga de trabajo |Indica el tipo de ubicación de contenido colocada en espera (por ejemplo, Exchange o SharePoint).
|Nombre de la ubicación |Indica la dirección SMTP (para buzones de Exchange) o la dirección URL (para los sitios de SharePoint) de la ubicación de contenido. | 
|IDENTIFICADOR de custodio |Si el origen de datos pertenece a un custodio, esta columna muestra el identificador único para el custodio en un caso determinado. Esta columna será nula para las ubicaciones que no sean de privación.|
|Nombre de custodio |El nombre del custodio en Active Directory.| 
|Nombre del caso |Nombre definido por el usuario del caso.| 
|Estado |Indica si la ubicación del contenido está actualmente en espera. | 
|IDENTIFICADOR de directiva de retención |El identificador único de la suspensión que contiene la ubicación del contenido. | 
|Fecha de creación de la suspensión |Indica la fecha en que se creó la Directiva de retención. Las fechas están en formato UTC. | 
|Nombre de la Directiva de retención |Nombre de la retención que contiene la ubicación del contenido. |
|Fecha de retención modificada |La fecha en que se modificó por última vez la retención. Las fechas están en formato UTC.| 
|Retención de última modificación realizada por|Nombre del usuario que modificó la retención por última vez.| 
|||

## <a name="communication-report"></a>Informe de comunicación

Su organización puede emitir notificaciones de retención legal para notificar a los custodios de su obligación de preservar la información relevante como parte del caso legal o la investigación. Puede usar el informe comunicaciones para ver los datos agregados en las confirmaciones, los avisos, las escalaciones y otros tipos de comunicaciones.

|Columna         |Descripción|
| -------------|-------------|
|IDENTIFICADOR de caso | Identificador único del caso.|
|Nombre del caso | Nombre definido por el usuario del caso.|
|IDENTIFICADOR de custodio |El identificador único del custodio en un caso determinado.|
|Nombre de custodio |El nombre del custodio.|
|Tipo de aviso |Indica el tipo de notificación que se emitió para el custodio.|
|Responsable de la expedición |El nombre del usuario que emitió la notificación de retención legal.|
|Evento de notificación|Indica el mensaje de notificación de suspensión legal enviado al usuario. Los valores posibles son: aviso, reasignación, confirmación y emisión de la suspensión.|
|Fecha de envío |La fecha en la que se emitió la comunicación. En el caso de las confirmaciones, esta columna indica el momento en el que el custodio reconoció el aviso. Las fechas están en formato UTC.|
|||
