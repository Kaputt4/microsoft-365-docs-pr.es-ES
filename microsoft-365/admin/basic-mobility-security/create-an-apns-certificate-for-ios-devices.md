---
title: Crear un certificado de APNs para dispositivos iOS
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
description: Administrar dispositivos iOS en la movilidad y la seguridad básicas.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337099"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear un certificado de APNs para dispositivos iOS

Para administrar dispositivos iOS como iPad y iPhone en Basic Mobility and Security, cree un certificado de APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.
    
2. En el explorador, escriba  [https://protection.office.com](https://protection.office.com/) .
    
3. Seleccione  **Data loss prevention**   >  **Administración de dispositivos**de prevención de pérdida de datos y elija **certificado de APNs para dispositivos iOS**.    

4. En la página Configuración del certificado de notificación de inserción de Apple, elija **siguiente**.
    
5. Seleccione descargar el archivo CSR y guardar la solicitud de firma de certificado en algún lugar del equipo que recuerde. Seleccione  **siguiente**.
    
6. En la página crear un certificado de APNs:  

    1. Seleccione portal de APNS de Apple para abrir el portal de certificados push de Apple.
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Seleccione  **crear un certificado**   y acepte los términos de uso.
    
    4. Vaya a la solicitud de firma de certificado que descargó en el equipo de Microsoft 365 y seleccione **cargar**.
    
        Descargue el certificado de APNs creado por el portal de certificados push de Apple en su equipo.
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Vuelva a Microsoft 365 y seleccione **siguiente**   para ir a la página  **cargar certificado de APNS**   .
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. Seleccione  **Finalizar**.
    
Para completar la configuración, vuelva al centro de cumplimiento de & de seguridad > **directivas de seguridad**   >  **Administración de dispositivos administración**de la   >  **configuración**.
