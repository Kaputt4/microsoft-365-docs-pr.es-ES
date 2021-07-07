---
title: Preguntas más frecuentes sobre la base de pruebas
description: Revisar las preguntas más frecuentes
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323384"
---
# <a name="test-base-faq"></a><span data-ttu-id="e18df-103">Preguntas más frecuentes sobre la base de pruebas</span><span class="sxs-lookup"><span data-stu-id="e18df-103">Test Base FAQ</span></span>

<span data-ttu-id="e18df-104">**P: ¿Cómo se envían los paquetes al equipo base de pruebas?**</span><span class="sxs-lookup"><span data-stu-id="e18df-104">**Q: How do we submit our packages to Test Base team?**</span></span>

<span data-ttu-id="e18df-105">**A:** Envíe los paquetes directamente al entorno base de prueba mediante nuestro portal de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="e18df-105">**A:** Submit your packages directly to the Test Base environment using our self-serve portal.</span></span>

<span data-ttu-id="e18df-106">Para enviar el paquete de la aplicación, vaya a [Azure Portal](https://www.aka.ms/testbaseportal "Página principal de base de prueba") y cargue una carpeta comprimida que contenga los archivos binarios, las dependencias y los scripts de prueba de la aplicación a través del panel del portal de prueba base de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="e18df-106">To submit your application package, navigate to the [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") and upload a zipped folder containing your application's binaries, dependencies, and test scripts via the self-serve Test Base portal dashboard.</span></span> 

<span data-ttu-id="e18df-107">Consulte la guía del usuario de incorporación para obtener más información o póngase en contacto con nuestro equipo en para obtener <testbasepreview@microsoft.com> ayuda y más información.</span><span class="sxs-lookup"><span data-stu-id="e18df-107">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="e18df-108">**P: ¿Qué son las pruebas de salida (OOB)**</span><span class="sxs-lookup"><span data-stu-id="e18df-108">**Q: What are Out-of-box (OOB) tests?**</span></span>

<span data-ttu-id="e18df-109">**A:** Las pruebas de fábrica (OOB) se estandarizan, se ejecuta la prueba predeterminada donde se instalan, se inician y se cierran treinta (30) veces los paquetes de aplicación y, a continuación, se desinstalan.</span><span class="sxs-lookup"><span data-stu-id="e18df-109">**A:** Out-of-box (OOB) tests are standardized, default test runs where application packages are installed, launched and closed thirty (30) times, and then uninstalled.</span></span> 

<span data-ttu-id="e18df-110">Los paquetes creados para Test Base tendrán los siguientes scripts de prueba: instalar, iniciar, cerrar y, opcionalmente, el script de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="e18df-110">The packages created for Test Base will have the following test scripts: install, launch, close, and optionally the uninstall script.</span></span> 

<span data-ttu-id="e18df-111">Las pruebas de lista para usar (OOB) le proporcionan telemetría estandarizada en la aplicación para comparar entre Windows compilaciones.</span><span class="sxs-lookup"><span data-stu-id="e18df-111">The Out-of-box (OOB) tests provide you with standardized telemetry on your application to compare across Windows builds.</span></span>

<span data-ttu-id="e18df-112">**P: ¿Podemos enviar pruebas fuera de las pruebas lista para usar (instalar, iniciar, cerrar, desinstalar scripts de prueba)?**</span><span class="sxs-lookup"><span data-stu-id="e18df-112">**Q: Can we submit tests outside of the Out-of-box tests (install, launch, close, uninstall test scripts)?**</span></span>

<span data-ttu-id="e18df-113">**A:** Sí, los clientes también pueden cargar paquetes de aplicaciones para **pruebas funcionales** a través del panel del portal de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="e18df-113">**A:** Yes, customers can also upload application packages for **functional tests** via the self-serve portal dashboard.</span></span>
<span data-ttu-id="e18df-114">**Las pruebas funcionales** son pruebas que permiten a los clientes ejecutar sus scripts para ejecutar funciones personalizadas en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="e18df-114">**Functional tests** are tests that enable customers execute their scripts to run custom functionality on their application.</span></span>


## <a name="testing"></a><span data-ttu-id="e18df-115">Pruebas</span><span class="sxs-lookup"><span data-stu-id="e18df-115">Testing</span></span>

<span data-ttu-id="e18df-116">**P: ¿Admite pruebas funcionales?**</span><span class="sxs-lookup"><span data-stu-id="e18df-116">**Q: Do you support functional tests?**</span></span>

<span data-ttu-id="e18df-117">**A:** Sí, Test Base admite pruebas funcionales.</span><span class="sxs-lookup"><span data-stu-id="e18df-117">**A:** Yes, Test Base supports functional tests.</span></span> <span data-ttu-id="e18df-118">Las pruebas funcionales son pruebas que permiten a nuestros clientes ejecutar sus scripts para ejecutar funciones personalizadas en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="e18df-118">Functional tests are tests that enable our customers execute their scripts to run custom functionality on their application.</span></span> 

<span data-ttu-id="e18df-119">Para enviar el paquete de la aplicación para pruebas funcionales, basta con cargar la carpeta comprimida que contiene los archivos binarios, dependencias y scripts de prueba de la aplicación a través de nuestro panel del portal de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="e18df-119">To submit your application package for functional testing, simply upload the zipped folder containing your application's binaries, dependencies, and test scripts via our self-serve portal dashboard.</span></span> 

<span data-ttu-id="e18df-120">Consulte la guía del usuario de incorporación para obtener más información o póngase en contacto con nuestro equipo en para obtener <testbasepreview@microsoft.com> ayuda y más información.</span><span class="sxs-lookup"><span data-stu-id="e18df-120">Please see the onboarding user guide for more information or contact our team at <testbasepreview@microsoft.com> for assistance and more information.</span></span>

<span data-ttu-id="e18df-121">**P: ¿Cómo controla Test Base nuestros datos de prueba?**</span><span class="sxs-lookup"><span data-stu-id="e18df-121">**Q: How does Test Base handle our test data?**</span></span>

<span data-ttu-id="e18df-122">**A:** Test Base recopila y administra los datos de prueba de forma segura en el entorno de Azure.</span><span class="sxs-lookup"><span data-stu-id="e18df-122">**A:** Test Base securely collects and manages your test data on the Azure environment.</span></span> 

<span data-ttu-id="e18df-123">**P: ¿La base de pruebas puede admitir nuestras pruebas automatizadas?**</span><span class="sxs-lookup"><span data-stu-id="e18df-123">**Q: Can Test Base support our automated tests?**</span></span>

<span data-ttu-id="e18df-124">Sí, Test Base admite pruebas automatizadas, pero no se admiten pruebas manuales en este momento debido a las capacidades de servicio.</span><span class="sxs-lookup"><span data-stu-id="e18df-124">Yes, Test Base supports automated tests however, we do not support manual tests at this time due to service capabilities.</span></span>

<span data-ttu-id="e18df-125">**P: ¿Qué idiomas y marcos de pruebas automatizadas admite?**</span><span class="sxs-lookup"><span data-stu-id="e18df-125">**Q: What languages and frameworks of automated tests do you support?**</span></span>

<span data-ttu-id="e18df-126">**A:** Se admiten todos los idiomas y marcos.</span><span class="sxs-lookup"><span data-stu-id="e18df-126">**A:** We support all languages and frameworks.</span></span> <span data-ttu-id="e18df-127">Invocamos todos los scripts a través de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e18df-127">We invoke all scripts through PowerShell.</span></span> 

<span data-ttu-id="e18df-128">También tendrá que proporcionar (cargar) los archivos binarios dependientes del marco necesario.</span><span class="sxs-lookup"><span data-stu-id="e18df-128">You will also need to provide (upload) the dependent binaries of the required framework.</span></span>

<span data-ttu-id="e18df-129">**P: ¿Cuánto tiempo proporciona Test Base los resultados de las pruebas?**</span><span class="sxs-lookup"><span data-stu-id="e18df-129">**Q: How soon does Test Base provide test results?**</span></span>

<span data-ttu-id="e18df-130">**A:** Para cada prueba que ejecutemos en las compilaciones de versión previa, proporcionaremos resultados en un plazo de 48 horas en el panel [de Azure Portal.](https://www.aka.ms/testbaseportal "Página principal de base de prueba")</span><span class="sxs-lookup"><span data-stu-id="e18df-130">**A:** For each test that we run against the pre-release builds, we will provide results within 48 hours on your [Azure Portal](https://www.aka.ms/testbaseportal "Test Base Homepage") dashboard.</span></span>

<span data-ttu-id="e18df-131">**P: ¿Puede reiniciar después de la instalación?**</span><span class="sxs-lookup"><span data-stu-id="e18df-131">**Q: Can you reboot after install?**</span></span>

<span data-ttu-id="e18df-132">**A:** Sí, nuestro proceso admite el reinicio después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="e18df-132">**A:** Yes, our process supports rebooting after installation.</span></span> <span data-ttu-id="e18df-133">Asegúrese de seleccionar esta opción en la lista desplegable "Configuración opcional" al configurar las **tareas** en el portal de incorporación.</span><span class="sxs-lookup"><span data-stu-id="e18df-133">Be sure to select this option from the “Optional settings” drop list when setting your **Tasks** on the onboarding portal.</span></span>

<span data-ttu-id="e18df-134">Para las pruebas de lista para usar (OOB), puede especificar si se necesita un reinicio para el _script Install._</span><span class="sxs-lookup"><span data-stu-id="e18df-134">For Out-of-box (OOB) tests, you can specify whether a reboot is needed for the _Install script._</span></span>

![Imagen de reinicio](Media/reboot.png)

<span data-ttu-id="e18df-136">Aunque para las pruebas funcionales, puede especificar si se requiere un reinicio para cada script que se agrega.</span><span class="sxs-lookup"><span data-stu-id="e18df-136">While for functional tests, you can specify whether a reboot is required for each script that is added.</span></span>

![Cómo seleccionar pruebas funcionales](Media/functionalreboot.png)

<span data-ttu-id="e18df-138">**P: ¿Windows versiones compatibles?**</span><span class="sxs-lookup"><span data-stu-id="e18df-138">**Q: What Windows versions do you support?**</span></span>

<span data-ttu-id="e18df-139">**A:** Actualmente, se admiten Windows 10, Windows Server 2016, Windows Server 2016 Core, Windows Server 2019 y Windows Server 2019 Core.</span><span class="sxs-lookup"><span data-stu-id="e18df-139">**A:** We currently support Windows 10 clients, Windows Server 2016, Windows Server 2016 Core version, Windows Server 2019, and Windows Server 2019 Core version.</span></span>

<span data-ttu-id="e18df-140">**P: ¿Cuál es la diferencia entre las pruebas de actualización de seguridad y las pruebas de actualización de características?**</span><span class="sxs-lookup"><span data-stu-id="e18df-140">**Q: What is the difference between Security Update tests and Feature Update tests?**</span></span>

<span data-ttu-id="e18df-141">**A:** Para las pruebas de **<ins></ins>** actualización de seguridad, se prueban las actualizaciones de seguridad mensuales previas a la publicación en Windows que se centran en mantener a nuestros usuarios siempre seguros y protegidos.</span><span class="sxs-lookup"><span data-stu-id="e18df-141">**A:** For Security update tests, we test against the **<ins>monthly pre-release security updates</ins>** on Windows which are focused on keeping our users always secure and protected.</span></span> <span data-ttu-id="e18df-142">Para las pruebas de actualización **<ins></ins>** de características, se prueba con las actualizaciones de características binacionales previas a la versión, que introducen nuevas características y capacidades en Windows.</span><span class="sxs-lookup"><span data-stu-id="e18df-142">For the Feature update tests, we test against the **<ins>bi-annual pre-release feature updates</ins>** which introduces new features and capabilities on Windows.</span></span>

## <a name="debugging-options"></a><span data-ttu-id="e18df-143">Opciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e18df-143">Debugging options</span></span>

<span data-ttu-id="e18df-144">**P: ¿Tenemos acceso a las máquinas virtuales (VM) en caso de errores? ¿Qué comparte Test Base?**</span><span class="sxs-lookup"><span data-stu-id="e18df-144">**Q: Do we get access to the Virtual Machines (VMs) in case of failures? What does Test Base share?**</span></span>

<span data-ttu-id="e18df-145">**A:** Para que el servicio sea compatible y las actualizaciones de versión previa sean seguras, solo Microsoft tiene acceso a las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="e18df-145">**A:** For the service to be compliant and the pre-release updates be secure, only Microsoft has access to the VMs.</span></span> <span data-ttu-id="e18df-146">Sin embargo, los clientes pueden ver los resultados de las pruebas y otras métricas de prueba en el panel del portal, incluidas las señales de bloqueo y bloqueo, las métricas de confiabilidad, la memoria y el uso de la CPU, etc. También generamos y proporcionamos registros de ejecuciones de pruebas en el panel para su descarga y análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="e18df-146">However, customers can view test results and other test metrics on their portal dashboard, including crash and hang signals, reliability metrics, memory and CPU utilization etc. We also generate and provide logs of test runs on the dashboard for download and further analysis.</span></span> 

<span data-ttu-id="e18df-147">También podemos proporcionar volcados de memoria para la depuración de bloqueos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e18df-147">We can also provide memory dumps for crash debugging as needed.</span></span>

<span data-ttu-id="e18df-148">**P: Si se han encontrado problemas durante las pruebas, ¿cuáles son los siguientes pasos para resolver estos problemas?**</span><span class="sxs-lookup"><span data-stu-id="e18df-148">**Q: If there are issues found during the testing, what are the next steps to resolve these issues?**</span></span>

<span data-ttu-id="e18df-149">**A:** El equipo base de prueba realizará un proceso de evaluación inicial para determinar la causa raíz del error y, según nuestros resultados, se enrutaremos al cliente o a los equipos internos de Microsoft para la depuración.</span><span class="sxs-lookup"><span data-stu-id="e18df-149">**A:** The Test Base team will perform an initial triage process to determine the root cause of the error, and then depending on our findings, we will route to the customer or internal teams within Microsoft for debugging.</span></span> 

<span data-ttu-id="e18df-150">Siempre trabajamos estrechamente con nuestros clientes en la corrección conjunta para resolver cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="e18df-150">We always work closely with our customers in joint remediation to resolve any issues.</span></span> 

<span data-ttu-id="e18df-151">**P: ¿Microsoft mantiene la versión de la revisión de seguridad hasta que se resuelva el problema? ¿Qué resoluciones alternativas están disponibles?**</span><span class="sxs-lookup"><span data-stu-id="e18df-151">**Q: Does Microsoft hold the release of the security patch until the issue is resolved? What alternate resolutions are available?**</span></span>

<span data-ttu-id="e18df-152">**A:** El objetivo de Test Base es garantizar que nuestros clientes finales conjuntos no se enfrentan a ningún problema.</span><span class="sxs-lookup"><span data-stu-id="e18df-152">**A:** The goal of Test Base is to ensure our joint end customers do not face any issues.</span></span> <span data-ttu-id="e18df-153">Trabajaremos duro con los proveedores de software para solucionar cualquier problema antes de la versión, pero en caso de que la corrección no sea viable, tenemos otras resoluciones, como correcciones y bloques.</span><span class="sxs-lookup"><span data-stu-id="e18df-153">We will work hard with Software Vendors to address any issues before the release, but in case the fix is not feasible we have other resolutions such as shims and blocks.</span></span>

## <a name="miscellaneous"></a><span data-ttu-id="e18df-154">Varios</span><span class="sxs-lookup"><span data-stu-id="e18df-154">Miscellaneous</span></span>

<span data-ttu-id="e18df-155">**P: ¿Cómo funcionará el servicio con un servidor local?**</span><span class="sxs-lookup"><span data-stu-id="e18df-155">**Q: How will the service work with an on-prem server?**</span></span>

<span data-ttu-id="e18df-156">**A:** Actualmente no proporcionamos compatibilidad con servidores locales.</span><span class="sxs-lookup"><span data-stu-id="e18df-156">**A:** We currently do not provide support for on-prem servers.</span></span> <span data-ttu-id="e18df-157">Sin embargo, si el servidor expone el extremo HTTP, podemos conectarnos a él a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="e18df-157">However, if the server is exposing HTTP endpoint, we can connect to it over the internet.</span></span>

<span data-ttu-id="e18df-158">**P: ¿Quién hospeda las máquinas virtuales?**</span><span class="sxs-lookup"><span data-stu-id="e18df-158">**Q: Who hosts the VMs?**</span></span>

<span data-ttu-id="e18df-159">**A:** Microsoft aprovisiona la máquina virtual para este servicio, tomando la carga de hacerlo desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="e18df-159">**A:** Microsoft provisions the VM for this service, taking the load of doing so from the customer.</span></span>

<span data-ttu-id="e18df-160">**P: ¿Este servicio admite aplicaciones web, móviles o de escritorio?**</span><span class="sxs-lookup"><span data-stu-id="e18df-160">**Q: Does this service support web, mobile, or desktop applications?**</span></span>

<span data-ttu-id="e18df-161">**A:** Actualmente, nuestro enfoque está en las aplicaciones de escritorio, sin embargo, tenemos planes para incorporar aplicaciones web en el futuro, pero no se admiten aplicaciones móviles en este momento.</span><span class="sxs-lookup"><span data-stu-id="e18df-161">**A:** Currently, our focus is on desktop applications, however, we have plans to onboard web applications in the future, but we do not support mobile applications at this time.</span></span>

<span data-ttu-id="e18df-162">**P: ¿Cuál es la diferencia entre Test Base y SUVP?**</span><span class="sxs-lookup"><span data-stu-id="e18df-162">**Q: What is the difference between Test Base and SUVP?**</span></span>

<span data-ttu-id="e18df-163">**A:** La mayor diferencia entre Test Base y SUVP es que nuestros partners incorporaron sus aplicaciones en el entorno de Azure de Base de pruebas para que la validación se ejecute con actualizaciones de versión previa en lugar de realizar las propias pruebas.</span><span class="sxs-lookup"><span data-stu-id="e18df-163">**A:** The biggest difference between Test Base and SUVP is that our partners onboard their applications onto the Test Base Azure environment for validation runs against pre-release updates instead of carrying out the tests themselves.</span></span> 

<span data-ttu-id="e18df-164">Además de las pruebas de actualizaciones de seguridad previas a la versión, se admiten pruebas de actualizaciones de características previas a la versión en nuestra plataforma.</span><span class="sxs-lookup"><span data-stu-id="e18df-164">In addition to pre-release security updates testing, we support pre-release feature updates testing on our platform.</span></span> <span data-ttu-id="e18df-165">Tenemos muchos otros tipos de actualizaciones y pruebas del sistema operativo en nuestra guía básica.</span><span class="sxs-lookup"><span data-stu-id="e18df-165">We have many other types of updates and OS testing on our roadmap.</span></span>

<span data-ttu-id="e18df-166">**P: ¿Hay un costo asociado con el servicio?**</span><span class="sxs-lookup"><span data-stu-id="e18df-166">**Q: Is there a cost associated with the service?**</span></span>

<span data-ttu-id="e18df-167">**A:** El servicio Base de prueba será gratuito para los usuarios hasta la Disponibilidad general (GA).</span><span class="sxs-lookup"><span data-stu-id="e18df-167">**A:** The Test Base service will be free to users until General Availability (GA).</span></span> <span data-ttu-id="e18df-168">En ese momento, anunciaremos una estructura de costos que estará en vigor para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="e18df-168">At that time, we will announce a cost structure that will be in effect for all customers.</span></span> 

<span data-ttu-id="e18df-169">**P: ¿Cómo puedo proporcionar comentarios sobre Test Base?**</span><span class="sxs-lookup"><span data-stu-id="e18df-169">**Q: How can I provide feedback about Test Base?**</span></span>

<span data-ttu-id="e18df-170">**A:** Para compartir sus comentarios sobre Test Base, seleccione el icono **Comentarios** en la parte inferior izquierda del portal.</span><span class="sxs-lookup"><span data-stu-id="e18df-170">**A:** To share your feedback about Test Base, select the **Feedback** icon at the bottom left of the portal.</span></span> <span data-ttu-id="e18df-171">Incluye una captura de pantalla con el envío para ayudar a Microsoft a comprender mejor tus comentarios.</span><span class="sxs-lookup"><span data-stu-id="e18df-171">Include a screenshot with your submission to help Microsoft better understand your feedback.</span></span> 

<span data-ttu-id="e18df-172">También puede enviar sugerencias de productos y enviar otras ideas en <testbasepreview@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="e18df-172">You can also submit product suggestions and upvote other ideas at <testbasepreview@microsoft.com>.</span></span>
