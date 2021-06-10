---
title: Agregar el dominio de Google Workspace
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
description: Aprende a mover tu dominio de Google Workspace a Microsoft 365 para empresas.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578776"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="fe388-103">Agregar el dominio de Google Workspace a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe388-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="fe388-104">Agrega tu dominio de Google Workspace a Microsoft 365 para empresas para que puedas seguir usando tu dirección de correo electrónico empresarial.</span><span class="sxs-lookup"><span data-stu-id="fe388-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="fe388-105">¿Se atreve?</span><span class="sxs-lookup"><span data-stu-id="fe388-105">Try it!</span></span>

1. <span data-ttu-id="fe388-106">Vaya al Centro [Microsoft 365 administración.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fe388-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="fe388-107">En el Centro Microsoft 365 administración, en el panel de navegación izquierdo, seleccione **Mostrar** todo , **Configuración** y, a continuación, **Dominios**.</span><span class="sxs-lookup"><span data-stu-id="fe388-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="fe388-108">Elija **Agregar dominio**, escriba su nombre de dominio y seleccione Usar este **dominio**.</span><span class="sxs-lookup"><span data-stu-id="fe388-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="fe388-109">Elija, **Agregue un registro TXT a los registros DNS de dominios,** **seleccione Continuar** y copie el valor TXT.</span><span class="sxs-lookup"><span data-stu-id="fe388-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="fe388-110">Vuelva a la Consola de administración de [Google](https://admin.google.com), elija **Dominios** **,** Administrar dominios , **Ver** detalles , **Administrar** dominio , **DNS** y, a continuación, desplácese hacia abajo hasta Registros de **recursos personalizados.**</span><span class="sxs-lookup"><span data-stu-id="fe388-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="fe388-111">Abra la lista desplegable del tipo de registro, elija **TXT**, pegue el valor TXT que copió y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fe388-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="fe388-112">Por lo general, la actualización toma un hecho en unos minutos, pero puede tardar hasta 48 horas.</span><span class="sxs-lookup"><span data-stu-id="fe388-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="fe388-113">Vuelva al Centro Microsoft 365 administración, **seleccione Comprobar** y, a continuación, **Cierre**.</span><span class="sxs-lookup"><span data-stu-id="fe388-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="fe388-114">Para establecer el dominio como el correo electrónico principal de los usuarios, en el panel de navegación izquierdo, seleccione **Usuarios**  >  **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="fe388-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="fe388-115">Elija un usuario, seleccione **Administrar nombre de usuario y correo** electrónico, **Editar**, seleccione su dominio en la lista desplegable y, a continuación, seleccione **Listo** y **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="fe388-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="fe388-116">Repita este proceso para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="fe388-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="fe388-117">Cuando haya terminado, estará listo para instalar aplicaciones Office y migrar el correo electrónico y los elementos del calendario a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe388-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 