---
title: Administración de buzones de correo de Exchange Online en un entorno multigeográfico
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Obtenga información sobre cómo administrar Exchange Online configuración multige geográfica en su entorno Microsoft 365 con PowerShell.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905589"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="a348d-103">Administración de buzones de correo de Exchange Online en un entorno multigeográfico</span><span class="sxs-lookup"><span data-stu-id="a348d-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="a348d-104">Exchange Online PowerShell es necesario para ver y configurar propiedades geográficas múltiples en el entorno Microsoft 365 usuario.</span><span class="sxs-lookup"><span data-stu-id="a348d-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="a348d-105">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a348d-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="a348d-106">Necesitará la v1.1.166.0 o una versión posterior en la v1.x del [módulo PowerShell de Microsoft Azure Active Directory](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) para ver la propiedad **PreferredDataLocation** en los objetos de usuario.</span><span class="sxs-lookup"><span data-stu-id="a348d-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="a348d-107">No se puede modificar el valor de **PreferredDataLocation** directamente a través del PowerShell de AAD en los objetos de usuario que se sincronizan en AAD a través de AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a348d-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="a348d-108">Solo se pueden modificar objetos basados en la nube a través del PowerShell de AAD.</span><span class="sxs-lookup"><span data-stu-id="a348d-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="a348d-109">Para conectarse al PowerShell de Azure AD, consulte [Conectarse al PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a348d-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="a348d-110">En Exchange Online varios entornos geográficos, no es necesario realizar ningún paso manual para agregar geos al espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a348d-110">In Exchange Online multi-geo environments, you don't need to do any manual steps to add geos to your tenant.</span></span> <span data-ttu-id="a348d-111">Después de recibir la publicación del Centro de mensajes que indica que multigeo está listo para Exchange Online, todas las geos disponibles estarán listas y configuradas para su uso.</span><span class="sxs-lookup"><span data-stu-id="a348d-111">After you receive the Message Center post that says multi-geo is ready for Exchange Online, all available geos will be ready and configured for you to use.</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="a348d-112">Conectarse directamente a una ubicación geográfica con el PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a348d-112">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="a348d-113">Normalmente, el PowerShell de Exchange Online se conecta a la ubicación geográfica central.</span><span class="sxs-lookup"><span data-stu-id="a348d-113">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="a348d-114">Sin embargo, también puede conectarse directamente a las ubicaciones geográficas satélite.</span><span class="sxs-lookup"><span data-stu-id="a348d-114">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="a348d-115">Debido a las mejoras en el rendimiento, se recomienda conectarse directamente a la ubicación satélite si únicamente administra usuarios en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="a348d-115">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="a348d-116">Los requisitos para instalar y usar el módulo EXO V2 se describen en [Instalar y mantener el módulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="a348d-116">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="a348d-117">Para conectar Exchange Online PowerShell a una ubicación geográfica específica, el parámetro *ConnectionUri* es diferente de las instrucciones de conexión normales.</span><span class="sxs-lookup"><span data-stu-id="a348d-117">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="a348d-118">El resto de comandos y valores son los mismos.</span><span class="sxs-lookup"><span data-stu-id="a348d-118">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="a348d-119">En concreto, debe agregar el valor `?email=<emailaddress>` al final del valor _ConnectionUri._</span><span class="sxs-lookup"><span data-stu-id="a348d-119">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="a348d-120">`<emailaddress>` es la dirección de correo electrónico **de cualquier buzón** en la ubicación geográfica de destino.</span><span class="sxs-lookup"><span data-stu-id="a348d-120">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="a348d-121">Los permisos para ese buzón o la relación con sus credenciales no son un factor; la dirección de correo electrónico simplemente indica Exchange Online PowerShell dónde conectarse.</span><span class="sxs-lookup"><span data-stu-id="a348d-121">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="a348d-122">Microsoft 365 o Microsoft 365 GCC los clientes normalmente no necesitan usar el parámetro _ConnectionUri_ para conectarse a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a348d-122">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="a348d-123">Pero, para conectarse a una ubicación geográfica específica, debe usar el parámetro _ConnectionUri_ para que pueda usarlo `?email=<emailaddress>` en el valor.</span><span class="sxs-lookup"><span data-stu-id="a348d-123">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="a348d-124">Conectar a una ubicación geográfica en Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a348d-124">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="a348d-125">Las siguientes instrucciones de conexión funcionan para cuentas que están o no están configuradas para la autenticación multifactor (MFA).</span><span class="sxs-lookup"><span data-stu-id="a348d-125">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="a348d-126">En una ventana de Windows PowerShell, cargue el módulo EXO V2 ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a348d-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="a348d-127">En el siguiente ejemplo, admin@contoso.onmicrosoft.com es la cuenta de administrador y la ubicación geográfica de destino es donde reside el buzón olga@contoso.onmicrosoft.com correo.</span><span class="sxs-lookup"><span data-stu-id="a348d-127">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="a348d-128">Escriba la contraseña de la admin@contoso.onmicrosoft.com en el símbolo del sistema que aparece.</span><span class="sxs-lookup"><span data-stu-id="a348d-128">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="a348d-129">Si la cuenta está configurada para MFA, también debe escribir el código de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a348d-129">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="a348d-130">Ver las ubicaciones geográficas disponibles configuradas en su organización de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a348d-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="a348d-131">Para ver la lista de ubicaciones geográficas configuradas en Microsoft 365 Multi-Geo, ejecute el siguiente comando en el PowerShell de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a348d-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="a348d-132">Ver la ubicación geográfica central para su organización de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a348d-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="a348d-133">Para ver la ubicación geográfica central de su inquilino, ejecute el siguiente comando en el PowerShell de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a348d-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="a348d-134">Buscar la ubicación geográfica de un buzón</span><span class="sxs-lookup"><span data-stu-id="a348d-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="a348d-135">El cmdlet **Get-Mailbox** en el PowerShell de Exchange Online muestra las siguientes propiedades multigeográficas en buzones:</span><span class="sxs-lookup"><span data-stu-id="a348d-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="a348d-136">**Database**: Las tres primeras letras del nombre de la base de datos corresponden al código geográfico, que indica dónde se encuentra el buzón.</span><span class="sxs-lookup"><span data-stu-id="a348d-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="a348d-137">Para los buzones de archivo en línea, podría usarse la propiedad **ArchiveDatabase**.</span><span class="sxs-lookup"><span data-stu-id="a348d-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="a348d-138">**MailboxRegion**: Especifica el código de ubicación geográfica definido por el administrador (sincronizado desde **PreferredDataLocation** en Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a348d-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="a348d-139">**MailboxRegionLastUpdateTime**: Indica cuándo se actualizó MailboxRegion por última vez (de forma automática o manual).</span><span class="sxs-lookup"><span data-stu-id="a348d-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="a348d-140">Para ver estas propiedades de un buzón, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="a348d-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="a348d-141">Por ejemplo, para ver la información geográfica del buzón chris@contoso.onmicrosoft.com, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a348d-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="a348d-142">El resultado del comando tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="a348d-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="a348d-143">Si el código de ubicación geográfica del nombre de la base de datos no coincide con el valor **MailboxRegion,** el buzón se colocará automáticamente en una cola de reubicación y se trasladará a la ubicación geográfica especificada por el valor **MailboxRegion** (Exchange Online busca una discrepancia entre estos valores de propiedad).</span><span class="sxs-lookup"><span data-stu-id="a348d-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="a348d-144">Mover un buzón existente basado únicamente en la nube a una ubicación geográfica específica</span><span class="sxs-lookup"><span data-stu-id="a348d-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="a348d-145">Un usuario basado únicamente en la nube es un usuario que no está sincronizado con el inquilino a través de AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a348d-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="a348d-146">Dicho usuario se creó directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a348d-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="a348d-147">Use los cmdlets **Get-MsolUser** y **Set-MsolUser** en el módulo de Azure AD para Windows PowerShell para ver o especificar la ubicación geográfica donde se almacenará el buzón de un usuario basado únicamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="a348d-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="a348d-148">Para ver el valor **PreferredDataLocation** de un usuario, use la siguiente sintaxis en el PowerShell de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a348d-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="a348d-149">Por ejemplo, para ver el valor de **PreferredDataLocation** para el usuario michelle@contoso.onmicrosoft.com, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a348d-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="a348d-150">Para modificar el valor de **PreferredDataLocation** para un objeto de un usuario basado únicamente en la nube, use la siguiente sintaxis en el PowerShell de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a348d-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="a348d-151">Por ejemplo, para definir el valor de **PreferredDataLocation** en la ubicación geográfica Unión Europea (EUR) para el usuario michelle@contoso.onmicrosoft.com, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a348d-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="a348d-152">Como se mencionó anteriormente, no puede usar este procedimiento para objetos de usuario sincronizados de Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="a348d-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="a348d-153">Tiene que cambiar el valor de **PreferredDataLocation** en Active Directory y sincronizarlo con AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a348d-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="a348d-154">Para obtener más información, consulte [Sincronización de Azure Active Directory Connect: configurar la ubicación de datos preferida para recursos de Microsoft 365](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="a348d-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="a348d-155">El tiempo que se tarda en reubicar un buzón a una nueva ubicación geográfica depende de varios factores:</span><span class="sxs-lookup"><span data-stu-id="a348d-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="a348d-156">El tamaño y tipo de buzón.</span><span class="sxs-lookup"><span data-stu-id="a348d-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="a348d-157">La cantidad de buzones que se migrarán.</span><span class="sxs-lookup"><span data-stu-id="a348d-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="a348d-158">La disponibilidad de recursos de migración.</span><span class="sxs-lookup"><span data-stu-id="a348d-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="a348d-159">Mover un buzón inactivo a una ubicación geográfica específica</span><span class="sxs-lookup"><span data-stu-id="a348d-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="a348d-160">No puede mover buzones inactivos que se conservan con fines de cumplimiento (por ejemplo, buzones en retención por juicio) cambiando su **valor PreferredDataLocation.**</span><span class="sxs-lookup"><span data-stu-id="a348d-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="a348d-161">Para mover un buzón inactivo a una ubicación geográfica diferente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a348d-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="a348d-162">Recupere el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="a348d-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="a348d-163">Para obtener instrucciones, vea [Recuperar un buzón inactivo.](../compliance/recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="a348d-163">For instructions, see [Recover an inactive mailbox](../compliance/recover-an-inactive-mailbox.md).</span></span>

2. <span data-ttu-id="a348d-164">Impedir que el Asistente para carpeta administrada procese el buzón recuperado reemplazando por el nombre, alias, cuenta o dirección de correo electrónico del buzón y ejecutando el siguiente comando en \<MailboxIdentity\> [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="a348d-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="a348d-165">Asigne una **Exchange Online de plan 2** al buzón recuperado.</span><span class="sxs-lookup"><span data-stu-id="a348d-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="a348d-166">Este paso es necesario para volver a colocar el buzón en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="a348d-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="a348d-167">Para obtener instrucciones, vea [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="a348d-167">For instructions, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).</span></span>

4. <span data-ttu-id="a348d-168">Configure el **valor PreferredDataLocation** en el buzón como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="a348d-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="a348d-169">Después de confirmar que el buzón se ha movido a la nueva ubicación geográfica, vuelva a colocar el buzón recuperado en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="a348d-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="a348d-170">Para obtener instrucciones, vea [Colocar un buzón en retención por juicio](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="a348d-170">For instructions, see [Place a mailbox on Litigation Hold](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="a348d-171">Después de comprobar que la retención por juicio está en curso, permita que el Asistente para carpetas administradas vuelva a procesar el buzón reemplazando por el nombre, alias, cuenta o dirección de correo electrónico del buzón y ejecutando el siguiente comando en \<MailboxIdentity\> [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="a348d-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="a348d-172">Vuelva a hacer que el buzón esté inactivo quitando la cuenta de usuario asociada al buzón.</span><span class="sxs-lookup"><span data-stu-id="a348d-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="a348d-173">Para obtener instrucciones, [vea Delete a user from your organization](../admin/add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a348d-173">For instructions, see [Delete a user from your organization](../admin/add-users/delete-a-user.md).</span></span> <span data-ttu-id="a348d-174">Este paso también libera la licencia Exchange Online plan 2 para otros usos.</span><span class="sxs-lookup"><span data-stu-id="a348d-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="a348d-175">**Nota:** Al mover un buzón inactivo a una ubicación geográfica diferente, puede afectar a los resultados de búsqueda de contenido o a la capacidad de buscar en el buzón desde la ubicación geográfica anterior.</span><span class="sxs-lookup"><span data-stu-id="a348d-175">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="a348d-176">Para obtener más información, vea [Searching and exporting content in Multi-Geo environments](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span><span class="sxs-lookup"><span data-stu-id="a348d-176">For more information, see [Searching and exporting content in Multi-Geo environments](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="a348d-177">Crear nuevos buzones basados en la nube en una ubicación geográfica específica</span><span class="sxs-lookup"><span data-stu-id="a348d-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="a348d-178">Para crear un nuevo buzón en una ubicación geográfica específica, debe realizar uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a348d-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="a348d-179">Configure el **valor PreferredDataLocation** como se describe en la sección Mover  un buzón de correo de solo nube existente a una [ubicación geográfica](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) específica antes de crear el buzón en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a348d-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="a348d-180">Por ejemplo, configure el valor **PreferredDataLocation** en un usuario antes de asignar una licencia.</span><span class="sxs-lookup"><span data-stu-id="a348d-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="a348d-181">Asignar una licencia al mismo tiempo que se define el valor de **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="a348d-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="a348d-182">Para crear un nuevo usuario con licencia basado únicamente en la nube (que no esté sincronizado con AAD Connect) en una ubicación geográfica específica, use la siguiente sintaxis en el PowerShell de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a348d-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="a348d-183">Este ejemplo crea una cuenta de usuario para Elizabeth Brunner con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a348d-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="a348d-184">Nombre de usuario principal: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a348d-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="a348d-185">Nombre: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="a348d-185">First name: Elizabeth</span></span>
- <span data-ttu-id="a348d-186">Apellido: Brunner</span><span class="sxs-lookup"><span data-stu-id="a348d-186">Last name: Brunner</span></span>
- <span data-ttu-id="a348d-187">Nombre para mostrar: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="a348d-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="a348d-188">Contraseña: Se genera de forma aleatoria y se muestra en los resultados del comando (debido a que no se usa el parámetro *contraseña*)</span><span class="sxs-lookup"><span data-stu-id="a348d-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="a348d-189">Licencia: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="a348d-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="a348d-190">Ubicación: Australia (AUS)</span><span class="sxs-lookup"><span data-stu-id="a348d-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="a348d-191">Para obtener más información sobre cómo crear nuevas cuentas de usuario y cómo encontrar valores de LicenseAssignment en el PowerShell de Azure AD, consulte [Crear cuentas de usuario con PowerShell](create-user-accounts-with-microsoft-365-powershell.md) y [Ver licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a348d-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a348d-192">Si usa el PowerShell de Exchange Online para habilitar un buzón y necesita que este se cree directamente en la ubicación geográfica especificada en **PreferredDataLocation**, debe usar un cmdlet de Exchange Online como **Enable-Mailbox** o **New-Mailbox** directamente con el servicio basado en la nube.</span><span class="sxs-lookup"><span data-stu-id="a348d-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="a348d-193">Si usa el cmdlet **Enable-RemoteMailbox** en el entorno local de Exchange PowerShell, el buzón se creará en la ubicación geográfica central.</span><span class="sxs-lookup"><span data-stu-id="a348d-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="a348d-194">Incorporar buzones existentes en el entorno local a una ubicación geográfica específica</span><span class="sxs-lookup"><span data-stu-id="a348d-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="a348d-195">Puede usar las herramientas y procesos de incorporación estándar para migrar un buzón del entorno local de una organización de Exchange a Exchange Online, incluidos el [Panel de migración en el EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) y el cmdlet [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) del PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a348d-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="a348d-196">El primer paso consiste en comprobar que existe un objeto de usuario para que cada buzón se quiere incorporar y comprobar que el valor de **PreferredDataLocation** está configurado correctamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a348d-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="a348d-197">Las herramientas de incorporación respetarán el valor de **PreferredDataLocation** y migrarán los buzones directamente a la ubicación geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="a348d-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="a348d-198">Como alternativa, puede seguir los pasos a continuación para incorporar buzones directamente a una ubicación geográfica específica con el cmdlet [New-MoveRequest](/powershell/module/exchange/new-moverequest) del PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a348d-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="a348d-199">Compruebe que existe el objeto de usuario para cada buzón que se va a incorporar y que **PreferredDataLocation** está definido en el valor deseado en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a348d-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="a348d-200">El valor de **PreferredDataLocation** se sincronizará con el atributo **MailboxRegion** del objeto de usuario del correo correspondiente en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a348d-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="a348d-201">Conéctese directamente con la ubicación geográfica satélite específica siguiendo las instrucciones de conexión mostradas anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a348d-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="a348d-202">En el PowerShell de Exchange Online, almacene en una variable las credenciales de administrador del entorno local que se usan para realizar una migración de buzones ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a348d-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="a348d-203">En el PowerShell de Exchange Online, cree un nuevo **New-MoveRequest** similar al del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a348d-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="a348d-204">Repita el paso 4 para cada buzón que quiera migrar del entorno local de Exchange a la ubicación geográfica satélite a la que está conectado actualmente.</span><span class="sxs-lookup"><span data-stu-id="a348d-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="a348d-205">Si quiere migrar más buzones a ubicaciones geográficas satélite diferentes, repita los pasos 2 a 4 para cada ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="a348d-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="a348d-206">Informes multigeográficos</span><span class="sxs-lookup"><span data-stu-id="a348d-206">Multi-geo reporting</span></span>

<span data-ttu-id="a348d-207">Los **Informes de uso multigeográfico** en el Centro de administración de Microsoft 365 muestran el número de usuarios por ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="a348d-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="a348d-208">El informe muestra la distribución de usuarios durante el mes actual y proporciona los datos históricos para los últimos 6 meses.</span><span class="sxs-lookup"><span data-stu-id="a348d-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="a348d-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a348d-209">See also</span></span>

[<span data-ttu-id="a348d-210">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a348d-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)