---
title: Implementar actualizaciones para ATP de Microsoft Defender para Mac
description: Controle las actualizaciones de ATP de Microsoft Defender para Mac en entornos empresariales.
keywords: microsoft, defender, atp, mac, actualizaciones, implementar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 99f507ad381ee21ba91753716439180fafe37c24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074344"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="f18a8-104">Implementar actualizaciones para Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="f18a8-104">Deploy updates for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f18a8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f18a8-105">**Applies to:**</span></span>

- [<span data-ttu-id="f18a8-106">Microsoft Defender para endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="f18a8-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="f18a8-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f18a8-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f18a8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f18a8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f18a8-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="f18a8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f18a8-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="f18a8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f18a8-111">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="f18a8-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="f18a8-112">Para actualizar Microsoft Defender para Endpoint para Mac, se usa un programa denominado Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="f18a8-112">To update Microsoft Defender for Endpoint for Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="f18a8-113">De forma predeterminada, MAU comprueba automáticamente las actualizaciones diariamente, pero puede cambiarla a semanal, mensual o manual.</span><span class="sxs-lookup"><span data-stu-id="f18a8-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Captura de pantalla mau](images/MDATP-34-MAU.png)

<span data-ttu-id="f18a8-115">Si decide implementar actualizaciones mediante las herramientas de distribución de software, debe configurar MAU para comprobar manualmente si hay actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="f18a8-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="f18a8-116">Puede implementar preferencias para configurar cómo y cuándo MAU busca actualizaciones para los Mac de su organización.</span><span class="sxs-lookup"><span data-stu-id="f18a8-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="f18a8-117">Usar msupdate</span><span class="sxs-lookup"><span data-stu-id="f18a8-117">Use msupdate</span></span>

<span data-ttu-id="f18a8-118">MAU incluye una herramienta de línea de comandos, denominada *msupdate*, que está diseñada para los administradores de TI para que tengan un control más preciso sobre cuándo se aplican las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f18a8-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="f18a8-119">Las instrucciones para usar esta herramienta se pueden encontrar en [Update Office para Mac mediante msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="f18a8-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="f18a8-120">En MAU, el identificador de aplicación de Microsoft Defender para Endpoint para Mac es *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="f18a8-120">In MAU, the application identifier for Microsoft Defender for Endpoint for Mac is *WDAV00*.</span></span> <span data-ttu-id="f18a8-121">Para descargar e instalar las actualizaciones más recientes de Microsoft Defender para Endpoint para Mac, ejecute el siguiente comando desde una ventana de Terminal:</span><span class="sxs-lookup"><span data-stu-id="f18a8-121">To download and install the latest updates for Microsoft Defender for Endpoint for Mac, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="f18a8-122">Establecer preferencias para Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="f18a8-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="f18a8-123">En esta sección se describen las preferencias más comunes que se pueden usar para configurar MAU.</span><span class="sxs-lookup"><span data-stu-id="f18a8-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="f18a8-124">Esta configuración se puede implementar como un perfil de configuración a través de la consola de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="f18a8-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="f18a8-125">En las secciones siguientes se muestra un ejemplo de un perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="f18a8-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="f18a8-126">Establecer el nombre del canal</span><span class="sxs-lookup"><span data-stu-id="f18a8-126">Set the channel name</span></span>

<span data-ttu-id="f18a8-127">El canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen a través de MAU.</span><span class="sxs-lookup"><span data-stu-id="f18a8-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="f18a8-128">Los `Beta` dispositivos pueden probar nuevas características antes de que los dispositivos `Preview` en `Current` y .</span><span class="sxs-lookup"><span data-stu-id="f18a8-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="f18a8-129">El `Current` canal contiene la versión más estable del producto.</span><span class="sxs-lookup"><span data-stu-id="f18a8-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f18a8-130">Antes de Microsoft AutoUpdate versión 4.29, los canales tenían nombres diferentes:</span><span class="sxs-lookup"><span data-stu-id="f18a8-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="f18a8-131">`Beta` se `InsiderFast` denominaba (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="f18a8-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="f18a8-132">`Preview` se `External` denominaba (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="f18a8-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="f18a8-133">`Current` se nombraba `Production`</span><span class="sxs-lookup"><span data-stu-id="f18a8-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="f18a8-134">Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa en `Beta` o `Preview` .</span><span class="sxs-lookup"><span data-stu-id="f18a8-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|||
|:--|:--|
| <span data-ttu-id="f18a8-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f18a8-135">**Domain**</span></span> | <span data-ttu-id="f18a8-136">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f18a8-136">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="f18a8-137">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f18a8-137">**Key**</span></span> | <span data-ttu-id="f18a8-138">ChannelName</span><span class="sxs-lookup"><span data-stu-id="f18a8-138">ChannelName</span></span> |
| <span data-ttu-id="f18a8-139">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f18a8-139">**Data type**</span></span> | <span data-ttu-id="f18a8-140">Cadena</span><span class="sxs-lookup"><span data-stu-id="f18a8-140">String</span></span> |
| <span data-ttu-id="f18a8-141">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f18a8-141">**Possible values**</span></span> | <span data-ttu-id="f18a8-142">Beta</span><span class="sxs-lookup"><span data-stu-id="f18a8-142">Beta</span></span> <br/> <span data-ttu-id="f18a8-143">Preview</span><span class="sxs-lookup"><span data-stu-id="f18a8-143">Preview</span></span> <br/> <span data-ttu-id="f18a8-144">Current</span><span class="sxs-lookup"><span data-stu-id="f18a8-144">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="f18a8-145">Esta configuración cambia el canal de todas las aplicaciones que se actualizan a través de Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="f18a8-145">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="f18a8-146">Para cambiar el canal solo para Microsoft Defender para Endpoint para Mac, ejecute el siguiente comando después de reemplazar `[channel-name]` por el canal deseado:</span><span class="sxs-lookup"><span data-stu-id="f18a8-146">To change the channel only for Microsoft Defender for Endpoint for Mac, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="f18a8-147">Establecer frecuencia de comprobación de actualización</span><span class="sxs-lookup"><span data-stu-id="f18a8-147">Set update check frequency</span></span>

<span data-ttu-id="f18a8-148">Cambiar la frecuencia con la que MAU busca actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f18a8-148">Change how often MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="f18a8-149">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f18a8-149">**Domain**</span></span> | <span data-ttu-id="f18a8-150">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f18a8-150">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="f18a8-151">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f18a8-151">**Key**</span></span> | <span data-ttu-id="f18a8-152">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="f18a8-152">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="f18a8-153">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f18a8-153">**Data type**</span></span> | <span data-ttu-id="f18a8-154">Entero</span><span class="sxs-lookup"><span data-stu-id="f18a8-154">Integer</span></span> |
| <span data-ttu-id="f18a8-155">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="f18a8-155">**Default value**</span></span> | <span data-ttu-id="f18a8-156">720 (minutos)</span><span class="sxs-lookup"><span data-stu-id="f18a8-156">720 (minutes)</span></span> |
| <span data-ttu-id="f18a8-157">**Comment**</span><span class="sxs-lookup"><span data-stu-id="f18a8-157">**Comment**</span></span> | <span data-ttu-id="f18a8-158">Este valor se establece en minutos.</span><span class="sxs-lookup"><span data-stu-id="f18a8-158">This value is set in minutes.</span></span> |
|||

### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="f18a8-159">Cambiar la forma en que MAU interactúa con las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="f18a8-159">Change how MAU interacts with updates</span></span>

<span data-ttu-id="f18a8-160">Cambiar la forma en que MAU busca actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="f18a8-160">Change how MAU searches for updates.</span></span>

|||
|:--|:--|
| <span data-ttu-id="f18a8-161">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f18a8-161">**Domain**</span></span> | <span data-ttu-id="f18a8-162">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f18a8-162">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="f18a8-163">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f18a8-163">**Key**</span></span> | <span data-ttu-id="f18a8-164">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="f18a8-164">HowToCheck</span></span> |
| <span data-ttu-id="f18a8-165">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f18a8-165">**Data type**</span></span> | <span data-ttu-id="f18a8-166">Cadena</span><span class="sxs-lookup"><span data-stu-id="f18a8-166">String</span></span> |
| <span data-ttu-id="f18a8-167">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f18a8-167">**Possible values**</span></span> | <span data-ttu-id="f18a8-168">Manual</span><span class="sxs-lookup"><span data-stu-id="f18a8-168">Manual</span></span> <br/> <span data-ttu-id="f18a8-169">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="f18a8-169">AutomaticCheck</span></span> <br/> <span data-ttu-id="f18a8-170">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="f18a8-170">AutomaticDownload</span></span> |
| <span data-ttu-id="f18a8-171">**Comment**</span><span class="sxs-lookup"><span data-stu-id="f18a8-171">**Comment**</span></span> |  <span data-ttu-id="f18a8-172">Ten en cuenta que AutomaticDownload realizará una descarga e instalará silenciosamente si es posible.</span><span class="sxs-lookup"><span data-stu-id="f18a8-172">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="f18a8-173">Cambiar si el botón "Buscar actualizaciones" está habilitado</span><span class="sxs-lookup"><span data-stu-id="f18a8-173">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="f18a8-174">Cambie si los usuarios locales podrán hacer clic en la opción "Buscar actualizaciones" en la interfaz de usuario de Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="f18a8-174">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|||
|:--|:--|
| <span data-ttu-id="f18a8-175">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f18a8-175">**Domain**</span></span> | <span data-ttu-id="f18a8-176">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f18a8-176">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="f18a8-177">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f18a8-177">**Key**</span></span> | <span data-ttu-id="f18a8-178">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="f18a8-178">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="f18a8-179">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f18a8-179">**Data type**</span></span> | <span data-ttu-id="f18a8-180">Booleano</span><span class="sxs-lookup"><span data-stu-id="f18a8-180">Boolean</span></span> |
| <span data-ttu-id="f18a8-181">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f18a8-181">**Possible values**</span></span> | <span data-ttu-id="f18a8-182">True (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f18a8-182">True (default)</span></span> <br/> <span data-ttu-id="f18a8-183">False</span><span class="sxs-lookup"><span data-stu-id="f18a8-183">False</span></span> |
|||

### <a name="disable-insider-checkbox"></a><span data-ttu-id="f18a8-184">Casilla Deshabilitar Insider</span><span class="sxs-lookup"><span data-stu-id="f18a8-184">Disable Insider checkbox</span></span>

<span data-ttu-id="f18a8-185">Se establece en true para que el "Join the Office Insider Program..." casilla no disponible / grised hacia fuera para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f18a8-185">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|||
|:--|:--|
| <span data-ttu-id="f18a8-186">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f18a8-186">**Domain**</span></span> | <span data-ttu-id="f18a8-187">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f18a8-187">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="f18a8-188">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f18a8-188">**Key**</span></span> | <span data-ttu-id="f18a8-189">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="f18a8-189">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="f18a8-190">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f18a8-190">**Data type**</span></span> | <span data-ttu-id="f18a8-191">Booleano</span><span class="sxs-lookup"><span data-stu-id="f18a8-191">Boolean</span></span> |
| <span data-ttu-id="f18a8-192">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f18a8-192">**Possible values**</span></span> | <span data-ttu-id="f18a8-193">False (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f18a8-193">False (default)</span></span> <br/> <span data-ttu-id="f18a8-194">Verdadero</span><span class="sxs-lookup"><span data-stu-id="f18a8-194">True</span></span> |
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="f18a8-195">Limitar la telemetría que se envía desde MAU</span><span class="sxs-lookup"><span data-stu-id="f18a8-195">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="f18a8-196">Se establece en false para enviar datos de latido mínimos, sin uso de aplicaciones y sin detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="f18a8-196">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|||
|:--|:--|
| <span data-ttu-id="f18a8-197">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f18a8-197">**Domain**</span></span> | <span data-ttu-id="f18a8-198">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f18a8-198">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="f18a8-199">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f18a8-199">**Key**</span></span> | <span data-ttu-id="f18a8-200">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="f18a8-200">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="f18a8-201">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f18a8-201">**Data type**</span></span> | <span data-ttu-id="f18a8-202">Booleano</span><span class="sxs-lookup"><span data-stu-id="f18a8-202">Boolean</span></span> |
| <span data-ttu-id="f18a8-203">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f18a8-203">**Possible values**</span></span> | <span data-ttu-id="f18a8-204">True (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f18a8-204">True (default)</span></span> <br/> <span data-ttu-id="f18a8-205">False</span><span class="sxs-lookup"><span data-stu-id="f18a8-205">False</span></span> |
|||

## <a name="example-configuration-profile"></a><span data-ttu-id="f18a8-206">Perfil de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f18a8-206">Example configuration profile</span></span>

<span data-ttu-id="f18a8-207">El siguiente perfil de configuración se usa para:</span><span class="sxs-lookup"><span data-stu-id="f18a8-207">The following configuration profile is used to:</span></span>
- <span data-ttu-id="f18a8-208">Colocar el dispositivo en el canal beta</span><span class="sxs-lookup"><span data-stu-id="f18a8-208">Place the device in the Beta channel</span></span>
- <span data-ttu-id="f18a8-209">Descargar e instalar actualizaciones automáticamente</span><span class="sxs-lookup"><span data-stu-id="f18a8-209">Automatically download and install updates</span></span>
- <span data-ttu-id="f18a8-210">Habilitar el botón "Buscar actualizaciones" en la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f18a8-210">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="f18a8-211">Permitir que los usuarios del dispositivo se inscriban en los canales de Insider</span><span class="sxs-lookup"><span data-stu-id="f18a8-211">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="f18a8-212">JAMF</span><span class="sxs-lookup"><span data-stu-id="f18a8-212">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="f18a8-213">Intune</span><span class="sxs-lookup"><span data-stu-id="f18a8-213">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="f18a8-214">Para configurar MAU, puede implementar este perfil de configuración desde la herramienta de administración que usa su empresa:</span><span class="sxs-lookup"><span data-stu-id="f18a8-214">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="f18a8-215">Desde JAMF, cargue este perfil de configuración y establezca el dominio de preferencia en *com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="f18a8-215">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="f18a8-216">Desde Intune, cargue este perfil de configuración y establezca el nombre del perfil de configuración personalizado en *com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="f18a8-216">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="f18a8-217">Recursos</span><span class="sxs-lookup"><span data-stu-id="f18a8-217">Resources</span></span>

- [<span data-ttu-id="f18a8-218">referencia de msupdate</span><span class="sxs-lookup"><span data-stu-id="f18a8-218">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
