---
title: Proteger las cuentas de administrador
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo configurar y proteger las cuentas de administrador.
ms.openlocfilehash: 6160f7458dc9a4c343c48f07d87776529c4f1326
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594825"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="b0353-103">Proteger las cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="b0353-103">Protect your administrator accounts</span></span>

<span data-ttu-id="b0353-104">Como las cuentas de administrador tienen privilegios elevados, son objetivos muy valiosos para los hackers y los delincuentes cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="b0353-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="b0353-105">Este artículo describe:</span><span class="sxs-lookup"><span data-stu-id="b0353-105">This article describes:</span></span>

- <span data-ttu-id="b0353-106">Cómo configurar una cuenta de administrador adicional para las emergencias.</span><span class="sxs-lookup"><span data-stu-id="b0353-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="b0353-107">Cómo proteger estas cuentas.</span><span class="sxs-lookup"><span data-stu-id="b0353-107">How to protect these accounts.</span></span>
 
<span data-ttu-id="b0353-108">Cuando se suscriba a Microsoft 365 Business y escriba la información, se convertirá automáticamente en el administrador global. Un administrador global tiene el control final de las cuentas de usuario y el resto de la configuración en el centro de administración de Microsoft, pero hay muchos tipos diferentes de cuentas de administrador con distintos grados de acceso.</span><span class="sxs-lookup"><span data-stu-id="b0353-108">When you sign up for Microsoft 365 Business and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="b0353-109">Consulte [acerca](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) de los roles de administrador para obtener información sobre los diferentes niveles de acceso para cada tipo de rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="b0353-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>


## <a name="create-additional-admin-accounts"></a><span data-ttu-id="b0353-110">Crear cuentas de administrador adicionales</span><span class="sxs-lookup"><span data-stu-id="b0353-110">Create additional admin accounts</span></span>

<span data-ttu-id="b0353-111">Use cuentas de administrador solo para la administración.</span><span class="sxs-lookup"><span data-stu-id="b0353-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="b0353-112">Los administradores deben tener una cuenta de usuario independiente para el uso normal de las aplicaciones de Office y solo usar su cuenta administrativa cuando sea necesario para administrar cuentas y dispositivos, y mientras se trabaja en otras funciones de administración.</span><span class="sxs-lookup"><span data-stu-id="b0353-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="b0353-113">También es una buena idea quitar la licencia de Microsoft 365 Business de las cuentas de administrador para que no tenga que pagar por ellas.</span><span class="sxs-lookup"><span data-stu-id="b0353-113">It's also a good idea to remove the Microsoft 365 Business license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="b0353-114">Querrá configurar al menos una cuenta de administrador global adicional para conceder acceso de administrador a otro empleado de confianza.</span><span class="sxs-lookup"><span data-stu-id="b0353-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="b0353-115">También puede crear cuentas de administrador independientes para la administración de usuarios (este rol se denomina **Administrador de administración de usuarios**).</span><span class="sxs-lookup"><span data-stu-id="b0353-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="b0353-116">Para obtener más información, vea [acerca de los roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="b0353-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="b0353-117">Para crear cuentas de administrador adicionales:</span><span class="sxs-lookup"><span data-stu-id="b0353-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="b0353-118">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administración</a> y, a continuación, elija usuarios **activos** de **usuarios** \> en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b0353-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Elija usuarios y, a continuación, usuarios activos en el panel de navegación izquierdo](media/Activeusers.png)

2. <span data-ttu-id="b0353-120">En la página **usuarios activos** , seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **nuevo usuario** , escriba el nombre y otra información.</span><span class="sxs-lookup"><span data-stu-id="b0353-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="b0353-121">Expanda la sección **roles** y elija **administrador global** para conceder a este usuario acceso de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b0353-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="b0353-122">También puede elegir **Administrador personalizado** y elegir cualquiera de los roles que se muestran.</span><span class="sxs-lookup"><span data-stu-id="b0353-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="b0353-123">Escriba un correo electrónico alternativo en el cuadro de texto **dirección de correo alternativa** .</span><span class="sxs-lookup"><span data-stu-id="b0353-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="b0353-124">Puede usar esta dirección para recuperar la información de contraseña si se bloquea. Para los administradores globales, también se enviará una declaración de facturación a esta dirección.</span><span class="sxs-lookup"><span data-stu-id="b0353-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Elegir el rol de administrador](media/adminroles.png)
    
4. <span data-ttu-id="b0353-126">En la sección **licencias de productos** , mueva el selector de **Microsoft 365 Business** a **desactivado** y la opción **crear usuario sin licencia de producto** en **activado**.</span><span class="sxs-lookup"><span data-stu-id="b0353-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Elegir la licencia del producto](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="b0353-128">Crear una cuenta de administrador de emergencia</span><span class="sxs-lookup"><span data-stu-id="b0353-128">Create an emergency admin account</span></span>

<span data-ttu-id="b0353-129">También debe crear una cuenta de copia de seguridad que no esté configurada con multi-factor Authentication (MFA), de modo que no se bloquee por error (por ejemplo, si pierde el teléfono que está usando como segunda forma de verificación).</span><span class="sxs-lookup"><span data-stu-id="b0353-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="b0353-130">Asegúrese de que la contraseña de esta cuenta es una frase o al menos 16 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="b0353-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="b0353-131">Esto se conoce a menudo como una "cuenta de" Break-Glass ".</span><span class="sxs-lookup"><span data-stu-id="b0353-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="b0353-132">Crear una cuenta de usuario para usted</span><span class="sxs-lookup"><span data-stu-id="b0353-132">Create a user account for yourself</span></span>

<span data-ttu-id="b0353-133">Use su cuenta de usuario para participar en la colaboración con su organización, incluida la comprobación del correo.</span><span class="sxs-lookup"><span data-stu-id="b0353-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="b0353-134">Esto significa que las credenciales de administrador podrían ser similares a *Alice. Chavez<span></span>@Contoso. org* y la cuenta de usuario normal podría ser similar a *Alice<span></span>@Contoso. com*.</span><span class="sxs-lookup"><span data-stu-id="b0353-134">This means your admin credentials might be similar to  *Alice.Chavez<span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="b0353-135">Para crear una nueva cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="b0353-135">To create a new user account:</span></span>
1. <span data-ttu-id="b0353-136">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administración</a> y, a continuación, elija usuarios **activos** de **usuarios** \> en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b0353-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="b0353-137">En la página **usuarios activos** , seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **nuevo usuario** , escriba el nombre y otra información.</span><span class="sxs-lookup"><span data-stu-id="b0353-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="b0353-138">Expanda la sección **roles** y elija **usuario (sin acceso administrativo)**.</span><span class="sxs-lookup"><span data-stu-id="b0353-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
1. <span data-ttu-id="b0353-139">En la sección **licencias de producto** , mueva el selector de **Microsoft 365 empresa** a **activado**.</span><span class="sxs-lookup"><span data-stu-id="b0353-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span> 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="b0353-140">Registrar cada una de estas cuentas para la autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="b0353-140">Register each of these accounts for multi-factor authentication</span></span>


## <a name="additional-recommendations"></a><span data-ttu-id="b0353-141">Recomendaciones adicionales</span><span class="sxs-lookup"><span data-stu-id="b0353-141">Additional recommendations</span></span>

- <span data-ttu-id="b0353-142">Asegúrese de que las cuentas de administrador también están configuradas para la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="b0353-142">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="b0353-143">Le mostraremos cómo hacerlo en [configurar directivas de acceso condicional](m365-campaigns-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="b0353-143">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="b0353-144">Antes de usar cuentas de administrador, cierre todas las sesiones y aplicaciones del explorador no relacionadas, incluidas las cuentas de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="b0353-144">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="b0353-145">También puede usar en las ventanas del explorador privado o incógnito.</span><span class="sxs-lookup"><span data-stu-id="b0353-145">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="b0353-146">Después de completar las tareas de administración, asegúrese de cerrar la sesión del explorador.</span><span class="sxs-lookup"><span data-stu-id="b0353-146">After completing admin tasks, be sure to sign out of the browser session.</span></span>