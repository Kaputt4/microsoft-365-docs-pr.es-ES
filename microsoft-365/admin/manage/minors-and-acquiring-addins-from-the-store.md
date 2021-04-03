---
title: Menores y adquirir complementos de la Tienda
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Obtenga información sobre los reglamentos del Reglamento general de protección de datos (RGPD) que rigen los datos personales de los menores.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580923"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores y adquirir complementos de la Tienda

El Reglamento general de protección de datos (RGPD) es un reglamento de la Unión Europea que se hace efectivo el 25 de mayo de 2018. Proporciona a los usuarios derechos y protección de sus datos. Uno de los aspectos del RGPD es que los menores no pueden enviar sus datos personales a partes que sus padres o tutores no han aprobado. La edad específica definida como un menor depende de la región donde se encuentra el individuo.
  
Las regiones que tienen regulaciones legales sobre el consentimiento paterno incluyen los Estados Unidos, Corea del Sur, el Reino Unido y la Unión Europea. Para esas regiones, se bloqueará a un menor (a través de Azure Active Directory) para que no pueda obtener nuevos complementos de Office de la Tienda y ejecutar complementos que se adquirieron anteriormente. Para los países sin regulaciones legales, no habrá restricciones de descarga.
  
Se determina que un usuario es un menor en función de los datos especificados en Azure Active Directory. El administrador de la organización es responsable de declarar el grupo de edad legal y el consentimiento paterno para ese usuario.
  
Si el padre/tutor da su consentimiento a un menor mediante un complemento específico, el administrador de la organización puede usar la implementación centralizada para implementar ese complemento en todos los menores que tengan consentimiento.
  
Para cumplir con el RGPD para menores, debe asegurarse de que una de las siguientes compilaciones de Office se implemente en su escuela o organización.
 
 **Para Word, Excel, PowerPoint y Project:** 

|**Plataforma** <br/> |**Número de compilación** <br/> |
|:-----|:-----|
|Aplicaciones de Microsoft 365 para empresas (Canal actual)  <br/> |9001.2138   <br/> |
|Aplicaciones de Microsoft 365 para empresas (Canal de empresa semianual)  <br/> |8431.2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office para la web  <br/> |N/D  <br/> |
   
 **Para Outlook**: 
  
|**Plataforma** <br/> |**Número de compilación** <br/> |
|:-----|:-----|
|Outlook 2016 para Windows (MSI)  <br/> |Compilación sin TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisitos de Office 2013**
  
Word, Excel y PowerPoint 2013 para Windows admitirán las mismas comprobaciones secundarias si la Biblioteca de autenticación de Active Directory (ADAL) está habilitada. Hay dos opciones para el cumplimiento, como se explica a continuación.
  
- **Habilitar ADAL**. En este artículo se explica cómo habilitar ADAL para Office 2013: Usar la autenticación moderna de [Microsoft 365 con clientes de Office.](../../enterprise/modern-auth-for-office-2013-and-2016.md)<br/>También debe establecer las claves del Registro para habilitar ADAL, como se explica en Habilitar la autenticación moderna para [Office 2013 en dispositivos Windows.](../security-and-compliance/enable-modern-authentication.md)<br/>Además, debe instalar las siguientes actualizaciones de abril para Office 2013:
    
  - [Descripción de la actualización de seguridad de Office 2013: 10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, actualización para Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **No habilite a ADAL**. Si no puede habilitar ADAL en Office 2013, nuestra recomendación es usar la directiva de grupo para desactivar la Tienda para los clientes de Office. La información sobre cómo desactivar la configuración de la aplicación para Office se encuentra [aquí.](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))

## <a name="related-articles"></a>Artículos relacionados

[Implementar complementos en el centro de administración](./manage-deployment-of-add-ins.md)

[Administrar complementos en el centro de administración](./manage-addins-in-the-admin-center.md)
