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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a publicar los certificados apropiados en Office 365 antes de enviar mensajes de S/MIME protegidos en Exchange Online.
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826486"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizar certificados de usuario con Office 365 para S/MIME

Para que cualquier persona pueda enviar mensajes protegidos por S/MIME en Exchange Online, deben configurarse los certificados apropiados. Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Para sincronizar los certificados que admiten S/MIME

Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory. Para obtener más información, vea [Información general de Servicios de certificados de Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Una vez publicados los certificados, use la herramienta de Azure AD Connect para sincronizar los datos de usuario de su entorno de Exchange local con Office 365. Para obtener más información sobre este proceso, consulte [sincronización de Azure ad Connect: comprender y personalizar la sincronización](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Además de sincronizar otros datos de directorio, para fines de S/MIME, la herramienta sincronizará los atributos  **userCertificate** y **userSMIMECertificate** para cada objeto de usuario, de modo que los datos puedan usarse para firmar y cifrar mensajes.

## <a name="more-information"></a>Más información

[S/MIME para la firma y cifrado de mensajes](s-mime-for-message-signing-and-encryption.md)

[¿Qué es Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
