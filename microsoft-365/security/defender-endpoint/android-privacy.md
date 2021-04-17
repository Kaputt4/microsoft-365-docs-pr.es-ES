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
ms.openlocfilehash: 79f8882e21f23e75d85813cde03260ef17adf246
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876114"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="933fd-104">Microsoft Defender para punto de conexión en Android: información de privacidad</span><span class="sxs-lookup"><span data-stu-id="933fd-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="933fd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="933fd-105">**Applies to:**</span></span>
- [<span data-ttu-id="933fd-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="933fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="933fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="933fd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="933fd-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="933fd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="933fd-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="933fd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="933fd-110">Defender for Endpoint para Android recopila información de los dispositivos Android configurados y la almacena en el mismo espacio empresarial donde tiene Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="933fd-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="933fd-111">La información se recopila para ayudar a mantener Defender for Endpoint for iOS seguro, actualizado, con el rendimiento esperado y para admitir el servicio.</span><span class="sxs-lookup"><span data-stu-id="933fd-111">The information is collected to help keep Defender for Endpoint for iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="933fd-112">Para obtener más información sobre el almacenamiento de datos, vea [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="933fd-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="933fd-113">La información se recopila para ayudar a mantener Defender for Endpoint for Android seguro, actualizado, con el rendimiento esperado y para admitir el servicio.</span><span class="sxs-lookup"><span data-stu-id="933fd-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="933fd-114">Datos requeridos</span><span class="sxs-lookup"><span data-stu-id="933fd-114">Required Data</span></span> 

<span data-ttu-id="933fd-115">Los datos requeridos constan de datos necesarios para que Defender for Endpoint for Android funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="933fd-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="933fd-116">Estos datos son esenciales para el funcionamiento del servicio y pueden incluir datos relacionados con el usuario final, la organización, el dispositivo y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="933fd-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="933fd-117">Esta es una lista de los tipos de datos que se recopilan:</span><span class="sxs-lookup"><span data-stu-id="933fd-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="933fd-118">Información de la aplicación</span><span class="sxs-lookup"><span data-stu-id="933fd-118">App information</span></span>

<span data-ttu-id="933fd-119">Información sobre **paquetes de** aplicaciones android malintencionadas (APK) en el dispositivo, incluidos los</span><span class="sxs-lookup"><span data-stu-id="933fd-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="933fd-120">Instalar origen</span><span class="sxs-lookup"><span data-stu-id="933fd-120">Install source</span></span>
-  <span data-ttu-id="933fd-121">Ubicación de almacenamiento (ruta de acceso de archivo) del APK</span><span class="sxs-lookup"><span data-stu-id="933fd-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="933fd-122">Tiempo de instalación, tamaño del APK y permisos</span><span class="sxs-lookup"><span data-stu-id="933fd-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="933fd-123">Página web / Información de red</span><span class="sxs-lookup"><span data-stu-id="933fd-123">Web page / Network information</span></span>

- <span data-ttu-id="933fd-124">Dirección URL completa del sitio web solo cuando se detecta una conexión malintencionada o una página web.</span><span class="sxs-lookup"><span data-stu-id="933fd-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="933fd-125">Información de conexión</span><span class="sxs-lookup"><span data-stu-id="933fd-125">Connection information</span></span>
- <span data-ttu-id="933fd-126">Tipo de protocolo (como HTTP, HTTPS, etc.)</span><span class="sxs-lookup"><span data-stu-id="933fd-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="933fd-127">Información de dispositivo y cuenta</span><span class="sxs-lookup"><span data-stu-id="933fd-127">Device and account information</span></span>

- <span data-ttu-id="933fd-128">Información del dispositivo, como fecha &, versión de Android, modelo OEM, información de CPU e identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="933fd-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="933fd-129">El identificador de dispositivo es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="933fd-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="933fd-130">Wi-Fi mac del adaptador</span><span class="sxs-lookup"><span data-stu-id="933fd-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="933fd-131">[Id. de Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generado por Android en el momento del primer arranque del dispositivo)</span><span class="sxs-lookup"><span data-stu-id="933fd-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="933fd-132">Identificador único global (GUID) generado aleatoriamente</span><span class="sxs-lookup"><span data-stu-id="933fd-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="933fd-133">Información de inquilino, dispositivo y usuario</span><span class="sxs-lookup"><span data-stu-id="933fd-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="933fd-134">Id. de dispositivo de Azure Active Directory (AD) e id. de usuario de Azure: identifica de forma única el dispositivo, el usuario respectivamente en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="933fd-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="933fd-135">Identificador de inquilino de Azure: GUID que identifica su organización en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="933fd-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="933fd-136">Id. de organización de ATP de Microsoft Defender: identificador único asociado a la empresa a la que pertenece el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="933fd-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="933fd-137">Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se verán afectadas</span><span class="sxs-lookup"><span data-stu-id="933fd-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="933fd-138">Nombre principal de usuario: id. de correo electrónico del usuario</span><span class="sxs-lookup"><span data-stu-id="933fd-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="933fd-139">Datos de uso de productos y servicios</span><span class="sxs-lookup"><span data-stu-id="933fd-139">Product and service usage data</span></span>

<span data-ttu-id="933fd-140">La siguiente información se recopila solo para la aplicación de Microsoft Defender para endpoint instalada en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="933fd-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="933fd-141">Información del paquete de la aplicación, incluido el nombre, la versión y el estado de actualización de la aplicación</span><span class="sxs-lookup"><span data-stu-id="933fd-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="933fd-142">Acciones realizadas en la aplicación</span><span class="sxs-lookup"><span data-stu-id="933fd-142">Actions performed in the app</span></span>

-   <span data-ttu-id="933fd-143">Información de detección de amenazas, como el nombre de la amenaza, la categoría, etc.</span><span class="sxs-lookup"><span data-stu-id="933fd-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="933fd-144">Registros de informes de bloqueo generados por Android</span><span class="sxs-lookup"><span data-stu-id="933fd-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="933fd-145">Datos opcionales</span><span class="sxs-lookup"><span data-stu-id="933fd-145">Optional Data</span></span>

<span data-ttu-id="933fd-146">Los datos opcionales incluyen datos de diagnóstico y datos de comentarios.</span><span class="sxs-lookup"><span data-stu-id="933fd-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="933fd-147">Datos de diagnóstico opcionales: datos adicionales que nos ayudan a mejorar el producto y proporcionan información mejorada para ayudarnos a detectar, diagnosticar y solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="933fd-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="933fd-148">Los datos de diagnóstico opcionales incluyen:</span><span class="sxs-lookup"><span data-stu-id="933fd-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="933fd-149">Uso de aplicaciones, CPU y red</span><span class="sxs-lookup"><span data-stu-id="933fd-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="933fd-150">Estado del dispositivo desde la perspectiva de la aplicación, incluido el estado del examen, los tiempos de examen, los permisos de aplicación concedidos y el estado de actualización</span><span class="sxs-lookup"><span data-stu-id="933fd-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="933fd-151">Características configuradas por el administrador</span><span class="sxs-lookup"><span data-stu-id="933fd-151">Features configured by the admin</span></span>

-   <span data-ttu-id="933fd-152">Información básica sobre los exploradores del dispositivo</span><span class="sxs-lookup"><span data-stu-id="933fd-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="933fd-153">**Los datos de** comentarios se recopilan a través de los comentarios desde la aplicación proporcionados por el usuario</span><span class="sxs-lookup"><span data-stu-id="933fd-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="933fd-154">Dirección de correo electrónico del usuario, si decide proporcionarla</span><span class="sxs-lookup"><span data-stu-id="933fd-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="933fd-155">Tipo de comentarios (sonriente, ceño fruncido, idea) y los comentarios enviados por el usuario</span><span class="sxs-lookup"><span data-stu-id="933fd-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
