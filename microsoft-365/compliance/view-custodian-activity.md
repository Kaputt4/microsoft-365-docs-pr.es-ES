---
title: Ver la actividad de auditoría de custodio
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use la herramienta administración de custodios de eDiscovery (Premium) para acceder fácilmente a la actividad y buscar en ella a los custodios dentro de su caso.
ms.custom:
- seo-marvel-mar2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 35b622e00caeeca78c85849f03b3a21f8a28b443
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64943521"
---
# <a name="view-custodian-audit-activity"></a>Ver la actividad de auditoría de custodio

¿Necesita averiguar si un usuario ha visto un documento determinado o si ha purgado un elemento de su buzón? Microsoft Purview eDiscovery (Premium) ahora se integra con la herramienta de búsqueda de registros de auditoría existente en el portal de cumplimiento de Microsoft Purview. Con esta experiencia insertada, puede usar la herramienta de administración de custodias de eDiscovery (Premium) para facilitar la investigación mediante el acceso y la búsqueda de la actividad en busca de custodios dentro de su caso.

## <a name="get-permissions"></a>Obtener permisos

Usted debe tener asignado el rol de Registros de auditoría o Registros de auditoría de solo lectura en Exchange Online para buscar en el registro de auditoría. De forma predeterminada, estos roles se asignan a los grupos de roles Administración de cumplimiento normativo y Administración de la organización en la página Permisos del <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>. Para proporcionar a un usuario la capacidad de buscar en el registro de auditoría de eDiscovery (Premium) con el nivel mínimo de privilegios, puede crear un grupo de roles personalizado en Exchange Online, agregar el rol registros de auditoría o registros de auditoría de View-Only y, a continuación, agregar el usuario como miembro del nuevo grupo de roles. Para obtener más información, consulteAdministrar grupos de roles en Exchange en línea.

> [!IMPORTANT]
> Si asigna a un usuario el rol Registros de auditoría View-Only o Registros de auditoría en la página Permisos del portal de cumplimiento, no podrá buscar en el registro de auditoría. Tiene que asignar los permisos en Exchange en línea. Esto se debe a que el cmdlet subyacente que se usa para buscar en el registro de auditoría es un cmdlet Exchange en línea.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Paso 1: Buscar en el registro de auditoría las actividades realizadas por un custodio

1. Vaya a **eDiscovery > eDiscovery (Premium)** y abra el caso.
  
2. Haga clic en la pestaña **Orígenes** .
  
3. En la página **Custodios** , seleccione un custodio de la lista y, a continuación, haga clic en **Ver actividad de custodio** en la página desplegable.

    Se muestra la página de búsqueda Actividades de custodio. Tenga en cuenta que el custodio que seleccionó en el paso anterior se muestra en el cuadro desplegable **Custodio** . Puede seleccionar diferentes custodios en el cuadro desplegable, pero solo puede buscar actividades para un custodio a la vez.

    ![Página de búsqueda de actividades de custodio.](../media/AeDCustodianActivities1.png)
   
4. Configurar los siguientes criterios de búsqueda: 
      
   1. **Actividades** : haga clic en la lista desplegable para mostrar las actividades que puede buscar. Después de que ejecute la búsqueda, solo se muestran las entradas seleccionadas del registro de auditoría de las actividades. Al seleccionar **Mostrar resultados para todas las actividades** , se mostrarán los resultados de todas las actividades realizadas por el custodio que coincidan con los demás criterios de búsqueda.

      ![Lista de actividades.](../media/CustodianActivityAudit.PNG)
      
   1. **Fecha de inicio y fecha de finalización** : seleccione un intervalo de fecha y hora para mostrar los eventos que se produjeron dentro de ese período. Los últimos siete días se seleccionan de forma predeterminada. La fecha y la hora se presentan en formato de Hora universal coordinada (UTC). El intervalo de fechas máximo que puede especificar es de un año.
      
   1. **Custodios** : haga clic en este cuadro y, a continuación, seleccione un custodio específico para mostrar los resultados de la búsqueda. Los registros de auditoría de la actividad seleccionada realizada por los usuarios seleccionados en este cuadro se muestran en la lista de resultados.
      
5. Haga clic en ![Botón Buscar.](../media/SearchButton.PNG)  para ejecutar la búsqueda con los criterios de búsqueda. Los resultados de la búsqueda se cargan y, después de unos instantes, se muestran en Resultados en la página de búsqueda Actividades de custodio. 

## <a name="step-2-view-the-audit-log-search-results"></a>Paso 2: Ver los resultados de la búsqueda de registros de auditoría

Los resultados de una búsqueda de registros de auditoría se muestran en Resultados en la página Registro de auditoría del custodio. Un máximo de 5000 eventos (más recientes) se muestran en incrementos de 150 eventos. Para mostrar más eventos puede usar la barra de desplazamiento en el panel Resultados o también puede presionar Mayús+Fin para mostrar los siguientes 150 eventos.

Los resultados contienen la siguiente información sobre cada evento que la búsqueda ha devuelto.
- **Fecha**: la fecha y la hora (en formato UTC) cuando se ha realizado el evento.

- **Dirección IP**: la dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.

- **Usuario**: el usuario (o cuenta de servicio) que ha realizado la acción que ha desencadenado el evento.

- **Actividad**: la actividad que ha realizado el usuario. Este valor corresponde a las actividades que ha seleccionado en la lista desplegable de actividades. Para un evento del registro de auditoría de administración de Exchange, el valor de esta columna es un cmdlet de Exchange.

- **Elemento**: el objeto que se ha creado o modificado como resultado de la actividad correspondiente. Por ejemplo, el archivo que se ha visto o modificado, o la cuenta de usuario que se ha actualizado. No todas las actividades tienen un valor en esta columna.

- **Detalle**: detalles adicionales sobre una actividad. De nuevo, no todas las actividades tendrán un valor.

## <a name="step-3-filter-the-search-results"></a>Paso 3: Filtrar los resultados de la búsqueda

Además de ordenar, también puede filtrar los resultados de una búsqueda de registro de auditoría. Esto puede ayudarle a filtrar rápidamente los resultados de un usuario o actividad específico. 

Para filtrar los resultados:

 1. Cree y ejecute una búsqueda de registros de auditoría.
  
2. Cuando se muestren los resultados, haga clic en **Filtrar resultados**.
 
3. Los cuadros de palabra clave se muestran en cada encabezado de columna.
  
4. Haga clic en uno de lo cuadros que se visualizan en las cabeceras de columna y escriba una palabra o frase, dependiendo de la columna que esté filtrando. Los resultados se volverán a ajustar de manera dinámica para mostrar los eventos que coincidan con su filtro.
  
5. Para borrar un filtro, haga clic en la **X** en el cuadro de filtro o simplemente haga clic en **Ocultar filtrado**.

## <a name="export-the-search-results-to-a-file"></a>Exportación de los resultados de la búsqueda a un archivo

Puede exportar los resultados de una búsqueda de registros de auditoría a un archivo de valores separados por comas (CSV) en el equipo local. Puede abrir este archivo en Microsoft Excel y usar características como búsqueda, ordenación, filtrado y división de una sola columna (que contiene celdas de varios valores) en varias columnas.

1. Ejecute una búsqueda de registro de auditoría, y luego revise los criterios de búsqueda hasta que tenga los resultados deseados.
  
2. Haga clic en Exportar resultados y seleccione una de las siguientes opciones:

    - **Guardar los resultados cargados:** Elija esta opción para exportar solo las entradas que se muestran en **Resultados** en la página **de búsqueda del registro de auditoría del custodio** . El archivo CSV que se descarga contiene las mismas columnas (y datos) que se muestran en la página (Fecha, Usuario, Actividad, Elemento y Detalles). Se incluye una columna adicional (titulada **Más**) en el archivo CSV que contiene más información de la entrada de registro de auditoría. Como está exportando los mismos resultados que se han cargado (y visualizado) en la página Búsqueda de registros de auditoría, se exportan un máximo de 5 000 entradas.
        
    - **Descargue todos los resultados:** Elija esta opción para exportar todas las entradas del registro de auditoría que cumplan los criterios de búsqueda. Para obtener un gran conjunto de resultados de búsqueda, elija esta opción para descargar todas las entradas del registro de auditoría, además de los 5000 resultados que se pueden mostrar en la página de búsqueda del **registro de auditoría del custodio** . Esta opción descargará los datos sin procesar del registro de auditoría en un archivo CSV y contiene información adicional de la entrada de registro de auditoría en una columna denominada AuditData. Puede tardar más en descargar el archivo si elige esta opción de exportación ya que el archivo puede ser mucho más grande que el que se descarga si eligiera otra opción.
    
      > [!IMPORTANT]
      > Puede descargar un máximo de 50 000 entradas en un archivo CSV desde una única búsqueda de registros de auditoría. Si se descargan 50 000 entradas en el archivo CSV, probablemente puede suponer que existen más de 50 000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, pruebe a usar un intervalo de fecha para reducir el número de entradas de registro de auditoría. Puede que tenga que ejecutar varias búsquedas con intervalos de fecha de menor tamaño para exportar más de 50 000 entradas.
        

3. Después de seleccionar una opción de exportación, se muestra un mensaje en la parte inferior de la ventana que le pide que abra el archivo CSV, lo guarde en la carpeta Descargas o guárdelo en una carpeta específica.

Para obtener más información sobre cómo ver, filtrar o exportar resultados de búsqueda de registros de auditoría, consulte [Búsqueda en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md).
