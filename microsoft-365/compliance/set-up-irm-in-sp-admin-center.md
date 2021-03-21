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
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Obtenga información sobre cómo usar SharePoint Online IRM a través de Microsoft Azure Active Directory Rights Management Services (RMS) para proteger listas y bibliotecas de documentos de SharePoint.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919406"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Configurar Information Rights Management (IRM) en el Centro de administración de SharePoint

En SharePoint Online, la protección IRM se aplica a los archivos del nivel de lista y de biblioteca. Antes de que su organización pueda usar la protección de IRM, primero debe configurar Rights Management. IRM confía en el servicio Azure Rights Management de Azure Information Protection para cifrar y asignar restricciones de uso. Algunos planes de Microsoft 365 incluyen Azure Rights Management, pero no todos. Para obtener más información, lea [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Activar el servicio IRM con el Centro de administración de SharePoint

Antes de que la organización pueda proteger las listas y bibliotecas de SharePoint con IRM, primero debe activar el servicio de Administración de derechos de la organización. Para obtener información sobre cómo [activar Azure Rights Management](/information-protection/deploy-use/activate-service). Debe usar una cuenta profesional o educativa que tenga privilegios de administrador global para habilitar el servicio de Administración de derechos. De lo contrario, no podrá usar las características de IRM con SharePoint Online.
  
Después de activar el servicio de Rights Management, inicie sesión en el Centro de administración de SharePoint para activar IRM.
  
1. Inicie sesión como administrador global o administrador de SharePoint.
    
2. Seleccione el icono del iniciador de aplicaciones ![Icono del iniciador de aplicaciones de Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) situado en la esquina superior izquierda y elija **Administración** para abrir el centro de administración de Microsoft 365. (Si no ve el icono Administrador, no tiene permisos de administrador en su organización). 
    
3. En el panel izquierdo, elija **Centros de administración de** \> **SharePoint**.
    
4. En el panel izquierdo, elija **configuración** y, a continuación, elija **la página de configuración clásica**.
    
5. En la **sección Information Rights Management (IRM),** elija Usar el servicio **IRM** especificado en la configuración y, a continuación, elija **Actualizar configuración de IRM**. Después de actualizar la configuración de IRM, los usuarios de la organización pueden empezar a usar IRM en sus listas de SharePoint y bibliotecas de documentos. Sin embargo, las opciones para hacerlo pueden tardar hasta una hora en aparecer en Configuración de biblioteca y Configuración de lista.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Listas y bibliotecas de documentos de SharePoint habilitados para IRM
<a name="__toc220831191"> </a>

Después de actualizar la configuración de IRM, los propietarios de sitios pueden proteger con IRM sus listas y bibliotecas de documentos de SharePoint. Para obtener más información, [vea Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Cuando los propietarios de sitios habilitan IRM para una lista o biblioteca, pueden proteger los tipos de archivo admitidos en esa lista o biblioteca. Cuando IRM está habilitado para una biblioteca, la administración de derechos se aplica a todos los archivos de esa biblioteca. Al habilitar IRM para una lista, la administración de derechos solo se aplica a los archivos adjuntos a los elementos de lista, no a los elementos de lista reales.
  
Cuando las personas descargan archivos en una lista o biblioteca habilitada para IRM, los archivos se cifran para que solo los usuarios autorizados puedan verlos. Cada archivo administrado por derechos también contiene una licencia de emisión que impone restricciones a las personas que ven el archivo. Entre las restricciones típicas se incluyen hacer un archivo de solo lectura, deshabilitar la copia de texto, impedir que los usuarios guarden una copia local y evitar que los usuarios impriman el archivo. Los programas cliente que pueden leer tipos de archivo compatibles con IRM usan la licencia de emisión dentro del archivo administrado por derechos para aplicar estas restricciones. Así es como un archivo administrado por derechos conserva su protección incluso después de su descarga. Para habilitar IRM en una lista o biblioteca, vea [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
No puede crear ni editar documentos en una biblioteca habilitada para IRM con Office en un explorador. En su lugar, una persona a la vez puede descargar y editar archivos cifrados por IRM. Use check-in y check-out para administrar  *la co-autoría*  o la creación entre varios usuarios. 
  
Al descargar un archivo PDF de una biblioteca protegida por IRM, Microsoft 365 crea un archivo PDF protegido. La extensión del archivo no cambiará, pero el archivo está protegido. Para ver este archivo necesitará el visor de Azure Information Protection, el cliente completo de Azure Information Protection u otra aplicación que admita la visualización de archivos PDF protegidos. 
  
SharePoint Online admite el cifrado de los siguientes tipos de archivo:
  
- PDF
    
- Los formatos de archivo 97-2003 para los siguientes Microsoft Office: Word, Excel y PowerPoint
    
- Formatos de Office Open XML para los siguientes Microsoft Office: Word, Excel y PowerPoint
    
- Formato de especificación de papel XML (XPS)
 
> [!NOTE]
> La protección de IRM no se puede aplicar a documentos protegidos (como archivos PDF firmados digitalmente), ya que SharePoint necesita abrir el documento al cargarlo. 

## <a name="next-steps"></a>Pasos siguientes
<a name="__toc220831191"> </a>

Una vez que haya habilitado IRM para SharePoint Online, puede empezar a aplicar la administración de derechos a listas y bibliotecas. Para obtener información, [vea Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
El nuevo cliente de sincronización de OneDrive para Windows ahora admite la sincronización de bibliotecas de documentos de SharePoint protegidas por IRM y ubicaciones de OneDrive (siempre que la configuración de IRM de la biblioteca no esté configurada para expirar los derechos de acceso de documentos). Para obtener más información o para empezar a implementar el nuevo cliente de sincronización, vea [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).
  
[Principio de página](set-up-irm-in-sp-admin-center.md)