---
title: Integración de Cortana con Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 'Obtenga información sobre cómo usar Cortana, cuando se integra con Office 365. Puede desactivar Cortana en el centro de administración para restringir el acceso a los datos de la organización. '
ms.openlocfilehash: 21de80d127498dd40db932923a8d650b87b8a24c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257421"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="aee24-104">Cortana en Office 365</span><span class="sxs-lookup"><span data-stu-id="aee24-104">Cortana in Office 365</span></span>

<span data-ttu-id="aee24-105">Cortana es un asistente digital basado en la nube y un servicio de Microsoft 365 y Office 365 que funciona en todos los dispositivos y servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aee24-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="aee24-106">Cortana puede usar la información almacenada en Microsoft 365 y Office 365 para ayudar a los usuarios de su organización a mantenerse al día y obtener información, tareas sugeridas y ayuda con sus reuniones, documentos y contactos.</span><span class="sxs-lookup"><span data-stu-id="aee24-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="aee24-107">Información para administradores</span><span class="sxs-lookup"><span data-stu-id="aee24-107">Info for admins</span></span>

<span data-ttu-id="aee24-108">El cumplimiento es un compromiso que Microsoft realiza a los clientes de la empresa.</span><span class="sxs-lookup"><span data-stu-id="aee24-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="aee24-109">Obtenga más información sobre Microsoft Compliance Framework.</span><span class="sxs-lookup"><span data-stu-id="aee24-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="aee24-110">Al igual que otros servicios de Microsoft 365 y Office 365, las características de Cortana compatibles están protegidas y protegidas de acuerdo con los términos del servicio en línea que incluyen un conjunto de promesas que implican la protección de los datos de los usuarios contra pérdidas accidentales, alteraciones revelación o acceso no autorizado o destrucción ilícita.</span><span class="sxs-lookup"><span data-stu-id="aee24-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="aee24-111">Todas las demás características de Cortana (es decir, los servicios conectados opcionales de Cortana) están sujetas al [contrato de servicios de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=2109174) y a la declaración de privacidad de [Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span><span class="sxs-lookup"><span data-stu-id="aee24-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="aee24-112">Los servicios de Cortana se dividen en dos categorías de datos, servicios **compatibles** y **opcionales conectados**, que puede controlar.</span><span class="sxs-lookup"><span data-stu-id="aee24-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="aee24-113">Desactivar los servicios conectados opcionales de Cortana</span><span class="sxs-lookup"><span data-stu-id="aee24-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="aee24-114">Los servicios conectados opcionales de Cortana pueden desactivarse para los empleados de su organización.</span><span class="sxs-lookup"><span data-stu-id="aee24-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="aee24-115">Se deshabilitarán los servicios conectados opcionales de Cortana en Cortana en Windows y la aplicación móvil de Cortana.</span><span class="sxs-lookup"><span data-stu-id="aee24-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="aee24-116">Esto incluye avisos de Cortana, listas, tareas y otras características.</span><span class="sxs-lookup"><span data-stu-id="aee24-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="aee24-117">Los servicios de la categoría compatible (es decir, las experiencias de Cortana OST), como el correo electrónico informativo de Cortana, y reproducir mis correos electrónicos en Outlook Mobile, seguirán activos.</span><span class="sxs-lookup"><span data-stu-id="aee24-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="aee24-118">En el centro de administración de Microsoft 365, seleccione**configuración** de **configuración** > y seleccione **Cortana**.</span><span class="sxs-lookup"><span data-stu-id="aee24-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="aee24-119">Active la casilla **permitir que Cortana las experiencias conectadas opcionales usen los datos hospedados de Microsoft de su organización** para habilitar o deshabilitar la experiencia conectada de Cortana.</span><span class="sxs-lookup"><span data-stu-id="aee24-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="aee24-120">Seleccione **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="aee24-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="aee24-121">Desactivar experiencias de OST de Cortana</span><span class="sxs-lookup"><span data-stu-id="aee24-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="aee24-122">Los empleados de la organización pueden optar por no participar en la experiencia OST de Cortana siguiendo los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="aee24-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="aee24-123">Abra Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="aee24-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="aee24-124">Vaya a **configuración**.</span><span class="sxs-lookup"><span data-stu-id="aee24-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="aee24-125">Seleccione **reproducir mis mensajes de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="aee24-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="aee24-126">Mueva el botón de alternancia a desactivado en las cuentas que desea deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="aee24-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="aee24-127">Correo electrónico de informe</span><span class="sxs-lookup"><span data-stu-id="aee24-127">Briefing email</span></span>

<span data-ttu-id="aee24-128">La deshabilitación de Cortana en la barra de tareas no deshabilita el correo electrónico de informe de Cortana.</span><span class="sxs-lookup"><span data-stu-id="aee24-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="aee24-129">Los empleados deben cancelar su suscripción de forma individual.</span><span class="sxs-lookup"><span data-stu-id="aee24-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="aee24-130">Las personas de su organización pueden optar por el correo electrónico del informe de Cortana seleccionando **Cancelar suscripción** en el pie de página del mensaje.</span><span class="sxs-lookup"><span data-stu-id="aee24-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>