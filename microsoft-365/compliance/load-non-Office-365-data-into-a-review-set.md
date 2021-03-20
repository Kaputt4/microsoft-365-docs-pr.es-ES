---
title: Cargar datos que no son de Microsoft 365 en un conjunto de opiniones
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
description: Obtenga información sobre cómo importar datos que no son de Microsoft 365 a un conjunto de revisión para su análisis en un caso de exhibición de documentos electrónicos avanzada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903506"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Cargar datos que no son de Microsoft 365 en un conjunto de opiniones

No todos los documentos que necesita analizar en eDiscovery avanzada se encuentran en Microsoft 365. Con la característica de importación de datos que no es de Microsoft 365 en eDiscovery avanzada, puede cargar documentos que no se encuentran en Microsoft 365 en un conjunto de opiniones. En este artículo se muestra cómo llevar los documentos que no son de Microsoft 365 a eDiscovery avanzado para su análisis.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para cargar contenido que no es de Office 365

El uso de la característica de carga que no sea de Microsoft 365 descrita en este artículo requiere que tenga lo siguiente:

- Todos los custodios a los que desee asociar contenido que no sea de Microsoft 365 deben tener asignada la licencia correspondiente. Para obtener más información, vea [Introducción a la exhibición de documentos electrónicos avanzada.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

- Un caso de exhibición de documentos electrónicos avanzado existente.

- Los custodios deben agregarse al caso para poder cargar y asociar los datos que no son de Microsoft 365 a ellos.

- Los datos que no son de Microsoft 365 deben ser un tipo de archivo compatible con la exhibición de documentos electrónicos avanzada. Para obtener más información, vea [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).

- Todos los archivos que se cargan en un conjunto de revisión deben estar ubicados en carpetas, donde cada carpeta está asociada con un custodiado específico. Los nombres de estas carpetas deben usar el siguiente formato de nomenclatura: *alias@domainname*. El alias@domainname debe ser el alias y el dominio de Microsoft 365 del usuario. Puede recopilar todas las alias@domainname carpetas de una carpeta raíz. La carpeta raíz solo puede contener las alias@domainname carpetas. No se admiten archivos sueltos en la carpeta raíz.

   La estructura de carpetas de los datos que no son de Microsoft 365 que desea cargar sería similar al ejemplo siguiente:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Donde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com y staci.gonzalez@contoso.com son las direcciones SMTP de los custodios en el caso.

   ![Estructura de carpetas de carga de datos que no son de Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Una cuenta que se asigna al grupo de roles administrador de exhibición de documentos electrónicos (y se agrega como administrador de exhibición de documentos electrónicos).

- La herramienta AzCopy v8.1 instalada en un equipo que tiene acceso a la estructura de carpetas de contenido que no son de Microsoft 365. Para instalar AzCopy, consulta [Transferir datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy). Asegúrese de instalar AzCopy en la ubicación predeterminada, que es **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**. Debe usar AzCopy v8.1. Es posible que otras versiones de AzCopy no funcionen al cargar datos que no son de Microsoft 365 en eDiscovery avanzada.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Cargar contenido que no es de Microsoft 365 en eDiscovery avanzado

1. Como administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos, abra eDiscovery avanzado y vaya al caso de que se cargarán los datos que no sean de Microsoft 365.  

2. Haga **clic en** Revisar conjuntos y, a continuación, seleccione el conjunto de opiniones para cargar los datos que no son de Microsoft 365.  Si no tiene un conjunto de revisión, puede crear uno. 
 
3. En el conjunto de **opiniones,** haga clic en **Administrar** conjunto de opiniones y, a continuación, haga clic en Ver cargas en el icono de datos que no es **de Microsoft 365.**

4. Haga **clic en Cargar archivos** para iniciar el Asistente para importación de datos.

   ![Cargar archivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   El primer paso del asistente prepara una ubicación segura de Azure Storage proporcionada por Microsoft para cargar los archivos.  Cuando se completa la preparación, el **botón Siguiente: Cargar archivos** se activa.

   ![Importación que no es de Microsoft 365: Preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Haga **clic en Siguiente: Cargar archivos**.

6. En la **página Cargar archivos,** haga lo siguiente:

   ![Importación que no es de Microsoft 365: Cargar archivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. En el **cuadro Ruta** de acceso a la ubicación de los archivos, compruebe o escriba la ubicación de la carpeta raíz donde ha almacenado los datos que no son de Microsoft 365 que desea cargar. Por ejemplo, para la ubicación de los archivos de ejemplo que se muestran en la sección Antes de **empezar,** escriba **%USERPROFILE\Downloads\nonO365**. Al proporcionar la ubicación correcta, se garantiza que el comando AzCopy que se muestra en el cuadro debajo de la ruta de acceso se actualice correctamente.

   b. Haga **clic en Copiar en** el Portapapeles para copiar el comando que se muestra en el cuadro.

7. Inicie un símbolo del sistema de Windows, pegue el comando que copió en el paso anterior y, a continuación, presione **Entrar** para iniciar el comando AzCopy.  Después de iniciar el comando, los archivos que no sean de Microsoft 365 se cargarán en la ubicación de Azure Storage que se preparó en el paso 4.

   ![Importación que no es de Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Como se ha indicado anteriormente, debe usar AzCopy v8.1 para usar correctamente el comando que se proporciona en la página **Cargar archivos.** Si se produce un error en el comando AzCopy proporcionado, consulte [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Vuelva al Centro de seguridad & cumplimiento y haga clic en **Siguiente: Procesar archivos** en el asistente.  Esto inicia el procesamiento, la extracción de texto y la indización de los archivos que no son de Microsoft 365 que se cargaron en la ubicación de Azure Storage.  

9. Realice un seguimiento del progreso  del procesamiento de  los archivos en la página Archivos de proceso o en la pestaña Trabajos al ver un trabajo denominado Agregar datos que no son de **Microsoft 365 a** un conjunto de opiniones.  Una vez finalizado el trabajo, los nuevos archivos estarán disponibles en el conjunto de revisión.

   ![Importación que no es de Microsoft 365: Procesar archivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Una vez finalizado el procesamiento, puede cerrar el asistente.