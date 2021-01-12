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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo conectar su dominio a Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794707"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="077b9-103">Conectar su dominio a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="077b9-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="077b9-104">Una vez que haya configurado Microsoft 365 y movido los datos de correo electrónico de Google Workspace, puede conectar su dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="077b9-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="077b9-105">Primero tendrá que eliminar los registros DNS existentes de Google y, a continuación, podemos agregar nuevos registros DNS de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="077b9-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="077b9-106">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="077b9-106">Try it!</span></span>

1. <span data-ttu-id="077b9-107">Inicie sesión en la consola de administración de Google Workspace [en admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="077b9-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="077b9-108">Seleccione **Dominios**, **Administrar dominios**, Ver **detalles,** **Administrar dominio** y, a continuación, **DNS** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="077b9-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="077b9-109">Desplácese hacia abajo **hasta registros sintéticos,** **abra Google Workspace,** **seleccione Eliminar** y, a continuación, **vuelva a** eliminar.</span><span class="sxs-lookup"><span data-stu-id="077b9-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="077b9-110">Desplácese hacia abajo **hasta Registros** de recursos personalizados y elimine los registros DNS existentes que aparezcan, incluidos los que haya creado anteriormente para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="077b9-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="077b9-111">Vaya al Centro [de administración de Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="077b9-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="077b9-112">En el panel de navegación izquierdo, elija Mostrar **todo**, **Configuración**, **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="077b9-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="077b9-113">A continuación, elija su dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="077b9-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="077b9-114">Seleccione **Continuar configuración** y, a continuación, para conectar su dominio, elija  **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="077b9-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="077b9-115">Desplácese hacia abajo para ver los registros DNS que deben copiarse en Google.</span><span class="sxs-lookup"><span data-stu-id="077b9-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="077b9-116">Abra **Registros MX** y, en Puntos para dirección o **valor,** copie el registro.</span><span class="sxs-lookup"><span data-stu-id="077b9-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="077b9-117">Vuelva a Google y, en la sección Registros de **recursos personalizados,** abra la lista desplegable de tipos de registro y seleccione **MX**.</span><span class="sxs-lookup"><span data-stu-id="077b9-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="077b9-118">En el **campo** Datos, pegue el registro que copió.</span><span class="sxs-lookup"><span data-stu-id="077b9-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="077b9-119">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="077b9-119">Then select **Add**.</span></span>
1. <span data-ttu-id="077b9-120">Repita el proceso para los registros CNAME y TXT y agregue los valores en la página de administración de DNS de Google.</span><span class="sxs-lookup"><span data-stu-id="077b9-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="077b9-121">Vuelva al Centro de administración de Microsoft 365 y seleccione **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="077b9-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="077b9-122">La configuración del dominio se ha completado.</span><span class="sxs-lookup"><span data-stu-id="077b9-122">Your domain setup is complete.</span></span>