---
title: Menores de edad y adquisición de complementos de la Tienda
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Obtenga información sobre las regulaciones del Reglamento general de protección de datos (RGPD) que rigen los datos personales de los menores.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306556"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores de edad y adquisición de complementos de la Tienda

El Reglamento general de protección de datos (RGPD) es un reglamento de la Unión Europea que se hace efectivo el 25 de mayo de 2018. Concede a los usuarios derechos y protección de sus datos. Uno de los aspectos del RGPD es que los menores no pueden enviar sus datos personales a las partes que sus padres o tutores no han aprobado. La edad específica definida como menor depende de la región donde se encuentra la persona.
  
Las regiones que tienen normativas legales sobre el consentimiento parental incluyen Los Estados Unidos, Corea del Sur, Reino Unido y la Unión Europea. Para esas regiones, se bloqueará a un menor (a través de Azure Active Directory) para que no pueda obtener nuevos complementos de Office de la Tienda y ejecutar complementos que se adquirieron anteriormente. Para los países sin normativas legales, no habrá restricciones de descarga.
  
Se determina que un usuario es un menor en función de los datos especificados en Azure Active Directory. El administrador de la organización es responsable de declarar el grupo de edad legal y el consentimiento parental para ese usuario.
  
Si el elemento primario/tutor da su consentimiento a un menor mediante un complemento específico, el administrador de la organización puede usar la implementación centralizada para implementar ese complemento para todos los menores que tengan consentimiento.
  
Para cumplir con el RGPD para menores, debe asegurarse de que se implemente una de las siguientes compilaciones de Office en su escuela u organización.
 
 **Para Word, Excel, PowerPoint y Project:** 

|**Plataforma** <br/> |**Número de compilación** <br/> |
|:-----|:-----|
|Aplicaciones de Microsoft 365 para empresas (Canal actual)  <br/> |9001.2138   <br/> |
|Aplicaciones de Microsoft 365 para empresas (Canal empresarial semianual)  <br/> |8431.2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office para la web  <br/> |N/D  <br/> |
   
 **Para Outlook:** 
  
|**Plataforma** <br/> |**Número de compilación** <br/> |
|:-----|:-----|
|Outlook 2016 para Windows (MSI)  <br/> |Compilación sin TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisitos de Office 2013**
  
Word, Excel y PowerPoint 2013 para Windows admitirán las mismas comprobaciones secundarias si la Biblioteca de autenticación de Active Directory (ADAL) está habilitada. Hay dos opciones de cumplimiento, como se explica a continuación.
  
- **Habilitar ADAL**. En este artículo se explica cómo habilitar ADAL para Office 2013: Usar la autenticación moderna de [Microsoft 365 con clientes de Office.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)<br/>También debe establecer las claves del Registro para habilitar ADAL, como se explica en Habilitar la autenticación moderna para [Office 2013 en dispositivos Windows.](../security-and-compliance/enable-modern-authentication.md)<br/>Además, debe instalar las siguientes actualizaciones de abril para Office 2013:
    
  - [Descripción de la actualización de seguridad de Office 2013: 10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, actualización de Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **No habilite ADAL**. Si no puede habilitar ADAL en Office 2013, le recomendamos que use la directiva de grupo para desactivar la Tienda para los clientes de Office. Aquí encontrará información sobre cómo desactivar la configuración de la aplicación para [Office.](https://technet.microsoft.com/library/cc178992.aspx)

## <a name="related-articles"></a>Artículos relacionados

[Implementar complementos en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Administrar complementos en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
