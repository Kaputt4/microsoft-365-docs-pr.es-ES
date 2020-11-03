---
title: Etiquetas de cuarentena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Los administradores pueden aprender a usar las etiquetas de cuarentena para controlar lo que los usuarios pueden hacer a sus mensajes en cuarentena.
ms.openlocfilehash: e50d7eea4cec3c87231dda855725b1e901f5fa33
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845701"
---
# <a name="quarantine-tags"></a><span data-ttu-id="31d48-103">Etiquetas de cuarentena</span><span class="sxs-lookup"><span data-stu-id="31d48-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="31d48-104">Las características que se describen en este artículo están actualmente en versión preliminar, no están disponibles para todos los usuarios y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="31d48-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="31d48-105">Las etiquetas de cuarentena de Exchange Online Protection (EOP) permiten a los administradores controlar lo que los usuarios pueden hacer a sus mensajes en cuarentena en función de cómo llegó el mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="31d48-106">Tradicionalmente, EOP ha permitido o ha impedido ciertos niveles de interactividad para los mensajes en [cuarentena](find-and-release-quarantined-messages-as-a-user.md) y en las [notificaciones de correo no deseado para el usuario final](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="31d48-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="31d48-107">Por ejemplo, los usuarios finales pueden ver y liberar mensajes que se pusieron en cuarentena por filtrado contra correo electrónico no deseado o en masa, pero no pueden ver ni liberar mensajes que se pusieron en cuarentena como suplantación de identidad de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="31d48-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="31d48-108">Para [las características de protección admitidas, las](#step-2-assign-a-quarantine-tag-to-supported-features)etiquetas de cuarentena especifican lo que los usuarios pueden hacer en los mensajes de notificación de correo no deseado para el usuario final y en cuarentena en los mensajes en cuarentena (mensajes en los que el usuario es un destinatario).</span><span class="sxs-lookup"><span data-stu-id="31d48-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="31d48-109">Las etiquetas de cuarentena predeterminadas se asignan automáticamente para imponer las capacidades históricas para los usuarios finales en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="31d48-110">O bien, puede crear y asignar etiquetas de cuarentena personalizadas para permitir o impedir que los usuarios finales realicen acciones específicas en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="31d48-111">Los permisos individuales se combinan en los siguientes grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="31d48-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="31d48-112">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="31d48-112">No access</span></span>
- <span data-ttu-id="31d48-113">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="31d48-113">Limited access</span></span>
- <span data-ttu-id="31d48-114">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="31d48-114">Full access</span></span>

<span data-ttu-id="31d48-115">En la tabla siguiente se describen los permisos individuales disponibles y lo que se incluye o no incluidos en los grupos de permisos predeterminados:</span><span class="sxs-lookup"><span data-stu-id="31d48-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="31d48-116">Permiso</span><span class="sxs-lookup"><span data-stu-id="31d48-116">Permission</span></span>|<span data-ttu-id="31d48-117">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="31d48-117">No access</span></span>|<span data-ttu-id="31d48-118">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="31d48-118">Limited access</span></span>|<span data-ttu-id="31d48-119">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="31d48-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="31d48-120">**Permitir remitente** ( _PermissionToAllowSender_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-120">**Allow sender** ( _PermissionToAllowSender_ )</span></span>|||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="31d48-122">**Bloquear remitente** ( _PermissionToBlockSender_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-122">**Block sender** ( _PermissionToBlockSender_ )</span></span>||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="31d48-125">**Eliminar** ( _PermissionToDelete_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-125">**Delete** ( _PermissionToDelete_ )</span></span>||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="31d48-128">**Vista previa** ( _PermissionToPreview_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-128">**Preview** ( _PermissionToPreview_ )</span></span>||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="31d48-131">**Permitir que los destinatarios liberen un mensaje de la cuarentena** ( _PermissionToRelease_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-131">**Allow recipients to release a message from quarantine** ( _PermissionToRelease_ )</span></span>|||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="31d48-133">**Permitir que los destinatarios soliciten que se libere un mensaje de la cuarentena** ( _PermissionToRequestRelease_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-133">**Allow recipients to request a message to be released from quarantine** ( _PermissionToRequestRelease_ )</span></span>||![Marca de verificación](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="31d48-135">Si no le gustan los permisos predeterminados en los grupos de permisos preestablecidos, puede usar permisos personalizados cuando cree o modifique etiquetas de cuarentena personalizadas.</span><span class="sxs-lookup"><span data-stu-id="31d48-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="31d48-136">Para obtener más información acerca de lo que hace cada permiso, consulte la sección detalles de permisos de la [etiqueta de cuarentena](#quarantine-tag-permission-details) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="31d48-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="31d48-137">Puede crear y asignar etiquetas de cuarentena en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones de Exchange Online; independiente de EOP con PowerShell en organizaciones de EOP sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="31d48-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="31d48-138">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="31d48-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="31d48-139">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="31d48-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="31d48-140">Para ir directamente a la página **etiquetas de cuarentena** , Abra <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="31d48-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="31d48-141">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="31d48-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="31d48-142">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="31d48-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="31d48-143">Para ver, crear, modificar o quitar etiquetas de cuarentena, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="31d48-143">To view, create, modify, or remove quarantine tags, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="31d48-144">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="31d48-144">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="31d48-145">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="31d48-145">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="31d48-146">Paso 1: crear etiquetas de cuarentena en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="31d48-146">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="31d48-147">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración** \> **Policy** de amenazas y, a continuación, seleccione **marcas de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="31d48-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="31d48-148">En la página **etiquetas de cuarentena** , seleccione **Agregar etiqueta personalizada**.</span><span class="sxs-lookup"><span data-stu-id="31d48-148">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="31d48-149">Se abrirá el asistente **nueva etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="31d48-149">The **New tag** wizard opens.</span></span> <span data-ttu-id="31d48-150">En la página **nombre de etiqueta** , escriba un nombre breve pero único en el campo Nombre de **etiqueta** .</span><span class="sxs-lookup"><span data-stu-id="31d48-150">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="31d48-151">Deberá identificar y seleccionar la etiqueta por nombre en los próximos pasos.</span><span class="sxs-lookup"><span data-stu-id="31d48-151">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="31d48-152">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="31d48-152">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="31d48-153">En la página **acceso al mensaje de destinatarios** , seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="31d48-153">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="31d48-154">**Sin acceso**</span><span class="sxs-lookup"><span data-stu-id="31d48-154">**No access**</span></span>
   - <span data-ttu-id="31d48-155">**Acceso limitado**</span><span class="sxs-lookup"><span data-stu-id="31d48-155">**Limited access**</span></span>
   - <span data-ttu-id="31d48-156">**Acceso completo**</span><span class="sxs-lookup"><span data-stu-id="31d48-156">**Full access**</span></span>

   <span data-ttu-id="31d48-157">Los permisos individuales que se incluyen en estos grupos de permisos se describen anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="31d48-157">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="31d48-158">Para especificar permisos personalizados, seleccione **establecer acceso específico (avanzado)** y configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="31d48-158">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="31d48-159">**Seleccione versión preferencia** de la acción: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="31d48-159">**Select release action preference** : Select one of the following values:</span></span>
       - <span data-ttu-id="31d48-160">**No hay ninguna acción de liberación** : este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="31d48-160">**No release action** : This is the default value.</span></span>
       - <span data-ttu-id="31d48-161">**Permitir que los destinatarios liberen un mensaje de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="31d48-161">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="31d48-162">**Permitir que los destinatarios soliciten que se libere un mensaje de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="31d48-162">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="31d48-163">**Seleccionar acciones adicionales los destinatarios pueden realizar en los mensajes en cuarentena** : Seleccione algunos, todos o ninguno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="31d48-163">**Select additional actions recipients can take on quarantined messages** : Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="31d48-164">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="31d48-164">**Delete**</span></span>
       - <span data-ttu-id="31d48-165">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="31d48-165">**Preview**</span></span>
       - <span data-ttu-id="31d48-166">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-166">**Allow sender**</span></span>
       - <span data-ttu-id="31d48-167">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-167">**Block sender**</span></span>

   <span data-ttu-id="31d48-168">Estos permisos y su efecto en los mensajes en cuarentena y en las notificaciones de correo no deseado para el usuario final se describen en la sección [detalles de permisos de etiqueta de cuarentena](#quarantine-tag-permission-details) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="31d48-168">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="31d48-169">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="31d48-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="31d48-170">En la página de **Resumen** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="31d48-170">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="31d48-171">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="31d48-171">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="31d48-172">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="31d48-172">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="31d48-173">Haga clic en **listo** en la página de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="31d48-173">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="31d48-174">Ahora está listo para asignar la etiqueta Quarantine a una característica de cuarentena, tal como se describe en la sección [paso 2](#step-2-assign-a-quarantine-tag-to-supported-features) .</span><span class="sxs-lookup"><span data-stu-id="31d48-174">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="31d48-175">Crear etiquetas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="31d48-175">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="31d48-176">Si prefiere usar PowerShell para crear etiquetas de cuarentena, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use el cmdlet **New-QuarantineTag** .</span><span class="sxs-lookup"><span data-stu-id="31d48-176">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="31d48-177">Tiene dos métodos diferentes para elegir:</span><span class="sxs-lookup"><span data-stu-id="31d48-177">You have two different methods to choose from:</span></span>

- <span data-ttu-id="31d48-178">Use el parámetro _EndUserQuarantinePermissionsValue_ .</span><span class="sxs-lookup"><span data-stu-id="31d48-178">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="31d48-179">Use el parámetro _EndUserQuarantinePermissions_ .</span><span class="sxs-lookup"><span data-stu-id="31d48-179">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="31d48-180">Estos métodos se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="31d48-180">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="31d48-181">Usar el parámetro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="31d48-181">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="31d48-182">Para crear una etiqueta Quarantine con el parámetro _EndUserQuarantinePermissionsValue_ , use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="31d48-182">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="31d48-183">El parámetro _EndUserQuarantinePermissionsValue_ usa un valor decimal que se convierte a partir de un valor binario.</span><span class="sxs-lookup"><span data-stu-id="31d48-183">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="31d48-184">El valor binario corresponde a los permisos de cuarentena disponibles para el usuario final en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="31d48-184">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="31d48-185">Para cada permiso, el valor 1 equivale a verdadero y el valor 0 equivale a falso.</span><span class="sxs-lookup"><span data-stu-id="31d48-185">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="31d48-186">En la tabla siguiente se describen el orden y los valores necesarios para cada permiso individual en los grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="31d48-186">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="31d48-187">Permiso</span><span class="sxs-lookup"><span data-stu-id="31d48-187">Permission</span></span>|<span data-ttu-id="31d48-188">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="31d48-188">No access</span></span>|<span data-ttu-id="31d48-189">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="31d48-189">Limited access</span></span>|<span data-ttu-id="31d48-190">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="31d48-190">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="31d48-191">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="31d48-191">PermissionToAllowSender</span></span>|<span data-ttu-id="31d48-192">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-192">0</span></span>|<span data-ttu-id="31d48-193">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-193">0</span></span>|<span data-ttu-id="31d48-194">1</span><span class="sxs-lookup"><span data-stu-id="31d48-194">1</span></span>|
|<span data-ttu-id="31d48-195">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="31d48-195">PermissionToBlockSender</span></span>|<span data-ttu-id="31d48-196">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-196">0</span></span>|<span data-ttu-id="31d48-197">1</span><span class="sxs-lookup"><span data-stu-id="31d48-197">1</span></span>|<span data-ttu-id="31d48-198">1</span><span class="sxs-lookup"><span data-stu-id="31d48-198">1</span></span>|
|<span data-ttu-id="31d48-199">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="31d48-199">PermissionToDelete</span></span>|<span data-ttu-id="31d48-200">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-200">0</span></span>|<span data-ttu-id="31d48-201">1</span><span class="sxs-lookup"><span data-stu-id="31d48-201">1</span></span>|<span data-ttu-id="31d48-202">1</span><span class="sxs-lookup"><span data-stu-id="31d48-202">1</span></span>|
|<span data-ttu-id="31d48-203">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="31d48-203">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="31d48-204">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-204">0</span></span>|<span data-ttu-id="31d48-205">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-205">0</span></span>|<span data-ttu-id="31d48-206">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-206">0</span></span>|
|<span data-ttu-id="31d48-207">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="31d48-207">PermissionToPreview</span></span>|<span data-ttu-id="31d48-208">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-208">0</span></span>|<span data-ttu-id="31d48-209">1</span><span class="sxs-lookup"><span data-stu-id="31d48-209">1</span></span>|<span data-ttu-id="31d48-210">1</span><span class="sxs-lookup"><span data-stu-id="31d48-210">1</span></span>|
|<span data-ttu-id="31d48-211">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="31d48-211">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="31d48-212">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-212">0</span></span>|<span data-ttu-id="31d48-213">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-213">0</span></span>|<span data-ttu-id="31d48-214">1</span><span class="sxs-lookup"><span data-stu-id="31d48-214">1</span></span>|
|<span data-ttu-id="31d48-215">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="31d48-215">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="31d48-216">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-216">0</span></span>|<span data-ttu-id="31d48-217">1</span><span class="sxs-lookup"><span data-stu-id="31d48-217">1</span></span>|<span data-ttu-id="31d48-218">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-218">0</span></span>|
|<span data-ttu-id="31d48-219">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="31d48-219">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="31d48-220">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-220">0</span></span>|<span data-ttu-id="31d48-221">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-221">0</span></span>|<span data-ttu-id="31d48-222">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-222">0</span></span>|
|<span data-ttu-id="31d48-223">Valor binario</span><span class="sxs-lookup"><span data-stu-id="31d48-223">Binary value</span></span>|<span data-ttu-id="31d48-224">00000000</span><span class="sxs-lookup"><span data-stu-id="31d48-224">00000000</span></span>|<span data-ttu-id="31d48-225">01101010</span><span class="sxs-lookup"><span data-stu-id="31d48-225">01101010</span></span>|<span data-ttu-id="31d48-226">11101100</span><span class="sxs-lookup"><span data-stu-id="31d48-226">11101100</span></span>|
|<span data-ttu-id="31d48-227">Valor decimal que se va a usar</span><span class="sxs-lookup"><span data-stu-id="31d48-227">Decimal value to use</span></span>|<span data-ttu-id="31d48-228">comprendi</span><span class="sxs-lookup"><span data-stu-id="31d48-228">0</span></span>|<span data-ttu-id="31d48-229">106</span><span class="sxs-lookup"><span data-stu-id="31d48-229">106</span></span>|<span data-ttu-id="31d48-230">236</span><span class="sxs-lookup"><span data-stu-id="31d48-230">236</span></span>|

<span data-ttu-id="31d48-231"><sup>\*</sup> Actualmente, este valor siempre es 0.</span><span class="sxs-lookup"><span data-stu-id="31d48-231"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="31d48-232">Para PermissionToViewHeader, el valor 0 no oculta el botón **Ver encabezado de mensaje** en los detalles del mensaje en cuarentena (el botón siempre está disponible).</span><span class="sxs-lookup"><span data-stu-id="31d48-232">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="31d48-233"><sup>\*\*</sup> No establezca ninguno de estos valores en 1.</span><span class="sxs-lookup"><span data-stu-id="31d48-233"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="31d48-234">Establezca uno en 1 y el otro en 0, o establézcalo en 0.</span><span class="sxs-lookup"><span data-stu-id="31d48-234">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="31d48-235">En este ejemplo se crea un nuevo nombre de etiqueta de cuarentena NoAccess que asigna los permisos sin acceso como se describe en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="31d48-235">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="31d48-236">Para los permisos de acceso limitado, use el valor 106.</span><span class="sxs-lookup"><span data-stu-id="31d48-236">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="31d48-237">Para los permisos de acceso total, use el valor 236.</span><span class="sxs-lookup"><span data-stu-id="31d48-237">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="31d48-238">Para los permisos personalizados, use la tabla anterior para obtener el valor binario correspondiente a los permisos que desee.</span><span class="sxs-lookup"><span data-stu-id="31d48-238">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="31d48-239">Convierta el valor binario a un valor decimal y use el valor decimal para el parámetro _EndUserQuarantinePermissionsValue_ .</span><span class="sxs-lookup"><span data-stu-id="31d48-239">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="31d48-240">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="31d48-240">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="31d48-241">Usar el parámetro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="31d48-241">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="31d48-242">Para crear una etiqueta Quarantine con el parámetro _EndUserQuarantinePermissionsValue_ , siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31d48-242">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="31d48-243">A.</span><span class="sxs-lookup"><span data-stu-id="31d48-243">A.</span></span> <span data-ttu-id="31d48-244">Almacene un objeto de permisos de cuarentena en una variable con el cmdlet **New-QuarantinePermissions** .</span><span class="sxs-lookup"><span data-stu-id="31d48-244">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>
<br/>
<span data-ttu-id="31d48-245">B.</span><span class="sxs-lookup"><span data-stu-id="31d48-245">B.</span></span> <span data-ttu-id="31d48-246">Use la variable como el valor _EndUserQuarantinePermissions_ en el comando **New-QuarantineTag** .</span><span class="sxs-lookup"><span data-stu-id="31d48-246">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="31d48-247">Paso A: almacenar un objeto de permisos de cuarentena en una variable</span><span class="sxs-lookup"><span data-stu-id="31d48-247">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="31d48-248">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="31d48-248">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="31d48-249">El valor predeterminado para los parámetros no usados es `$false` , por lo que solo necesita usar los parámetros en los que desea establecer el valor `$true` .</span><span class="sxs-lookup"><span data-stu-id="31d48-249">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="31d48-250">Los ejemplos siguientes muestran cómo crear objetos de permiso que corresponden a los grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="31d48-250">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="31d48-251">**Sin acceso** :</span><span class="sxs-lookup"><span data-stu-id="31d48-251">**No access** :</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="31d48-252">**Acceso limitado** :</span><span class="sxs-lookup"><span data-stu-id="31d48-252">**Limited access** :</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="31d48-253">**Acceso total** :</span><span class="sxs-lookup"><span data-stu-id="31d48-253">**Full access** :</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="31d48-254">Para ver los valores que ha establecido, ejecute el nombre de variable como un comando (por ejemplo, ejecute el comando `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="31d48-254">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="31d48-255">Para los permisos personalizados, no establezca los parámetros _PermissionToRelease_ y _PermissionToRequestRelease_ en `$true` .</span><span class="sxs-lookup"><span data-stu-id="31d48-255">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="31d48-256">Establezca uno en `$true` y déjelo como `$false` , o deje ambos como `$false` .</span><span class="sxs-lookup"><span data-stu-id="31d48-256">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="31d48-257">También puede modificar una variable de objeto de permisos existente después de crearla, pero antes de usarla mediante el cmdlet **set-QuarantinePermissions** .</span><span class="sxs-lookup"><span data-stu-id="31d48-257">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="31d48-258">Para obtener información más detallada acerca de la sintaxis y los parámetros, consulte [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) y [set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="31d48-258">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="31d48-259">Paso B: usar la variable en el comando New-QuarantineTag</span><span class="sxs-lookup"><span data-stu-id="31d48-259">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="31d48-260">Una vez que haya creado y guardado el objeto Permissions en una variable, use la variable para el valor del parámetro _EndUserQuarantinePermission_ en el siguiente comando **New-QuarantineTag** :</span><span class="sxs-lookup"><span data-stu-id="31d48-260">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="31d48-261">En este ejemplo se crea una nueva etiqueta Quarantine llamada LimitedAccess mediante el `$LimitedAccess` objeto Permissions descrito y creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="31d48-261">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="31d48-262">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="31d48-262">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="31d48-263">Paso 2: asignar una etiqueta de cuarentena a las características admitidas</span><span class="sxs-lookup"><span data-stu-id="31d48-263">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="31d48-264">En las características de protección _admitidas_ que ponen mensajes o archivos en cuarentena (de forma automática o como una acción configurable), puede asignar una etiqueta Quarantine a las acciones de cuarentena disponibles.</span><span class="sxs-lookup"><span data-stu-id="31d48-264">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="31d48-265">En la tabla siguiente se describen las características que ponen en cuarentena los mensajes y la disponibilidad de las etiquetas de cuarentena:</span><span class="sxs-lookup"><span data-stu-id="31d48-265">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="31d48-266">Característica</span><span class="sxs-lookup"><span data-stu-id="31d48-266">Feature</span></span>|<span data-ttu-id="31d48-267">¿Se admiten las etiquetas de cuarentena?</span><span class="sxs-lookup"><span data-stu-id="31d48-267">Quarantine tags supported?</span></span>|<span data-ttu-id="31d48-268">Etiquetas de cuarentena predeterminadas usadas</span><span class="sxs-lookup"><span data-stu-id="31d48-268">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="31d48-269">[Directivas contra correo no deseado](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="31d48-269">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="31d48-270">**Correo no deseado** ( _SpamAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-270">**Spam** ( _SpamAction_ )</span></span></li><li><span data-ttu-id="31d48-271">**Correo no deseado de alta confianza** ( _HighConfidenceSpamAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-271">**High confidence spam** ( _HighConfidenceSpamAction_ )</span></span></li><li><span data-ttu-id="31d48-272">**Correo electrónico de suplantación de identidad** ( _PhishSpamAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-272">**Phishing email** ( _PhishSpamAction_ )</span></span></li><li><span data-ttu-id="31d48-273">**Correo electrónico de suplantación de identidad de alta confianza** ( _HighConfidencePhishAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-273">**High confidence phishing email** ( _HighConfidencePhishAction_ )</span></span></li><li><span data-ttu-id="31d48-274">**Correo electrónico masivo** ( _BulkSpamAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-274">**Bulk email** ( _BulkSpamAction_ )</span></span></li></ul>|<span data-ttu-id="31d48-275">Sí</span><span class="sxs-lookup"><span data-stu-id="31d48-275">Yes</span></span>|<ul><li><span data-ttu-id="31d48-276">DefaultSpamTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="31d48-276">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="31d48-277">DefaultHighConfSpamTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="31d48-277">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="31d48-278">DefaultPhishTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="31d48-278">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="31d48-279">DefaultHighConfPhishTag (sin acceso)</span><span class="sxs-lookup"><span data-stu-id="31d48-279">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="31d48-280">DefaultBulkTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="31d48-280">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="31d48-281">Directivas contra la suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="31d48-281">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="31d48-282">[Protección de inteligencia de suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-282">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</span></span></li><li><span data-ttu-id="31d48-283">[Protección de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="31d48-283">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="31d48-284">**Si un usuario suplantado envía un correo electrónico** ( _TargetedUserProtectionAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-284">**If email is sent by an impersonated user** ( _TargetedUserProtectionAction_ )</span></span></li><li><span data-ttu-id="31d48-285">**Si un dominio suplantado envía un correo electrónico** ( _TargetedDomainProtectionAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-285">**If email is sent by an impersonated domain** ( _TargetedDomainProtectionAction_ )</span></span></li><li><span data-ttu-id="31d48-286">Inteligencia de buzones **Mailbox intelligence** \> **Si un usuario suplantado envía un correo electrónico** ( _MailboxIntelligenceProtectionAction_ )</span><span class="sxs-lookup"><span data-stu-id="31d48-286">**Mailbox intelligence** \> **If email is sent by an impersonated user** ( _MailboxIntelligenceProtectionAction_ )</span></span></li></ul></li></ul></ul>|<span data-ttu-id="31d48-287">No</span><span class="sxs-lookup"><span data-stu-id="31d48-287">No</span></span>|<span data-ttu-id="31d48-288">No aplicable</span><span class="sxs-lookup"><span data-stu-id="31d48-288">n/a</span></span>|
|<span data-ttu-id="31d48-289">[Directivas antimalware](configure-anti-malware-policies.md): todos los mensajes detectados siempre se ponen en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-289">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="31d48-290">No</span><span class="sxs-lookup"><span data-stu-id="31d48-290">No</span></span>|<span data-ttu-id="31d48-291">No aplicable</span><span class="sxs-lookup"><span data-stu-id="31d48-291">n/a</span></span>|
|[<span data-ttu-id="31d48-292">ATP para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31d48-292">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="31d48-293">No</span><span class="sxs-lookup"><span data-stu-id="31d48-293">No</span></span>|<span data-ttu-id="31d48-294">No aplicable</span><span class="sxs-lookup"><span data-stu-id="31d48-294">n/a</span></span>|
|<span data-ttu-id="31d48-295">[Reglas de flujo de correo](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (también conocidas como reglas de transporte) con la acción: **entregar el mensaje a la cuarentena hospedada** ( _cuarentena_ ).</span><span class="sxs-lookup"><span data-stu-id="31d48-295">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** ( _Quarantine_ ).</span></span>|<span data-ttu-id="31d48-296">No</span><span class="sxs-lookup"><span data-stu-id="31d48-296">No</span></span>|<span data-ttu-id="31d48-297">No aplicable</span><span class="sxs-lookup"><span data-stu-id="31d48-297">n/a</span></span>|
|

<span data-ttu-id="31d48-298"><sup>\*</sup> La configuración de protección de suplantación solo está disponible en directivas antiphishing en Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="31d48-298"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="31d48-299">Si está satisfecho con los permisos de usuario final que proporcionan las etiquetas de cuarentena predeterminadas, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="31d48-299">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="31d48-300">Si desea personalizar las funciones del usuario final (botones disponibles) en las notificaciones de correo no deseado del usuario final o en los detalles de los mensajes en cuarentena, puede asignar una etiqueta de cuarentena personalizada.</span><span class="sxs-lookup"><span data-stu-id="31d48-300">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="31d48-301">Asignar etiquetas de cuarentena en directivas contra correo no deseado en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="31d48-301">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="31d48-302">En [configurar las directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)se describen las instrucciones completas para la creación y modificación de las directivas contra el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="31d48-302">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="31d48-303">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración** \> **Policy** \> de amenazas y, a continuación, seleccione **anti-spam**.</span><span class="sxs-lookup"><span data-stu-id="31d48-303">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="31d48-304">O bien, Abra <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="31d48-304">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="31d48-305">Busque y seleccione una directiva contra correo no deseado existente para editarla o cree una nueva Directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="31d48-305">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="31d48-306">En el control flotante detalles de la Directiva, expanda la sección **acciones en masa y correo no deseado** .</span><span class="sxs-lookup"><span data-stu-id="31d48-306">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>
  
4. <span data-ttu-id="31d48-307">Si ha seleccionado **mensaje en cuarentena** para la acción de un veredicto de filtrado de correo no deseado disponible, el cuadro **Aplicar etiqueta de directiva de cuarentena** estará disponible para que seleccione la etiqueta de cuarentena para dicho veredicto.</span><span class="sxs-lookup"><span data-stu-id="31d48-307">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="31d48-308">**Nota** : cuando se crea una nueva Directiva, un valor de etiqueta de cuarentena en blanco para un veredicto de filtrado de correo no deseado indica que se usa la etiqueta de cuarentena predeterminada para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="31d48-308">**Note** : When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="31d48-309">Cuando edita la directiva más adelante, los valores en blanco se reemplazan por los nombres de las etiquetas de cuarentena predeterminadas reales, tal como se describe en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="31d48-309">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>
  
   ![Selecciones de etiquetas de cuarentena en una directiva contra correo no deseado](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="31d48-311">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="31d48-311">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="31d48-312">Asignar etiquetas de cuarentena en directivas contra correo no deseado en PowerShell</span><span class="sxs-lookup"><span data-stu-id="31d48-312">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="31d48-313">Si prefiere usar PowerShell para asignar etiquetas de cuarentena en directivas contra correo no deseado, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="31d48-313">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="31d48-314">**Notas** :</span><span class="sxs-lookup"><span data-stu-id="31d48-314">**Notes** :</span></span>

- <span data-ttu-id="31d48-315">El valor predeterminado para el parámetro _HighConfidencePhishAction_ es Quarantine, por lo que no es necesario configurar la acción de cuarentena para detecciones de suplantación de identidad (phishing) de alta confianza en nuevas directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="31d48-315">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="31d48-316">Para todos los demás veredictos del filtrado de correo no deseado en las directivas contra correo no deseado nuevas o existentes, la etiqueta Quarantine solo es efectiva si el valor de la acción es Quarantine.</span><span class="sxs-lookup"><span data-stu-id="31d48-316">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="31d48-317">Para ver los valores de la acción en las directivas antispam existentes, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="31d48-317">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="31d48-318">Para obtener información sobre los valores de acción predeterminada y los valores de acción recomendados para Standard y Strict, vea configuración de la [Directiva contra correo no deseado de EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="31d48-318">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="31d48-319">Un veredicto de filtrado de correo no deseado sin un parámetro correspondiente de la etiqueta Quarantine significa que se usa la [etiqueta de cuarentena predeterminada](#step-2-assign-a-quarantine-tag-to-supported-features) para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="31d48-319">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="31d48-320">Sólo tiene que reemplazar una etiqueta Quarantine predeterminada por una etiqueta de cuarentena personalizada si desea cambiar las funciones predeterminadas del usuario final en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-320">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="31d48-321">Una nueva Directiva contra correo no deseado en PowerShell requiere una directiva de filtro de correo no deseado (configuración) mediante el cmdlet **New-HostedContentFilterPolicy** y una nueva regla de filtro de correo no deseado (filtros de destinatario) mediante el cmdlet **New-HostedContentFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="31d48-321">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="31d48-322">Para obtener instrucciones, vea [usar PowerShell para crear directivas contra correo no deseado](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="31d48-322">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="31d48-323">En este ejemplo se crea una nueva Directiva de filtro de correo no deseado denominada Research Department con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="31d48-323">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="31d48-324">La acción para todos los veredictos de filtrado de correo no deseado se establece en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-324">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="31d48-325">La etiqueta de cuarentena personalizada denominada NoAccess, que no asigna permisos de **acceso** , reemplaza a todas las etiquetas de cuarentena predeterminadas que aún no no **contengan** permisos de acceso de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="31d48-325">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="31d48-326">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31d48-326">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="31d48-327">En este ejemplo se modifica la Directiva de filtro de correo no deseado existente denominada Human Resources.</span><span class="sxs-lookup"><span data-stu-id="31d48-327">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="31d48-328">La acción para el veredicto de cuarentena de correo no deseado se establece en cuarentena y se asigna la etiqueta de cuarentena personalizada denominada NoAccess.</span><span class="sxs-lookup"><span data-stu-id="31d48-328">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="31d48-329">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31d48-329">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="31d48-330">Configurar las opciones globales de notificación de cuarentena en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="31d48-330">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="31d48-331">La configuración global de las etiquetas de cuarentena le permite personalizar las notificaciones de correo no deseado para el usuario final que se envían a los destinatarios de los mensajes que se pusieron en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-331">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="31d48-332">Para obtener más información acerca de estas notificaciones, consulte [End-User spam Notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="31d48-332">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="31d48-333">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración** \> **Policy** de amenazas y, a continuación, seleccione **marcas de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="31d48-333">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="31d48-334">En la página **etiquetas de cuarentena** , seleccione **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="31d48-334">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="31d48-335">En el control flotante **configuración de notificación de cuarentena** que se abre, configure algunas o todas las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="31d48-335">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="31d48-336">**Usar mi logotipo de la compañía** : Seleccione esta opción para reemplazar el logotipo de Microsoft predeterminado que se usa en la parte superior de las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="31d48-336">**Use my company logo** : Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="31d48-337">Antes de hacerlo, debe seguir las instrucciones que se indican en [customize the Microsoft 365 Theme for your Organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to Upload your custom logo.</span><span class="sxs-lookup"><span data-stu-id="31d48-337">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="31d48-338">En la siguiente captura de pantalla se muestra un logotipo personalizado en una notificación de correo no deseado para el usuario final:</span><span class="sxs-lookup"><span data-stu-id="31d48-338">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Un logotipo personalizado en una notificación de correo no deseado para el usuario final](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="31d48-340">**Elija lenguaje** : las notificaciones de correo no deseado para el usuario final ya se localizan en función de la configuración de idioma del destinatario.</span><span class="sxs-lookup"><span data-stu-id="31d48-340">**Choose language** : End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="31d48-341">Puede especificar texto personalizado en diferentes idiomas para el **nombre para mostrar** y los valores de **declinación de responsabilidades** .</span><span class="sxs-lookup"><span data-stu-id="31d48-341">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="31d48-342">Seleccione al menos un idioma en el cuadro primer idioma y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="31d48-342">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="31d48-343">Puede seleccionar varios idiomas haciendo clic en **Agregar** después de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="31d48-343">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="31d48-344">Un cuadro de idioma de sección muestra todos los idiomas que ha seleccionado:</span><span class="sxs-lookup"><span data-stu-id="31d48-344">A section language box shows all of the languages that you've selected:</span></span>

     ![Idiomas seleccionados en el segundo cuadro de idioma de la configuración de notificación de cuarentena global de las etiquetas de cuarentena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="31d48-346">**Nombre para mostrar** : personalizar el nombre para mostrar del remitente que se usa en las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="31d48-346">**Display name** : Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="31d48-347">Para cada idioma que haya agregado, seleccione el idioma en el cuadro segundo idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro **nombre para mostrar** .</span><span class="sxs-lookup"><span data-stu-id="31d48-347">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="31d48-348">En la siguiente captura de pantalla se muestra el nombre para mostrar personalizado en una notificación de correo no deseado para el usuario final:</span><span class="sxs-lookup"><span data-stu-id="31d48-348">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Un nombre para mostrar del remitente personalizado en una notificación de correo no deseado del usuario final](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="31d48-350">**Declinación de responsabilidades** : agregar una declinación de responsabilidades personalizada a la parte inferior de las notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="31d48-350">**Disclaimer** : Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="31d48-351">El texto localizado, **un aviso de declinación de responsabilidades de su organización:** siempre se incluye en primer lugar, seguido del texto que especifique.</span><span class="sxs-lookup"><span data-stu-id="31d48-351">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="31d48-352">Para cada idioma que haya agregado, seleccione el idioma en el cuadro segundo idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro **declinación de responsabilidades** .</span><span class="sxs-lookup"><span data-stu-id="31d48-352">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="31d48-353">En la siguiente captura de pantalla se muestra la declinación de responsabilidades personalizada en una notificación de correo no deseado de usuario final:</span><span class="sxs-lookup"><span data-stu-id="31d48-353">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Una declinación de responsabilidades personalizada en la parte inferior de una notificación de correo no deseado de usuario final](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="31d48-355">Ver las etiquetas de cuarentena en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="31d48-355">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="31d48-356">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración** \> **Policy** de amenazas y, a continuación, seleccione **marcas de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="31d48-356">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="31d48-357">Para ver la configuración de las etiquetas de cuarentena integradas o personalizadas, seleccione la etiqueta cuarentena de la lista (no active la casilla de verificación).</span><span class="sxs-lookup"><span data-stu-id="31d48-357">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="31d48-358">Para ver la configuración global, seleccione **configuración global**</span><span class="sxs-lookup"><span data-stu-id="31d48-358">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="31d48-359">Ver las etiquetas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="31d48-359">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="31d48-360">Si prefiere usar PowerShell para ver las etiquetas de cuarentena, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="31d48-360">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="31d48-361">Para ver una lista de Resumen de todas las etiquetas integradas o personalizadas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="31d48-361">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="31d48-362">Para ver la configuración de las etiquetas de cuarentena integradas o personalizadas, reemplace \<TagName\> por el nombre de la etiqueta Quarantine y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="31d48-362">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="31d48-363">Para ver la configuración global, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="31d48-363">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="31d48-364">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="31d48-364">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="31d48-365">Quitar las etiquetas de cuarentena en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="31d48-365">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="31d48-366">**Notas** :</span><span class="sxs-lookup"><span data-stu-id="31d48-366">**Notes** :</span></span>

- <span data-ttu-id="31d48-367">No puede quitar las etiquetas de cuarentena integradas.</span><span class="sxs-lookup"><span data-stu-id="31d48-367">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="31d48-368">Antes de quitar una etiqueta de cuarentena personalizada, compruebe que no se esté usando.</span><span class="sxs-lookup"><span data-stu-id="31d48-368">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="31d48-369">Por ejemplo, ejecute el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="31d48-369">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="31d48-370">Si se está usando la etiqueta Quarantine, [reemplace la etiqueta cuarentena asignada antes de](#step-2-assign-a-quarantine-tag-to-supported-features) quitarla.</span><span class="sxs-lookup"><span data-stu-id="31d48-370">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="31d48-371">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración** \> **Policy** de amenazas y, a continuación, seleccione **marcas de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="31d48-371">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="31d48-372">En la página **etiquetas de cuarentena** , seleccione la etiqueta de cuarentena personalizada que desee quitar y, a continuación, haga clic en **Eliminar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="31d48-372">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="31d48-373">Haga clic en **quitar etiqueta** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="31d48-373">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="31d48-374">Quitar etiquetas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="31d48-374">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="31d48-375">Si prefiere usar PowerShell para quitar una etiqueta de cuarentena personalizada, reemplace \<TagName\> por el nombre de la etiqueta Quarantine y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="31d48-375">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="31d48-376">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="31d48-376">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="31d48-377">Detalles del permiso de etiqueta de cuarentena</span><span class="sxs-lookup"><span data-stu-id="31d48-377">Quarantine tag permission details</span></span>

<span data-ttu-id="31d48-378">En las secciones siguientes se describen los efectos de los grupos de permisos predeterminados y los permisos individuales en los detalles de los mensajes en cuarentena y en las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="31d48-378">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="31d48-379">Grupos de permisos preestablecidos</span><span class="sxs-lookup"><span data-stu-id="31d48-379">Preset permissions groups</span></span>

<span data-ttu-id="31d48-380">Los permisos individuales que se incluyen en los grupos de permisos preestablecidos se enumeran en la tabla al principio de este artículo.</span><span class="sxs-lookup"><span data-stu-id="31d48-380">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="31d48-381">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="31d48-381">No access</span></span>

<span data-ttu-id="31d48-382">Si la etiqueta Quarantine asigna los permisos **sin acceso** (sin permisos), los usuarios seguirán teniendo algunas capacidades de línea base:</span><span class="sxs-lookup"><span data-stu-id="31d48-382">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="31d48-383">**Detalles del mensaje en cuarentena** : el botón **Ver encabezado del mensaje** siempre está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-383">**Quarantined message details** : The **View message header** button is always available.</span></span>

  ![Botones disponibles en los detalles de los mensajes en cuarentena si la etiqueta Quarantine da al usuario ningún permiso de acceso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="31d48-385">**Notificaciones de correo no deseado para el usuario final** : siempre está disponible el botón **revisar** que lleva al usuario al mensaje en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-385">**End-user spam notifications** : The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Botones disponibles en la notificación de correo no deseado para el usuario final si la etiqueta Quarantine da al usuario ningún permiso de acceso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="31d48-387">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="31d48-387">Limited access</span></span>

<span data-ttu-id="31d48-388">Si la etiqueta Quarantine asigna los permisos de **acceso limitado** , los usuarios obtienen las siguientes capacidades:</span><span class="sxs-lookup"><span data-stu-id="31d48-388">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="31d48-389">**Detalles del mensaje en cuarentena** : están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="31d48-389">**Quarantined message details** : The following buttons are available:</span></span>
  - <span data-ttu-id="31d48-390">**Publicación de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="31d48-390">**Request release**</span></span>
  - <span data-ttu-id="31d48-391">**Ver encabezado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="31d48-391">**View message header**</span></span>
  - <span data-ttu-id="31d48-392">**Vista previa del mensaje**</span><span class="sxs-lookup"><span data-stu-id="31d48-392">**Preview message**</span></span>
  - <span data-ttu-id="31d48-393">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-393">**Block sender**</span></span>
  - <span data-ttu-id="31d48-394">**Quitar de cuarentena**</span><span class="sxs-lookup"><span data-stu-id="31d48-394">**Remove from quarantine**</span></span>

  ![Botones disponibles en los detalles de los mensajes en cuarentena si la etiqueta Quarantine da a los usuarios permisos de acceso limitado](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="31d48-396">**Notificaciones de correo no deseado para el usuario final** : están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="31d48-396">**End-user spam notifications** : The following buttons are available:</span></span>
  - <span data-ttu-id="31d48-397">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-397">**Block sender**</span></span>
  - <span data-ttu-id="31d48-398">**Revisar**</span><span class="sxs-lookup"><span data-stu-id="31d48-398">**Review**</span></span>

  ![Botones disponibles en la notificación de correo no deseado para el usuario final si la etiqueta Quarantine da a los usuarios permisos de acceso limitado](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="31d48-400">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="31d48-400">Full access</span></span>

<span data-ttu-id="31d48-401">Si la etiqueta Quarantine asigna los permisos de **acceso total** (todos los permisos disponibles), los usuarios obtienen las siguientes capacidades:</span><span class="sxs-lookup"><span data-stu-id="31d48-401">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="31d48-402">**Detalles del mensaje en cuarentena** : están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="31d48-402">**Quarantined message details** : The following buttons are available:</span></span>
  - <span data-ttu-id="31d48-403">**Liberar mensaje**</span><span class="sxs-lookup"><span data-stu-id="31d48-403">**Release message**</span></span>
  - <span data-ttu-id="31d48-404">**Ver encabezado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="31d48-404">**View message header**</span></span>
  - <span data-ttu-id="31d48-405">**Vista previa del mensaje**</span><span class="sxs-lookup"><span data-stu-id="31d48-405">**Preview message**</span></span>
  - <span data-ttu-id="31d48-406">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-406">**Block sender**</span></span>
  - <span data-ttu-id="31d48-407">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-407">**Allow sender**</span></span>
  - <span data-ttu-id="31d48-408">**Quitar de cuarentena**</span><span class="sxs-lookup"><span data-stu-id="31d48-408">**Remove from quarantine**</span></span>

  ![Botones disponibles en los detalles de los mensajes en cuarentena si la etiqueta Quarantine da a los usuarios permisos de acceso total](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="31d48-410">**Notificaciones de correo no deseado para el usuario final** : están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="31d48-410">**End-user spam notifications** : The following buttons are available:</span></span>
  - <span data-ttu-id="31d48-411">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="31d48-411">**Block sender**</span></span>
  - <span data-ttu-id="31d48-412">**Versión**</span><span class="sxs-lookup"><span data-stu-id="31d48-412">**Release**</span></span>
  - <span data-ttu-id="31d48-413">**Revisar**</span><span class="sxs-lookup"><span data-stu-id="31d48-413">**Review**</span></span>

  ![Botones disponibles en la notificación de correo no deseado para el usuario final si la etiqueta Quarantine da a los usuarios permisos de acceso total](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="31d48-415">Permisos individuales</span><span class="sxs-lookup"><span data-stu-id="31d48-415">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="31d48-416">Recuerde que los usuarios siempre obtienen los botones descritos en la sección [sin acceso](#no-access) .</span><span class="sxs-lookup"><span data-stu-id="31d48-416">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="31d48-417">Estos botones no se incluyen en las descripciones de los permisos individuales.</span><span class="sxs-lookup"><span data-stu-id="31d48-417">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="31d48-418">Permiso Permitir remitente</span><span class="sxs-lookup"><span data-stu-id="31d48-418">Allow sender permission</span></span>

<span data-ttu-id="31d48-419">El permiso **Permitir remitente** ( _PermissionToAllowSender_ ) controla el acceso al botón que permite a los usuarios agregar de forma cómoda el remitente del mensaje en cuarentena a la lista de remitentes seguros.</span><span class="sxs-lookup"><span data-stu-id="31d48-419">The **Allow sender** permission ( _PermissionToAllowSender_ ) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="31d48-420">**Detalles del mensaje en cuarentena** :</span><span class="sxs-lookup"><span data-stu-id="31d48-420">**Quarantined message details** :</span></span>
  - <span data-ttu-id="31d48-421">Permiso **Permitir remitente** habilitado: el botón **Permitir remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-421">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="31d48-422">Permiso **Permitir remitente** deshabilitado: el botón **Permitir remitente** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-422">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="31d48-423">**Notificaciones de correo no deseado para el usuario final** : sin efecto.</span><span class="sxs-lookup"><span data-stu-id="31d48-423">**End-user spam notifications** : No effect.</span></span>

<span data-ttu-id="31d48-424">Para obtener más información acerca de la lista de remitentes seguros, consulte [impedir el bloqueo de remitentes de confianza](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) y [usar Exchange Online PowerShell para configurar la colección de listas seguras en un buzón](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="31d48-424">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="31d48-425">Permiso bloquear remitente</span><span class="sxs-lookup"><span data-stu-id="31d48-425">Block sender permission</span></span>

<span data-ttu-id="31d48-426">El permiso **bloquear remitente** ( _PermissionToBlockSender_ ) controla el acceso al botón que permite a los usuarios agregar convenientemente el remitente del mensaje en cuarentena a la lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="31d48-426">The **Block sender** permission ( _PermissionToBlockSender_ ) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="31d48-427">**Detalles del mensaje en cuarentena** :</span><span class="sxs-lookup"><span data-stu-id="31d48-427">**Quarantined message details** :</span></span>
  - <span data-ttu-id="31d48-428">Permiso **bloquear remitente** habilitado: el botón **bloquear remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-428">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="31d48-429">Permiso **bloquear remitente** deshabilitado: el botón **bloquear remitente** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="31d48-430">**Notificaciones de correo no deseado para el usuario final** :</span><span class="sxs-lookup"><span data-stu-id="31d48-430">**End-user spam notifications** :</span></span>
  - <span data-ttu-id="31d48-431">Permiso **bloquear remitente** deshabilitado: el botón **bloquear remitente** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-431">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="31d48-432">Permiso **bloquear remitente** habilitado: el botón **bloquear remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-432">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="31d48-433">Para obtener más información acerca de la lista de remitentes bloqueados, vea [bloquear mensajes de alguien](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) y [usar Exchange Online PowerShell para configurar la colección de listas seguras en un buzón](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="31d48-433">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="31d48-434">Permiso de eliminación</span><span class="sxs-lookup"><span data-stu-id="31d48-434">Delete permission</span></span>

<span data-ttu-id="31d48-435">El permiso de **eliminación** ( _PermissionToDelete_ ) controla la capacidad de los usuarios de eliminar sus mensajes (mensajes en los que el usuario es un destinatario) de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-435">The **Delete** permission ( _PermissionToDelete_ ) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="31d48-436">**Detalles del mensaje en cuarentena** :</span><span class="sxs-lookup"><span data-stu-id="31d48-436">**Quarantined message details** :</span></span>
  - <span data-ttu-id="31d48-437">Permiso de **eliminación** habilitado: el botón **quitar la cuarentena** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-437">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="31d48-438">Permiso de **eliminación** deshabilitado: el botón **quitar de cuarentena** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-438">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="31d48-439">**Notificaciones de correo no deseado para el usuario final** : sin efecto.</span><span class="sxs-lookup"><span data-stu-id="31d48-439">**End-user spam notifications** : No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="31d48-440">Permiso de vista previa</span><span class="sxs-lookup"><span data-stu-id="31d48-440">Preview permission</span></span>

<span data-ttu-id="31d48-441">El permiso de **vista previa** ( _PermissionToPreview_ ) controla la capacidad de los usuarios de obtener una vista previa de los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-441">The **Preview** permission ( _PermissionToPreview_ ) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="31d48-442">**Detalles del mensaje en cuarentena** :</span><span class="sxs-lookup"><span data-stu-id="31d48-442">**Quarantined message details** :</span></span>
  - <span data-ttu-id="31d48-443">Permiso de **vista previa** habilitado: el botón **vista previa del mensaje** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-443">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="31d48-444">Permiso de **vista previa** deshabilitado: el botón **vista previa de mensaje** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-444">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="31d48-445">**Notificaciones de correo no deseado para el usuario final** : sin efecto.</span><span class="sxs-lookup"><span data-stu-id="31d48-445">**End-user spam notifications** : No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="31d48-446">Permitir que los destinatarios liberen un mensaje del permiso de cuarentena</span><span class="sxs-lookup"><span data-stu-id="31d48-446">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="31d48-447">El permiso **permitir a los destinatarios publicar un mensaje de cuarentena** ( _PermissionToRelease_ ) controla la capacidad de los usuarios de liberar los mensajes en cuarentena directamente y sin la aprobación de un administrador.</span><span class="sxs-lookup"><span data-stu-id="31d48-447">The **Allow recipients to release a message from quarantine** permission ( _PermissionToRelease_ ) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="31d48-448">**Detalles del mensaje en cuarentena** :</span><span class="sxs-lookup"><span data-stu-id="31d48-448">**Quarantined message details** :</span></span>
  - <span data-ttu-id="31d48-449">Permiso habilitado: el botón **liberar mensaje** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-449">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="31d48-450">Permiso deshabilitado: el botón **liberar mensaje** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-450">Permission disabled: The **Release message** button is not available.</span></span>
  
- <span data-ttu-id="31d48-451">**Notificaciones de correo no deseado para el usuario final** :</span><span class="sxs-lookup"><span data-stu-id="31d48-451">**End-user spam notifications** :</span></span>
  - <span data-ttu-id="31d48-452">Permiso habilitado: el botón **liberar** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-452">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="31d48-453">Permiso deshabilitado: el botón **liberar** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-453">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="31d48-454">Permitir que los destinatarios soliciten que se libere un mensaje del permiso de cuarentena</span><span class="sxs-lookup"><span data-stu-id="31d48-454">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="31d48-455">El permiso permitir que los **destinatarios soliciten un mensaje se libere del** permiso de cuarentena ( _PermissionToRequestRelease_ ) controla la capacidad de los usuarios de _solicitar_ la liberación de sus mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="31d48-455">The **Allow recipients to request a message to be released from quarantine** permission ( _PermissionToRequestRelease_ ) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="31d48-456">El mensaje solo se publica después de que un administrador apruebe la solicitud.</span><span class="sxs-lookup"><span data-stu-id="31d48-456">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="31d48-457">**Detalles del mensaje en cuarentena** :</span><span class="sxs-lookup"><span data-stu-id="31d48-457">**Quarantined message details** :</span></span>
  - <span data-ttu-id="31d48-458">Permiso habilitado: el botón **Solicitar versión** está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-458">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="31d48-459">Permiso deshabilitado: el botón de la versión de la **solicitud** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-459">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="31d48-460">**Notificaciones de correo no deseado para el usuario final** : el botón **liberar** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="31d48-460">**End-user spam notifications** : The **Release** button is not available.</span></span>
