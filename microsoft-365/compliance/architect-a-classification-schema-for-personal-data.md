---
title: Diseño de un esquema de clasificación de datos personales
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Determine si su organización pondrá en práctica las etiquetas como parte de su plan de Reglamento general de protección de datos (GDPR).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17484e56206ba8f32db3c779623f2f8d7ed57496
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035172"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>Diseño de un esquema de clasificación de datos personales

Los artículos anteriores de esta serie se centran en el uso de tipos de información confidencial para identificar datos personales que están sujetos al RGPD. Los tipos de información confidencial son una forma de clasificación. Esta puede ser toda la clasificación que necesita. Sin embargo, muchas organizaciones implementan una estrategia de gobierno de datos más amplia con etiquetas. Use este tema para decidir si también quiere implementar etiquetas como parte de su plan de RGPD. Si lo hace, este tema proporciona algunas directrices y ejemplos.

Nota: la definición de un esquema de clasificación para una organización y la configuración de directivas, etiquetas y condiciones requiere un diseño y una preparación cuidadosos. Es importante tener en cuenta que no se trata de un proceso basado en ti. Asegúrese de trabajar con su equipo legal y de cumplimiento para crear un esquema de etiquetado y clasificación adecuado para los datos de su organización.

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a>Decidir si debe utilizar etiquetas además de tipos de datos confidenciales

Puede tomar uno de los dos métodos para la clasificación de información personal en Microsoft 365. Puede usar cualquiera de estos para protección de RGPD. Si decide usar solo los tipos de información confidencial para clasificación, puede omitir el resto de este tema.

Elija una de las siguientes opciones.

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a>Opción 1: Usar solo los tipos de información confidencial de Microsoft 365

- Los tipos de información confidencial funcionan correctamente para identificar y proteger datos personales sujetos al RGPD y otros tipos de normas.

- Estos son más fáciles de usar si su organización ya no tiene o no va a implementar un plan de gobierno de datos más amplio con etiquetas.

- Estas funcionan con reglas DLP (como sucede con las etiquetas de retención).

- Los tipos de información confidencial funcionan con Cloud App Security para que pueda detectar información confidencial en otras aplicaciones SaaS.

### <a name="option-2-use-sensitive-information-types--retention-labels"></a>Opción 2: Usar tipos de información confidencial y etiquetas de retención

- Necesitará los tipos de información confidencial para aplicar automáticamente etiquetas a datos personales que están sujetos al RGPD, por lo que son un requisito previo.

- Usar etiquetas de retención le permite incluir información personal que está sujeta al RGPD en un plan de gobierno de datos más amplio para su organización.

## <a name="develop-a-label-schema-that-includes-personal-data"></a>Desarrollar un esquema de etiqueta que incluya datos personales

Antes de usar las funciones técnicas para aplicar las etiquetas y la protección, en primer lugar, puede trabajar en la organización para definir un esquema de clasificación. Es posible que su organización ya tenga un esquema de clasificación que facilite la adición de datos personales. Este tema incluye un esquema de clasificación de ejemplo. Si es necesario, puede usar este ejemplo como punto de partida.

### <a name="getting-started"></a>Introducción

Para empezar, decida el número y los nombres de las etiquetas que va a implementar. Hágalo sin preocuparse sobre la tecnología que debe usar y cómo se aplicarán las etiquetas. Aplique este esquema de forma universal en su organización, incluyendo a los datos que se encuentran en almacenamiento local y en otros servicios en la nube.

### <a name="recommendations"></a>Recomendaciones 

Al diseñar e implementar directivas, etiquetas y condiciones, tenga en cuenta estas recomendaciones:

- Use un esquema de clasificación existente (si lo hay) &ndash; muchas empresas ya usan la clasificación de datos en alguna forma. Evalúe atentamente el esquema de etiqueta existente y, si es posible, úselo como está. Usar etiquetas familiares que son reconocible para el usuario final llevará a cabo la adopción.

- Empiece con las directivas y etiquetas predeterminadas &ndash; todas las soluciones se incluyen con un conjunto de etiquetas y directivas predefinidas. Valore estas consideraciones en los requisitos empresariales y jurídicos de la organización y considere la posibilidad de usarlos en lugar de crear otros nuevos.

- Iniciar pequeña &ndash; no hay prácticamente ningún límite en el número de etiquetas que se pueden crear. Sin embargo, un gran número de etiquetas y subetiquetas afectarán negativamente a la adopción. Muchas opciones suelen significar que no hay ninguna opción.

- Use escenarios y casos de uso &ndash; identificar los casos de uso comunes en la organización y usar escenarios que se deriven de la GDPR para comprobar si la configuración de etiqueta y clasificación puede funcionar en la práctica.

- Pregunta en cada solicitud de una etiqueta nueva &ndash; ¿todos los escenarios o casos de uso necesitan una nueva etiqueta o pueden usar lo que ya tiene? Mantener el número de etiquetas en un mínimo mejora la adopción.

- Use subetiquetas para los departamentos clave &ndash; algunos departamentos tendrán necesidades específicas que requieran etiquetas específicas. Defina estas etiquetas como subetiquetas en una etiqueta existente y considere la posibilidad de usar directivas de ámbito que estén asignadas a grupos de usuarios en lugar de globalmente.

- Considere la posibilidad de usar directivas de ámbito &ndash; directivas dirigidas a subconjuntos de usuarios evitarán "sobrecarga de etiqueta". Una directiva con ámbito le permite asignar un rol o un departamento (subformulario) específico solo a los empleados que trabajan para ese departamento específico.

- Usar nombres de etiqueta significativos &ndash; recomendamos que no use jerga, estándares o acrónimos como nombres de etiqueta. Pruebe a usar nombres que tengan repercusión en el usuario final para mejorar la adopción. En lugar de usar etiquetas como PII, PCI, HIPAA, LBI, AC, y HBI, considere la posibilidad de usar nombres como no empresarial, público, general, confidencial y muy confidencial.

### <a name="example-classification-schema"></a>Ejemplo de esquema de clasificación

<table>
<thead>
<tr class="header">
<th align="left"><strong>Nombre de etiqueta</strong></th>
<th align="left"><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personal</td>
<td align="left">Datos no empresariales, únicamente para uso personal.</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">Datos profesionales preparados y aprobados específicamente para consumo público.</td>
</tr>
<tr class="odd">
<td align="left">Datos de cliente</td>
<td align="left">Datos profesionales que contienen información de identificación personal. Algunos ejemplos son números de tarjeta de crédito, números de cuentas bancarias y números de la Seguridad Social.</td>
</tr>
<tr class="even">
<td align="left">Datos de recursos humanos</td>
<td align="left">Datos de recursos humanos sobre los empleados de Contoso, como datos de número de empleado y salario.</td>
</tr>
<tr class="odd">
<td align="left">Confidencial</td>
<td align="left">Datos empresariales confidenciales que podrían causar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: contratos, informes de seguridad, resúmenes de previsión y datos de la cuenta de ventas.</td>
</tr>
<tr class="even">
<td align="left">Extremadamente confidencial</td>
<td align="left">Datos empresariales extremadamente confidenciales que podrían provocar daños a la empresa si se comparten con personas no autorizadas. Algunos ejemplos son: información de empleados y clientes, contraseñas, código fuente e informes financieros previamente anunciados.</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>Definir un criterio de búsqueda y de taxonomía en todas las etiquetas

Después de desarrollar un esquema de clasificación para su organización, el siguiente paso es desarrollar la taxonomía y los criterios de búsqueda para encontrar estos datos. En el caso de los datos personales, ya ha completado el trabajo mediante la identificación de los tipos de información confidencial y la personalización o la creación de nuevos tipos de información confidencial para su entorno.

La siguiente tabla proporciona un esquema de ejemplo, taxonomía y criterios de búsqueda de una organización. Las etiquetas están ordenadas por nivel de confidencialidad de menos confidenciales a más confidenciales para asegurar que los datos que coincidan con varias condiciones de etiqueta se asignan la etiqueta adecuada.

Nota: El ejemplo de configuración se proporciona únicamente con fines ilustrativos y no está pensado como guía de implementación o referencia.

Lo más importante es asegurarse de que el trabajo que dedica para clasificar los datos personales para cumplimiento de RGPD se adaptan a los objetivos de toda la organización.

### <a name="example-schema-taxonomy-and-search-criteria"></a>Esquema de ejemplo, taxonomía y criterios de búsqueda

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etiqueta</strong></th>
<th align="left"><strong>Taxonomía</strong></th>
<th align="left"><strong>Método</strong></th>
<th align="left"><strong>Sintaxis de búsqueda</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personal</td>
<td align="left">El usuario final ha etiquetado manualmente los documentos personales.</td>
<td align="left">Manual</td>
<td align="left">El usuario final ha etiquetado manualmente los documentos personales.</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">Documentos que contienen la frase “Aprobado para publicación ##/####” (que no distingue mayúsculas de minúsculas) donde # representa cualquier dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: aprobado para publicación*</p>
<p>RegEx: (?i)(\bAprobado para publicación \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Datos del cliente</td>
<td align="left">Tipos de información confidencial para datos de ciudadanos de la UE.</td>
<td align="left">Tipos de información confidencial</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Recursos humanos: datos de empleado</td>
<td align="left">Documentos que contienen el ID. de empleado que distingue mayúsculas de minúsculas en el formato CONTOSO-9##### donde # representa un número.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: CONTOSO-9*</p>
<p>RegEx: (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Recursos humanos: datos de sueldo</td>
<td align="left">Los documentos que incluyen la palabra clave Contoso (no distingue mayúsculas de minúsculas) y la palabra clave compensación o salario (no distingue mayúsculas de minúsculas)</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: Contoso Y (Salario O Compensación)</p>
<p>RegEx: (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">Confidencial</td>
<td align="left">Documentos que contienen la frase Confidencial de Contoso (no distingue mayúsculas de minúsculas).</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: Confidencial de Contoso</p>
<p>RegEx: (?i)(\bConfidencial de Contoso\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Extremadamente confidencial</td>
<td align="left">Documentos que incluyen la frase Secreto de Contoso (distingue mayúsculas de minúsculas) o Secreto-C#### donde # representa cualquier dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL: Secreto de Contoso O Secreto-C*</p>
<p>RegEx: (?i)(\bSecreto de Contoso\b)|(\bSecreto-C\d{4}\b)</p></td>
</tr>
</tbody>
</table>
