---
title: Cargar datos que no son de Microsoft 365 en pruebas
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
description: Obtenga información sobre cómo usar la característica de importación de contenido no de Office 365 para cargar documentos que no son de Office 365 en pruebas en una investigación de datos.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: b6d8c2f65a1fa3a43fa2ac4bf3821cc6c1fac514
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285376"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>Cargar datos que no son de Microsoft 365 en pruebas

No todos los documentos que puede que necesite analizar en una investigación de datos se ubicarán en Microsoft 365. Con la característica de importación de contenido que no es de Microsoft 365, puede cargar documentos que no vivan en Microsoft 365 en pruebas para que puedan analizarse en una investigación de datos.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para cargar contenido no de Office 365

Para usar la característica de carga que no es de Microsoft 365, tal y como se describe en este procedimiento, es necesario que:

- Una suscripción A Microsoft 365 o A Office 365 E5.

- Todas las personas de interés cuyo contenido que no sea de Microsoft 365 se cargarán deben tener la licencia del complemento E5 o E5 adecuada.

- Un caso de eDiscovery existente.

- Todos los archivos para carga recopilados en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentran en este formato *alias@domainname*. El *alias@domainname* debe ser el alias y el dominio del usuario. Puede recopilar todas las carpetas de *alias@domainname* en una carpeta raíz. La carpeta raíz solo puede contener las carpetas *alias@domainname* , no debe haber archivos sueltos en la carpeta raíz.

- Una cuenta que sea un administrador de eDiscovery o un administrador de exhibición de documentos electrónicos herramientas de almacenamiento de Microsoft Azure instaladas en un equipo que tenga acceso a la estructura de carpetas de contenido que no son de Microsoft 365.

- Instale AzCopy, que puede hacer desde [Introducción a azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>Cargar contenido que no es de Microsoft 365 en una investigación de datos

1. Abra **investigaciones de datos** y vaya a la investigación en la que se cargarán los datos que no son de Microsoft 365.  Haga clic en la pestaña **evidencia** y, a continuación, seleccione el conjunto de evidencias en el que desea cargar los datos.  Si aún no ha creado un conjunto de evidencias, puede hacerlo ahora.  Por último, haga clic en **administrar evidencias** y **Ver cargas** en la sección de datos

2. Haga clic en el botón **cargar archivos** para iniciar el Asistente para importación de datos que no es de Microsoft 365.

![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. El primer paso del asistente simplemente prepara un BLOB seguro de Azure para los archivos que se van a cargar.  Una vez completada la preparación, haga clic en el botón **cargar archivos** .

![Preparación para la importación de datos que no son de Microsoft 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. En el paso **cargar archivos** , especifique la **ruta de acceso a la ubicación de los archivos**, aquí es donde se ubican los datos que no son de Microsoft 365 que tiene previsto importar.  La configuración de la ubicación correcta asegura que el comando AzCopy se haya actualizado correctamente.

> [!NOTE]
> Si todavía no ha instalado AzCopy, puede hacerlo desde aquí: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. Copie el comando predefinido haciendo clic en el vínculo **copiar al portapapeles** . Inicie un símbolo del sistema de Windows, pegue el comando y presione Entrar.  Los archivos se cargarán en el almacenamiento de blobs seguro de Azure para el paso siguiente.

![Cargar archivos para importación de datos que no son de Microsoft 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Usar AzCopy para importar datos que no son de Microsoft 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Por último, vuelva al cumplimiento de & de seguridad y haga clic en el botón **siguiente: procesar archivos** .  Esto inicia el procesamiento, la extracción de texto y la indización de los archivos cargados.  Puede realizar un seguimiento del progreso del procesamiento aquí o en la pestaña **trabajos** .  Una vez completados, los nuevos archivos están disponibles en el conjunto de evidencias.  Una vez finalizado el procesamiento, puede descartar el asistente.

![Archivos de proceso de importación que no son de Microsoft 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

