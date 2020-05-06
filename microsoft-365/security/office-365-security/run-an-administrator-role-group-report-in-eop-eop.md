---
title: Ejecutar un informe de grupo de roles de administrador en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a ejecutar un informe de grupo de roles de administrador en Exchange Online Protection (EOP).
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034461"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="68c21-103">Ejecutar un informe de grupo de roles de administrador en EOP</span><span class="sxs-lookup"><span data-stu-id="68c21-103">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="68c21-104">Cuando un administrador agrega o quita miembros de grupos de roles de administrador, Exchange Online Protection (EOP) registra cada ocurrencia.</span><span class="sxs-lookup"><span data-stu-id="68c21-104">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="68c21-105">Al ejecutar un informe de grupo de roles de administrador en el centro de administración de Exchange (EAC), las entradas se muestran como resultados de búsqueda e incluyen los grupos de funciones afectados, quién cambió la pertenencia al grupo de roles y cuándo se realizaron las actualizaciones de pertenencia.</span><span class="sxs-lookup"><span data-stu-id="68c21-105">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="68c21-106">Use este informe para supervisar los cambios en los permisos administrativos asignados a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="68c21-106">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="68c21-107">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="68c21-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="68c21-108">Tiempo estimado para finalizar: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="68c21-108">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="68c21-109">Para abrir el centro de administración de Exchange, vea [centro de administración de Exchange en Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="68c21-109">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="68c21-p102">Deberá tener asignados permisos antes de poder llevar a cabo este procedimiento o procedimientos. Para ver qué permisos necesita, consulte el Sección "Informes" del tema [Permisos de características en EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="68c21-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="68c21-112">Para obtener información acerca de los métodos abreviados de teclado que se pueden aplicar a los procedimientos de este tema, consulte [métodos abreviados de teclado para el centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="68c21-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="68c21-113">¿Problemas?</span><span class="sxs-lookup"><span data-stu-id="68c21-113">Having problems?</span></span> <span data-ttu-id="68c21-114">Solicite ayuda en el foro de [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="68c21-114">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="68c21-115">Usar el EAC para ejecutar un informe de grupo de roles de administrador</span><span class="sxs-lookup"><span data-stu-id="68c21-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="68c21-116">Ejecute el informe de grupo de roles de administrador para buscar los cambios en los grupos de roles de administración de la organización dentro de un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="68c21-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="68c21-117">En el EAC, vaya a **Administración de cumplimiento** \> **Auditoría** y haga clic en **Ejecutar un informe de grupo de roles de administrador**.</span><span class="sxs-lookup"><span data-stu-id="68c21-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="68c21-p104">Elija la **Fecha de inicio** y la **Fecha de finalización**. De manera predeterminada, el informe busca los cambios efectuados en los grupos de roles de administrador en las últimas dos semanas.</span><span class="sxs-lookup"><span data-stu-id="68c21-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="68c21-p105">Para ver los cambios de un determinado grupo de roles, haga clic en **Seleccionar grupos de roles**. Seleccione el grupo o los grupos de roles en el siguiente cuadro de diálogo y haga clic en **Aceptar**. También puede dejar el campo en blanco para buscar todos los grupos de roles cambiados.</span><span class="sxs-lookup"><span data-stu-id="68c21-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="68c21-123">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="68c21-123">Click **Search**.</span></span>

<span data-ttu-id="68c21-p106">Si se encuentran cambios con los criterios especificados, aparecerán en el panel de resultados. Haga clic en un grupo de roles de los resultados de la búsqueda para ver los cambios en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="68c21-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="68c21-126">¿Cómo saber si el proceso se ha completado correctamente?</span><span class="sxs-lookup"><span data-stu-id="68c21-126">How do you know this worked?</span></span>

<span data-ttu-id="68c21-p107">Si se ejecutó correctamente un informe de grupo de roles de administrador, los grupos de roles que cambiaron dentro del intervalo de fechas se muestran en el panel de resultados de la búsqueda. Si no hay resultados, entonces no se hicieron cambios a los grupos de funciones dentro del intervalo de fechas especificado. Si cree que debería haber resultados, cambie el intervalo de fechas y vuelva a ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="68c21-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="68c21-130">Supervisión de cambios en la pertenencia a grupos de funciones</span><span class="sxs-lookup"><span data-stu-id="68c21-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="68c21-p108">Cuando se agregan miembros a un grupo de funciones, o se quitan de él, los resultados de la búsqueda mostrados en el panel de detalles indican que la pertenencia al grupo de funciones se ha actualizado y enumera los miembros actuales. En los resultados no se indica explícitamente el usuario que se agregó o quitó.</span><span class="sxs-lookup"><span data-stu-id="68c21-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="68c21-p109">Para determinar si un usuario se agregó o quitó, tiene que comparar dos entradas independientes en el informe. Por ejemplo, veamos las siguientes entradas de registro para el grupo de roles **Servicio de asistencia**:</span><span class="sxs-lookup"><span data-stu-id="68c21-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="68c21-135">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="68c21-135">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="68c21-136">Administrador</span><span class="sxs-lookup"><span data-stu-id="68c21-136">Administrator</span></span> <br> <span data-ttu-id="68c21-137">Miembros actualizados: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="68c21-137">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="68c21-138">2/06/2018 10:09 A.M.</span><span class="sxs-lookup"><span data-stu-id="68c21-138">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="68c21-139">Administrador</span><span class="sxs-lookup"><span data-stu-id="68c21-139">Administrator</span></span> <br> <span data-ttu-id="68c21-140">Miembros actualizados: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="68c21-140">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="68c21-141">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="68c21-141">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="68c21-142">Administrador</span><span class="sxs-lookup"><span data-stu-id="68c21-142">Administrator</span></span> <br> <span data-ttu-id="68c21-143">Miembros actualizados: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="68c21-143">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="68c21-144">En este ejemplo, la cuenta de usuario Administrador realizó los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="68c21-144">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="68c21-145">El 2/06/2018 agrega el usuario tonip.</span><span class="sxs-lookup"><span data-stu-id="68c21-145">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="68c21-146">El 2/19/2018, eliminó el usuario pilarp.</span><span class="sxs-lookup"><span data-stu-id="68c21-146">On 2/19/2018, they removed the user pilarp.</span></span>
