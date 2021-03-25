---
title: Evaluar el acceso controlado a carpetas
description: Vea cómo el acceso controlado a carpetas puede ayudar a proteger los archivos de que las aplicaciones malintencionadas cambien.
keywords: Protección contra vulnerabilidades, windows 10, Windows Defender, ransomware, proteger, evaluar, probar, probar, probar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218753"
---
# <a name="evaluate-controlled-folder-access"></a><span data-ttu-id="ec449-104">Evaluar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="ec449-104">Evaluate controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec449-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ec449-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec449-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ec449-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="ec449-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec449-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="ec449-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ec449-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ec449-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ec449-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="ec449-110">[El acceso controlado](controlled-folders.md) a carpetas es una característica que ayuda a proteger los documentos y archivos contra modificaciones de aplicaciones sospechosas o malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="ec449-110">[Controlled folder access](controlled-folders.md) is a feature that helps protect your documents and files from modification by suspicious or malicious apps.</span></span> <span data-ttu-id="ec449-111">El acceso controlado a carpetas es compatible con clientes de Windows Server 2019 y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ec449-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="ec449-112">Es especialmente útil para ayudar a proteger contra [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) que intenta cifrar los archivos y retenerlos como rehenes.</span><span class="sxs-lookup"><span data-stu-id="ec449-112">It is especially useful in helping protect against [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) that attempts to encrypt your files and hold them hostage.</span></span>

<span data-ttu-id="ec449-113">Este artículo le ayuda a evaluar el acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="ec449-113">This article helps you evaluate controlled folder access.</span></span> <span data-ttu-id="ec449-114">Explica cómo habilitar el modo de auditoría para que pueda probar la característica directamente en su organización.</span><span class="sxs-lookup"><span data-stu-id="ec449-114">It explains how to enable audit mode so you can test the feature directly in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="ec449-115">También puede visitar el sitio web de escenario de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="ec449-115">You can also visit the Microsoft Defender for Endpoint demo scenario website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

## <a name="use-audit-mode-to-measure-impact"></a><span data-ttu-id="ec449-116">Usar el modo de auditoría para medir el impacto</span><span class="sxs-lookup"><span data-stu-id="ec449-116">Use audit mode to measure impact</span></span>

<span data-ttu-id="ec449-117">Habilite el acceso controlado a carpetas en  modo auditoría para ver un registro de lo que hubiera ocurrido si se hubiera habilitado completamente.</span><span class="sxs-lookup"><span data-stu-id="ec449-117">Enable the controlled folder access in audit mode to see a record of what *would* have happened if it was fully enabled.</span></span> <span data-ttu-id="ec449-118">Pruebe cómo funcionará la característica en su organización para asegurarse de que no afecta a las aplicaciones de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="ec449-118">Test how the feature will work in your organization to ensure it doesn't affect your line-of-business apps.</span></span> <span data-ttu-id="ec449-119">También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos suelen producirse durante un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="ec449-119">You can also get an idea of how many suspicious file modification attempts generally occur over a certain period of time.</span></span>

<span data-ttu-id="ec449-120">Para habilitar el modo de auditoría, use el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ec449-120">To enable audit mode, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> <span data-ttu-id="ec449-121">Si quieres auditar completamente cómo funcionará el acceso controlado a carpetas en tu organización, tendrás que usar una herramienta de administración para implementar esta configuración en dispositivos de tus redes.</span><span class="sxs-lookup"><span data-stu-id="ec449-121">If you want to fully audit how controlled folder access will work in your organization, you'll need to use a management tool to deploy this setting to devices in your network(s).</span></span>
<span data-ttu-id="ec449-122">También puedes usar la directiva de grupo, Intune, la administración de dispositivos móviles (MDM) o Microsoft Endpoint Manager para configurar e implementar la configuración, como se describe en el tema principal acceso controlado a [carpetas](controlled-folders.md).</span><span class="sxs-lookup"><span data-stu-id="ec449-122">You can also use Group Policy, Intune, mobile device management (MDM), or Microsoft Endpoint Manager to configure and deploy the setting, as described in the main [controlled folder access topic](controlled-folders.md).</span></span>

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="ec449-123">Revisar eventos de acceso controlado a carpetas en el Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="ec449-123">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="ec449-124">Los siguientes eventos de acceso controlado a carpetas aparecen en el Visor de eventos de Windows en la carpeta Microsoft/Windows/Windows Defender/Operational.</span><span class="sxs-lookup"><span data-stu-id="ec449-124">The following controlled folder access events appear in Windows Event Viewer under Microsoft/Windows/Windows Defender/Operational folder.</span></span>

<span data-ttu-id="ec449-125">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec449-125">Event ID</span></span> | <span data-ttu-id="ec449-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec449-126">Description</span></span>
-|-
 <span data-ttu-id="ec449-127">5007</span><span class="sxs-lookup"><span data-stu-id="ec449-127">5007</span></span> | <span data-ttu-id="ec449-128">Evento cuando se cambia la configuración</span><span class="sxs-lookup"><span data-stu-id="ec449-128">Event when settings are changed</span></span>
 <span data-ttu-id="ec449-129">1124</span><span class="sxs-lookup"><span data-stu-id="ec449-129">1124</span></span> | <span data-ttu-id="ec449-130">Evento de acceso a carpetas controladas auditada</span><span class="sxs-lookup"><span data-stu-id="ec449-130">Audited controlled folder access event</span></span>
 <span data-ttu-id="ec449-131">1123</span><span class="sxs-lookup"><span data-stu-id="ec449-131">1123</span></span> | <span data-ttu-id="ec449-132">Evento de acceso controlado a carpetas bloqueadas</span><span class="sxs-lookup"><span data-stu-id="ec449-132">Blocked controlled folder access event</span></span>

> [!TIP]
> <span data-ttu-id="ec449-133">Puedes configurar una suscripción de [reenvío de eventos de Windows](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) para recopilar los registros de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="ec449-133">You can configure a [Windows Event Forwarding subscription](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) to collect the logs centrally.</span></span> 

## <a name="customize-protected-folders-and-apps"></a><span data-ttu-id="ec449-134">Personalizar aplicaciones y carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="ec449-134">Customize protected folders and apps</span></span>

<span data-ttu-id="ec449-135">Durante la evaluación, es posible que quieras agregar a la lista de carpetas protegidas o permitir que determinadas aplicaciones modifiquen archivos.</span><span class="sxs-lookup"><span data-stu-id="ec449-135">During your evaluation, you may wish to add to the list of protected folders, or allow certain apps to modify files.</span></span>

<span data-ttu-id="ec449-136">Vea [Proteger carpetas](controlled-folders.md) importantes con acceso controlado a carpetas para configurar la característica con herramientas de administración, como la directiva de grupo, PowerShell y los proveedores de servicios de configuración mdm (CSP).</span><span class="sxs-lookup"><span data-stu-id="ec449-136">See [Protect important folders with controlled folder access](controlled-folders.md) for configuring the feature with management tools, including Group Policy, PowerShell, and MDM configuration service providers (CSPs).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec449-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec449-137">See also</span></span>

* [<span data-ttu-id="ec449-138">Proteger carpetas importantes con acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="ec449-138">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="ec449-139">Evaluar Microsoft Defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ec449-139">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
* [<span data-ttu-id="ec449-140">Usar el modo de auditoría</span><span class="sxs-lookup"><span data-stu-id="ec449-140">Use audit mode</span></span>](audit-windows-defender.md)
