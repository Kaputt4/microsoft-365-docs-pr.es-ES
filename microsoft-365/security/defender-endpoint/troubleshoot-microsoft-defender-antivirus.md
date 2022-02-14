---
title: Antivirus de Microsoft Defender de eventos y códigos de error
description: Buscar las causas y soluciones de los Antivirus de Microsoft Defender de eventos y errores
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/27/2022
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: db4401e1215ab50e47425dee15a1337466e1e98a
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807541"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Revisar registros de sucesos y códigos de error para solucionar problemas del Antivirus de Windows Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Si encuentra un problema con Antivirus de Microsoft Defender, puede buscar en las tablas de este tema un problema de coincidencia y una posible solución.

La lista de tablas:

- [Antivirus de Microsoft Defender de eventos](#windows-defender-av-ids) (se aplican a Windows 10, Windows 11 y Windows Server 2016)
- [Antivirus de Microsoft Defender de error de cliente](#error-codes)
- [Códigos Antivirus de Microsoft Defender de error de cliente internos (usados por Microsoft durante el desarrollo y las pruebas)](#internal-error-codes)

> [!TIP]
> También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las siguientes características funcionan:
>
> - Protección entregada en la nube
> - Aprendizaje rápido (incluido Bloquear a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseado

> [!NOTE]
> El sitio de demostración defender para el punto de conexión en demo.wd.microsoft.com está en desuso y se quitará en el futuro.

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Antivirus de Microsoft Defender de eventos

Antivirus de Microsoft Defender registra los IDs de eventos en el Windows de eventos.

Puede ver directamente el registro de eventos, o si tiene una herramienta de administración de eventos y de información de seguridad (SIEM) de terceros, también puede consumir los Antivirus de Microsoft Defender de eventos de cliente para revisar eventos y errores [específicos](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de los puntos de conexión.

En la tabla de esta sección se enumeran los principales Antivirus de Microsoft Defender de eventos y, siempre que sea posible, proporciona soluciones sugeridas para corregir o resolver el error.

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Para ver un evento Antivirus de Microsoft Defender evento

1. Abra **el Visor de eventos**.
2. En el árbol de consola, expanda **Registros de aplicaciones** y servicios, **microsoft y,** a continuación, **Windows** y, a continuación **, Windows Defender**.
3. Haga doble clic en **Operativo**.
4. En el panel de detalles, vea la lista de eventos individuales para buscar el evento.
5. Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las **pestañas General** **y** Detalles.

<table>
<tr>
<th colspan="2" >Identificador de evento: 1000</th>
</tr>
<tr>
<td>
Nombre simbólico:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Se inició un examen de antimalware. </b>
</td>
</tr>
<tr>
<td >
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de identificador del examen correspondiente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo de examen&gt;, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros de&gt; examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Recursos de examen: &lt; Recursos (como archivos/directorios/BHO) que se examinaron.&gt;</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Usuario&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1001</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Se ha finalizado un examen de antimalware.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de identificador del examen correspondiente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo de examen&gt;, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros de&gt; examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Domainlt&gt;\&; UserScan&gt;</dt> 
<dt>Time: &lt;la duración de un examen.&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1002</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Antes de finalizar, se detuvo un examen antimalware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de identificador del examen correspondiente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo de examen&gt;, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros de&gt; examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Domainlt&gt;&amp;; UserScan&gt;</dt> 
<dt>Time: &lt;la duración de un examen.&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1003</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Se ha pausado un examen antimalware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de identificador del examen correspondiente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo de examen&gt;, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros de&gt; examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt;Domainlt&gt;\&; Usuario&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1004</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Se reanudó un examen antimalware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de identificador del examen correspondiente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo de examen&gt;, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros de&gt; examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt;Domainlt&gt;\&; Usuario&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1005</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Error en un examen antimalware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de identificador del examen correspondiente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo de examen&gt;, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros de&gt; examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Domainlt&gt;\&; UserError&gt;</dt> 
<dt>Code: Código &lt;de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente antivirus encontró un error y se detuvo el examen actual. El examen puede producir un error debido a un problema del lado cliente. Este registro de evento incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), los parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.
Para solucionar este evento:
<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el <b></b> número de error en el cuadro Buscar para buscar el código de error.</li>
<li>Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1006</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware encontró malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;Origen de detección&gt;, por ejemplo:<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;Tipo de detección&gt;, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen de detección&gt; por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también pueden ser invocados por terceros.
UACStatus</dt>
<dt>: &lt;StatusUser&gt;</dt>
<dt>: &lt;Domainlt&gt;\&; UserProcess&gt;</dt> 
<dt>Name: &lt;Process in the PIDSignature&gt;</dt> 
<dt>Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1007</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado. Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Usuario: &lt; Domainlt&gt;\&; UserName&gt;</dt>
<dt>: &lt;Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt>
<dt> Acción: &lt;Acción&gt;, por ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado: &lt; StatusSignature&gt;</dt> 
<dt>Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1008</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al tomar medidas en malware u otro software potencialmente no deseado. Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Usuario: &lt; Domainlt&gt;\&; UserName&gt;</dt>
<dt>: &lt;Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; PathAction de&gt;</dt>
<dt> archivo: &lt;Acción&gt;, por ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Código de error: &lt; Código de error&gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;Descripción del error&gt; Descripción del error. </dt> 
<dt>Estado: &lt; StatusSignature&gt;</dt> 
<dt>Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1009</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware restauró un elemento de cuarentena. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha restaurado un elemento de cuarentena. Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt> 
<dt>de archivoUser: &lt;Domainlt&gt;\&; UserSignature&gt;</dt> 
<dt>Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1010</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware no pudo restaurar un elemento de cuarentena. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar restaurar un elemento desde la cuarentena. Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt> 
<dt>de archivoUser: &lt;Domainlt&gt;\&; UserError&gt;</dt> 
<dt>Code: Código &lt;de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;Descripción del error&gt; Descripción del error. </dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1011</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware eliminó un elemento de la cuarentena. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha eliminado un elemento de la cuarentena.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt> 
<dt>de archivoUser: &lt;Domainlt&gt;\&; UserSignature&gt;</dt> 
<dt>Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1012</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware no pudo eliminar un elemento de la cuarentena.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar eliminar un elemento de la cuarentena.
Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt> 
<dt>de archivoUser: &lt;Domainlt&gt;\&; UserError&gt;</dt> 
<dt>Code: Código &lt;de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;Descripción del error&gt; Descripción del error. </dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1013</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware eliminó el historial de malware y otro software potencialmente no deseado.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha eliminado el historial de malware y otro software potencialmente no deseado.
<dl>
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Usuario&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1014</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
La plataforma antimalware no pudo eliminar el historial de malware y otro software potencialmente no deseado.
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar quitar el historial de malware y otro software potencialmente no deseado.
<dl>
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; UserError&gt;</dt> 
<dt>Code: Código &lt;de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1015</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware detectó un comportamiento sospechoso.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha detectado un comportamiento sospechoso.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;Origen de detección&gt;, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;Tipo de detección&gt;, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen de detección&gt; por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también pueden ser invocados por terceros.
UACStatus</dt>
<dt>: &lt;StatusUser&gt;</dt>
<dt>: &lt;Domainlt&gt;\&; UserProcess&gt;</dt> 
<dt>Name: &lt;Process in the PIDSignature&gt;</dt> 
<dt>ID: Enumeration matching severity.</dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine versionFidelity&gt;</dt> 
<dt>Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1116</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware detectó malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha detectado malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;Origen de detección&gt;, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;Tipo de detección&gt;, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen de detección&gt; por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también pueden ser invocados por terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; UserProcess&gt;</dt> 
<dt>Name: &lt;Process in the PIDSignature&gt;</dt> 
<dt>Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No se requiere ninguna acción. Antivirus de Microsoft Defender suspender y tomar medidas rutinarias en esta amenaza. Si desea quitar la amenaza manualmente, en la interfaz Antivirus de Microsoft Defender, haga clic en <b>Limpiar equipo</b>.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1117</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;Origen de detección&gt;, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;Tipo de detección&gt;, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen de detección&gt; por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también pueden ser invocados por terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; UserProcess&gt;</dt> 
<dt>Name: &lt;Process in the PIDAction&gt;</dt>
<dt>: &lt;Action&gt;, for example:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de acciones adicionalesError&gt;</dt> 
<dt>Code: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Antivirus de Microsoft Defender, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detecta un malware, restaurará la siguiente configuración del sistema y los servicios que el malware podría haber cambiado:<ul>
<li>Configuración predeterminada de Internet Explorer o Microsoft Edge configuración</li>
<li>Configuración del control de acceso de usuario</li>
<li>Configuración de Chrome</li>
<li>Datos de control de arranque</li>
<li>Configuración del Registro regedit y administrador de tareas</li>
<li>Windows, servicio de transferencia inteligente en segundo plano y servicio de llamadas de procedimiento remoto</li>
<li>Windows del sistema operativo</li></ul>
El contexto anterior se aplica a las siguientes versiones de cliente y servidor:
<table>
<tr>
<th>Sistema operativo</th>
<th>Versión del sistema operativo</th>
</tr>
<tr>
<td>
Sistema operativo cliente
</td>
<td>
Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 y versiones posteriores
</td>
</tr>
<tr>
<td>
Sistema operativo del servidor
</td>
<td>
Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 y Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. Antivirus de Microsoft Defender o ha puesto en cuarentena una amenaza.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1118</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error no crítico al tomar medidas en malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;Origen de detección&gt;, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;Tipo de detección&gt;, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen de detección&gt; por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también pueden ser invocados por terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; UserProcess&gt;</dt> 
<dt>Name: &lt;Process in the PIDAction&gt;</dt>
<dt>: &lt;Action&gt;, for example:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de acciones adicionalesError&gt;</dt> 
<dt>Code: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. Antivirus de Microsoft Defender no pudo completar una tarea relacionada con la corrección de malware. No se trata de un error crítico.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1119</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware encontró un error crítico al intentar tomar medidas en malware u otro software potencialmente no deseado. Hay más detalles en el mensaje de evento.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error crítico al tomar medidas en malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; Threat nameID&gt;</dt>
<dt>: &lt;Threat IDSeverity&gt;</dt>
<dt>: &lt;Severity&gt;, for example:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de categoría&gt;, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;Origen de detección&gt;, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;Tipo de detección&gt;, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen de detección&gt; por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también pueden ser invocados por terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; UserProcess&gt;</dt> 
<dt>Name: &lt;Process in the PIDAction&gt;</dt>
<dt>: &lt;Action&gt;, for example:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de acciones adicionalesError&gt;</dt> 
<dt>Code: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El Antivirus de Microsoft Defender encontró este error debido a problemas críticos. Es posible que el extremo no esté protegido. Revise la descripción del error y, a continuación, siga los <b>pasos de acción de usuario</b> pertinentes a continuación.
<table>
<tr>
<th>Acción</th>
<th>Acción del usuario</th>
</tr>
<tr>
<td>
<b>Quitar</b>
</td>
<td>
Actualice las definiciones y compruebe que la eliminación se ha realizado correctamente.
</td>
</tr>
<tr>
<td>
<b>Limpiar</b>
</td>
<td>
Actualice las definiciones y compruebe que la corrección se ha realizado correctamente.
</td>
</tr>
<tr>
<td>
<b>Cuarentena</b>
</td>
<td>
Actualice las definiciones y compruebe que el usuario tiene permiso para acceder a los recursos necesarios.
</td>
</tr>
<tr>
<td>
<b>Permitir</b>
</td>
<td>
Compruebe que el usuario tiene permiso para obtener acceso a los recursos necesarios.
</td>
</tr>
</table>

Si este evento persiste:<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el <b></b> número de error en el cuadro Buscar para buscar el código de error.</li>
<li>Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1120</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Antivirus de Microsoft Defender ha deducido los hashes de un recurso de amenaza.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.
<dl>
<dt>Versión actual de la plataforma: &lt; Versión actual de la&gt;</dt> 
<dt>plataformaThreat Resource Path: &lt;PathHashes&gt;</dt>
<dt>: &lt;Hashes&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging sin firma</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1127</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_FOLDER_GUARD_SECTOR_BLOCK</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Acceso controlado a carpetas (CFA) bloqueó un proceso que no es de confianza para que no realice cambios en la memoria. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Acceso controlado a carpetas ha bloqueado un proceso que no es de confianza para modificar potencialmente los sectores de disco.
<br/> Para obtener más información acerca del registro de eventos, vea lo siguiente:
<dl>
<dt>EventID: &lt; EventID&gt;, por ejemplo: 1127Version</dt>
<dt>: &lt;Version&gt;,</dt> por ejemplo: 
<dt>0Level: &lt;Level&gt;, por ejemplo: win:</dt>
<dt>WarningTimeCreated: &lt;SystemTime&gt;,</dt> hora en la que se creó el 
<dt>eventoEventRecordID: &lt;EventRecordID&gt;,</dt> número de índice del evento en el registro de 
<dt>eventosExecution ProcessID: &lt;Execution ProcessID&gt;,</dt> proceso que generó el 
<dt>eventChannel: &lt;Canal&gt; de eventos, por ejemplo: Microsoft- Windows-Windows Defender/</dt>
<dt>OperationalComputer: &lt;Computer nameSecurity&gt;</dt> 
<dt>UserID: &lt;Security UserIDProduct&gt;</dt> 
<dt>Name: &lt;Product Name&gt;, for example: Antivirus de Microsoft Defender</dt> 
<dt>Product Version: &lt;Product VersionDetection&gt;</dt>
<dt> Time: &lt;Detection Time&gt;, time when CFA blocked an un untrusted processUser</dt>
<dt>: &lt;Domainlt&gt;\&; UserPath&gt;</dt>
<dt>: &lt;&gt;</dt> nombre del dispositivo, nombre del dispositivo o disco al que ha accedido un proceso que no es de confianza para la modificación Nombre de proceso: 
<dt>Ruta de acceso del proceso, el nombre de ruta de acceso del proceso que CFA &lt;&gt;</dt> bloqueó para obtener acceso al dispositivo o disco para modificarLa versión de inteligencia de seguridadEngine 
<dt>Versión: &lt;Antimalware Engine versión&gt;</dt>
<dt>&lt;&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El usuario puede agregar el proceso bloqueado a la <i>lista Proceso</i> permitido para CFA, con Powershell o Seguridad de Windows Centro.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 1150</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Si la plataforma antimalware notifica el estado a una plataforma de supervisión, este evento indica que la plataforma antimalware se está ejecutando y en un estado correcto. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.
<dl>
<dt>Versión de la plataforma: &lt; Versión actual de&gt;</dt> 
<dt>la plataformaSignature Versión: &lt;Versión de definiciónEngine&gt;</dt> 
<dt>Versión: &lt;Antimalware Engine versión&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El Antivirus de Microsoft Defender está en buen estado. Este evento se notifica cada hora.
</td>
</tr>

<tr>
<th colspan="2">Identificador de evento: 1151</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Endpoint Protection de estado del cliente (hora UTC)</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Informe de estado del cliente antivirus.
<dl>
<dt>Versión de la plataforma: &lt; &gt;Versión</dt> actual de la 
<dt>plataformaEngine Versión: &lt;Antimalware Engine&gt;</dt> Versión del motor de inspección en tiempo real De red
<dt>: &lt;&gt;</dt> Versión del motor de inspección en tiempo real De red Versión de firma de Antivirus Versión de 
<dt>firmaAntispyware: &lt;Versión de firma antispywareNetwork&gt;</dt> Versión de firma de inspección en tiempo real
<dt>: &lt;&gt;</dt>
<dt>&lt; Network Realtime Inspection signature versionRTP&gt;</dt> 
<dt>state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature&gt; age  (en días)</dt> 
<dt>Antigüedad de firma antispyware: &lt; Antigüedad de firma antispyware&gt; (</dt>en días)Última antigüedad del examen rápido
<dt>: &lt;&gt;</dt> última antigüedad del examen rápido (en días)Última antigüedad completa del examen
<dt>: &lt;&gt;</dt> Última antigüedad completa del examen (en días)Tiempo de creación de firmas antivirus
<dt>: ?&lt; Hora de creación de firmas antivirusAntispyware&gt;</dt> 
<dt>hora de creación de firmas: ?&lt; Hora de creación de firmas antispywareLa&gt;</dt> 
<dt>última hora de inicio del examen rápido: ?&lt; Última hora de inicio del examen rápidoLa&gt;</dt> 
<dt>última hora de finalización del examen rápido: ?&lt; Last quick scan end timeLast&gt;</dt> 
<dt>quick scan source: &lt;Last quick scan source&gt; (0 = scan didn't run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt; Last full scan start timeLast&gt;</dt> 
<dt>full scan end time: ?&lt; Last full scan end timeLast&gt;</dt> 
<dt>full scan source: &lt;Last full scan source&gt; (0 = scan didn't run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting
</dl>
</td>
</tr>

<tr>
<th colspan="2">Identificador de evento: 2000</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Las definiciones de antimalware se actualizaron correctamente. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Se ha actualizado la versión de firma del antivirus.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma actualPrevious&gt;</dt> 
<dt>Signature Version: &lt;Previous signature versionSignature&gt;</dt>
<dt> Type: &lt;Signature type&gt;, for example: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Tipo de actualización: &lt; Tipo de actualización&gt;, Completo o Delta.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Versión del motor UserCurrent&gt;</dt>
<dt>: &lt;versión actual del motorPrevious&gt;</dt> Versión del motor
<dt>: &lt;Versión anterior del motor&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El Antivirus de Microsoft Defender está en buen estado. Este evento se notifica cuando las firmas se actualizan correctamente.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2001</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Error en la actualización de inteligencia de seguridad. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar firmas.
<dl>
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número de versiónPrevious&gt;</dt> 
<dt>versión de inteligencia de seguridad: &lt;Versión anteriorActualizar&gt;</dt>
<dt> Origen: &lt;Origen de&gt; actualización, por ejemplo:
<ul>
<li>Carpeta de actualización de inteligencia de seguridad</li>
<li>Servidor de actualización de inteligencia de seguridad interna</li>
<li>Microsoft Update Server</li>
<li>Compartir archivos</li>
<li>Centro de protección contra malware de Microsoft (MMPC)</li>
</ul>
</dt>
<dt>Fase de actualización: &lt;fase de actualización&gt;, por ejemplo:
<ul>
<li>Búsqueda</li>
<li>Descargar</li>
<li>Instalar</li>
</ul>
</dt>
<dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre de servidor para Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt> Tipo de firma: &lt;Tipo de firma&gt;, por ejemplo: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Tipo de actualización: &lt; Tipo de actualización&gt;, Completo o Delta.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; UserCurrent&gt;</dt> 
<dt>Engine Version: &lt;Current engine versionPrevious&gt;</dt> 
<dt>Engine Version: &lt;Previous engine versionError&gt;</dt> 
<dt>Code: &lt;Error code&gt; Result code associated with threat status. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Este error se produce cuando hay un problema al actualizar definiciones.
Para solucionar este evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</li>
<li>Revisa las entradas del archivo %Windir%\WindowsUpdate.log para obtener más información sobre este error.</li>
<li>Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2002</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware se actualizó correctamente. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender versión del motor se ha actualizado.
<dl>
<dt>Versión actual del motor: &lt; Versión actual del motorPrevious&gt;</dt> 
<dt>Engine Version: &lt;Previous engine versionEngine&gt;</dt> 
<dt>Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Usuario&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El Antivirus de Microsoft Defender está en buen estado. Este evento se notifica cuando el motor de antimalware se actualiza correctamente.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2003</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Error en la actualización del motor de antimalware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar el motor.
<dl>
<dt>Versión del motor nueva:</dt>
<dt>Versión anterior del motor: Versión &lt;anterior&gt;</dt> del 
<dt>motorIntecto de motor: &lt;tipo&gt; de motor, motor antimalware o motor del sistema de inspección de red.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; UserError&gt;</dt> 
<dt>Code: Código &lt;de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Error Antivirus de Microsoft Defender actualización de cliente. Este evento se produce cuando el cliente no se actualiza. Este evento suele deberse a una interrupción en la conectividad de red durante una actualización.
Para solucionar este evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</li>
<li>Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2004</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Hubo un problema al cargar definiciones de antimalware. El motor de antimalware intentará cargar el último conjunto de definiciones bien conocido.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar cargar firmas e intentará volver a un conjunto de firmas conocido.
<dl>
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt> 
<dt>Versión de firma: &lt; Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y falló. Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado. Antivirus de Microsoft Defender intentará volver a un conjunto de definiciones conocido.
Para solucionar este evento:
<ol>
<li>Reinicie el equipo e inténtelo de nuevo.</li>
<li>Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft web</a>.
Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.
</li>
<li>Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2005</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware no se pudo cargar porque la plataforma antimalware no está actualizada. La plataforma antimalware cargará el último motor antimalware bueno conocido e intentará actualizarlo.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender no se pudo cargar el motor de antimalware porque no se admite la versión actual de la plataforma. Antivirus de Microsoft Defender volverá al último motor conocido y se intenta actualizar la plataforma.
<dl>
<dt>Versión actual de la plataforma: &lt;versión actual de la plataforma&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2006</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Error en la actualización de la plataforma. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar la plataforma.
<dl>
<dt>Versión actual de la plataforma: &lt; Versión actual de la plataformaError&gt;</dt> 
<dt>Code: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2007</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma pronto estará des actualizada. Descargue la plataforma más reciente para mantener la protección actualizada.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender pronto necesitará una versión de plataforma más reciente para admitir versiones futuras del motor de antimalware. Descargue la plataforma Antivirus de Microsoft Defender para mantener el mejor nivel de protección disponible.
<dl>
<dt>Versión actual de la plataforma: &lt;versión actual de la plataforma&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2010</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware usaba el servicio de firma dinámica para obtener definiciones adicionales. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender <i>servicio de firma dinámica</i> para recuperar firmas adicionales para ayudar a proteger el equipo.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma actual&gt;</dt>
<dt> Tipo de firma: &lt;Tipo de firma&gt;, por ejemplo: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión del motor actual&gt;</dt>
<dt> Tipo de firma dinámica: &lt;Tipo de firma dinámica&gt;, por ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de persistencia: &lt; PathDynamic&gt;</dt> 
<dt>Signature Version: &lt;Version numberDynamic&gt;</dt> 
<dt>Signature Compilation Timestamp: &lt;TimestampPersistence&gt;</dt>
<dt> Limit Type: &lt;Persistence limit type&gt;, for example:
<ul>
<li>Versión de VDM</li>
<li>Timestamp</li>
<li>Sin límite</li>
</ul>
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2011</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El servicio de firma dinámica eliminó las definiciones dinámicas des actualizadas. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender servicio <i>de firma dinámica para</i> descartar firmas obsoletas.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma actual&gt;</dt>
<dt> Tipo de firma: &lt;Tipo de firma&gt;, por ejemplo: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión del motor actual&gt;</dt>
<dt> Tipo de firma dinámica: &lt;Tipo de firma dinámica&gt;, por ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de persistencia: &lt; PathDynamic&gt;</dt> 
<dt>Signature Version: &lt;Version numberDynamic&gt;</dt> 
<dt>Signature Compilation Timestamp: &lt;TimestampRemoval&gt;</dt> 
<dt>Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:
<ul>
<li>Versión de VDM</li>
<li>Timestamp</li>
<li>Sin límite</li>
</ul>
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El Antivirus de Microsoft Defender está en buen estado. Este evento se notifica cuando el servicio de firma dinámica elimina correctamente definiciones dinámicas des actualizadas.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2012</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware encontró un error al intentar usar el servicio de firma dinámica. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar usar <i>el servicio de firma dinámica</i>.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma actual&gt;</dt>
<dt> Tipo de firma: &lt;Tipo de firma&gt;, por ejemplo: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión del motor actualError&gt;</dt> 
<dt>Code: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
<dt> Tipo de firma dinámica: &lt;tipo de firma dinámica&gt;, por ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de persistencia: &lt; PathDynamic&gt;</dt> 
<dt>Signature Version: &lt;Version numberDynamic&gt;</dt> 
<dt>Signature Compilation Timestamp: &lt;TimestampPersistence&gt;</dt>
<dt> Limit Type: &lt;Persistence limit type&gt;, for example:
<ul>
<li>Versión de VDM</li>
<li>Timestamp</li>
<li>Sin límite</li>
</ul>
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Comprueba la configuración de conectividad a Internet.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2013</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El servicio de firma dinámica eliminó todas las definiciones dinámicas. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender descarta todas las firmas <i>del servicio de firma</i> dinámica.
<dl>
<dt>Versión actual de la firma: &lt;versión actual de la firma&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2020</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware descargó un archivo limpio. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender descargado un archivo limpio.
<dl>
<dt>Nombre de archivo: &lt; Nombre de archivo&gt; Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de firma actualActual&gt;</dt> 
<dt>del motor: &lt;versión actual del motor&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2021</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware no pudo descargar un archivo limpio. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar descargar un archivo limpio.
<dl>
<dt>Nombre de archivo: &lt; Nombre de archivo&gt; Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de firma actualActual&gt;</dt> 
<dt>del motor Versión: Versión &lt;actual del&gt;</dt> 
<dt>motorError Code: &lt;Código de error&gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Comprueba la configuración de conectividad a Internet.
El Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica. Es probable que este error se deba a un problema de conectividad de red.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2030</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware se descargó y está configurado para ejecutarse sin conexión en el siguiente reinicio del sistema.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender descargado y configurado antivirus sin conexión para que se ejecute en el siguiente reinicio.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2031</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware no pudo descargar ni configurar un examen sin conexión.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar descargar y configurar antivirus sin conexión.
<dl>
<dt>Código de error: &lt; Código de error&gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2040</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La compatibilidad con antimalware para esta versión del sistema operativo finalizará próximamente. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
La compatibilidad con el sistema operativo expirará en breve. Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2041</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La compatibilidad con antimalware para este sistema operativo ha finalizado. Debe actualizar el sistema operativo para que la compatibilidad continúe. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
La compatibilidad con el sistema operativo ha expirado. Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 2042</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware ya no es compatible con este sistema operativo y ya no protege el sistema contra malware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
La compatibilidad con el sistema operativo ha expirado. Antivirus de Microsoft Defender ya no se admite en el sistema operativo, ha dejado de funcionar y no protege contra amenazas de malware.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 3002</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La protección en tiempo real encontró un error y produjo un error.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender Real-Time de protección ha encontrado un error y ha producido un error.
<dl>
<dt>Característica: &lt;Característica&gt;, por ejemplo:
<ul>
<li>En Access</li>
<li>Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Código de error: &lt; Código de error&gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt> 
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque es posible que el sistema no se protegió durante algún tiempo.
La Antivirus de Microsoft Defender protección en tiempo real del cliente encontró un error porque uno de los servicios no se pudo iniciar.
Si le sigue un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 3007</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Protección en tiempo real recuperada de un error. Se recomienda ejecutar un examen completo del sistema cuando vea este error. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender Protección en tiempo real ha reiniciado una característica. Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba abajo.
<dl>
<dt>Característica: &lt;Característica&gt;, por ejemplo:
<ul>
<li>En Access</li>
<li>Descargas de IE y Outlook datos adjuntos de Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Se ha reiniciado la característica de protección en tiempo real. Si este evento vuelve a ocurrir, ponte en contacto <a href="https://go.microsoft.com/fwlink/?LinkId=215491">con el Soporte técnico de Microsoft</a>.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5000</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La protección en tiempo real está habilitada. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5001</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La protección en tiempo real está deshabilitada. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado se deshabilitó.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5004</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La configuración de protección en tiempo real cambió. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender configuración de características de protección en tiempo real ha cambiado.
<dl>
<dt>Característica: &lt;Característica&gt;, por ejemplo:
<ul>
<li>En Access</li>
<li>Descargas de IE y Outlook datos adjuntos de Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Configuración: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5007</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>Se cambió la configuración de la plataforma antimalware.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender configuración ha cambiado. Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.
<dl>
<dt>Valor antiguo: &lt; Número de valor antiguo Valor&gt; de configuración del antivirus anterior.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de valor&gt; Nuevo valor de configuración antivirus.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5008</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El motor de antimalware encontró un error y produjo un error.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender motor se ha terminado debido a un error inesperado.
<dl>
<dt>Tipo de error: &lt; Tipo de&gt; error, por ejemplo: Crash o HangException</dt> 
<dt>Code: &lt;Error codeResource&gt;</dt>
<dt>: &lt;Resource&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Para solucionar este evento:<ol>
<li>Intente reiniciar el servicio.<ul>
<li>Para antimalware, antivirus y spyware, en un símbolo del sistema con privilegios elevados, escriba <b>net stop msmpsvc</b> y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor de antimalware.</li>
<li>Para el <i>sistema</i> de inspección de red, en un símbolo del sistema con privilegios elevados, escriba <b>net start nissrv</b> y, a continuación, <i></i> escriba <b>net start nissrv</b> para reiniciar el motor del sistema de inspección de red mediante el NiSSRV.exe archivo.
</li>
</ul>
</li>
<li>Si se produce un error de la misma manera, busque el código de error accediendo al Sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> y especificando el número de error en el cuadro Búsqueda y póngase en contacto con el Soporte técnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">de Microsoft</a>.<b></b></li>
</ol>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El Antivirus de Microsoft Defender cliente se detuvo debido a un error inesperado.
Para solucionar este evento:
<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el <b></b> número de error en el cuadro Buscar para buscar el código de error.</li>
<li>Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5009</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El examen de malware y otro software potencialmente no deseado está habilitado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender se ha habilitado el examen de malware y otro software potencialmente no deseado.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5010</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El examen de malware y otro software potencialmente no deseado está deshabilitado.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender de búsqueda de malware y otro software potencialmente no deseado está deshabilitado.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5011</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El examen de virus está habilitado.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender se ha habilitado el examen de virus.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5012</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>El examen de virus está deshabilitado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender está deshabilitado el examen de virus.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5013</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>
</b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La protección contra alteraciones bloqueó un cambio en Antivirus de Microsoft Defender.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Si la protección contra alteraciones está habilitada, cualquier intento de cambiar cualquiera de las configuraciones de Defender si está bloqueada y se genera el identificador de evento 5013 que indica qué cambio de configuración se bloqueó.
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5100</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware expirará pronto. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha entrado en un período de gracia y expirará pronto. Después de expirar, este programa deshabilitará la protección contra virus, spyware y otro software potencialmente no deseado.
<dl>
<dt>Motivo de expiración: el Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la Antivirus de Microsoft Defender expirará.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">Identificador de evento: 5101</th>
</tr>
<tr><td>
Nombre simbólico:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
Mensaje:
</td>
<td >
<b>La plataforma antimalware ha expirado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender período de gracia ha expirado. La protección contra virus, spyware y otro software potencialmente no deseado está deshabilitada.
<dl>
<dt>Motivo de expiración:</dt>
<dt>Fecha de expiración: </dt>
<dt>Código de error: &lt;Código de&gt; error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error&gt; Descripción del error. </dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Antivirus de Microsoft Defender de error de cliente Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le dará un código de error para ayudarle a solucionar el problema. En la mayoría de los casos, un error significa que hubo un problema al instalar una actualización.
En esta sección se proporciona la siguiente información sobre Antivirus de Microsoft Defender errores de cliente.
- El código de error - El posible motivo del error Consejo - sobre qué hacer ahora

Use la información de estas tablas para ayudar a solucionar Antivirus de Microsoft Defender códigos de error.


<table>
<tr>
<th colspan="2">Código de error: 0x80508007</th>
</tr>
<tr>
<td>Message</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
Posible motivo
</td>
<td>
Este error indica que es posible que se haya quedo sin memoria.
</td>
</tr>
<tr>
<td>Solución</td>
<td>
<ol>
<li>Comprueba la memoria disponible en el dispositivo.</li>
<li>Cierra todas las aplicaciones no usadas que se estén ejecutando para liberar memoria en el dispositivo.</li>
<li>Reinicie el dispositivo y vuelva a ejecutar el examen.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x8050800C</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que puede haber un problema con el producto de seguridad.
</td>
</tr><tr><td>Solución</td><td>
<ol>
<li>Actualice las definiciones. Cualquiera de las dos:<ol>
<li>Haga clic <b>en el botón Actualizar definiciones</b> de la <b>ficha</b> Actualizar en Antivirus de Microsoft Defender. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>O bien
</li>
<li>Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft web</a>.
Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.
</li>
</ol>
</li>
<li>Ejecute un examen completo.
</li>
<li>Reinicie el dispositivo e inténtelo de nuevo.</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508020</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que puede haber un error de configuración del motor; normalmente, esto está relacionado con datos de entrada que no permiten que el motor funcione correctamente.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x805080211
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que Antivirus de Microsoft Defender no pudo poner en cuarentena una amenaza.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508022
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que se requiere un reinicio para completar la eliminación de amenazas.
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es posible que la amenaza ya no esté presente en los medios o que el malware pueda impedir que se pueda examinar el dispositivo.
</tr><tr><td>Solución
</td>
<td>
Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Examen de seguridad de Microsoft</a> actualizar el software de seguridad e inténtelo de nuevo.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508024 </th></tr>
<tr>
<td>Message</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que puede ser necesario realizar un examen completo del sistema.
</td></tr>
<tr>
<td>Solución</td><td>
Ejecute un examen completo del sistema.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508025
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que se requieren pasos manuales para completar la eliminación de amenazas.
</td></tr><tr><td>Solución</td><td>
Siga los pasos de corrección manuales descritos en la Enciclopedia de <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Protección contra malware de Microsoft</a>. Puede encontrar un vínculo específico de la amenaza en el historial de eventos.<br/></td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508026
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es posible que no se pueda quitar dentro del tipo de contenedor.
</td></tr><tr><td>Solución</td><td>
Antivirus de Microsoft Defender no es capaz de corregir las amenazas detectadas dentro del archivo. Considere la posibilidad de quitar manualmente los recursos detectados.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508027
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que la eliminación de amenazas medias y bajas podría deshabilitarse.
</td></tr><tr><td>Solución</td><td>
Compruebe las amenazas detectadas y resuelvalas según sea necesario.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508029
</th>
</tr><tr><td>Message</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es necesario volver a examinar la amenaza.
</td></tr><tr><td>Solución</td><td>
Ejecute un examen completo del sistema.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508030
</th>
</tr><tr><td>Message</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es necesario realizar un examen sin conexión.
</td></tr><tr><td>Solución</td><td>
Ejecute sin conexión Antivirus de Microsoft Defender. Puede leer sobre cómo hacerlo en el artículo sin <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">conexión Antivirus de Microsoft Defender línea</a>.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508031
</th>
</tr><tr><td>Message</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que Antivirus de Microsoft Defender no admite la versión actual de la plataforma y requiere una nueva versión de la plataforma.
</td></tr><tr><td>Solución</td><td>
Solo puede usar Antivirus de Microsoft Defender en Windows 10 y Windows 11. Para Windows 8, Windows 7 y Windows Vista, puede usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>Los siguientes códigos de error se usan durante las pruebas internas de Antivirus de Microsoft Defender.

Si ve estos errores, puede intentar actualizar definiciones [](manage-updates-baselines-microsoft-defender-antivirus.md) y forzar un nuevo análisis directamente en el punto de conexión.


<table>
<tr>
<th colspan="3">Códigos de error internos</th>
</tr>
<tr>
<th><b>Código de error</b></th>
<th>Mensaje mostrado</th>
<th>Posible motivo de error y resolución</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
Compruebe la conexión a Internet y vuelva a ejecutar el examen.
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E
</td>
<td rowspan="34">
Se trata de un error interno. La causa no está claramente definida.
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
Se trata de un error interno. Puede desencadenarse cuando la eliminación de malware no se realiza correctamente.
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
Se trata de un error interno. Puede que se haya desencadenado cuando un examen no se completa.
</td>
</tr>
</table>

## <a name="related-topics"></a>Temas relacionados

- [Informe sobre la Antivirus de Microsoft Defender protección](report-monitor-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
