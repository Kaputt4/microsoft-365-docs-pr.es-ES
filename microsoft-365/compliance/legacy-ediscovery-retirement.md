---
title: Retirada de herramientas heredadas de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place exhibición de documentos electrónicos y retención In-Place (y los cmdlets de PowerShell correspondientes) en Exchange Online se retirarán en la primera mitad de 2020. El cmdlet Search-Mailbox y Advanced eDiscovery v1.0 también se retiran en el mismo período de tiempo.
ms.openlocfilehash: 77a7daf36c86cd302f774e5a4b934148d3dfd5a7
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341001"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Retirada de herramientas heredadas de eDiscovery

> [!IMPORTANT]
> La funcionalidad de las herramientas de exhibición de documentos electrónicos heredadas descritas en este artículo se ha quitado del servicio Microsoft 365 o sigue disponible, pero ya no es compatible. Cualquier funcionalidad que aún esté disponible puede quitarse sin previo aviso. Si sigue usando cualquiera de estas herramientas heredadas, considere la posibilidad de migrar a las herramientas de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365 o una de las alternativas descritas en este artículo.

A lo largo de los años, Microsoft ha proporcionado herramientas de exhibición de documentos electrónicos que le permiten buscar, obtener una vista previa y exportar contenido de correo electrónico desde Exchange Online. Sin embargo, estas herramientas ya no ofrecen una forma eficaz de buscar contenido que no sea de Exchange en otros servicios Microsoft 365, como SharePoint Online y Microsoft 365 Groups. Para solucionar esto, Microsoft ofrece otras herramientas de exhibición de documentos electrónicos que le ayudarán a buscar una amplia variedad de Microsoft 365 contenido. Y hemos estado trabajando duro para incorporar la funcionalidad de exhibición de documentos electrónicos más actual y eficaz en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com). Esto permite a las organizaciones responder a solicitudes legales, internas y de otro tipo de documentos de contenido en muchos Microsoft 365, incluidos Exchange Online.

Como resultado de esta nueva y mejorada funcionalidad de exhibición de documentos electrónicos en Centro de cumplimiento de Microsoft 365, estamos retirando las siguientes características y funciones relacionadas con la exhibición de documentos electrónicos relacionadas con la búsqueda de contenido de correo electrónico en Exchange Online y Microsoft 365:

- [Exhibición de](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) documentos [](/exchange/security-and-compliance/create-or-remove-in-place-holds) electrónicos local y retenciones locales en el centro Exchange administración local.

- Los cmdlets Exchange Online PowerShell que admiten In-Place eDiscovery y In-Place Holds (estos cmdlets se identifican colectivamente como cmdlets **-MailboxSearch).* Esto incluye los cmdlets siguientes:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Los cmdlets [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) y [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) estarán disponibles después de que se retiren los demás cmdlets ****-MailboxSearch*** para que pueda usarlos para ayudarle en la transición a otras herramientas de exhibición de documentos electrónicos y retención. Sin embargo, después de una fecha determinada (citado a continuación), el soporte técnico de Microsoft ya no admitirá estos dos cmdlets.

- El [cmdlet Search-Mailbox](/powershell/module/exchange/search-mailbox) en Exchange Online PowerShell.

- Las siguientes operaciones en la API Exchange Web Services:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [eDiscovery avanzado de Office 365 v1.0](./overview-ediscovery-20.md), que es la primera versión de Advanced eDiscovery a la que se tiene acceso a través de un caso de exhibición de documentos electrónicos principal en el Centro de Office 365 seguridad & cumplimiento. La retirada de Advanced eDiscovery v1.0 no afecta a su capacidad para crear y administrar casos de exhibición de documentos electrónicos principales.

> [!NOTE]
> La funcionalidad de exhibición de documentos electrónicos que se retira solo se aplica a las versiones basadas en la nube de Microsoft 365 y Office 365. La funcionalidad de exhibición de documentos electrónicos en versiones locales de Exchange y SharePoint seguirá siendo compatible hasta nuevo aviso.

Las secciones siguientes de este artículo proporcionan instrucciones sobre cada característica que se va a retirar. Esta información, incluidas las escalas de tiempo y las herramientas alternativas que puede usar en lugar de la herramienta retirada.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery and In-Place Holds en el Centro Exchange administración 

Según el anuncio original del 1 de julio de 2017, se retirará la funcionalidad de retención de In-Place eDiscovery & en el Centro de administración de Exchange (EAC). La In-Place de exhibición de documentos electrónicos & en el EAC le permitía buscar, retener y exportar contenido desde Exchange Online. In-Place eDiscovery también le permite copiar los resultados de búsqueda en un buzón de correo de detección para que usted u otros administradores de exhibición de documentos electrónicos puedan revisar el contenido y que esté disponible para solicitudes legales, reglamentarias y públicas.

Dado que todas estas funcionalidades (excepto para copiar resultados de búsqueda en un buzón de correo de detección) ahora están disponibles en las herramientas de búsqueda de contenido, exhibición de documentos electrónicos y Advanced eDiscovery en [Centro de cumplimiento de Microsoft 365](./microsoft-365-compliance-center.md) (con funcionalidad mejorada, confiabilidad y compatibilidad con una amplia variedad de servicios de Microsoft 365), se recomienda empezar a usar estas herramientas lo antes posible. Para ayudarle en la transición a estas otras herramientas de exhibición de documentos electrónicos, en la tabla siguiente se enumeran las herramientas que puede usar en lugar de In-Place eDiscovery y In-Place Hold.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 Enterprise organizaciones

- Office 365 y Microsoft 365 Educación organizaciones

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Escala de tiempo para la retirada

- 1 de julio de 2020: no podrá crear nuevas búsquedas y retenciones, pero aún puede ejecutar, editar y eliminar búsquedas existentes bajo su propio riesgo. El soporte técnico de Microsoft ya no In-Place las & de exhibición de documentos electrónicos en el EAC.

- 1 de octubre de 2020: la funcionalidad In-Place eDiscovery & holds en el EAC se colocará en modo de solo lectura. Esto significa que solo podrás quitar las búsquedas y retenciones existentes.

### <a name="alternative-tools"></a>Herramientas alternativas

En la tabla siguiente se describen otras herramientas que puede usar para reemplazar la funcionalidad existente que se está retirando.

<table>
<thead>
<tr class="header">
<th>Funcionalidad</th>
<th>Herramienta alternativa</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Búsqueda, exportación y retención con fines legales</td>
<td>Casos principales de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365 </td>
<td><p>El uso de las funcionalidades de los casos principales de exhibición de documentos electrónicos proporciona la paridad funcional para In-Place eDiscovery y In-Place holds. Esto incluye lo siguiente:</p>
<ul>
<li>
<p>La búsqueda escala a millones de ubicaciones</p>
</li>
<li>
<p>Mayor confiabilidad para buscar, exportar y poner contenido en espera</p>
</li>
<li>
<p>Buscar contenido en para Exchange Online, SharePoint Online, OneDrive para la Empresa, Skype Empresarial, Microsoft Teams, grupos de Yammer, grupos de Microsoft 365 y otro contenido almacenado en aplicaciones Office 365</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Retención con fines de retención</td>
<td>Directivas de retención en el Centro de cumplimiento de Microsoft 365</td>
<td><p>Puede usar directivas de retención para conservar el contenido y, si lo desea, eliminarlo después de que expire el período de retención. Otras funcionalidades incluyen:</p>
<ul>
<li>
<p>Aplicar directivas a toda la organización </p>
</li><li>
<p>Aplicar directivas a ubicaciones de contenido específicas, como Exchange Online, SharePoint Online, OneDrive para la Empresa, Skype Empresarial, Microsoft Teams y Office 365 grupos</p></li>
<li>
<p>Aplicar directivas a usuarios específicos</p></li></ul>
<p>Para obtener más información, vea <a href="/microsoft-365/compliance/retention-policies"> Learn about retention policies and retention labels</a>.</td>
</tr>
<tr class="odd">
<td>Copiar los resultados de la búsqueda de correo electrónico en un buzón de correo de detección para su revisión</td><td>Conjuntos de revisión en Advanced eDiscovery v2.0</td>
<td><p>Revisar el contenido en Microsoft 365 nunca ha sido más fácil. Los conjuntos de revisión tienen muchas capacidades excelentes para ayudar a reducir la cantidad de tiempo y datos necesarios para revisar, incluidos:</p>
<ul>
<li><p>Realizar consultas de búsqueda rápida y filtrar contenido en un conjunto de revisión</p></li>
<li><p>Analizar el contenido de un conjunto de revisión; esto incluye subprocesos de correo electrónico, detección casi duplicada, análisis de temas y codificación predictiva</p></li>
<li><p>Etiquetar documentos en un conjunto de revisión</p></li>
<li><p>Sugerencias de etiquetado para ayudar a identificar el contenido de privilegios de cliente de abogado</p></li></ul>
<p>Para más información, consulte<a href="/microsoft-365/compliance/overview-ediscovery-20"> información sobre la solución de eDiscovery avanzado en Microsoft 365</a>.</p>
<p>
<p>Como alternativa, puede exportar resultados de búsqueda a archivos PST y, a continuación, usar Microsoft 365 import service para importar los TSP a un buzón de correo de detección. Para obtener instrucciones paso a paso, vea <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.
</tr>
<tr class=even>
  <td>Copiar mensajes de un buzón a otro buzón</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para dar a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado deja su organización y necesita dar a otra persona acceso al correo electrónico del ex empleado), le recomendamos que asigne permisos a esa persona para tener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar elementos de buzón en otro buzón de usuario o en un buzón compartido, simplemente asigne a un usuario los permisos necesarios para tener acceso al buzón de origen.</td>
  
  </tr>
<tr class="odd">
<td>Restaurar elementos de la carpeta Elementos recuperables</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Puede restaurar elementos eliminados permanentemente <i></i> (también conocidos como elementos eliminados temporalmente) en los buzones, siempre que el período de retención de elementos eliminados para un elemento no haya expirado. Para obtener más información, vea <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Carpeta Elementos recuperables en Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Preguntas frecuentes sobre In-Place eDiscovery y In-Place holds

**Uso la funcionalidad copiar resultados de búsqueda de In-Place de exhibición de documentos electrónicos & en el EAC para copiar los resultados de la búsqueda en un buzón de correo de detección para su revisión por parte de los abogados. ¿Qué opciones tengo ahora?**

Hay dos maneras de replicar esta funcionalidad hoy en día. El primero es usar conjuntos [de revisión en Advanced eDiscovery v2.0](./view-documents-in-review-set.md). Los conjuntos de revisión tienen muchas de las mismas capacidades que se ven en una herramienta de revisión tradicional, como la búsqueda rápida de documentos, el etiquetado, el subproceso de correo electrónico, la agrupación casi duplicada, el análisis de temas y la codificación predictiva. Si aún desea usar buzones de detección para su revisión, la segunda opción es exportar los resultados de búsqueda a archivos PST y luego importar los archivos PST a un buzón de correo de detección mediante la característica de importación [de PST](use-network-upload-to-import-pst-files.md) en el Centro de cumplimiento de Microsoft.

**¿Cómo puedo controlar qué ubicaciones de contenido (como buzones o sitios) que un administrador de exhibición de documentos electrónicos puede buscar con las nuevas herramientas?**

El Centro de cumplimiento de Microsoft 365 también usa [límites de cumplimiento](set-up-compliance-boundaries.md) para controlar qué ubicaciones de contenido puede buscar un administrador de exhibición de documentos electrónicos. Los límites de cumplimiento son útiles en las entidades gubernamentales que necesitan mantenerse dentro de los límites de las agencias o las corporaciones multinacionales necesarias para respetar a los miembros de la junta geográfica.

**¿Cómo puedo mover mis búsquedas y retenciones actuales al Centro de cumplimiento de Microsoft 365?**

Es posible migrar las In-Place de exhibición de documentos electrónicos y las retenciones desde el EAC mediante PowerShell. Para obtener instrucciones, consulte [Migrate searches and holds from the EAC to the Centro de cumplimiento de Microsoft 365](./migrate-legacy-ediscovery-searches-and-holds.md).

## <a name="-mailboxsearch-cmdlets"></a>\*Cmdlets -MailboxSearch

Según el aviso original anunciado el 1 de julio de 2017 en el Centro de administración de Exchange, la funcionalidad de retención de In-Place eDiscovery & y los cmdlets **\* -MailboxSearch** correspondientes se están retirando. Estos cmdlets proporcionan a los usuarios la capacidad de buscar, retener y exportar contenido de buzones de correo para solicitudes legales, reglamentarias y públicas.

Dado que estas funcionalidades ya están disponibles en [<span class="underline">el</span>](./microsoft-365-compliance-center.md) PowerShell del Centro de seguridad Centro de cumplimiento de Microsoft 365 y Office 365 seguridad & con un rendimiento y escalabilidad mejorados, debe usar estos cmdlets mejorados. Estos cmdlets incluyen [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)y [<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 Enterprise organizaciones

- Office 365 y Microsoft 365 Educación organizaciones

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: No podrá usar **New-MailboxSearch** para crear nuevas búsquedas de exhibición de documentos electrónicos de In-Place y retenciones de In-Place, pero aún puede usar cmdlets para ejecutar, editar y eliminar las búsquedas y retenciones existentes bajo su propio riesgo. El soporte técnico de Microsoft ya no proporcionará asistencia para este tipo de búsquedas y retenciones.

- 1 de octubre de 2020: Como se ha indicado anteriormente, la funcionalidad In-Place eDiscovery & Holds en el EAC se colocará en modo de solo lectura. Esto también significa que no podrá usar los cmdlets **New-MailboxSearch**, **Start-MailboxSearch** o **Set-MailboxSearch.** Solo podrás obtener y quitar las búsquedas y retenciones existentes.

### <a name="alternative-tools"></a>Herramientas alternativas

En la tabla siguiente se describen otras herramientas que puede usar para reemplazar la funcionalidad existente que se está retirando.

<table>
<thead>
<tr class="header">
<th>Funcionalidad</th>
<th>Herramientas alternativas</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Búsqueda y exportación</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan juntos para ayudarle a buscar y exportar contenido. Puede crear una nueva búsqueda y ver la estimación de búsqueda mediante los cmdlets <strong>New-</strong>, <strong>Get-</strong>y <strong>Start-ComplianceSearch.</strong> A continuación, puede usar el cmdlet <strong>New-ComplianceSearchAction</strong> para exportar los resultados de la búsqueda. Todavía tendrás que usar la herramienta de exhibición de documentos electrónicos principal en el Centro de cumplimiento de Microsoft 365 descargar esos resultados de búsqueda en el equipo local.</p>
<p>
<p><strong>Nota:</strong> Si usa estos cmdlets para crear búsquedas que no están asociadas con un <strong></strong> caso principal de exhibición de documentos electrónicos, estas búsquedas se ubicarán en la página Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Retener contenido en un buzón</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Las retenciones en el Centro de cumplimiento de Microsoft 365 deben asociarse con un ComplianceCase. En primer lugar, cree el caso de cumplimiento y, a continuación, cree un CaseHoldPolicy y un CaseHoldRule.</p>
<p><strong>Nota:</strong> La creación de CaseHoldPolicy sin crear CaseHoldRule hará que la retención sea inoperable hasta que se cree CaseHoldRule y se asocie a CaseHoldPolicy. Consulte la documentación del cmdlet para obtener más información.</p></td>
</tr>
<tr class="odd">
<td>Copiar resultados de búsqueda en un buzón de correo de detección</td>
<td>Ninguno</td>
<td>No hay reemplazo directo para esta funcionalidad porque no proporciona acceso a todos los Microsoft 365 servicios. Consulta las siguientes preguntas más frecuentes para obtener soluciones alternativas.</td>
</tr>
  <tr class=even>
  <td>Copiar mensajes de un buzón a otro buzón</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para dar a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado deja su organización y necesita dar a otra persona acceso al correo electrónico del ex empleado), le recomendamos que asigne permisos a esa persona para tener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar elementos de buzón en otro buzón de usuario o en un buzón compartido, solo tiene que asignar permisos de usuario para tener acceso al buzón de origen.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Preguntas más frecuentes sobre los cmdlets ***-MailboxSearch**

**Usamos Copy Search para exportar mensajes de correo electrónico o mensajes instantáneos con fines de otra exhibición de documentos electrónicos e investigaciones legales. ¿Qué otras opciones tenemos después de retirar estos cmdlets?**

Las [<span class="underline">API de Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) proporcionan una serie de métodos para extraer datos para análisis y otros fines que son mucho más resistentes y escalables que el uso de los cmdlets **\* -MailboxSearch.**

**¿Cómo puedo migrar mis búsquedas y retenciones al Centro de cumplimiento de Microsoft 365?**

Es posible migrar las búsquedas In-Place eDiscovery y las retenciones desde el centro de administración de Exchange mediante un script de PowerShell. Para obtener más información, vea [Migrate legacy eDiscovery searches and holds to the Centro de cumplimiento de Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md).

**Una vez retirados los cmdlets, ¿seguiré siendo capaz de quitar o recuperar búsquedas?**

Sí, aunque quitamos la capacidad de crear y modificar búsquedas, seguirás siendo capaz de usar **Get-MailboxSearch** y **Remove-MailboxSearch hasta** nuevo aviso. Sin embargo, el uso de estos cmdlets correrá su propio riesgo después de las fechas de retiro y el Soporte técnico de Microsoft ya no podrá proporcionar asistencia.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

El cmdlet **Search-Mailbox** en Exchange Online PowerShell se está retirando como se anunció originalmente en una advertencia en el resultado del cmdlet a partir de 2018. El **cmdlet Search-Mailbox** se usó originalmente para buscar en el buzón de un usuario y purgar contenido malintencionado. Se recomienda empezar a usar los cmdlets **New-ComplianceSearch** y **New-ComplianceSearchAction** en powerShell del Centro de seguridad & de Office 365 para buscar y purgar contenido. Para una experiencia de seguridad [<span class="underline"></span>](../security/index.yml) integrada, las características de seguridad Microsoft 365 proporcionan una protección contra amenazas sólida para el correo electrónico y muchas otras servicios Microsoft.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 Enterprise organizaciones

- Office 365 y Microsoft 365 Educación organizaciones

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

-  1 de julio de 2020: El cmdlet **Search-Mailbox** ya no estará disponible y el soporte técnico de Microsoft ya no proporcionará asistencia.

### <a name="alternative-tools"></a>Herramientas alternativas

En la tabla siguiente se describen otras herramientas que puede usar para reemplazar la funcionalidad existente que se está retirando.

<table>
<thead>
<tr class="header">
<th>Funcionalidad</th>
<th>Herramientas alternativas</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Buscar en un buzón</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan juntos para ayudarle a buscar y exportar contenido. Puede crear una nueva búsqueda y ver la estimación de búsqueda mediante los cmdlets <strong>New-</strong>, <strong>Get-</strong>y <strong>Start-ComplianceSearch.</strong> A continuación, puede usar el <strong>comando New-ComplianceSearchAction -Export</strong> para exportar los resultados de la búsqueda. Todavía tendrás que usar la herramienta de exhibición de documentos electrónicos principal en el Centro de cumplimiento de Microsoft 365 descargar esos resultados de búsqueda en el equipo local.</p></p>
</td>
</tr>
<tr class="even">
<td>Eliminar correo electrónico masivo de un buzón</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">Configurar una directiva de archivo y eliminación para buzones de correo</span></a></p>
<p></p></td>
<td><p>Los administradores pueden crear una directiva de archivado y eliminación que mueva automáticamente los elementos al buzón de archivo de un usuario y elimine automáticamente los elementos del buzón.</p>
</td>
</tr>
<tr class="even">
<td>Copiar resultados de búsqueda en un buzón de correo de detección</td>
<td> </td>
<td>No hay reemplazo directo para esta funcionalidad porque no proporciona acceso a todos los Microsoft 365 servicios. Vea las preguntas más frecuentes en la <strong>sección Cmdlets *-MailboxSearch</strong> para obtener soluciones alternativas. </td>
</tr>
<tr class=odd>
  <td>Copiar mensajes de un buzón a otro buzón</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para dar a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado deja su organización y necesita dar a otra persona acceso al correo electrónico del ex empleado), le recomendamos que asigne permisos a esa persona para tener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar elementos de buzón en otro buzón de usuario o en un buzón compartido, simplemente asigne un permiso de usuario para tener acceso al buzón de origen.</td>
</tr>
<tr class=even>
  <td>Purgar mensajes de un buzón</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan juntos para ayudarle a buscar y purgar contenido. Puede crear y ejecutar una búsqueda con cmdlets <strong>New-ComplianceSearch</strong> y <strong>New-ComplianceSearch</strong> y, a continuación, puede purgar el contenido mediante el comando <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Para obtener más información, vea <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Buscar y eliminar mensajes</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Purgar mensajes de un buzón</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
<td>Para purgar mensajes de un buzón, asigne permisos de administrador para tener acceso al buzón del empleado. Los mensajes se pueden eliminar y reciclar según sea necesario aprovechando las capacidades integradas de búsqueda y visualización en Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Operaciones de api de servicios web

Estas operaciones en la API de servicios web de Exchange las usa la característica & de exhibición de documentos electrónicos de In-Place en el Centro de administración de Exchange y los cmdlets **\* -MailboxSearch** correspondientes en Exchange Online PowerShell. También se retirarán como parte de la retirada de las otras herramientas de exhibición de documentos electrónicos heredadas.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 Enterprise organizaciones

- Office 365 y Microsoft 365 Educación organizaciones

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: Las operaciones GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes y GetHoldOnMailboxes ya no estarán disponibles y el soporte técnico de Microsoft ya no proporcionará asistencia.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, que es la versión de Advanced eDiscovery disponible en un caso principal de exhibición de documentos electrónicos haciendo clic en Cambiar a **Advanced eDiscovery**, se está retirando. Su funcionalidad se ha reemplazado por la nueva [solución Advanced eDiscovery en](./ediscovery.md) el Centro de cumplimiento de Microsoft 365.

Para determinar si su organización usa Advanced eDiscovery v1.0:

1. Vaya al [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).

2. En el panel de navegación izquierdo del centro de cumplimiento, haga clic en **eDiscovery > Core** y abra un caso de eDiscovery principal.

3. Si ve el botón Cambiar **a Advanced eDiscovery,** al hacer clic en él, se le llevará a la versión 1.0 de Advanced eDiscovery, que se está retirando. La capacidad de crear y administrar casos en eDiscovery principal no se verá afectada. Solo se retirará la capacidad de agregar y analizar datos de casos en Advanced eDiscovery v1.0 (haciendo clic en Cambiar **a Advanced eDiscovery**).

La nueva solución de Advanced eDiscovery en Microsoft 365 (también conocida como *Advanced eDiscovery v2.0*) proporciona todas las capacidades de la solución original, pero ahora incluye un enfoque basado en custodia para identificar contenido en otros servicios de Microsoft 365, recopilar ese contenido y agregarlo a un conjunto de opiniones donde los revisores pueden aprovechar las consultas de búsqueda rápidas, etiquetas y características de análisis para ayudar a crear documentos relevantes. Advanced eDiscovery ahora incluye un procesamiento mejorado y visores nativos para tipos de archivo de Microsoft y no de Microsoft, una lista completa de tipos de archivo está [aquí](./supported-filetypes-ediscovery20.md) y los campos de metadatos admitidos están [aquí.](./document-metadata-fields-in-advanced-ediscovery.md) Además, la nueva solución de Advanced eDiscovery proporciona una característica de administración de retención de custodia eficaz que le permite aplicar retenciones al contenido de diferentes servicios, notificar a los usuarios las retenciones y realizar un seguimiento de las respuestas de los custodios, todo dentro de un caso Advanced eDiscovery.

Para acceder a eDiscovery avanzado v2.0:

1. Vaya al [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, luego, seleccione **eDiscovery > Avanzado**.

En este momento, se recomienda comenzar a realizar la transición del flujo de trabajo de exhibición de documentos electrónicos a la nueva Advanced eDiscovery de exhibición de documentos electrónicos. Si es necesario, puede archivar los Advanced eDiscovery casos 1.0 exportando el contenido y almacenándoselo sin conexión. Aunque todavía podrá tener acceso Advanced eDiscovery v1.0 en los casos existentes hasta el 31 de diciembre de 2020, el soporte técnico de Microsoft no proporcionará soporte técnico después del 1 de octubre de 2020. Consulta la siguiente escala de tiempo para obtener más detalles.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 Enterprise organizaciones

- Office 365 y Microsoft 365 Educación organizaciones

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: no podrá crear nuevos Advanced eDiscovery casos de v1.0.

- 1 de octubre de 2020: no podrá agregar nuevos datos (Preparar resultados de búsqueda para Advanced eDiscovery) a ningún caso. Podrá seguir trabajando con datos en casos existentes bajo su propio riesgo. El soporte técnico de Microsoft ya no proporcionará asistencia. 

- 31 de diciembre de 2020: no podrá tener acceso a Advanced eDiscovery casos de v1.0.

### <a name="alternative-tools"></a>Herramientas alternativas

La [Advanced eDiscovery de](./overview-ediscovery-20.md) la Centro de cumplimiento de Microsoft 365.