---
title: Implementar actualizaciones para Microsoft Defender para Endpoint en Mac
description: Controle las actualizaciones de Microsoft Defender para Endpoint en Mac en entornos empresariales.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, actualizaciones, implementar
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
ms.openlocfilehash: 886195de38856306d69932446eae34212fe4bb0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934506"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0918c-104">Implementar actualizaciones para Microsoft Defender para Endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="0918c-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0918c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0918c-105">**Applies to:**</span></span>

- [<span data-ttu-id="0918c-106">Microsoft Defender para punto de conexión en macOS</span><span class="sxs-lookup"><span data-stu-id="0918c-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="0918c-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0918c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0918c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0918c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0918c-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="0918c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0918c-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0918c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0918c-111">Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características.</span><span class="sxs-lookup"><span data-stu-id="0918c-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="0918c-112">Para actualizar Microsoft Defender para Endpoint en macOS, se usa un programa denominado Microsoft AutoUpdate (MAU).</span><span class="sxs-lookup"><span data-stu-id="0918c-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="0918c-113">De forma predeterminada, MAU comprueba automáticamente las actualizaciones diariamente, pero puede cambiarla a semanal, mensual o manual.</span><span class="sxs-lookup"><span data-stu-id="0918c-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Captura de pantalla mau](images/MDATP-34-MAU.png)

<span data-ttu-id="0918c-115">Si decide implementar actualizaciones mediante las herramientas de distribución de software, debe configurar MAU para comprobar manualmente si hay actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="0918c-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="0918c-116">Puede implementar preferencias para configurar cómo y cuándo MAU busca actualizaciones para los Mac de su organización.</span><span class="sxs-lookup"><span data-stu-id="0918c-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="0918c-117">Usar msupdate</span><span class="sxs-lookup"><span data-stu-id="0918c-117">Use msupdate</span></span>

<span data-ttu-id="0918c-118">MAU incluye una herramienta de línea de comandos, denominada *msupdate*, que está diseñada para los administradores de TI para que tengan un control más preciso sobre cuándo se aplican las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0918c-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="0918c-119">Las instrucciones para usar esta herramienta se pueden encontrar en [Update Office para Mac mediante msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="0918c-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="0918c-120">En MAU, el identificador de aplicación de Microsoft Defender para Endpoint en macOS es *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="0918c-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="0918c-121">Para descargar e instalar las actualizaciones más recientes de Microsoft Defender para Endpoint en macOS, ejecute el siguiente comando desde una ventana de Terminal:</span><span class="sxs-lookup"><span data-stu-id="0918c-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="0918c-122">Establecer preferencias para Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="0918c-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="0918c-123">En esta sección se describen las preferencias más comunes que se pueden usar para configurar MAU.</span><span class="sxs-lookup"><span data-stu-id="0918c-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="0918c-124">Esta configuración se puede implementar como un perfil de configuración a través de la consola de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="0918c-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="0918c-125">En las secciones siguientes se muestra un ejemplo de un perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="0918c-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="0918c-126">Establecer el nombre del canal</span><span class="sxs-lookup"><span data-stu-id="0918c-126">Set the channel name</span></span>

<span data-ttu-id="0918c-127">El canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen a través de MAU.</span><span class="sxs-lookup"><span data-stu-id="0918c-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="0918c-128">Los `Beta` dispositivos pueden probar nuevas características antes de que los dispositivos `Preview` en `Current` y .</span><span class="sxs-lookup"><span data-stu-id="0918c-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="0918c-129">El `Current` canal contiene la versión más estable del producto.</span><span class="sxs-lookup"><span data-stu-id="0918c-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0918c-130">Antes de Microsoft AutoUpdate versión 4.29, los canales tenían nombres diferentes:</span><span class="sxs-lookup"><span data-stu-id="0918c-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="0918c-131">`Beta` se `InsiderFast` denominaba (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="0918c-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="0918c-132">`Preview` se `External` denominaba (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="0918c-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="0918c-133">`Current` se nombraba `Production`</span><span class="sxs-lookup"><span data-stu-id="0918c-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="0918c-134">Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa en `Beta` o `Preview` .</span><span class="sxs-lookup"><span data-stu-id="0918c-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="0918c-135">Section</span><span class="sxs-lookup"><span data-stu-id="0918c-135">Section</span></span>|<span data-ttu-id="0918c-136">Valor</span><span class="sxs-lookup"><span data-stu-id="0918c-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="0918c-137">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="0918c-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="0918c-138">**Key**</span><span class="sxs-lookup"><span data-stu-id="0918c-138">**Key**</span></span> | <span data-ttu-id="0918c-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="0918c-139">ChannelName</span></span> |
| <span data-ttu-id="0918c-140">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0918c-140">**Data type**</span></span> | <span data-ttu-id="0918c-141">Cadena</span><span class="sxs-lookup"><span data-stu-id="0918c-141">String</span></span> |
| <span data-ttu-id="0918c-142">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="0918c-142">**Possible values**</span></span> | <span data-ttu-id="0918c-143">Beta</span><span class="sxs-lookup"><span data-stu-id="0918c-143">Beta</span></span> <br/> <span data-ttu-id="0918c-144">Preview</span><span class="sxs-lookup"><span data-stu-id="0918c-144">Preview</span></span> <br/> <span data-ttu-id="0918c-145">Current</span><span class="sxs-lookup"><span data-stu-id="0918c-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="0918c-146">Esta configuración cambia el canal de todas las aplicaciones que se actualizan a través de Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="0918c-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="0918c-147">Para cambiar el canal solo para Microsoft Defender para Endpoint en macOS, ejecute el siguiente comando después de reemplazar `[channel-name]` por el canal deseado:</span><span class="sxs-lookup"><span data-stu-id="0918c-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="0918c-148">Establecer frecuencia de comprobación de actualización</span><span class="sxs-lookup"><span data-stu-id="0918c-148">Set update check frequency</span></span>

<span data-ttu-id="0918c-149">Cambiar la frecuencia con la que MAU busca actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0918c-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="0918c-150">Section</span><span class="sxs-lookup"><span data-stu-id="0918c-150">Section</span></span>|<span data-ttu-id="0918c-151">Valor</span><span class="sxs-lookup"><span data-stu-id="0918c-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="0918c-152">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="0918c-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="0918c-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="0918c-153">**Key**</span></span> | <span data-ttu-id="0918c-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="0918c-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="0918c-155">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0918c-155">**Data type**</span></span> | <span data-ttu-id="0918c-156">Entero</span><span class="sxs-lookup"><span data-stu-id="0918c-156">Integer</span></span> |
| <span data-ttu-id="0918c-157">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="0918c-157">**Default value**</span></span> | <span data-ttu-id="0918c-158">720 (minutos)</span><span class="sxs-lookup"><span data-stu-id="0918c-158">720 (minutes)</span></span> |
| <span data-ttu-id="0918c-159">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0918c-159">**Comment**</span></span> | <span data-ttu-id="0918c-160">Este valor se establece en minutos.</span><span class="sxs-lookup"><span data-stu-id="0918c-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="0918c-161">Cambiar la forma en que MAU interactúa con las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="0918c-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="0918c-162">Cambiar la forma en que MAU busca actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0918c-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="0918c-163">Section</span><span class="sxs-lookup"><span data-stu-id="0918c-163">Section</span></span>|<span data-ttu-id="0918c-164">Valor</span><span class="sxs-lookup"><span data-stu-id="0918c-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="0918c-165">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="0918c-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="0918c-166">**Key**</span><span class="sxs-lookup"><span data-stu-id="0918c-166">**Key**</span></span> | <span data-ttu-id="0918c-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="0918c-167">HowToCheck</span></span> |
| <span data-ttu-id="0918c-168">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0918c-168">**Data type**</span></span> | <span data-ttu-id="0918c-169">Cadena</span><span class="sxs-lookup"><span data-stu-id="0918c-169">String</span></span> |
| <span data-ttu-id="0918c-170">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="0918c-170">**Possible values**</span></span> | <span data-ttu-id="0918c-171">Manual</span><span class="sxs-lookup"><span data-stu-id="0918c-171">Manual</span></span> <br/> <span data-ttu-id="0918c-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="0918c-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="0918c-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="0918c-173">AutomaticDownload</span></span> |
| <span data-ttu-id="0918c-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="0918c-174">**Comment**</span></span> |  <span data-ttu-id="0918c-175">Ten en cuenta que AutomaticDownload realizará una descarga e instalará silenciosamente si es posible.</span><span class="sxs-lookup"><span data-stu-id="0918c-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="0918c-176">Cambiar si el botón "Buscar actualizaciones" está habilitado</span><span class="sxs-lookup"><span data-stu-id="0918c-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="0918c-177">Cambie si los usuarios locales podrán hacer clic en la opción "Buscar actualizaciones" en la interfaz de usuario de Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="0918c-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="0918c-178">Section</span><span class="sxs-lookup"><span data-stu-id="0918c-178">Section</span></span>|<span data-ttu-id="0918c-179">Valor</span><span class="sxs-lookup"><span data-stu-id="0918c-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="0918c-180">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="0918c-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="0918c-181">**Key**</span><span class="sxs-lookup"><span data-stu-id="0918c-181">**Key**</span></span> | <span data-ttu-id="0918c-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="0918c-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="0918c-183">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0918c-183">**Data type**</span></span> | <span data-ttu-id="0918c-184">Booleano</span><span class="sxs-lookup"><span data-stu-id="0918c-184">Boolean</span></span> |
| <span data-ttu-id="0918c-185">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="0918c-185">**Possible values**</span></span> | <span data-ttu-id="0918c-186">True (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="0918c-186">True (default)</span></span> <br/> <span data-ttu-id="0918c-187">False</span><span class="sxs-lookup"><span data-stu-id="0918c-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="0918c-188">Casilla Deshabilitar Insider</span><span class="sxs-lookup"><span data-stu-id="0918c-188">Disable Insider checkbox</span></span>

<span data-ttu-id="0918c-189">Se establece en true para que el "Join the Office Insider Program..." casilla no disponible / grised hacia fuera para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0918c-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="0918c-190">Section</span><span class="sxs-lookup"><span data-stu-id="0918c-190">Section</span></span>|<span data-ttu-id="0918c-191">Valor</span><span class="sxs-lookup"><span data-stu-id="0918c-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="0918c-192">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="0918c-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="0918c-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="0918c-193">**Key**</span></span> | <span data-ttu-id="0918c-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="0918c-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="0918c-195">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0918c-195">**Data type**</span></span> | <span data-ttu-id="0918c-196">Booleano</span><span class="sxs-lookup"><span data-stu-id="0918c-196">Boolean</span></span> |
| <span data-ttu-id="0918c-197">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="0918c-197">**Possible values**</span></span> | <span data-ttu-id="0918c-198">False (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="0918c-198">False (default)</span></span> <br/> <span data-ttu-id="0918c-199">Verdadero</span><span class="sxs-lookup"><span data-stu-id="0918c-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="0918c-200">Limitar la telemetría que se envía desde MAU</span><span class="sxs-lookup"><span data-stu-id="0918c-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="0918c-201">Se establece en false para enviar datos de latido mínimos, sin uso de aplicaciones y sin detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="0918c-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="0918c-202">Section</span><span class="sxs-lookup"><span data-stu-id="0918c-202">Section</span></span>|<span data-ttu-id="0918c-203">Valor</span><span class="sxs-lookup"><span data-stu-id="0918c-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="0918c-204">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="0918c-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="0918c-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="0918c-205">**Key**</span></span> | <span data-ttu-id="0918c-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="0918c-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="0918c-207">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0918c-207">**Data type**</span></span> | <span data-ttu-id="0918c-208">Booleano</span><span class="sxs-lookup"><span data-stu-id="0918c-208">Boolean</span></span> |
| <span data-ttu-id="0918c-209">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="0918c-209">**Possible values**</span></span> | <span data-ttu-id="0918c-210">True (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="0918c-210">True (default)</span></span> <br/> <span data-ttu-id="0918c-211">False</span><span class="sxs-lookup"><span data-stu-id="0918c-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="0918c-212">Perfil de configuración de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0918c-212">Example configuration profile</span></span>

<span data-ttu-id="0918c-213">El siguiente perfil de configuración se usa para:</span><span class="sxs-lookup"><span data-stu-id="0918c-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="0918c-214">Colocar el dispositivo en el canal beta</span><span class="sxs-lookup"><span data-stu-id="0918c-214">Place the device in the Beta channel</span></span>
- <span data-ttu-id="0918c-215">Descargar e instalar actualizaciones automáticamente</span><span class="sxs-lookup"><span data-stu-id="0918c-215">Automatically download and install updates</span></span>
- <span data-ttu-id="0918c-216">Habilitar el botón "Buscar actualizaciones" en la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="0918c-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="0918c-217">Permitir que los usuarios del dispositivo se inscriban en los canales de Insider</span><span class="sxs-lookup"><span data-stu-id="0918c-217">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="0918c-218">JAMF</span><span class="sxs-lookup"><span data-stu-id="0918c-218">JAMF</span></span>

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

### <a name="intune"></a><span data-ttu-id="0918c-219">Intune</span><span class="sxs-lookup"><span data-stu-id="0918c-219">Intune</span></span>

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

<span data-ttu-id="0918c-220">Para configurar MAU, puede implementar este perfil de configuración desde la herramienta de administración que usa su empresa:</span><span class="sxs-lookup"><span data-stu-id="0918c-220">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="0918c-221">Desde JAMF, cargue este perfil de configuración y establezca el dominio de preferencia en *com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="0918c-221">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="0918c-222">Desde Intune, cargue este perfil de configuración y establezca el nombre del perfil de configuración personalizado en *com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="0918c-222">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="0918c-223">Recursos</span><span class="sxs-lookup"><span data-stu-id="0918c-223">Resources</span></span>

- [<span data-ttu-id="0918c-224">referencia de msupdate</span><span class="sxs-lookup"><span data-stu-id="0918c-224">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
