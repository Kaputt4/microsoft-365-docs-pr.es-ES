---
title: 'Configuración de S/MIME: Exchange Online para Outlook en la web'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descripción de lo que deben hacer los administradores de Exchange Online para ver y configurar la configuración de S/MIME en Outlook en la web en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204970"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="4b243-103">Configurar la configuración de S/MIME en Exchange Online para Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="4b243-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4b243-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="4b243-104">**Applies to**</span></span>
- [<span data-ttu-id="4b243-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4b243-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4b243-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4b243-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4b243-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b243-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4b243-108">Como administrador de Exchange Online, puede configurar Outlook en la web (anteriormente conocido como Outlook Web App) para permitir el envío y recepción de mensajes protegidos por S/MIME.</span><span class="sxs-lookup"><span data-stu-id="4b243-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="4b243-109">Use los cmdlets **Get-SmimeConfig** y **Set-SmimeConfig** para ver y administrar esta característica en PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4b243-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="4b243-110">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4b243-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="4b243-111">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) y [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="4b243-111">For detailed syntax and parameter information, see [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="4b243-112">Consideraciones para el nuevo Microsoft Edge (basado en Chromium)</span><span class="sxs-lookup"><span data-stu-id="4b243-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="4b243-113">Para usar S/MIME en Outlook en la web en el nuevo explorador web [de Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) usted (u otro administrador) debe establecer y configurar la directiva de explorador de Microsoft Edge denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en el nuevo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4b243-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="4b243-114">El valor de la directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="4b243-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="4b243-115">Y tenga en cuenta que la aplicación de esta directiva requiere dispositivos unidos a un dominio o unidos a Azure AD, por lo que el uso de S/MIME en el nuevo explorador de Microsoft Edge requiere dispositivos unidos a un dominio o unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4b243-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="4b243-116">Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="4b243-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="4b243-117">Este paso es un requisito previo para usar nuevo Microsoft Edge; no reemplaza el control S/MIME instalado por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4b243-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="4b243-118">Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante el primer uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="4b243-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="4b243-119">O bien, los usuarios pueden ir proactivamente a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.</span><span class="sxs-lookup"><span data-stu-id="4b243-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="4b243-120">Consideraciones para Chrome</span><span class="sxs-lookup"><span data-stu-id="4b243-120">Considerations for Chrome</span></span>

<span data-ttu-id="4b243-121">Para usar S/MIME en Outlook en la web en el explorador web de Google Chrome, usted (u otro administrador) debe establecer y configurar la directiva Chromium denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en Chrome.</span><span class="sxs-lookup"><span data-stu-id="4b243-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="4b243-122">El valor de la directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="4b243-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="4b243-123">Y tenga en cuenta que la aplicación de esta directiva requiere equipos unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="4b243-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="4b243-124">Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="4b243-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="4b243-125">Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME instalado por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4b243-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="4b243-126">Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la web durante el primer uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="4b243-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="4b243-127">O bien, los usuarios pueden ir proactivamente a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga del control.</span><span class="sxs-lookup"><span data-stu-id="4b243-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4b243-128">Más información</span><span class="sxs-lookup"><span data-stu-id="4b243-128">For more information</span></span>

[<span data-ttu-id="4b243-129">S/MIME para la firma y el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="4b243-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)