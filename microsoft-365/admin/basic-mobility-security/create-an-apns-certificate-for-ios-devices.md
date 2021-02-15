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
description: Administrar dispositivos iOS en movilidad y seguridad básicas.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877085"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear certificados de APN para dispositivos iOS

Para administrar dispositivos iOS, como iPad y iPhone, en Movilidad y seguridad básicas, cree un certificado APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el explorador, escriba  [https://protection.office.com](https://protection.office.com/) .

3. Seleccione  **Administración de dispositivos de prevención** de pérdida de   > datos y elija Certificado **de APNs para dispositivos iOS.** ****

4. En la página Configuración del certificado de notificación de inserción de Apple, elija **Siguiente.**

5. Seleccione Descargar el archivo CSR y guarde la solicitud de firma de certificado en algún lugar del equipo que recuerde. Seleccione  **Siguiente**.

6. En la página Crear un certificado de APNs:  

    1. Seleccione Apple APNS Portal para abrir el Portal de certificados de inserción de Apple.

    2. Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Seleccione  **Crear un certificado y** acepte los   Términos de uso.

    4. Vaya a la solicitud de firma de certificado que descargó en su equipo desde Microsoft 365 y seleccione **Cargar**.

        Descargue el certificado APNs creado por el Portal de certificados de inserción de Apple en su equipo.

       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Vuelva a Microsoft 365  y seleccione Siguiente para ir a la página de certificado   de CARGA de  **APNS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione  **Finalizar**.

Para completar la configuración, vuelva al Centro de seguridad y & cumplimiento > **directivas** de seguridad de   >  ****   >  **dispositivos Administrar la configuración.**
