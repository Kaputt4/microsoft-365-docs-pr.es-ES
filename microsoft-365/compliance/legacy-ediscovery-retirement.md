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
description: In-Place eDiscovery y In-Place (y los cmdlets de PowerShell correspondientes) en Exchange Online se retirarán en la primera mitad de 2020. El Search-Mailbox y eDiscovery avanzado v1.0 también se retiran en el mismo período de tiempo.
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750883"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Retirada de herramientas heredadas de eDiscovery

> [!IMPORTANT]
> Microsoft ha estado evaluando la situación de salud pública y comprendemos el impacto que esto tiene en nuestros clientes. Queremos ser socios sólidos y ciudadanos globales responsables. Para aliviar una de las muchas cargas a las que se enfrenta, vamos a retrasar tres meses la retirada programada de las herramientas de exhibición de documentos electrónicos heredadas descritas en este artículo. **Las fechas de retirada actualizadas se reflejan a continuación.**

A lo largo de los años, Microsoft ha proporcionado herramientas de exhibición de documentos electrónicos que le permiten buscar, obtener una vista previa y exportar contenido de correo electrónico de Exchange Online. Sin embargo, estas herramientas ya no ofrecen una forma eficaz de buscar contenido que no sea de Exchange en otros servicios de Microsoft 365, como SharePoint Online y Grupos de Microsoft 365. Para solucionar este problema, Microsoft ofrece otras herramientas de exhibición de documentos electrónicos que le ayudarán a buscar una amplia variedad de contenido de Microsoft 365. Y hemos estado trabajando duro para incorporar la funcionalidad de exhibición de documentos electrónicos más actual y eficaz en el Centro de cumplimiento de [Microsoft 365.](https://compliance.microsoft.com) Esto permite a las organizaciones responder a solicitudes legales, internas y de otros documentos de contenido en muchos servicios de Microsoft 365, incluido Exchange Online.

Como resultado de esta nueva y mejorada funcionalidad de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365, estamos retirando las siguientes características y funcionalidades relacionadas con la exhibición de documentos electrónicos relacionadas con la búsqueda de contenido de correo electrónico en Exchange Online y Microsoft 365:

- [Exhibición de documentos](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) electrónicos local y [retenciones locales](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) en el Centro de administración de Exchange.

- Los cmdlets de PowerShell de Exchange Online que admiten In-Place eDiscovery y In-Place Holds (estos cmdlets se identifican colectivamente como cmdlets **-MailboxSearch).* Esto incluye los cmdlets siguientes:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Los cmdlets [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) y [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) estarán disponibles después de retirar los demás cmdlets ****-MailboxSearch**_ para que pueda usarlos para ayudarle en la transición a otras herramientas de exhibición de documentos electrónicos y retención. Sin embargo, después de una fecha determinada (mencionada a continuación), el soporte técnico de Microsoft ya no admitirá estos dos cmdlets.

- El [cmdlet Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) en Exchange Online PowerShell.

- Las siguientes operaciones en la API de servicios Web Exchange:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- EDiscovery avanzado de [Office 365 v1.0](office-365-advanced-ediscovery.md), que es la primera versión de eDiscovery avanzado a la que se tiene acceso a través de un caso de eDiscovery principal en el Centro de seguridad y cumplimiento de Office 36 & 5. La retirada de eDiscovery avanzado v1.0 no afecta a su capacidad para crear y administrar casos principales de eDiscovery.

> [!NOTE]
> La funcionalidad de exhibición de documentos electrónicos que se retira solo se aplica a las versiones basadas en la nube de Microsoft 365 y Office 365. La funcionalidad de exhibición de documentos electrónicos en versiones locales de Exchange y SharePoint seguirá siendo compatible hasta nuevo aviso.

Las siguientes secciones de este artículo proporcionan instrucciones sobre cada característica que se va a retirar. Esta información incluye escalas de tiempo y herramientas alternativas que puedes usar en lugar de la herramienta retirada.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery y In-Place en el Centro de administración de Exchange 

Según el anuncio original del 1 de julio de 2017, la funcionalidad de retención & de exhibición de documentos electrónicos de In-Place en el Centro de administración de Exchange (EAC) se está retirando. La In-Place de eDiscovery & en el EAC le permitía buscar, retener y exportar contenido de Exchange Online. In-Place eDiscovery también le permite copiar los resultados de la búsqueda en un buzón de correo de detección para que usted u otros administradores de exhibición de documentos electrónicos puedan revisar el contenido y hacer que esté disponible para solicitudes legales, reglamentarias y públicas.

Dado que todas estas capacidades (excepto para copiar los resultados de la búsqueda en un buzón de correo de detección) están ahora disponibles en la búsqueda de contenido, las herramientas de exhibición de documentos electrónicos y eDiscovery avanzado en el Centro de cumplimiento de [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (con funcionalidad mejorada, confiabilidad y compatibilidad para una amplia gama de servicios de Microsoft 365), le recomendamos que empiece a usar estas herramientas lo antes posible. Para ayudarle en la transición a estas otras herramientas de exhibición de documentos electrónicos, en la tabla siguiente se enumeran las herramientas que puede usar en lugar de In-Place eDiscovery y In-Place Retención.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Organizaciones de Office 365 y Microsoft 365 Enterprise

- Organizaciones de Office 365 y Microsoft 365 Educación

- Organizaciones de Office 365 y Microsoft 365 Government; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Escala de tiempo para la retirada

- 1 de julio de 2020: No podrá crear nuevas búsquedas y retenciones, pero aún puede ejecutar, editar y eliminar búsquedas existentes bajo su propia responsabilidad. El Soporte técnico de Microsoft ya no In-Place retención & eDiscovery en el EAC.

- 1 de octubre de 2020: La funcionalidad In-Place eDiscovery & Holds en el EAC se colocará en modo de solo lectura. Esto significa que solo podrá quitar las búsquedas y retenciones existentes.

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
<td>Casos principales de eDiscovery en el Centro de cumplimiento de Microsoft 365 </td>
<td><p>El uso de las capacidades de los casos principales de exhibición de documentos electrónicos proporciona la paridad funcional para In-Place eDiscovery y In-Place de exhibición de documentos electrónicos. Esto incluye lo siguiente:</p>
<ul>
<li>
<p>La búsqueda se escala a millones de ubicaciones</p>
</li>
<li>
<p>Mayor confiabilidad para buscar, exportar y poner contenido en espera</p>
</li>
<li>
<p>Buscar contenido en Exchange Online, SharePoint Online, OneDrive para la Empresa, Skype Empresarial, Microsoft Teams, Grupos de Yammer, Grupos de Microsoft 365 y otro contenido almacenado en aplicaciones de Office 365</p></li></ul>
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
<p>Aplicar directivas a ubicaciones de contenido específicas como Exchange Online, SharePoint Online, OneDrive para la Empresa, Skype Empresarial, Microsoft Teams y Grupos de Office 365</p></li>
<li>
<p>Aplicación de directivas a usuarios específicos</p></li></ul>
<p>Para obtener más información, vea <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">Más información sobre las directivas de retención y las etiquetas de retención.</a></td>
</tr>
<tr class="odd">
<td>Copiar los resultados de la búsqueda de correo electrónico en un buzón de correo de detección para su revisión</td><td>Conjuntos de revisión en eDiscovery avanzado v2.0</td>
<td><p>Revisar el contenido de Microsoft 365 nunca ha sido más fácil. Los conjuntos de revisión tienen muchas capacidades excelentes para ayudar a reducir la cantidad de tiempo y datos necesarios para revisar, incluidos:</p>
<ul>
<li><p>Realizar consultas de búsqueda rápida y filtrar contenido en un conjunto de revisión</p></li>
<li><p>Analizar el contenido de un conjunto de revisión; esto incluye subprocesos de correo electrónico, detección casi duplicada, análisis de temas y codificación predictiva</p></li>
<li><p>Etiquetar documentos en un conjunto de revisión</p></li>
<li><p>Sugerencias de etiquetado para ayudar a identificar el contenido de privilegios de abogado de cliente</p></li></ul>
<p>Para más información, consulte<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20"> información sobre la solución de eDiscovery avanzado en Microsoft 365</a>.</p>
<p>
<p>Como alternativa, puede exportar los resultados de la búsqueda a archivos PST y, a continuación, usar el servicio de importación de Microsoft 365 para importar los archivos PST a un buzón de correo de detección. Para obtener instrucciones paso a paso, vea Usar la carga en la red para importar <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">archivos PST a Office 365.</a>
</tr>
<tr class=even>
  <td>Copiar mensajes de un buzón de correo a un buzón diferente</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado abandona la organización y necesita conceder a otra persona acceso al correo electrónico del antiguo empleado), le recomendamos que asigne permisos a esa persona para tener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar elementos de buzón en otro buzón de usuario o en un buzón compartido, solo tiene que asignar permisos de usuario para tener acceso al buzón de origen.</td>
  
  </tr>
<tr class="odd">
<td>Restaurar elementos de la carpeta Elementos recuperables</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Puede restaurar los elementos eliminados <i></i> permanentemente (también conocidos como elementos eliminados temporalmente) en los buzones, siempre y cuando el período de retención de elementos eliminados de un elemento no haya expirado. Para obtener más información, vea <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">la carpeta Elementos recuperables en Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Preguntas más frecuentes sobre In-Place eDiscovery y In-Place locales

_ Uso la funcionalidad de copia de resultados de búsqueda de In-Place eDiscovery & Retenciones en el EAC para copiar los resultados de la búsqueda en un buzón de correo de detección para que los abogados los *revisen. ¿Qué opciones tengo ahora?**

Hay dos formas de replicar esta funcionalidad hoy en día. El primero es usar conjuntos [de revisión en eDiscovery avanzado v2.0.](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set) Los conjuntos de revisión tienen muchas de las mismas capacidades que ve en una herramienta de revisión tradicional, como la búsqueda rápida de documentos, etiquetado, subprocesos de correo electrónico, agrupación casi duplicada, análisis de temas y codificación predictiva. Si todavía desea usar buzones de correo de detección para su revisión, la segunda opción es exportar los resultados de la búsqueda a los archivos PST y, a continuación, importar los archivos PST a un buzón de correo de detección mediante la característica de importación de [PST](use-network-upload-to-import-pst-files.md) en el Centro de cumplimiento de Microsoft.

**¿Cómo controlo qué ubicaciones de contenido (como buzones o sitios) que un administrador de exhibición de documentos electrónicos puede buscar con las nuevas herramientas?**

El Centro de cumplimiento de [](set-up-compliance-boundaries.md) Microsoft 365 también usa límites de cumplimiento para controlar qué ubicaciones de contenido puede buscar un administrador de exhibición de documentos electrónicos. Los límites de cumplimiento son útiles en las entidades gubernamentales que necesitan permanecer dentro de los límites de las agencias o las corporaciones multinacionales necesarias para respetar a los miembros de la directiva geográfica.

**¿Cómo puedo mover mis búsquedas y retenciones actuales al Centro de cumplimiento de Microsoft 365?**

Es posible migrar In-Place búsquedas y retenciones de exhibición de documentos electrónicos desde el EAC mediante PowerShell. Para obtener instrucciones, consulte Migrar búsquedas y [retenciones desde el EAC al Centro de cumplimiento de Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2114224)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

Según el aviso original anunciado el 1 de julio de 2017 en el Centro de administración de Exchange, se están retirando la funcionalidad de retención de & de exhibición de documentos electrónicos de In-Place y los cmdlets **\* -MailboxSearch** correspondientes. Estos cmdlets proporcionan a los usuarios la capacidad de buscar, retener y exportar contenido de buzones de correo para solicitudes legales, reglamentarias y públicas.

Dado que estas funcionalidades ahora están disponibles en el Centro de cumplimiento de [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) y PowerShell del Centro de seguridad & y cumplimiento de Office 365 con un rendimiento y escalabilidad mejorados, debe usar estos cmdlets mejorados. Estos cmdlets incluyen [<span class="underline"> \* -ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)y [<span class="underline"> \* -ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Organizaciones de Office 365 y Microsoft 365 Enterprise

- Organizaciones de Office 365 y Microsoft 365 Educación

- Organizaciones de Office 365 y Microsoft 365 Government; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: No podrá usar **New-MailboxSearch** para crear nuevas búsquedas de exhibición de documentos electrónicos de In-Place y retenciones de In-Place, pero aún puede usar cmdlets para ejecutar, editar y eliminar búsquedas y retenciones existentes bajo su propia responsabilidad. El Soporte técnico de Microsoft ya no proporcionará asistencia para este tipo de búsquedas y retenciones.

- 1 de octubre de 2020: Como se indicó anteriormente, la funcionalidad de In-Place eDiscovery & Holds en el EAC se colocará en modo de solo lectura. Esto también significa que no podrá usar los cmdlets **New-MailboxSearch**, **Start-MailboxSearch** o **Set-MailboxSearch.** Solo podrá obtener y quitar las búsquedas y retenciones existentes.

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
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan conjuntamente para ayudarle a buscar y exportar contenido. Puede crear una nueva búsqueda y ver la estimación de búsqueda con los cmdlets <strong>New-</strong>, <strong>Get y</strong> <strong>Start-ComplianceSearch.</strong> A continuación, puede usar el cmdlet <strong>New-ComplianceSearchAction</strong> para exportar los resultados de la búsqueda. Todavía tendrá que usar la herramienta de exhibición de documentos electrónicos principal en el Centro de cumplimiento de Microsoft 365 para descargar esos resultados de búsqueda en su equipo local.</p>
<p>
<p><strong>Nota:</strong> Si usa estos cmdlets para crear búsquedas que no están asociadas a un <strong></strong> caso de eDiscovery principal, estas búsquedas se encontrarán en la página Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Retener contenido en un buzón</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Las retenciones en el Centro de cumplimiento de Microsoft 365 deben estar asociadas a un ComplianceCase. En primer lugar, cree el caso de cumplimiento y, a continuación, cree caseHoldPolicy y CaseHoldRule.</p>
<p><strong>Nota:</strong> La creación de CaseHoldPolicy sin crear CaseHoldRule hará que la retención no se puede mantener hasta que se cree caseHoldRule y se asocie a CaseHoldPolicy. Consulte la documentación del cmdlet para obtener más información.</p></td>
</tr>
<tr class="odd">
<td>Copiar los resultados de la búsqueda en un buzón de correo de detección</td>
<td>Ninguno</td>
<td>No hay ningún reemplazo directo para esta funcionalidad porque no proporciona acceso a todos los servicios de Microsoft 365. Consulte las siguientes preguntas más frecuentes para obtener soluciones alternativas.</td>
</tr>
  <tr class=even>
  <td>Copiar mensajes de un buzón de correo a un buzón diferente</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado abandona la organización y necesita conceder a otra persona acceso al correo electrónico del antiguo empleado), le recomendamos que asigne permisos a esa persona para tener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar elementos de buzón en otro buzón de usuario o en un buzón compartido, solo tiene que asignar permisos de usuario para tener acceso al buzón de origen.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Preguntas más frecuentes sobre los cmdlets ***-MailboxSearch**

**Usamos La búsqueda de copia para exportar mensajes de correo electrónico o mensajes instantáneos con fines de otra exhibición de documentos electrónicos e investigaciones legales. ¿Qué otras opciones tenemos después de retirar estos cmdlets?**

Las API de [<span class="underline">Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) proporcionan una serie de métodos para extraer datos para el análisis y otros fines que son mucho más resistentes y escalables que el uso de los cmdlets **\* -MailboxSearch.**

**¿Cómo puedo migrar mis búsquedas y retenciones al Centro de cumplimiento de Microsoft 365?**

Es posible migrar In-Place búsquedas y retenciones de exhibición de documentos electrónicos desde el Centro de administración de Exchange mediante un script de PowerShell. Para obtener más información, vea Migrar búsquedas y retenciones de exhibición de documentos electrónicos heredadas al Centro de cumplimiento de [Microsoft 365.](migrate-legacy-eDiscovery-searches-and-holds.md)

**Después de retirar los cmdlets, ¿seguiré siendo capaz de quitar o recuperar búsquedas?**

Sí, aunque estamos quitando la capacidad de crear y modificar búsquedas, podrá seguir utilizando **Get-MailboxSearch** y **Remove-MailboxSearch** hasta nuevo aviso. Sin embargo, el uso de estos cmdlets será bajo su propia responsabilidad después de las fechas de retirada y el Soporte técnico de Microsoft ya no podrá proporcionar asistencia.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

The **Search-Mailbox** cmdlet in Exchange Online PowerShell is being retired as originally announced in a warning in the cmdlet output starting back in 2018. El cmdlet **Search-Mailbox se** usó originalmente para buscar en el buzón de un usuario y purgar contenido malintencionado. Le recomendamos que empiece a usar los cmdlets **New-ComplianceSearch** y **New-ComplianceSearchAction** en PowerShell del Centro de seguridad y cumplimiento de Office 36 & 5 para buscar y purgar contenido. Para una experiencia de seguridad integrada, las características de seguridad de [<span class="underline">Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) proporcionan una sólida protección contra amenazas para el correo electrónico y muchos otros servicios Microsoft.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Organizaciones de Office 365 y Microsoft 365 Enterprise

- Organizaciones de Office 365 y Microsoft 365 Educación

- Organizaciones de Office 365 y Microsoft 365 Government; esto incluye GCC, GCC High y DoD

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
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan conjuntamente para ayudarle a buscar y exportar contenido. Puede crear una nueva búsqueda y ver la estimación de búsqueda con los cmdlets <strong>New-</strong>, <strong>Get y</strong> <strong>Start-ComplianceSearch.</strong> A continuación, puede usar el <strong>comando New-ComplianceSearchAction -Export</strong> para exportar los resultados de la búsqueda. Todavía tendrá que usar la herramienta de exhibición de documentos electrónicos principal en el Centro de cumplimiento de Microsoft 365 para descargar esos resultados de búsqueda en su equipo local.</p></p>
</td>
</tr>
<tr class="even">
<td>Eliminar correo electrónico masivo de un buzón</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Configurar una directiva de archivo y eliminación para buzones de correo</span></a></p>
<p></p></td>
<td><p>Los administradores pueden crear una directiva de archivado y eliminación que mueva automáticamente los elementos al buzón de archivo de un usuario y elimine automáticamente los elementos del buzón.</p>
</td>
</tr>
<tr class="even">
<td>Copiar los resultados de la búsqueda en un buzón de correo de detección</td>
<td> </td>
<td>No hay ningún reemplazo directo para esta funcionalidad porque no proporciona acceso a todos los servicios de Microsoft 365. Consulte las preguntas más frecuentes en la <strong>sección de cmdlets *-MailboxSearch</strong> para obtener soluciones alternativas. </td>
</tr>
<tr class=odd>
  <td>Copiar mensajes de un buzón de correo a un buzón diferente</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado abandona la organización y necesita conceder a otra persona acceso al correo electrónico del antiguo empleado), le recomendamos que asigne permisos a esa persona para tener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar elementos de buzón en otro buzón de usuario o en un buzón compartido, solo tiene que asignar permisos de usuario para tener acceso al buzón de origen.</td>
</tr>
<tr class=even>
  <td>Purgar mensajes de un buzón</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction funcionan conjuntamente para ayudarle a buscar y purgar contenido. Puede crear y ejecutar una búsqueda con los cmdlets <strong>New-ComplianceSearch</strong> y <strong>New-ComplianceSearch</strong> y, a continuación, purgar el contenido mediante el comando <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Para obtener más información, vea <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Buscar y eliminar mensajes.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Purgar mensajes de un buzón</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
<td>Para purgar mensajes de un buzón, asigne permisos de administrador para tener acceso al buzón del empleado. Los mensajes se pueden eliminar y reciclar según sea necesario aprovechando las funciones integradas de búsqueda y visualización en Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Operaciones de la API de servicios Web Exchange

Estas operaciones en la API de servicios web de Exchange se usan en la característica retenciones de & de exhibición de documentos electrónicos de In-Place en el Centro de administración de Exchange y los cmdlets **\* -MailboxSearch** correspondientes en Exchange Online PowerShell. También se retirarán como parte de la retirada de las otras herramientas de exhibición de documentos electrónicos heredadas.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Organizaciones de Office 365 y Microsoft 365 Enterprise

- Organizaciones de Office 365 y Microsoft 365 Educación

- Organizaciones de Office 365 y Microsoft 365 Government; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: Las operaciones GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes y GetHoldOnMailboxes ya no estarán disponibles y el soporte técnico de Microsoft ya no proporcionará asistencia.

## <a name="advanced-ediscovery-v10"></a>EDiscovery avanzado v1.0

Se está retirando eDiscovery avanzado v1.0, que es la versión de eDiscovery avanzado disponible en un caso de eDiscovery principal haciendo clic en Cambiar a **eDiscovery** avanzado. Su funcionalidad se ha reemplazado por la nueva solución [de eDiscovery avanzado](https://aka.ms/edisco) en el Centro de cumplimiento de Microsoft 365.

Para determinar si su organización usa eDiscovery avanzado v1.0:

1. Vaya al Centro [de seguridad y & cumplimiento de Office 365.](https://protection.office.com)

2. En el panel de navegación izquierdo del Centro de seguridad & cumplimiento, haga clic en **eDiscovery > eDiscovery** y abra un caso de eDiscovery principal.

3. Si ve el botón Cambiar a **eDiscovery** avanzado, al hacer clic en él se le llevará a la versión 1.0 de eDiscovery avanzado, que se está retirando. La capacidad de crear y administrar casos en eDiscovery principal no se verá afectada. Solo se está retirando la capacidad de agregar y analizar datos de casos en eDiscovery avanzado v1.0 (haciendo clic en Cambiar a **eDiscovery** avanzado).

La nueva solución de eDiscovery avanzado de Microsoft 365 (también conocida como *eDiscovery avanzado v2.0)* proporciona todas las capacidades de la solución original, pero ahora incluye un enfoque basado en administradores para identificar contenido en otros servicios de Microsoft 365, recopilar ese contenido y luego agregarlo a un conjunto de revisión donde los revisores pueden aprovechar las ventajas de las consultas de búsqueda rápida, el etiquetado y las características de análisis para ayudar a crear documentos relevantes. La exhibición avanzada de documentos electrónicos ahora incluye un procesamiento mejorado y visores nativos [](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) para tipos de archivo de Microsoft y no de Microsoft, una lista completa de tipos de archivo está aquí y los campos de metadatos admitidos están [aquí.](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery) Además, la nueva solución de eDiscovery avanzado proporciona una eficaz característica de administración de retenciones de administrador que le permite aplicar retenciones a contenido de diferentes servicios, notificar a los usuarios sobre las retenciones y realizar un seguimiento de las respuestas de administrador, todo ello dentro de un caso de eDiscovery avanzado.

Para obtener acceso a eDiscovery avanzado v2.0:

1. Vaya al Centro [de cumplimiento de Microsoft 365.](https://compliance.microsoft.com)

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en Mostrar todo y, a continuación, haga clic en **eDiscovery > avanzado.**

En este momento, le recomendamos que comience a realizar la transición del flujo de trabajo de exhibición de documentos electrónicos a la nueva funcionalidad de eDiscovery avanzado. Si es necesario, puede archivar los casos de eDiscovery avanzado 1.0 exportando el contenido y almacenandolo sin conexión. Aunque todavía podrá acceder a eDiscovery avanzado v1.0 en casos existentes hasta el 31 de diciembre de 2020, el soporte técnico de Microsoft no proporcionará soporte técnico después del 1 de octubre de 2020. Consulta la siguiente escala de tiempo para obtener más detalles.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Organizaciones de Office 365 y Microsoft 365 Enterprise

- Organizaciones de Office 365 y Microsoft 365 Educación

- Organizaciones de Office 365 y Microsoft 365 Government; esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: No podrá crear nuevos casos de eDiscovery avanzado v1.0.

- 1 de octubre de 2020: No podrá agregar nuevos datos (preparar los resultados de búsqueda para eDiscovery avanzado) en ningún caso. Podrá seguir trabajando con datos en casos existentes bajo su propia responsabilidad. El Soporte técnico de Microsoft ya no proporcionará asistencia. 

- 31 de diciembre de 2020: No podrá acceder a los casos de eDiscovery avanzado v1.0.

### <a name="alternative-tools"></a>Herramientas alternativas

La [solución de eDiscovery avanzado en](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) el Centro de cumplimiento de Microsoft 365.
