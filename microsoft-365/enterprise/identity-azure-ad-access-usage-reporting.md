---
title: 'Paso 13: Supervisar la actividad de inicio de sesión y del espacio empresarial'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure los informes de uso y acceso de Azure AD.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871145"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="c7c94-103">Paso 13: Supervisar la actividad de inicio de sesión y del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="c7c94-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="c7c94-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c7c94-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c7c94-p101">En este paso, revisará los registros de auditoría y la actividad de inicio de sesión con los informes de Azure AD. Hay disponibles dos tipos de informes.</span><span class="sxs-lookup"><span data-stu-id="c7c94-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="c7c94-p102">El **Informe de actividades de registros de auditoría** registra el historial de todas las tareas realizadas en el espacio empresarial de Azure AD. Este informe responde a preguntas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7c94-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="c7c94-109">¿Quién agregó a un usuario a un grupo de administradores?</span><span class="sxs-lookup"><span data-stu-id="c7c94-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="c7c94-110">¿Qué usuarios inician sesión en una aplicación específica?</span><span class="sxs-lookup"><span data-stu-id="c7c94-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="c7c94-111">¿Cuántos restablecimientos de contraseña se producen?</span><span class="sxs-lookup"><span data-stu-id="c7c94-111">How many password resets are happening?</span></span>

<span data-ttu-id="c7c94-p103">El **Informe de actividades de inicios de sesión** registra quién realizó las tareas incluidas en el informe de registros de auditoría. Este informe responde a preguntas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7c94-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="c7c94-114">Para un usuario específico que esté bajo investigación, ¿cuál es su patrón de inicio de sesión?</span><span class="sxs-lookup"><span data-stu-id="c7c94-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="c7c94-115">¿Cuál es mi volumen de inicios de sesión en un día, semana o mes?</span><span class="sxs-lookup"><span data-stu-id="c7c94-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="c7c94-116">¿Cuántos de estos intentos de inicio de sesión no fueron correctos y para qué cuentas?</span><span class="sxs-lookup"><span data-stu-id="c7c94-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="c7c94-117">Para obtener más información sobre los informes y obtener acceso a ellos, vea [Informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c7c94-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="c7c94-118">Como resultado de este paso, obtendrá información sobre estos informes y conocerá cómo puede usarlos para comprender en profundidad los eventos y actividades de Azure AD con fines de planeamiento y seguridad.</span><span class="sxs-lookup"><span data-stu-id="c7c94-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="c7c94-119">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c7c94-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="c7c94-120">Permitir a los usuarios crear y administrar sus propios grupos</span><span class="sxs-lookup"><span data-stu-id="c7c94-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
