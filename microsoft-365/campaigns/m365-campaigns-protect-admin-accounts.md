---
title: Proteger las cuentas de administrador
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo configurar y proteger las cuentas de administrador.
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398246"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="1463f-103">Proteger las cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="1463f-103">Protect your administrator accounts</span></span>

<span data-ttu-id="1463f-104">Dado que las cuentas de administrador vienen con privilegios elevados, son objetivos valiosos para los hackers y los ciberdelincuentes.</span><span class="sxs-lookup"><span data-stu-id="1463f-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="1463f-105">Este artículo describe:</span><span class="sxs-lookup"><span data-stu-id="1463f-105">This article describes:</span></span>

- <span data-ttu-id="1463f-106">Cómo configurar una cuenta de administrador adicional para emergencias.</span><span class="sxs-lookup"><span data-stu-id="1463f-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="1463f-107">Cómo proteger estas cuentas.</span><span class="sxs-lookup"><span data-stu-id="1463f-107">How to protect these accounts.</span></span>

<span data-ttu-id="1463f-108">Cuando te registras para Microsoft 365 y escribes tu información, automáticamente te conviertes en el administrador global. Un administrador global tiene el control final de las cuentas de usuario y todas las demás configuraciones del Centro de administración de Microsoft, pero hay muchos tipos diferentes de cuentas de administrador con distintos grados de acceso.</span><span class="sxs-lookup"><span data-stu-id="1463f-108">When you sign up for Microsoft 365 and enter your information, you automatically become the Global admin. A Global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="1463f-109">Consulta [sobre los roles de administrador](/office365/admin/add-users/about-admin-roles) para obtener información sobre los diferentes niveles de acceso para cada tipo de rol de administrador.</span><span class="sxs-lookup"><span data-stu-id="1463f-109">See [about admin roles](/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="1463f-110">Crear cuentas de administrador adicionales</span><span class="sxs-lookup"><span data-stu-id="1463f-110">Create additional admin accounts</span></span>

<span data-ttu-id="1463f-111">Use cuentas de administrador solo para la administración.</span><span class="sxs-lookup"><span data-stu-id="1463f-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="1463f-112">Los administradores deben tener una cuenta de usuario independiente para el uso regular de aplicaciones de Office y usar solo su cuenta administrativa cuando sea necesario para administrar cuentas y dispositivos, y mientras trabajan en otras funciones de administración.</span><span class="sxs-lookup"><span data-stu-id="1463f-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="1463f-113">También es buena idea quitar la licencia de Microsoft 365 de las cuentas de administrador para que no tenga que pagar por ellas.</span><span class="sxs-lookup"><span data-stu-id="1463f-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="1463f-114">Tendrás que configurar al menos una cuenta de administrador global adicional para dar acceso de administrador a otro empleado de confianza.</span><span class="sxs-lookup"><span data-stu-id="1463f-114">You'll want to set up at least one additional Global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="1463f-115">También puede crear cuentas de administrador independientes para la administración de usuarios (este rol se denomina **Administrador de administración de usuarios**).</span><span class="sxs-lookup"><span data-stu-id="1463f-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="1463f-116">Para obtener más información, vea [acerca de los roles de administrador](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1463f-116">For more information, see [about admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="1463f-117">Para crear cuentas de administrador adicionales:</span><span class="sxs-lookup"><span data-stu-id="1463f-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="1463f-118">Vaya al Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">de administración y,</a> a continuación, **elija Usuarios** \> **usuarios activos** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="1463f-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Elija Usuarios y, a continuación, Usuarios activos en la navegación izquierda](../media/Activeusers.png)

 2. <span data-ttu-id="1463f-120">En la **página Usuarios activos,** seleccione Agregar **un** usuario en la parte superior de la página y, en el **panel** Nuevo usuario, escriba el nombre y otra información.</span><span class="sxs-lookup"><span data-stu-id="1463f-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="1463f-121">Expanda la **sección Roles** y elija **Administrador global** para proporcionar a este usuario acceso de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1463f-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="1463f-122">También puede elegir Administrador **personalizado y** elegir cualquiera de los roles que se muestran.</span><span class="sxs-lookup"><span data-stu-id="1463f-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="1463f-123">Escriba un correo electrónico alternativo en el **cuadro de texto Dirección de correo** electrónico alternativa.</span><span class="sxs-lookup"><span data-stu-id="1463f-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="1463f-124">Puede usar esta dirección para recuperar la información de contraseña si se bloquea. Para los administradores globales, también se enviará una declaración de facturación a esta dirección.</span><span class="sxs-lookup"><span data-stu-id="1463f-124">You can use this address to recover your password information if you get locked out. For Global admins, a billing statement will also be sent to this address.</span></span>

    ![Elegir el rol de administrador](../media/adminroles.png)

 4. <span data-ttu-id="1463f-126">En la **sección Licencias de productos,** mueva el selector de **Microsoft 365 Empresa** a **Desactivado** y Crear usuario sin licencia **de producto** a **On**.</span><span class="sxs-lookup"><span data-stu-id="1463f-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Elegir la licencia del producto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="1463f-128">Crear una cuenta de administrador de emergencia</span><span class="sxs-lookup"><span data-stu-id="1463f-128">Create an emergency admin account</span></span>

<span data-ttu-id="1463f-129">También debe crear una cuenta de copia de seguridad que no esté configurada con la autenticación multifactor (MFA) para que no se bloquee accidentalmente (por ejemplo, si pierde el teléfono que está usando como segunda forma de comprobación).</span><span class="sxs-lookup"><span data-stu-id="1463f-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="1463f-130">Asegúrese de que la contraseña de esta cuenta es una frase o al menos 16 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="1463f-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="1463f-131">Esto se conoce a menudo como una "cuenta de cristal de interrupción".</span><span class="sxs-lookup"><span data-stu-id="1463f-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="1463f-132">Crear una cuenta de usuario por ti mismo</span><span class="sxs-lookup"><span data-stu-id="1463f-132">Create a user account for yourself</span></span>

<span data-ttu-id="1463f-133">Use su cuenta de usuario para participar en la colaboración con su organización, incluida la comprobación del correo.</span><span class="sxs-lookup"><span data-stu-id="1463f-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="1463f-134">Esto significa que sus credenciales de administrador pueden ser similares a  *Alice.Chávez <span></span> @Contoso.org* y su cuenta de usuario normal puede ser similar a *Alice <span></span> @Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="1463f-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="1463f-135">Para crear una nueva cuenta de usuario:</span><span class="sxs-lookup"><span data-stu-id="1463f-135">To create a new user account:</span></span>

1. <span data-ttu-id="1463f-136">Vaya al Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">de administración y,</a> a continuación, **elija Usuarios** \> **usuarios activos** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="1463f-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="1463f-137">En la **página Usuarios activos,** seleccione Agregar **un** usuario en la parte superior de la página y, en el **panel** Nuevo usuario, escriba el nombre y otra información.</span><span class="sxs-lookup"><span data-stu-id="1463f-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="1463f-138">Expanda la **sección Roles** y elija **Usuario (sin acceso administrativo).**</span><span class="sxs-lookup"><span data-stu-id="1463f-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="1463f-139">En la **sección Licencias de productos,** mueva el selector **de Microsoft 365 Empresa** a **On**.</span><span class="sxs-lookup"><span data-stu-id="1463f-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="turn-on-security-defaults"></a><span data-ttu-id="1463f-140">Activar valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="1463f-140">Turn on security defaults</span></span>

<span data-ttu-id="1463f-141">Los valores predeterminados de seguridad ayudan a proteger su organización de ataques relacionados con la identidad proporcionando una configuración de seguridad preconfigurada que Microsoft administra en nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="1463f-141">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="1463f-142">Estas opciones incluyen habilitar la autenticación multifactor (MFA) para todos los administradores y cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="1463f-142">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="1463f-143">Para obtener más información sobre los valores predeterminados de seguridad y para obtener información sobre cómo habilitarlos, vea [Activar valores predeterminados de seguridad](m365-campaigns-conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="1463f-143">For more information about security defaults and to learn how to enable them on, see [Turn on security defaults](m365-campaigns-conditional-access.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="1463f-144">Recomendaciones adicionales</span><span class="sxs-lookup"><span data-stu-id="1463f-144">Additional recommendations</span></span>

- <span data-ttu-id="1463f-145">Antes de usar cuentas de administrador, cierre todas las aplicaciones y sesiones de explorador no relacionadas, incluidas las cuentas de correo electrónico personales.</span><span class="sxs-lookup"><span data-stu-id="1463f-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="1463f-146">También puedes usar en ventanas de explorador privadas o de incógnito.</span><span class="sxs-lookup"><span data-stu-id="1463f-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="1463f-147">Después de completar las tareas de administración, asegúrese de cerrar la sesión del explorador.</span><span class="sxs-lookup"><span data-stu-id="1463f-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
