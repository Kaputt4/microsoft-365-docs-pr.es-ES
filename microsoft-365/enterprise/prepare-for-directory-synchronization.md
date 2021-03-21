---
title: Prepararse para la sincronización de directorios de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Describe cómo prepararse para aprovisionar usuarios a Microsoft 365 mediante la sincronización de directorios y las ventajas a largo plazo de usar este método.
ms.openlocfilehash: 1fe99247a5c50c7bb8fc7eb1347ce6a4cd6aad94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927329"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="d8947-103">Prepararse para la sincronización de directorios de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d8947-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="d8947-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d8947-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d8947-105">Las ventajas de la sincronización de directorios y identidad híbrida de la organización incluyen:</span><span class="sxs-lookup"><span data-stu-id="d8947-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="d8947-106">Reducción de los programas administrativos de la organización</span><span class="sxs-lookup"><span data-stu-id="d8947-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="d8947-107">Habilitar opcionalmente un escenario de inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="d8947-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="d8947-108">Automatizar cambios de cuenta en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d8947-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="d8947-109">Para obtener más información acerca de las ventajas de usar la sincronización de directorios, vea identidad híbrida con [Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) e [identidad híbrida para Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="d8947-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="d8947-110">Sin embargo, la sincronización de directorios requiere planeación y preparación para garantizar que los Servicios de dominio de Active Directory (AD DS) se sincronicen con el inquilino de Azure AD de su suscripción a Microsoft 365 con un mínimo de errores.</span><span class="sxs-lookup"><span data-stu-id="d8947-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="d8947-111">Siga estos pasos para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="d8947-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="d8947-112">1. Tareas de limpieza de directorios</span><span class="sxs-lookup"><span data-stu-id="d8947-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="d8947-113">Antes de sincronizar su AD DS con el inquilino de Azure AD, debe limpiar su AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8947-114">Si no realizas la limpieza de AD DS antes de sincronizar, puede provocar un impacto negativo significativo en el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="d8947-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="d8947-115">Puede tardar días o incluso semanas en pasar por el ciclo de sincronización de directorios, identificar errores y volver a sincronizar.</span><span class="sxs-lookup"><span data-stu-id="d8947-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="d8947-116">En AD DS, complete las siguientes tareas de limpieza para cada cuenta de usuario a la que se le asignará una licencia de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d8947-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="d8947-117">Asegúrese de que una dirección de correo electrónico válida y única en el **atributo proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="d8947-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="d8947-118">Quite los valores duplicados del **atributo proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="d8947-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="d8947-119">Si es posible, asegúrese de que el atributo **userPrincipalName** es válido y único en el objeto **de usuario del** usuario.</span><span class="sxs-lookup"><span data-stu-id="d8947-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="d8947-120">Para obtener la mejor experiencia de sincronización, asegúrese de que el UPN de AD DS coincide con el UPN de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d8947-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="d8947-121">Si un usuario no tiene un valor para el atributo **userPrincipalName,** el objeto **user** debe contener un valor válido y único para el atributo **sAMAccountName.**</span><span class="sxs-lookup"><span data-stu-id="d8947-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="d8947-122">Quite los valores duplicados del **atributo userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="d8947-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="d8947-123">Para un uso óptimo de la lista global de direcciones (GAL), asegúrese de que la información de los siguientes atributos de la cuenta de usuario de AD DS sea correcta:</span><span class="sxs-lookup"><span data-stu-id="d8947-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="d8947-124">givenName</span><span class="sxs-lookup"><span data-stu-id="d8947-124">givenName</span></span>
   - <span data-ttu-id="d8947-125">surname</span><span class="sxs-lookup"><span data-stu-id="d8947-125">surname</span></span>
   - <span data-ttu-id="d8947-126">displayName</span><span class="sxs-lookup"><span data-stu-id="d8947-126">displayName</span></span>
   - <span data-ttu-id="d8947-127">Puesto</span><span class="sxs-lookup"><span data-stu-id="d8947-127">Job Title</span></span>
   - <span data-ttu-id="d8947-128">Departamento</span><span class="sxs-lookup"><span data-stu-id="d8947-128">Department</span></span>
   - <span data-ttu-id="d8947-129">Oficina</span><span class="sxs-lookup"><span data-stu-id="d8947-129">Office</span></span>
   - <span data-ttu-id="d8947-130">Teléfono de la oficina</span><span class="sxs-lookup"><span data-stu-id="d8947-130">Office Phone</span></span>
   - <span data-ttu-id="d8947-131">Teléfono móvil</span><span class="sxs-lookup"><span data-stu-id="d8947-131">Mobile Phone</span></span>
   - <span data-ttu-id="d8947-132">Número de fax</span><span class="sxs-lookup"><span data-stu-id="d8947-132">Fax Number</span></span>
   - <span data-ttu-id="d8947-133">Dirección</span><span class="sxs-lookup"><span data-stu-id="d8947-133">Street Address</span></span>
   - <span data-ttu-id="d8947-134">Ciudad</span><span class="sxs-lookup"><span data-stu-id="d8947-134">City</span></span>
   - <span data-ttu-id="d8947-135">Provincia</span><span class="sxs-lookup"><span data-stu-id="d8947-135">State or Province</span></span>
   - <span data-ttu-id="d8947-136">Código postal</span><span class="sxs-lookup"><span data-stu-id="d8947-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="d8947-137">País o región</span><span class="sxs-lookup"><span data-stu-id="d8947-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="d8947-138">2. Preparación de atributos y objetos de directorio</span><span class="sxs-lookup"><span data-stu-id="d8947-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="d8947-139">La sincronización de directorios correcta entre AD DS y Microsoft 365 requiere que los atributos de AD DS estén preparados correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8947-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="d8947-140">Por ejemplo, debe asegurarse de que no se usan caracteres específicos en determinados atributos que están sincronizados con el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="d8947-141">Los caracteres inesperados no provocan errores en la sincronización de directorios, pero pueden devolver una advertencia.</span><span class="sxs-lookup"><span data-stu-id="d8947-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="d8947-142">Los caracteres no válidos provocarán un error en la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="d8947-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="d8947-143">La sincronización de directorios también producirá un error si algunos de los usuarios de AD DS tienen uno o más atributos duplicados.</span><span class="sxs-lookup"><span data-stu-id="d8947-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="d8947-144">Cada usuario debe tener atributos únicos.</span><span class="sxs-lookup"><span data-stu-id="d8947-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="d8947-145">Los atributos que necesita preparar se enumeran aquí:</span><span class="sxs-lookup"><span data-stu-id="d8947-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="d8947-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="d8947-146">**displayName**</span></span>

  - <span data-ttu-id="d8947-147">Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="d8947-148">Si este atributo existe en el objeto de usuario, debe haber un valor para él.</span><span class="sxs-lookup"><span data-stu-id="d8947-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="d8947-149">Es decir, el atributo no debe estar en blanco.</span><span class="sxs-lookup"><span data-stu-id="d8947-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="d8947-150">Número máximo de caracteres: 256</span><span class="sxs-lookup"><span data-stu-id="d8947-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="d8947-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="d8947-151">**givenName**</span></span>

  - <span data-ttu-id="d8947-152">Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo requiere ni lo usa.</span><span class="sxs-lookup"><span data-stu-id="d8947-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="d8947-153">Número máximo de caracteres: 64</span><span class="sxs-lookup"><span data-stu-id="d8947-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="d8947-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="d8947-154">**mail**</span></span>

  - <span data-ttu-id="d8947-155">El valor del atributo debe ser único en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d8947-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8947-156">Si hay valores duplicados, se sincroniza el primer usuario con el valor.</span><span class="sxs-lookup"><span data-stu-id="d8947-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="d8947-157">Los usuarios subsiguientes no aparecerán en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="d8947-158">Debe modificar el valor de Microsoft 365 o modificar ambos valores en AD DS para que ambos usuarios aparezcan en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="d8947-159">**mailNickname** (alias de Exchange)</span><span class="sxs-lookup"><span data-stu-id="d8947-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="d8947-160">El valor del atributo no puede comenzar por un punto (.).</span><span class="sxs-lookup"><span data-stu-id="d8947-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="d8947-161">El valor del atributo debe ser único en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d8947-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8947-162">Los caracteres de subrayado ("_") en el nombre sincronizado indican que el valor original de este atributo contiene caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="d8947-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="d8947-163">Para obtener más información sobre este atributo, vea [Atributo de alias de Exchange](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="d8947-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="d8947-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="d8947-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="d8947-165">Atributo de varios valores</span><span class="sxs-lookup"><span data-stu-id="d8947-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="d8947-166">Número máximo de caracteres por valor: 256</span><span class="sxs-lookup"><span data-stu-id="d8947-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="d8947-167">El valor del atributo no debe contener un espacio.</span><span class="sxs-lookup"><span data-stu-id="d8947-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="d8947-168">El valor del atributo debe ser único en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d8947-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="d8947-169">Caracteres no válidos: \< \> ( ) ; , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="d8947-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="d8947-170">Tenga en cuenta que los caracteres no válidos se aplican a los caracteres siguientes al delimitador de tipos y ,, de forma que SMTP:User@contso.com, pero SMTP:user:M@contoso.com no lo es.</span><span class="sxs-lookup"><span data-stu-id="d8947-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d8947-171">Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d8947-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="d8947-172">Quite las direcciones duplicadas o no deseadas si existen.</span><span class="sxs-lookup"><span data-stu-id="d8947-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="d8947-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="d8947-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="d8947-174">Número máximo de caracteres: 20</span><span class="sxs-lookup"><span data-stu-id="d8947-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="d8947-175">El valor del atributo debe ser único en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d8947-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="d8947-176">Caracteres no válidos: [ \ " | , / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="d8947-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="d8947-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="d8947-177">\* ']</span></span>
  - <span data-ttu-id="d8947-178">Si un usuario tiene un atributo **sAMAccountName** no válido pero tiene un atributo **userPrincipalName** válido, la cuenta de usuario se crea en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="d8947-179">Si tanto **sAMAccountName** como **userPrincipalName** no son válidos, se debe actualizar el atributo **userPrincipalName** de AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="d8947-180">**sn** (apellido)</span><span class="sxs-lookup"><span data-stu-id="d8947-180">**sn** (surname)</span></span>

  - <span data-ttu-id="d8947-181">Si el atributo existe en el objeto de usuario, se sincronizará con Microsoft 365, pero Microsoft 365 no lo requiere ni lo usa.</span><span class="sxs-lookup"><span data-stu-id="d8947-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="d8947-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="d8947-182">**targetAddress**</span></span>

    <span data-ttu-id="d8947-183">Es necesario que el atributo **targetAddress** (por ejemplo, SMTP:tom@contoso.com) que se rellena para el usuario debe aparecer en la GAL de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="d8947-184">En escenarios de migración de mensajería de terceros, esto requeriría la extensión de esquema de Microsoft 365 para AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="d8947-185">La extensión de esquema de Microsoft 365 también agregaría otros atributos útiles para administrar objetos de Microsoft 365 que se rellenan mediante una herramienta de sincronización de directorios de AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="d8947-186">Por ejemplo, se agregaría **el atributo msExchHideFromAddressLists** para administrar buzones o grupos de distribución ocultos.</span><span class="sxs-lookup"><span data-stu-id="d8947-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="d8947-187">Número máximo de caracteres: 256</span><span class="sxs-lookup"><span data-stu-id="d8947-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="d8947-188">El valor del atributo no debe contener un espacio.</span><span class="sxs-lookup"><span data-stu-id="d8947-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="d8947-189">El valor del atributo debe ser único en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d8947-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="d8947-190">Caracteres no válidos: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="d8947-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="d8947-191">Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d8947-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="d8947-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="d8947-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="d8947-193">El **atributo userPrincipalName** debe tener el formato de inicio de sesión de estilo de Internet donde el nombre de usuario va seguido del signo de at (@) y un nombre de dominio: por ejemplo, user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d8947-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="d8947-194">Todas las direcciones del Protocolo simple de transporte de correo (SMTP) deben cumplir con los estándares de mensajería de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d8947-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="d8947-195">El número máximo de caracteres para el **atributo userPrincipalName** es 113.</span><span class="sxs-lookup"><span data-stu-id="d8947-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="d8947-196">Se permite un número específico de caracteres antes y después del signo at (@), como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="d8947-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="d8947-197">Número máximo de caracteres para el nombre de usuario que está delante del signo at (@): 64</span><span class="sxs-lookup"><span data-stu-id="d8947-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="d8947-198">Número máximo de caracteres para el nombre de dominio después del signo at (@): 48</span><span class="sxs-lookup"><span data-stu-id="d8947-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="d8947-199">Caracteres no válidos: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="d8947-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="d8947-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="d8947-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="d8947-201">Caracteres permitidos: A – Z, a - z, 0 – 9, ' .</span><span class="sxs-lookup"><span data-stu-id="d8947-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="d8947-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="d8947-202">- _ !</span></span> <span data-ttu-id="d8947-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="d8947-203"># ^ ~</span></span>
  - <span data-ttu-id="d8947-204">Las letras con marcas diacríticos, como umlauts, acentos y tildes, son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="d8947-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="d8947-205">El carácter @ es necesario en cada **valor userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="d8947-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="d8947-206">El carácter @ no puede ser el primer carácter de cada valor **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="d8947-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="d8947-207">El nombre de usuario no puede terminar con un punto (.), una yand ( ), un &amp; espacio o un signo at (@).</span><span class="sxs-lookup"><span data-stu-id="d8947-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="d8947-208">El nombre de usuario no puede contener espacios.</span><span class="sxs-lookup"><span data-stu-id="d8947-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="d8947-209">Se deben usar dominios enrutables; por ejemplo, no se pueden usar dominios locales o internos.</span><span class="sxs-lookup"><span data-stu-id="d8947-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="d8947-210">Unicode se convierte a guiones bajos.</span><span class="sxs-lookup"><span data-stu-id="d8947-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="d8947-211">**userPrincipalName** no puede contener valores duplicados en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d8947-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="d8947-212">3. Preparar el atributo userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d8947-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="d8947-213">Active Directory está diseñado para permitir que los usuarios finales de la organización inicien sesión en el directorio mediante **sAMAccountName** o **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="d8947-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="d8947-214">Del mismo modo, los usuarios finales pueden iniciar sesión en Microsoft 365 con el nombre principal de usuario (UPN) de su cuenta laboral o educativa.</span><span class="sxs-lookup"><span data-stu-id="d8947-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="d8947-215">La sincronización de directorios intenta crear nuevos usuarios en Azure Active Directory mediante el mismo UPN que está en AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="d8947-216">El UPN tiene el formato de una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d8947-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="d8947-217">En Microsoft 365, el UPN es el atributo predeterminado que se usa para generar la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d8947-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="d8947-218">Es fácil obtener **userPrincipalName** (en AD DS y en Azure AD) y la dirección de correo electrónico principal en **proxyAddresses** establecida en valores diferentes.</span><span class="sxs-lookup"><span data-stu-id="d8947-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="d8947-219">Cuando se establecen en valores diferentes, puede haber confusión para los administradores y los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="d8947-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="d8947-220">Es mejor alinear estos atributos para reducir la confusión.</span><span class="sxs-lookup"><span data-stu-id="d8947-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="d8947-221">Para cumplir los requisitos del inicio de sesión único con Servicios de federación de Active Directory (AD FS) 2.0, debe asegurarse de que los UPN de Azure Active Directory y su AD DS coincidan y usen un espacio de nombres de dominio válido.</span><span class="sxs-lookup"><span data-stu-id="d8947-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="d8947-222">4. Agregar un sufijo UPN alternativo a AD DS</span><span class="sxs-lookup"><span data-stu-id="d8947-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="d8947-223">Es posible que deba agregar un sufijo UPN alternativo para asociar las credenciales corporativas del usuario con el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d8947-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="d8947-224">Un sufijo UPN es la parte de un UPN situada a la derecha del carácter @.</span><span class="sxs-lookup"><span data-stu-id="d8947-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="d8947-225">Los UPN que se usan para el inicio de sesión único pueden contener letras, números, puntos, guiones y caracteres de subrayado, pero ningún otro tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="d8947-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="d8947-226">Para obtener más información sobre cómo agregar un sufijo UPN alternativo a Active Directory, vea [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span><span class="sxs-lookup"><span data-stu-id="d8947-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="d8947-227">5. Hacer coincidir el UPN de AD DS con el UPN de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d8947-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="d8947-228">Si ya ha configurado la sincronización de directorios, es posible que el UPN del usuario para Microsoft 365 no coincida con el UPN de AD DS del usuario definido en su AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="d8947-229">Esto puede suceder cuando se ha asignado una licencia a un usuario antes de que se comprobara el dominio.</span><span class="sxs-lookup"><span data-stu-id="d8947-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="d8947-230">Para solucionar esto, use PowerShell para corregir UPN duplicado para actualizar el [UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) del usuario para asegurarse de que el UPN de Microsoft 365 coincida con el nombre de usuario corporativo y el dominio.</span><span class="sxs-lookup"><span data-stu-id="d8947-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="d8947-231">Si va a actualizar el UPN en AD DS y desea que se sincronice con la identidad de Azure Active Directory, debe quitar la licencia del usuario en Microsoft 365 antes de realizar los cambios en AD DS.</span><span class="sxs-lookup"><span data-stu-id="d8947-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="d8947-232">Vea también [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="d8947-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8947-233">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d8947-233">Next steps</span></span>

<span data-ttu-id="d8947-234">Si ha realizado los pasos 1 a 5 anteriores, vea [Configurar la sincronización de directorios](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="d8947-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>