---
title: Habilitar la característica de análisis periódica limitada de Antivirus de Microsoft Defender
description: El análisis periódico limitado te permite usar Antivirus de Microsoft Defender además de tus otros proveedores de ANTIVIRUS instalados
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 64b65363ff53773f73cbbdc33b05a0a1beaf7f92
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691248"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="dafe0-104">Usar análisis periódico limitado en Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dafe0-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dafe0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="dafe0-105">**Applies to:**</span></span>

- [<span data-ttu-id="dafe0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="dafe0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dafe0-107">El examen periódico limitado es un tipo especial de detección y corrección de amenazas que se puede habilitar cuando se instala otro producto antivirus en un dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dafe0-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="dafe0-108">Solo se puede habilitar en determinadas situaciones.</span><span class="sxs-lookup"><span data-stu-id="dafe0-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="dafe0-109">Para obtener más información sobre el examen periódico limitado y cómo funciona Antivirus de Microsoft Defender con otros productos antivirus, vea [Compatibilidad de Antivirus de Microsoft Defender.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="dafe0-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="dafe0-110">**Microsoft no recomienda usar esta característica en entornos empresariales. Esta es una característica destinada principalmente a los consumidores.**</span><span class="sxs-lookup"><span data-stu-id="dafe0-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="dafe0-111">Esta característica solo usa un subconjunto limitado de las capacidades de Antivirus de Microsoft Defender para detectar malware y no podrá detectar la mayoría de malware y software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="dafe0-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="dafe0-112">Además, las capacidades de administración e informes serán limitadas.</span><span class="sxs-lookup"><span data-stu-id="dafe0-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="dafe0-113">Microsoft recomienda a las empresas elegir su solución antivirus principal y usarla exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="dafe0-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="dafe0-114">Cómo habilitar el examen periódico limitado</span><span class="sxs-lookup"><span data-stu-id="dafe0-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="dafe0-115">De forma predeterminada, Antivirus de Microsoft Defender se habilitará en un dispositivo Windows 10 si no hay ningún otro producto antivirus instalado, o si el otro producto está des actualizado, expirado o no funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="dafe0-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="dafe0-116">Si Antivirus de Microsoft Defender está habilitado, aparecerán las opciones habituales para configurarlo en ese dispositivo:</span><span class="sxs-lookup"><span data-stu-id="dafe0-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Aplicación de Seguridad de Windows que muestra las opciones de ANTIVIRUS de Microsoft Defender, incluidas las opciones de examen, la configuración y las opciones de actualización](images/vtp-wdav.png)

<span data-ttu-id="dafe0-118">Si otro producto antivirus está instalado y funciona correctamente, Antivirus de Microsoft Defender se deshabilitará a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="dafe0-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="dafe0-119">La aplicación Seguridad de Windows cambiará la sección Protección contra **&** virus para mostrar el estado del producto ANTIVIRUS y proporcionar un vínculo a las opciones de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="dafe0-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="dafe0-120">Debajo de cualquier producto ANTIVIRUS de terceros, aparecerá un nuevo vínculo como opciones **de Antivirus de Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="dafe0-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="dafe0-121">Al hacer clic en este vínculo, se expandirá para mostrar la alternancia que habilita el examen periódico limitado.</span><span class="sxs-lookup"><span data-stu-id="dafe0-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="dafe0-122">Tenga en cuenta que la opción periódica limitada es una alternancia para habilitar o deshabilitar el examen periódico.</span><span class="sxs-lookup"><span data-stu-id="dafe0-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="dafe0-123">Al deslizar el conmutador a **On,** se mostrarán las opciones estándar de Antivirus de Microsoft Defender debajo del producto ANTIVIRUS de terceros.</span><span class="sxs-lookup"><span data-stu-id="dafe0-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="dafe0-124">La opción de examen periódico limitado aparecerá en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="dafe0-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="dafe0-125">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="dafe0-125">Related articles</span></span>

- [<span data-ttu-id="dafe0-126">Configurar la protección de comportamiento, heurística y en tiempo real</span><span class="sxs-lookup"><span data-stu-id="dafe0-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dafe0-127">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="dafe0-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)