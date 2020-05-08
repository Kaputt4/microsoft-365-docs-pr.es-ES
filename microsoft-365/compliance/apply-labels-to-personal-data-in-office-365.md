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
ms.openlocfilehash: 42cfc73433a7087f0f5dd62f2da9b27b5a3cf48d
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165263"
---
# <a name="apply-labels-to-personal-data"></a><span data-ttu-id="78dbe-103">Aplicación de etiquetas a datos personales</span><span class="sxs-lookup"><span data-stu-id="78dbe-103">Apply labels to personal data</span></span>

 <span data-ttu-id="78dbe-104">Use este tema si utiliza las etiquetas de clasificación como parte de su plan de protección de RGPD.</span><span class="sxs-lookup"><span data-stu-id="78dbe-104">Use this topic if you're using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="78dbe-105">Si utiliza etiquetas para la protección de datos personales de Microsoft 365, Microsoft recomienda que empiece con las [etiquetas de retención](labels.md).</span><span class="sxs-lookup"><span data-stu-id="78dbe-105">If you're using labels for protection of personal data in Microsoft 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="78dbe-106">Con las etiquetas de retención, puede:</span><span class="sxs-lookup"><span data-stu-id="78dbe-106">With retention labels, you can:</span></span>
- <span data-ttu-id="78dbe-107">Usar el Gobierno de datos avanzado para aplicar automáticamente etiquetas con tipos de información confidencial u otros criterios.</span><span class="sxs-lookup"><span data-stu-id="78dbe-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
- <span data-ttu-id="78dbe-108">Usar etiquetas de retención con la prevención de pérdida de datos para aplicar la protección.</span><span class="sxs-lookup"><span data-stu-id="78dbe-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="78dbe-109">Usar etiquetas con eDiscovery y Búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="78dbe-109">Use labels with eDiscovery and Content Search.</span></span> 

<span data-ttu-id="78dbe-110">Cloud App Security actualmente no admite etiquetas de retención, pero puede usar tipos de información confidencial de Microsoft 365 con Cloud App Security para supervisar los datos personales que residen en otras aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="78dbe-110">Cloud App Security doesn't currently support retention labels, but you can use Microsoft 365 sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="78dbe-111">Actualmente se recomiendan las [etiquetas de confidencialidad](sensitivity-labels.md) para la aplicación de etiquetas a archivos locales y en otros proveedores y servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="78dbe-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="78dbe-112">Estas también se recomiendan para los archivos de Microsoft 365 que requieren el cifrado de Azure Information Protection (AIP) para la protección de datos, como archivos de secreto comercial.</span><span class="sxs-lookup"><span data-stu-id="78dbe-112">These are also recommended for files in Microsoft 365 that require Azure Information Protection encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="78dbe-113">En este momento, no se recomienda usar Azure Information Protection para aplicar el cifrado a archivos en Microsoft 365 con datos que están sujetos al RGPD.</span><span class="sxs-lookup"><span data-stu-id="78dbe-113">At this time, using Azure Information Protection to apply encryption is not recommended for files in Microsoft 365 with data that is subject to the GDPR.</span></span> <span data-ttu-id="78dbe-114">Los servicios de Microsoft 365 actualmente no pueden leer archivos cifrados AIP.</span><span class="sxs-lookup"><span data-stu-id="78dbe-114">Microsoft 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="78dbe-115">Por ello, el servicio no puede encontrar datos confidenciales en dichos archivos.</span><span class="sxs-lookup"><span data-stu-id="78dbe-115">Therefore, the service can't find sensitive data in these files.</span></span>

<span data-ttu-id="78dbe-116">Pueden aplicarse etiquetas de confidencialidad a correo en Exchange Online que funcionan con la prevención de pérdida de datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78dbe-116">Retention labels can be applied to mail in Exchange Online and these labels work with Microsoft 365 data loss prevention.</span></span> 

![Etiquetas de Microsoft 365 y de Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="78dbe-118">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="78dbe-118">In the illustration:</span></span>

-   <span data-ttu-id="78dbe-119">Use las etiquetas de retención para los datos personales y archivos secretos empresariales muy regulados en SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="78dbe-119">Use retention labels for personal data and for highly regulated and trade secret files in SharePoint Online and OneDrive for Business.</span></span>
-   <span data-ttu-id="78dbe-120">Los tipos de información confidencial de Microsoft 365 pueden usarse en Microsoft 365 y con Cloud App Security para supervisar datos personales que residen en otras aplicaciones SaaS.</span><span class="sxs-lookup"><span data-stu-id="78dbe-120">Microsoft 365 sensitive information types can be used within Microsoft 365 and with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>
-   <span data-ttu-id="78dbe-121">Use las etiquetas de confidencialidad para archivos secretos empresariales muy regulados, correo electrónico de Exchange Online, archivos en otros servicios SaaS, archivos en centros de datos locales y archivos de otros proveedores en la nube.</span><span class="sxs-lookup"><span data-stu-id="78dbe-121">Use sensitivity labels for highly regulated and trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="78dbe-122">Uso de etiquetas de retención y tipos de información confidencial en Microsoft 365 para la protección de información</span><span class="sxs-lookup"><span data-stu-id="78dbe-122">Use retention labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="78dbe-123">En la ilustración siguiente se muestra cómo pueden aprovecharse las etiquetas de retención y los tipos de información confidencial en las directivas de etiquetas, de prevención de pérdida de datos y de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="78dbe-123">The following illustration shows how retention labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Etiquetas y tipos de información confidencial de Office](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="78dbe-125">Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="78dbe-125">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78dbe-126"><strong>Elementos de clasificación</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-126"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="78dbe-127"><strong>Directivas de etiqueta: 2 ejemplos</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-127"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="78dbe-128"><strong>Directivas de prevención de pérdida de datos: 2 ejemplos</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-128"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="78dbe-129"><strong>Directivas de Cloud App Security para todas las aplicaciones SaaS: 1 ejemplo</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-129"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="78dbe-130">Etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="78dbe-130">Retention labels.</span></span> <span data-ttu-id="78dbe-131">Ejemplos: personal, público, datos de clientes, datos de recursos humanos, confidencial, extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="78dbe-131">Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="78dbe-p105">Aplicar automáticamente esta etiqueta...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="78dbe-135">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="78dbe-135">Customer data</span></span></p>
<p><span data-ttu-id="78dbe-p106">...a documentos que coincidan con estos tipos de información confidencial...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="78dbe-142">&lt;lista de ejemplos de información confidencial disponibles&gt;</span><span class="sxs-lookup"><span data-stu-id="78dbe-142">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="78dbe-p107">Aplicar esta protección...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="78dbe-146">&lt;definir la protección&gt;</span><span class="sxs-lookup"><span data-stu-id="78dbe-146">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="78dbe-p108">...a documentos con esta etiqueta...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="78dbe-153">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="78dbe-153">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="78dbe-p109">Enviar alerta cuando los archivos con estos atributos...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="78dbe-157">Elija uno o varios atributos: atributo PII predefinido, tipo de información confidencial de Microsoft 365, etiqueta de confidencialidad (AIP), expresión personalizada.</span><span class="sxs-lookup"><span data-stu-id="78dbe-157">Choose one or more attributes: predefined PII attribute, Microsoft 365 sensitive information type, sensitivity label (AIP), custom expression</span></span></p>
<p><span data-ttu-id="78dbe-158">.</span><span class="sxs-lookup"><span data-stu-id="78dbe-158">.</span></span> <span data-ttu-id="78dbe-159">.</span><span class="sxs-lookup"><span data-stu-id="78dbe-159">.</span></span> <span data-ttu-id="78dbe-160">.</span><span class="sxs-lookup"><span data-stu-id="78dbe-160">.</span></span> <span data-ttu-id="78dbe-161">en cualquier aplicación de SaaS autorizada se comparten fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="78dbe-161">in any sanctioned SaaS app are shared outside the organization</span></span></p><p><span data-ttu-id="78dbe-162">Nota: las etiquetas de retención actualmente no se admiten en Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="78dbe-162">Note: Retention labels are currently not supported in Cloud App Security.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="78dbe-p111">Tipos de información confidencial. Ejemplos: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="78dbe-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="78dbe-p112">Publicar estas etiquetas para los usuarios para aplicar manualmente...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="78dbe-168">&lt;seleccionar etiquetas&gt;</span><span class="sxs-lookup"><span data-stu-id="78dbe-168">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="78dbe-p113">...a estas ubicaciones...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="78dbe-175">&lt;todas las ubicaciones o elegir ubicaciones específicas&gt;</span><span class="sxs-lookup"><span data-stu-id="78dbe-175">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="78dbe-p114">Aplicar esta protección...</span><span class="sxs-lookup"><span data-stu-id="78dbe-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="78dbe-179">&lt;definir la protección&gt;</span><span class="sxs-lookup"><span data-stu-id="78dbe-179">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="78dbe-p115">...a documentos que coincidan con estos tipos de información confidencial&gt;</span><span class="sxs-lookup"><span data-stu-id="78dbe-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="78dbe-184">Asignar prioridades a las directivas de etiqueta de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="78dbe-184">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="78dbe-p116">Para los datos personales que están sujetos a RGPD, Microsoft recomienda aplicar etiquetas automáticamente mediante tipos de información confidencial que gestione en su entorno. Es importante que las directivas de aplicación automática de etiquetas estén bien diseñadas y probadas para asegurar que se produce el comportamiento esperado.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="78dbe-p117">El orden en que las directivas de aplicación automática se crean y si los usuarios aplican o no estas etiquetas afectan al resultado. Por lo tanto, es importante planear cuidadosamente la distribución. Esto es lo que necesita saber.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="78dbe-189">Una etiqueta de cada vez</span><span class="sxs-lookup"><span data-stu-id="78dbe-189">One label at a time</span></span>

<span data-ttu-id="78dbe-190">Solo puede aplicar una etiqueta a un documento.</span><span class="sxs-lookup"><span data-stu-id="78dbe-190">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="78dbe-191">Las directivas de aplicación automática antiguas tienen prioridad</span><span class="sxs-lookup"><span data-stu-id="78dbe-191">Older auto-apply policies win</span></span>

<span data-ttu-id="78dbe-p118">Si hay varias reglas que asignan una etiqueta de aplicación automática y el contenido cumple las condiciones de varias reglas, se asigna la etiqueta de la regla más antigua. Por este motivo, es importante planear minuciosamente las directivas de etiqueta antes de configurarlas. Si una organización necesita un cambio en la prioridad de las directivas de etiqueta, tendrá que eliminarlas y volver a crearlas.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="78dbe-195">Las etiquetas de usuario aplicadas manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente</span><span class="sxs-lookup"><span data-stu-id="78dbe-195">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="78dbe-p119">Las etiquetas que el usuario aplica manualmente tienen prioridad sobre las etiquetas aplicadas automáticamente. Las directivas de aplicación automática no pueden reemplazar una etiqueta que ya ha aplicado un usuario, pero los usuarios pueden reemplazar las etiquetas que se aplican automáticamente.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="78dbe-199">Las etiquetas asignadas automáticamente pueden actualizarse</span><span class="sxs-lookup"><span data-stu-id="78dbe-199">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="78dbe-200">Las directivas de etiqueta más recientes o las actualizaciones de directivas existentes pueden actualizar etiquetas asignadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="78dbe-200">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="78dbe-201">Asegúrese de que su plan para implementar etiquetas incluye:</span><span class="sxs-lookup"><span data-stu-id="78dbe-201">Be sure your plan for implementing labels includes:</span></span>

- <span data-ttu-id="78dbe-202">Dar prioridad al orden en que se crean las directivas de aplicación automática.</span><span class="sxs-lookup"><span data-stu-id="78dbe-202">Prioritizing the order that auto-apply policies are created.</span></span>

- <span data-ttu-id="78dbe-p120">Permita el tiempo suficiente para que las etiquetas se apliquen automáticamente antes de implementarlas para que los usuarios las apliquen manualmente. Pueden ser necesarios hasta siete días para que las etiquetas se apliquen a todo el contenido que coincida con las condiciones.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="78dbe-205">Prioridad de ejemplo para crear directivas de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="78dbe-205">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78dbe-206"><strong>Etiquetas</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-206"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="78dbe-207"><strong>Orden de prioridad para crear directivas de aplicación automática</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-207"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="78dbe-208">Recursos humanos: datos de empleado</span><span class="sxs-lookup"><span data-stu-id="78dbe-208">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="78dbe-209">1</span><span class="sxs-lookup"><span data-stu-id="78dbe-209">1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="78dbe-210">Datos de cliente</span><span class="sxs-lookup"><span data-stu-id="78dbe-210">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="78dbe-211">2</span><span class="sxs-lookup"><span data-stu-id="78dbe-211">2</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="78dbe-212">Extremadamente confidencial</span><span class="sxs-lookup"><span data-stu-id="78dbe-212">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="78dbe-213">3</span><span class="sxs-lookup"><span data-stu-id="78dbe-213">3</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="78dbe-214">Recursos humanos: datos de sueldo</span><span class="sxs-lookup"><span data-stu-id="78dbe-214">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="78dbe-215">4</span><span class="sxs-lookup"><span data-stu-id="78dbe-215">4</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="78dbe-216">Confidencial</span><span class="sxs-lookup"><span data-stu-id="78dbe-216">Confidential</span></span></td>
<td align="left"><span data-ttu-id="78dbe-217">5</span><span class="sxs-lookup"><span data-stu-id="78dbe-217">5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="78dbe-218">Público</span><span class="sxs-lookup"><span data-stu-id="78dbe-218">Public</span></span></td>
<td align="left"><span data-ttu-id="78dbe-219">6</span><span class="sxs-lookup"><span data-stu-id="78dbe-219">6</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="78dbe-220">Personal</span><span class="sxs-lookup"><span data-stu-id="78dbe-220">Personal</span></span></td>
<td align="left"><span data-ttu-id="78dbe-221">Directiva que no es de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="78dbe-221">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="78dbe-222">Crear etiquetas y aplicar directivas de etiqueta automáticamente</span><span class="sxs-lookup"><span data-stu-id="78dbe-222">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="78dbe-223">Cree etiquetas y directivas en el centro de seguridad o el centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78dbe-223">Create labels and policies in the security center or the compliance center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="78dbe-224"><strong>Paso</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-224"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="78dbe-225"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="78dbe-225"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78dbe-226">Conceda permisos a los miembros de su equipo de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78dbe-226">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="78dbe-p121">Los miembros de su equipo de cumplimiento que vayan a crear etiquetas necesitan permisos para usar el centro de seguridad y/o el centro de cumplimiento. Vaya a los permisos en el centro de seguridad o el centro de cumplimiento y modifique los miembros del grupo Administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p121">Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="78dbe-229">Vea <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Proporcionar acceso a los usuarios al centro de seguridad y/o el centro de cumplimiento</a>.</span><span class="sxs-lookup"><span data-stu-id="78dbe-229">See <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Give users access to the security center and/or the compliance center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="78dbe-230">Crear etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="78dbe-230">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="78dbe-231">Vaya a Clasificaciones en el centro de seguridad o el centro de cumplimiento, elija Etiquetas de retención y cree las etiquetas para su entorno.</span><span class="sxs-lookup"><span data-stu-id="78dbe-231">Go to Classifications in the Security center or the Compliance center, choose Retention labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="78dbe-232">Cree directivas de aplicación automática para etiquetas.</span><span class="sxs-lookup"><span data-stu-id="78dbe-232">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="78dbe-p122">Vaya a Clasificación en el Centro de seguridad y cumplimiento, elija Directivas de etiqueta y cree las directivas de aplicación automática de etiquetas. Asegúrese de crear estas directivas en el orden de la prioridad.</span><span class="sxs-lookup"><span data-stu-id="78dbe-p122">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="78dbe-235">La siguiente ilustración muestra cómo crear una etiqueta de aplicación automática para la etiqueta Datos de cliente.</span><span class="sxs-lookup"><span data-stu-id="78dbe-235">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![Crear y aplicar una etiqueta de datos de cliente](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="78dbe-237">En la ilustración:</span><span class="sxs-lookup"><span data-stu-id="78dbe-237">In the illustration:</span></span>

- <span data-ttu-id="78dbe-238">Se crea la etiqueta "Datos de cliente".</span><span class="sxs-lookup"><span data-stu-id="78dbe-238">The "Customer data" label is created.</span></span>

- <span data-ttu-id="78dbe-239">Se listan los tipos de información confidencial deseados para RGPD: número nacional de Bélgica, número de tarjeta de crédito, número de carnet de identidad de Croacia, documento de identidad nacional de Finlandia</span><span class="sxs-lookup"><span data-stu-id="78dbe-239">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

- <span data-ttu-id="78dbe-240">Crear una directiva de aplicación automática asigna la etiqueta "Datos de cliente" a cualquier archivo que contenga uno de los tipos de información confidencial que añada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="78dbe-240">Create an auto-apply policy assigns the label "Customer data" to any file that includes one of the sensitive information types that you add to the policy.</span></span>
