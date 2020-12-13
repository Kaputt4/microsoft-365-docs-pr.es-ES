---
title: Importar contenido que no es de Microsoft 365 para el análisis avanzado de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Pasos para importar contenido que no está almacenado en Microsoft 365 en un BLOB de Azure para que se pueda analizar con AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662905"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importar contenido que no es de Microsoft 365 para el análisis avanzado de exhibición de documentos electrónicos (Classic)

No todos los documentos que puede que necesite analizar con eDiscovery avanzado residirán en Microsoft 365. Con la característica de importación de contenido que no es de Microsoft 365 en eDiscovery avanzado, puede cargar documentos que no vivan en Microsoft 365 (excepto los archivos PST) en un caso vinculado al BLOB de Azure Storage y analizarlos con la exhibición avanzada de documentos electrónicos. En este procedimiento se muestra cómo traer documentos que no son de Microsoft 365 en eDiscovery avanzado para su análisis.
  
> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Puede adquirir una suscripción de complemento de almacenamiento de datos de eDiscovery avanzada para el contenido que no es de Microsoft 365. Esto está disponible exclusivamente para el contenido que se va a analizar con la exhibición avanzada de documentos electrónicos. Siga los pasos que se indican en [comprar o editar un complemento para Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) y compre el complemento de almacenamiento avanzado de eDiscovery. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para cargar contenido no de Office 365

El uso de la característica cargar no de Office 365 tal y como se describe en este procedimiento requiere que tenga:
  
- Una suscripción a Office 365 E3 con Advanced Compliance Add-on o E5.
    
- Todos los custodios cuyo contenido que no pertenezca a Office 365 se cargarán deben tener E3 con las licencias del complemento de cumplimiento avanzado o E5.
    
- Un caso de eDiscovery existente.
    
- Todos los archivos para carga recopilados en carpetas en las que hay una carpeta por custodio y el nombre de las carpetas se encuentran en este formato  *alias@domainname*  . Los  *alias@domainname*  deben ser usuarios alias y dominio Office 365. Puede recopilar todas las carpetas de  *alias@domainname*  en una carpeta raíz. La carpeta raíz solo puede contener las carpetas  *alias@domainname*  , no debe haber archivos sueltos en la carpeta raíz.
    
- Una cuenta que sea administrador de exhibición de documentos electrónicos o administrador de exhibición de documentos electrónicos.
    
- [Herramientas de almacenamiento de Microsoft Azure](https://aka.ms/downloadazcopy) instaladas en un equipo que tiene acceso a la estructura de carpetas de contenido no Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Cargar contenido no de Office 365 en eDiscovery avanzado


1. Como administrador de eDiscovery o administrador de exhibición de documentos electrónicos, Abra **eDiscovery** y abra el caso en el que se cargarán los datos que no son de Office 365. Si necesita crear un caso, consulte [administrar casos de eDiscovery en el &amp; centro de seguridad y cumplimiento](ediscovery-cases.md).
    
2. Haga clic en **cambiar a exhibición avanzada de** documentos electrónicos.

3. Seleccione **Review sets** en el menú.

4. Seleccione un conjunto de revisiones existente o elija **Agregar conjunto de revisión**.

5. Seleccione **administrar conjunto de revisión**.

6. En la tarjeta de datos que no son de Office 365, seleccione **Ver cargas**.

7. Elija **cargar archivos** para iniciar el Asistente para carga de archivos.

8. La primera pestaña es **1. Paso de preparación**. Seleccione **siguiente: cargar archivos**.

9. En la **2. Ficha cargar archivos** se le pedirá que descargue AzCopy.exe si todavía no lo ha hecho y, a continuación, para proporcionar la ruta de acceso a la ubicación del archivo. Por ejemplo, le `C:\Upload`  dará el comando para ejecutar AzCopy.exe. Con el `C:\Upload` , verá:

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. Abra una ventana de símbolo del sistema y ejecute el comando AzCopy.exe para importar los datos en Azure. Una vez que haya cargado todos los datos, seleccione **siguiente: procesar archivos**.

11. La siguiente ficha es **3. Procese los archivos** en los que verá los custodios que tienen datos asociados y también le mostrarán el progreso de los datos que se van a importar.
        
    Para obtener más información sobre la sintaxis de Azcopy, vea [transferir datos con Azcopy en Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy). 
    
    Para obtener más información sobre el procesamiento avanzado de eDiscovery, consulte [ejecutar el módulo de proceso y cargar datos en la exhibición avanzada de documentos electrónicos (Classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md). 
    
    > [!IMPORTANT]
    > Debe haber una carpeta raíz por usuario y el nombre de la carpeta debe tener el formato <b>alias@domainname</b>  . 
   
    > [!IMPORTANT]
    > Una vez que el contenedor se procesa correctamente en eDiscovery avanzado, ya no podrá agregar nuevo contenido al almacenamiento SAS en Azure. Si recopila contenido adicional y desea agregarlo al análisis de eDiscovery avanzado, debe crear un nuevo contenedor de **datos distinto de Office 365** y repetir este procedimiento. 
  
    > [!NOTE]
    > Si el contenedor  *no se procesa correctamente debido a problemas de nombres de carpeta*  y, a continuación, soluciona los problemas, deberá crear un nuevo contenedor y volver a conectar y cargar de nuevo con los procedimientos descritos en este artículo.
