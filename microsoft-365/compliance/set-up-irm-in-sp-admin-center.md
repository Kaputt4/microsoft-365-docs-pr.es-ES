---
title: Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Obtenga información sobre cómo usar IRM de SharePoint Online a través de Microsoft Azure Active Directory Rights Management Services (RMS) para proteger las listas de SharePoint y las bibliotecas de documentos.
ms.collection:
- tier3
- purview-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.openlocfilehash: b002cc58192b5bed9799bdddaaad09d82cc0101b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631796"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint

En SharePoint Online, la protección IRM se aplica a los archivos del nivel de lista y de biblioteca. Antes de que su organización pueda usar la protección de IRM, primero debe configurar Rights Management. IRM confía en el servicio Azure Rights Management de Azure Information Protection para cifrar y asignar restricciones de uso. Algunos planes de Microsoft 365 incluyen Azure Rights Management, pero no todos. Para obtener más información, consulte [Cómo Azure Rights Management las aplicaciones y servicios de Office](/azure/information-protection/understand-explore/office-apps-services-support).
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Activar el servicio IRM con el Centro de administración de SharePoint

Antes de que su organización pueda proteger IRM las listas y bibliotecas de SharePoint, primero debe activar el servicio Rights Management para su organización. Para obtener información sobre cómo ver [Activación de Azure Rights Management](/information-protection/deploy-use/activate-service). Debe usar una cuenta profesional o educativa que tenga privilegios de administrador global para habilitar el servicio Rights Management. De lo contrario, no podrá usar características de IRM con SharePoint Online.
  
Después de activar el servicio Rights Management, inicie sesión en el Centro de administración de SharePoint para activar IRM.
  
1. Inicie sesión como administrador global o administrador de SharePoint.
    
2. Seleccione el icono ![del iniciador de aplicaciones Icono del iniciador de aplicaciones en Office 365.](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) en la esquina superior izquierda y elija **Administración** para abrir el Centro de administración de Microsoft 365. (Si no ve el icono de Administración, no tiene permisos de administrador en su organización). 
    
3. En el panel izquierdo, elija **Administración centros** \> centro de <a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">administración de SharePoint</a>.
    
4. En el panel izquierdo, elija **configuración** y, a continuación, elija **la página configuración clásica**.
    
5. En la sección **Information Rights Management (IRM),** elija **Usar el servicio IRM especificado en la configuración** y, a continuación, elija **Actualizar configuración de IRM**. Después de actualizar la configuración de IRM, los usuarios de su organización pueden empezar a usar IRM en sus listas de SharePoint y bibliotecas de documentos. Sin embargo, las opciones para hacerlo pueden tardar hasta una hora en aparecer en Configuración de biblioteca y Configuración de lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Listas y bibliotecas de documentos de SharePoint habilitadas para IRM
<a name="__toc220831191"> </a>

Después de actualizar la configuración de IRM, los propietarios del sitio pueden proteger IRM sus listas de SharePoint y bibliotecas de documentos. Para obtener más información, vea [Aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
Cuando los propietarios del sitio habilitan IRM para una lista o biblioteca, pueden proteger los tipos de archivo admitidos en esa lista o biblioteca. Cuando IRM está habilitado para una biblioteca, rights management se aplica a todos los archivos de esa biblioteca. Al habilitar IRM para una lista, rights management solo se aplica a los archivos adjuntos a elementos de lista, no a los elementos de lista reales.
  
Cuando los usuarios descargan archivos en una lista o biblioteca habilitada para IRM, los archivos se cifran para que solo los usuarios autorizados puedan verlos. Cada archivo administrado con derechos también contiene una licencia de emisión que impone restricciones a las personas que ven el archivo. Entre las restricciones típicas se incluyen la realización de un archivo de solo lectura, la deshabilitación de la copia de texto, la prevención de que los usuarios guarden una copia local e impedir que los usuarios impriman el archivo. Los programas cliente que pueden leer tipos de archivo compatibles con IRM usan la licencia de emisión dentro del archivo administrado por derechos para aplicar estas restricciones. Así es como un archivo administrado con derechos conserva su protección incluso después de descargarlo. Para habilitar IRM en una lista o biblioteca, consulte [Aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
No se pueden crear ni editar documentos en una biblioteca habilitada para IRM mediante Office en un explorador. En su lugar, una persona a la vez puede descargar y editar archivos cifrados con IRM. Use la protección y el desproteger para administrar la  *coautoría* o la creación entre varios usuarios. 
  
Al descargar un archivo PDF desde una biblioteca protegida por IRM, Microsoft 365 crea un archivo PDF protegido. La extensión del archivo no cambiará, pero el archivo está protegido. Para ver este archivo necesitará el visor de Azure Information Protection, el cliente completo de Azure Information Protection u otra aplicación que admita la visualización de archivos PDF protegidos.
  
SharePoint Online admite el cifrado de los siguientes tipos de archivo:
  
- PDF
    
- Los formatos de archivo 97-2003 para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formatos Open XML de Office para los siguientes programas de Microsoft Office: Word, Excel y PowerPoint
    
- Formato de especificación de papel XML (XPS)
 
> [!NOTE]
> La protección de IRM no se puede aplicar a documentos protegidos (como archivos PDF firmados digitalmente), ya que SharePoint necesita abrir el documento al cargarlo. 

## <a name="next-steps"></a>Pasos siguientes
<a name="__toc220831191"> </a>

Una vez que haya habilitado IRM para SharePoint Online, puede empezar a aplicar la administración de derechos a listas y bibliotecas. Para obtener información, consulte [Aplicar Information Rights Management a una lista o biblioteca](apply-irm-to-a-list-or-library.md).
  
El nuevo cliente de Sincronización de OneDrive para Windows ahora admite la sincronización de bibliotecas de documentos de SharePoint protegidas por IRM y ubicaciones de OneDrive (siempre y cuando la configuración de IRM para la biblioteca no esté establecida para expirar los derechos de acceso a documentos). Para obtener más información, o para empezar a implementar el nuevo cliente de sincronización, consulte [Implementación del nuevo cliente de Sincronización de OneDrive para Windows](/onedrive/deploy-on-windows).
  
[Principio de página](set-up-irm-in-sp-admin-center.md)
