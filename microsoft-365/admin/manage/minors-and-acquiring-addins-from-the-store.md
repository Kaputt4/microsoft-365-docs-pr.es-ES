---
title: Menores y adquisición de complementos de la Tienda
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Obtenga información sobre las regulaciones del Reglamento General de Protección de Datos (RGPD) que rigen los datos personales de los menores.
ms.openlocfilehash: a3effed0efb2dc03ba769dd8a9d0d8685f3b6f34
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208466"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores y adquisición de complementos de la Tienda

El Reglamento General de Protección de Datos (RGPD) es un reglamento de la Unión Europea que entrará en vigor el 25 de mayo de 2018. Proporciona a los usuarios derechos y protección de sus datos. Uno de los aspectos del RGPD es que los menores no pueden enviar sus datos personales a las partes que su padre o tutor no haya aprobado. La edad específica definida como menor depende de la región donde se encuentre el individuo.

Entre las regiones que tienen regulaciones legales sobre el consentimiento parental se incluyen la Estados Unidos, Corea del Sur, el Reino Unido y la Unión Europea. En esas regiones, se impedirá que un menor (a través de Azure Active Directory) obtenga nuevos complementos de Office de la Tienda y ejecute complementos que se adquirieron anteriormente. En el caso de los países sin regulaciones legales, no habrá restricciones de descarga.

Se determina que un usuario es menor en función de los datos especificados en Azure Active Directory. El administrador de la organización es responsable de declarar el grupo de edad legal y el consentimiento parental para ese usuario.

Si el padre/tutor da su consentimiento a un menor mediante un complemento específico, el administrador de la organización puede usar la implementación centralizada para implementar ese complemento en todos los menores que tengan consentimiento.

Para cumplir con el RGPD para los menores, debe asegurarse de que una de las siguientes compilaciones de Office se implementa en su escuela o organización.

 **Para Word, Excel, PowerPoint y Project**:

|Plataforma|Número de compilación|
|---|---|
|Aplicaciones Microsoft 365 para empresas (canal actual)|9001.2138|
|Aplicaciones Microsoft 365 para empresas (Canal empresarial semestral)|8431.2159|
|Office 2016 para Windows|16.0.4672.1000|
|Office 2013 para Windows|15.0.5023.1000|
|Office 2016 para Mac|16.11.18020200|
|Office para la web|N/D|

 **Para Outlook**:

|Plataforma|Número de compilación|
|---|---|
|Outlook 2016 para Windows (MSI)|Compilación sin TBD|
|Outlook 2016 para Windows (C2R)|16.0.9323.1000|
|Office 2016 para Mac|16.0.9318.1000|
|Outlook mobile para iOS|2.75.0|
|Outlook mobile para Android|2.2.145|
|Outlook.com|N/D|

 **Requisitos de Office 2013**

Word, Excel y PowerPoint 2013 para Windows admitirán las mismas comprobaciones secundarias si la biblioteca de autenticación de Active Directory (ADAL) está habilitada. Hay dos opciones para el cumplimiento, como se explica a continuación.

- **Habilite ADAL**. En este artículo se explica cómo habilitar ADAL para Office 2013: [Usar la autenticación moderna de Microsoft 365 con clientes de Office](../../enterprise/modern-auth-for-office-2013-and-2016.md).<br/>También debe establecer las claves del Registro para habilitar ADAL, como se explica en [Habilitación de la autenticación moderna para Office 2013 en dispositivos Windows](../security-and-compliance/enable-modern-authentication.md).<br/>Además, debe instalar las siguientes actualizaciones de abril para Office 2013:

  - [Descripción de la actualización de seguridad para Office 2013: 10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)

  - [3 de abril de 2018, actualización para Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)

- **No habilite ADAL**. Si no puede habilitar ADAL en Office 2013, nuestra recomendación es usar directiva de grupo para desactivar la Tienda para los clientes de Office. Aquí [encontrará información](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)) sobre cómo desactivar la configuración de la aplicación para Office.

## <a name="related-articles"></a>Artículos relacionados

[Implementar complementos en el centro de administración](./manage-deployment-of-add-ins.md)

[Administrar complementos en el centro de administración](./manage-addins-in-the-admin-center.md)
