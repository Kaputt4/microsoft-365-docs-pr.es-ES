---
title: Anclar aplicaciones al iniciador de aplicaciones de los usuarios
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Como administrador global, puede anclar hasta tres aplicaciones al iniciador de aplicaciones de los usuarios.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310880"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="845f3-103">Anclar aplicaciones al iniciador de aplicaciones de los usuarios</span><span class="sxs-lookup"><span data-stu-id="845f3-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="845f3-104">Puede usar controles en el portal de Azure Active Directory para anclar hasta tres aplicaciones a Office.com y el iniciador de aplicaciones para todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="845f3-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="845f3-105">También puede organizar grupos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="845f3-105">You can also organize groups of applications.</span></span> <span data-ttu-id="845f3-106">Más adelante, el usuario podrá desanclar cualquier aplicación que agregue en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="845f3-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="845f3-107">Para anclar una aplicación a los usuarios, debe ser un administrador de la aplicación de nube o un administrador de aplicaciones en Azure Active Directory, o un administrador global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="845f3-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="845f3-108">Para obtener más información acerca de los roles de administrador, vea [roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) y [roles de administrador en Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="845f3-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="845f3-109">Para obtener más información sobre el iniciador de aplicaciones y Office.com, vea [reunirse con el iniciador de aplicaciones](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) y [actualizaciones a Office.com y el artículo del blog del iniciador de aplicaciones de Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) .</span><span class="sxs-lookup"><span data-stu-id="845f3-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="845f3-110">Usar el portal de Azure Active Directory para anclar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="845f3-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="845f3-111">Vaya al centro de administración de Microsoft 365 en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="845f3-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="845f3-112">En el panel de navegación izquierdo, elija **Mostrar todo**y, en **centros de administración**, elija **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="845f3-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="845f3-113">En **Azure Active Directory**, elija Configuración de usuario de **aplicaciones empresariales**  >  **User settings**.</span><span class="sxs-lookup"><span data-stu-id="845f3-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="845f3-114">En la sección **configuración de Office 365** , elija **Agregar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="845f3-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="845f3-115">Elija las aplicaciones que quiera anclar en el iniciador de aplicaciones de los usuarios y luego elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="845f3-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Configuración de Microsoft 365 para anclar aplicaciones.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="845f3-117">Anclar una aplicación personalizada</span><span class="sxs-lookup"><span data-stu-id="845f3-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="845f3-118">La interfaz de usuario le indicará si necesita comprar licencias de Azure AD adicionales para usar esta característica.</span><span class="sxs-lookup"><span data-stu-id="845f3-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="845f3-119">Para obtener más información, vea [precios de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="845f3-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="845f3-120">En **Azure Active Directory**, elija **Enterprise applications**  >  **nueva aplicación** de aplicaciones empresariales en la parte superior de la página **todas las aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="845f3-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="845f3-121">En la página **Agregar una aplicación** , elija **aplicación que no sea de Galería** o **cree su propia aplicación** si se encuentran en la versión preliminar de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="845f3-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="845f3-122">Escriba un nombre para la aplicación y, después, asignar usuario en la pestaña **usuarios y grupos** .</span><span class="sxs-lookup"><span data-stu-id="845f3-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="845f3-123">Use la pestaña **propiedades** para cargar un icono para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="845f3-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="845f3-124">Para asignar una dirección URL a la aplicación, en la pestaña **Inicio de sesión único** , elija **vinculado** y, a continuación, escriba una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="845f3-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="845f3-125">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="845f3-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="845f3-126">Crear colecciones de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="845f3-126">Create application collections</span></span>

<span data-ttu-id="845f3-127">También puede crear colecciones de aplicaciones para los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="845f3-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="845f3-128">Para obtener instrucciones, vea [crear colecciones en el portal mis aplicaciones en el portal de Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span><span class="sxs-lookup"><span data-stu-id="845f3-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>