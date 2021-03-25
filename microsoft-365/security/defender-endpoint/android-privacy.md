---
title: 'ATP de Microsoft Defender para Android: información de privacidad'
description: Controles de privacidad, cómo configurar las opciones de directiva que afectan a la privacidad y la información sobre los datos de diagnóstico recopilados en ATP de Microsoft Defender para Android.
keywords: microsoft, defender, atp, android, privacidad, diagnóstico
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: abb22b2e733d1e40bd4f2733ef2d25767c69ccf7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163332"
---
#  <a name="microsoft-defender-for-endpoint-for-android---privacy-information"></a><span data-ttu-id="28315-104">Microsoft Defender para endpoint para Android: información de privacidad</span><span class="sxs-lookup"><span data-stu-id="28315-104">Microsoft Defender for Endpoint for Android - Privacy information</span></span>

<span data-ttu-id="28315-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="28315-105">**Applies to:**</span></span>
- [<span data-ttu-id="28315-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28315-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28315-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28315-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28315-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="28315-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28315-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="28315-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="28315-110">Defender for Endpoint para Android recopila información de los dispositivos Android configurados y la almacena en el mismo espacio empresarial donde tiene Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="28315-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="28315-111">La información se recopila para ayudar a mantener Defender for Endpoint for Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.</span><span class="sxs-lookup"><span data-stu-id="28315-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="28315-112">Datos requeridos</span><span class="sxs-lookup"><span data-stu-id="28315-112">Required Data</span></span> 

<span data-ttu-id="28315-113">Los datos requeridos constan de datos necesarios para que Defender for Endpoint for Android funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="28315-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="28315-114">Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="28315-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="28315-115">Esta es una lista de los tipos de datos que se recopilan:</span><span class="sxs-lookup"><span data-stu-id="28315-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="28315-116">Información de la aplicación</span><span class="sxs-lookup"><span data-stu-id="28315-116">App information</span></span>

<span data-ttu-id="28315-117">Información sobre paquetes de aplicaciones Android (APK) en el dispositivo, incluidos los</span><span class="sxs-lookup"><span data-stu-id="28315-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="28315-118">Instalar origen</span><span class="sxs-lookup"><span data-stu-id="28315-118">Install source</span></span>
-  <span data-ttu-id="28315-119">Ubicación de almacenamiento (ruta de acceso de archivo) del APK</span><span class="sxs-lookup"><span data-stu-id="28315-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="28315-120">Tiempo de instalación, tamaño del APK y permisos</span><span class="sxs-lookup"><span data-stu-id="28315-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="28315-121">Página web / Información de red</span><span class="sxs-lookup"><span data-stu-id="28315-121">Web page / Network information</span></span>

- <span data-ttu-id="28315-122">Dirección URL completa (en exploradores compatibles), cuando se hace clic en</span><span class="sxs-lookup"><span data-stu-id="28315-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="28315-123">Información de conexión</span><span class="sxs-lookup"><span data-stu-id="28315-123">Connection information</span></span>
- <span data-ttu-id="28315-124">Tipo de protocolo (como HTTP, HTTPS, etc.)</span><span class="sxs-lookup"><span data-stu-id="28315-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="28315-125">Información de dispositivo y cuenta</span><span class="sxs-lookup"><span data-stu-id="28315-125">Device and account information</span></span>

- <span data-ttu-id="28315-126">Información del dispositivo, como fecha &, versión de Android, modelo OEM, información de CPU e identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="28315-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="28315-127">El identificador de dispositivo es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="28315-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="28315-128">Wi-Fi mac del adaptador</span><span class="sxs-lookup"><span data-stu-id="28315-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="28315-129">[Id. de Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generado por Android en el momento del primer arranque del dispositivo)</span><span class="sxs-lookup"><span data-stu-id="28315-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="28315-130">Identificador único global (GUID) generado aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="28315-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="28315-131">Información de inquilino, dispositivo y usuario</span><span class="sxs-lookup"><span data-stu-id="28315-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="28315-132">Id. de dispositivo de Azure Active Directory (AD) e id. de usuario de Azure: identifica de forma única el dispositivo, el usuario respectivamente en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28315-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="28315-133">Identificador de inquilino de Azure: GUID que identifica su organización en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="28315-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="28315-134">Id. de organización de ATP de Microsoft Defender: identificador único asociado a la empresa a la que pertenece el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28315-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="28315-135">Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se verán afectadas</span><span class="sxs-lookup"><span data-stu-id="28315-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="28315-136">Nombre principal de usuario: id. de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="28315-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="28315-137">Datos de uso de productos y servicios</span><span class="sxs-lookup"><span data-stu-id="28315-137">Product and service usage data</span></span>
-   <span data-ttu-id="28315-138">Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación</span><span class="sxs-lookup"><span data-stu-id="28315-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="28315-139">Acciones realizadas en la aplicación</span><span class="sxs-lookup"><span data-stu-id="28315-139">Actions performed in the app</span></span>

-   <span data-ttu-id="28315-140">Información de detección de amenazas, como el nombre de la amenaza, la categoría, etc.</span><span class="sxs-lookup"><span data-stu-id="28315-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="28315-141">Registros de informes de bloqueo generados por Android</span><span class="sxs-lookup"><span data-stu-id="28315-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="28315-142">Datos opcionales</span><span class="sxs-lookup"><span data-stu-id="28315-142">Optional Data</span></span>

<span data-ttu-id="28315-143">Los datos opcionales incluyen datos de diagnóstico y datos de comentarios.</span><span class="sxs-lookup"><span data-stu-id="28315-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="28315-144">Datos de diagnóstico opcionales: datos adicionales que nos ayudan a mejorar el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="28315-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="28315-145">Los datos de diagnóstico opcionales incluyen:</span><span class="sxs-lookup"><span data-stu-id="28315-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="28315-146">Uso de aplicaciones, CPU y red</span><span class="sxs-lookup"><span data-stu-id="28315-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="28315-147">Estado del dispositivo desde la perspectiva de la aplicación, incluido el estado del examen, los tiempos de examen, los permisos de aplicación concedidos y el estado de actualización</span><span class="sxs-lookup"><span data-stu-id="28315-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="28315-148">Características configuradas por el administrador</span><span class="sxs-lookup"><span data-stu-id="28315-148">Features configured by the admin</span></span>

-   <span data-ttu-id="28315-149">Información básica sobre los exploradores del dispositivo</span><span class="sxs-lookup"><span data-stu-id="28315-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="28315-150">**Los datos de** comentarios se recopilan a través de los comentarios desde la aplicación proporcionados por el usuario</span><span class="sxs-lookup"><span data-stu-id="28315-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="28315-151">Dirección de correo electrónico del usuario, si decide proporcionarla</span><span class="sxs-lookup"><span data-stu-id="28315-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="28315-152">Tipo de comentarios (sonriente, ceño fruncido, idea) y los comentarios enviados por el usuario</span><span class="sxs-lookup"><span data-stu-id="28315-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
