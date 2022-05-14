---
title: Antivirus de Microsoft Defender identificadores de evento y códigos de error
description: Buscar las causas y soluciones de los identificadores y errores de eventos de Antivirus de Microsoft Defender
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
ms.openlocfilehash: 52105373f0bc6bb70f6433eba4dacb4580a0f804
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416724"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Revisar registros de sucesos y códigos de error para solucionar problemas del Antivirus de Windows Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Si encuentra un problema con Antivirus de Microsoft Defender, puede buscar en las tablas de este tema para encontrar un problema coincidente y una posible solución.

La lista de tablas:

- [Antivirus de Microsoft Defender identificadores de evento](#windows-defender-av-ids) (se aplican a Windows 10, Windows 11 y Windows Server 2016)
- [Antivirus de Microsoft Defender códigos de error de cliente](#error-codes)
- [Códigos de error de cliente de Antivirus de Microsoft Defender internos (utilizados por Microsoft durante el desarrollo y las pruebas)](#internal-error-codes)

> [!TIP]
> También puede visitar el sitio web de demostración de Microsoft Defender para punto de conexión en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las siguientes características funcionan:
>
> - Protección entregada en la nube
> - Aprendizaje rápido (incluido Bloquear a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseados

> [!NOTE]
> El sitio de demostración de Defender para punto de conexión en demo.wd.microsoft.com está en desuso y se eliminará en el futuro.

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>identificadores de eventos de Antivirus de Microsoft Defender

Antivirus de Microsoft Defender registra los identificadores de evento en el registro de eventos de Windows.

Puede ver directamente el registro de eventos o, si tiene una herramienta de administración de eventos e información de seguridad (SIEM) de terceros, también puede consumir [Antivirus de Microsoft Defender identificadores de eventos de cliente](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) para revisar eventos y errores específicos de los puntos de conexión.

En la tabla de esta sección se enumeran los identificadores de evento de Antivirus de Microsoft Defender principales y, siempre que sea posible, se proporcionan soluciones sugeridas para corregir o resolver el error.

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Para ver un evento Antivirus de Microsoft Defender

1. Abra **Visor de eventos**.
2. En el árbol de consola, expanda **Registros de aplicaciones y servicios**, **Microsoft**, **Windows** y, a continuación, **Windows Defender**.
3. Haga doble clic en **Operativo**.
4. En el panel de detalles, vea la lista de eventos individuales para buscar el evento.
5. Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las pestañas **General** y **Detalles** .

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
<b>Se inició un examen antimalware. </b>
</td>
</tr>
<tr>
<td >
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de id. del examen pertinente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo&gt; de examen, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros&gt; de examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Examinar recursos: &lt; Recursos (como archivos, directorios o BHO) que se examinaron.&gt;</dt> 
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
<b>Finalizó un examen antimalware.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de id. del examen pertinente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo&gt; de examen, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros&gt; de examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Domainlt&gt;\&; Tiempo de análisis de usuario&gt;</dt>
<dt>: &lt;duración de un examen.&gt;</dt>
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
<b>Se detuvo un examen antimalware antes de que finalizara. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
<dl>
<dt>Id. de examen: &lt; Número de id. del examen pertinente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo&gt; de examen, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros&gt; de examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Domainlt&gt;&amp;; Tiempo de análisis de usuario&gt;</dt>
<dt>: &lt;duración de un examen.&gt;</dt>
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
<dt>Id. de examen: &lt; Número de id. del examen pertinente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo&gt; de examen, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros&gt; de examen, por ejemplo:<ul>
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
<dt>Id. de examen: &lt; Número de id. del examen pertinente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo&gt; de examen, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros&gt; de examen, por ejemplo:<ul>
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
<dt>Id. de examen: &lt; Número de id. del examen pertinente.&gt;</dt>
<dt> Tipo de examen: &lt;tipo&gt; de examen, por ejemplo:<ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt;parámetros&gt; de examen, por ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Domainlt&gt;\&; Código UserError&gt;</dt>
<dt>: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente antivirus encontró un error y el examen actual se ha detenido. Es posible que se produzca un error en el examen debido a un problema del lado cliente. Este registro de eventos incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), los parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.
Para solucionar este evento:
<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya al <a href="https://go.microsoft.com/fwlink/?LinkId=215163">sitio Soporte técnico de Microsoft</a> y escriba el número de error en el cuadro <b>Buscar</b> para buscar el código de error.</li>
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
<b>El motor antimalware encontró malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;tipo&gt; de detección, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Usuario: iniciado por el usuario</li>
<li>Sistema: iniciado por el sistema</li>
<li>En tiempo real: componente iniciado en tiempo real</li>
<li>IOAV: se han iniciado las descargas de IE y los datos adjuntos Outlook Express</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Inicio anticipado de Antimalware (ELAM). Esto incluye el malware detectado por la secuencia de arranque.</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también lo pueden invocar terceros.
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
<b>La plataforma antimalware realizó una acción para proteger el sistema contra malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina contra malware u otro software potencialmente no deseado. Para obtener más información, vea los artículos siguientes: 
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
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt>
<dt> Acción: &lt;acción&gt;, por ejemplo:<ul>
<li>Limpiar: se ha limpiado el recurso</li>
<li>Cuarentena: el recurso se puso en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera.</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se ha bloqueado la ejecución del recurso</li>
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
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema contra malware u otro software potencialmente no deseado, pero se produjo un error en la acción.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al tomar medidas sobre malware u otro software potencialmente no deseado. Para obtener más información, vea los artículos siguientes: 
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
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; File pathAction&gt;</dt>
<dt>: &lt;acción&gt;, por ejemplo:<ul>
<li>Limpiar: se ha limpiado el recurso</li>
<li>Cuarentena: el recurso se puso en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera.</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se ha bloqueado la ejecución del recurso</li>
</ul>
</dt>
<dt>Código de error: &lt; Código&gt; de error Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;descripción&gt; del error Descripción del error. </dt> 
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
<b>La plataforma antimalware restauró un elemento de la cuarentena. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha restaurado un elemento de la cuarentena. Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt; del</dt> 
<dt>archivoUsuario: &lt;Domainlt&gt;\&; UserSignature&gt;</dt> 
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
<b>La plataforma antimalware no pudo restaurar un elemento de la cuarentena. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar restaurar un elemento de la cuarentena. Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt; del</dt> 
<dt>archivoUsuario: &lt;Domainlt&gt;\&; Código UserError&gt;</dt>
<dt>: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;descripción&gt; del error Descripción del error. </dt> 
<dt>Versión de firma: &lt; Versión de&gt; definición</dt> 
<dt>VersionEngine: &lt;versión&gt; Antimalware Engine</dt>
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
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt; del</dt> 
<dt>archivoUsuario: &lt;Domainlt&gt;\&; UserSignature&gt;</dt> 
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
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt; del</dt> 
<dt>archivoUsuario: &lt;Domainlt&gt;\&; Código UserError&gt;</dt>
<dt>: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;descripción&gt; del error Descripción del error. </dt> 
<dt>Versión de firma: &lt; Versión de&gt; definición</dt> 
<dt>VersionEngine: &lt;versión&gt; Antimalware Engine</dt>
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
<b>El historial de eliminación de la plataforma antimalware de malware y otro software potencialmente no deseado.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha eliminado el historial de malware y otro software potencialmente no deseado.
<dl>
<dt>Hora: la hora en que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenaza para que no haya ninguna confusión con respecto a si es el tiempo de corrección o el tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
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
Antivirus de Microsoft Defender ha encontrado un error al intentar eliminar el historial de malware y otro software potencialmente no deseado.
<dl>
<dt>Hora: la hora en que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenaza para que no haya ninguna confusión con respecto a si es el tiempo de corrección o el tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Código UserError&gt;</dt>
<dt>: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar. </dt>
<dt>Descripción del error: &lt;descripción&gt; del error Descripción del error. </dt>
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
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;origen&gt; de detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;tipo&gt; de detección, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Usuario: iniciado por el usuario</li>
<li>Sistema: iniciado por el sistema</li>
<li>En tiempo real: componente iniciado en tiempo real</li>
<li>IOAV: se han iniciado las descargas de IE y los datos adjuntos Outlook Express</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Inicio anticipado de Antimalware (ELAM). Esto incluye el malware detectado por la secuencia de arranque.</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también lo pueden invocar terceros.
UACStatus</dt>
<dt>: &lt;StatusUser&gt;</dt>
<dt>: &lt;Domainlt&gt;\&; Nombre de userprocess&gt;</dt>
<dt>: &lt;procese en el identificador PIDSignature&gt;</dt>
<dt>: gravedad de coincidencia de enumeración.</dt> 
<dt>Versión de firma: &lt; &gt;Versión de definición</dt> 
<dt>VersionEngine: &lt;Antimalware Engine versionFidelity&gt;</dt> 
<dt>Label:</dt>
<dt>Target File Name: &lt;Nombre de archivo&gt; Nombre del archivo.</dt>
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
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;origen&gt; de detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;tipo&gt; de detección, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Usuario: iniciado por el usuario</li>
<li>Sistema: iniciado por el sistema</li>
<li>En tiempo real: componente iniciado en tiempo real</li>
<li>IOAV: se han iniciado las descargas de IE y los datos adjuntos Outlook Express</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Inicio anticipado de Antimalware (ELAM). Esto incluye el malware detectado por la secuencia de arranque.</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también lo pueden invocar terceros.
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
No se requiere ninguna acción. Antivirus de Microsoft Defender puede suspender y realizar acciones rutinarias en esta amenaza. Si desea quitar la amenaza manualmente, en la interfaz de Antivirus de Microsoft Defender, haga clic en <b>Limpiar equipo</b>.
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
<b>La plataforma antimalware realizó una acción para proteger el sistema contra malware u otro software potencialmente no deseado. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina contra malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;origen&gt; de detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;tipo&gt; de detección, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Usuario: iniciado por el usuario</li>
<li>Sistema: iniciado por el sistema</li>
<li>En tiempo real: componente iniciado en tiempo real</li>
<li>IOAV: se han iniciado las descargas de IE y los datos adjuntos Outlook Express</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Inicio anticipado de Antimalware (ELAM). Esto incluye el malware detectado por la secuencia de arranque.</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también lo pueden invocar terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; Nombre de userprocess&gt;</dt>
<dt>: &lt;procese en pidaction&gt;</dt>
<dt>: &lt;acción&gt;, por ejemplo:<ul>
<li>Limpiar: se ha limpiado el recurso</li>
<li>Cuarentena: el recurso se puso en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera.</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se ha bloqueado la ejecución del recurso</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de acciones&gt; adicionales</dt> 
<dt>Código de error: &lt;código&gt; de error Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt> 
<dt>Versión de firma: &lt; Versión de&gt; definición</dt> 
<dt>VersionEngine: &lt;Antimalware Engine versión&gt;</dt> NOTA: Siempre que Antivirus de Microsoft Defender, Microsoft Security Essentials, herramienta de eliminación de software malintencionado o System Center Endpoint Protection detecta un malware, restaurará los siguientes servicios y configuración del sistema que el malware podría haber cambiado:<ul>
<li>Configuración predeterminada de Internet Explorer o Microsoft Edge</li>
<li>Configuración de Access Control de usuario</li>
<li>Configuración de Chrome</li>
<li>Datos de control de arranque</li>
<li>Regedit y la configuración del Registro del Administrador de tareas</li>
<li>Windows Update, Servicio de transferencia inteligente en segundo plano y servicio de llamada a procedimiento remoto</li>
<li>Windows archivos del sistema operativo</li></ul>
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
No es necesario realizar ninguna acción. Antivirus de Microsoft Defender ha quitado o puesto en cuarentena una amenaza.
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
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema contra malware u otro software potencialmente no deseado, pero se produjo un error en la acción. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error no crítico al tomar medidas sobre malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;origen&gt; de detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;tipo&gt; de detección, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Usuario: iniciado por el usuario</li>
<li>Sistema: iniciado por el sistema</li>
<li>En tiempo real: componente iniciado en tiempo real</li>
<li>IOAV: se han iniciado las descargas de IE y los datos adjuntos Outlook Express</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Inicio anticipado de Antimalware (ELAM). Esto incluye el malware detectado por la secuencia de arranque.</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también lo pueden invocar terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; Nombre de userprocess&gt;</dt>
<dt>: &lt;procese en pidaction&gt;</dt>
<dt>: &lt;acción&gt;, por ejemplo:<ul>
<li>Limpiar: se ha limpiado el recurso</li>
<li>Cuarentena: el recurso se puso en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera.</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se ha bloqueado la ejecución del recurso</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de acciones&gt; adicionales</dt> 
<dt>Código de error: &lt;código&gt; de error Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt> 
<dt>Versión de firma: &lt; Versión de&gt; definición</dt> 
<dt>VersionEngine: &lt;Antimalware Engine versión&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. Antivirus de Microsoft Defender no pudo completar una tarea relacionada con la corrección de malware. Esto no es un error crítico.
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
<b>La plataforma antimalware encontró un error crítico al intentar tomar medidas sobre malware u otro software potencialmente no deseado. Hay más detalles en el mensaje de evento.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error crítico al tomar medidas sobre malware u otro software potencialmente no deseado.<br/>Para obtener más información, vea los artículos siguientes: 
<dl>
<dt>Nombre: &lt; &gt;Nombre de amenazaID</dt>
<dt>: &lt;Id.&gt;</dt>
<dt> de amenazaSeveridad: &lt;Gravedad&gt;, por ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; &gt;Descripción de la categoría, por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Camino: &lt; Ruta de acceso&gt;</dt>
<dt> del archivoDetection Origen: &lt;origen&gt; de detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de detección: &lt;tipo&gt; de detección, por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de detección: &lt;origen&gt; de detección, por ejemplo:<ul>
<li>Usuario: iniciado por el usuario</li>
<li>Sistema: iniciado por el sistema</li>
<li>En tiempo real: componente iniciado en tiempo real</li>
<li>IOAV: se han iniciado las descargas de IE y los datos adjuntos Outlook Express</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Inicio anticipado de Antimalware (ELAM). Esto incluye el malware detectado por la secuencia de arranque.</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PowerShell, VBS), aunque también lo pueden invocar terceros.
UACUser</dt>
<dt>: &lt;Domainlt&gt;\&; Nombre de userprocess&gt;</dt>
<dt>: &lt;procese en pidaction&gt;</dt>
<dt>: &lt;acción&gt;, por ejemplo:<ul>
<li>Limpiar: se ha limpiado el recurso</li>
<li>Cuarentena: el recurso se puso en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera.</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se ha bloqueado la ejecución del recurso</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de acciones&gt; adicionales</dt> 
<dt>Código de error: &lt;código&gt; de error Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt> 
<dt>Versión de firma: &lt; Versión de&gt; definición</dt> 
<dt>VersionEngine: &lt;Antimalware Engine versión&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente Antivirus de Microsoft Defender encontró este error debido a problemas críticos. Es posible que el punto de conexión no esté protegido. Revise la descripción del error y, a continuación, siga los pasos pertinentes <b>de la acción Usuario</b> que se indican a continuación.
<table>
<tr>
<th>Acción</th>
<th>Acción del usuario</th>
</tr>
<tr>
<td>
<b>Eliminar</b>
</td>
<td>
Actualice las definiciones y compruebe que la eliminación se realizó correctamente.
</td>
</tr>
<tr>
<td>
<b>Limpio</b>
</td>
<td>
Actualice las definiciones y compruebe que la corrección se realizó correctamente.
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
<b>Conceder</b>
</td>
<td>
Compruebe que el usuario tiene permiso para acceder a los recursos necesarios.
</td>
</tr>
</table>

Si este evento persiste:<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya al <a href="https://go.microsoft.com/fwlink/?LinkId=215163">sitio Soporte técnico de Microsoft</a> y escriba el número de error en el cuadro <b>Buscar</b> para buscar el código de error.</li>
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
<dt>Versión actual de la plataforma: &lt; Versión&gt; actual</dt> 
<dt>de la plataformaThreat Resource Path: &lt;PathHashes&gt;</dt>
<dt>: &lt;Hashes&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging unsigned</b>.</div>
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
<b>El acceso controlado a carpetas (CFA) bloqueó un proceso que no es de confianza para realizar cambios en la memoria. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
El acceso controlado a carpetas ha bloqueado un proceso que no es de confianza para modificar potencialmente los sectores de disco.
<br/> Para obtener más información sobre el registro de eventos, consulte lo siguiente:
<dl>
<dt>Eventid: &lt; EventID&gt;, por ejemplo: 1127Version</dt>
<dt>: &lt;Version&gt;, por ejemplo: 0Level</dt>
<dt>: &lt;Level&gt;, por ejemplo: win:WarningTimeCreated</dt>
<dt>: &lt;SystemTime&gt;, hora en que se creó el eventoEventRecordID</dt>
<dt>: &lt;EventRecordID&gt;, número de índice del evento en el evento logExecution</dt> 
<dt>ProcessID: &lt;Execution ProcessID&gt;, proceso que generó el canal</dt> 
<dt>&gt;eventChannel: &lt;Event, por ejemplo: Microsoft- Windows-Windows Defender/</dt>
<dt>OperationalComputer: &lt;Nombre&gt; del</dt> 
<dt>equipoSeguridad UserID: &lt;UserID&gt;</dt> 
<dt>De seguridadNombre del producto: &lt;Nombre&gt; del producto, por ejemplo: Antivirus de Microsoft Defender</dt> 
<dt>Producción: &lt;Versión&gt; del</dt> 
<dt>productoDetection Hora: &lt;tiempo&gt; de detección, hora en que CFA bloqueó un proceso que no es de confianzaUsuario</dt>
<dt>: &lt;Domainlt&gt;\&; UserPath&gt;</dt>
<dt>: &lt;nombre&gt; del dispositivo, nombre del dispositivo o disco al que un proceso que no es de confianza al que se ha accedido para la modificaciónNombre</dt> del 
<dt>proceso: &lt;ruta de acceso&gt; del proceso, nombre de la ruta de acceso del proceso al que CFA bloqueó el acceso al dispositivo o al disco para su modificaciónSeguridad</dt> 
<dt>de inteligencia versión: &lt;Versión&gt; de inteligencia de seguridad</dt> Versión de diseño
<dt>: &lt;Antimalware Engine versión&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El usuario puede agregar el proceso bloqueado a la lista <i>Proceso permitido</i> para CFA mediante PowerShell o Seguridad de Windows Center.
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
<dt>Versión de la plataforma: &lt; Versión actual de&gt; la</dt> 
<dt>plataformaSignature Version: &lt;Definition versionEngine&gt;</dt> 
<dt>Version: &lt;Antimalware Engine version&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente Antivirus de Microsoft Defender está en un estado correcto. Este evento se notifica cada hora.
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
<b>Endpoint Protection informe de estado de cliente (hora utc)</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Informe de estado de cliente antivirus.
<dl>
<dt>Versión de la plataforma: &lt; Versión actual de&gt; la plataforma</dt> 
<dt>Versión de ingeniería: &lt;versión Antimalware Engine Versión&gt;</dt> 
<dt>del motor de inspección en tiempo real de red Versión del motor&gt; de &lt;inspección en tiempo real</dt> 
<dt>Versión de la firma del antivirus: &lt;Versión&gt; de firma del antivirus</dt> 
<dt>Versión de firma de Antispyware: &lt;Versión&gt; de firma de AntispywareRed</dt> 
<dt>versión de la firma de inspección en tiempo real: &lt; Versión&gt; de la firma de inspección en tiempo real</dt> de 
<dt>&lt;red Estado de protección en tiempo real Estado de protección&gt; en tiempo real (Habilitado o Deshabilitado)</dt>
<dt>Estado de OA: &lt;Estado&gt; de acceso (habilitado o deshabilitado)</dt>
<dt>Estado ioAV: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: Antivirus signature age (&lt;Antigüedad&gt; de la firma del antivirus)  (en días)</dt> 
<dt>Antigüedad de la firma antispyware: &lt; Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt; Tiempo&gt; de creación de firmas</dt> 
<dt>antivirusAntispyware signature creation time: ?&lt; Tiempo de creación&gt; de firmas antispywareLa</dt> 
<dt>hora de inicio del examen rápido: ?&lt; Hora de inicio&gt; del último examen</dt> 
<dt>rápidoLa hora de finalización del examen rápido: ?&lt; Última hora&gt; de finalización del examen rápidoLa</dt> 
<dt>última fuente de examen rápido: &lt;último origen&gt; de examen rápido (0 = no se ejecutó el examen, 1 = iniciado por el usuario, 2 = iniciado por el sistema)</dt>
<dt>Última hora de inicio del examen completo: ?&lt; Última hora&gt; de inicio del examen</dt> 
<dt>completoLa hora de finalización del examen completo: ?&lt; Última hora&gt; de finalización del examen completoLa</dt> 
<dt>última fuente de examen completo: &lt;último origen&gt; de examen completo (0 = no se ejecutó el examen, 1 = iniciado por el usuario, 2 = iniciado por el sistema)</dt>
<dt>Estado del producto: Para solucionar problemas internos
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
<dt>Versión de firma actual: &lt; Versión&gt; de firma</dt> 
<dt>actualPrevious Signature Version: &lt;Versión de firma&gt;</dt>
<dt> anteriorTipo de firma: &lt;Tipo&gt; de firma, por ejemplo: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Tipo de actualización: &lt; &gt;Tipo de actualización, full o delta.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; UserCurrent&gt;</dt> 
<dt>Engine Version: &lt;Versión actual del motorPrevious&gt;</dt> 
<dt>Engine Version: &lt;Versión anterior del motor&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente Antivirus de Microsoft Defender está en un estado correcto. Este evento se notifica cuando las firmas se actualizan correctamente.
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
Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar las firmas.
<dl>
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número de&gt;</dt> 
<dt>versiónPrevious security intelligence version: &lt;Versión&gt;</dt>
<dt> anteriorActualizar origen: &lt;Actualizar origen&gt;, por ejemplo:
<ul>
<li>Carpeta de actualización de inteligencia de seguridad</li>
<li>Servidor de actualización de inteligencia de seguridad interna</li>
<li>Microsoft Update Server</li>
<li>Compartir archivos</li>
<li>Centro de protección contra malware de Microsoft (MMPC)</li>
</ul>
</dt>
<dt>Fase de actualización: &lt;fase&gt; de actualización, por ejemplo:
<ul>
<li>Buscar </li>
<li>Descargar</li>
<li>Instalar</li>
</ul>
</dt>
<dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre del servidor para Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt> Tipo de firma: &lt;tipo&gt; de firma, por ejemplo: <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Tipo de actualización: &lt; &gt;Tipo de actualización, full o delta.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; UserCurrent&gt;</dt> 
<dt>Engine Version: &lt;Current engine versionPrevious&gt;</dt> 
<dt>Engine Version: &lt;Previous engine versionError&gt;</dt> 
<dt>Code: &lt;Error code&gt; Result code associated with threat status . Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Este error se produce cuando hay un problema al actualizar las definiciones.
Para solucionar este evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerce un nuevo análisis directamente en el punto de conexión.</li>
<li>Revise las entradas del archivo %Windir%\WindowsUpdate.log para obtener más información sobre este error.</li>
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
<b>El motor antimalware se actualizó correctamente. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender versión del motor se ha actualizado.
<dl>
<dt>Versión actual del motor: &lt; Versión&gt; actual</dt> del 
<dt>motorPrevious Engine Version: &lt;Versión anterior del motorTipo&gt;</dt> 
<dt>de ingeniería: &lt;Tipo&gt; de motor, motor antimalware o motor del sistema de inspección de red.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Usuario&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente Antivirus de Microsoft Defender está en un estado correcto. Este evento se notifica cuando el motor antimalware se actualiza correctamente.
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
<b>Error en la actualización del motor antimalware. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar el motor.
<dl>
<dt>Nueva versión del motor:</dt>
<dt>Versión anterior del motor: &lt;Versión&gt; anterior del motorTipo</dt> 
<dt>de ingeniería: &lt;tipo&gt; de motor, motor antimalware o motor del sistema de inspección de red.</dt> 
<dt>Usuario: &lt; Domainlt&gt;\&; Código UserError&gt;</dt>
<dt>: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Error en la actualización del cliente Antivirus de Microsoft Defender. Este evento se produce cuando el cliente no se actualiza a sí mismo. Este evento suele deberse a una interrupción de la conectividad de red durante una actualización.
Para solucionar este evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerce un nuevo análisis directamente en el punto de conexión.</li>
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
<b>Se produjo un problema al cargar definiciones de antimalware. El motor antimalware intentará cargar el último conjunto correcto de definiciones conocido.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar cargar firmas y intentará revertir a un conjunto de firmas conocido y correcto.
<dl>
<dt>Firmas tentativas:</dt>
<dt>Código de error: &lt;código&gt; de error Código de error Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt> 
<dt>Versión de firma: &lt; Versión de&gt; definición</dt> 
<dt>Versionengine: &lt;versión&gt; del motor antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y produjo un error. Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado. Antivirus de Microsoft Defender intentará revertir a un conjunto de definiciones conocido y correcto.
Para solucionar este evento:
<ol>
<li>Reinicie el equipo e inténtelo de nuevo.</li>
<li>Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">sitio de Inteligencia de seguridad de Microsoft</a>.
Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como una solución a largo plazo para actualizar definiciones.
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
<b>No se pudo cargar el motor antimalware porque la plataforma antimalware no está actualizada. La plataforma antimalware cargará el último motor antimalware correcto conocido e intentará actualizarlo.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender no se pudo cargar el motor antimalware porque no se admite la versión actual de la plataforma. Antivirus de Microsoft Defender se revertirá al último motor correcto conocido y se intentará una actualización de la plataforma.
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
<dt>Versión actual de la plataforma: &lt; Versión&gt; actual</dt> 
<dt>de la plataforma Código de error: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
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
<b>La plataforma pronto estará obsoleta. Descargue la plataforma más reciente para mantener la protección actualizada.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender pronto necesitará una versión más reciente de la plataforma para admitir futuras versiones del motor antimalware. Descargue la plataforma de Antivirus de Microsoft Defender más reciente para mantener el mejor nivel de protección disponible.
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
<b>El motor antimalware usó el servicio de firma dinámica para obtener definiciones adicionales. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender usa <i>el servicio de firma dinámica</i> para recuperar firmas adicionales que ayuden a proteger el equipo.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma&gt; actualTipo</dt> de firma: &lt;Tipo&gt; de firma, por ejemplo:
<dt> <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión&gt; actual del motorTipo</dt> de firma dinámica: &lt;tipo&gt; de firma dinámica, por ejemplo:
<dt>
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de acceso de persistencia: &lt; PathDynamic&gt;</dt> 
<dt>Signature Version: &lt;Version numberDynamic&gt;</dt> 
<dt>Signature Compilation Timestamp: &lt;TimestampPersistence&gt;</dt>
<dt> Limit Type: &lt;Persistence limit type&gt;, for example:
<ul>
<li>Versión de VDM</li>
<li>Timestamp</li>
<li>Sin límite</li>
</ul>
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma de fastpath.</dt>
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
<b>El servicio de firma dinámica eliminó las definiciones dinámicas obsoletas. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha usado <i>el servicio de firma dinámica</i> para descartar firmas obsoletas.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma&gt; actualTipo</dt> de firma: &lt;Tipo&gt; de firma, por ejemplo:
<dt> <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión&gt; actual del motorTipo</dt> de firma dinámica: &lt;tipo&gt; de firma dinámica, por ejemplo:
<dt>
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de acceso de persistencia: &lt; PathDynamic&gt;</dt> 
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
<dt>Límite de persistencia: límite de persistencia de la firma de fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente Antivirus de Microsoft Defender está en un estado correcto. Este evento se notifica cuando el servicio de firma dinámica elimina correctamente las definiciones dinámicas obsoletas.
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
<b>El motor antimalware encontró un error al intentar usar el servicio de firma dinámica. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar usar <i>el servicio de firma dinámica</i>.
<dl>
<dt>Versión de firma actual: &lt; Versión de firma&gt; actualTipo</dt> de firma: &lt;Tipo&gt; de firma, por ejemplo:
<dt> <ul>
<li>Antivirus</li>
<li>Antiespía</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión&gt; actual</dt> 
<dt>del motor Código de error: &lt;código de error Código&gt; de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
<dt> Tipo de firma dinámica: &lt;tipo&gt; de firma dinámica, por ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de acceso de persistencia: &lt; PathDynamic&gt;</dt> 
<dt>Signature Version: &lt;Version numberDynamic&gt;</dt> 
<dt>Signature Compilation Timestamp: &lt;TimestampPersistence&gt;</dt>
<dt> Limit Type: &lt;Persistence limit type&gt;, for example:
<ul>
<li>Versión de VDM</li>
<li>Timestamp</li>
<li>Sin límite</li>
</ul>
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma de fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Compruebe la configuración de conectividad a Internet.
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
Antivirus de Microsoft Defender descarta todas las firmas del <i>servicio de firma dinámica</i>.
<dl>
<dt>Versión de firma actual: &lt;versión de firma actual&gt;</dt>
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
<b>El motor antimalware descargó un archivo limpio. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender descargó un archivo limpio.
<dl>
<dt>Nombre: &lt; &gt; Nombre de archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión&gt; de firma actual</dt> 
<dt>Versión actual del motor: &lt;versión&gt; actual del motor</dt>
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
<b>El motor antimalware no pudo descargar un archivo limpio. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar descargar un archivo limpio.
<dl>
<dt>Nombre: &lt; &gt; Nombre de archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión&gt; de firma actual</dt> 
<dt>Versión actual del motor: &lt;Versión&gt; actual del motor</dt> 
<dt>Código de error Código de &lt;error&gt; Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Compruebe la configuración de conectividad a Internet.
El cliente Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica. Es probable que este error se deba a un problema de conectividad de red.
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
<b>El motor antimalware se descargó y está configurado para ejecutarse sin conexión en el siguiente reinicio del sistema.</b>
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
<b>El motor antimalware no pudo descargar y configurar un examen sin conexión.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender ha encontrado un error al intentar descargar y configurar el antivirus sin conexión.
<dl>
<dt>Código de error: &lt; Código&gt; de error Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
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
<b>Pronto finalizará la compatibilidad con antimalware para esta versión del sistema operativo. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
La compatibilidad con el sistema operativo expirará en breve. Ejecutar Antivirus de Microsoft Defender en un sistema operativo sin soporte técnico no es una solución adecuada para protegerse contra amenazas.
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
<b>La compatibilidad con antimalware para este sistema operativo ha finalizado. Debe actualizar el sistema operativo para obtener soporte técnico continuo. </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
La compatibilidad con el sistema operativo ha expirado. Ejecutar Antivirus de Microsoft Defender en un sistema operativo sin soporte técnico no es una solución adecuada para protegerse contra amenazas.
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
<b>El motor antimalware ya no admite este sistema operativo y ya no protege el sistema contra malware. </b>
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
Antivirus de Microsoft Defender Real-Time característica protección ha encontrado un error y ha producido un error.
<dl>
<dt>Característica: &lt;característica&gt;, por ejemplo:
<ul>
<li>En el acceso</li>
<li>Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Código de error: &lt; Código&gt; de error Código de resultado asociado al estado de la amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt> 
<dt>Motivo: la razón por la que Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque es posible que el sistema no esté protegido durante algún tiempo.
La característica de protección en tiempo real del cliente de Antivirus de Microsoft Defender encontró un error porque uno de los servicios no se pudo iniciar.
Si va seguido de un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error.
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
Antivirus de Microsoft Defender Protección en tiempo real ha reiniciado una característica. Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba inactivo.
<dl>
<dt>Característica: &lt;característica&gt;, por ejemplo:
<ul>
<li>En el acceso</li>
<li>Descargas de IE y datos adjuntos de Outlook Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Motivo: la razón por la que Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Se ha reiniciado la característica de protección en tiempo real. Si este evento se produce de nuevo, póngase en contacto con <a href="https://go.microsoft.com/fwlink/?LinkId=215491">el soporte técnico de Microsoft</a>.
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
Antivirus de Microsoft Defender análisis de protección en tiempo real para detectar malware y otro software potencialmente no deseado se ha habilitado.
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
Antivirus de Microsoft Defender examen de protección en tiempo real para detectar malware y otro software potencialmente no deseado se deshabilitó.
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
Antivirus de Microsoft Defender configuración de la característica de protección en tiempo real ha cambiado.
<dl>
<dt>Característica: &lt;característica&gt;, por ejemplo:
<ul>
<li>En el acceso</li>
<li>Descargas de IE y datos adjuntos de Outlook Express</li>
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
<b>La configuración de la plataforma antimalware ha cambiado.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender configuración ha cambiado. Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.
<dl>
<dt>Valor anterior: &lt; Número de&gt; valor antiguo Valor de configuración del antivirus antiguo.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de&gt; valor Nuevo valor de configuración del antivirus.</dt>
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
<b>El motor antimalware encontró un error y produjo un error.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Antivirus de Microsoft Defender motor se ha terminado debido a un error inesperado.
<dl>
<dt>Tipo de error: &lt; &gt;Tipo de error, por ejemplo: Crash o HangException</dt> 
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
<li>Para antimalware, antivirus y spyware, en un símbolo del sistema con <b>privilegios elevados, escriba net stop msmpsvc</b> y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor antimalware.</li>
<li>Para el <i>sistema de inspección</i> de red, en un símbolo del sistema con <b>privilegios elevados, escriba net start nissrv</b> y, a continuación, escriba <b>net start nissrv</b> para reiniciar el motor del <i>sistema de inspección</i> de red mediante el archivo NiSSRV.exe.
</li>
</ul>
</li>
<li>Si se produce un error de la misma manera, busque el código de error accediendo al <a href="https://go.microsoft.com/fwlink/?LinkId=215163">sitio Soporte técnico de Microsoft</a> y escribiendo el número de error en el cuadro <b>Buscar</b> y póngase en contacto con <a href="https://go.microsoft.com/fwlink/?LinkId=215491">el soporte técnico de Microsoft</a>.</li>
</ol>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El motor de cliente de Antivirus de Microsoft Defender se detuvo debido a un error inesperado.
Para solucionar este evento:
<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya al <a href="https://go.microsoft.com/fwlink/?LinkId=215163">sitio Soporte técnico de Microsoft</a> y escriba el número de error en el cuadro <b>Buscar</b> para buscar el código de error.</li>
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
Antivirus de Microsoft Defender análisis de malware y otro software potencialmente no deseado se ha habilitado.
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
Antivirus de Microsoft Defender examen de malware y otro software potencialmente no deseado está deshabilitado.
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
Antivirus de Microsoft Defender se ha habilitado el examen en busca de virus.
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
Antivirus de Microsoft Defender examen de virus está deshabilitado.
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
Si la protección contra alteraciones está habilitada, cualquier intento de cambiar cualquiera de la configuración de Defender si está bloqueado y se genera el identificador de evento 5013 que indica qué cambio de configuración se bloqueó.
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
Antivirus de Microsoft Defender ha entrado en un período de gracia y pronto expirará. Después de la expiración, este programa deshabilitará la protección contra virus, spyware y otro software potencialmente no deseado.
<dl>
<dt>Motivo de expiración: el motivo Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la fecha Antivirus de Microsoft Defender expirará.</dt>
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
<dt>código de error: &lt;código&gt; de error Código de resultado asociado al estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción&gt; del error Descripción del error. </dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Antivirus de Microsoft Defender códigos de error de cliente Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le proporcionará un código de error para ayudarle a solucionar el problema. Con frecuencia, un error significa que se produjo un problema al instalar una actualización.
En esta sección se proporciona la siguiente información sobre Antivirus de Microsoft Defender errores de cliente.
- El código de - error El posible motivo del error - Consejo sobre lo que debe hacer ahora

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
Este error indica que es posible que se haya quedado sin memoria.
</td>
</tr>
<tr>
<td>Solución</td>
<td>
<ol>
<li>Compruebe la memoria disponible en el dispositivo.</li>
<li>Cierre las aplicaciones sin usar que se ejecutan para liberar memoria en el dispositivo.</li>
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
<li>Actualice las definiciones. Cualquiera de los dos:<ol>
<li>Haga clic en el botón <b>Actualizar definiciones</b> de la pestaña <b>Actualizar</b> de Antivirus de Microsoft Defender. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>O bien
</li>
<li>Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">sitio de Inteligencia de seguridad de Microsoft</a>.
Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como una solución a largo plazo para actualizar definiciones.
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
Este error indica que podría haber un error de configuración del motor; Normalmente, esto está relacionado con los datos de entrada que no permiten que el motor funcione correctamente.
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
Este error indica que es posible que la amenaza ya no esté presente en los medios, o que el malware podría impedir que digitalizara el dispositivo.
</tr><tr><td>Solución
</td>
<td>
Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Examen de seguridad de Microsoft</a> actualice el software de seguridad e inténtelo de nuevo.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508024 </th></tr>
<tr>
<td>Message</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es posible que sea necesario realizar un examen completo del sistema.
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
Siga los pasos de corrección manual descritos en la <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Enciclopedia de protección contra malware de Microsoft</a>. Puede encontrar un vínculo específico de la amenaza en el historial de eventos.<br/></td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508026
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es posible que no se admita la eliminación dentro del tipo de contenedor.
</td></tr><tr><td>Solución</td><td>
Antivirus de Microsoft Defender no puede corregir las amenazas detectadas dentro del archivo. Considere la posibilidad de quitar manualmente los recursos detectados.
</td>
</tr>
<tr>
<th colspan="2">Código de error: 0x80508027
</th>
</tr><tr><td>Message</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Posible motivo</td>
<td>
Este error indica que es posible que se deshabilite la eliminación de amenazas bajas y medianas.
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
Este error indica que se requiere un examen sin conexión.
</td></tr><tr><td>Solución</td><td>
Ejecute Antivirus de Microsoft Defender sin conexión. Puede leer sobre cómo hacerlo en el <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">artículo de Antivirus de Microsoft Defender sin conexión</a>.
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

Si ve estos errores, puede intentar [actualizar las definiciones](manage-updates-baselines-microsoft-defender-antivirus.md) y forzar un nuevo análisis directamente en el punto de conexión.


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
Se trata de un error interno. Es posible que se haya desencadenado cuando un examen no se completa.
</td>
</tr>
</table>

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)


## <a name="related-topics"></a>Temas relacionados

- [Informe sobre Antivirus de Microsoft Defender protección](report-monitor-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
