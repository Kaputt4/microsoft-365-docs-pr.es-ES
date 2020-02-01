---
title: Sincronizar certificados de usuario con Office 365 para S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Antes de poder enviar mensajes protegidos por S/MIME, deben configurarse los certificados apropiados. Para poder enviar mensajes cifrados mediante Exchange Online, el programa de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje. Este certificado X.509 público debe publicarse en Office 365.
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598197"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="a9ba7-105">Sincronizar certificados de usuario con Office 365 para S/MIME</span><span class="sxs-lookup"><span data-stu-id="a9ba7-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="a9ba7-106">Para que cualquier persona pueda enviar mensajes protegidos por S/MIME en Exchange Online, deben configurarse los certificados apropiados.</span><span class="sxs-lookup"><span data-stu-id="a9ba7-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="a9ba7-107">Para enviar mensajes cifrados a través de Exchange Online, la aplicación de correo electrónico del remitente usa el certificado público del destinatario para cifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a9ba7-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="a9ba7-108">Este certificado X.509 público debe publicarse en Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9ba7-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="a9ba7-109">Para sincronizar los certificados que admiten S/MIME</span><span class="sxs-lookup"><span data-stu-id="a9ba7-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="a9ba7-110">Para comenzar a configurar S/MIME, emita los certificados y publíquelos en sus Servicios de directorio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9ba7-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="a9ba7-111">Para obtener más información, vea [Información general de Servicios de certificados de Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="a9ba7-111">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="a9ba7-112">Una vez publicados los certificados, use la herramienta de Azure AD Connect para sincronizar los datos de usuario de su entorno de Exchange local con Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9ba7-112">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="a9ba7-113">Para obtener más información sobre este proceso, consulte [sincronización de Azure ad Connect: comprender y personalizar la sincronización](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="a9ba7-113">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="a9ba7-114">Además de sincronizar otros datos de directorio, para fines de S/MIME, la herramienta sincronizará los atributos **userCertificate** y **userSMIMECertificate** para cada objeto de usuario, de modo que los datos puedan usarse para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a9ba7-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="a9ba7-115">Más información</span><span class="sxs-lookup"><span data-stu-id="a9ba7-115">More Information</span></span>

[<span data-ttu-id="a9ba7-116">S/MIME para la firma y cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="a9ba7-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="a9ba7-117">¿Qué es Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="a9ba7-117">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
