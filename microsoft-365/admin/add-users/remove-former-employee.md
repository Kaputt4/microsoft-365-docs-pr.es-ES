---
title: 'Quitar un antiguo empleado: información general'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga los pasos de esta solución para quitar un antiguo empleado Microsoft 365 proteger los datos de su organización.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241741"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="065d9-103">Información general: Quitar un antiguo empleado y datos seguros</span><span class="sxs-lookup"><span data-stu-id="065d9-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="065d9-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span><span class="sxs-lookup"><span data-stu-id="065d9-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="065d9-105">En esta serie de artículos se explica cómo bloquear el acceso a Microsoft 365, los pasos que debe seguir para proteger los datos y cómo permitir que otros empleados accedan a los datos.</span><span class="sxs-lookup"><span data-stu-id="065d9-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="065d9-106">Vea un breve vídeo sobre cómo quitar a un empleado.</span><span class="sxs-lookup"><span data-stu-id="065d9-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="065d9-107">Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="065d9-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="065d9-108">Para evitar que un empleado inicia sesión:</span><span class="sxs-lookup"><span data-stu-id="065d9-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="065d9-109">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="065d9-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="065d9-110">Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña.**</span><span class="sxs-lookup"><span data-stu-id="065d9-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="065d9-111">Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="065d9-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="065d9-112">(No se lo envíe).</span><span class="sxs-lookup"><span data-stu-id="065d9-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="065d9-113">Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta,** seleccione **Iniciar la sesión.**</span><span class="sxs-lookup"><span data-stu-id="065d9-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="065d9-114">Debe ser un administrador global para iniciar la sesión.</span><span class="sxs-lookup"><span data-stu-id="065d9-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="065d9-115">Dentro de una hora , o después de salir de la página Microsoft 365 actual en la que se encuentran, se les pedirá que inicien sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="065d9-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="065d9-116">Un token de acceso es bueno durante una hora, por lo que la escala de tiempo depende de cuánto tiempo queda en ese token y de si navegan fuera de su página web actual.</span><span class="sxs-lookup"><span data-stu-id="065d9-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="065d9-117">Aunque hemos numerado los pasos de esta solución y no tiene que completar la solución con el orden exacto, se recomienda realizar los pasos de esta manera.</span><span class="sxs-lookup"><span data-stu-id="065d9-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="065d9-118">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="065d9-118">Before you begin</span></span>

<span data-ttu-id="065d9-119">Debe ser un administrador global para completar los pasos de esta solución.</span><span class="sxs-lookup"><span data-stu-id="065d9-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="065d9-120">**Paso**</span><span class="sxs-lookup"><span data-stu-id="065d9-120">**Step**</span></span> <br/> |<span data-ttu-id="065d9-121">**Por qué se debe realizar este procedimiento**</span><span class="sxs-lookup"><span data-stu-id="065d9-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="065d9-122">Paso 1: impedir que un antiguo empleado inicia sesión y bloquee el acceso a Microsoft 365 servicios</span><span class="sxs-lookup"><span data-stu-id="065d9-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="065d9-123">Esto bloquea el inicio de sesión de su antiguo empleado Microsoft 365 e impide que la persona acceda a Microsoft 365 servicios.</span><span class="sxs-lookup"><span data-stu-id="065d9-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="065d9-124">Paso 2: Guardar el contenido del buzón de un antiguo empleado</span><span class="sxs-lookup"><span data-stu-id="065d9-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="065d9-125">Esto es útil para la persona que va a asumir el trabajo del empleado, o si hay litigio.</span><span class="sxs-lookup"><span data-stu-id="065d9-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="065d9-126">Paso 3: Reenviar el correo electrónico de un antiguo empleado a otro empleado o convertirlo a un buzón compartido</span><span class="sxs-lookup"><span data-stu-id="065d9-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="065d9-p104">Esta opción permite mantener activa la dirección de correo electrónico de su antiguo empleado. Si tiene clientes o socios que siguen enviando correos electrónicos a la dirección del antiguo empleado, con esta opción el correo llegará a la persona que ahora se encarga del trabajo.</span><span class="sxs-lookup"><span data-stu-id="065d9-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="065d9-129">Paso 4: Dar a otro empleado acceso a OneDrive y Outlook datos</span><span class="sxs-lookup"><span data-stu-id="065d9-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="065d9-130">Si solo quita la licencia de un usuario, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.</span><span class="sxs-lookup"><span data-stu-id="065d9-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="065d9-131">Antes de eliminar la cuenta, debe dar acceso a sus OneDrive y Outlook a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="065d9-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="065d9-132">Después de eliminar la cuenta de un empleado, el contenido de su OneDrive y Outlook se conserva durante **30** días.</span><span class="sxs-lookup"><span data-stu-id="065d9-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="065d9-133">Sin embargo, durante esos 30 días, puede restaurar la cuenta del usuario y obtener acceso a su contenido.</span><span class="sxs-lookup"><span data-stu-id="065d9-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="065d9-134">Si restaura la cuenta del usuario, el contenido OneDrive y Outlook seguirá siendo accesible para usted incluso después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="065d9-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="065d9-135">Paso 5: Borrar y bloquear el dispositivo móvil de un antiguo empleado</span><span class="sxs-lookup"><span data-stu-id="065d9-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="065d9-136">Quita los datos profesionales del teléfono o de la tableta.</span><span class="sxs-lookup"><span data-stu-id="065d9-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="065d9-137">Paso 6: Quitar y eliminar la Microsoft 365 de un antiguo empleado</span><span class="sxs-lookup"><span data-stu-id="065d9-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="065d9-p106">Cuando quita una licencia, puede asignarla a otra persona. O bien, puede eliminar la licencia para no pagar por ella hasta que contrate a otra persona.  </span><span class="sxs-lookup"><span data-stu-id="065d9-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="065d9-p107">Al quitar o eliminar una licencia, el correo electrónico, los contactos y el calendario antiguos del usuario se conservan durante **30 días** y, después, se eliminan permanentemente. Si quita o elimina una licencia, pero no elimina la cuenta, podrá obtener acceso al contenido de OneDrive del usuario incluso hasta 30 días después.  </span><span class="sxs-lookup"><span data-stu-id="065d9-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="065d9-142">Paso 7: Eliminar la cuenta de usuario de un antiguo empleado</span><span class="sxs-lookup"><span data-stu-id="065d9-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="065d9-143">Esto quita la cuenta del centro de administración.</span><span class="sxs-lookup"><span data-stu-id="065d9-143">This removes the account from your admin center.</span></span> <span data-ttu-id="065d9-144">Mantiene todo organizado.</span><span class="sxs-lookup"><span data-stu-id="065d9-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="065d9-145">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="065d9-145">Related articles</span></span>

[<span data-ttu-id="065d9-146">Restaurar un usuario</span><span class="sxs-lookup"><span data-stu-id="065d9-146">Restore a user</span></span>](restore-user.md)
