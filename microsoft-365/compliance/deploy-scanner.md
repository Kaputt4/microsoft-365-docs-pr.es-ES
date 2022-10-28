---
title: Más información sobre el escáner de Microsoft Purview Information Protection
f1.keywords: ''
ms.author: libarson
author: libarson
manager: aashishr
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- purview-compliance
- tier3
description: Obtenga información sobre cómo el analizador de Microsoft Purview Information Protection puede detectar, clasificar y proteger archivos en almacenes de datos.
ms.openlocfilehash: 82006023b6893a62028067e2b99bed9e92ffdbb4
ms.sourcegitcommit: 3d7dd25abcbf923b45eae84ff4d9d2bb95ef4ca4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68777909"
---
# <a name="learn-about-the-information-protection-scanner"></a>Más información sobre el analizador de protección de la información

Use la información de esta sección para obtener información sobre el analizador de protección de la información de Microsoft Purview y, a continuación, cómo instalar, configurar, ejecutar y, si es necesario, solucionar problemas.

El analizador se ejecuta como servicio en Windows Server y le permite detectar, clasificar y proteger archivos en los siguientes almacenes de datos:

- **Rutas de acceso UNC** para recursos compartidos de red que usan los protocolos SMB o NFS (versión preliminar).

- **Bibliotecas de documentos y carpetas de SharePoint** para SharePoint Server 2019 a través de SharePoint Server 2013.

Para clasificar y proteger los archivos, el escáner usa [etiquetas de confidencialidad configuradas](sensitivity-labels.md) en el portal de cumplimiento Microsoft Purview.

## <a name="overview-of-the-scanner"></a>Información general del escáner

El analizador de protección de la información puede inspeccionar cualquier archivo que Windows pueda indexar. Si ha configurado etiquetas de confidencialidad para aplicar la clasificación automática, el analizador puede etiquetar los archivos detectados para aplicar esa clasificación y, opcionalmente, aplicar o quitar la protección. 

En la imagen siguiente se muestra la arquitectura del analizador, donde el analizador detecta archivos en los servidores locales y de SharePoint.

:::image type="content" source="../media/scanner-arch.png" alt-text="arquitectura del escáner de Microsoft Purview Information Protection":::

Para inspeccionar los archivos, el analizador usa IFilters instalados en el equipo. Para determinar si los archivos necesitan etiquetado, el analizador usa tipos de información confidencial y detección de patrones, o patrones regex.

El analizador usa el cliente de Azure Information Protection y puede clasificar y proteger los mismos tipos de archivos que el cliente. Para obtener más información, consulte [Tipos de archivo admitidos por el cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-file-types).

Realice cualquiera de las siguientes acciones para configurar los exámenes según sea necesario:

- **Ejecute el analizador en modo de detección solo** para crear informes que comprueben lo que sucede cuando se etiquetan los archivos.
- **Ejecute el analizador para detectar archivos con información confidencial**, sin configurar etiquetas que apliquen la clasificación automática.
- **Ejecute el analizador automáticamente** para aplicar etiquetas según lo configurado. 
- **Defina una lista de tipos de archivo** para especificar archivos específicos que se van a examinar o excluir.

> [!NOTE]
> El escáner no detecta y etiqueta en tiempo real. Rastrea sistemáticamente los archivos de los almacenes de datos que especifique. Configure este ciclo para que se ejecute una vez o repetidamente.

> [!TIP]
> El analizador admite clústeres de escáner con varios nodos, lo que permite que su organización se escale horizontalmente y logre tiempos de examen más rápidos y un ámbito más amplio. 
> 
> Implemente varios nodos desde el principio o comience con un clúster de un solo nodo y agregue nodos adicionales más adelante a medida que crezca. Implemente varios nodos con el mismo nombre de clúster y base de datos para el cmdlet **Install-AIPScanner** .
> 

## <a name="the-scanning-process"></a>El proceso de examen

Al examinar archivos, el analizador de protección de la información se ejecuta mediante los pasos siguientes:

[1. Determinar si los archivos están incluidos o excluidos para el examen](#1-determine-whether-files-are-included-or-excluded-for-scanning)

[2. Inspeccionar y etiquetar archivos](#2-inspect-and-label-files)

[3. Etiquetar archivos que no se pueden inspeccionar](#3-label-files-that-cant-be-inspected) 

Para obtener más información, consulte [Archivos no etiquetados por el analizador](#files-not-labeled-by-the-scanner).

### <a name="1-determine-whether-files-are-included-or-excluded-for-scanning"></a>1. Determinar si los archivos están incluidos o excluidos para el examen 

El analizador omite automáticamente los archivos que se excluyen de la clasificación y la protección, como archivos ejecutables y archivos del sistema. Para obtener más información, vea [Tipos de archivo excluidos de la clasificación y la protección](/azure/information-protection/rms-client/clientv2-admin-guide-file-types#file-types-excluded-from-classification-and-protection).

El analizador también tiene en cuenta las listas de archivos definidas explícitamente para examinar o excluir del examen. De forma predeterminada, las listas de archivos se aplican a todos los repositorios de datos y también se pueden definir solo para repositorios específicos.

Para definir listas de archivos para su examen o exclusión, use la configuración **Tipos de archivo para examinar** en el trabajo de examen de contenido. Por ejemplo:

![Configuración de tipos de archivo para examinar en el portal de cumplimiento de Purview](../media/scanner-file-types-purview.png)

Para obtener más información, consulte [Implementación del analizador para clasificar y proteger automáticamente los archivos](deploy-scanner-configure-install.md).

### <a name="2-inspect-and-label-files"></a>2. Inspeccionar y etiquetar archivos

Después de identificar los archivos excluidos, el analizador de protección de la información vuelve a filtrar para identificar los archivos admitidos para la inspección.

Estos filtros son los mismos que usa el sistema operativo para Windows Search e indexación, y no requieren ninguna configuración adicional. IFilter de Windows también se usa para examinar los tipos de archivo que usan Word, Excel y PowerPoint, y para documentos PDF y archivos de texto.

Para obtener una lista completa de los tipos de archivo admitidos para la inspección y otras instrucciones para configurar filtros para incluir archivos .zip y .tiff, consulte [Tipos de archivo admitidos para la inspección](/azure/information-protection/rms-client/clientv2-admin-guide-file-types#file-types-supported-for-inspection).

Después de la inspección, los tipos de archivo admitidos se etiquetan con las condiciones especificadas para las etiquetas. Si usa el modo de detección, estos archivos se pueden notificar para que contengan las condiciones especificadas para las etiquetas o para que contengan cualquier tipo de información confidencial conocida.

#### <a name="stopped-scanner-processes"></a>Procesos de escáner detenidos

Si el analizador se detiene y no completa un examen de un gran número de archivos en el repositorio, es posible que tenga que aumentar el número de puertos dinámicos para el sistema operativo que hospeda los archivos.

Por ejemplo, la protección del servidor para SharePoint es una de las razones por las que el analizador superaría el número de conexiones de red permitidas y, por lo tanto, se detendrá.

Para comprobar si la protección del servidor para SharePoint es la causa de la detención del analizador, busque el siguiente mensaje de error en los registros del analizador en **%localappdata%\Microsoft\MSIP\Logs\MSIPScanner.iplog** (varios registros se comprimen en un archivo ZIP):

`Unable to connect to the remote server ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted IP:port`

Para obtener más información sobre cómo ver el intervalo de puertos actual y aumentarlo si es necesario, consulte [Configuración que se puede modificar para mejorar el rendimiento de la red](/biztalk/technical-guides/settings-that-can-be-modified-to-improve-network-performance).

> [!TIP]
> En el caso de las granjas de servidores de SharePoint grandes, es posible que tenga que aumentar el umbral de vista de lista, que tiene un valor predeterminado de **5000**.
>
> Para obtener más información, vea [Administrar listas y bibliotecas grandes en SharePoint](https://support.office.com/article/manage-large-lists-and-libraries-in-sharepoint-b8588dae-9387-48c2-9248-c24122f07c59#__bkmkchangelimit&ID0EAABAAA=Server).
>

### <a name="3-label-files-that-cant-be-inspected"></a>3. Etiquetar archivos que no se pueden inspeccionar

Para los tipos de archivo que no se pueden inspeccionar, el analizador aplica la etiqueta predeterminada de su directiva de etiqueta de confidencialidad o la etiqueta predeterminada configurada para el analizador.

### <a name="files-not-labeled-by-the-scanner"></a>Archivos no etiquetados por el escáner
El analizador no puede etiquetar los archivos en las siguientes circunstancias:

- Cuando la etiqueta aplica la clasificación, pero no la protección, y el tipo de archivo no admite la clasificación solo por parte del cliente. Para obtener más información, vea [Tipos de archivo admitidos solo para la clasificación](/azure/information-protection/rms-client/clientv2-admin-guide-file-types#file-types-supported-for-classification-only).

- Cuando la etiqueta aplica la clasificación y la protección, pero el analizador no admite el tipo de archivo.
  
    De forma predeterminada, el escáner solo protege los tipos de archivo de Office y los archivos PDF cuando están protegidos mediante el estándar ISO para el cifrado PDF. 

    Se pueden agregar otros tipos de archivos para la protección al [cambiar los tipos de archivos que se van a proteger](deploy-scanner-configure-install.md#change-which-file-types-to-protect).

**Ejemplo**: después de inspeccionar .txt archivos, el analizador no puede aplicar una etiqueta configurada solo para la clasificación, ya que el tipo de archivo .txt no admite solo la clasificación. 

Sin embargo, si la etiqueta está configurada para la clasificación y la protección, y el tipo de archivo .txt se incluye para que el escáner lo proteja, el analizador puede etiquetar el archivo.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre la implementación del analizador, consulte los artículos siguientes:

- [Requisitos previos de implementación del analizador](deploy-scanner-prereqs.md)
- [Configuración e instalación del analizador](deploy-scanner-configure-install.md)
- [Ejecución de exámenes mediante el analizador](deploy-scanner-manage.md)

**Más información**:

- [¡Vea nuestro vídeo de demostración de un extremo a otro del escáner!](https://www.youtube.com/watch?v=f1gy1KalSts) Vea una revisión paso a paso de la arquitectura, la arquitectura, la recomendación, la instalación y la configuración del escáner.

- Consulte nuestro blog sobre los procedimientos recomendados para el escáner: [Procedimientos recomendados para implementar y usar el escáner UL de AIP](https://aka.ms/AIPScannerBestPractices).

- ¿Está interesado en cómo el equipo de ingeniería y operaciones de Core Services en Microsoft implementó este escáner?  Lea el caso práctico técnico: [Automatización de la protección de datos con azure Information Protection escáner](https://www.microsoft.com/itshowcase/Article/Content/1070/Automating-data-protection-with-Azure-Information-Protection-scanner).

- También puede usar PowerShell para clasificar y proteger de forma interactiva los archivos del equipo de escritorio. Para obtener más información sobre este y otros escenarios que usan PowerShell, consulte [Uso de PowerShell con azure Information Protection cliente de etiquetado unificado](./
- .md).
