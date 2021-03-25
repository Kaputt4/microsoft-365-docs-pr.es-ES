---
title: Habilitar la integración de SIEM en Microsoft Defender para endpoint
description: Habilite la integración siem para recibir detecciones en la solución de administración de eventos y información de seguridad (SIEM).
keywords: habilitar siem connector, siem, connector, security information and events
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
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076243"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="e9ebc-104">Habilitar la integración de SIEM en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e9ebc-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9ebc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e9ebc-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9ebc-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e9ebc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="e9ebc-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e9ebc-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e9ebc-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="e9ebc-109">Habilita la integración de la información de seguridad y la administración de eventos (SIEM) para que puedas extraer detecciones del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="e9ebc-110">Extraer detecciones mediante la solución SIEM o mediante la conexión directa a la API de REST de detecciones.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="e9ebc-111">[Microsoft Defender para alerta de](alerts.md) extremo se compone de una o más detecciones.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="e9ebc-112">[Microsoft Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="e9ebc-113">La API de alerta de punto de conexión de Microsoft Defender es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="e9ebc-114">Para obtener más información, vea [Alert methods and properties y](alerts.md) List [alerts](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="e9ebc-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e9ebc-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e9ebc-115">Prerequisites</span></span>

- <span data-ttu-id="e9ebc-116">El usuario que activa la configuración debe tener permisos para crear una aplicación en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="e9ebc-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="e9ebc-117">Se trata de alguien con los siguientes roles:</span><span class="sxs-lookup"><span data-stu-id="e9ebc-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="e9ebc-118">Administrador de seguridad y administrador global</span><span class="sxs-lookup"><span data-stu-id="e9ebc-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="e9ebc-119">Administrador de aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="e9ebc-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="e9ebc-120">Administrador de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e9ebc-120">Application Administrator</span></span>
  - <span data-ttu-id="e9ebc-121">Propietario de la entidad de servicio</span><span class="sxs-lookup"><span data-stu-id="e9ebc-121">Owner of the service principal</span></span>

- <span data-ttu-id="e9ebc-122">Durante la activación inicial, se muestra una pantalla emergente para especificar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="e9ebc-123">Asegúrese de permitir las ventanas emergentes para este sitio.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="e9ebc-124">Habilitar la integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="e9ebc-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="e9ebc-125">En el panel de navegación, seleccione **Configuración**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Imagen de la integración siem desde el menú Configuración1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="e9ebc-127">Si se produce un error al intentar habilitar la aplicación de conector SIEM, compruebe la configuración del bloqueador de elementos emergentes del explorador.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="e9ebc-128">Puede que esté bloqueando la nueva ventana que se abre al habilitar la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="e9ebc-129">Seleccione **Habilitar integración SIEM**.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="e9ebc-130">Esto activa la sección detalles de acceso al conector **SIEM** con valores rellenados previamente y se crea una aplicación en el inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e9ebc-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="e9ebc-131">El secreto de cliente solo se muestra una vez.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-131">The client secret is only displayed once.</span></span> <span data-ttu-id="e9ebc-132">Asegúrese de conservar una copia de ella en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Imagen de la integración siem desde el menú Configuración2](images/siem_details.png)

3. <span data-ttu-id="e9ebc-134">Elija el tipo SIEM que use en su organización.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e9ebc-135">Si selecciona HP ArcSight, deberá guardar estos dos archivos de configuración:</span><span class="sxs-lookup"><span data-stu-id="e9ebc-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="e9ebc-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="e9ebc-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="e9ebc-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="e9ebc-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="e9ebc-138">Si desea conectarse directamente a la API de REST de detecciones mediante acceso mediante programación, elija **API genérica.**</span><span class="sxs-lookup"><span data-stu-id="e9ebc-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="e9ebc-139">Copie los valores individuales o **seleccione Guardar detalles en el** archivo para descargar un archivo que contenga todos los valores.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="e9ebc-140">Seleccione **Generar tokens** para obtener un token de acceso y actualización.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="e9ebc-141">Tendrás que generar un nuevo token de actualización cada 90 días.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="e9ebc-142">Siga las instrucciones para crear un registro de aplicaciones de Azure AD para [Microsoft Defender para endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) y asígnele los permisos correctos para leer alertas.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="e9ebc-143">Ahora puede continuar con la configuración de la solución SIEM o la conexión a la API de REST de detecciones a través del acceso mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="e9ebc-144">Tendrás que usar los tokens al configurar la solución SIEM para permitir que reciba detecciones del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="e9ebc-145">Integrar Microsoft Defender para endpoint con IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="e9ebc-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="e9ebc-146">Puede configurar IBM QRadar para recopilar detecciones de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="e9ebc-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e9ebc-147">Para obtener más información, vea [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span><span class="sxs-lookup"><span data-stu-id="e9ebc-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9ebc-148">Ver también</span><span class="sxs-lookup"><span data-stu-id="e9ebc-148">See also</span></span>
- [<span data-ttu-id="e9ebc-149">Configurar HP ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="e9ebc-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="e9ebc-150">Campos de Microsoft Defender para detección de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="e9ebc-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="e9ebc-151">Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST</span><span class="sxs-lookup"><span data-stu-id="e9ebc-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="e9ebc-152">Solucionar problemas de integración de herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="e9ebc-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
