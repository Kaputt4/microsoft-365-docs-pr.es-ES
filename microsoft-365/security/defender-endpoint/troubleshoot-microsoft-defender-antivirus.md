---
title: Códigos de error e IDs de eventos antivirus de Microsoft Defender
description: Buscar las causas y soluciones para los errores y los IDs de eventos de Antivirus de Microsoft Defender
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d78728ae6b79914e5e9bac46e000d633793ae991
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691603"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Revisar los registros de eventos y los códigos de error para solucionar problemas con Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Si encuentra un problema con Microsoft Defender Antivirus, puede buscar en las tablas de este tema para encontrar un problema de coincidencia y una posible solución.

La lista de tablas:

- [IDs de eventos](#windows-defender-av-ids) de Antivirus de Microsoft Defender (se aplican a Windows 10 y Windows Server 2016)
- [Códigos de error de cliente de Antivirus de Microsoft Defender](#error-codes)
- [Códigos de error de cliente de Antivirus de Microsoft Defender internos (usados por Microsoft durante el desarrollo y las pruebas)](#internal-error-codes)

> [!TIP]
> También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:
> 
> - Protección entregada en la nube
> - Aprendizaje rápido (incluido Bloquear a primera vista)
> - Bloqueo de aplicaciones potencialmente no deseado

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>IDs de eventos de Antivirus de Microsoft Defender

Antivirus de Microsoft Defender registra los IDs de eventos en el registro de eventos de Windows.

Puede ver directamente el registro de eventos, o si tiene una herramienta de administración de eventos y información de seguridad (SIEM) de terceros, también puede usar los [IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de eventos del cliente antivirus de Microsoft Defender para revisar eventos y errores específicos de los puntos de conexión.

En la tabla de esta sección se enumeran los principales IDs de eventos de Antivirus de Microsoft Defender y, siempre que sea posible, se proporcionan soluciones sugeridas para corregir o resolver el error. 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Para ver un evento antivirus de Microsoft Defender

1.  Abra **el Visor de eventos**.
2.  En el árbol de consola, expanda **Registros de aplicaciones y** servicios , a continuación, **Microsoft**, a continuación, **Windows** y, a continuación, **Windows Defender**.
3.  Haga doble clic en **Operativo**.
4.  En el panel de detalles, vea la lista de eventos individuales para buscar el evento.
5.  Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las **pestañas General** **y** Detalles.

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
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Recursos de examen: &lt; Recursos (como archivos/directorios/BHO) que se &gt; examinaron.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
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
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
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
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Dominio &gt; &amp; lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
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
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
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
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
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
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:<ul>
<li>Examen completo</li>
<li>Examen rápido</li>
<li>Examen del cliente</li>
</ul>
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente antivirus encontró un error y se detuvo el examen actual. El examen puede producir un error debido a un problema del lado cliente. Este registro de evento incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.
Para solucionar este evento:
<ol>
<li>Vuelva a ejecutar el examen.</li>
<li>Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</li>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.
Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión
<dt> &lt; de &gt; </dt>definición Versión del
<dt>motor: versión del motor &lt; &gt; antimalware</dt>
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
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt> Action: &lt; Action , por &gt; ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
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
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta &gt; de acceso</dt> 
<dt> de archivo &lt; Acción: Acción , por &gt; ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
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
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
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
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.
Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en el identificador de firma
<dt> &lt; &gt; PID:</dt>
<dt>Gravedad de coincidencia de enumeración.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>Fidelity
<dt>Label:</dt>
<dt>Target File Name: File name Name of the &lt; &gt; file.</dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.
Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión
<dt> &lt; de &gt; </dt>definición Versión del
<dt>motor: versión del motor &lt; &gt; antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No se requiere ninguna acción. Antivirus de Microsoft Defender puede suspender y tomar medidas rutinarias en esta amenaza. Si desea quitar la amenaza manualmente, en la interfaz antivirus de Microsoft Defender, haga clic <b>en Limpiar equipo</b>.
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.
Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; &gt;</dt>Versión del motor de definición: versión del motor
<dt> &lt; &gt; antimalware</dt> NOTA: siempre que Antivirus de Microsoft Defender, Microsoft Security Essentials, Herramienta de eliminación de software malintencionado o System Center Endpoint Protection detecte un malware, restaurará la siguiente configuración del sistema y los servicios que el malware podría haber cambiado:<ul>
<li>Configuración predeterminada de Internet Explorer o Microsoft Edge</li>
<li>Configuración del control de acceso de usuario</li>
<li>Configuración de Chrome</li>
<li>Datos de control de arranque</li>
<li>Configuración del Registro regedit y administrador de tareas</li>
<li>Windows Update, el servicio de transferencia inteligente en segundo plano y el servicio de llamadas de procedimiento remoto</li>
<li>Archivos del sistema operativo Windows</li></ul>
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
No es necesario realizar ninguna acción. Antivirus de Microsoft Defender eliminó o en cuarentena una amenaza. 
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.
Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
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
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:<ul>
<li>Bajo</li>
<li>Moderado</li>
<li>Alto</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:
<ul>
<li>Unknown</li>
<li>Equipo local</li>
<li>Recurso compartido de red</li>
<li>Internet</li>
<li>Tráfico entrante</li>
<li>Tráfico saliente</li>
</ul>
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:<ul>
<li>Heurística</li>
<li>Generic</li>
<li>Concreto</li>
<li>Firma dinámica</li>
</ul>
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:<ul>
<li>Usuario: usuario iniciado</li>
<li>Sistema: sistema iniciado</li>
<li>En tiempo real: componente en tiempo real iniciado</li>
<li>IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</li>
<li>NIS: sistema de inspección de red</li>
<li>IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</li>
<li>Antimalware de inicio anticipado (ELAM). Esto incluye malware detectado por la secuencia de arranque</li>
<li>Atestación remota</li>
</ul>Interfaz de examen antimalware (AMSI). Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.
Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:<ul>
<li>Clean: el recurso se ha limpiado</li>
<li>Cuarentena: el recurso se ha puesto en cuarentena</li>
<li>Quitar: se eliminó el recurso</li>
<li>Permitir: se permitió que el recurso se ejecutara o existiera</li>
<li>Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</li>
<li>Sin acción: sin acción</li>
<li>Bloquear: se bloqueó el recurso para que no se ejecutara</li>
</ul>
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente antivirus de Microsoft Defender encontró este error debido a problemas críticos. Es posible que el extremo no esté protegido. Revise la descripción del error y, a continuación, siga los <b>pasos de acción de usuario</b> pertinentes a continuación.
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
<li>Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</li>
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
El cliente antivirus de Microsoft Defender está en funcionamiento en buen estado.
<dl>
<dt>Versión actual de la plataforma: &lt; Ruta de &gt; acceso de</dt>recurso de amenaza de la
<dt> &lt; &gt; versión</dt>actual de la plataforma:
<dt>hashes de ruta: &lt; hashes &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging sin signo</b>.</div>
<div> </div>
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
El cliente antivirus de Microsoft Defender está en funcionamiento en buen estado.
<dl>
<dt>Versión de la plataforma: &lt; Versión de &gt; la plataforma actual</dt>Versión de firma: Versión del motor
<dt>de la &lt; &gt; </dt>
<dt> &lt; &gt; versión de definición: versión del motor antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente antivirus de Microsoft Defender está en buen estado. Este evento se notifica cada hora.
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
<b>Informe de estado del cliente de Endpoint Protection (hora UTC) </b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
Informe de estado del cliente antivirus.
<dl>
<dt>Versión de la plataforma: &lt; &gt;</dt>Versión actual de la plataforma Versión del motor: Versión del motor
<dt> &lt; &gt; antimalware</dt>Versión del motor de inspección en tiempo real
<dt>de red: &lt; &gt; </dt>Versión de firma del motor de inspección en tiempo real de red
<dt>Versión &lt; &gt; </dt>de firma antivirus Versión de firma
<dt> &lt; &gt; antispyware Versión</dt>de firma de inspección en tiempo
<dt>real: &lt; &gt; </dt>Estado rtp de la firma de inspección en tiempo real de red: Estado de protección en tiempo real (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Estado
<dt>de OA: Estado de IOAV en tiempo real (habilitado o &lt; &gt; deshabilitado):</dt>Estado de las descargas de IE y los datos adjuntos de Outlook Express (habilitados o deshabilitados): Estado de supervisión del comportamiento (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Antigüedad de firma del antivirus
<dt> &lt; &gt; (en días)</dt>Antigüedad de firma antispyware: Antigüedad de firma
<dt> &lt; antispyware &gt; (en días)</dt>Última antigüedad del examen rápido: Última antigüedad del examen rápido
<dt> &lt; &gt; (en días)</dt>Última antigüedad completa del examen( en
<dt> &lt; &gt; días)</dt>Tiempo de creación de firmas
<dt> &lt; &gt; </dt>
<dt>antivirus: ? &lt; Hora de &gt; creación de firmas antivirus</dt>Tiempo de
<dt>creación de firmas antispyware: ? &lt; Hora de creación &gt; de firmas antispyware</dt>
<dt>Última hora de inicio del examen rápido: ? &lt; Última hora de &gt; inicio del examen rápido</dt>Última hora de finalización del examen
<dt>rápido: ? &lt; Última &gt; hora</dt>de finalización del examen rápido Último origen de examen rápido: Último origen de examen rápido (0 = el examen no se&#39;se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Última hora de inicio del examen
<dt>completo: ? &lt; Última hora de &gt; inicio del examen completo</dt>Última hora de finalización del examen
<dt>completo: ? &lt; Última &gt; hora</dt>de finalización del examen completo Último origen de examen completo: Último origen de examen completo (0 = el examen no se&#39;no se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Estado del producto: Para la solución de problemas interna 
<dt>
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
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión de firma anterior: Versión de firma &lt; anterior &gt; </dt>Tipo de 
<dt> firma: Tipo de firma , por &lt; &gt; ejemplo: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>del motor actual del usuario: versión actual del &lt; &gt; motor</dt>Versión anterior del
<dt>motor: Versión anterior del &lt; motor &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente antivirus de Microsoft Defender está en buen estado. Este evento se notifica cuando las firmas se actualizan correctamente.
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
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número &gt; de versión</dt>
<dt>Versión de inteligencia de seguridad anterior: Versión &lt; &gt; anterior</dt>Update 
<dt> Source: Update source , por &lt; &gt; ejemplo:
<ul>
<li>Carpeta de actualización de inteligencia de seguridad</li>
<li>Servidor de actualización de inteligencia de seguridad interna</li>
<li>Microsoft Update Server</li>
<li>Compartir archivos</li>
<li>Centro de protección contra malware de Microsoft (MMPC)</li>
</ul>
</dt>
<dt>Update Stage: &lt; Update stage , por &gt; ejemplo:
<ul>
<li>Búsqueda</li>
<li>Descargar</li>
<li>Instalar</li>
</ul>
</dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre del servidor de 
<dt>Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo de firma: &lt; Tipo de firma , por &gt; ejemplo: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>actual del motor del usuario: &lt; &gt; Versión</dt>actual del motor Versión anterior del motor: Versión
<dt> &lt; anterior &gt; </dt>del motor Código de error: Código de error Código de
<dt>resultado asociado con el estado de la &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
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
Se ha actualizado la versión del motor de Antivirus de Microsoft Defender.
<dl>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt>
<dt>Versión anterior del motor: &lt; &gt; Versión anterior</dt>del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
No es necesario realizar ninguna acción. El cliente antivirus de Microsoft Defender está en buen estado. Este evento se notifica cuando el motor de antimalware se actualiza correctamente.
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
<dt>Nueva versión del motor:</dt>
<dt>Versión anterior del motor: &lt; &gt; </dt>Versión anterior del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Error en la actualización del cliente de Antivirus de Microsoft Defender. Este evento se produce cuando el cliente no se actualiza. Este evento suele deberse a una interrupción en la conectividad de red durante una actualización.
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
<dt>Firmas intentadas:</dt>
<dt>Código de error: Código de error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
El cliente de Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y falló. Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado. Antivirus de Microsoft Defender intentará volver a un conjunto de definiciones conocido.
Para solucionar este evento:
<ol>
<li>Reinicie el equipo e inténtelo de nuevo.</li>
<li>Descargue las definiciones más recientes del sitio <a href="https://aka.ms/wdsi">de Inteligencia de seguridad de Microsoft</a>.
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
Antivirus de Microsoft Defender no pudo cargar el motor de antimalware porque no se admite la versión actual de la plataforma. Antivirus de Microsoft Defender volverá al último motor conocido y se intenta actualizar la plataforma.
<dl>
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
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
<dt>Versión actual de la plataforma: &lt; Versión actual &gt; de la plataforma</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
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
Antivirus de Microsoft Defender necesitará pronto una versión de plataforma más reciente para admitir versiones futuras del motor de antimalware. Descargue la plataforma antivirus de Microsoft Defender más reciente para mantener el mejor nivel de protección disponible.
<dl>
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
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
El Antivirus de Microsoft Defender <i>usó el Servicio de firmas dinámicas</i> para recuperar firmas adicionales para ayudar a proteger el equipo.
<dl>
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:
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
El Antivirus de Microsoft Defender <i>usó el servicio de firmas dinámicas</i> para descartar firmas obsoletas.
<dl>
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:
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
No es necesario realizar ninguna acción. El cliente antivirus de Microsoft Defender está en buen estado. Este evento se notifica cuando el servicio de firma dinámica elimina correctamente definiciones dinámicas des actualizadas.
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
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Versión actual del motor: &lt; Versión del &gt; motor actual</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt> Tipo de firma dinámica: &lt; Tipo de firma dinámica , por &gt; ejemplo:
<ul>
<li>Versión</li>
<li>Timestamp</li>
<li>Sin límite</li>
<li>Duración</li>
</ul>
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:
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
El Antivirus de Microsoft Defender descartó todas <i>las firmas del servicio de firmas</i> dinámicas.
<dl>
<dt>Versión actual de la firma: &lt; versión actual de la firma&gt;</dt>
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
Antivirus de Microsoft Defender descargó un archivo limpio.
<dl>
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión actual &gt; del motor</dt>
<dt>de firma Actual: versión actual del &lt; motor &gt; </dt>
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
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión actual del motor: Versión actual &lt; del &gt; </dt>motor Código de error: Código de
<dt>error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Comprueba la configuración de conectividad a Internet.
El cliente de Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica. Es probable que este error se deba a un problema de conectividad de red. 
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
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
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
La compatibilidad con el sistema operativo ha expirado. Antivirus de Microsoft Defender ya no es compatible con el sistema operativo, ha dejado de funcionar y no protege contra amenazas de malware.
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
La característica de protección Real-Time Antivirus de Microsoft Defender ha encontrado un error y ha producido un error.
<dl>
<dt>Característica: &lt; Característica , por &gt; ejemplo:
<ul>
<li>En Access</li>
<li>Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> Motivo: el motivo por el que la protección en tiempo real de Antivirus de 
<dt>Microsoft Defender ha reiniciado una característica.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque&#39;es posible que el sistema no se protegió durante algún tiempo.
El cliente antivirus de Microsoft Defender&#39;la característica de protección en tiempo real encontró un error porque uno de los servicios no se pudo iniciar. Si le sigue un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error. 
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
Protección en tiempo real de Antivirus de Microsoft Defender ha reiniciado una característica. Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba abajo.
<dl>
<dt>Característica: &lt; Característica , por &gt; ejemplo:
<ul>
<li>En Access</li>
<li>Descargas de IE y datos adjuntos de Outlook Express</li>
<li>Supervisión del comportamiento</li>
<li>Sistema de inspección de red</li>
</ul>
</dt>
<dt>Motivo: el motivo por el que la protección en tiempo real de Antivirus de Microsoft Defender ha reiniciado una característica.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Acción del usuario:
</td>
<td >
Se ha reiniciado la característica de protección en tiempo real. Si este evento se produce de nuevo, póngase en contacto <a href="https://go.microsoft.com/fwlink/?LinkId=215491">con el Soporte técnico de Microsoft</a>. 
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
Se ha habilitado el examen de protección en tiempo real de Antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado.
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
Se deshabilitó el examen de protección en tiempo real de Antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado. 
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
La configuración de la característica de protección en tiempo real de Antivirus de Microsoft Defender ha cambiado.
<dl>
<dt>Característica: &lt; Característica , por &gt; ejemplo:
<ul>
<li>En Access</li>
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
<b>Se cambió la configuración de la plataforma antimalware.</b>
</td>
</tr>
<tr>
<td>
Descripción:
</td>
<td >
La configuración de Antivirus de Microsoft Defender ha cambiado. Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.
<dl>
<dt>Valor antiguo: &lt; Número de valor antiguo &gt; Valor de configuración del antivirus anterior.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de valor &gt; Nuevo valor de configuración antivirus.</dt>
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
El motor antivirus de Microsoft Defender ha finalizado debido a un error inesperado.
<dl>
<dt>Tipo de error: &lt; Tipo de &gt; error , por ejemplo: Bloquear o bloquear código</dt>de
<dt>excepción: &lt; Código de &gt; error</dt>
<dt>Recurso: &lt; recurso &gt; </dt>
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
<li>Para antimalware, antivirus y spyware, en un símbolo del sistema con privilegios elevados, escriba <b>net stop msmpsvc</b>y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor de antimalware.</li>
<li>Para el sistema <i>de</i>inspección de red , en un símbolo del sistema con privilegios elevados, escriba <b>net start nissrv</b>y, a continuación, escriba <b>net start nissrv</b> para reiniciar el motor del sistema de inspección de red mediante el archivo NiSSRV.exe. <i></i>
</li>
</ul>
</li>
<li>Si se produce un error de la misma manera, busque el código de <b></b> error accediendo al Sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> y especificando el número de error en el cuadro Búsqueda y póngase en contacto con el Soporte técnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">de Microsoft</a>.</li>
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
<li>Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</li>
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
Se ha habilitado el examen del antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado.
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
El examen del antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado está deshabilitado.
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
Se ha habilitado el examen antivirus de Microsoft Defender en busca de virus. 
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
El examen del Antivirus de Microsoft Defender en busca de virus está deshabilitado. 
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
<dt>Motivo de expiración: el motivo por el que el Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la fecha en que expirará Antivirus de Microsoft Defender.</dt>
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
El período de gracia de Antivirus de Microsoft Defender ha expirado. La protección contra virus, spyware y otro software potencialmente no deseado está deshabilitada.
<dl>
<dt>Motivo de expiración:</dt>
<dt>Fecha de expiración: </dt>Código de error: Código de error Código de resultado asociado con el estado de la 
<dt> &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
## Códigos de error de cliente de Antivirus de Microsoft Defender Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le dará un código de error para ayudarle a solucionar el problema. En la mayoría de los casos, un error significa que hubo un problema al instalar una actualización.
En esta sección se proporciona la siguiente información acerca de los errores de cliente de Antivirus de Microsoft Defender.
-   El código de error -   El posible motivo del error Consejo sobre qué hacer -   ahora

Use la información de estas tablas para solucionar problemas de códigos de error de Antivirus de Microsoft Defender.


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
<li>Haga clic en <b>el botón Actualizar definiciones</b> de la <b>pestaña</b> Actualizar del Antivirus de Microsoft Defender. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>O bien
</li>
<li>Descargue las definiciones más recientes del sitio <a href="https://aka.ms/wdsi">de Inteligencia de seguridad de Microsoft</a>.
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
Este error indica que antivirus de Microsoft Defender no pudo poner en cuarentena una amenaza. 
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
Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Escáner de seguridad de Microsoft</a> y, a continuación, actualice el software de seguridad e inténtelo de nuevo. 
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
Siga los pasos de corrección manuales descritos en la Enciclopedia de Protección contra malware <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">de Microsoft</a>. Puede encontrar un vínculo específico de la amenaza en el historial de eventos.<br/></td>
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
Ejecute el Antivirus de Microsoft Defender sin conexión. Puede leer sobre cómo hacerlo en el artículo de <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Antivirus de Microsoft Defender sin conexión.</a>
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
Solo puedes usar Antivirus de Microsoft Defender en Windows 10. Para Windows 8, Windows 7 y Windows Vista, puedes usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a> Los siguientes códigos de error se usan durante las pruebas internas del Antivirus de Microsoft Defender.

Si ve estos errores, puede [](manage-updates-baselines-microsoft-defender-antivirus.md) intentar actualizar definiciones y forzar un nuevo análisis directamente en el punto de conexión.


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

- [Informe sobre la protección antivirus de Microsoft Defender](report-monitor-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)