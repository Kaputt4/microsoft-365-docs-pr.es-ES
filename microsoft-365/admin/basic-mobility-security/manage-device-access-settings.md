---
title: Administrar la configuración de acceso a dispositivos en la movilidad y la seguridad básicas
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La movilidad y la seguridad básica pueden ayudarle a proteger y administrar dispositivos móviles.
ms.openlocfilehash: e66465d312c4268aca82677fa4e517aaeb822ce3
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430296"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a>Administrar la configuración de acceso a dispositivos en la movilidad y la seguridad básicas

Si está usando la movilidad y la seguridad básicas, puede haber dispositivos que no puede administrar con la movilidad y la seguridad básicas. Si es así, debe bloquear el acceso a la aplicación de Exchange ActiveSync al correo electrónico de Microsoft 365 para dispositivos móviles que no son compatibles con la movilidad y la seguridad básicas. Esto ayuda a proteger la información de la organización en más dispositivos.

Siga estos pasos:

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.
    
2. En el explorador, escriba:  [https://protection.office.com](https://protection.office.com/) .    

    >[!IMPORTANT]
    >Si esta es la primera vez que usa MDM para Microsoft 365 Business Standard, actívelo aquí: activar la [Administración de dispositivos móviles](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Una vez que la haya activado, administre los dispositivos con [Office 365 Security & Compliance](https://protection.office.com/).

3. Vaya a prevención de pérdida de datos >directivas de dispositivo de  **Administración de dispositivos**   >  **Device policies**y seleccione **administrar la configuración de acceso a dispositivos en toda la organización**.
    
4. Seleccione **bloquear**.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Casilla de verificación de acceso básico a bloque de seguridad y movilidad":::

5. Seleccione **Guardar**. 

Para obtener información sobre los dispositivos compatibles con la movilidad y la seguridad básica, consulte [capacidades básicas de movilidad y seguridad](capabilities.md).