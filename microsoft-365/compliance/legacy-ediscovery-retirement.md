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
description: In-Place eDiscovery y la retención de In-Place (y los cmdlets de PowerShell correspondientes) en Exchange Online se retirarán en la primera mitad de 2020. El cmdlet Search-Mailbox y la exhibición avanzada de documentos electrónicos v 1.0 también se están retirando en el mismo período de tiempo.
ms.openlocfilehash: e8edda9436d62e07d0f64126a012791080766aba
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877471"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Retirada de herramientas heredadas de eDiscovery

> [!IMPORTANT]
> Microsoft ha evaluado la situación de salud pública y comprendemos el impacto que esto tiene en nuestros clientes. Queremos ser socios seguros y ciudadanos globales responsables. Para facilitar una de las muchas sobrecargas que tiene enfrentadas, vamos a retrasar la jubilación programada para las herramientas de eDiscovery heredadas que se describen en este artículo en tres meses. **Las fechas de retirada actualizadas se reflejan a continuación.**

A lo largo de los años, Microsoft ha ofrecido herramientas de eDiscovery que le permiten buscar, obtener una vista previa y exportar contenido de correo electrónico desde Exchange Online. Sin embargo, estas herramientas ya no ofrecen una forma efectiva de buscar contenido que no es de Exchange en otros servicios de Microsoft 365, como SharePoint Online y los grupos de Microsoft 365. Para solucionar esto, Microsoft ofrece otras herramientas de eDiscovery que le ayudarán a buscar una amplia variedad de contenido de Microsoft 365. Y hemos trabajado duro para incorporar la funcionalidad de exhibición de documentos electrónicos más actual y eficaz en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com). Esto permite a las organizaciones responder a solicitudes legales, internas y de otro documento sobre contenido en muchos servicios de Microsoft 365, incluido Exchange Online.

Como resultado de esta nueva y mejorada funcionalidad de eDiscovery en el centro de cumplimiento de Microsoft 365, estamos retirando las siguientes características relacionadas con la exhibición de documentos electrónicos y la funcionalidad relacionada con la búsqueda de contenido de correo electrónico en Exchange Online y Microsoft 365:

- [Exhibición](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) de documentos electrónicos local y [conservaciones locales](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) en el centro de administración de Exchange.

- Los cmdlets de PowerShell de Exchange online que admiten In-Place las suspensiones de exhibición de documentos electrónicos y In-Place (estos cmdlets se identifican colectivamente como cmdlets * *-MailboxSearch* ). Esto incluye los siguientes cmdlets:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Los cmdlets [Get-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) y [Remove-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) estarán disponibles después de que se retiran los otros cmdlets * * * *-MailboxSearch * * _ para que pueda usarlos como ayuda en la transición a otras herramientas de exhibición de documentos electrónicos y retención. Sin embargo, después de una fecha determinada (citada a continuación), el soporte técnico de Microsoft ya no será compatible con estos dos cmdlets.

- El cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) en Exchange Online PowerShell.

- Las siguientes operaciones en la API de servicios web Exchange:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v 1.0](office-365-advanced-ediscovery.md), que es la primera versión de Advanced eDiscovery a la que se tiene acceso a través de un caso básico de eDiscovery en el centro de seguridad & cumplimiento de Office 365. La retirada de eDiscovery avanzado v 1.0 no afecta a la capacidad de crear y administrar casos básicos de eDiscovery.

> [!NOTE]
> La funcionalidad de exhibición de documentos electrónicos que se está retirando solo se aplica a las versiones basadas en nube de Microsoft 365 y Office 365. la funcionalidad de exhibición de documentos electrónicos de las versiones locales de Exchange y SharePoint seguirá siendo compatible hasta que se produzca una nueva notificación.

En las siguientes secciones de este artículo se proporcionan instrucciones sobre cómo retirar cada característica. Esta información, incluidas las escalas de tiempo y las herramientas alternativas que puede usar en lugar de la herramienta retirada.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place la exhibición de documentos electrónicos y las suspensiones de In-Place en el centro de administración de Exchange 

De acuerdo con el anuncio original del 1 de julio de 2017, se está retirando la funcionalidad de conservación de exhibición de documentos electrónicos In-Place & eDiscovery en el centro de administración de Exchange (EAC). La página suspensiones de In-Place eDiscovery & en el EAC le permite buscar, retener y exportar contenido de Exchange Online. In-Place eDiscovery también le permite copiar los resultados de la búsqueda en un buzón de correo de detección para que usted u otros administradores de eDiscovery puedan revisar el contenido y hacer que esté disponible para las solicitudes legales, reglamentarias y públicas.

Debido a que todas estas capacidades (excepto la de copiar los resultados de la búsqueda en un buzón de correo de detección) ahora están disponibles en la búsqueda de contenido, las herramientas eDiscovery y eDiscovery avanzado del [centro de cumplimiento de microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (con funcionalidad, confiabilidad y soporte mejorados para una amplia gama de servicios de Microsoft 365), se recomienda empezar a usar estas herramientas tan pronto como sea posible. Para ayudarle en la transición a estas otras herramientas de eDiscovery, en la tabla siguiente se enumeran las herramientas que puede usar en lugar de In-Place eDiscovery y la suspensión de In-Place.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 organizaciones empresariales

- Organizaciones de Educación de Office 365 y Microsoft 365

- Office 365 y Microsoft 365 organizaciones gubernamentales; Esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Escala de tiempo para la jubilación

- 1 de julio de 2020: no podrá crear nuevas búsquedas y suspensiones, pero puede seguir ejecutando, editando y eliminando las búsquedas existentes bajo su propio riesgo. El soporte técnico de Microsoft ya no In-Place las retenciones de eDiscovery & en el EAC.

- 1 de octubre de 2020: la funcionalidad In-Place eDiscovery & mantiene en el EAC se colocará en modo de solo lectura. Esto significa que solo podrá quitar búsquedas y suspensiones existentes.

### <a name="alternative-tools"></a>Herramientas alternativas

En la tabla siguiente se describen otras herramientas que puede usar para reemplazar las funciones existentes que se están retirando.

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
<td>Búsqueda, exportación y retención por motivos legales</td>
<td>Casos principales de eDiscovery en el centro de cumplimiento de Microsoft 365 </td>
<td><p>El uso de las capacidades de los casos de eDiscovery principales proporciona la paridad funcional para In-Place eDiscovery y las suspensiones de In-Place. Esto incluye lo siguiente:</p>
<ul>
<li>
<p>La búsqueda se ajusta a millones de ubicaciones</p>
</li>
<li>
<p>Mayor confiabilidad para la búsqueda, exportación y colocación de contenido en retención</p>
</li>
<li>
<p>Buscar contenido en para Exchange Online, SharePoint Online, OneDrive para la empresa, Skype empresarial, Microsoft Teams, grupos de Yammer, grupos de 365 de Microsoft y otro contenido almacenado en aplicaciones de Office 365</p></li></ul>
<p>Para obtener más información, vea <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations"> administrar investigaciones legales en Office 365</a>.</td>
</tr>
<tr class="even">
<td>Retención para fines de retención</td>
<td>Directivas de retención en el centro de cumplimiento de Microsoft 365</td>
<td><p>Puede usar directivas de retención para retener contenido y, si lo desea, eliminarlo una vez que expire el período de retención. Entre otras capacidades se incluyen:</p>
<ul>
<li>
<p>Aplicación de directivas a toda la organización </p>
</li><li>
<p>Aplicación de directivas a ubicaciones de contenido específicas como Exchange Online, SharePoint Online, OneDrive para la empresa, Skype empresarial, Microsoft Teams y Office 365 grupos</p></li>
<li>
<p>Aplicación de directivas a usuarios específicos</p></li></ul>
<p>Para obtener más información, vea <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> información sobre las directivas de retención y las etiquetas de retención</a>.</td>
</tr>
<tr class="odd">
<td>Copiar los resultados de la búsqueda de correo electrónico en un buzón de detección para su revisión</td><td>Revisar conjuntos en eDiscovery avanzado v 2.0</td>
<td><p>La revisión del contenido en Microsoft 365 nunca ha sido más sencilla. Los conjuntos de revisión tienen muchas capacidades excelentes para ayudarle a reducir la cantidad de tiempo y los datos necesarios para la revisión, entre los que se incluyen:</p>
<ul>
<li><p>Realizar consultas de Fast Search y filtrar el contenido de un conjunto de revisión</p></li>
<li><p>Analizar el contenido de un conjunto de revisión; Esto incluye el subprocesamiento de correo electrónico, la detección de casi duplicados, el análisis de temas y la codificación predictiva</p></li>
<li><p>Etiquetar documentos en un conjunto de revisión</p></li>
<li><p>Sugerencias de etiquetado para ayudar a identificar el contenido del privilegio de clientes de abogados</p></li></ul>
<p>Para más información, consulte<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20"> información sobre la solución de eDiscovery avanzado en Microsoft 365</a>.</p>
<p>
<p>Como alternativa, puede exportar los resultados de la búsqueda a archivos PST y, a continuación, usar el servicio de importación de Microsoft 365 para importar los archivos PST a un buzón de correo de detección. Para obtener instrucciones paso a paso, consulte <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">usar la carga de red para importar archivos PST a Office 365</a>.
</tr>
<tr class=even>
  <td>Copiar mensajes de un buzón a otro buzón</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado abandona la organización y necesita conceder acceso al correo del antiguo empleado a otra persona), se recomienda asignar los permisos de esa persona para obtener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar los elementos del buzón a otro buzón de usuario o a un buzón compartido, solo tiene que asignar a un usuario permisos para obtener acceso al buzón de origen.</td>
  
  </tr>
<tr class="odd">
<td>Restaurar elementos de la carpeta elementos recuperables</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Puede restaurar elementos eliminados permanentemente (también conocidos como elementos <i>eliminados temporalmente</i> ) en buzones de correo, siempre que el período de retención de elementos eliminados para un elemento no haya expirado. Para obtener más información, vea <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">carpeta elementos recuperables en Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Preguntas más frecuentes acerca de In-Place eDiscovery y las suspensiones de In-Place

_ *Uso la funcionalidad copiar resultados de búsqueda de In-Place suspensiones de & de eDiscovery en el EAC para copiar los resultados de la búsqueda en un buzón de correo de detección para su revisión por parte de los abogados. ¿Qué opciones tengo ahora?**

Actualmente, hay dos formas de replicar esta funcionalidad. La primera es usar los [conjuntos de revisiones en EDiscovery avanzado v 2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set). Los conjuntos de revisión tienen muchas de las mismas funciones que se ven en una herramienta de revisión tradicional, como Fast Search of Documents, tagging, subprocesamiento de correo electrónico, casi agrupación de duplicados, análisis de temas y Codificación predictiva. Si aún desea usar buzones de correo de detección para revisión, la segunda opción es exportar los resultados de la búsqueda a archivos PST y, a continuación, importar los archivos PST a un buzón de correo de detección mediante la [característica de importación de PST](use-network-upload-to-import-pst-files.md) del centro de cumplimiento de Microsoft.

**¿Cómo controlo qué ubicaciones de contenido (como buzones o sitios) que puede realizar un administrador de exhibición de documentos electrónicos con las nuevas herramientas?**

El centro de cumplimiento de Microsoft 365 también usa [límites de cumplimiento](set-up-compliance-boundaries.md) para controlar las ubicaciones de contenido que puede buscar un administrador de exhibición de documentos electrónicos. Los límites de cumplimiento son útiles en entidades gubernamentales que deben mantenerse dentro de los límites de la agencia o las corporaciones multinacionales necesarias para respetar los tableros geográficos.

**¿Cómo puedo transferir mis suspensiones y búsquedas actuales al centro de cumplimiento de Microsoft 365?**

Es posible migrar In-Place las búsquedas y las suspensiones de eDiscovery desde el EAC con PowerShell. Para obtener instrucciones, consulte [migrar búsquedas y suspensiones del EAC al centro de cumplimiento de Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224).

## <a name="-mailboxsearch-cmdlets"></a>\*Cmdlets-MailboxSearch

Según el aviso original anunciado el 1 de julio de 2017 en el centro de administración de Exchange, se está retirando In-Place la funcionalidad de conservación de exhibición de documentos electrónicos & y los cmdlets **\* -MailboxSearch** correspondientes. Estos cmdlets proporcionan a los usuarios la capacidad de buscar, conservar y exportar contenido de buzones de correo para solicitudes legales, reglamentarias y públicas.

Como estas capacidades ahora están disponibles en el [<span class="underline">centro de cumplimiento de Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) y el PowerShell del centro de cumplimiento de & de seguridad de Office 365 con mejoras en el rendimiento y la escalabilidad, debería usar estos cmdlets mejorados. Estos cmdlets incluyen [<span class="underline"> \* -ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)y [<span class="underline"> \* -ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 organizaciones empresariales

- Organizaciones de Educación de Office 365 y Microsoft 365

- Office 365 y Microsoft 365 organizaciones gubernamentales; Esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: no podrá usar **New-MailboxSearch** para crear nuevas In-Place búsquedas de exhibición de documentos electrónicos y retenciones de In-Place, pero puede seguir usando cmdlets para ejecutar, editar y eliminar las búsquedas y las suspensiones existentes bajo su responsabilidad. El soporte técnico de Microsoft ya no ofrece asistencia para estos tipos de búsquedas y suspensiones.

- 1 de octubre de 2020: como se mencionó anteriormente, la funcionalidad de In-Place eDiscovery & mantiene en el EAC se colocará en modo de solo lectura. Esto también significa que no podrá usar los cmdlets **New-mailboxsearch** , **Start-mailboxsearch** o **set-mailboxsearch** . Solo podrás obtener y quitar búsquedas y suspensiones existentes.

### <a name="alternative-tools"></a>Herramientas alternativas

En la tabla siguiente se describen otras herramientas que puede usar para reemplazar las funciones existentes que se están retirando.

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
<td>Buscar y exportar</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction trabajan conjuntamente para ayudarle a buscar y exportar contenido. Puede crear una búsqueda nueva y ver la estimación de la búsqueda con los cmdlets <strong>New-</strong>, <strong>Get-</strong>y <strong>Start-ComplianceSearch</strong> . A continuación, puede usar el cmdlet <strong>New-ComplianceSearchAction</strong> para exportar los resultados de la búsqueda. Todavía tendrá que usar la herramienta de exhibición de documentos electrónicos principal del centro de cumplimiento de Microsoft 365 para descargar los resultados de la búsqueda en el equipo local.</p>
<p>
<p><strong>Nota:</strong> Si usa estos cmdlets para crear búsquedas que no están asociadas a un caso de exhibición de documentos electrónicos principal, estas búsquedas se encuentran en la página <strong>búsqueda de contenido</strong> en el centro de cumplimiento de Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Retener contenido en un buzón</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Las suspensiones del centro de cumplimiento de Microsoft 365 deben asociarse con un ComplianceCase. En primer lugar, cree el caso de cumplimiento y, a continuación, cree un CaseHoldPolicy y un CaseHoldRule.</p>
<p><strong>Nota:</strong> La creación de un CaseHoldPolicy sin un CaseHoldRule de creación hará que la retención no funcione hasta que se cree el CaseHoldRule y se asocie a la CaseHoldPolicy. Consulte la documentación del cmdlet para obtener más información.</p></td>
</tr>
<tr class="odd">
<td>Copiar los resultados de la búsqueda en un buzón de detección</td>
<td>Ninguno</td>
<td>No hay reemplazo directo para esta funcionalidad, ya que no proporciona acceso a todos los servicios de Microsoft 365. Consulte las preguntas más frecuentes siguientes para obtener soluciones alternativas.</td>
</tr>
  <tr class=even>
  <td>Copiar mensajes de un buzón a otro buzón</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado abandona la organización y necesita conceder acceso al correo del antiguo empleado a otra persona), se recomienda asignar los permisos de esa persona para obtener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar los elementos del buzón a otro buzón de usuario o a un buzón compartido, solo tiene que asignar a un usuario permisos para obtener acceso al buzón de origen.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Preguntas más frecuentes sobre los cmdlets * **-MailboxSearch**

**Usamos la copia de búsqueda para exportar mensajes de correo electrónico o mensajes instantáneos para fines de otras investigaciones legales y eDiscovery. ¿Qué otras opciones tiene cuando se retiran estos cmdlets?**

Las [<span class="underline">API de Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) proporcionan una serie de métodos para extraer datos para el análisis y otros propósitos que son mucho más resistentes y escalables que con los cmdlets **\* -MailboxSearch** .

**¿Cómo puedo migrar Mis búsquedas y retenciones al centro de cumplimiento de Microsoft 365?**

Es posible migrar In-Place las búsquedas y las suspensiones de eDiscovery desde el centro de administración de Exchange mediante un script de PowerShell. Para obtener más información, consulte [migrar búsquedas y suspensiones de eDiscovery heredado al centro de cumplimiento de Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md).

**Una vez retirados los cmdlets, ¿podré quitar o recuperar las búsquedas?**

Sí, aunque estamos eliminando la capacidad de crear y modificar búsquedas, aún podrá usar **Get-mailboxsearch** y **Remove-MailboxSearch** hasta recibir más avisos. Sin embargo, el uso de estos cmdlets será bajo su propio riesgo después de que las fechas de jubilación y soporte técnico de Microsoft ya no puedan proporcionar asistencia.

## <a name="search-mailbox-cmdlet"></a>Cmdlet de Search-Mailbox

El cmdlet **Search-Mailbox** en Exchange Online PowerShell se está retirando como se anunció originalmente en una advertencia en la salida del cmdlet que comienza en 2018. El cmdlet **Search-Mailbox** se usó originalmente para buscar en el buzón de correo de un usuario y purgar contenido malintencionado. Le recomendamos que empiece a usar los cmdlets **New-ComplianceSearch** y **New-ComplianceSearchAction** en Office 365 Security & el centro de cumplimiento de PowerShell para buscar y purgar contenido. Para una experiencia de seguridad integrada, las [<span class="underline">características de seguridad de microsoft 365</span>](https://docs.microsoft.com/microsoft-365/security/) proporcionan una sólida protección contra amenazas para el correo electrónico y muchos otros servicios de Microsoft.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 organizaciones empresariales

- Organizaciones de Educación de Office 365 y Microsoft 365

- Office 365 y Microsoft 365 organizaciones gubernamentales; Esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

-  1 de julio de 2020: el cmdlet **Search-Mailbox** dejará de estar disponible y el soporte técnico de Microsoft ya no proporcionará asistencia.

### <a name="alternative-tools"></a>Herramientas alternativas

En la tabla siguiente se describen otras herramientas que puede usar para reemplazar las funciones existentes que se están retirando.

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
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction trabajan conjuntamente para ayudarle a buscar y exportar contenido. Puede crear una búsqueda nueva y ver la estimación de la búsqueda con los cmdlets <strong>New-</strong>, <strong>Get-</strong>y <strong>Start-ComplianceSearch</strong> . A continuación, puede usar el comando <strong>New-ComplianceSearchAction-Export</strong> para exportar los resultados de la búsqueda. Todavía tendrá que usar la herramienta de exhibición de documentos electrónicos principal del centro de cumplimiento de Microsoft 365 para descargar los resultados de la búsqueda en el equipo local.</p></p>
</td>
</tr>
<tr class="even">
<td>Eliminar el correo electrónico masivo de un buzón</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Configurar una directiva de archivo y eliminación para buzones de correo</span></a></p>
<p></p></td>
<td><p>Los administradores pueden crear una directiva de archivado y eliminación que mueva automáticamente los elementos al buzón de archivo de un usuario y elimine automáticamente los elementos del buzón.</p>
</td>
</tr>
<tr class="even">
<td>Copiar los resultados de la búsqueda en un buzón de detección</td>
<td> </td>
<td>No hay reemplazo directo para esta funcionalidad, ya que no proporciona acceso a todos los servicios de Microsoft 365. Consulte las preguntas más frecuentes en la sección <strong>cmdlets *-MailboxSearch</strong> para obtener soluciones alternativas. </td>
</tr>
<tr class=odd>
  <td>Copiar mensajes de un buzón a otro buzón</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
  <td>Para conceder a una persona acceso al correo electrónico de otro usuario (por ejemplo, cuando un empleado abandona la organización y necesita conceder acceso al correo del antiguo empleado a otra persona), se recomienda asignar los permisos de esa persona para obtener acceso al buzón del antiguo empleado. Por lo tanto, en lugar de copiar los elementos del buzón a otro buzón de usuario o a un buzón compartido, solo tiene que asignar a un usuario permisos para obtener acceso al buzón de origen.</td>
</tr>
<tr class=even>
  <td>Purgar mensajes de un buzón</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Los cmdlets ComplianceSearch y ComplianceSearchAction trabajan conjuntamente para ayudarle a buscar y depurar contenido. Puede crear y ejecutar una búsqueda con los cmdlets <strong>New-compliancesearch</strong> y <strong>New-compliancesearch</strong> y, a continuación, puede purgar el contenido con el comando <strong>New-ComplianceSearchAction-Purge-PurgeType</strong> . Para obtener más información, vea <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Buscar y eliminar mensajes</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Purgar mensajes de un buzón</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Asignar permisos a un buzón</a></td>
<td>Para purgar mensajes de un buzón de correo, asigne a un administrador permisos para obtener acceso al buzón de correo del empleado. Los mensajes se pueden eliminar y reciclar según sea necesario aprovechando las capacidades de búsqueda y visualización integradas en Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Operaciones de la API de servicios web Exchange

Estas operaciones en la API de los servicios web Exchange se usan en la característica In-Place eDiscovery & retenciones del centro de administración de Exchange y los cmdlets **\* -MailboxSearch** de Exchange en Exchange Online PowerShell. También se retirarán como parte de la retirada de las otras herramientas de eDiscovery heredadas.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 organizaciones empresariales

- Organizaciones de Educación de Office 365 y Microsoft 365

- Office 365 y Microsoft 365 organizaciones gubernamentales; Esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: las operaciones de GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes y GetHoldOnMailboxes ya no estarán disponibles y el soporte técnico de Microsoft ya no proporcionará asistencia.

## <a name="advanced-ediscovery-v10"></a>EDiscovery avanzado v 1.0

EDiscovery avanzado v 1.0, que es la versión de eDiscovery avanzado disponible en un caso de exhibición de documentos electrónicos principal al hacer clic en **cambiar a exhibición avanzada** de documentos electrónicos, se está retirando. Su funcionalidad se ha reemplazado por la nueva [solución Advanced eDiscovery](https://aka.ms/edisco) en el centro de cumplimiento de Microsoft 365.

Para determinar si su organización está usando eDiscovery avanzado v 1.0:

1. Vaya al [centro de cumplimiento de & de seguridad de Office 365](https://protection.office.com).

2. En el panel de navegación izquierdo del centro de seguridad & cumplimiento, haga clic en **ediscovery > eDiscovery** y abra un caso principal de eDiscovery.

3. Si ve el botón **cambiar a eDiscovery avanzado** , al hacer clic en él le llevará a la versión 1,0 de eDiscovery avanzado, que se está retirando. La capacidad de crear y administrar casos en la exhibición de documentos electrónicos principal no se verá afectada. Solo se retirará la capacidad de agregar y analizar datos de casos en eDiscovery avanzado v 1.0 (haciendo clic en **cambiar a EDiscovery avanzado** ).

La nueva solución avanzada de exhibición de documentos electrónicos de Microsoft 365 (también denominada *EDiscovery avanzado v 2.0* ) proporciona todas las capacidades de la solución original, pero ahora incluye un enfoque basado en custodios para identificar contenido en otros servicios de Microsoft 365, recopilar dicho contenido y, a continuación, agregarlo a un conjunto de revisión en el que los revisores pueden aprovechar las consultas de Fast Search, el etiquetado y las características de análisis para facilitar la selección de documentos relevantes. La exhibición avanzada de documentos electrónicos ahora incluye mejoras de procesamiento y visores nativos para tipos de archivo de Microsoft y que [no son de](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)Microsoft, aquí se muestra una lista completa de los tipos de [archivo y los](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) campos de metadatos admitidos. Además, la nueva solución Advanced eDiscovery proporciona una potente característica de administración de retenciones de custodios que le permite aplicar suspensiones a contenido en diferentes servicios, notificar a los usuarios de las suspensiones y realizar un seguimiento de las respuestas de custodios, todo dentro de un caso de eDiscovery avanzado.

Para acceder a la exhibición avanzada de documentos electrónicos v 2.0:

1. Vaya al [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).

2. En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, a continuación, en **eDiscovery > avanzadas**.

En este momento, le recomendamos que empiece a realizar la transición del flujo de trabajo de eDiscovery a la nueva funcionalidad de eDiscovery avanzado. Si es necesario, puede archivar los casos avanzados de eDiscovery 1,0 exportando el contenido y almacenándolos sin conexión. Aunque aún podrá obtener acceso a la exhibición avanzada de documentos electrónicos v 1.0 en casos existentes hasta el 31 de diciembre de 2020, el soporte técnico de Microsoft no proporcionará soporte técnico después del 1 de octubre de 2020. Para obtener más información, vea la siguiente escala de tiempo.

### <a name="scope-of-affected-organizations"></a>Ámbito de las organizaciones afectadas

- Office 365 y Microsoft 365 organizaciones empresariales

- Organizaciones de Educación de Office 365 y Microsoft 365

- Office 365 y Microsoft 365 organizaciones gubernamentales; Esto incluye GCC, GCC High y DoD

- Office 365 Germany

### <a name="timeline"></a>Escala de tiempo

- 1 de julio de 2020: no podrá crear nuevos casos de exhibición de documentos electrónicos v 1.0 avanzado.

- 1 de octubre de 2020: no podrá agregar nuevos datos (preparar los resultados de la búsqueda para la exhibición avanzada de documentos electrónicos) en ningún caso. Podrá seguir trabajando con los datos en casos existentes bajo su propio riesgo. El soporte técnico de Microsoft ya no ofrece asistencia. 

- 31 de diciembre de 2020: no podrá acceder a los casos avanzados de eDiscovery v 1.0.

### <a name="alternative-tools"></a>Herramientas alternativas

La [solución Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) en el centro de cumplimiento de Microsoft 365.
