---
title: Supervisión de Exchange Online para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Usar supervisión de Exchange Online para obtener información sobre avisos o incidentes de correo electrónico en Microsoft 365.
ms.openlocfilehash: 53dc7f990f57fd8d4da68bd424947676cbf0e85d
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572880"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="a1492-103">Supervisión de Exchange Online para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1492-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="a1492-104">Puede usar la supervisión de Exchange Online en el Centro de administración de Microsoft 365 para supervisar el estado del servicio de Exchange para la suscripción de Microsoft 365 de su organización.</span><span class="sxs-lookup"><span data-stu-id="a1492-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="a1492-105">La supervisión de Exchange Online ofrece información sobre incidentes y avisos que se recopilan en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="a1492-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="a1492-106">**Infraestructura**: se detecta un problema en la infraestructura de Microsoft 365 que es propiedad de Microsoft para proporcionar actualizaciones periódicas y solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="a1492-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="a1492-107">Por ejemplo, los usuarios no pueden acceder a Exchange Online debido a problemas con Exchange u otra infraestructura en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1492-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="a1492-108">**Infraestructura de terceros**: se detecta un problema en una infraestructura de terceros en la que la organización tiene una dependencia y necesita una acción de su organización para su resolución.</span><span class="sxs-lookup"><span data-stu-id="a1492-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="a1492-109">Por ejemplo, las transacciones de autenticación de usuario se limitan con un proveedor de servicio de token de seguridad (STS) de terceros que impide que los usuarios se conecten a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a1492-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="a1492-110">**Infraestructura del cliente**: se detecta un problema en la infraestructura de la organización y requiere una acción de su organización para su resolución.</span><span class="sxs-lookup"><span data-stu-id="a1492-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="a1492-111">Por ejemplo, los usuarios no pueden acceder a Exchange Online porque no pueden obtener un token de autenticación de un proveedor de STS hospedado por la organización debido a un certificado caducado.</span><span class="sxs-lookup"><span data-stu-id="a1492-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="a1492-112">Aquí se muestra un ejemplo de la página **Estado del servicio** en el Centro de administración de Microsoft 365, disponible en **Estado > Estado del servicio**.</span><span class="sxs-lookup"><span data-stu-id="a1492-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![La página de Estado del servicio en el Centro de administración de Microsoft 365](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="a1492-114">El valor de la columna **Estado** indica si el servicio está en buen estado o tiene avisos o incidentes basados en los servicios en la nube que mantiene Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1492-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="a1492-115">El valor de la columna **Problemas de su organización y de terceros** indica que la infraestructura de su organización o el software de terceros afecta a la experiencia del estado del servicio de sus usuarios con Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a1492-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="a1492-116">Los avisos o incidencias requieren *sus* acciones para resolverse.</span><span class="sxs-lookup"><span data-stu-id="a1492-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="a1492-117">Aquí se muestra un ejemplo de la página de supervisión de **Exchange Online** en el Centro de administración de Microsoft 365, disponible en **Estado > Estado del servicio > Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="a1492-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![La página de supervisión de Exchange Online en el Centro de administración de Microsoft 365](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="a1492-119">Con la página de supervisión de **Exchange Online**, puede ver si el servicio de Exchange Online está en buen estado o no y si hay incidentes o avisos asociados.</span><span class="sxs-lookup"><span data-stu-id="a1492-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="a1492-120">Con la supervisión de Exchange Online, puede observar el estado del servicio para escenarios de correo electrónico específicos y ver señales casi en tiempo real para determinar el impacto por escenario.</span><span class="sxs-lookup"><span data-stu-id="a1492-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="a1492-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1492-121">Requirements</span></span>

<span data-ttu-id="a1492-122">Esta vista previa está habilitada para los clientes que cumplan estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="a1492-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="a1492-123">Su organización necesita tener un número de licencias de al menos 10 000, de uno o de una combinación de estos productos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a1492-123">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="a1492-124">Por ejemplo, su organización puede tener 3 000 licencias de Office 365 E3 y 8 500 de Microsoft 365 E5, con un total de 11 500 licencias de productos aptos.</span><span class="sxs-lookup"><span data-stu-id="a1492-124">For example, your organization can have 3,000 Office 365 E3 licenses and 8,500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="a1492-125">Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.</span><span class="sxs-lookup"><span data-stu-id="a1492-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="a1492-126">Con la supervisión de Exchange Online, puede ver el estado de los siguientes clientes de correo electrónico basándose en la actividad de lectura de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="a1492-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="a1492-127">Versión de escritorio de Outlook  </span><span class="sxs-lookup"><span data-stu-id="a1492-127">Outlook Desktop</span></span>
- <span data-ttu-id="a1492-128">Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="a1492-128">Outlook on the Web</span></span>
- <span data-ttu-id="a1492-129">Clientes de correo electrónico nativo de iOS y Android</span><span class="sxs-lookup"><span data-stu-id="a1492-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="a1492-130">Aplicación móvil de Outlook en iOS y Android</span><span class="sxs-lookup"><span data-stu-id="a1492-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="a1492-131">Cliente de Outlook para Mac</span><span class="sxs-lookup"><span data-stu-id="a1492-131">Outlook Mac client</span></span>

<span data-ttu-id="a1492-132">Para estos clientes, puede ver el número de usuarios activos en los últimos 30 minutos basándose en los usuarios que lean un correo electrónico, así como la cantidad de incidentes y avisos en el panel.</span><span class="sxs-lookup"><span data-stu-id="a1492-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="a1492-133">Estos datos se comparan con el mismo intervalo de la semana anterior para ver si hay un problema.</span><span class="sxs-lookup"><span data-stu-id="a1492-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="a1492-134">El recuento de usuarios activos se mide por una única actividad, por ejemplo, cuando un usuario lee un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1492-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="a1492-135">Solo se tienen en cuenta los últimos 30 minutos de actividad.</span><span class="sxs-lookup"><span data-stu-id="a1492-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="a1492-136">También puede supervisar el estado de Exchange Online en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="a1492-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="a1492-137">**Flujo de correo**: el número de mensajes entregados correctamente a un buzón sin retraso desde que el mensaje llegó a la red Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1492-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="a1492-138">**Autenticación básica y autenticación moderna**: número de usuarios validados correctamente en el servicio de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a1492-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Un ejemplo de supervisión del estado de Exchange para la entrega de correo](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="a1492-140">Para todos estos escenarios, los números clave son para los últimos 30 minutos en el panel principal.</span><span class="sxs-lookup"><span data-stu-id="a1492-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="a1492-141">Las vistas detalladas de cada uno de estos escenarios muestran la tendencia en tiempo casi real durante siete días con un agregado de 30 minutos en comparación con la semana anterior.</span><span class="sxs-lookup"><span data-stu-id="a1492-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="a1492-142">Enviarnos comentarios</span><span class="sxs-lookup"><span data-stu-id="a1492-142">Send us feedback</span></span>

<span data-ttu-id="a1492-143">Hay dos formas de proporcionar comentarios:</span><span class="sxs-lookup"><span data-stu-id="a1492-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="a1492-144">Usar la opción **Enviar comentarios** disponible en cada página del Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1492-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="a1492-145">Enviar comentarios usando el vínculo **¿Es útil esta publicación?** para un incidente o aviso específico.</span><span class="sxs-lookup"><span data-stu-id="a1492-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![El vínculo "¿Es útil esta publicación?"](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="a1492-148">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="a1492-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a1492-149">1. ¿Por qué no veo “Supervisión de Exchange Online” en Estado en el Centro de administración de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="a1492-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="a1492-150">En primer lugar, asegúrese de que ha habilitado el nuevo Centro de administración en la página **Inicio** del Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1492-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="a1492-151">Después, asegúrese de que cumple los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a1492-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="a1492-152">Su organización necesita tener un número de licencias de al menos 10 000, de uno o de una combinación de estos productos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a1492-152">Your organization needs to have a license count of at least 10,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="a1492-153">Su organización necesita tener al menos 50 usuarios activos de Exchange Online mensuales.</span><span class="sxs-lookup"><span data-stu-id="a1492-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="a1492-154">Si el número de licencias de la organización es inferior a 10 000 usuarios y los usuarios activos mensuales son menos de 50, no se habilitará la supervisión de Exchange Online hasta que se cumplan estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="a1492-154">If the license count for your organization goes below 10,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="a1492-155">2. El número de usuarios activos en el panel de control de cada cliente parece ser bajo.</span><span class="sxs-lookup"><span data-stu-id="a1492-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="a1492-156">Tenemos muchas licencias activas asignadas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a1492-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="a1492-157">¿Qué significa esto?</span><span class="sxs-lookup"><span data-stu-id="a1492-157">What does this mean?</span></span> 

<span data-ttu-id="a1492-158">El recuento de usuarios activos que se muestra en la supervisión se basa en una ventana de 30 minutos donde los usuarios han realizado la actividad indicada en la característica.</span><span class="sxs-lookup"><span data-stu-id="a1492-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="a1492-159">No debe confundirse con los números de uso.</span><span class="sxs-lookup"><span data-stu-id="a1492-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="a1492-160">Para ver los números de uso, utilice los informes de actividad en el Centro de administración de Microsoft 365 (**Informes > Uso**).</span><span class="sxs-lookup"><span data-stu-id="a1492-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="a1492-161">3. ¿Hay otros escenarios de supervisión para otros servicios, como Microsoft Teams y SharePoint?</span><span class="sxs-lookup"><span data-stu-id="a1492-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="a1492-162">Microsoft está integrando esta experiencia directamente en el panel de Estado del servicio en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1492-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a1492-163">Esto ofrecerá oportunidades para que Microsoft extienda escenarios de supervisión a otros servicios, que se anunciarán cuando haya novedades para compartir.</span><span class="sxs-lookup"><span data-stu-id="a1492-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="a1492-164">4. ¿Cuál es el plan para la disponibilidad general de esta experiencia?</span><span class="sxs-lookup"><span data-stu-id="a1492-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="a1492-165">Microsoft ha integrado la supervisión de Exchange Online directamente en el panel de **Estado del servicio** en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1492-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="a1492-166">Con esta nueva experiencia integrada, el plan de Microsoft es recopilar sus comentarios y definir nuestro plan de disponibilidad general.</span><span class="sxs-lookup"><span data-stu-id="a1492-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="a1492-167">5. ¿Es una característica gratuita (incluida) o de pago (extra)?</span><span class="sxs-lookup"><span data-stu-id="a1492-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="a1492-168">Esta característica está en versión preliminar pública y solo está disponible para los clientes que cumplan los requisitos de la pregunta 1.</span><span class="sxs-lookup"><span data-stu-id="a1492-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="a1492-169">6. ¿Cómo puedo proporcionar comentarios?</span><span class="sxs-lookup"><span data-stu-id="a1492-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="a1492-170">Para los comentarios generales, use el icono **Enviar comentarios** en la esquina inferior derecha de la página de supervisión de **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="a1492-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="a1492-171">Para los comentarios sobre incidentes o avisos use el vínculo **¿Es útil esta publicación?**.</span><span class="sxs-lookup"><span data-stu-id="a1492-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="a1492-172">7. ¿Dónde están los datos instrumentados para los escenarios que muestran las tendencias de actividad?</span><span class="sxs-lookup"><span data-stu-id="a1492-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="a1492-173">Los datos se instrumentan en el servicio de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a1492-173">The data is instrumented in the Exchange Online service.</span></span> <span data-ttu-id="a1492-174">Si se produce un error antes de que la solicitud llegue a Exchange Online o existe un error en Exchange Online, verá una caída en la señal de actividad.</span><span class="sxs-lookup"><span data-stu-id="a1492-174">If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>

