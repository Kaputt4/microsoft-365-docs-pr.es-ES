---
title: Usar un código QR para iniciar sesión en las aplicaciones Outlook móviles
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Aprende a usar un código QR para autenticar y descargar Outlook móvil.
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286710"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="05f34-103">Usar un código QR para iniciar sesión en las aplicaciones Outlook móviles</span><span class="sxs-lookup"><span data-stu-id="05f34-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05f34-104">Esta característica solo está disponible para las organizaciones que han activado La versión dirigida en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05f34-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="05f34-105">Para activar la versión dirigida y obtener más información sobre cómo funciona, vea Configurar las opciones de versión estándar o [dirigida.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="05f34-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="05f34-106">Nos expandiremos a más organizaciones en las próximas semanas a través de la versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="05f34-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="05f34-107">La vista previa pública proporciona acceso anticipado a Microsoft 365 características.</span><span class="sxs-lookup"><span data-stu-id="05f34-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="05f34-108">Como administrador de Microsoft 365, puedes permitir que los usuarios inicien sesión en Outlook para la aplicación de Android o iOS en sus dispositivos móviles sin tener que escribir su nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="05f34-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="05f34-109">Al examinar un código QR, los usuarios pueden autenticarse e iniciar sesión de forma segura en Outlook móvil.</span><span class="sxs-lookup"><span data-stu-id="05f34-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="05f34-110">En Outlook en la Web otras aplicaciones de escritorio Outlook escritorio, los usuarios pueden ver notificaciones que les informan de que pueden usar Outlook en su dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="05f34-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="05f34-111">El administrador puede administrar estas notificaciones mediante Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="05f34-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="05f34-112">Si los usuarios deciden enviarse un mensaje de texto SMS para descargar la aplicación en su dispositivo móvil, aparecerá un código QR en su equipo.</span><span class="sxs-lookup"><span data-stu-id="05f34-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="05f34-113">Podrán examinar el código QR para iniciar sesión en Outlook en su teléfono o tableta.</span><span class="sxs-lookup"><span data-stu-id="05f34-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="05f34-114">Este código QR es un token de corta duración que solo se puede canjear una vez.</span><span class="sxs-lookup"><span data-stu-id="05f34-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="05f34-115">En algunos casos, los usuarios deben volver a autenticarse en su equipo para generar el código QR.</span><span class="sxs-lookup"><span data-stu-id="05f34-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="05f34-116">Usar Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="05f34-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="05f34-117">Esta característica está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="05f34-117">This feature is on by default.</span></span> <span data-ttu-id="05f34-118">Para deshabilitar esta característica, siga los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="05f34-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="05f34-119">[Conectar a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="05f34-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
2. <span data-ttu-id="05f34-120">Con PowerShell, puede deshabilitar las notificaciones que informan a los usuarios sobre el Outlook aplicaciones móviles.</span><span class="sxs-lookup"><span data-stu-id="05f34-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="05f34-121">Esto también impide que se muestra el flujo de inicio de sesión de código QR.</span><span class="sxs-lookup"><span data-stu-id="05f34-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="05f34-122">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="05f34-122">Related content</span></span>

<span data-ttu-id="05f34-123">[Configurar las opciones de versión estándar o dirigida](release-options-in-office-365.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="05f34-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="05f34-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (artículo)</span><span class="sxs-lookup"><span data-stu-id="05f34-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (article)</span></span>