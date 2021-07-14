---
title: Investigar las alertas de detección de anomalías
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Investigar las alertas de detección de anomalías.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420475"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="f7325-103">Investigar las alertas de detección de anomalías</span><span class="sxs-lookup"><span data-stu-id="f7325-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="f7325-104">El gobierno de aplicaciones de Microsoft proporciona detecciones de seguridad y alertas de actividades maliciosas.</span><span class="sxs-lookup"><span data-stu-id="f7325-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="f7325-105">El objetivo de esta guía es proporcionarle información general y práctica sobre cada alerta, para ayudarle en sus tareas de investigación y corrección.</span><span class="sxs-lookup"><span data-stu-id="f7325-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="f7325-106">En esta guía se incluye información general sobre las condiciones de activación de las alertas.</span><span class="sxs-lookup"><span data-stu-id="f7325-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="f7325-107">Dado que las detecciones de anomalías no son deterministas por naturaleza, sólo se activan cuando hay un comportamiento que se desvía de la norma.</span><span class="sxs-lookup"><span data-stu-id="f7325-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="f7325-108">Por último, algunas alertas pueden estar en previsión, así que revise regularmente la documentación oficial para conocer el estado actualizado de las alertas.</span><span class="sxs-lookup"><span data-stu-id="f7325-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="f7325-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="f7325-109">MITRE ATT&CK</span></span>

<span data-ttu-id="f7325-110">Para facilitar la relación entre las alertas de gobernanza de aplicaciones de Microsoft y la conocida matriz ATT&CK de MITRE, hemos clasificado las alertas según su correspondiente táctica ATT&CK de MITRE.</span><span class="sxs-lookup"><span data-stu-id="f7325-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="f7325-111">Esta referencia adicional facilita la comprensión de la técnica de ataque sospechosa potencialmente en uso cuando se activa la alerta de Microsoft Application Security and Governance.</span><span class="sxs-lookup"><span data-stu-id="f7325-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="f7325-112">Esta guía proporciona información sobre cómo investigar y solucionar las alertas de gobernanza de aplicaciones de Microsoft en las siguientes categorías.</span><span class="sxs-lookup"><span data-stu-id="f7325-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="f7325-113">Acceso inicial</span><span class="sxs-lookup"><span data-stu-id="f7325-113">Initial Access</span></span>
- <span data-ttu-id="f7325-114">Ejecución</span><span class="sxs-lookup"><span data-stu-id="f7325-114">Execution</span></span>
- <span data-ttu-id="f7325-115">Persistencia</span><span class="sxs-lookup"><span data-stu-id="f7325-115">Persistence</span></span>
- <span data-ttu-id="f7325-116">Elevación de privilegios</span><span class="sxs-lookup"><span data-stu-id="f7325-116">Privilege Escalation</span></span>
- <span data-ttu-id="f7325-117">Evasión de defensa</span><span class="sxs-lookup"><span data-stu-id="f7325-117">Defense Evasion</span></span>
- <span data-ttu-id="f7325-118">Acceso a credenciales</span><span class="sxs-lookup"><span data-stu-id="f7325-118">Credential Access</span></span>
- <span data-ttu-id="f7325-119">Colección</span><span class="sxs-lookup"><span data-stu-id="f7325-119">Collection</span></span>
- <span data-ttu-id="f7325-120">Exfiltración</span><span class="sxs-lookup"><span data-stu-id="f7325-120">Exfiltration</span></span>
- <span data-ttu-id="f7325-121">Impacto</span><span class="sxs-lookup"><span data-stu-id="f7325-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="f7325-122">Clasificación de las alertas de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7325-122">Security alert classifications</span></span>

<span data-ttu-id="f7325-123">Tras una investigación adecuada, todas las alertas de gobernanza de aplicaciones de Microsoft pueden clasificarse como uno de los siguientes tipos de actividad:</span><span class="sxs-lookup"><span data-stu-id="f7325-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="f7325-124">Verdadero positivo (TP): una alerta sobre una actividad maliciosa confirmada.</span><span class="sxs-lookup"><span data-stu-id="f7325-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="f7325-125">Verdadero positivo benigno (B-TP): una alerta sobre una actividad sospechosa pero no maliciosa, como una prueba de penetración u otra acción sospechosa autorizada.</span><span class="sxs-lookup"><span data-stu-id="f7325-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="f7325-126">Falso positivo (FP): una alerta sobre una actividad no maliciosa.</span><span class="sxs-lookup"><span data-stu-id="f7325-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="f7325-127">Pasos generales de la investigación</span><span class="sxs-lookup"><span data-stu-id="f7325-127">General investigation steps</span></span>

<span data-ttu-id="f7325-128">Utilice las siguientes directrices generales cuando investigue cualquier tipo de alerta para obtener una comprensión más clara de la amenaza potencial antes de aplicar la acción recomendada.</span><span class="sxs-lookup"><span data-stu-id="f7325-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="f7325-129">Revise el nivel de gravedad de la aplicación y compárelo con el resto de la aplicación en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="f7325-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="f7325-130">Esta revisión le ayudará a identificar qué aplicaciones de su inquilino suponen un mayor riesgo.</span><span class="sxs-lookup"><span data-stu-id="f7325-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="f7325-131">Si identifica un TP, revise todas las actividades de la aplicación para comprender el impacto.</span><span class="sxs-lookup"><span data-stu-id="f7325-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="f7325-132">Por ejemplo, revise la siguiente información de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="f7325-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="f7325-133">Ámbitos de acceso concedidos</span><span class="sxs-lookup"><span data-stu-id="f7325-133">Scopes granted access</span></span>
  - <span data-ttu-id="f7325-134">Comportamiento inusual</span><span class="sxs-lookup"><span data-stu-id="f7325-134">Unusual behavior</span></span>  
  - <span data-ttu-id="f7325-135">Dirección IP y ubicación</span><span class="sxs-lookup"><span data-stu-id="f7325-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="f7325-136">Alertas de acceso inicial</span><span class="sxs-lookup"><span data-stu-id="f7325-136">Initial access alerts</span></span>

<span data-ttu-id="f7325-137">Esta sección describe las alertas que indican que una aplicación maliciosa puede estar intentando mantenerse en su organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="f7325-138">Nombre de la aplicación codificado con ámbitos de consentimiento sospechosos</span><span class="sxs-lookup"><span data-stu-id="f7325-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="f7325-139">**Gravedad:** media</span><span class="sxs-lookup"><span data-stu-id="f7325-139">**Severity:** Medium</span></span>

<span data-ttu-id="f7325-140">**Descripción**: esta detección identifica aplicaciones OAuth con caracteres, como Unicode o caracteres codificados, solicitados para ámbitos de consentimiento sospechosos y que accedieron a las carpetas de correo de los usuarios a través de la Graph API.</span><span class="sxs-lookup"><span data-stu-id="f7325-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="f7325-141">Esta alerta puede indicar un intento de camuflar una aplicación maliciosa como una aplicación conocida y de confianza para que los adversarios puedan engañar a los usuarios para que den su consentimiento a la aplicación maliciosa.</span><span class="sxs-lookup"><span data-stu-id="f7325-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="f7325-142">**¿TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="f7325-142">**TP or FP?**</span></span>

- <span data-ttu-id="f7325-143">**TP**: si puede confirmar que la aplicación de OAuth ha codificado el nombre para mostrar con ámbitos sospechosos entregados desde un origen desconocido, se indica un verdadero positivo.</span><span class="sxs-lookup"><span data-stu-id="f7325-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="f7325-144">**Acción recomendada**: revise el nivel de permiso solicitado por esta aplicación y los usuarios a los que se les ha concedido acceso.</span><span class="sxs-lookup"><span data-stu-id="f7325-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="f7325-145">Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="f7325-146">Para prohibir el acceso a la aplicación, en la página de aplicaciones OAuth, en la fila en la que aparece la aplicación que quieres prohibir, selecciona el icono de prohibición.</span><span class="sxs-lookup"><span data-stu-id="f7325-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="f7325-147">Puedes elegir si quieres informar a los usuarios de que la aplicación que instalaron y autorizaron ha sido prohibida.</span><span class="sxs-lookup"><span data-stu-id="f7325-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="f7325-148">La notificación permite a los usuarios saber que la aplicación se desactivará y no tendrán acceso a la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="f7325-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="f7325-149">Si no quiere que lo sepan, anule la selección de la opción Notificar a los usuarios que han concedido acceso a esta aplicación prohibida en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f7325-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="f7325-150">Le recomendamos que haga saber a los usuarios de la aplicación que su uso está a punto de ser prohibido.</span><span class="sxs-lookup"><span data-stu-id="f7325-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="f7325-151">**FP**: si debe confirmar que la aplicación tiene un nombre codificado pero tiene un uso empresarial legítimo en la organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="f7325-152">**Acción recomendada**: descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="f7325-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f7325-153">Comprender el alcance de la infracción</span><span class="sxs-lookup"><span data-stu-id="f7325-153">Understand the scope of the breach</span></span>

<span data-ttu-id="f7325-154">Siga el tutorial sobre cómo [investigar aplicaciones de OAuth de riesgo](/cloud-app-security/investigate-risky-oauth).</span><span class="sxs-lookup"><span data-stu-id="f7325-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="f7325-155">La aplicación OAuth con ámbitos de lectura tiene una URL de respuesta sospechosa</span><span class="sxs-lookup"><span data-stu-id="f7325-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="f7325-156">**Gravedad**: media</span><span class="sxs-lookup"><span data-stu-id="f7325-156">**Severity**: Medium</span></span>

<span data-ttu-id="f7325-157">**Descripción**: esta detección identifica una aplicación OAuth con sólo ámbitos de lectura como User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared que redirige a una URL de respuesta sospechosa a través de Graph API.</span><span class="sxs-lookup"><span data-stu-id="f7325-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="f7325-158">Esta actividad intenta indicar que una aplicación maliciosa con permisos de menor privilegio (como los ámbitos de lectura) podría ser explotada para llevar a cabo el reconocimiento de la cuenta de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f7325-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="f7325-159">**¿TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="f7325-159">**TP or FP?**</span></span>

- <span data-ttu-id="f7325-160">**TP**: si puede confirmar que la aplicación OAuth con alcance de lectura se entrega desde una fuente desconocida, y redirige a una URL sospechosa, entonces se indica un verdadero positivo.</span><span class="sxs-lookup"><span data-stu-id="f7325-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="f7325-161">**Acción recomendada**: revise la URL de respuesta y los ámbitos solicitados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="f7325-162">Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="f7325-163">Revise el nivel de permiso solicitado por esta aplicación y qué usuarios han concedido el acceso.</span><span class="sxs-lookup"><span data-stu-id="f7325-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="f7325-164">Para prohibir el acceso a la aplicación, en la página de aplicaciones OAuth, en la fila en la que aparece la aplicación que quieres prohibir, selecciona el icono de prohibición.</span><span class="sxs-lookup"><span data-stu-id="f7325-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="f7325-165">Puedes elegir si quieres informar a los usuarios de que la aplicación que instalaron y autorizaron ha sido prohibida.</span><span class="sxs-lookup"><span data-stu-id="f7325-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="f7325-166">La notificación permite a los usuarios saber que la aplicación se desactivará y no tendrán acceso a la aplicación conectada.</span><span class="sxs-lookup"><span data-stu-id="f7325-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="f7325-167">Si no quiere que lo sepan, anule la selección de la opción Notificar a los usuarios que han concedido acceso a esta aplicación prohibida en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f7325-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="f7325-168">Le recomendamos que haga saber a los usuarios de la aplicación que su uso está a punto de ser prohibido.</span><span class="sxs-lookup"><span data-stu-id="f7325-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="f7325-169">**FP**: Si tras la investigación, puede confirmar que la aplicación tiene un uso empresarial legítimo en la organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="f7325-170">**Acción recomendada**: descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="f7325-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f7325-171">Comprender el alcance de la infracción</span><span class="sxs-lookup"><span data-stu-id="f7325-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="f7325-172">Revise todas las actividades realizadas por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="f7325-173">Si sospecha de una aplicación, le recomendamos que investigue el nombre de la aplicación y la URL de respuesta en diferentes tiendas de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f7325-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="f7325-174">Cuando compruebe las tiendas de aplicaciones, céntrese en los siguientes tipos de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="f7325-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="f7325-175">Aplicaciones que se han creado recientemente.</span><span class="sxs-lookup"><span data-stu-id="f7325-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="f7325-176">Aplicaciones con una URL de respuesta sospechosa</span><span class="sxs-lookup"><span data-stu-id="f7325-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="f7325-177">Aplicaciones que no han sido actualizadas recientemente.</span><span class="sxs-lookup"><span data-stu-id="f7325-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="f7325-178">La falta de actualizaciones puede indicar que la aplicación ya no es compatible.</span><span class="sxs-lookup"><span data-stu-id="f7325-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="f7325-179">Si todavía sospecha que una aplicación es sospechosa, puede investigar el nombre de la aplicación, el nombre del editor y la URL de respuesta en línea</span><span class="sxs-lookup"><span data-stu-id="f7325-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="f7325-180">Alertas de persistencia</span><span class="sxs-lookup"><span data-stu-id="f7325-180">Persistence alerts</span></span>

<span data-ttu-id="f7325-181">Esta sección describe las alertas que indican que un actor malicioso puede estar intentando mantener su posición en su organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="f7325-182">La aplicación con un ámbito de OAuth sospechoso crea una regla de entrada</span><span class="sxs-lookup"><span data-stu-id="f7325-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="f7325-183">**Gravedad**: media</span><span class="sxs-lookup"><span data-stu-id="f7325-183">**Severity**: Medium</span></span>

<span data-ttu-id="f7325-184">**Id. MITRE ID**: T1137.005, T1114</span><span class="sxs-lookup"><span data-stu-id="f7325-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="f7325-185">Esta detección identifica una aplicación OAuth que consiente ámbitos sospechosos, crea una regla de bandeja de entrada sospechosa y luego accede a las carpetas de correo de los usuarios y a los mensajes a través de la Graph API.</span><span class="sxs-lookup"><span data-stu-id="f7325-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="f7325-186">Las reglas de la bandeja de entrada, como el reenvío de todos los correos electrónicos o de algunos específicos a otra cuenta de correo electrónico, y las llamadas de Graph para acceder a los correos electrónicos y enviarlos a otra cuenta de correo electrónico, pueden ser un intento de filtrar información de su organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="f7325-187">**¿TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="f7325-187">**TP or FP?**</span></span>

- <span data-ttu-id="f7325-188">**TP**: si puede confirmar que la regla de la bandeja de entrada fue creada por una aplicación de terceros OAuth con alcances sospechosos entregados desde una fuente desconocida, entonces se indica un verdadero positivo.</span><span class="sxs-lookup"><span data-stu-id="f7325-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="f7325-189">**Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="f7325-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="f7325-190">Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory y siga el tutorial sobre cómo quitar la regla de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="f7325-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="f7325-191">**FP**: Si puede confirmar que la aplicación creó una regla de bandeja de entrada a una cuenta de correo electrónico externa nueva o personal por razones legítimas.</span><span class="sxs-lookup"><span data-stu-id="f7325-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="f7325-192">**Acción recomendada**: descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="f7325-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f7325-193">Comprender el alcance de la infracción</span><span class="sxs-lookup"><span data-stu-id="f7325-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="f7325-194">Revise todas las actividades realizadas por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="f7325-195">Revise los alcances otorgados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="f7325-196">Revise la acción y la condición de la regla de entrada creada por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="f7325-197">Alertas de recopilación</span><span class="sxs-lookup"><span data-stu-id="f7325-197">Collection alerts</span></span>

<span data-ttu-id="f7325-198">Esta sección describe las alertas que indican que un actor malicioso puede estar intentando recopilar datos de interés para su objetivo desde su organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="f7325-199">La aplicación hizo llamadas anómalas a Graph para leer el correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f7325-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="f7325-200">**Gravedad**: media</span><span class="sxs-lookup"><span data-stu-id="f7325-200">**Severity**: Medium</span></span>

<span data-ttu-id="f7325-201">**Id. MITRE**: T1114</span><span class="sxs-lookup"><span data-stu-id="f7325-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="f7325-202">Esta detección identifica cuando la aplicación OAuth de la línea de negocio (LOB) accede a un volumen inusual y elevado de carpetas de correo y mensajes de los usuarios a través de la Graph API, lo que puede indicar un intento de violación de su organización.</span><span class="sxs-lookup"><span data-stu-id="f7325-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="f7325-203">**¿TP o FP?**</span><span class="sxs-lookup"><span data-stu-id="f7325-203">**TP or FP?**</span></span>

- <span data-ttu-id="f7325-204">**TP**: si puede confirmar que la actividad gráfica inusual fue realizada por la aplicación OAuth de la línea de negocio (LOB), entonces se indica un verdadero positivo.</span><span class="sxs-lookup"><span data-stu-id="f7325-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="f7325-205">**Acciones recomendadas**: deshabilite temporalmente la aplicación, restablezca la contraseña y vuelva a habilitarla.</span><span class="sxs-lookup"><span data-stu-id="f7325-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="f7325-206">Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f7325-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="f7325-207">**FP**: si puede confirmar que la aplicación está destinada a hacer un volumen inusualmente alto de llamadas gráficas.</span><span class="sxs-lookup"><span data-stu-id="f7325-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="f7325-208">**Acción recomendada**: descartar la alerta.</span><span class="sxs-lookup"><span data-stu-id="f7325-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f7325-209">Comprender el alcance de la infracción</span><span class="sxs-lookup"><span data-stu-id="f7325-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="f7325-210">Revise el registro de actividad de los eventos realizados por esta aplicación para obtener una mejor comprensión de otras actividades de Graph para leer correos electrónicos e intentar recopilar información de correo electrónico confidencial de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f7325-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="f7325-211">Supervisa si se agregan credenciales inesperadas a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7325-211">Monitor for unexpected credential being added to the app.</span></span>
