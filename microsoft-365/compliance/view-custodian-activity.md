---
title: Ver actividad de auditoría de custodios
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 46dffe5c388f247604bc67dc24916206452745da
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597267"
---
# <a name="view-custodian-audit-activity"></a>Ver actividad de auditoría de custodios

¿Necesita averiguar si un usuario ha visto un documento determinado o si ha purgado un elemento de su buzón? EDiscovery avanzado ya está integrado con la herramienta de búsqueda de registros de auditoría existente en el centro de seguridad & cumplimiento. Con esta experiencia insertada, puede usar la herramienta de administración de custodios de eDiscovery avanzada para facilitar su investigación al acceder fácilmente y buscar en la actividad para los custodios en su caso.

## <a name="before-you-begin"></a>Antes de empezar

Usted debe tener asignado el rol de Registros de auditoría o Registros de auditoría de solo lectura en Exchange en línea para buscar el registro de auditoría de Office 365. De forma predeterminada, estos roles se asignan a los grupos de roles de Administración de la organización y Administración de cumplimiento en la página depermisosdel centro de administración de Exchange. Para dar a un usuario la capacidad de buscar el registro de auditoría de eDiscovery avanzado con el nivel mínimo de privilegios, puede crear un grupo de roles personalizado en Exchange Online, agregar el rol registros de auditoría con permiso de vista o registros de auditoría y, a continuación, agregar el usuario como miembro del nuevo grupo de roles. Para obtener más información, consulteAdministrar grupos de roles en Exchange en línea.

> [!IMPORTANT]
> Si asigna a un usuario el rol registros de auditoría con permiso de vista o registros de auditoría en la página permisos del centro de seguridad & cumplimiento, no podrán buscar en el registro de auditoría de Office 365. Tiene que asignar los permisos en Exchange en línea. Esto se debe a que el cmdlet subyacente que se usa para buscar en el registro de auditoría es un cmdlet Exchange en línea.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Paso 1: buscar en el registro de auditoría las actividades realizadas por un custodio

1. Vaya a **ediscovery > eDiscovery avanzado** y abra el caso.
  
2. Haga clic en la ficha **custodios** .
  
3. Seleccione un custodio de la lista y, a continuación, haga clic en **ver actividad de custodios** en la página de control flotante.

    Se muestra la página de búsqueda de actividades de custodio. Nota el custodio que seleccionó en el paso anterior se muestra en el cuadro desplegable **custodio** . Puede seleccionar custodios diferentes en el cuadro desplegable, pero solo puede buscar actividades para un custodio a la vez.

    ![Página de búsqueda de actividades de custodio](media/AeDCustodianActivities1.png)
   
4. Configurar los siguientes criterios de búsqueda: 
      
   a. **Actividades** : haga clic en la lista desplegable para mostrar las actividades que puede buscar. Después de ejecutar la búsqueda, solo se muestran los registros de auditoría de las actividades seleccionadas. Al seleccionar **Mostrar resultados para todas las actividades** , se mostrarán los resultados de todas las actividades realizadas por el custodio que coinciden con los demás criterios de búsqueda.

      ![Lista de actividades](media/CustodianActivityAudit.PNG)
      
      b. Fecha de **Inicio y fecha de finalización** : Seleccione un intervalo de fechas y horas para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días están seleccionados de forma predeterminada. La fecha y la hora se presentan en formato de Hora universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es un año.
      
      c. **Custodios** : haga clic en este cuadro y seleccione un custodio específico para mostrar los resultados de la búsqueda. Los registros de auditoría para la actividad seleccionada realizada por los usuarios que seleccione en este cuadro se muestran en la lista de resultados.
      
   5. Haga clic en   ![Botón buscar](media/SearchButton.PNG)  para ejecutar la búsqueda con los criterios de búsqueda. Los resultados de la búsqueda se cargan y, después de unos segundos, se muestran en resultados en la página de búsqueda de actividades de custodio. 

## <a name="step-2-view-the-audit-log-search-results"></a>Paso 2: ver los resultados de la búsqueda de registros de auditoría

Los resultados de una búsqueda de registro de auditoría se muestran en resultados en la página de registro de auditoría de custodio. Un máximo de 5.000 (más reciente) se muestran en incrementos de 150 eventos. Para mostrar más eventos puede usar la barra de desplazamiento en el panel Resultados o también puede presionar Mayús+Fin para mostrar los siguientes 150 eventos.

Los resultados contienen la siguiente información sobre cada evento devuelto por la búsqueda.
- **Fecha**: la fecha y la hora (en formato UTC) cuando se ha realizado el evento.

- **Dirección IP**: la dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.

- **Usuario**: el usuario (o cuenta de servicio) que ha realizado la acción que ha desencadenado el evento.

- **Actividad**: la actividad que ha realizado el usuario. Este valor corresponde a las actividades que ha seleccionado en la lista desplegable de Actividades. Para un evento del registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange.

- **Elemento**: el objeto que se ha creado o modificado como resultado de la actividad correspondiente. Por ejemplo, el archivo que se ha visto o modificado, o la cuenta de usuario que se ha actualizado. No todas las actividades tienen un valor en esta columna.

- **Detalles**: detalles adicionales sobre una actividad. De nuevo, no todas las actividades tendrán un valor.

## <a name="step-3-filter-the-search-results"></a>Paso 3: Filtrar los resultados de la búsqueda

Además de ordenar, también puede filtrar los resultados de una búsqueda de registro de auditoría. Esto puede ayudarle a filtrar rápidamente los resultados de un usuario o actividad específicos. 

Para filtrar los resultados:

 1. Cree y ejecute una búsqueda de registros de auditoría.
  
2. Cuando se muestren los resultados, haga clic en **Filtrar resultados**.
 
3. Los cuadros de palabra clave se muestran en cada encabezado de columna.
  
4. Haga clic en uno de lo cuadros que se visualizan en las cabeceras de columna y escriba una palabra o frase, dependiendo de la columna que esté filtrando. Los resultados se volverán a ajustar de manera dinámica para mostrar los eventos que coincidan con su filtro.
  
5. Para borrar un filtro, haga clic en la **X** en el cuadro filtro o simplemente haga clic en **ocultar filtrado**.

## <a name="export-the-search-results-to-a-file"></a>Exportar los resultados de la búsqueda a un archivo

Puede exportar los resultados de una búsqueda de registro de auditoría a un archivo de valores separados por comas (CSV) en el equipo local. Puede abrir este archivo en Microsoft Excel y usar características como buscar, ordenar, filtrar y dividir una sola columna (que contiene celdas de varios valores) en varias columnas.

1. Ejecute una búsqueda de registro de auditoría, y luego revise los criterios de búsqueda hasta que tenga los resultados deseados.
  
2. Haga clic en Exportar resultados y seleccione una de las siguientes opciones:

    - **Guardar los resultados cargados:** Elija esta opción para exportar solo las entradas que se muestran en **resultados** en la página de **búsqueda de registro de auditoría de custodios** . El archivo CSV que se descarga contiene las mismas columnas (y datos) que se muestran en la página (Fecha, Usuario, Actividad, Elemento y Detalles). Una columna adicional (que se titula **más**) se incluye en el archivo CSV que contiene más información de la entrada del registro de auditoría. Como está exportando los mismos resultados que se han cargado (y visualizado) en la página Búsqueda de registros de auditoría, se exportan un máximo de 5 000 entradas.
        
    - **Descargar todos los resultados:** Elija esta opción para exportar todas las entradas del registro de auditoría de Office 365 que cumplan los criterios de búsqueda. Para un conjunto grande de resultados de búsqueda, elija esta opción para descargar todas las entradas del registro de auditoría, además de los resultados de 5.000 que se pueden mostrar en la página de búsqueda del **registro de auditoría de custodio** . Con esta opción se descargan los datos sin procesar del registro de auditoría en un archivo CSV y se incluye información adicional de la entrada del registro de auditoría en una columna denominada AuditData. Puede tardar más en descargar el archivo si elige esta opción de exportación ya que el archivo puede ser mucho más grande que el que se descarga si eligiera otra opción.
    
      > [!IMPORTANT]
      > Puede descargar un máximo de 50 000 entradas en un archivo CSV desde una única búsqueda de registros de auditoría. Si se descargan 50 000 entradas en el archivo CSV, probablemente puede suponer que existen más de 50 000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, pruebe a usar un intervalo de fecha para reducir el número de entradas de registro de auditoría. Puede que tenga que ejecutar varias búsquedas con intervalos de fecha de menor tamaño para exportar más de 50 000 entradas.
        

3. Después de seleccionar una opción de exportación, se muestra un mensaje en la parte inferior de la ventana donde se le pide que abra el archivo CSV, que lo guarde en la carpeta downloads o lo guarde en una carpeta específica

Para obtener más información acerca de cómo ver, filtrar o exportar los resultados de la búsqueda de registros de auditoría, vea [Buscar en el registro de auditoría del centro de seguridad & cumplimiento](search-the-audit-log-in-security-and-compliance.md).
