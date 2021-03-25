---
title: Sincronizar certificados de usuario con Office 365 para S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a publicar los certificados adecuados en Office 365 antes de enviar mensajes protegidos por S/MIME en Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207343"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizar certificados de usuario con Office 365 para S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Para que cualquier usuario pueda enviar mensajes protegidos por S/MIME en Exchange Online, se deben configurar los certificados adecuados. Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Para sincronizar los certificados que admiten S/MIME

Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory. Para obtener más información, vea [Información general de Servicios de certificados de Active Directory](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Después de publicar los certificados, use la herramienta Azure AD Connect para sincronizar los datos de usuario de su entorno de Exchange local con Office 365. Para obtener más información sobre este proceso, vea [Sincronización de Azure AD Connect: Comprender y personalizar la sincronización.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

Junto con la sincronización de otros datos de directorio, para fines S/MIME, la herramienta sincronizará los atributos  **userCertificate** y **userSMIMECertificate** para cada objeto de usuario de modo que los datos se puedan usar para firmar y cifrar mensajes.

## <a name="more-information"></a>Más información

[S/MIME para la firma y cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)

[¿Qué es Azure AD Connect?](/azure/active-directory/hybrid/whatis-azure-ad-connect)