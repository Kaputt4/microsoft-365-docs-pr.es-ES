---
title: Menores y adquisición de complementos desde la tienda
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
description: Obtenga información sobre las regulaciones generales del Reglamento de protección de datos (RGPD) que rigen los datos personales de los menores.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306556"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores y adquisición de complementos desde la tienda

El Reglamento General de protección de datos (RGPD) es un Reglamento de la Unión Europea que se hace efectivo el 25 de mayo de 2018. Proporciona a los usuarios derechos y protección de sus datos. Uno de los aspectos de la RGPD es que los menores no pueden tener sus datos personales enviados a las partes que su padre o tutor no han aprobado. La antigüedad específica definida como un menor depende de la región en la que se encuentra la persona.
  
Las regiones que tienen regulaciones legales sobre el consentimiento paterno incluyen los Estados Unidos, Corea del sur, Reino Unido y la Unión Europea. Para esas regiones, un menor se bloquea (a través de Azure Active Directory) desde la obtención de nuevos complementos de Office de la tienda y la ejecución de complementos adquiridos anteriormente. En el caso de los países sin las regulaciones legales, no habrá ninguna restricción de descarga.
  
Un usuario se determina como secundario en función de los datos especificados en Azure Active Directory. El administrador de la organización es responsable de declarar el grupo de edad legal y el consentimiento paterno para ese usuario.
  
Si el tutor o el tutor consiente a un menor con un complemento específico, el administrador de la organización puede usar la implementación centralizada para implementar ese complemento en todos los menores que tengan el consentimiento del usuario.
  
Para que RGPD cumpla con los menores, debe asegurarse de que una de las siguientes compilaciones de Office está implementada en su centro educativo o de organización.
 
 **Para Word, Excel, PowerPoint y Project**: 

|**Plataforma** <br/> |**Número de compilación** <br/> |
|:-----|:-----|
|Microsoft 365 apps for Enterprise (canal actual)  <br/> |9001,2138   <br/> |
|Microsoft 365 aplicaciones para empresas (canal empresarial semestral)  <br/> |8431,2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office para la Web  <br/> |N/D  <br/> |
   
 **Para Outlook**: 
  
|**Plataforma** <br/> |**Número de compilación** <br/> |
|:-----|:-----|
|Outlook 2016 para Windows (MSI)  <br/> |Compilación sin TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisitos de Office 2013**
  
Word, Excel y PowerPoint 2013 para Windows admitirán las mismas comprobaciones menores si la biblioteca de autenticación de Active Directory (ADAL) está habilitada. Hay dos opciones para el cumplimiento normativo, tal como se explica a continuación.
  
- **Habilitar Adal**. En este artículo se explica cómo habilitar ADAL para Office 2013: [usar la autenticación moderna de Microsoft 365 con clientes de Office](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).<br/>También debe configurar las claves del registro para habilitar ADAL, tal y como se explica en [enable Modern Authentication for Office 2013 on Windows Devices](../security-and-compliance/enable-modern-authentication.md).<br/>Además, debe instalar las siguientes actualizaciones de abril para Office 2013:
    
  - [Descripción de la actualización de seguridad para Office 2013:10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, actualización para Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **No habilite Adal**. Si no puede habilitar ADAL en Office 2013, nuestra recomendación es usar la Directiva de grupo para desactivar la tienda para los clientes de Office. [Aquí](https://technet.microsoft.com/library/cc178992.aspx)encontrará información sobre cómo desactivar la aplicación para la configuración de Office.

## <a name="related-articles"></a>Artículos relacionados

[Implementar complementos en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Administrar complementos en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
