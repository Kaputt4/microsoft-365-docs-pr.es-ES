---
title: Conectar su dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo conectar su dominio a Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925115"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="09669-103">Conectar su dominio a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="09669-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="09669-104">Una vez que haya configurado Microsoft 365 y movido los datos de correo electrónico de Google Workspace, puede conectar su dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09669-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="09669-105">Primero tendrá que eliminar los registros DNS existentes de Google y, a continuación, podemos agregar nuevos registros DNS de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09669-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="09669-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="09669-106">Try it!</span></span>

1. <span data-ttu-id="09669-107">Inicie sesión en la consola de administración de Google Workspace [en admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="09669-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="09669-108">Seleccione **Dominios**, **Administrar dominios**, Ver **detalles,** **Administrar dominio** y, a continuación, **DNS** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="09669-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="09669-109">Desplácese hacia abajo **hasta registros sintéticos,** **abra Google Workspace,** **seleccione Eliminar** y, a continuación, **vuelva a** eliminar.</span><span class="sxs-lookup"><span data-stu-id="09669-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="09669-110">Desplácese hacia abajo **hasta Registros** de recursos personalizados y elimine los registros DNS existentes que aparezcan, incluidos los que haya creado anteriormente para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09669-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="09669-111">Vaya al Centro [de administración de Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="09669-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="09669-112">En el panel de navegación izquierdo, elija Mostrar **todo**, **Configuración**, **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="09669-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="09669-113">A continuación, elija su dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="09669-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="09669-114">Seleccione **Continuar configuración** y, a continuación, para conectar su dominio, elija  **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="09669-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="09669-115">Desplácese hacia abajo para ver los registros DNS que deben copiarse en Google.</span><span class="sxs-lookup"><span data-stu-id="09669-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="09669-116">Abra **Registros MX** y, en Puntos para dirección o **valor,** copie el registro.</span><span class="sxs-lookup"><span data-stu-id="09669-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="09669-117">Vuelva a Google y, en la sección Registros de **recursos personalizados,** abra la lista desplegable de tipos de registro y seleccione **MX**.</span><span class="sxs-lookup"><span data-stu-id="09669-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="09669-118">En el **campo** Datos, pegue el registro que copió.</span><span class="sxs-lookup"><span data-stu-id="09669-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="09669-119">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="09669-119">Then select **Add**.</span></span>
1. <span data-ttu-id="09669-120">Repita el proceso para los registros CNAME y TXT y agregue los valores en la página de administración de DNS de Google.</span><span class="sxs-lookup"><span data-stu-id="09669-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="09669-121">Vuelva al Centro de administración de Microsoft 365 y seleccione **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="09669-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="09669-122">La configuración del dominio se ha completado.</span><span class="sxs-lookup"><span data-stu-id="09669-122">Your domain setup is complete.</span></span>