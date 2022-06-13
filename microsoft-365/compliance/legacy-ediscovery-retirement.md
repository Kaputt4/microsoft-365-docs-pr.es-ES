---
title: Herramientas de exhibición de documentos electrónicos heredadas retiradas
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
description: In-Place eDiscovery y In-Place Hold (y los cmdlets de PowerShell correspondientes) en Exchange Online se retirarán en el primer semestre de 2020. El cmdlet Search-Mailbox y microsoft Purview eDiscovery (Premium) v1.0 también se están retirando en el mismo período de tiempo.
ms.openlocfilehash: 36883f7edae391ff3461d5d6c135112a4f058671
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012296"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Retirada de herramientas heredadas de eDiscovery

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

> [!IMPORTANT]
> La funcionalidad de las herramientas de exhibición de documentos electrónicos heredadas descritas en este artículo se ha quitado del servicio Microsoft 365 o sigue estando disponible, pero ya no se admite. Cualquier funcionalidad que todavía esté disponible puede quitarse sin previo aviso. Si sigue usando cualquiera de estas herramientas heredadas, considere la posibilidad de migrar a las herramientas de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview o en una de las alternativas descritas en este artículo.

A lo largo de los años, Microsoft ha proporcionado herramientas de exhibición de documentos electrónicos que le permiten buscar, obtener una vista previa y exportar contenido de correo electrónico desde Exchange Online. Sin embargo, estas herramientas ya no ofrecen una manera eficaz de buscar contenido que no sea Exchange en otros servicios de Microsoft 365, como SharePoint Online y Grupos de Microsoft 365. Para solucionar este problema, Microsoft ofrece otras herramientas de exhibición de documentos electrónicos que le ayudan a buscar una amplia variedad de contenido Microsoft 365. Y hemos estado trabajando duro para incorporar la funcionalidad de eDiscovery más actual y eficaz en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento</a>. Esto permite a las organizaciones responder a solicitudes legales, internas y de otros documentos de contenido en muchos servicios de Microsoft 365, incluidos Exchange Online.

Como resultado de esta nueva y mejorada funcionalidad de exhibición de documentos electrónicos en el portal de cumplimiento, retiramos las siguientes características y funcionalidades relacionadas con eDiscovery relacionadas con la búsqueda de contenido de correo electrónico en Exchange Online y Microsoft 365:

- [eDiscovery local](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) y [las retenciones locales](/exchange/security-and-compliance/create-or-remove-in-place-holds) en el centro de administración de Exchange.

- Los cmdlets de PowerShell Exchange Online que admiten In-Place eDiscovery y In-Place Holds (estos cmdlets se identifican colectivamente como cmdlets **-MailboxSearch*). Esto incluye los siguientes cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Los cmdlets [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) y [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) estarán disponibles después de que se retiren los demás cmdlets de ****-MailboxSearch*** para que pueda usarlos para ayudar en la transición a otras herramientas de exhibición de documentos electrónicos y almacenamiento. Sin embargo, después de una fecha determinada (citada a continuación) Soporte técnico de Microsoft ya no admitirán estos dos cmdlets.

- Cmdlet [Search-Mailbox](/powershell/module/exchange/search-mailbox) en Exchange Online PowerShell.

- Las siguientes operaciones en la API de servicios web de Exchange:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Microsoft Purview eDiscovery (Premium) v1.0](./overview-ediscovery-20.md), que es la primera versión de eDiscovery (Premium) a la que se accede a través de un caso de eDiscovery (estándar) de Microsoft Purview en el portal de cumplimiento. La retirada de eDiscovery (Premium) v1.0 no afecta a la capacidad de crear y administrar casos de exhibición de documentos electrónicos (estándar).

> [!NOTE]
> La funcionalidad eDiscovery que se está retirando solo se aplica a las versiones basadas en la nube de Microsoft 365 y Office 365. La funcionalidad de exhibición de documentos electrónicos en versiones locales de Exchange y SharePoint seguirá siendo compatible hasta nuevo aviso.

En las secciones siguientes de este artículo se proporcionan instrucciones sobre cada característica que se va a retirar. Esta información incluye escalas de tiempo y herramientas alternativas que puede usar en lugar de la herramienta retirada.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery y In-Place holds en el centro de administración de Exchange 

Según el anuncio original del 1 de julio de 2017, se está retirando la funcionalidad In-Place eDiscovery & Hold en el Centro de administración de Exchange (EAC). La página In-Place eDiscovery & Holds del EAC le permite buscar, mantener y exportar contenido de Exchange Online. In-Place eDiscovery también le permite copiar los resultados de búsqueda en un buzón de detección para que usted u otros administradores de eDiscovery puedan revisar el contenido y ponerlo a disposición de solicitudes legales, reglamentarias y públicas.

Dado que todas estas funcionalidades (excepto para copiar resultados de búsqueda en un buzón de detección) ahora están disponibles en las herramientas de búsqueda de contenido, exhibición de documentos electrónicos y exhibición de documentos electrónicos (Premium) en el [portal de cumplimiento](./microsoft-365-compliance-center.md) (con funcionalidad mejorada, confiabilidad y compatibilidad con una amplia gama de servicios de Microsoft 365), se recomienda empezar a usar estas herramientas lo antes posible. Para ayudarle en la transición a estas otras herramientas de exhibición de documentos electrónicos, en la tabla siguiente se enumeran las herramientas que puede usar en lugar de In-Place eDiscovery y In-Place Hold.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- organizaciones Office 365 y Microsoft 365 Enterprise

- organizaciones Office 365 y Microsoft 365 Educación

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Escala de tiempo para la retirada

- 1 de julio de 2020: no podrá crear nuevas búsquedas y retenciones, pero puede ejecutar, editar y eliminar búsquedas existentes a su propio riesgo. Soporte técnico de Microsoft ya no In-Place & de exhibición de documentos electrónicos en el EAC.

- 1 de octubre de 2020: la funcionalidad In-Place eDiscovery & Holds en el EAC se colocará en modo de solo lectura. Esto significa que solo podrá quitar las búsquedas y retenciones existentes.

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
<td>Casos de eDiscovery (Estándar) en el portal de cumplimiento </td>
<td><p>El uso de las capacidades de los casos de exhibición de documentos electrónicos (estándar) proporciona la paridad funcional para In-Place eDiscovery y In-Place retenciones. Esto incluye lo siguiente:</p>
<ul>
<li>
<p>La búsqueda se escala a millones de ubicaciones</p>
</li>
<li>
<p>Mayor confiabilidad para buscar, exportar y colocar contenido en espera</p>
</li>
<li>
<p>Buscar contenido en para Exchange Online, SharePoint Online, OneDrive para la Empresa, Skype Empresarial, Microsoft Teams, grupos Yammer, Grupos de Microsoft 365 y otro contenido almacenado en aplicaciones Office 365</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Suspensión con fines de retención</td>
<td>Directivas de retención en el portal de cumplimiento</td>
<td><p>Puede usar directivas de retención para conservar el contenido y, si lo desea, eliminarlo después de que expire el período de retención. Otras funcionalidades incluyen:</p>
<ul>
<li>
<p>Aplicación de directivas a toda la organización </p>
</li><li>
<p>Aplicación de directivas a ubicaciones de contenido específicas como Exchange Online, SharePoint Online, OneDrive para la Empresa, Skype Empresarial, Microsoft Teams y grupos de Office 365</p></li>
<li>
<p>Aplicación de directivas a usuarios específicos</p></li></ul>
<p>Para obtener más información, consulte <a href="/microsoft-365/compliance/retention-policies"> Más información sobre las directivas de retención y las etiquetas de retención</a>.</td>
</tr>
<tr class="odd">
<td>Copia de los resultados de la búsqueda de correo electrónico en un buzón de detección para su revisión</td><td>Conjuntos de revisión en eDiscovery (Premium) v2.0</td>
<td><p>Revisar el contenido de Microsoft 365 nunca ha sido tan fácil. Los conjuntos de revisión tienen muchas funcionalidades excelentes para ayudar a reducir la cantidad de tiempo y los datos necesarios para revisar, entre los que se incluyen:</p>
<ul>
<li><p>Realizar consultas de búsqueda rápida y filtrar contenido en un conjunto de revisión</p></li>
<li><p>Analizar contenido en un conjunto de revisión; esto incluye el subproceso de correo electrónico, la detección casi duplicada, el análisis de temas y la codificación predictiva</p></li>
<li><p>Etiquetar documentos en un conjunto de revisión</p></li>
<li><p>Sugerencias de etiquetado para ayudar a identificar el contenido de privilegios de cliente de abogado</p></li></ul>
<p>Para obtener más información, vea <a href="/microsoft-365/compliance/overview-ediscovery-20">Información general de la solución eDiscovery (Premium) en Microsoft 365</a>.</p>
<p>
<p>Como alternativa, puede exportar los resultados de búsqueda a archivos PST y, a continuación, usar Microsoft 365 Servicio de importación para importar los PST a un buzón de detección. Para obtener instrucciones paso a paso, consulte <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Uso de la carga de red para importar archivos PST a Office 365</a>.
</tr>
<tr class=even>
  <td>Copia de mensajes de un buzón a otro buzón</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignación de permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado deja su organización y necesita conceder a otra persona acceso al correo electrónico del empleado anterior), se recomienda asignar a esa persona permisos para acceder al buzón del empleado anterior. Por lo tanto, en lugar de copiar elementos de buzón de correo a otro buzón de usuario o a un buzón compartido, solo tiene que asignar a un usuario los permisos necesarios para acceder al buzón de origen.</td>
  
  </tr>
<tr class="odd">
<td>Restauración de elementos desde la carpeta Elementos recuperables</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Puede restaurar elementos eliminados permanentemente (también conocidos como elementos <i>eliminados temporalmente</i> ) en buzones de correo, siempre y cuando el período de retención de elementos eliminados de un elemento no haya expirado. Para obtener más información, vea <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Carpeta Elementos recuperables en Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Preguntas más frecuentes sobre In-Place eDiscovery y In-Place Holds

**Uso la funcionalidad de copia de resultados de búsqueda de In-Place eDiscovery & Holds en el EAC para copiar los resultados de búsqueda en un buzón de detección para que los abogados los revisen. ¿Qué opciones tengo ahora?**

Hay dos maneras de replicar esta funcionalidad hoy en día. La primera es usar [conjuntos de revisión en eDiscovery (Premium) v2.0](./view-documents-in-review-set.md). Los conjuntos de revisión tienen muchas de las mismas funcionalidades que se ven en una herramienta de revisión tradicional, como la búsqueda rápida de documentos, el etiquetado, el subproceso de correo electrónico, la agrupación casi duplicada, el análisis de temas y la codificación predictiva. Si todavía desea usar buzones de detección para su revisión, la segunda opción es exportar los resultados de búsqueda a archivos PST y, a continuación, importar los archivos PST a un buzón de detección mediante la [característica de importación de PST](use-network-upload-to-import-pst-files.md) en el Centro de cumplimiento de Microsoft.

**Cómo controlar qué ubicaciones de contenido (como buzones o sitios) que un administrador de exhibición de documentos electrónicos puede buscar mediante las nuevas herramientas?**

El portal de cumplimiento también usa [límites de cumplimiento](set-up-compliance-boundaries.md) para controlar qué ubicaciones de contenido puede buscar un Administrador de exhibición de documentos electrónicos. Los límites de cumplimiento son útiles en las entidades gubernamentales que necesitan permanecer dentro de los límites de las agencias o las corporaciones multinacionales necesarias para respetar los abordajes geográficos.

**¿Cómo puedo mover mis búsquedas y retenciones actuales al portal de cumplimiento de Microsoft Purview?**

Es posible migrar In-Place búsquedas y retenciones de eDiscovery desde el EAC mediante PowerShell. Para obtener instrucciones, consulte [Migración de búsquedas y retenciones desde el EAC al portal de cumplimiento](./migrate-legacy-ediscovery-searches-and-holds.md).

## <a name="-mailboxsearch-cmdlets"></a>\*Cmdlets -MailboxSearch

Según el aviso original anunciado el 1 de julio de 2017 en el Centro de administración de Exchange, se están retirando la funcionalidad In-Place eDiscovery & Hold y los cmdlets **-MailboxSearch correspondientes\***. Estos cmdlets proporcionan a los usuarios la capacidad de buscar, mantener y exportar contenido de buzón de correo para solicitudes legales, reglamentarias y públicas.

Dado que estas funcionalidades ahora están disponibles en el [<span class="underline">portal de cumplimiento</span>](./microsoft-365-compliance-center.md) y Office 365 PowerShell de cumplimiento de seguridad & con rendimiento y escalabilidad mejorados, debe usar estos cmdlets mejorados. Estos cmdlets incluyen [<span class="underline">\*-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule) y [<span class="underline">\*-ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- organizaciones Office 365 y Microsoft 365 Enterprise

- organizaciones Office 365 y Microsoft 365 Educación

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: no podrá usar **New-MailboxSearch** para crear nuevas búsquedas In-Place eDiscovery y In-Place retenciones, pero todavía puede usar cmdlets para ejecutar, editar y eliminar búsquedas y retenciones existentes bajo su propio riesgo. Soporte técnico de Microsoft ya no proporcionará ayuda para este tipo de búsquedas y retenciones.

- 1 de octubre de 2020: como se indicó anteriormente, la funcionalidad In-Place eDiscovery & Holds en el EAC se colocará en modo de solo lectura. Esto también significa que no podrá usar los cmdlets **New-MailboxSearch**, **Start-MailboxSearch** o **Set-MailboxSearch** . Solo podrá obtener y quitar búsquedas y retenciones existentes.

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
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan juntos para ayudarle a buscar y exportar contenido. Puede crear una nueva búsqueda y ver la estimación de búsqueda mediante los cmdlets <strong>New-</strong>, <strong>Get-y Start-ComplianceSearch</strong>. <strong></strong> A continuación, puede usar el cmdlet <strong>New-ComplianceSearchAction</strong> para exportar los resultados de la búsqueda. Seguirá teniendo que usar la herramienta eDiscovery (Estándar) en el portal de cumplimiento para descargar esos resultados de búsqueda en el equipo local.</p>
<p>
<p><strong>Nota:</strong> Si usa estos cmdlets para crear búsquedas que no están asociadas a un caso de exhibición de documentos electrónicos (estándar), estas búsquedas se ubicarán en la página <strong>Búsqueda de contenido</strong> del portal de cumplimiento.</p></td>
</tr>
<tr class="even">
<td>Mantener contenido en un buzón</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Las retenciones en el portal de cumplimiento deben estar asociadas a compliancecase. En primer lugar, cree el caso de cumplimiento y, a continuación, cree un CaseHoldPolicy y un CaseHoldRule.</p>
<p><strong>Nota:</strong> La creación de caseholdpolicy sin una instancia de CaseHoldRule hará que la suspensión no se pueda ejecutar hasta que se cree CaseHoldRule y se asocie a CaseHoldPolicy. Consulte la documentación del cmdlet para obtener más información.</p></td>
</tr>
<tr class="odd">
<td>Copia de los resultados de la búsqueda en un buzón de detección</td>
<td>Ninguno</td>
<td>No hay ningún reemplazo directo para esta funcionalidad porque no proporciona acceso a todos los servicios Microsoft 365. Consulte las siguientes preguntas más frecuentes a continuación para obtener soluciones alternativas.</td>
</tr>
  <tr class=even>
  <td>Copia de mensajes de un buzón a otro buzón</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignación de permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado deja su organización y necesita conceder a otra persona acceso al correo electrónico del empleado anterior), se recomienda asignar a esa persona permisos para acceder al buzón del empleado anterior. Por lo tanto, en lugar de copiar elementos de buzón de correo en otro buzón de usuario o un buzón compartido, solo tiene que asignar permisos de usuario para acceder al buzón de origen.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Preguntas más frecuentes sobre los cmdlets ***-MailboxSearch**

**Usamos Copy Search para exportar mensajes de correo electrónico o mensajes instantáneos con fines de eDiscovery eDiscovery e investigaciones legales. ¿Qué otras opciones tenemos después de retirar estos cmdlets?**

Las [<span class="underline">API de Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) proporcionan una serie de métodos para extraer datos con fines de análisis y otros que son mucho más resistentes y escalables que el uso de los **\*cmdlets -MailboxSearch**.

**¿Cómo puedo migrar mis búsquedas y retenciones al portal de cumplimiento?**

Es posible migrar In-Place búsquedas y retenciones de exhibición de documentos electrónicos desde el centro de administración de Exchange mediante un script de PowerShell. Para obtener más información, consulte [Migración de búsquedas y retenciones de exhibición de documentos electrónicos heredadas al portal de cumplimiento](migrate-legacy-eDiscovery-searches-and-holds.md).

**Una vez retirados los cmdlets, ¿podré quitar o recuperar búsquedas?**

Sí, aunque se elimina la capacidad de crear y modificar búsquedas, seguirá siendo capaz de usar **Get-MailboxSearch** y **Remove-MailboxSearch** hasta nuevo aviso. Sin embargo, el uso de estos cmdlets estará en su propio riesgo después de las fechas de retirada y Soporte técnico de Microsoft ya no podrá proporcionar asistencia.

## <a name="search-mailbox-cmdlet"></a>cmdlet Search-Mailbox

El cmdlet **Search-Mailbox** de Exchange Online PowerShell se está retirando como se anunció originalmente en una advertencia en la salida del cmdlet a partir de 2018. El cmdlet **Search-Mailbox** se usó originalmente para buscar en el buzón de un usuario y purgar contenido malintencionado. Se recomienda empezar a usar los cmdlets **New-ComplianceSearch** y **New-ComplianceSearchAction** en Office 365 Security & Compliance PowerShell para buscar y purgar contenido. Para una experiencia de seguridad integrada, las [<span class="underline">características de seguridad Microsoft 365</span>](../security/index.yml) proporcionan una sólida protección contra amenazas para el correo electrónico y muchos otros servicios Microsoft.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- organizaciones Office 365 y Microsoft 365 Enterprise

- organizaciones Office 365 y Microsoft 365 Educación

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

-  1 de julio de 2020: El cmdlet **Search-Mailbox** ya no estará disponible y Soporte técnico de Microsoft ya no proporcionará ayuda.

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
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan juntos para ayudarle a buscar y exportar contenido. Puede crear una nueva búsqueda y ver la estimación de búsqueda mediante los cmdlets <strong>New-</strong>, <strong>Get-y Start-ComplianceSearch</strong>. <strong></strong> A continuación, puede usar el comando <strong>New-ComplianceSearchAction -Export</strong> para exportar los resultados de la búsqueda. Seguirá teniendo que usar la herramienta eDiscovery (Estándar) en el portal de cumplimiento para descargar esos resultados de búsqueda en el equipo local.</p></p>
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
<td>Copia de los resultados de la búsqueda en un buzón de detección</td>
<td> </td>
<td>No hay ningún reemplazo directo para esta funcionalidad porque no proporciona acceso a todos los servicios Microsoft 365. Consulte las preguntas más frecuentes en la sección <strong>cmdlets *-MailboxSearch</strong> para obtener soluciones alternativas. </td>
</tr>
<tr class=odd>
  <td>Copia de mensajes de un buzón a otro buzón</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignación de permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado deja su organización y necesita conceder a otra persona acceso al correo electrónico del empleado anterior), se recomienda asignar a esa persona permisos para acceder al buzón del empleado anterior. Por lo tanto, en lugar de copiar elementos de buzón de correo a otro buzón de usuario o a un buzón compartido, solo tiene que asignar un permiso de usuario para acceder al buzón de origen.</td>
</tr>
<tr class=even>
  <td>Purgar mensajes de un buzón</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan juntos para ayudarle a buscar y purgar contenido. Puede crear y ejecutar una búsqueda con los cmdlets <strong>New-ComplianceSearch</strong> y <strong>New-ComplianceSearch</strong> y, a continuación, puede purgar el contenido mediante el comando <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> . Para obtener más información, vea <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Buscar y eliminar mensajes</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Purgar mensajes de un buzón</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignación de permisos a un buzón</a></td>
<td>Para purgar mensajes de un buzón de correo, asigne permisos de administrador para acceder al buzón del empleado. Los mensajes se pueden eliminar y reciclar según sea necesario aprovechando las funcionalidades integradas de búsqueda y visualización en Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange operaciones de API de servicios web

Estas operaciones en la API de servicios web de Exchange las usa la característica In-Place eDiscovery & Holds en el centro de administración de Exchange y los cmdlets **-MailboxSearch correspondientes\*** en Exchange Online PowerShell. También se retirarán como parte de la retirada de las otras herramientas de exhibición de documentos electrónicos heredadas.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- organizaciones Office 365 y Microsoft 365 Enterprise

- organizaciones Office 365 y Microsoft 365 Educación

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: Las operaciones GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes y GetHoldOnMailboxes ya no estarán disponibles y Soporte técnico de Microsoft ya no proporcionarán asistencia.

## <a name="ediscovery-premium-v10"></a>eDiscovery (Premium) v1.0

eDiscovery (Premium) v1.0, que es la versión de eDiscovery (Premium) disponible en un caso de eDiscovery (Estándar) haciendo clic en **Cambiar a eDiscovery (Premium)**, se está retirando. Su funcionalidad se ha reemplazado por la nueva [solución eDiscovery (Premium)](./ediscovery.md) en el portal de cumplimiento.

Para determinar si su organización usa eDiscovery (Premium) v1.0:

1. Vaya al portal de cumplimiento, seleccione **eDiscovery** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank">**Core**</a> y abra un caso de exhibición de documentos electrónicos (estándar).

1. Si ve el botón **Cambiar a eDiscovery (Premium),** al hacer clic en él se le llevará a la versión 1.0 de eDiscovery (Premium), que se está retirando. La capacidad de crear y administrar casos en eDiscovery (Estándar) no se verá afectada. Solo se está retirando la capacidad de agregar y analizar datos de casos en eDiscovery (Premium) v1.0 (haciendo clic en **Cambiar a eDiscovery (Premium)**).

La nueva solución eDiscovery (Premium) en Microsoft 365 (también conocida como *eDiscovery (Premium) v2.0*) proporciona todas las funcionalidades de la solución original, pero ahora incluye un enfoque basado en custodios para identificar contenido en otros Microsoft 365  servicios, recopilar ese contenido y, a continuación, agregarlo a un conjunto de revisión en el que los revisores pueden aprovechar las ventajas de las consultas de búsqueda rápida, el etiquetado y las características de análisis para ayudar a eliminar los documentos pertinentes. eDiscovery (Premium) ahora incluye un procesamiento mejorado y visores nativos para los tipos de archivo de Microsoft y que no son de Microsoft, una lista completa de tipos de archivo está [aquí](./supported-filetypes-ediscovery20.md) y los campos de metadatos admitidos están [aquí](./document-metadata-fields-in-advanced-ediscovery.md). Además, la nueva solución eDiscovery (Premium) proporciona una eficaz característica de administración de custodias que le permite aplicar retenciones al contenido de diferentes servicios, notificar a los usuarios de las retenciones y realizar un seguimiento de las respuestas del custodio, todo ello dentro de un caso de exhibición de documentos electrónicos (Premium).

Para acceder a eDiscovery (Premium) v2.0:

Vaya al portal de cumplimiento, seleccione **eDiscovery** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank">**Advanced**</a> y abra un caso de exhibición de documentos electrónicos (estándar).

En este momento, se recomienda empezar a realizar la transición del flujo de trabajo de exhibición de documentos electrónicos a la nueva funcionalidad de exhibición de documentos electrónicos (Premium). Si es necesario, puede archivar los casos de eDiscovery (Premium) 1.0 exportando el contenido y almacenándolo sin conexión. Aunque todavía podrá acceder a eDiscovery (Premium) v1.0 en los casos existentes hasta el 31 de diciembre de 2020, Soporte técnico de Microsoft no proporcionará soporte técnico después del 1 de octubre de 2020. Consulte la siguiente escala de tiempo para obtener más detalles.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- organizaciones Office 365 y Microsoft 365 Enterprise

- organizaciones Office 365 y Microsoft 365 Educación

- Office 365 y Microsoft 365 organizaciones gubernamentales; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: no podrá crear nuevos casos de eDiscovery (Premium) v1.0.

- 1 de octubre de 2020: no podrá agregar nuevos datos (Preparar los resultados de búsqueda para eDiscovery (Premium)) a ningún caso. Podrá seguir trabajando con datos en casos existentes a su propio riesgo. Soporte técnico de Microsoft ya no proporcionará asistencia. 

- 31 de diciembre de 2020: no podrá acceder a los casos de eDiscovery (Premium) v1.0.

### <a name="alternative-tools"></a>Herramientas alternativas

La [solución eDiscovery (Premium)](./overview-ediscovery-20.md) en el portal de cumplimiento.
