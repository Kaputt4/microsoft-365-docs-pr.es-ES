---
title: Cargar datos que no son de Microsoft 365 en un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo importar datos no Microsoft 365 a un conjunto de revisión para su análisis en un Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903506"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Cargar datos que no son de Microsoft 365 en un conjunto de revisión

No todos los documentos que necesita analizar en Advanced eDiscovery se encuentran en Microsoft 365. Con la característica de importación de datos que no son de Microsoft 365 en eDiscovery avanzado, puede cargar documentos que no se encuentren en Microsoft 365 a un conjunto de revisión. En este artículo se muestra cómo llevar los documentos que no Microsoft 365 a Advanced eDiscovery para su análisis.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para cargar contenido que no Office 365 contenido

El uso de la característica de carga no Microsoft 365 descrita en este artículo requiere que tenga lo siguiente:

- Todos los custodios a los que desea asociar contenido que no Microsoft 365 deben tener asignada la licencia adecuada. Para obtener más información, vea [Introducción a Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Un caso Advanced eDiscovery existente.

- Los custodios deben agregarse al caso para poder cargar y asociar los datos que no Microsoft 365 a ellos.

- Los datos que no son de Microsoft 365 deben ser un tipo de archivo compatible con eDiscovery avanzado. Para más información, consulte [Tipos de archivo admitidos en eDiscovery avanzado](supported-filetypes-ediscovery20.md).

- Todos los archivos que se cargan en un conjunto de revisión deben encontrarse en carpetas, donde cada carpeta está asociada a un custodio específico. Los nombres de estas carpetas deben usar el siguiente formato de nomenclatura: *alias@domainname*. El alias@domainname debe ser el dominio y el alias de Microsoft 365 del usuario. Puede recopilar todas las alias@domainname carpetas de una carpeta raíz. La carpeta raíz solo puede contener las alias@domainname carpetas. No se admiten archivos sueltos en la carpeta raíz.

   La estructura de carpetas para los datos que no Microsoft 365 que desea cargar sería similar al siguiente ejemplo:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.

   ![Estructura de carpetas Microsoft 365 carga de datos no Microsoft 365 datos](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Una cuenta que se asigna al grupo de roles administrador de exhibición de documentos electrónicos (y se agrega como administrador de exhibición de documentos electrónicos).

- La herramienta AzCopy v8.1 instalada en un equipo que tiene acceso a la estructura de carpetas de contenido que no Microsoft 365 de contenido. Para instalar AzCopy, vea [Transferir datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy). Asegúrese de instalar AzCopy en la ubicación predeterminada, que es **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**. Debe usar AzCopy v8.1. Es posible que otras versiones de AzCopy no funcionen al cargar datos que no Microsoft 365 en Advanced eDiscovery.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Upload contenido no Microsoft 365 contenido en Advanced eDiscovery

1. Como administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos, abra Advanced eDiscovery y vaya al caso de que los datos no Microsoft 365 se cargarán en.  

2. Haga **clic en** Conjuntos de revisión y, a continuación, seleccione el conjunto de revisión en el que se cargarán los Microsoft 365 no seleccionados.  Si no tiene un conjunto de revisión, puede crear uno. 
 
3. En el conjunto de revisión, haga clic en **Administrar conjunto de revisión** y, después, haga clic en **Ver cargas** en el mosaico **Datos que no son de Microsoft 365**.

4. Haga clic **Cargar archivos** para iniciar el asistente para importar datos.

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   El primer paso del asistente prepara una ubicación segura de Azure Storage proporcionada por Microsoft en la que se pueden cargar los archivos.  Cuando se complete la preparación, se activará el botón **Siguiente: cargar archivos**.

   ![Importación no Microsoft 365: Preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Haga clic en **Siguiente: Cargar archivos**.

6. En la **página Upload archivos,** haga lo siguiente:

   ![Importación sin Microsoft 365: Upload archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. En el **cuadro Ruta** de acceso a la ubicación de los archivos, compruebe o escriba la ubicación de la carpeta raíz donde ha almacenado los datos que no Microsoft 365 desea cargar. Por ejemplo, para la ubicación de los archivos de ejemplo que se muestran en la sección Antes de **empezar,** escriba **%USERPROFILE\Downloads\nonO365**. Al proporcionar la ubicación correcta, se garantiza que el comando AzCopy que se muestra en el cuadro debajo de la ruta de acceso se actualice correctamente.

   b. Haga **clic en Copiar en** el Portapapeles para copiar el comando que se muestra en el cuadro.

7. Inicie un Windows de comandos, pegue el comando que copió en el paso anterior y, a continuación, presione **ENTRAR** para iniciar el comando AzCopy.  Después de iniciar el comando, los archivos que no Microsoft 365 se cargarán en la ubicación Azure Storage que se preparó en el paso 4.

   ![Importación sin Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Como se ha indicado anteriormente, debe usar AzCopy v8.1 para usar correctamente el comando que se proporciona en la **página Upload archivos.** Si se produce un error en el comando AzCopy proporcionado, consulte [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Vuelva al Centro de seguridad & cumplimiento y haga clic en **Siguiente: Procesar archivos** en el asistente.  Se iniciará el procesamiento, la extracción de texto y la indexación de los archivos que no son de Microsoft 365 y que se cargaron en la ubicación de Azure Storage.  

9. Realice un seguimiento del progreso  del procesamiento de  los archivos en la página Archivos de proceso o en la pestaña Trabajos al ver un trabajo denominado Agregar datos no Microsoft 365 a un conjunto **de revisión**.  Una vez finalizado el trabajo, los nuevos archivos estarán disponibles en el conjunto de revisión.

   ![Importación sin Microsoft 365: procesar archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Una vez finalizado el proceso, puede cerrar el asistente.