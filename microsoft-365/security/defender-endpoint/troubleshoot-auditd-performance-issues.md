---
title: Solución de problemas de rendimiento de AuditD con Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo solucionar problemas de rendimiento relacionados con AuditD que podría encontrar con Microsoft Defender para Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, troubleshooting, AuditD, XMDEClientAnalyzer, installation, deploy, uninstallation
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 31aaf297fd3622eede2e1532ad60a20666d1bd07
ms.sourcegitcommit: 49c275f78664740988bbc4ca4b14d3ad758e1468
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2022
ms.locfileid: "66882891"
---
# <a name="troubleshoot-auditd-performance-issues-with-microsoft-defender-for-endpoint-on-linux"></a>Solución de problemas de rendimiento de AuditD con Microsoft Defender para punto de conexión en Linux 

En este artículo se proporcionan instrucciones sobre cómo solucionar problemas de rendimiento relacionados con AuditD que puede encontrar con Microsoft Defender para punto de conexión en Linux. 

**Fondo:** 

- Microsoft Defender para punto de conexión en distribuciones del sistema operativo Linux usa el marco AuditD para recopilar determinados tipos de eventos de telemetría. 

- Los eventos del sistema capturados por las reglas agregadas a `/etc/audit/rules.d/` se agregarán a audit.log(s) y podrían afectar a la auditoría del host y a la recopilación ascendente.  

- Los eventos agregados por Microsoft Defender para punto de conexión en Linux se etiquetarán con `mdatp` clave. 

- Si el servicio AuditD está mal configurado o sin conexión, es posible que falten algunos eventos. Para solucionar este problema, consulte: [Solución de problemas de eventos o alertas que faltan para Microsoft Defender para punto de conexión en Linux.](linux-support-events.md)

En determinadas cargas de trabajo de servidor, se pueden observar dos problemas: 

- **Consumo elevado** de recursos de CPU de **_mdatp_audisp_plugin_** proceso. 

- ***/var/log/audit/audit.log*** se convierte en grande o gira con frecuencia. 

Estos problemas pueden producirse en servidores con muchos eventos que inundan AuditD.  

Esto puede ocurrir si hay varios consumidores para AuditD, o demasiadas reglas con la combinación de Microsoft Defender para punto de conexión y consumidores de terceros, o una carga de trabajo alta que genera una gran cantidad de eventos. 

Para solucionar estos problemas, empiece por [recopilar registros de MDEClientAnalyzer](run-analyzer-macos-linux.md) en el servidor afectado de ejemplo. 

> [!NOTE]
> Como procedimiento recomendado general, se recomienda actualizar el [agente de Microsoft Defender para punto de conexión a la versión más reciente disponible](linux-whatsnew.md) y confirmar que el problema persiste antes de investigar más.


## <a name="xmdeclientanalyzer"></a>XMDEClientAnalyzer 

Cuando se usa XMDEClientAnalyzer, los siguientes archivos mostrarán la salida que proporciona información para ayudarle a solucionar problemas.
- auditd_info.txt
- auditd_log_analysis.txt


### <a name="auditd_infotxt"></a>auditd_info.txt

Contiene la configuración general de AuditD y mostrará:

- Qué procesos se registran como consumidores auditados. 

- **Auditctl -s** output with **enabled=2**  

    - Sugiere que auditada está en modo inmutable (requiere reiniciar para que los cambios de configuración surtan efecto). 

- **Auditctl -l** output  

    - Mostrará qué reglas se cargan actualmente en el kernel (que pueden ser diferentes de lo que existe en el disco en "/etc/auditd/rules.d/mdatp.rules"). 
    
    - Mostrará qué reglas están relacionadas con Microsoft Defender para punto de conexión. 
    
### <a name="auditd_log_analysistxt"></a>auditd_log_analysis.txt

Contiene información agregada importante que resulta útil al investigar problemas de rendimiento de AuditD.  

- Qué componente posee los eventos más notificados (Microsoft Defender para punto de conexión eventos se etiquetarán con `key=mdatp`). 

- Los principales iniciadores de informes. 

- Las llamadas del sistema más comunes (eventos de red o sistema de archivos, entre otros). 

- Qué rutas de acceso del sistema de archivos son las más ruidosas. 

**Para mitigar la mayoría de los problemas de rendimiento de AuditD, puede implementar la exclusión de AuditD. **

> [!NOTE]
> Las exclusiones solo se deben realizar para los iniciadores o rutas de acceso de baja amenaza y alto ruido. Por ejemplo, no excluya /bin/bash, que corre el riesgo de crear un punto ciego grande.
> [Errores comunes que se deben evitar al definir exclusiones](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus).



## <a name="exclusion-types"></a>Tipos de exclusión 

La herramienta de compatibilidad XMDEClientAnalyzer contiene la sintaxis que se puede usar para agregar reglas de configuración de exclusión AuditD: 

Exclusión de AuditD: ayuda de sintaxis de la herramienta de soporte técnico:

:::image type="content" source="images/auditd-exclusion-support-tool-syntax-help.png" alt-text="sintaxis que se puede usar para agregar reglas de configuración de exclusión auditada" lightbox="images/auditd-exclusion-support-tool-syntax-help.png":::

**Por iniciador** 

- **-e/ -exe** full binary path > Quita todos los eventos de este iniciador 

**Por ruta de acceso** 

- **-d/ -dir** ruta de acceso completa a un directorio > Quita los eventos del sistema de archivos destinados a este directorio. 

Ejemplos: 

Si "`/opt/app/bin/app`" escribe en "`/opt/app/cfg/logs/1234.log`", puede usar la herramienta de soporte técnico para excluir con varias opciones: 

`-e /opt/app/bin/app`

`-d /opt/app/cfg`

`-x /usr/bin/python /etc/usercfg` 

`-d /usr/app/bin/`

Más ejemplos: 

`./mde_support_tool.sh exclude -p <process id>`

`./mde_support_tool.sh exclude -e <process name>`

Para excluir más de un elemento, concatene las exclusiones en una línea: 

`./mde_support_tool.sh exclude -e <process name> -e <process name 2> -e <process name3>`
 
La marca -x se usa para excluir el acceso a subdirectorios por parte de iniciadores específicos, por ejemplo: 

`./mde_support_tool.sh exclude -x /usr/sbin/mv /tmp`

Lo anterior excluirá la supervisión de la subcarpeta /tmp, cuando el proceso mv acceda a ella. 

 
> [!NOTE]
> Póngase en contacto con el soporte técnico de Microsoft si necesita ayuda para analizar y mitigar problemas de rendimiento relacionados con AuditD, o con la implementación de exclusiones auditadas a escala. 


