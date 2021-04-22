---
title: Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux
ms.reviewer: ''
description: Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, nube, conectividad, comunicación
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933114"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="16489-104">Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="16489-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16489-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="16489-105">**Applies to:**</span></span>
- [<span data-ttu-id="16489-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="16489-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16489-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16489-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="16489-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="16489-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16489-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="16489-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="16489-110">Ejecutar la prueba de conectividad</span><span class="sxs-lookup"><span data-stu-id="16489-110">Run the connectivity test</span></span>

<span data-ttu-id="16489-111">Para probar si Defender for Endpoint en Linux puede comunicarse con la nube con la configuración de red actual, ejecute una prueba de conectividad desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="16489-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="16489-112">salida esperada:</span><span class="sxs-lookup"><span data-stu-id="16489-112">expected output:</span></span>

```output
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="16489-113">Si se produce un error en la prueba de conectividad, compruebe si el dispositivo tiene acceso a Internet y si alguno de los puntos de conexión [requeridos](microsoft-defender-endpoint-linux.md#network-connections) por el producto está bloqueado por un proxy o firewall.</span><span class="sxs-lookup"><span data-stu-id="16489-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="16489-114">Los errores con error de curva 35 o 60 indican el rechazo de anclado de certificado.</span><span class="sxs-lookup"><span data-stu-id="16489-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="16489-115">Compruebe si la conexión está bajo inspección SSL o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="16489-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="16489-116">Si es así, agrega Microsoft Defender para Endpoint a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="16489-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="16489-117">Pasos de solución de problemas para entornos sin proxy o con proxy transparente</span><span class="sxs-lookup"><span data-stu-id="16489-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="16489-118">Para probar que una conexión no está bloqueada en un entorno sin un proxy o con un proxy transparente, ejecute el siguiente comando en el terminal:</span><span class="sxs-lookup"><span data-stu-id="16489-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="16489-119">El resultado de este comando debe ser similar a:</span><span class="sxs-lookup"><span data-stu-id="16489-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="16489-120">Pasos de solución de problemas para entornos con proxy estático</span><span class="sxs-lookup"><span data-stu-id="16489-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="16489-121">Pac, WPAD y proxies autenticados no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="16489-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="16489-122">Asegúrese de que solo se usa un proxy estático o un proxy transparente.</span><span class="sxs-lookup"><span data-stu-id="16489-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="16489-123">Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="16489-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="16489-124">Configure una excepción para la inspección SSL y el servidor proxy para pasar directamente los datos de Defender para Endpoint en Linux a las direcciones URL relevantes sin interceptación.</span><span class="sxs-lookup"><span data-stu-id="16489-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="16489-125">Agregar el certificado de interceptación al almacén global no permitirá la interceptación.</span><span class="sxs-lookup"><span data-stu-id="16489-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="16489-126">Si se requiere un proxy estático, agregue un parámetro de proxy al comando anterior, donde corresponda a la dirección `proxy_address:port` y el puerto de proxy:</span><span class="sxs-lookup"><span data-stu-id="16489-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="16489-127">Asegúrese de usar la misma dirección de proxy y el mismo puerto configurados en el `/lib/system/system/mdatp.service` archivo.</span><span class="sxs-lookup"><span data-stu-id="16489-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="16489-128">Compruebe la configuración de proxy si hay errores de los comandos anteriores.</span><span class="sxs-lookup"><span data-stu-id="16489-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="16489-129">El proxy estático no se puede configurar a través de una variable de entorno en `HTTPS_PROXY` todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="16489-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="16489-130">En su lugar, `HTTPS_PROXY` asegúrese de que está correctamente establecido en el `/lib/system/system/mdatp.service` archivo.</span><span class="sxs-lookup"><span data-stu-id="16489-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="16489-131">Para usar un proxy estático, se `mdatp.service` debe modificar el archivo.</span><span class="sxs-lookup"><span data-stu-id="16489-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="16489-132">Asegúrese de que `#` el inicial se quita para descomprimir la siguiente línea de `/lib/systemd/system/mdatp.service` :</span><span class="sxs-lookup"><span data-stu-id="16489-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="16489-133">Asegúrese también de que la dirección de proxy estática correcta esté rellenada para reemplazar `address:port` .</span><span class="sxs-lookup"><span data-stu-id="16489-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="16489-134">Si este archivo es correcto, intente ejecutar el siguiente comando en el terminal para volver a cargar Defender para Endpoint en Linux y propagar la configuración:</span><span class="sxs-lookup"><span data-stu-id="16489-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="16489-135">Una vez que se ha hecho correctamente, intente otra prueba de conectividad desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="16489-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="16489-136">Si el problema persiste, póngase en contacto con el servicio de soporte al cliente.</span><span class="sxs-lookup"><span data-stu-id="16489-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="16489-137">Recursos</span><span class="sxs-lookup"><span data-stu-id="16489-137">Resources</span></span>

- <span data-ttu-id="16489-138">Para obtener más información acerca de cómo configurar el producto para que use un proxy estático, vea [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="16489-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
