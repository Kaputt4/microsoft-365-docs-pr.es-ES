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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916459"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="6df7c-103">Sincronizar certificados de usuario con Office 365 para S/MIME</span><span class="sxs-lookup"><span data-stu-id="6df7c-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6df7c-104">Para que cualquier usuario pueda enviar mensajes protegidos por S/MIME en Exchange Online, se deben configurar los certificados adecuados.</span><span class="sxs-lookup"><span data-stu-id="6df7c-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="6df7c-105">Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6df7c-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="6df7c-106">Este certificado X.509 público debe publicarse en Office 365.</span><span class="sxs-lookup"><span data-stu-id="6df7c-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="6df7c-107">Para sincronizar los certificados que admiten S/MIME</span><span class="sxs-lookup"><span data-stu-id="6df7c-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="6df7c-108">Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6df7c-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="6df7c-109">Para obtener más información, vea [Información general de Servicios de certificados de Active Directory](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="6df7c-109">For more information, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="6df7c-110">Después de publicar los certificados, use la herramienta Azure AD Connect para sincronizar los datos de usuario de su entorno de Exchange local con Office 365.</span><span class="sxs-lookup"><span data-stu-id="6df7c-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="6df7c-111">Para obtener más información sobre este proceso, vea [Sincronización de Azure AD Connect: Comprender y personalizar la sincronización.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="6df7c-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="6df7c-112">Junto con la sincronización de otros datos de directorio, para fines S/MIME, la herramienta sincronizará los atributos  **userCertificate** y **userSMIMECertificate** para cada objeto de usuario de modo que los datos se puedan usar para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="6df7c-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="6df7c-113">Más información</span><span class="sxs-lookup"><span data-stu-id="6df7c-113">More Information</span></span>

[<span data-ttu-id="6df7c-114">S/MIME para la firma y cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="6df7c-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="6df7c-115">¿Qué es Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="6df7c-115">What is Azure AD Connect?</span></span>](/azure/active-directory/hybrid/whatis-azure-ad-connect)