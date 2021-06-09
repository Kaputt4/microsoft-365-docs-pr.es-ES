---
title: 'Microsoft Defender para punto de conexión en Android: información de privacidad'
description: Controles de privacidad, cómo configurar las opciones de directiva que afectan a la privacidad y la información sobre los datos de diagnóstico recopilados en Microsoft Defender para Endpoint en Android.
keywords: microsoft, defender, Microsoft Defender para endpoint, android, privacidad, diagnóstico
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
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694346"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="d9a54-104">Microsoft Defender para punto de conexión en Android: información de privacidad</span><span class="sxs-lookup"><span data-stu-id="d9a54-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="d9a54-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d9a54-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9a54-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d9a54-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d9a54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9a54-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d9a54-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9a54-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9a54-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9a54-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="d9a54-110">Defender for Endpoint en Android recopila información de los dispositivos Android configurados y la almacena en el mismo espacio empresarial donde tiene Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="d9a54-110">Defender for Endpoint on Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="d9a54-111">La información se recopila para ayudar a mantener Defender for Endpoint for Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.</span><span class="sxs-lookup"><span data-stu-id="d9a54-111">The information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="d9a54-112">Para obtener más información sobre el almacenamiento de datos, vea [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="d9a54-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="d9a54-113">La información se recopila para ayudar a mantener Defender for Endpoint for Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.</span><span class="sxs-lookup"><span data-stu-id="d9a54-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

<span data-ttu-id="d9a54-114">Para obtener más información sobre las preguntas de privacidad más comunes sobre Microsoft Defender para endpoint en dispositivos móviles Android e iOS, consulta Microsoft Defender para endpoint y tu privacidad en dispositivos móviles Android e [iOS.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)</span><span class="sxs-lookup"><span data-stu-id="d9a54-114">For more information on most common privacy questions about Microsoft Defender for Endpoint on Android and iOS mobile devices, see [Microsoft Defender for Endpoint and your privacy on Android and iOS mobile devices](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a).</span></span>

## <a name="required-data"></a><span data-ttu-id="d9a54-115">Datos requeridos</span><span class="sxs-lookup"><span data-stu-id="d9a54-115">Required Data</span></span> 

<span data-ttu-id="d9a54-116">Los datos requeridos constan de datos necesarios para que Defender for Endpoint for Android funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="d9a54-116">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="d9a54-117">Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d9a54-117">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="d9a54-118">Esta es una lista de los tipos de datos que se recopilan:</span><span class="sxs-lookup"><span data-stu-id="d9a54-118">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="d9a54-119">Información de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d9a54-119">App information</span></span>

<span data-ttu-id="d9a54-120">Información sobre **paquetes de** aplicaciones android malintencionadas (APK) en el dispositivo, incluidos los</span><span class="sxs-lookup"><span data-stu-id="d9a54-120">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="d9a54-121">Instalar origen</span><span class="sxs-lookup"><span data-stu-id="d9a54-121">Install source</span></span>
-  <span data-ttu-id="d9a54-122">Storage ubicación (ruta de acceso de archivo) del APK</span><span class="sxs-lookup"><span data-stu-id="d9a54-122">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="d9a54-123">Tiempo de instalación, tamaño del APK y permisos</span><span class="sxs-lookup"><span data-stu-id="d9a54-123">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="d9a54-124">Página web / Información de red</span><span class="sxs-lookup"><span data-stu-id="d9a54-124">Web page / Network information</span></span>

- <span data-ttu-id="d9a54-125">Dirección URL completa del sitio web solo cuando se detecta una conexión malintencionada o una página web.</span><span class="sxs-lookup"><span data-stu-id="d9a54-125">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="d9a54-126">Información de conexión</span><span class="sxs-lookup"><span data-stu-id="d9a54-126">Connection information</span></span>
- <span data-ttu-id="d9a54-127">Tipo de protocolo (como HTTP, HTTPS, etc.)</span><span class="sxs-lookup"><span data-stu-id="d9a54-127">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="d9a54-128">Información de dispositivo y cuenta</span><span class="sxs-lookup"><span data-stu-id="d9a54-128">Device and account information</span></span>

- <span data-ttu-id="d9a54-129">Información del dispositivo, como fecha &, versión de Android, modelo OEM, información de CPU e identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d9a54-129">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="d9a54-130">El identificador de dispositivo es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9a54-130">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="d9a54-131">Wi-Fi mac del adaptador</span><span class="sxs-lookup"><span data-stu-id="d9a54-131">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="d9a54-132">[Id. de Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generado por Android en el momento del primer arranque del dispositivo)</span><span class="sxs-lookup"><span data-stu-id="d9a54-132">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="d9a54-133">Identificador único global (GUID) generado aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="d9a54-133">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="d9a54-134">Información de inquilino, dispositivo y usuario</span><span class="sxs-lookup"><span data-stu-id="d9a54-134">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="d9a54-135">Azure Active Directory de dispositivo (AD) y el id. de usuario de Azure: identifica de forma única el dispositivo, el usuario respectivamente en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d9a54-135">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="d9a54-136">Identificador de inquilino de Azure: GUID que identifica la organización dentro de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d9a54-136">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="d9a54-137">Id. de la organización de Microsoft Defender para extremo: identificador único asociado a la empresa a la que pertenece el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9a54-137">Microsoft Defender for Endpoint org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="d9a54-138">Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se verán afectadas</span><span class="sxs-lookup"><span data-stu-id="d9a54-138">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="d9a54-139">Nombre principal de usuario: id. de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="d9a54-139">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="d9a54-140">Datos de uso de productos y servicios</span><span class="sxs-lookup"><span data-stu-id="d9a54-140">Product and service usage data</span></span>

<span data-ttu-id="d9a54-141">La siguiente información se recopila solo para la aplicación de Microsoft Defender para endpoint instalada en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9a54-141">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="d9a54-142">Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d9a54-142">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="d9a54-143">Acciones realizadas en la aplicación</span><span class="sxs-lookup"><span data-stu-id="d9a54-143">Actions performed in the app</span></span>

-   <span data-ttu-id="d9a54-144">Información de detección de amenazas, como el nombre de la amenaza, la categoría, etc.</span><span class="sxs-lookup"><span data-stu-id="d9a54-144">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="d9a54-145">Registros de informes de bloqueo generados por Android</span><span class="sxs-lookup"><span data-stu-id="d9a54-145">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="d9a54-146">Datos opcionales</span><span class="sxs-lookup"><span data-stu-id="d9a54-146">Optional Data</span></span>

<span data-ttu-id="d9a54-147">Los datos opcionales incluyen datos de diagnóstico y datos de comentarios.</span><span class="sxs-lookup"><span data-stu-id="d9a54-147">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="d9a54-148">Datos de diagnóstico opcionales: datos adicionales que nos ayudan a mejorar el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="d9a54-148">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="d9a54-149">Los datos de diagnóstico opcionales incluyen:</span><span class="sxs-lookup"><span data-stu-id="d9a54-149">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="d9a54-150">Uso de aplicaciones, CPU y red</span><span class="sxs-lookup"><span data-stu-id="d9a54-150">App, CPU, and network usage</span></span>

-   <span data-ttu-id="d9a54-151">Estado del dispositivo desde la perspectiva de la aplicación, incluido el estado del examen, los tiempos de examen, los permisos de aplicación concedidos y el estado de actualización</span><span class="sxs-lookup"><span data-stu-id="d9a54-151">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="d9a54-152">Características configuradas por el administrador</span><span class="sxs-lookup"><span data-stu-id="d9a54-152">Features configured by the admin</span></span>

-   <span data-ttu-id="d9a54-153">Información básica sobre los exploradores del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d9a54-153">Basic information about the browsers on the device</span></span>

<span data-ttu-id="d9a54-154">**Los datos de** comentarios se recopilan a través de los comentarios desde la aplicación proporcionados por el usuario</span><span class="sxs-lookup"><span data-stu-id="d9a54-154">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="d9a54-155">Dirección de correo electrónico del usuario, si decide proporcionarla</span><span class="sxs-lookup"><span data-stu-id="d9a54-155">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="d9a54-156">Tipo de comentarios (sonriente, ceño fruncido, idea) y los comentarios enviados por el usuario</span><span class="sxs-lookup"><span data-stu-id="d9a54-156">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
