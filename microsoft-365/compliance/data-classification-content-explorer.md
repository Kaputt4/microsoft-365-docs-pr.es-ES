---
title: Introducción al explorador de contenido
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: El explorador de contenido le permite ver elementos etiquetados de forma nativa.
ms.openlocfilehash: 7166f8916bdd0a207cb5b32fa67d90279246e9d0
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2022
ms.locfileid: "68794124"
---
# <a name="get-started-with-content-explorer"></a>Introducción al explorador de contenido

El explorador de contenido le permite ver de forma nativa los elementos que se han resumido en la página de información general.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="prerequisites"></a>Requisitos previos

Para conocer los requisitos de licencia, consulte [Information Protection: Análisis de clasificación de datos: información general sobre el explorador de contenido y actividades](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)

### <a name="permissions"></a>Permisos

Para obtener acceso a la pestaña del explorador de contenido, una cuenta debe tener asignada una suscripción en uno de estos roles o grupos de roles. 

**Grupos de roles de Microsoft 365**

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento

> [!IMPORTANT]
> La pertenencia a estos grupos de roles no le permite ver la lista de elementos en el explorador de contenido o ver el contenido de los elementos en el explorador de contenido.

> [!IMPORTANT]
> Solo los administradores globales pueden administrar o asignar permisos a otros usuarios en el portal de cumplimiento. Para obtener más información vea [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md).
> 
### <a name="required-permissions-to-access-items-in-content-explorer"></a>Permisos necesarios para acceder a elementos en el explorador de contenido

El acceso al explorador de contenidos está altamente restringido porque permite leer el contenido de los archivos digitalizados.

> [!IMPORTANT]
> Estos permisos reemplazan los permisos que se asignan a los elementos de forma local, lo que permite ver el contenido. 

Existen dos roles que conceden acceso al explorador de contenido y se conceden mediante el <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">portal de cumplimiento de Microsoft Purview</a>:

- **Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view. The `data classification list viewer` role has been pre-assigned to this role group.

- **Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list. The `data classification content viewer` role has been pre-assigned to this role group.

La cuenta que use para tener acceso al explorador de contenido debe estar en uno de los grupos de roles o en ambos. Estos son grupos de roles independientes y no son acumulativos. Por ejemplo, si desea conceder a una cuenta la capacidad para ver los elementos y sus ubicaciones únicamente, conceda a los derechos de visores de listas de explorador de contenido. Si desea que esa misma cuenta también pueda ver el contenido de los elementos de la lista, conceda los derechos de visor de contenido de explorador de contenido.

También puede asignar uno o ambos roles a un grupo de roles personalizado para ajustar el acceso a Content Explorer.

Un administrador global puede asignar el visor de listas del explorador de contenido cuando sea necesario y la pertenencia al grupo de funciones del visor del explorador de contenido.

#### <a name="roles-and-role-groups-in-preview"></a>Roles y grupos de roles en la versión preliminar

Hay roles y grupos de roles en la versión preliminar que puede probar para ajustar los controles de acceso.

Esta es una lista de los roles aplicables que se encuentran en versión preliminar. Para obtener más información sobre ellos, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Administrador de Information Protection
- Analista de Information Protection
- Investigador de protección de información
- Lector de protección de información

Esta es una lista de los grupos de roles aplicables que se encuentran en versión preliminar. Para obtener más información, consulte [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md).

- Protección de la información
- Administradores de Information Protection
- Analistas de Information Protection
- Investigadores de Information Protection
- Lectores de Information Protection

## <a name="content-explorer"></a>Explorador de contenido

El explorador de contenido muestra una instantánea actual de los elementos que tienen una etiqueta de confidencial, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Una [directiva DLP](dlp-learn-about-dlp.md) puede ayudar a proteger información confidencial, lo que se define como un **tipo de información confidencial**. Microsoft 365 incluye [definiciones para muchos tipos comunes de información confidencial](sensitive-information-type-entity-definitions.md) de muchas regiones diferentes y listas para su uso. Por ejemplo, un número de tarjeta de crédito, números de cuenta bancaria y números de identificación nacional.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Una [etiqueta de confidencialidad](sensitivity-labels.md) es simplemente una etiqueta que indica el valor que tiene el elemento para su organización. Se puede aplicar manualmente o automáticamente. Una vez aplicada, la etiqueta se inserta en el documento y seguirá el documento dondequiera que vaya. Una etiqueta de confidencialidad habilita varios comportamientos de protección, como, por ejemplo, la marca de agua o el cifrado obligatorios.

Las etiquetas de confidencialidad deben habilitarse para los archivos de SharePoint y OneDrive para que los datos correspondientes aparezcan en la página de clasificación de datos. Para más información, vea [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

### <a name="retention-labels"></a>Etiquetas de retención

Una [etiqueta de retención](retention.md) le permite definir durante cuánto tiempo se conserva un elemento con una etiqueta y los pasos que se deben seguir antes de eliminarlo. Se puede aplicar manualmente o de manera automática mediante directivas. Puede ayudar a su organización a mantener el cumplimiento normativo y los requerimientos legales.

### <a name="how-to-use-content-explorer"></a>Cómo usar el explorador de contenido

1. Abra **Portal de cumplimiento de Microsoft Purview**  > **Clasificación de datos** > **Explorador de contenido**.
2. Si sabe el nombre de la etiqueta o el tipo de información confidencial, puede escribirlo en el cuadro de filtro.
3. De forma alternativa, puede buscar el elemento expandiendo el tipo de etiqueta y seleccionando la etiqueta de la lista.
4. Seleccione una ubicación en **todas las ubicaciones** y profundice en la estructura de carpetas hasta el elemento.
5. Haga doble clic para abrir el elemento de forma nativa en el explorador de contenido.

### <a name="export"></a>Exportar
El control **export** creará un archivo .csv que contiene una lista del área de foco del panel.

![control de exportación de clasificación de datos.](../media/data_classification_export_control.png)


> [!NOTE]
> Los recuentos pueden tardar hasta *siete días* en actualizarse en el explorador de contenido.

### <a name="filter"></a>Filtro

Al explorar en profundidad una ubicación, como una carpeta de Exchange o Teams, o un sitio de SharePoint o OneDrive, aparece la herramienta **Filtro**.

![herramienta de búsqueda del explorador de contenido.](../media/data_classification_search_tool.png)

El ámbito de la herramienta de búsqueda es lo que se muestra en el panel **Todas las ubicaciones** y lo que puede buscar varía en función de la ubicación seleccionada. 

Cuando **Exchange** o **Teams** son la ubicación seleccionada, puede buscar en la dirección de correo electrónico completa del buzón, por ejemplo, `user@domainname.com`.

Cuando **SharePoint** o **OneDrive** están seleccionados, la herramienta de búsqueda aparecerá cuando profundice en nombres de sitio, carpetas y archivos. 

Puede buscar en:

|valor|ejemplo  |
|---------|---------|
|nombre completo del sitio    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|nombre de archivo    |    `RES_Resume_1234.txt`     |
|texto al principio del nombre de archivo| `RES`|
|texto después de un carácter de subrayado (_) en el nombre de archivo|`Resume` o `1234`| 
|extensión de archivo|`txt`|

## <a name="provide-matchnot-a-match-accuracy-feedback-in-content-explorer"></a>Proporcionar comentarios de coincidencia o no de precisión de coincidencia en el explorador de contenido

Puede ver el número de coincidencias que tiene una SIT o un clasificador entrenable en el **Explorador de contenido**. También puede proporcionar comentarios sobre si un elemento es realmente una coincidencia o no mediante el mecanismo de comentarios **Match**, **Not a Match** y usar esos comentarios para ajustar los clasificadores. Consulte [Aumento de la precisión del clasificador (versión preliminar)](data-classification-increase-accuracy.md) para obtener más información. 


## <a name="see-also"></a>Recursos adicionales

- [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Información sobre las directivas de retención y las etiquetas de retención](retention.md)
- [Definiciones de entidad de tipos de información confidencial.md](sensitive-information-type-entity-definitions.md)
- [Información sobre la prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md)
