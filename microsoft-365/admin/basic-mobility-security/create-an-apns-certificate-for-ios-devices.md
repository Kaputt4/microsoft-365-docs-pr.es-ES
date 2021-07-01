---
title: Crear certificados de APN para dispositivos iOS
f1.keywords: NOCSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Administrar dispositivos iOS en Movilidad y seguridad básicas.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228248"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear certificados de APN para dispositivos iOS

Para administrar dispositivos iOS, como iPads y iPhones, en Movilidad y seguridad básicas, crea un certificado APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el explorador, escriba  <https://protection.office.com/> .

3. Seleccione  **Prevención de pérdida de** datos Administración   >  **de** dispositivos y elija Certificado **apns para dispositivos iOS.**

4. En la página Certificado de notificación de inserción Configuración Apple, elija **Siguiente**.

5. Seleccione Descargar el archivo CSR y guarde la solicitud de firma de certificado en algún lugar del equipo que recuerde. Seleccione  **Siguiente**.

6. En la página Crear un certificado de APNs:

    1. Selecciona Apple APNS Portal para abrir el Portal de certificados de inserción de Apple.

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Seleccione  **Crear un certificado** y acepte los   Términos de uso.

    4. Vaya a la solicitud de firma de certificado que descargó en el equipo desde Microsoft 365 y seleccione **Upload**.

       Descargue el certificado apns creado por el Portal de certificados de inserción de Apple en el equipo.

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. Vuelva a Microsoft 365 y seleccione  Siguiente para llegar a la Upload de certificado   de  **APNS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione  **Finalizar**.

Para completar la configuración, vuelva al Centro de seguridad y & cumplimiento > **directivas de** seguridad   >  **Administración de**   >  **dispositivos Administrar la configuración.**
