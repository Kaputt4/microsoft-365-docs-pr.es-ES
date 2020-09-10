---
title: Establecer zonas horarias y de idioma en Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 94af3e22-aca6-4e91-8b91-1cd5a02a9ea8
description: Cambiar la configuración de idioma y zona horaria en Microsoft bookings. Si las reservas se crean en un momento incorrecto, es posible que se establezcan reservas para la zona horaria incorrecta.
ms.openlocfilehash: 07e5dde2a896610ee079063943aff24ec69ba721
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420110"
---
# <a name="set-language-and-time-zones-in-microsoft-bookings"></a><span data-ttu-id="2916b-104">Establecer zonas horarias y de idioma en Microsoft bookings</span><span class="sxs-lookup"><span data-stu-id="2916b-104">Set language and time zones in Microsoft Bookings</span></span>

<span data-ttu-id="2916b-105">Si está usando Microsoft bookings y se crean reservas en un momento incorrecto, puede que sea necesario cambiar la configuración de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="2916b-105">If you are using Microsoft Bookings and bookings are created at the wrong time, then your time zone settings might need to be changed.</span></span> <span data-ttu-id="2916b-106">Del mismo modo, si algunas reservas están en un idioma incorrecto, es posible que deba cambiar la configuración de idioma.</span><span class="sxs-lookup"><span data-stu-id="2916b-106">Likewise, if some bookings are in the wrong language, you might need to change your language settings.</span></span>

<span data-ttu-id="2916b-107">Existen dos configuraciones de idioma y de zona horaria diferentes para las reservas.</span><span class="sxs-lookup"><span data-stu-id="2916b-107">There are two separate language and time zone settings for Bookings.</span></span> <span data-ttu-id="2916b-108">La primera opción controla el idioma y la zona horaria del calendario de reserva y se establece mediante la configuración de Outlook en la web para el calendario personal del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="2916b-108">The first setting controls the language and time zone of the booking calendar and is set using the Outlook on the web settings for the personal calendar of the logged-in user.</span></span> <span data-ttu-id="2916b-109">La segunda configuración afecta a la página de reserva de autoservicio que usan los clientes y se establece mediante una página de "configuración regional" que controla el idioma y la zona horaria sólo para esa página.</span><span class="sxs-lookup"><span data-stu-id="2916b-109">The second setting affects the self-service booking page that your customers use and is set using a "regional settings" page that controls language and time zone only for that page.</span></span>

> [!NOTE]
> <span data-ttu-id="2916b-110">Las reservas están activadas de forma predeterminada para los clientes con las suscripciones Microsoft 365 Business Standard, Microsoft 365 a3 o Microsoft 365 A5.</span><span class="sxs-lookup"><span data-stu-id="2916b-110">Bookings is turned on by default for customers who have the Microsoft 365 Business Standard, Microsoft 365 A3, or Microsoft 365 A5 subscriptions.</span></span> <span data-ttu-id="2916b-111">Las reservas también están disponibles para los clientes que tienen Office 365 Enterprise E3 y Office 365 Enterprise E5, pero están desactivados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2916b-111">Bookings is also available to customers who have Office 365 Enterprise E3 and Office 365 Enterprise E5, but it is turned off by default.</span></span> <span data-ttu-id="2916b-112">Para empezar, vea [obtener acceso a Microsoft bookings](get-access.md).</span><span class="sxs-lookup"><span data-stu-id="2916b-112">To get started, see [Get access to Microsoft Bookings](get-access.md).</span></span> <span data-ttu-id="2916b-113">Para activar o desactivar las reservas, consulte [activar o desactivar las reservas para su organización](turn-bookings-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2916b-113">To turn Bookings on or off, see [Turn Bookings on or off for your organization](turn-bookings-on-or-off.md).</span></span>

## <a name="setting-language-and-time-zone-for-a-booking-calendar"></a><span data-ttu-id="2916b-114">Configuración de idioma y zona horaria para un calendario de reserva</span><span class="sxs-lookup"><span data-stu-id="2916b-114">Setting language and time zone for a booking calendar</span></span>

<span data-ttu-id="2916b-115">El calendario de reserva usa la configuración de idioma y zona horaria del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="2916b-115">The booking calendar uses the logged-in user’s language and time zone settings.</span></span> <span data-ttu-id="2916b-116">Por ejemplo, si la zona horaria del usuario que ha iniciado sesión se establece en la hora estándar del este (EST), el calendario de reserva mostrará las horas de inicio y finalización de las citas existentes en EST.</span><span class="sxs-lookup"><span data-stu-id="2916b-116">For example, If the logged-in user’s time zone is set to Eastern Standard Time (EST), then the booking calendar will show existing appointment start and end times in EST.</span></span> <span data-ttu-id="2916b-117">Esta zona horaria se estableció originalmente cuando se crearon las cuentas de Microsoft 365 y Outlook en la web del usuario.</span><span class="sxs-lookup"><span data-stu-id="2916b-117">This time zone was originally set when the user’s Microsoft 365 and Outlook on the web accounts were created.</span></span>

<span data-ttu-id="2916b-118">Para establecer el idioma y la zona horaria del calendario de reserva:</span><span class="sxs-lookup"><span data-stu-id="2916b-118">To set the language and time zone for the booking calendar:</span></span>

1. <span data-ttu-id="2916b-119">Inicie sesión en Microsoft 365 y seleccione el icono de Outlook en la página de aterrizaje (tal como se muestra en la captura de pantalla siguiente) o en el iniciador de aplicaciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2916b-119">Log into Microsoft 365 and select the Outlook tile on the landing page (as shown in the screenshot below) or in the Microsoft 365 App Launcher.</span></span>

   ![Imagen del icono de Outlook en la página de aterrizaje de Microsoft 365](../media/bookings-outlook-tile.png)

1. <span data-ttu-id="2916b-121">Cuando se abra Outlook, seleccione el **icono de engranaje** en la esquina superior derecha de la pantalla para abrir la configuración personal y de la cuenta y, a continuación, busque "zona horaria" en el cuadro de búsqueda del panel de **configuración** .</span><span class="sxs-lookup"><span data-stu-id="2916b-121">After Outlook opens, select the **gear icon** in the upper, right-hand corner of the screen to open your personal and account settings, then search for “time zone” in the **Settings** panel search box.</span></span> <span data-ttu-id="2916b-122">El panel se actualizará para mostrar la configuración actual de idioma y zona horaria para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="2916b-122">The panel will update to show your current personal language and time zone settings for this account.</span></span> <span data-ttu-id="2916b-123">Como se indicó anteriormente, esta configuración también controla el idioma y la zona horaria del calendario de reserva.</span><span class="sxs-lookup"><span data-stu-id="2916b-123">As noted above, this setting also controls the language and time zone of the booking calendar.</span></span>

1. <span data-ttu-id="2916b-124">Para cambiar el idioma o la zona horaria, seleccione la flecha desplegable en el cuadro **idioma o zona horaria actual** y elija la configuración deseada.</span><span class="sxs-lookup"><span data-stu-id="2916b-124">Change the language or time zone by selecting the drop-down arrow in the **Language or Current time zone** box and choosing the desired setting.</span></span>

1. <span data-ttu-id="2916b-125">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2916b-125">Click **Save**.</span></span> <span data-ttu-id="2916b-126">El panel configuración se cierra, Outlook en la web se reiniciará y se aplicará la nueva configuración de idioma y zona horaria.</span><span class="sxs-lookup"><span data-stu-id="2916b-126">The Settings panel closes, Outlook on the web restarts, and the new language and time zone settings are applied.</span></span>

## <a name="setting-the-language-and-time-zone-for-the-booking-page"></a><span data-ttu-id="2916b-127">Establecimiento de la zona horaria y el idioma de la página de reserva</span><span class="sxs-lookup"><span data-stu-id="2916b-127">Setting the language and time zone for the booking page</span></span>

1. <span data-ttu-id="2916b-128">En Microsoft 365, seleccione el iniciador de aplicaciones y, a continuación, seleccione **reservas**.</span><span class="sxs-lookup"><span data-stu-id="2916b-128">In Microsoft 365, select the app launcher, and then select **Bookings**.</span></span>

1. <span data-ttu-id="2916b-129">En el panel de navegación, seleccione **Página de reserva** y seleccione cambiar la **configuración de idioma y zona horaria**.</span><span class="sxs-lookup"><span data-stu-id="2916b-129">In the navigation pane, select **Booking page** and select **Change language and time zone settings**.</span></span>

   ![Captura de pantalla: cambiar el vínculo de configuración de idioma y zona horaria](../media/bookings-region-language-timezone-settings.png)

1. <span data-ttu-id="2916b-131">Seleccione su idioma y la zona horaria actual y elija Aceptar.</span><span class="sxs-lookup"><span data-stu-id="2916b-131">Select your language and current time zone and choose OK.</span></span>

   ![Captura de pantalla: configuración de idioma y zona horaria](../media/bookings-region-timezone-settings.png)
