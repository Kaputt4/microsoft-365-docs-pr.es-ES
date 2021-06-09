---
title: Crear indicadores basados en certificados
ms.reviewer: ''
description: Cree indicadores basados en certificados que definan la detección, prevención y exclusión de entidades.
keywords: ioc, certificate, certificates, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845459"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="e6157-104">Crear indicadores basados en certificados</span><span class="sxs-lookup"><span data-stu-id="e6157-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e6157-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e6157-105">**Applies to:**</span></span>
- [<span data-ttu-id="e6157-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e6157-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e6157-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6157-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="e6157-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e6157-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e6157-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e6157-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="e6157-110">Puede crear indicadores para certificados.</span><span class="sxs-lookup"><span data-stu-id="e6157-110">You can create indicators for certificates.</span></span> <span data-ttu-id="e6157-111">Algunos casos de uso comunes incluyen:</span><span class="sxs-lookup"><span data-stu-id="e6157-111">Some common use cases include:</span></span>

- <span data-ttu-id="e6157-112">Escenarios en los que necesitas implementar [](attack-surface-reduction.md) tecnologías de [](controlled-folders.md) bloqueo, como reglas de reducción de superficie de ataque y acceso controlado a carpetas, pero necesitas permitir comportamientos de aplicaciones firmadas agregando el certificado en la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="e6157-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="e6157-113">Bloquear el uso de una aplicación firmada específica en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="e6157-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="e6157-114">Al crear un indicador para bloquear el certificado de la aplicación, Windows Defender AV evitará las ejecuciones de archivos (bloquear y corregir) y la investigación y corrección automatizadas se comportan igual.</span><span class="sxs-lookup"><span data-stu-id="e6157-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="e6157-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e6157-115">Before you begin</span></span>

<span data-ttu-id="e6157-116">Es importante comprender los siguientes requisitos antes de crear indicadores para certificados:</span><span class="sxs-lookup"><span data-stu-id="e6157-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="e6157-117">Esta característica está disponible si su organización usa Antivirus de Windows Defender y la protección basada en la nube está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e6157-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="e6157-118">Para obtener más información, vea [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="e6157-118">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="e6157-119">La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.</span><span class="sxs-lookup"><span data-stu-id="e6157-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="e6157-120">Compatible con máquinas de Windows 10, versión 1703 o posterior, Windows 2016 y 2019.</span><span class="sxs-lookup"><span data-stu-id="e6157-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="e6157-121">Las definiciones de protección contra virus y amenazas deben estar actualizadas.</span><span class="sxs-lookup"><span data-stu-id="e6157-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="e6157-122">Actualmente, esta característica admite la introducción de . CER o . Extensiones de archivo PEM.</span><span class="sxs-lookup"><span data-stu-id="e6157-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="e6157-123">Un certificado hoja válido es un certificado de firma que tiene una ruta de certificación válida y se debe encadenar a la entidad de certificación raíz (CA) de confianza de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6157-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="e6157-124">Como alternativa, se puede usar un certificado personalizado (autofirmado) siempre que sea de confianza para el cliente (el certificado de entidad de certificación raíz está instalado en la máquina local "Entidades de certificación raíz de confianza").</span><span class="sxs-lookup"><span data-stu-id="e6157-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="e6157-125">Los elementos secundarios o primarios de los EIC de certificado de permitir o bloquear no se incluyen en la funcionalidad de IoC de permitir o bloquear, solo se admiten certificados hoja.</span><span class="sxs-lookup"><span data-stu-id="e6157-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="e6157-126">Los certificados firmados por Microsoft no se pueden bloquear.</span><span class="sxs-lookup"><span data-stu-id="e6157-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="e6157-127">Cree un indicador para certificados desde la página de configuración:</span><span class="sxs-lookup"><span data-stu-id="e6157-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e6157-128">Puede tardar hasta 3 horas en crear y quitar un certificado IoC.</span><span class="sxs-lookup"><span data-stu-id="e6157-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="e6157-129">En el panel de navegación, **seleccione Configuración**  >  **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="e6157-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="e6157-130">Seleccione la **pestaña** Certificado.</span><span class="sxs-lookup"><span data-stu-id="e6157-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="e6157-131">Seleccione **Agregar indicador**.</span><span class="sxs-lookup"><span data-stu-id="e6157-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="e6157-132">Especifique los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="e6157-132">Specify the following details:</span></span>
   - <span data-ttu-id="e6157-133">Indicador: especifique los detalles de la entidad y defina la expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="e6157-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="e6157-134">Action: especifique la acción que se va a realizar y proporcione una descripción.</span><span class="sxs-lookup"><span data-stu-id="e6157-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="e6157-135">Ámbito: defina el ámbito del grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="e6157-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="e6157-136">Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e6157-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6157-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e6157-137">Related topics</span></span>
- [<span data-ttu-id="e6157-138">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="e6157-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="e6157-139">Crear indicadores para los archivos</span><span class="sxs-lookup"><span data-stu-id="e6157-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="e6157-140">Crear indicadores para direcciones IP y URL/dominios</span><span class="sxs-lookup"><span data-stu-id="e6157-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="e6157-141">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="e6157-141">Manage indicators</span></span>](indicator-manage.md)
