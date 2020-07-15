---
title: Aplicación de etiquetas a datos personales
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a utilizar las etiquetas de Office como parte de su plan de protección de la Normativa general de protección de datos (GDPR).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126821"
---
# <a name="apply-labels-to-personal-data"></a>Aplicación de etiquetas a datos personales

 Use este tema si utiliza las etiquetas de clasificación como parte de su plan de protección de RGPD. 

Si utiliza etiquetas para la protección de datos personales de Microsoft 365, Microsoft recomienda que empiece con las [etiquetas de retención](retention.md#retention-labels). Con las etiquetas de retención, puede:
- Usar el Gobierno de datos avanzado para aplicar automáticamente etiquetas con tipos de información confidencial u otros criterios.
- Usar etiquetas de retención con la prevención de pérdida de datos para aplicar la protección. 
- Usar etiquetas con eDiscovery y Búsqueda de contenido. 

Cloud App Security actualmente no admite etiquetas de retención, pero puede usar tipos de información confidencial de Microsoft 365 con Cloud App Security para supervisar los datos personales que residen en otras aplicaciones SaaS.

Actualmente se recomiendan las [etiquetas de confidencialidad](sensitivity-labels.md) para la aplicación de etiquetas a archivos locales y en otros proveedores y servicios en la nube. Estas también se recomiendan para los archivos de Microsoft 365 que requieren el cifrado de Azure Information Protection (AIP) para la protección de datos, como archivos de secreto comercial.

En este momento, no se recomienda usar Azure Information Protection para aplicar el cifrado a archivos en Microsoft 365 con datos que están sujetos al RGPD. Los servicios de Microsoft 365 actualmente no pueden leer archivos cifrados AIP. Por ello, el servicio no puede encontrar datos confidenciales en dichos archivos.

Pueden aplicarse etiquetas de confidencialidad a correo en Exchange Online que funcionan con la prevención de pérdida de datos de Microsoft 365. 

![Etiquetas de Microsoft 365 y de Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


En la ilustración:

-   Use las etiquetas de retención para los datos personales y archivos secretos empresariales muy regulados en SharePoint Online y OneDrive para la Empresa.
-   Los tipos de información confidencial de Microsoft 365 pueden usarse en Microsoft 365 y con Cloud App Security para supervisar datos personales que residen en otras aplicaciones SaaS.
-   Use las etiquetas de confidencialidad para archivos secretos empresariales muy regulados, correo electrónico de Exchange Online, archivos en otros servicios SaaS, archivos en centros de datos locales y archivos de otros proveedores en la nube.


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>Uso de etiquetas de retención y tipos de información confidencial en Microsoft 365 para la protección de información

En la ilustración siguiente se muestra cómo pueden aprovecharse las etiquetas de retención y los tipos de información confidencial en las directivas de etiquetas, de prevención de pérdida de datos y de Cloud App Security.

![Etiquetas y tipos de información confidencial de Office](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Elementos de clasificación</strong></th>
<th align="left"><strong>Directivas de etiqueta: 2 ejemplos</strong></th>
<th align="left"><strong>Directivas de prevención de pérdida de datos: 2 ejemplos</strong></th>
<th align="left"><strong>Directivas de Cloud App Security para todas las aplicaciones SaaS: 1 ejemplo</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Etiquetas de retención. Ejemplos: personal, público, datos de clientes, datos de recursos humanos, confidencial, extremadamente confidencial</td>
<td align="left"><p>Auto apply this label . . .</p>
<p>Datos de cliente</p>
<p>. . . to documents that match these sensitive information types . . .</p>
<p>&lt;lista de ejemplos de información confidencial disponibles&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;definir la protección&gt;</p>
<p>. . . to documents with this label . . .</p>
<p>Datos de cliente</p></td>
<td align="left"><p>Alert when files with these attributes . . .</p>
<p>Elija uno o varios atributos: atributo PII predefinido, tipo de información confidencial de Microsoft 365, etiqueta de confidencialidad (AIP), expresión personalizada.</p>
<p>. . . en cualquier aplicación de SaaS autorizada se comparten fuera de la organización</p><p>Nota: las etiquetas de retención actualmente no se admiten en Cloud App Security.</td>
</tr>
<tr class="even">
<td align="left">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</td>
<td align="left"><p>Publish these labels for users to manually apply . . .</p>
<p>&lt;seleccionar etiquetas&gt;</p>
<p>. . . to these locations . . .</p>
<p>&lt;todas las ubicaciones o elegir ubicaciones específicas&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;definir la protección&gt;</p>
<p>. . . to documents that match these sensitive information types&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>Asignar prioridades a las directivas de etiqueta de aplicación automática

For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.

The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.

### <a name="one-label-at-a-time"></a>Una etiqueta de cada vez

Solo puede aplicar una etiqueta a un documento.

### <a name="older-auto-apply-policies-win"></a>Las directivas de aplicación automática antiguas tienen prioridad

If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente

Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.

### <a name="auto-assigned-labels-can-be-updated"></a>Las etiquetas asignadas automáticamente pueden actualizarse

Las directivas de etiqueta más recientes o las actualizaciones de directivas existentes pueden actualizar etiquetas asignadas automáticamente.

Asegúrese de que su plan para implementar etiquetas incluye:

- Dar prioridad al orden en que se crean las directivas de aplicación automática.

- Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>Prioridad de ejemplo para crear directivas de aplicación automática

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etiquetas</strong></th>
<th align="left"><strong>Orden de prioridad para crear directivas de aplicación automática</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Recursos humanos: datos de empleado</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">Datos de cliente</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">Extremadamente confidencial</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">Recursos humanos: datos de sueldo</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">Confidencial</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">Personal</td>
<td align="left">Directiva que no es de aplicación automática</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>Crear etiquetas y aplicar directivas de etiqueta automáticamente

Cree etiquetas y directivas en el centro de seguridad o el centro de cumplimiento.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Paso</strong></th>
<th align="left"><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Conceda permisos a los miembros de su equipo de cumplimiento.</p></td>
<td align="left"><p>Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</p>
<p>Vea <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Proporcionar acceso a los usuarios al centro de seguridad y/o el centro de cumplimiento</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Crear etiquetas de retención.</p></td>
<td align="left">Vaya a Clasificaciones en el centro de seguridad o el centro de cumplimiento, elija Etiquetas de retención y cree las etiquetas para su entorno.</td>
</tr>
<tr class="odd">
<td align="left"><p>Cree directivas de aplicación automática para etiquetas.</p></td>
<td align="left">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</td>
</tr>
</tbody>
</table>

La siguiente ilustración muestra cómo crear una etiqueta de aplicación automática para la etiqueta Datos de cliente.

![Crear y aplicar una etiqueta de datos de cliente](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

En la ilustración:

- Se crea la etiqueta "Datos de cliente".

- Se listan los tipos de información confidencial deseados para RGPD: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia

- Crear una directiva de aplicación automática asigna la etiqueta "Datos de cliente" a cualquier archivo que contenga uno de los tipos de información confidencial que añada a la directiva.
