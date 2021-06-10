---
title: Habilitar y configurar las Antivirus de Microsoft Defender de protección
description: Habilitar y configurar Antivirus de Microsoft Defender de protección en tiempo real, como la supervisión del comportamiento, la heurística y el aprendizaje automático
keywords: antivirus, protección en tiempo real, rtp, aprendizaje automático, supervisión del comportamiento, heurística
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1e39e42b79a2a767473c4473434da249a0d07228
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275137"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Habilitar y configurar la protección siempre activa del Antivirus de Windows Defender en la directiva de grupo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

La protección siempre activa consiste en la protección en tiempo real, la supervisión del comportamiento y la heurística para identificar malware basado en actividades sospechosas y malintencionadas conocidas.

Estas actividades incluyen eventos, como procesos que hacen cambios inusuales en los archivos existentes, modificar o crear claves de registro de inicio automático y ubicaciones de inicio (también conocidas como puntos de extensibilidad de inicio automático o ASEP) y otros cambios en el sistema de archivos o la estructura de archivos.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Habilitar y configurar la protección siempre activa en la directiva de grupo

Puede usar el **Editor de directivas de** grupo local para habilitar y configurar Antivirus de Microsoft Defender de protección siempre activa.

Para habilitar y configurar la protección siempre activa:

1. Abra **el Editor de directivas de grupo local**. Para ello:  

    1. En el Windows 10 de búsqueda de la barra de tareas, escriba **gpedit**.
    
    1. En **Coincidencia recomendada,** haga clic **en Editar directiva de grupo** para iniciar el Editor de directivas de grupo **local.**
    
       ![Resultado de búsqueda de la barra de tareas de GPEdit](images/gpedit-search.png)

2. En el panel izquierdo del Editor de directivas de grupo **local,** expanda el árbol a Configuración del equipo Plantillas administrativas  >    >  **Windows componentes**  >  **Antivirus de Microsoft Defender**. 

3. Configure la configuración Antivirus de Microsoft Defender directiva de servicio antimalware. Para ello:  

    1. En el **Antivirus de Microsoft Defender** detalles de la derecha, haga doble clic en la configuración de directiva especificada en la tabla siguiente:

       | Configuración | Descripción | Configuración predeterminada |
       |-----------------------------|------------------------|-------------------------------|
       | Permitir el inicio del servicio antimalware con prioridad normal | Puede reducir la prioridad del motor de Antivirus de Microsoft Defender, que puede ser útil en implementaciones ligeras donde desea tener un proceso de inicio lo más delgado posible. Esto puede afectar a la protección en el extremo. | Habilitado
       | Permitir que el servicio antimalware siga ejecutándose siempre | Si las actualizaciones de protección se han deshabilitado, puede Antivirus de Microsoft Defender para que se ejecuten. Esto reduce la protección en el extremo. | Deshabilitado |
    
    1. Configure la configuración según corresponda y haga clic en **Aceptar**.
    
    1. Repita los pasos anteriores para cada configuración de la tabla.

4. Configure la Antivirus de Microsoft Defender de protección en tiempo real. Para ello:

    1. En el **panel Antivirus de Microsoft Defender** detalles, haga doble clic en Protección en **tiempo real**. O bien, en el **Antivirus de Microsoft Defender** en el panel izquierdo, haga clic **en Protección en tiempo real**.
    
    1. En el **panel de detalles protección** en tiempo real de la derecha, haga doble clic en la configuración de directiva especificada en la tabla siguiente:  

       | Configuración | Descripción | Configuración predeterminada |
       |-----------------------------|------------------------|-------------------------------|
       | Activar la supervisión del comportamiento | El motor de ANTIVIRUS supervisará los procesos de archivos, los cambios de archivos y del Registro, y otros eventos en los puntos de conexión en busca de actividad malintencionada sospechosa y conocida. | Habilitado |
       | Examinar todos los archivos y datos adjuntos descargados | Los archivos descargados y los datos adjuntos se examinan automáticamente. Esto funciona además del filtro Windows Defender SmartScreen, que examina los archivos antes y durante la descarga. | Habilitado |
       | Supervisar la actividad de archivos y programas en el equipo | El motor de Antivirus de Microsoft Defender toma nota de los cambios de archivos (escrituras de archivos, como movimientos, copias o modificaciones) y la actividad general del programa (programas que se abren o ejecutan y que hacen que se ejecuten otros programas). | Habilitado |
       | Activar las notificaciones de escritura por volumen sin procesar | La supervisión del comportamiento analizará la información sobre las escrituras de volumen sin procesar. | Habilitado |
       | Activar el examen de procesos siempre que esté habilitada la protección en tiempo real | Puede habilitar el motor de Antivirus de Microsoft Defender de forma independiente para examinar los procesos en ejecución en busca de modificaciones o comportamientos sospechosos. Esto resulta útil si ha deshabilitado temporalmente la protección en tiempo real y desea examinar automáticamente los procesos que se iniciaron mientras estaba deshabilitado. | Habilitado |
       | Definir el tamaño máximo de los archivos y datos adjuntos descargados que se examinarán | Puede definir el tamaño en kilobytes. | Habilitado |
       | Configurar la invalidación de configuración local para activar la supervisión del comportamiento | Configure una invalidación local para la configuración de la supervisión del comportamiento. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.| Habilitado |
       | Configurar la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados | Configure una invalidación local para la configuración del examen de todos los archivos y datos adjuntos descargados. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.| Habilitado |
       | Configurar la invalidación de configuración local para la actividad del programa y el archivo de supervisión en el equipo | Configure una invalidación local para la configuración de la supervisión de la actividad de archivos y programas en el equipo. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.| Habilitado |
       | Configurar la invalidación de configuración local para activar la protección en tiempo real | Configure una invalidación local para que la configuración active la protección en tiempo real. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.| Habilitado |
       | Configurar la invalidación de configuración local para la supervisión de la actividad de archivos entrantes y salientes | Configure una invalidación local para la configuración de la supervisión de la actividad de archivos entrantes y salientes. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local. | Habilitado |
       | Configurar la supervisión para la actividad del programa y los archivos entrantes y salientes | Especifique si la supervisión debe producirse en la dirección entrante, saliente, ambas o ninguna. Esto es relevante para las instalaciones de Windows Server en las que ha definido servidores específicos o roles de servidor que ven grandes cantidades de cambios de archivo en una sola dirección y desea mejorar el rendimiento de la red. Los puntos de conexión (y los servidores) totalmente actualizados en una red verán poco impacto en el rendimiento independientemente del número o la dirección de los cambios en los archivos. | Habilitado (ambas direcciones) |

    1. Configure la configuración según corresponda y haga clic en **Aceptar**.
    
    1. Repita los pasos anteriores para cada configuración de la tabla.

5. Configure la configuración de Antivirus de Microsoft Defender de análisis. Para ello:  

    1. En el **Antivirus de Microsoft Defender** en el panel izquierdo, haga clic en **Examinar**.
    
       ![Antivirus de Microsoft Defender Opciones de examen](images/gpedit-windows-defender-antivirus-scan.png)

    1. En el **panel Detección** de detalles de la derecha, haga doble clic en la configuración de directiva especificada en la tabla siguiente:

       | Configuración | Descripción | Configuración predeterminada |
       |-----------------------------|------------------------|-------------------------------|    
       | Activar heurística | La protección heurística deshabilitará o bloqueará la actividad sospechosa inmediatamente antes de que se pida al Antivirus de Microsoft Defender que detecte la actividad. | Habilitado |

    1. Configure la configuración según corresponda y haga clic en **Aceptar**.
    
6. Cierre **el Editor de directivas de grupo local**.


## <a name="disable-real-time-protection-in-group-policy"></a>Deshabilitar la protección en tiempo real en la directiva de grupo

> [!WARNING]
> Deshabilitar la protección en tiempo real reduce drásticamente la protección en los puntos de conexión y no se recomienda.

La principal funcionalidad de protección en tiempo real está habilitada de forma predeterminada, pero puede deshabilitarla mediante el Editor de directivas **de grupo local**.

Para deshabilitar la protección en tiempo real en la directiva de grupo:

1. Abra **el Editor de directivas de grupo local**.

   1. En el Windows 10 de búsqueda de la barra de tareas, escriba **gpedit**.
   
   1. En **Coincidencia recomendada,** haga clic **en Editar directiva de grupo** para iniciar el Editor de directivas de grupo **local.**

2.  En el panel izquierdo del Editor de directivas de grupo **local,** expanda el árbol a Configuración del equipo Plantillas administrativas Windows componentes Antivirus de Microsoft Defender  >    >    >    >  **protección en tiempo real**.

3. En el **panel detalles de protección** en tiempo real a la derecha, haga doble clic en Desactivar la protección en tiempo **real.**

   ![Desactivar la protección en tiempo real](images/gpedit-turn-off-real-time-protection.png)

4. En la ventana Desactivar la configuración de protección en tiempo **real,** establezca la opción en **Habilitado**.

   ![Desactivar la protección en tiempo real habilitada](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Haga clic en **Aceptar**.

6. Cierre **el Editor de directivas de grupo local**.

## <a name="related-articles"></a>Artículos relacionados

- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)