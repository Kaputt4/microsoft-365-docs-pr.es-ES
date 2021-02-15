---
title: Exportar resultados de la búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: Exportar los resultados de la búsqueda de una búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 a un equipo local. Los resultados del correo electrónico se exportan como archivos PST. El contenido de los sitios de SharePoint y OneDrive para la Empresa se exporta como documentos nativos de Office.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7027593768238b3d9a465eaa6038d92234c32f82
ms.sourcegitcommit: ddbc6f8ebadf2f8149dff910b743535cbc3fa3c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "49992516"
---
# <a name="export-content-search-results"></a>Exportar resultados de la búsqueda de contenido

Una vez ejecutada correctamente una búsqueda de contenido, puede exportar los resultados de la búsqueda a un equipo local. Cuando exporta los resultados de correo electrónico, estos se descargan en su equipo como archivos PST. Al exportar contenido de sitios de SharePoint y OneDrive para la Empresa, se exportan copias de documentos nativos de Office. Hay otros documentos e informes incluidos con los resultados de búsqueda exportados.
  
Exportar los resultados de una búsqueda de contenido implica preparar los resultados y, a continuación, descargarlos en un equipo local.
  
## <a name="before-you-export-content-search-results"></a>Antes de exportar los resultados de la búsqueda de contenido

- Para exportar los resultados de la búsqueda, debe tener asignado el rol de administración Exportar en el Centro de & cumplimiento. Este rol se asigna al grupo de roles de administrador de exhibición de documentos electrónicos integrado. No se asigna de forma predeterminada al grupo de roles de administración de la organización. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:
  
  - Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
  
  - Microsoft .NET Framework 4.7
  
- Debe usar uno de los siguientes exploradores compatibles para ejecutar la herramienta de exportación de exhibición de documentos electrónicos<sup>1:</sup>

  - Microsoft Edge <sup>2</sup>
  
    O

  - Microsoft Internet Explorer 10 y versiones posteriores
  
  > [!NOTE]
  > <sup>1</sup> Microsoft no fabrica extensiones ni complementos de terceros para ClickOnce aplicaciones. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con extensiones o complementos de terceros.<br/>
  > <sup>2</sup> Como resultado de los cambios recientes en Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada. Para obtener instrucciones sobre cómo habilitar ClickOnce en Edge, vea Usar la herramienta de exportación de exhibición de documentos [electrónicos en Microsoft Edge.](configure-edge-to-export-search-results.md)
  
- Se recomienda descargar los resultados de la búsqueda en un equipo local. Sin embargo, para evitar que el firewall o la infraestructura de proxy de su empresa causen problemas al descargar los resultados de la búsqueda, puede considerar la posibilidad de descargar los resultados de la búsqueda en un escritorio virtual fuera de la red. Esto puede disminuir los tiempos de espera que se producen en las conexiones de datos de Azure al exportar un gran número de archivos. Para obtener más información acerca de los escritorios virtuales, vea [Windows Virtual Desktop.](https://azure.microsoft.com/services/virtual-desktop) 

- Para mejorar el rendimiento al descargar resultados de búsqueda, considere dividir las búsquedas que devuelven un gran conjunto de resultados en búsquedas más pequeñas. Por ejemplo, puede usar intervalos de fechas en consultas de búsqueda para devolver un conjunto más pequeño de resultados que se pueden descargar más rápido.
  
- Al exportar los resultados de la búsqueda, los datos se almacenan temporalmente en una ubicación de Azure Storage proporcionada por Microsoft en la nube de Microsoft antes de que se descarguen en el equipo local. Asegúrese de que su organización puede conectarse al punto de conexión de Azure, que es **\* .blob.core.windows.net** (el comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan de la ubicación de Azure Storage dos semanas después de su creación. 
  
- Si su organización usa un servidor proxy para comunicarse con Internet, debe definir la configuración del servidor proxy en el equipo que usa para exportar los resultados de la búsqueda (para que el servidor proxy pueda autenticar la herramienta de exportación). Para ello, abre el archivo  *machine.config*  en la ubicación que coincida con tu versión de Windows. 
  
  - **32 bits:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64 bits:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Agregue las siguientes líneas al archivo  *machine.config*  en algún lugar entre las  `<configuration>`  `</configuration>` etiquetas y. Asegúrese de reemplazar y  `ProxyServer`  `Port` con los valores correctos para su organización; por ejemplo,  `proxy01.contoso.com:80` . 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

## <a name="step-1-prepare-search-results-for-export"></a>Paso 1: Preparar los resultados de búsqueda para la exportación

El primer paso es preparar los resultados de búsqueda para la exportación. Al preparar los resultados, se cargan en una ubicación de Azure Storage proporcionada por Microsoft en la nube de Microsoft. El contenido de los buzones y sitios se carga a una velocidad máxima de 2 GB por hora.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
  
2. Inicie sesión con su cuenta profesional o educativa.
  
3. En el panel izquierdo del Centro de seguridad & cumplimiento, haga clic en **Buscar** \> **contenido.**
  
4. En la **página Búsqueda de** contenido, seleccione una búsqueda. 
  
5. En el panel de detalles, en **Exportar resultados a un equipo**, haga clic en **Iniciar la exportación**.
  
    > [!NOTE]
    > Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda. Si esto ocurre, cancele la exportación, haga clic en **Actualizar los resultados de búsqueda** en el panel de detalles para la búsqueda seleccionada y, a continuación, inicie la exportación de nuevo después de que se actualicen los resultados.  
  
6. En la **página Exportar los resultados de** búsqueda, en Opciones de **salida,** elija una de las siguientes opciones:
  
    - Todos los elementos, excepto los que tienen un formato no reconocido, se cifran o no se indexaron por otros motivos.
  
    - Todos los elementos, incluidos los que tienen un formato no reconocido, están cifrados o no se indexaron por otros motivos.
  
    - Solo los elementos que tienen un formato no reconocido, están cifrados o no se indexaron por otros motivos
  
    Vea la [sección Más información](#more-information) para obtener una descripción sobre cómo se exportan los elementos parcialmente indizados. Para obtener más información acerca de los elementos parcialmente indizados, vea [Elementos parcialmente indizados en la búsqueda de contenido.](partially-indexed-items-in-content-search.md)
  
7. En **Exportar contenido de Exchange como**, elija una de las siguientes opciones:
  
    - **Un archivo PST para cada buzón:** Exporta un archivo PST para cada buzón de usuario que contiene los resultados de la búsqueda. Los resultados del buzón de archivo del usuario se incluyen en el mismo archivo PST. Esta opción reproduce la estructura de carpetas del buzón de correo de origen.
  
    - **Un archivo PST que contiene todos los mensajes:** Exporta un único archivo PST (denominado *Exchange.pst)* que contiene los resultados de la búsqueda de todos los buzones de origen incluidos en la búsqueda. Esta opción reproduce la estructura de carpetas de buzón para cada mensaje.
  
    - **Un archivo PST que contiene todos los mensajes en una sola carpeta:** Exporta los resultados de la búsqueda a un único archivo PST donde todos los mensajes se encuentran en una sola carpeta de nivel superior. Esta opción permite a los revisores revisar los elementos en orden cronológico (los elementos se ordenan por fecha de envío) sin tener que navegar por la estructura de carpetas de buzón original para cada elemento.
  
    - **Mensajes individuales:** Exporta los resultados de la búsqueda como mensajes de correo electrónico individuales, con el formato .msg. Si selecciona esta opción, los resultados de la búsqueda de correo electrónico se exportarán a una carpeta del sistema de archivos. La ruta de acceso de carpeta para mensajes individuales es la misma que la que se usa si exportó los resultados a archivos PST.
  
      > [!IMPORTANT]
      > Para descifrar mensajes protegidos por RMS cuando se exportan, debe exportar los resultados de la búsqueda de correo electrónico como mensajes individuales. Los mensajes cifrados permanecerán cifrados si exporta los resultados de la búsqueda como un archivo PST. Para obtener más información, consulte Descifrar mensajes de correo electrónico protegidos por RMS y [datos adjuntos](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments) de archivos cifrados en este artículo.
  
8. Haga clic en **la casilla Habilitar desduplicación** para excluir mensajes duplicados. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen buzones o carpetas públicas de Exchange. 
  
    Si selecciona esta opción, solo se exportará una copia de un mensaje incluso si se encuentran varias copias del mismo mensaje en los buzones en los que se ha buscado. El informe de resultados de exportación (Results.csv) contendrá una fila por cada copia de un mensaje duplicado para que pueda identificar los buzones (o carpetas públicas) que contienen una copia del mensaje duplicado. Para obtener más información acerca de la desduplicación y cómo se identifican los elementos duplicados, vea Desduplicación en los resultados de la [búsqueda de exhibición de documentos electrónicos.](de-duplication-in-ediscovery-search-results.md)
  
9. Haga clic **en la casilla Incluir versiones para documentos de SharePoint** para exportar todas las versiones de documentos de SharePoint. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios de SharePoint o OneDrive para la Empresa. 
  
10. Haga clic en la casilla Exportar archivos en una carpeta comprimida **(comprimida)** para exportar los resultados de la búsqueda a carpetas comprimidas. Esta opción solo está disponible cuando elige exportar elementos de Exchange como mensajes individuales y cuando los resultados de la búsqueda incluyen documentos de SharePoint o OneDrive. Esta opción se usa principalmente para evitar el límite de 260 caracteres en los nombres de ruta de acceso de archivo de Windows cuando se exportan los elementos. Consulte "Nombres de archivo de los elementos exportados" en la [sección Más](#more-information) información. 
  
11. Haga clic en **Iniciar la exportación**. Los resultados de la búsqueda están preparados para su descarga, lo que significa que se cargan en una ubicación de Azure Storage en la nube de Microsoft. Esto podría llevar varios minutos.

Vea la siguiente sección para obtener instrucciones para descargar los resultados de búsqueda exportados.
  
## <a name="step-2-download-the-search-results"></a>Paso 2: Descargar los resultados de búsqueda

El siguiente paso es descargar los resultados de la búsqueda desde la ubicación de Azure Storage en el equipo local.
  
1. En la **página Búsqueda de contenido,** haga clic en **la pestaña** Exportaciones. 
  
   Es posible que tenga que hacer clic **en Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que creó. Los trabajos de exportación tienen el mismo nombre que la búsqueda correspondiente **con _Export** anexado al nombre de búsqueda.
  
2. Seleccione el trabajo de exportación que creó en el paso 1.

3. En la página desplegable de la tecla **Exportar**, haga clic **en Copiar en el Portapapeles.** Use esta clave en el paso 6 para descargar los resultados de la búsqueda.
  
4. Haga clic en **Descargar resultados**.

5. Si se le pide que instale la herramienta de exportación de **exhibición** de documentos electrónicos, haga clic **en Instalar.**

6. En la herramienta de exportación de exhibición **de documentos electrónicos,** haga lo siguiente:

   ![Herramienta de exportación de exhibición de documentos electrónicos](../media/eDiscoveryExportTool.png)

   1. Pegue la clave de exportación que copió en el paso 3 en el cuadro correspondiente.
  
   2. Haga clic en **Examinar** para especificar la ubicación en la que desea descargar los archivos de los resultados de la búsqueda.
  
      > [!IMPORTANT]
      >  Debido a una actividad de red elevada durante la descarga, debe descargar los resultados de la búsqueda solo en una ubicación en una unidad interna del equipo local. Para obtener la mejor experiencia de descarga, siga estas directrices: <br/>
      >- No descargue los resultados de la búsqueda en una ruta de acceso UNC, una unidad de red asignada, una unidad USB externa o una cuenta sincronizada de OneDrive para la Empresa.<br/>
      >- Deshabilite el examen antivirus de la carpeta en la que descarga el resultado de la búsqueda.<br/>
      >- Descargue los resultados de la búsqueda en diferentes carpetas para trabajos de descarga simultáneos.

6. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.
  
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez completado el proceso de exportación, puede obtener acceso a los archivos en la ubicación donde se descargaron.

## <a name="more-information"></a>Más información

Aquí encontrará más información sobre cómo exportar los resultados de la búsqueda.
  
[Límites de exportación](#export-limits)
  
[Exportar informes](#export-reports)
  
[Exportar elementos parcialmente indizados](#exporting-partially-indexed-items)

[Exportar mensajes individuales o archivos PST](#exporting-individual-messages-or-pst-files)
  
[Exportar resultados de más de 100 000 buzones](#exporting-results-from-more-than-100000-mailboxes)

[Descifrar mensajes de correo electrónico protegidos por RMS y datos adjuntos de archivos cifrados](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Nombres de archivo de los elementos exportados](#filenames-of-exported-items)  
  
[Varios](#miscellaneous)
  
### <a name="export-limits"></a>Límites de exportación

Para obtener información acerca de los límites al exportar resultados de búsqueda de contenido, vea la sección "Límites de exportación" [en Límites para la búsqueda de contenido.](limits-for-content-search.md#export-limits)

### <a name="export-reports"></a>Exportar informes
  
- Al exportar los resultados de la búsqueda, se incluyen los siguientes informes además de los resultados de la búsqueda.
  
  - **Exportar resumen** Documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se buscaron, los tamaños estimados y descargados de los resultados de la búsqueda y el número estimado y descargado de elementos que se exportaron.
  
  - **Manifiesto** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda.
  
  - **Resultados** Documento de Excel que contiene información sobre cada elemento que se descarga como resultado de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos:
  
    - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
  
    - La fecha en que se envió o se recibió el mensaje.

    - La línea Asunto del mensaje.

    - El remitente y los destinatarios del mensaje.

    - Si el mensaje es un mensaje duplicado si habilitó la opción de desduplicación al exportar los resultados de la búsqueda. Los mensajes duplicados tienen un valor en la **columna Duplicar** a elemento que identifica el mensaje como duplicado. El valor de la **columna Duplicar a elemento** contiene la identidad del elemento del mensaje que se exportó. Para obtener más información, vea [Desduplicación en los resultados de búsqueda de exhibición de documentos electrónicos.](de-duplication-in-ediscovery-search-results.md)

      Para los documentos de sitios de SharePoint y OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:

      - La dirección URL del documento.

      - La dirección URL de la colección de sitio donde se ubica el documento.

      - La fecha en la que el documento se modificó por última vez.

      - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).

  - **Elementos no indexados** Documento de Excel que contiene información sobre los elementos parcialmente indizados que se incluirían en los resultados de la búsqueda. Si no incluye elementos parcialmente indizados al generar el informe de resultados de búsqueda, este informe se seguirá descargando, pero estará vacío.

  - **Errores y advertencias** Contiene errores y advertencias para los archivos encontrados durante la exportación. Vea la columna Detalles del error para obtener información específica de cada error o advertencia individual.

  - **Elementos omitido** Al exportar resultados de búsqueda de sitios de SharePoint y OneDrive para la Empresa, la exportación normalmente incluirá un informe de elementos omitido (SkippedItems.csv). Los elementos mencionados en este informe suelen ser elementos que no se descargarán, como una carpeta o un conjunto de documentos. No exportar estos tipos de elementos es por diseño. Para otros elementos que se omitieron, el campo "Tipo de error" y "Detalles del error" en el informe de elementos omitido muestra el motivo por el que se omitió el elemento y no se descargó con los otros resultados de la búsqueda.

  - **Registro de seguimiento** Contiene información de registro detallada sobre el proceso de exportación y puede ayudar a descubrir problemas durante la exportación.
  
    > [!NOTE]
    > Simplemente puede exportar estos documentos sin tener que exportar los resultados de búsqueda reales. Vea [Exportar un informe de búsqueda de contenido.](export-a-content-search-report.md) 
  
### <a name="exporting-partially-indexed-items"></a>Exportar elementos parcialmente indizados
  
- Si exporta elementos de buzón de una búsqueda de contenido que devuelve todos los elementos de buzón de los resultados de la búsqueda (porque no se incluyen palabras clave en la consulta de búsqueda), los elementos parcialmente indizados no se copiarán en el archivo PST que contiene los elementos no indexados. Esto se debe a que todos los elementos, incluidos los elementos parcialmente indizados, se incluyen automáticamente en los resultados de búsqueda normales. Esto significa que los elementos parcialmente indizados se incluirán en un archivo PST (o como mensajes individuales) que contenga los otros elementos indizados.

    Si exporta los elementos indizados y parcialmente indizados o si exporta solo los elementos indizados de una búsqueda de contenido que devuelve todos los elementos, se descargará el mismo número de elementos. Esto sucede aunque los resultados de búsqueda estimados para la búsqueda de contenido (que se muestran en las estadísticas de búsqueda en el Centro de seguridad & cumplimiento) incluirán una estimación independiente para el número de elementos parcialmente indizados. Por ejemplo, supongamos que la estimación de una búsqueda que incluye todos los elementos (sin palabras clave en la consulta de búsqueda) muestra que se encontraron 1.000 elementos y que también se encontraron 200 elementos parcialmente indizados. En este caso, los 1.000 elementos incluyen los elementos parcialmente indizados porque la búsqueda devuelve todos los elementos. En otras palabras, la búsqueda devuelve un total de 1.000 elementos y no 1.200 elementos (como puede esperar). Si exporta los resultados de esta búsqueda y elige exportar elementos indizados y parcialmente indizados (o exportar solo elementos parcialmente indizados), se descargarán 1.000 elementos. De nuevo, esto se debe a que los elementos parcialmente indizados se incluyen con los resultados normales (indizados) cuando se usa una consulta de búsqueda en blanco para devolver todos los elementos. En este mismo ejemplo, si decide exportar solo elementos parcialmente indizados, solo se descargarán los 200 elementos no indexados.

    Tenga en cuenta también que en el ejemplo anterior (al exportar elementos indizados  y parcialmente indizados o exportar solo elementos indizados), el informe De resumen de exportación incluido con los resultados de búsqueda exportados enumeraría 1.000 elementos estimados y 1.000 elementos descargados por los mismos motivos descritos anteriormente. 

- Si la búsqueda de la que exporta los resultados era una búsqueda de ubicaciones de contenido específicas o de todas las ubicaciones de contenido de la organización, solo se exportarán los elementos parciales de las ubicaciones de contenido que contengan elementos que coincidan con los criterios de búsqueda. En otras palabras, si no se encuentran resultados de búsqueda en un buzón o sitio, no se exportarán los elementos parcialmente indizados de ese buzón o sitio. El motivo de esto es que exportar elementos parcialmente indizados desde muchas ubicaciones de la organización puede aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

    Para exportar elementos parcialmente indizados de todas las ubicaciones de contenido de una búsqueda, configure la búsqueda para que devuelva todos los elementos (quitando las palabras clave de la consulta de búsqueda) y, a continuación, exporte solo elementos parcialmente indizados al exportar los resultados de la búsqueda.

    ![Usar la tercera opción de exportación para exportar solo elementos no indexados](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Al exportar resultados de búsqueda desde sitios de SharePoint o OneDrive para la Empresa, la capacidad de exportar elementos no indexados también depende de la opción de exportación que seleccione y de si un sitio en el que se ha buscado contiene un elemento indizado que coincide con los criterios de búsqueda. Por ejemplo, si busca sitios específicos de SharePoint o OneDrive para la Empresa y no se encuentran resultados de búsqueda, no se exportarán elementos sin indexar de esos sitios si elige la segunda opción de exportación para exportar elementos indexados y no indexados. Si un elemento indizado de un sitio coincide con los criterios de búsqueda, todos los elementos sin indexar de ese sitio se exportarán al exportar elementos indizados y no indexados. En la siguiente ilustración se describen las opciones de exportación en función de si un sitio contiene un elemento indizado que coincide con los criterios de búsqueda.

    ![Elija la opción de exportación en función de si un sitio contiene un elemento indizado que coincide con los criterios de búsqueda](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    1. Solo se exportan los elementos indizados que coinciden con los criterios de búsqueda. No se exportan elementos parcialmente indizados.

    2. Si ningún elemento indizado de un sitio coincide con los criterios de búsqueda, no se exportarán los elementos parcialmente indizados de ese mismo sitio. Si los elementos indizados de un sitio se devuelven en los resultados de la búsqueda, se exportan los elementos parcialmente indizados de ese sitio. En otras palabras, solo se exportan los elementos parcialmente indizados de los sitios que contienen elementos que coinciden con los criterios de búsqueda.

    3. Todos los elementos parcialmente indizados de todos los sitios de la búsqueda se exportan, independientemente de si un sitio contiene elementos que coinciden con los criterios de búsqueda.

    Si decide exportar elementos parcialmente indizados, los elementos de buzón parcialmente indizados se exportan en un archivo PST independiente, independientemente de la opción que elija en Exportar contenido de **Exchange como**.

- Si se devuelven elementos parcialmente indizados en los resultados de la búsqueda (porque otras propiedades de elementos parcialmente indizados coinciden con los criterios de búsqueda), los elementos parcialmente indizados se exportan con los resultados de búsqueda normales. Por lo tanto, si decide exportar elementos indizados y elementos parcialmente indizados (seleccionando la opción Todos los **elementos, incluidos** los que tienen un formato no reconocido, están cifrados o no se indexaron por otros motivos, la opción de exportación), los elementos parcialmente indizados exportados con los resultados normales se mostrarán en el informe de Results.csv. No se mostrarán en el informe de items.csv indexado.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Exportar mensajes individuales o archivos PST
  
- Si el nombre de la ruta de acceso de un mensaje supera el límite de caracteres máximo para Windows, el nombre de la ruta de acceso del archivo se trunca. Pero el nombre de la ruta de acceso del archivo original aparecerá en el manifiesto y el registro de resultados.
  
- Como se ha explicado anteriormente, los resultados de la búsqueda de correo electrónico se exportan a una carpeta en el sistema de archivos. La ruta de acceso de carpeta para mensajes individuales replicaría la ruta de acceso de carpeta en el buzón del usuario. Por ejemplo, para una búsqueda denominada "ContosoCase101" los mensajes de la bandeja de entrada de un usuario se ubicarán en la ruta de acceso de la  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` carpeta.

- Si decide exportar mensajes de correo electrónico en un archivo PST  que contiene  todos los mensajes de una sola carpeta, se incluyen una carpeta Elementos eliminados y una carpeta Carpetas de búsqueda en el nivel superior de la carpeta PST. Estas carpetas están vacías.

- Como se indicó anteriormente, debe exportar los resultados de la búsqueda de correo electrónico como mensajes individuales para descifrar los mensajes protegidos por RMS cuando se exportan. Los mensajes cifrados permanecerán cifrados si exporta los resultados de la búsqueda de correo electrónico como un archivo PST.
  
### <a name="exporting-results-from-more-than-100000-mailboxes"></a>Exportar resultados de más de 100 000 buzones

- Como se ha explicado anteriormente, debe usar PowerShell del Centro de seguridad & Cumplimiento para descargar los resultados de búsqueda de más de 100 000 buzones. Puede ejecutar el siguiente script en esta sección para descargar estos resultados de búsqueda. El uso de este script supone que ya ha exportado los  resultados de la búsqueda (el trabajo de exportación se muestra en la pestaña Exportaciones de la herramienta de búsqueda de contenido) y ahora desea descargarlos.

   ```powershell
   $export=Get-ComplianceSearchAction SEARCHNAME_Export -IncludeCredential;
   $exportUrl=   [System.Uri]::EscapeDataString(($export.Results.Split(";") | ?{$_ -like '*Container url*'} | %{$_.Split(":",2)} | select -last 1).Trim());
   $exportToken=($export.Results.Split(";") | ?{$_ -like '*SAS Token*'} | %{$_.Split(":",2)} | select -last 1).Trim();
   ."$env:ProgramFiles\Internet Explorer\IEXPLORE.EXE" "https://complianceclientsdf.blob.core.windows.net/v16/Microsoft.Office.Client.Discovery.UnifiedExportTool.application?name=$($export.Name)&source=$exportUrl&zip=allow&trace=1";
   $exportToken | clip;
   ```

  En el script, debe especificar el nombre de la búsqueda a la que desea exportar los resultados. Por ejemplo, para una búsqueda con nombre, `SearchAllMailboxes` reemplace SEARCHNAME_Export por `SearchAllMailboxes_Export` .

  Después de agregar el nombre de la búsqueda al script, puede copiar el texto del script y pegarlo en una ventana Windows PowerShell conectada Windows PowerShell [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)del Centro de seguridad & cumplimiento. Después de pegar el script, se muestra la herramienta de exportación de exhibición de documentos electrónicos (como cuando descarga los resultados de búsqueda mediante la interfaz de usuario):

  ![Herramienta de exportación de exhibición de documentos electrónicos](../media/eDiscoveryExportTool.png)

  Haga clic en el cuadro de teclas de exportación y, a continuación, presione para pegar la tecla de exportación (el script copia la tecla `CTRL + V` de exportación en el Portapapeles). Haga **clic en** Examinar para especificar la ubicación donde desea descargar los archivos y, a continuación, inicie la descarga.

  Como se indicó anteriormente, se recomienda descargar los resultados de la búsqueda en una unidad de disco local debido a la gran cantidad de actividad de disco (lecturas y escrituras). No descargue los resultados de la búsqueda en una unidad de red asignada u otra ubicación de red.

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Descifrar mensajes de correo electrónico protegidos por RMS y datos adjuntos de archivos cifrados

Los mensajes de correo electrónico protegidos por derechos (protegidos por RMS) incluidos en los resultados de una búsqueda de contenido se descifrarán al exportarlos. Además, cualquier archivo que se cifra con una tecnología de cifrado de [Microsoft](encryption.md) y se adjunta a un mensaje de correo electrónico que se incluye en los resultados de la búsqueda también se descifrará cuando se exporte. Esta funcionalidad de descifrado está habilitada de forma predeterminada para los miembros del grupo de roles administrador de exhibición de documentos electrónicos. Esto se debe a que la función de administración Descifrar RMS se asigna a este grupo de funciones de forma predeterminada. Tenga en cuenta lo siguiente al exportar mensajes de correo electrónico cifrados y datos adjuntos:
  
- Como se ha explicado anteriormente, para descifrar mensajes protegidos por RMS al exportarlos, debe exportar los resultados de la búsqueda como mensajes individuales. Si exporta los resultados de la búsqueda a un archivo PST, los mensajes protegidos por RMS permanecen cifrados.

- Los mensajes descifrados se identifican en el informe **ResultsLog.** Este informe contiene una columna denominada **Decode Status** y un valor **Decoded** en esta columna identifica los mensajes que se descifraron.

- Además de descifrar datos adjuntos de archivos al exportar resultados de búsqueda, también puede obtener una vista previa del archivo descifrado al obtener una vista previa de los resultados de la búsqueda. Solo puede ver el mensaje de correo electrónico protegido por derechos después de exportarlo.

- En este momento, la capacidad de descifrado al exportar resultados de búsqueda no incluye contenido cifrado de sitios de SharePoint y OneDrive para la Empresa. Sin embargo, la compatibilidad estará disponible próximamente para los documentos cifrados con tecnologías de cifrado de Microsoft y almacenados en SharePoint Online y OneDrive para la Empresa.

- Si necesita evitar que alguien descifra los mensajes de protección de RMS y los datos adjuntos de archivos cifrados, debe crear un grupo de roles personalizado (copiando el grupo de roles integrado administrador de exhibición de documentos electrónicos) y, a continuación, quitar el rol de administración Descifrar RMS del grupo de roles personalizado. A continuación, agregue la persona que no desea descifrar mensajes como miembro del grupo de roles personalizado.
  
### <a name="filenames-of-exported-items"></a>Nombres de archivo de los elementos exportados
  
- Hay un límite de 260 caracteres (impuesto por el sistema operativo) para el nombre completo de la ruta de acceso para los mensajes de correo electrónico y documentos del sitio exportados al equipo local. El nombre de la ruta de acceso completa de los elementos exportados incluye la ubicación original del elemento y la ubicación de la carpeta en el equipo local donde se descargan los resultados de la búsqueda. Por ejemplo, si especifica descargar los resultados de la búsqueda en la herramienta de exportación de exhibición de documentos electrónicos, el nombre completo de la ruta de acceso de un elemento de correo electrónico  `C:\Users\Admin\Desktop\SearchResults` descargado sería  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

    Si se supera el límite de 260 caracteres, se truncará el nombre completo de la ruta de acceso de un elemento.

  - Si el nombre de la ruta de acceso completa tiene más de 260 caracteres, el nombre del archivo se acortará para que se reduzca al límite; tenga en cuenta que el nombre de archivo truncado (excluyendo la extensión de archivo) no tendrá menos de ocho caracteres.

  - Si el nombre de la ruta de acceso completa sigue siendo demasiado largo después de acortar el nombre de archivo, el elemento se mueve de su ubicación actual a la carpeta principal. Si el nombre de la ruta de acceso sigue siendo demasiado largo, el proceso se repite: acorte el nombre de archivo y, si es necesario, vuelva a moverse a la carpeta principal. Este proceso se repite hasta que el nombre de la ruta de acceso completa está por debajo del límite de 260 caracteres.

  - Si ya existe un nombre de ruta de acceso completo truncado, se agrega un número de versión al final del nombre de archivo; por ejemplo,  `statusmessage(2).msg` .

    Para ayudar a mitigar este problema, considere la posibilidad de descargar los resultados de la búsqueda en una ubicación con un nombre de ruta de acceso corto; por ejemplo, descargar los resultados de la búsqueda en una carpeta con nombre agregaría menos caracteres a los nombres de ruta de acceso de los elementos exportados que descargarlos  `C:\Results` en una carpeta denominada  `C:\Users\Admin\Desktop\Results` .

- Al exportar documentos del sitio, también es posible que se modifique el nombre de archivo original de un documento. Esto sucede específicamente para los documentos que se han eliminado de un sitio de SharePoint o de OneDrive para la Empresa que se ha puesto en retención. Después de eliminar un documento que está en un sitio que está en conservación, el documento eliminado se mueve automáticamente a la biblioteca de conservación de documentos del sitio (que se creó cuando el sitio se colocó en retención). Cuando el documento eliminado se mueve a la biblioteca de conservación de documentos, se anexa un identificador único y generado aleatoriamente al nombre de archivo original del documento. Por ejemplo, si el nombre de archivo de un documento es y ese documento se elimina más adelante y se mueve a la biblioteca de conservación de documentos, el nombre de archivo del documento que se mueve a la biblioteca de conservación de documentos se modifica a un valor como  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` . Si un documento de la biblioteca de conservación de documentos coincide con la consulta de una búsqueda de contenido y exporta los resultados de esa búsqueda, el archivo exportado tiene el nombre de archivo modificado; en este ejemplo, el nombre de archivo del documento exportado sería  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    Cuando se modifica un documento de un sitio que está en retención (y se ha habilitado el control de versiones para la biblioteca de documentos del sitio), se crea automáticamente una copia del archivo en la biblioteca de conservación de documentos. En este caso, también se anexa un identificador único y generado aleatoriamente al nombre de archivo del documento que se copia en la biblioteca de conservación de documentos.

    El motivo por el que los nombres de archivo de los documentos que se mueven o copian a la biblioteca de conservación de documentos es evitar nombres de archivo en conflicto. Para obtener más información acerca de cómo colocar una retención en sitios y la biblioteca de conservación de documentos, vea Información general sobre la conservación local en [SharePoint Server 2016.](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)

### <a name="miscellaneous"></a>Varios
  
- Al descargar los resultados de búsqueda con la herramienta de exportación de exhibición de documentos electrónicos, es posible que reciba el siguiente error: este es un error transitorio, que normalmente se produce en la ubicación de `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` Azure Storage. Para resolver este problema, vuelva a intentar [descargar los resultados](#step-2-download-the-search-results)de la búsqueda, que reiniciarán la herramienta de exportación de exhibición de documentos electrónicos.

- Todos los resultados de búsqueda y los informes de exportación se incluyen en una carpeta que tiene el mismo nombre que en la búsqueda de contenido. Los mensajes de correo electrónico que se exportaron se ubican en una carpeta denominada **Exchange**. Los documentos se ubican en una carpeta denominada **SharePoint**.

- Los metadatos del sistema de archivos para documentos en sitios de SharePoint y OneDrive para la Empresa se mantienen cuando los documentos se exportan al equipo local. Eso significa que las propiedades del documento, como la fecha de creación y la fecha en la que se modificó por última vez, no cambian cuando se exportan los documentos.

- Si los resultados de la búsqueda incluyen un elemento de lista de SharePoint que coincide con la consulta de búsqueda, todas las filas de la lista se exportarán además del elemento que coincida con la consulta de búsqueda y los datos adjuntos de la lista. El motivo de este comportamiento es proporcionar un contexto para los elementos de lista que se devuelven en los resultados de la búsqueda. Tenga en cuenta también que los datos adjuntos y los elementos de lista adicionales pueden hacer que el recuento de elementos exportados sea diferente de la estimación original de los resultados de la búsqueda.
