---
title: Crear certificados de APN para dispositivos iOS
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Para administrar iOS dispositivos como iPads y iPhone en Basic Mobility and Security, empiece por crear un certificado APNs.
ms.openlocfilehash: 8bcbcdeac9f1cadd945c3f7c44e9192d57db7c82
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "65435797"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Crear certificados de APN para dispositivos iOS

Para administrar iOS dispositivos como iPads y iPhone en Basic Mobility and Security, cree un certificado APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el explorador, escriba <https://protection.office.com/>.

3. Seleccione **Data loss prevention** **Device management (Administración de** dispositivos de prevención \> de pérdida de datos) y elija **APNs Certificate for iOS devices (Certificado de APNs para dispositivos iOS**).

4. En la página Configuración certificado de notificación push de Apple, elija **Siguiente**.

5. Seleccione Descargar el archivo CSR y guarde la solicitud de firma de certificado en algún lugar del equipo que recuerde. Seleccione **Siguiente**.

6. En la página Crear un certificado APNs:

    1. Select Apple APNS Portal to open the Apple Push Certificates Portal. 

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Seleccione **Crear un certificado** y acepte los Términos de uso.

    4. Vaya a la solicitud de firma de certificado que descargó en el equipo desde Microsoft 365 y seleccione **Upload**.

       Descargue el certificado APNs creado por el portal de certificados push de Apple en el equipo.

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. Volver para Microsoft 365 y seleccione **Siguiente** para acceder a la página **Upload certificado DE APNS**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione **Finalizar**.

Para completar la configuración, vuelva a las directivas de seguridad de Security & Compliance Center \> **Administración** \> **de** \> **dispositivos Administración de la configuración**.
