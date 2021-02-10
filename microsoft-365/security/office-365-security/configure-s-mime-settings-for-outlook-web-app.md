---
title: 'Configuración de S/MIME: Exchange Online para Outlook en la Web'
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
description: Breve descripción de lo que los administradores de Exchange Online deben hacer para ver y configurar la configuración de S/MIME en Outlook en la Web en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165684"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="87ca3-103">Configurar las opciones de S/MIME en Exchange Online para Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="87ca3-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="87ca3-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="87ca3-104">**Applies to**</span></span>
- [<span data-ttu-id="87ca3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="87ca3-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="87ca3-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="87ca3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="87ca3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87ca3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="87ca3-108">Como administrador de Exchange Online, puede configurar Outlook en la Web (anteriormente conocido como Outlook Web App) para permitir el envío y recepción de mensajes protegidos por S/MIME.</span><span class="sxs-lookup"><span data-stu-id="87ca3-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="87ca3-109">Use los cmdlets **Get-SmimeConfig** y **Set-SmimeConfig** para ver y administrar esta característica en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87ca3-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="87ca3-110">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="87ca3-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="87ca3-111">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) y [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="87ca3-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="87ca3-112">Consideraciones para el nuevo Microsoft Edge (basado en Chromium)</span><span class="sxs-lookup"><span data-stu-id="87ca3-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="87ca3-113">Para usar S/MIME en Outlook en la web en el nuevo explorador web [de Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) usted (u otro administrador) debe establecer y configurar la directiva de explorador de Microsoft Edge denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en el nuevo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="87ca3-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="87ca3-114">El valor de directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="87ca3-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="87ca3-115">Además, tenga en cuenta que la aplicación de esta directiva requiere dispositivos unidos a un dominio o unidos a Azure AD, por lo que el uso de S/MIME en el nuevo explorador Microsoft Edge requiere efectivamente dispositivos unidos a un dominio o unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="87ca3-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="87ca3-116">Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="87ca3-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="87ca3-117">Este paso es un requisito previo para usar el nuevo Microsoft Edge; no reemplaza el control S/MIME que instalan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="87ca3-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="87ca3-118">Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la Web durante el primer uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="87ca3-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="87ca3-119">O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga para el control.</span><span class="sxs-lookup"><span data-stu-id="87ca3-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="87ca3-120">Consideraciones para Chrome</span><span class="sxs-lookup"><span data-stu-id="87ca3-120">Considerations for Chrome</span></span>

<span data-ttu-id="87ca3-121">Para usar S/MIME en Outlook en la Web en el explorador web Google Chrome, usted (u otro administrador) debe establecer y configurar la directiva chromium denominada **ExtensionInstallForcelist** para instalar la extensión Microsoft S/MIME en Chrome.</span><span class="sxs-lookup"><span data-stu-id="87ca3-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="87ca3-122">El valor de directiva es `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="87ca3-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="87ca3-123">Además, tenga en cuenta que la aplicación de esta directiva requiere equipos unidos a un dominio, por lo que el uso de S/MIME en Chrome requiere equipos unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="87ca3-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="87ca3-124">Para obtener más información **acerca de la directiva ExtensionInstallForcelist,** vea [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="87ca3-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="87ca3-125">Este paso es un requisito previo para usar Chrome; no reemplaza el control S/MIME que instalan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="87ca3-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="87ca3-126">Se pide a los usuarios que descarguen e instalen el control S/MIME en Outlook en la Web durante el primer uso de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="87ca3-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="87ca3-127">O bien, los usuarios pueden ir de forma proactiva a **S/MIME** en su configuración de Outlook en la web para obtener el vínculo de descarga para el control.</span><span class="sxs-lookup"><span data-stu-id="87ca3-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="87ca3-128">Más información</span><span class="sxs-lookup"><span data-stu-id="87ca3-128">For more information</span></span>

[<span data-ttu-id="87ca3-129">S/MIME para la firma y el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="87ca3-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
