---
title: 'Paso 5: Borrar y bloquear el dispositivo móvil de un antiguo empleado'
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
description: Siga estos pasos para bloquear el acceso a dispositivos móviles de un antiguo empleado.
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244295"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="b3570-103">Paso 5: Borrar y bloquear el dispositivo móvil de un antiguo empleado</span><span class="sxs-lookup"><span data-stu-id="b3570-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="b3570-104">Si tu antiguo empleado tenía un teléfono de la organización, puedes usar el Centro de administración de Exchange para borrar y bloquear ese dispositivo de modo que todos los datos de la organización se quiten del dispositivo y ya no se puedan conectar Office 365.</span><span class="sxs-lookup"><span data-stu-id="b3570-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="b3570-105">Si su organización usa Movilidad y seguridad básicas para administrar dispositivos móviles, puede borrar y bloquear esos dispositivos con Movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="b3570-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="b3570-106">Borrar el dispositivo móvil mediante el centro Exchange administración</span><span class="sxs-lookup"><span data-stu-id="b3570-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="b3570-107">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="b3570-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="b3570-108">En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**.</span><span class="sxs-lookup"><span data-stu-id="b3570-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="b3570-109">Seleccione el usuario y, en **Dispositivos móviles,** seleccione **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="b3570-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="b3570-110">En la **página Detalles del** dispositivo móvil, en **Dispositivos** móviles , seleccione el dispositivo móvil, seleccione **Borrar** dispositivo de borrado de datos y, a ![ continuación, seleccione ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="b3570-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="b3570-111">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b3570-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="b3570-112">Asegúrese de quitar o deshabilitar al usuario de su servicio de Enterprise Blackberry local.</span><span class="sxs-lookup"><span data-stu-id="b3570-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="b3570-113">También debe deshabilitar cualquier dispositivo BlackBerry para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b3570-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="b3570-114">Consulte la BlackBerry Business Cloud Services Administration Guide (Guía de administración de servicios de BlackBerry Business Cloud) si necesita pasos específicos sobre cómo deshabilitar al usuario.</span><span class="sxs-lookup"><span data-stu-id="b3570-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
