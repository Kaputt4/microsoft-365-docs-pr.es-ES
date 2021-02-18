---
title: Etiquetas de cuarentena
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Los administradores pueden aprender a usar etiquetas de cuarentena para controlar lo que los usuarios pueden hacer con sus mensajes en cuarentena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 207f22c9acaa183e195f5a2ee33be65cdf4991dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289418"
---
# <a name="quarantine-tags"></a><span data-ttu-id="b5120-103">Etiquetas de cuarentena</span><span class="sxs-lookup"><span data-stu-id="b5120-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="b5120-104">Las características que se describen en este artículo están actualmente en versión preliminar, no están disponibles para todos los usuarios y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="b5120-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="b5120-105">Las etiquetas de cuarentena en Exchange Online Protection (EOP) permiten a los administradores controlar lo que los usuarios pueden hacer con sus mensajes en cuarentena en función de cómo el mensaje llegó a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="b5120-106">EOP ha permitido o impedido tradicionalmente ciertos niveles de interactividad para mensajes en cuarentena y en notificaciones de correo no deseado [para el usuario final.](use-spam-notifications-to-release-and-report-quarantined-messages.md) [](find-and-release-quarantined-messages-as-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="b5120-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="b5120-107">Por ejemplo, los usuarios finales pueden ver y liberar mensajes que el filtrado contra correo no deseado ha puesto en cuarentena como correo no deseado o masivo, pero no pueden ver ni liberar mensajes que se han puesto en cuarentena como suplantación de identidad de confianza alta.</span><span class="sxs-lookup"><span data-stu-id="b5120-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="b5120-108">Para [](#step-2-assign-a-quarantine-tag-to-supported-features)las características de protección admitidas, las etiquetas de cuarentena especifican lo que los usuarios pueden hacer en los mensajes de notificación de correo no deseado para el usuario final y en los mensajes en cuarentena en cuarentena (mensajes en los que el usuario es un destinatario).</span><span class="sxs-lookup"><span data-stu-id="b5120-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="b5120-109">Las etiquetas de cuarentena predeterminadas se asignan automáticamente para aplicar las capacidades históricas para los usuarios finales en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="b5120-110">O bien, puede crear y asignar etiquetas de cuarentena personalizadas para permitir o impedir que los usuarios finales realicen acciones específicas en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="b5120-111">Los permisos individuales se combinan en los siguientes grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="b5120-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="b5120-112">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="b5120-112">No access</span></span>
- <span data-ttu-id="b5120-113">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="b5120-113">Limited access</span></span>
- <span data-ttu-id="b5120-114">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="b5120-114">Full access</span></span>

<span data-ttu-id="b5120-115">Los permisos individuales disponibles y lo que se incluye o no en los grupos de permisos preestablecidos se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5120-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="b5120-116">Permiso</span><span class="sxs-lookup"><span data-stu-id="b5120-116">Permission</span></span>|<span data-ttu-id="b5120-117">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="b5120-117">No access</span></span>|<span data-ttu-id="b5120-118">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="b5120-118">Limited access</span></span>|<span data-ttu-id="b5120-119">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="b5120-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="b5120-120">**Permitir remitente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="b5120-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="b5120-122">**Bloquear remitente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="b5120-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="b5120-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="b5120-125">**Delete** (_PermissionToDelete_)</span></span>||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="b5120-128">**Preview** (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="b5120-128">**Preview** (_PermissionToPreview_)</span></span>||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="b5120-131">**Permitir que los destinatarios liberen un mensaje de cuarentena** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="b5120-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="b5120-133">**Permitir que los destinatarios soliciten que un mensaje se libera de la cuarentena** (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="b5120-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Marca de verificación](../../media/checkmark.png)||
|

<span data-ttu-id="b5120-135">Si no le gustan los permisos predeterminados en los grupos de permisos preestablecidos, puede usar permisos personalizados al crear o modificar etiquetas de cuarentena personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b5120-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="b5120-136">Para obtener más información acerca de lo que hace cada permiso, vea la sección detalles del permiso de etiqueta [de](#quarantine-tag-permission-details) cuarentena más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5120-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="b5120-137">Puede crear y asignar etiquetas de cuarentena en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones de Exchange Online; EOP PowerShell independiente en organizaciones EOP sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="b5120-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5120-138">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="b5120-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5120-139">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b5120-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b5120-140">Para ir directamente a la página **Etiquetas de cuarentena,** abra <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="b5120-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="b5120-141">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5120-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b5120-142">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b5120-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b5120-143">Para ver, crear, modificar o quitar etiquetas de cuarentena, debe ser miembro de los **roles** de administrador de seguridad o administración de la organización en el Centro de [seguridad & cumplimiento.](permissions-in-the-security-and-compliance-center.md) </span><span class="sxs-lookup"><span data-stu-id="b5120-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="b5120-144">Paso 1: Crear etiquetas de cuarentena en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5120-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b5120-145">En el Centro de & cumplimiento, vaya a Directiva de administración **de** amenazas y, a continuación, \>  seleccione **Etiquetas de cuarentena.**</span><span class="sxs-lookup"><span data-stu-id="b5120-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="b5120-146">En la **página Etiquetas de** cuarentena, seleccione **Agregar etiqueta personalizada.**</span><span class="sxs-lookup"><span data-stu-id="b5120-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="b5120-147">Se **abrirá el Asistente para nueva** etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b5120-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="b5120-148">En la **página Nombre de** etiqueta, escriba un nombre breve pero único en el campo Nombre **de** etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b5120-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="b5120-149">Deberá identificar y seleccionar la etiqueta por su nombre en los próximos pasos.</span><span class="sxs-lookup"><span data-stu-id="b5120-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="b5120-150">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5120-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b5120-151">En la **página Acceso a mensajes de** destinatario, seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b5120-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="b5120-152">**Sin acceso**</span><span class="sxs-lookup"><span data-stu-id="b5120-152">**No access**</span></span>
   - <span data-ttu-id="b5120-153">**Acceso limitado**</span><span class="sxs-lookup"><span data-stu-id="b5120-153">**Limited access**</span></span>
   - <span data-ttu-id="b5120-154">**Acceso completo**</span><span class="sxs-lookup"><span data-stu-id="b5120-154">**Full access**</span></span>

   <span data-ttu-id="b5120-155">Los permisos individuales que se incluyen en estos grupos de permisos se describen anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5120-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="b5120-156">Para especificar permisos personalizados, seleccione **Establecer acceso específico (avanzado)** y configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b5120-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="b5120-157">**Seleccione la preferencia de acción de lanzamiento:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b5120-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="b5120-158">**Sin acción de lanzamiento:** este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b5120-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="b5120-159">**Permitir que los destinatarios liberen un mensaje de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="b5120-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="b5120-160">**Permitir que los destinatarios soliciten que un mensaje se libera de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="b5120-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="b5120-161">**Seleccione acciones adicionales que los destinatarios pueden realizar en** mensajes en cuarentena: seleccione algunos, todos o ninguno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b5120-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="b5120-162">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="b5120-162">**Delete**</span></span>
       - <span data-ttu-id="b5120-163">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="b5120-163">**Preview**</span></span>
       - <span data-ttu-id="b5120-164">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-164">**Allow sender**</span></span>
       - <span data-ttu-id="b5120-165">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-165">**Block sender**</span></span>

   <span data-ttu-id="b5120-166">Estos permisos y su efecto en los mensajes en cuarentena y [](#quarantine-tag-permission-details) en las notificaciones de correo no deseado para el usuario final se describen en la sección detalles de permisos de etiqueta de cuarentena más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5120-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="b5120-167">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b5120-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b5120-168">En la **página Resumen** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="b5120-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="b5120-169">Puedes hacer clic **en Editar** en cada opción para modificarla.</span><span class="sxs-lookup"><span data-stu-id="b5120-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b5120-170">Cuando haya terminado, haga clic en **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="b5120-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="b5120-171">Haga **clic en Listo** en la página de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="b5120-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="b5120-172">Ahora está listo para asignar la etiqueta de cuarentena a una característica de cuarentena, como se describe en la [sección Paso 2.](#step-2-assign-a-quarantine-tag-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="b5120-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="b5120-173">Crear etiquetas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5120-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="b5120-174">Si prefiere usar PowerShell para crear etiquetas en cuarentena, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use el cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="b5120-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="b5120-175">Tiene dos métodos diferentes entre los que elegir:</span><span class="sxs-lookup"><span data-stu-id="b5120-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="b5120-176">Use el _parámetro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="b5120-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="b5120-177">Use el _parámetro EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="b5120-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="b5120-178">Estos métodos se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="b5120-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="b5120-179">Usar el parámetro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="b5120-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="b5120-180">Para crear una etiqueta de cuarentena mediante el _parámetro EndUserQuarantinePermissionsValue,_ use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b5120-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="b5120-181">El _parámetro EndUserQuarantinePermissionsValue_ usa un valor decimal que se convierte a partir de un valor binario.</span><span class="sxs-lookup"><span data-stu-id="b5120-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="b5120-182">El valor binario corresponde a los permisos de cuarentena de usuario final disponibles en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="b5120-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="b5120-183">Para cada permiso, el valor 1 es igual a True y el valor 0 es False.</span><span class="sxs-lookup"><span data-stu-id="b5120-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="b5120-184">El orden y los valores necesarios para cada permiso individual en grupos de permisos preestablecidos se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5120-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="b5120-185">Permiso</span><span class="sxs-lookup"><span data-stu-id="b5120-185">Permission</span></span>|<span data-ttu-id="b5120-186">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="b5120-186">No access</span></span>|<span data-ttu-id="b5120-187">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="b5120-187">Limited access</span></span>|<span data-ttu-id="b5120-188">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="b5120-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="b5120-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="b5120-189">PermissionToAllowSender</span></span>|<span data-ttu-id="b5120-190">0</span><span class="sxs-lookup"><span data-stu-id="b5120-190">0</span></span>|<span data-ttu-id="b5120-191">0</span><span class="sxs-lookup"><span data-stu-id="b5120-191">0</span></span>|<span data-ttu-id="b5120-192">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-192">1</span></span>|
|<span data-ttu-id="b5120-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="b5120-193">PermissionToBlockSender</span></span>|<span data-ttu-id="b5120-194">0</span><span class="sxs-lookup"><span data-stu-id="b5120-194">0</span></span>|<span data-ttu-id="b5120-195">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-195">1</span></span>|<span data-ttu-id="b5120-196">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-196">1</span></span>|
|<span data-ttu-id="b5120-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="b5120-197">PermissionToDelete</span></span>|<span data-ttu-id="b5120-198">0</span><span class="sxs-lookup"><span data-stu-id="b5120-198">0</span></span>|<span data-ttu-id="b5120-199">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-199">1</span></span>|<span data-ttu-id="b5120-200">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-200">1</span></span>|
|<span data-ttu-id="b5120-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5120-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="b5120-202">0</span><span class="sxs-lookup"><span data-stu-id="b5120-202">0</span></span>|<span data-ttu-id="b5120-203">0</span><span class="sxs-lookup"><span data-stu-id="b5120-203">0</span></span>|<span data-ttu-id="b5120-204">0</span><span class="sxs-lookup"><span data-stu-id="b5120-204">0</span></span>|
|<span data-ttu-id="b5120-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="b5120-205">PermissionToPreview</span></span>|<span data-ttu-id="b5120-206">0</span><span class="sxs-lookup"><span data-stu-id="b5120-206">0</span></span>|<span data-ttu-id="b5120-207">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-207">1</span></span>|<span data-ttu-id="b5120-208">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-208">1</span></span>|
|<span data-ttu-id="b5120-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5120-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="b5120-210">0</span><span class="sxs-lookup"><span data-stu-id="b5120-210">0</span></span>|<span data-ttu-id="b5120-211">0</span><span class="sxs-lookup"><span data-stu-id="b5120-211">0</span></span>|<span data-ttu-id="b5120-212">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-212">1</span></span>|
|<span data-ttu-id="b5120-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5120-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="b5120-214">0</span><span class="sxs-lookup"><span data-stu-id="b5120-214">0</span></span>|<span data-ttu-id="b5120-215">1 </span><span class="sxs-lookup"><span data-stu-id="b5120-215">1</span></span>|<span data-ttu-id="b5120-216">0</span><span class="sxs-lookup"><span data-stu-id="b5120-216">0</span></span>|
|<span data-ttu-id="b5120-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5120-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="b5120-218">0</span><span class="sxs-lookup"><span data-stu-id="b5120-218">0</span></span>|<span data-ttu-id="b5120-219">0</span><span class="sxs-lookup"><span data-stu-id="b5120-219">0</span></span>|<span data-ttu-id="b5120-220">0</span><span class="sxs-lookup"><span data-stu-id="b5120-220">0</span></span>|
|<span data-ttu-id="b5120-221">Valor binario</span><span class="sxs-lookup"><span data-stu-id="b5120-221">Binary value</span></span>|<span data-ttu-id="b5120-222">00000000</span><span class="sxs-lookup"><span data-stu-id="b5120-222">00000000</span></span>|<span data-ttu-id="b5120-223">01101010</span><span class="sxs-lookup"><span data-stu-id="b5120-223">01101010</span></span>|<span data-ttu-id="b5120-224">11101100</span><span class="sxs-lookup"><span data-stu-id="b5120-224">11101100</span></span>|
|<span data-ttu-id="b5120-225">Valor decimal que se debe usar</span><span class="sxs-lookup"><span data-stu-id="b5120-225">Decimal value to use</span></span>|<span data-ttu-id="b5120-226">0</span><span class="sxs-lookup"><span data-stu-id="b5120-226">0</span></span>|<span data-ttu-id="b5120-227">106</span><span class="sxs-lookup"><span data-stu-id="b5120-227">106</span></span>|<span data-ttu-id="b5120-228">236</span><span class="sxs-lookup"><span data-stu-id="b5120-228">236</span></span>|

<span data-ttu-id="b5120-229"><sup>\*</sup> Actualmente, este valor siempre es 0.</span><span class="sxs-lookup"><span data-stu-id="b5120-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="b5120-230">Para PermissionToViewHeader, el valor 0  no oculta el botón Ver encabezado del mensaje en los detalles del mensaje en cuarentena (el botón siempre está disponible).</span><span class="sxs-lookup"><span data-stu-id="b5120-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="b5120-231"><sup>\*\*</sup> No establezca ambos valores en 1.</span><span class="sxs-lookup"><span data-stu-id="b5120-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="b5120-232">Establezca uno en 1 y el otro en 0, o establezca ambos en 0.</span><span class="sxs-lookup"><span data-stu-id="b5120-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="b5120-233">En este ejemplo se crea un nuevo nombre de etiqueta de cuarentena NoAccess que asigna los permisos Sin acceso, tal como se describe en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="b5120-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="b5120-234">Para los permisos de acceso limitado, use el valor 106.</span><span class="sxs-lookup"><span data-stu-id="b5120-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="b5120-235">Para los permisos de acceso completo, use el valor 236.</span><span class="sxs-lookup"><span data-stu-id="b5120-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="b5120-236">Para los permisos personalizados, use la tabla anterior para obtener el valor binario que corresponde a los permisos que desea.</span><span class="sxs-lookup"><span data-stu-id="b5120-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="b5120-237">Convierta el valor binario en un valor decimal y use el valor decimal para el parámetro _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="b5120-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="b5120-238">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="b5120-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="b5120-239">Usar el parámetro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="b5120-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="b5120-240">Para crear una etiqueta de cuarentena con el parámetro _EndUserQuarantinePermissionsValue,_ siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b5120-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="b5120-241">A.</span><span class="sxs-lookup"><span data-stu-id="b5120-241">A.</span></span> <span data-ttu-id="b5120-242">Almacene un objeto de permisos de cuarentena en una variable mediante el cmdlet **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="b5120-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="b5120-243">B.</span><span class="sxs-lookup"><span data-stu-id="b5120-243">B.</span></span> <span data-ttu-id="b5120-244">Use la variable como _el valor EndUserQuarantinePermissions_ en el **comando New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="b5120-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="b5120-245">Paso A: Almacenar un objeto de permisos de cuarentena en una variable</span><span class="sxs-lookup"><span data-stu-id="b5120-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="b5120-246">Utilice la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5120-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="b5120-247">El valor predeterminado para los parámetros no usados es , por lo que solo necesita usar los parámetros donde desea establecer `$false` el valor en `$true` .</span><span class="sxs-lookup"><span data-stu-id="b5120-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="b5120-248">En los ejemplos siguientes se muestra cómo crear objetos de permisos que corresponden a los grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="b5120-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="b5120-249">**Sin acceso:**</span><span class="sxs-lookup"><span data-stu-id="b5120-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="b5120-250">**Acceso limitado:**</span><span class="sxs-lookup"><span data-stu-id="b5120-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="b5120-251">**Acceso completo:**</span><span class="sxs-lookup"><span data-stu-id="b5120-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="b5120-252">Para ver los valores que ha establecido, ejecute el nombre de la variable como un comando (por ejemplo, ejecute el `$NoAccess` comando).</span><span class="sxs-lookup"><span data-stu-id="b5120-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="b5120-253">Para los permisos personalizados, no establezca los parámetros _PermissionToRelease_ y _PermissionToRequestRelease en_ `$true` .</span><span class="sxs-lookup"><span data-stu-id="b5120-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="b5120-254">Establezca uno en `$true` y deje el otro como , o deje ambos como `$false` `$false` .</span><span class="sxs-lookup"><span data-stu-id="b5120-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="b5120-255">También puede modificar una variable de objeto de permisos existente después de crearla, pero antes de usarla con el cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="b5120-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="b5120-256">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) y [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="b5120-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="b5120-257">Paso B: Usar la variable en el New-QuarantineTag comando</span><span class="sxs-lookup"><span data-stu-id="b5120-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="b5120-258">Después de crear y almacenar el objeto permissions en una variable, use la variable para el valor del parámetro _EndUserQuarantinePermission_ en el siguiente comando **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="b5120-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="b5120-259">En este ejemplo se crea una nueva etiqueta de cuarentena denominada LimitedAccess mediante el objeto de permisos que se describió y `$LimitedAccess` creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="b5120-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="b5120-260">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="b5120-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="b5120-261">Paso 2: Asignar una etiqueta de cuarentena a las características compatibles</span><span class="sxs-lookup"><span data-stu-id="b5120-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="b5120-262">En _las características_ de protección admitidas que ponen en cuarentena mensajes o archivos (automáticamente o como una acción configurable), puede asignar una etiqueta de cuarentena a las acciones de cuarentena disponibles.</span><span class="sxs-lookup"><span data-stu-id="b5120-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="b5120-263">En la tabla siguiente se describen las características que ponen en cuarentena los mensajes y la disponibilidad de las etiquetas de cuarentena:</span><span class="sxs-lookup"><span data-stu-id="b5120-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="b5120-264">Característica</span><span class="sxs-lookup"><span data-stu-id="b5120-264">Feature</span></span>|<span data-ttu-id="b5120-265">¿Se admiten etiquetas de cuarentena?</span><span class="sxs-lookup"><span data-stu-id="b5120-265">Quarantine tags supported?</span></span>|<span data-ttu-id="b5120-266">Etiquetas de cuarentena predeterminadas usadas</span><span class="sxs-lookup"><span data-stu-id="b5120-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="b5120-267">[Directivas contra correo no deseado:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b5120-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="b5120-268">**Correo no** deseado (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="b5120-269">**Correo no deseado de** confianza alta (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="b5120-270">**Correo electrónico de suplantación** de identidad _(PhishSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="b5120-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="b5120-271">**Correo electrónico de suplantación de** identidad de confianza alta (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="b5120-272">**Correo electrónico masivo** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="b5120-273">Sí</span><span class="sxs-lookup"><span data-stu-id="b5120-273">Yes</span></span>|<ul><li><span data-ttu-id="b5120-274">DefaultSpamTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="b5120-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="b5120-275">DefaultHighConfSpamTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="b5120-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="b5120-276">DefaultPhishTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="b5120-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="b5120-277">DefaultHighConfPhishTag (sin acceso)</span><span class="sxs-lookup"><span data-stu-id="b5120-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="b5120-278">DefaultBulkTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="b5120-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="b5120-279">Directivas contra la suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="b5120-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="b5120-280">[Protección de inteligencia de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de documentos (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="b5120-281">[Protección de suplantación:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b5120-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="b5120-282">**Si un usuario suplantado envía correo** electrónico (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="b5120-283">**Si un dominio suplantado envía correo** electrónico (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="b5120-284">**Inteligencia de buzones** \> **Si un usuario suplantado envía correo** electrónico (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="b5120-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="b5120-285">No</span><span class="sxs-lookup"><span data-stu-id="b5120-285">No</span></span>|<span data-ttu-id="b5120-286">n/a</span><span class="sxs-lookup"><span data-stu-id="b5120-286">n/a</span></span>|
|<span data-ttu-id="b5120-287">[Directivas antimalware:](configure-anti-malware-policies.md)todos los mensajes detectados siempre se ponen en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="b5120-288">No</span><span class="sxs-lookup"><span data-stu-id="b5120-288">No</span></span>|<span data-ttu-id="b5120-289">n/a</span><span class="sxs-lookup"><span data-stu-id="b5120-289">n/a</span></span>|
|[<span data-ttu-id="b5120-290">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b5120-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="b5120-291">No</span><span class="sxs-lookup"><span data-stu-id="b5120-291">No</span></span>|<span data-ttu-id="b5120-292">n/a</span><span class="sxs-lookup"><span data-stu-id="b5120-292">n/a</span></span>|
|<span data-ttu-id="b5120-293">[Reglas de flujo de](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) correo (también conocidas como reglas de transporte) con la acción: Entregar el mensaje a la **cuarentena** hospedada (_Cuarentena_).</span><span class="sxs-lookup"><span data-stu-id="b5120-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="b5120-294">No</span><span class="sxs-lookup"><span data-stu-id="b5120-294">No</span></span>|<span data-ttu-id="b5120-295">n/a</span><span class="sxs-lookup"><span data-stu-id="b5120-295">n/a</span></span>|
|

<span data-ttu-id="b5120-296"><sup>\*</sup> La configuración de protección de suplantación solo está disponible en las directivas contra suplantación de identidad en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5120-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="b5120-297">Si está satisfecho con los permisos de usuario final proporcionados por las etiquetas de cuarentena predeterminadas, no necesita hacer nada.</span><span class="sxs-lookup"><span data-stu-id="b5120-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="b5120-298">Si desea personalizar las capacidades del usuario final (botones disponibles) en las notificaciones de correo no deseado para el usuario final o en los detalles de los mensajes en cuarentena, puede asignar una etiqueta de cuarentena personalizada.</span><span class="sxs-lookup"><span data-stu-id="b5120-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="b5120-299">Asignar etiquetas de cuarentena en directivas contra correo no deseado en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5120-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="b5120-300">Las instrucciones completas para crear y modificar directivas contra correo no deseado se describen en Configurar directivas contra correo no deseado [en EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b5120-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="b5120-301">En el Centro de & cumplimiento,  vaya a Directiva de administración de amenazas y, a \>  \> continuación, seleccione **Correo no deseado.**</span><span class="sxs-lookup"><span data-stu-id="b5120-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="b5120-302">O bien, abra <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="b5120-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="b5120-303">Busque y seleccione una directiva contra correo no deseado existente para editarla o cree una nueva directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b5120-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="b5120-304">En el control desplegable de detalles de la directiva, expanda la sección Correo no deseado **y acciones masivas.**</span><span class="sxs-lookup"><span data-stu-id="b5120-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="b5120-305">Si ha seleccionado  el mensaje de cuarentena para la acción  de un veredicto de filtrado de correo no deseado disponible, el cuadro de etiqueta Aplicar directiva de cuarentena estará disponible para que seleccione la etiqueta de cuarentena para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="b5120-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="b5120-306">**Nota:** Al crear una nueva directiva, se usa un valor de etiqueta de cuarentena en blanco para un veredicto de filtrado de correo no deseado que indica la etiqueta de cuarentena predeterminada para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="b5120-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="b5120-307">Cuando más adelante edite la directiva, los valores en blanco se reemplazan por los nombres de etiqueta de cuarentena predeterminados reales, como se describe en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="b5120-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![Selecciones de etiquetas de cuarentena en una directiva contra correo no deseado](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="b5120-309">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b5120-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="b5120-310">Asignar etiquetas de cuarentena en directivas contra correo no deseado en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5120-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="b5120-311">Si prefiere usar PowerShell para asignar etiquetas de cuarentena en directivas contra correo no deseado, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="b5120-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="b5120-312">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="b5120-312">**Notes**:</span></span>

- <span data-ttu-id="b5120-313">El valor predeterminado para el parámetro _HighConfidencePhishAction_ es Quarantine, por lo que no es necesario establecer la acción cuarentena para las detecciones de suplantación de identidad de confianza alta en las nuevas directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="b5120-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="b5120-314">Para todos los demás veredictos de filtrado de correo no deseado en directivas contra correo no deseado nuevas o existentes, la etiqueta de cuarentena solo es efectiva si el valor de acción es Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="b5120-315">Para ver los valores de acción en las directivas contra correo no deseado existentes, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b5120-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="b5120-316">Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Standard y Strict, vea configuración de directiva contra [correo no deseado de EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b5120-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="b5120-317">Un veredicto de filtrado de correo no deseado sin un parámetro de etiqueta de cuarentena correspondiente significa que se usa la etiqueta de [cuarentena](#step-2-assign-a-quarantine-tag-to-supported-features) predeterminada para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="b5120-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="b5120-318">Solo necesita reemplazar una etiqueta de cuarentena predeterminada por una etiqueta de cuarentena personalizada si desea cambiar las capacidades predeterminadas del usuario final en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="b5120-319">Una nueva directiva contra correo no deseado en PowerShell requiere una directiva de filtro de correo no deseado (configuración) con el cmdlet **New-HostedContentFilterPolicy** y una nueva regla de filtro de correo no deseado (filtros de destinatarios) mediante el cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="b5120-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="b5120-320">Para obtener instrucciones, [vea Usar PowerShell para crear directivas contra correo no deseado.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="b5120-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="b5120-321">En este ejemplo se crea una nueva directiva de filtro de correo no deseado denominada Research Department con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b5120-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="b5120-322">La acción para todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="b5120-323">La etiqueta de cuarentena personalizada denominada NoAccess que asigna permisos **sin** acceso reemplaza a las etiquetas de cuarentena predeterminadas que aún **no** asignan permisos de acceso de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b5120-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="b5120-324">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b5120-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="b5120-325">En este ejemplo se modifica la directiva de filtro de correo no deseado existente denominada Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b5120-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="b5120-326">La acción para el veredicto de cuarentena de correo no deseado se establece en Cuarentena y se asigna la etiqueta de cuarentena personalizada denominada NoAccess.</span><span class="sxs-lookup"><span data-stu-id="b5120-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="b5120-327">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b5120-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="b5120-328">Configurar las opciones de notificación de cuarentena global en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5120-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="b5120-329">La configuración global de las etiquetas de cuarentena permite personalizar las notificaciones de correo no deseado para el usuario final que se envían a los destinatarios de los mensajes que se han puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="b5120-330">Para obtener más información acerca de estas notificaciones, consulte Notificaciones de correo no [deseado para el usuario final.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b5120-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="b5120-331">En el Centro de & cumplimiento, vaya a Directiva de administración **de** amenazas y, a continuación, \>  seleccione **Etiquetas de cuarentena.**</span><span class="sxs-lookup"><span data-stu-id="b5120-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="b5120-332">En la **página Etiquetas de** cuarentena, seleccione **Configuración global.**</span><span class="sxs-lookup"><span data-stu-id="b5120-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="b5120-333">En el **control desplegable de configuración de** notificación de cuarentena que se abre, configure algunas o todas las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5120-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="b5120-334">**Use el logotipo de mi** compañía: seleccione esta opción para reemplazar el logotipo predeterminado de Microsoft que se usa en la parte superior de las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="b5120-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="b5120-335">Antes de hacerlo, debe seguir las instrucciones de Personalizar el tema de [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) para que su organización cargue el logotipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="b5120-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="b5120-336">La siguiente captura de pantalla muestra un logotipo personalizado en una notificación de correo no deseado para el usuario final:</span><span class="sxs-lookup"><span data-stu-id="b5120-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Un logotipo personalizado en una notificación de correo no deseado para el usuario final](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="b5120-338">**Elegir idioma:** las notificaciones de correo no deseado para el usuario final ya están localizadas en función de la configuración de idioma del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b5120-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="b5120-339">Puede especificar texto personalizado en diferentes idiomas para los valores **de nombre para mostrar y** aviso de declinación **de** responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="b5120-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="b5120-340">Seleccione al menos un idioma en el primer cuadro de idioma y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b5120-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="b5120-341">Puede seleccionar varios idiomas haciendo clic en **Agregar** después de cada uno.</span><span class="sxs-lookup"><span data-stu-id="b5120-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="b5120-342">Un cuadro de idioma de sección muestra todos los idiomas que has seleccionado:</span><span class="sxs-lookup"><span data-stu-id="b5120-342">A section language box shows all of the languages that you've selected:</span></span>

     ![Idiomas seleccionados en el segundo cuadro de idioma en la configuración de notificación de cuarentena global de etiquetas de cuarentena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="b5120-344">**Nombre para** mostrar: personalizar el nombre para mostrar del remitente que se usa en las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="b5120-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="b5120-345">Para cada idioma que haya agregado, seleccione el idioma en el segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro Nombre para **mostrar.**</span><span class="sxs-lookup"><span data-stu-id="b5120-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="b5120-346">La siguiente captura de pantalla muestra el nombre para mostrar personalizado en una notificación de correo no deseado para el usuario final:</span><span class="sxs-lookup"><span data-stu-id="b5120-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Un nombre para mostrar del remitente personalizado en una notificación de correo no deseado para el usuario final](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="b5120-348">**Aviso** de declinación de responsabilidades: agregue un aviso de declinación de responsabilidades personalizado en la parte inferior de las notificaciones de correo no deseado para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="b5120-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="b5120-349">El texto localizado, **un aviso de declinación de** responsabilidades de su organización: siempre se incluye primero, seguido del texto que especifique.</span><span class="sxs-lookup"><span data-stu-id="b5120-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="b5120-350">Para cada idioma que haya agregado, seleccione el idioma en el segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro Aviso de declinación **de** responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="b5120-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="b5120-351">La siguiente captura de pantalla muestra el aviso de declinación de responsabilidades personalizado en una notificación de correo no deseado para el usuario final:</span><span class="sxs-lookup"><span data-stu-id="b5120-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Un aviso de declinación de responsabilidades personalizado en la parte inferior de una notificación de correo no deseado para el usuario final](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="b5120-353">Ver etiquetas de cuarentena en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5120-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b5120-354">En el Centro de & cumplimiento, vaya a Directiva de administración **de** amenazas y, a continuación, \>  seleccione **Etiquetas de cuarentena.**</span><span class="sxs-lookup"><span data-stu-id="b5120-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="b5120-355">Para ver la configuración de las etiquetas de cuarentena integradas o personalizadas, seleccione la etiqueta de cuarentena de la lista (no active la casilla).</span><span class="sxs-lookup"><span data-stu-id="b5120-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="b5120-356">Para ver la configuración global, seleccione **Configuración global**</span><span class="sxs-lookup"><span data-stu-id="b5120-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="b5120-357">Ver etiquetas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5120-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="b5120-358">Si prefiere usar PowerShell para ver etiquetas en cuarentena, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b5120-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="b5120-359">Para ver una lista resumida de todas las etiquetas integradas o personalizadas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b5120-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="b5120-360">Para ver la configuración de las etiquetas de cuarentena integradas o personalizadas, reemplace por el nombre de la etiqueta de cuarentena y \<TagName\> ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b5120-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="b5120-361">Para ver la configuración global, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b5120-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="b5120-362">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b5120-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="b5120-363">Quitar etiquetas de cuarentena en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b5120-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="b5120-364">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="b5120-364">**Notes**:</span></span>

- <span data-ttu-id="b5120-365">No puede quitar etiquetas de cuarentena integradas.</span><span class="sxs-lookup"><span data-stu-id="b5120-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="b5120-366">Antes de quitar una etiqueta de cuarentena personalizada, compruebe que no se esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="b5120-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="b5120-367">Por ejemplo, ejecute el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b5120-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="b5120-368">Si se usa la etiqueta de cuarentena, [reemplace la etiqueta](#step-2-assign-a-quarantine-tag-to-supported-features) de cuarentena asignada antes de quitarla.</span><span class="sxs-lookup"><span data-stu-id="b5120-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="b5120-369">En el Centro de & cumplimiento, vaya a Directiva de administración **de** amenazas y, a continuación, \>  seleccione **Etiquetas de cuarentena.**</span><span class="sxs-lookup"><span data-stu-id="b5120-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="b5120-370">En la **página Etiquetas de** cuarentena, seleccione la etiqueta de cuarentena personalizada que desea quitar y haga clic en **Eliminar etiqueta.**</span><span class="sxs-lookup"><span data-stu-id="b5120-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="b5120-371">Haga **clic en Quitar** etiqueta en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="b5120-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="b5120-372">Quitar etiquetas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5120-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="b5120-373">Si prefiere usar PowerShell para quitar una etiqueta de cuarentena personalizada, reemplace por el nombre de la etiqueta de cuarentena y \<TagName\> ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b5120-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="b5120-374">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="b5120-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="b5120-375">Detalles del permiso de etiqueta de cuarentena</span><span class="sxs-lookup"><span data-stu-id="b5120-375">Quarantine tag permission details</span></span>

<span data-ttu-id="b5120-376">En las secciones siguientes se describen los efectos de los grupos de permisos preestablecidos y los permisos individuales en los detalles de los mensajes en cuarentena y en las notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="b5120-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="b5120-377">Grupos de permisos preestablecidos</span><span class="sxs-lookup"><span data-stu-id="b5120-377">Preset permissions groups</span></span>

<span data-ttu-id="b5120-378">Los permisos individuales que se incluyen en los grupos de permisos preestablecidos se enumeran en la tabla al principio de este artículo.</span><span class="sxs-lookup"><span data-stu-id="b5120-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="b5120-379">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="b5120-379">No access</span></span>

<span data-ttu-id="b5120-380">Si la etiqueta de cuarentena asigna los **permisos Sin** acceso (sin permisos), los usuarios aún obtienen algunas funcionalidades de línea base:</span><span class="sxs-lookup"><span data-stu-id="b5120-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="b5120-381">**Detalles del mensaje en cuarentena:** el **botón Ver encabezado del** mensaje siempre está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Botones disponibles en los detalles del mensaje en cuarentena si la etiqueta de cuarentena proporciona al usuario permisos sin acceso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="b5120-383">**Notificaciones de correo no deseado para el** usuario final: el botón Revisar que lleva al usuario al mensaje en cuarentena siempre está disponible. </span><span class="sxs-lookup"><span data-stu-id="b5120-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Botones disponibles en la notificación de correo no deseado para el usuario final si la etiqueta de cuarentena concede al usuario permisos sin acceso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="b5120-385">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="b5120-385">Limited access</span></span>

<span data-ttu-id="b5120-386">Si la etiqueta de cuarentena asigna los permisos **de acceso** limitado, los usuarios obtienen las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="b5120-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="b5120-387">**Detalles del mensaje en cuarentena:** están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="b5120-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="b5120-388">**Solicitud de lanzamiento**</span><span class="sxs-lookup"><span data-stu-id="b5120-388">**Request release**</span></span>
  - <span data-ttu-id="b5120-389">**Ver encabezado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="b5120-389">**View message header**</span></span>
  - <span data-ttu-id="b5120-390">**Vista previa del mensaje**</span><span class="sxs-lookup"><span data-stu-id="b5120-390">**Preview message**</span></span>
  - <span data-ttu-id="b5120-391">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-391">**Block sender**</span></span>
  - <span data-ttu-id="b5120-392">**Quitar de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="b5120-392">**Remove from quarantine**</span></span>

  ![Botones disponibles en los detalles del mensaje en cuarentena si la etiqueta de cuarentena concede al usuario permisos de acceso limitado](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="b5120-394">**Notificaciones de correo no deseado para el usuario** final: están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="b5120-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="b5120-395">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-395">**Block sender**</span></span>
  - <span data-ttu-id="b5120-396">**Revisar**</span><span class="sxs-lookup"><span data-stu-id="b5120-396">**Review**</span></span>

  ![Botones disponibles en la notificación de correo no deseado para el usuario final si la etiqueta de cuarentena concede al usuario permisos de acceso limitado](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="b5120-398">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="b5120-398">Full access</span></span>

<span data-ttu-id="b5120-399">Si la etiqueta de cuarentena asigna los permisos de **acceso** completo (todos los permisos disponibles), los usuarios obtienen las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="b5120-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="b5120-400">**Detalles del mensaje en cuarentena:** están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="b5120-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="b5120-401">**Mensaje de versión**</span><span class="sxs-lookup"><span data-stu-id="b5120-401">**Release message**</span></span>
  - <span data-ttu-id="b5120-402">**Ver encabezado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="b5120-402">**View message header**</span></span>
  - <span data-ttu-id="b5120-403">**Vista previa del mensaje**</span><span class="sxs-lookup"><span data-stu-id="b5120-403">**Preview message**</span></span>
  - <span data-ttu-id="b5120-404">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-404">**Block sender**</span></span>
  - <span data-ttu-id="b5120-405">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-405">**Allow sender**</span></span>
  - <span data-ttu-id="b5120-406">**Quitar de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="b5120-406">**Remove from quarantine**</span></span>

  ![Botones disponibles en los detalles del mensaje en cuarentena si la etiqueta de cuarentena concede al usuario permisos de acceso total](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="b5120-408">**Notificaciones de correo no deseado para el usuario** final: están disponibles los siguientes botones:</span><span class="sxs-lookup"><span data-stu-id="b5120-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="b5120-409">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="b5120-409">**Block sender**</span></span>
  - <span data-ttu-id="b5120-410">**Versión**</span><span class="sxs-lookup"><span data-stu-id="b5120-410">**Release**</span></span>
  - <span data-ttu-id="b5120-411">**Revisar**</span><span class="sxs-lookup"><span data-stu-id="b5120-411">**Review**</span></span>

  ![Botones disponibles en la notificación de correo no deseado para el usuario final si la etiqueta de cuarentena concede al usuario permisos de acceso completo](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="b5120-413">Permisos individuales</span><span class="sxs-lookup"><span data-stu-id="b5120-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="b5120-414">Recuerde que los usuarios siempre obtienen los botones descritos en la [sección Sin](#no-access) acceso.</span><span class="sxs-lookup"><span data-stu-id="b5120-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="b5120-415">Estos botones no se incluyen en las descripciones de permisos individuales.</span><span class="sxs-lookup"><span data-stu-id="b5120-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="b5120-416">Permitir permiso de remitente</span><span class="sxs-lookup"><span data-stu-id="b5120-416">Allow sender permission</span></span>

<span data-ttu-id="b5120-417">El **permiso** Permitir remitente (_PermissionToAllowSender_) controla el acceso al botón que permite a los usuarios agregar cómodamente el remitente del mensaje en cuarentena a su lista de remitentes seguros.</span><span class="sxs-lookup"><span data-stu-id="b5120-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="b5120-418">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="b5120-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b5120-419">**Permitir permiso de** remitente habilitado: **el botón** Permitir remitente está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="b5120-420">**Permitir permiso de** remitente deshabilitado: el **botón** Permitir remitente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="b5120-421">**Notificaciones de correo no deseado para el usuario** final: sin efecto.</span><span class="sxs-lookup"><span data-stu-id="b5120-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="b5120-422">Para obtener más información acerca de la lista de remitentes seguros, vea Impedir que los remitentes de confianza se bloqueen y [Usar Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)para configurar la colección de listas [seguras](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) en un buzón.</span><span class="sxs-lookup"><span data-stu-id="b5120-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="b5120-423">Bloquear el permiso del remitente</span><span class="sxs-lookup"><span data-stu-id="b5120-423">Block sender permission</span></span>

<span data-ttu-id="b5120-424">El **permiso bloquear remitente** (_PermissionToBlockSender_) controla el acceso al botón que permite a los usuarios agregar cómodamente el remitente del mensaje en cuarentena a su lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b5120-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="b5120-425">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="b5120-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b5120-426">**Bloquear permiso de** remitente habilitado: el botón Bloquear **remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="b5120-427">**Bloquear permiso de** remitente deshabilitado: **el botón** Bloquear remitente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="b5120-428">**Notificaciones de correo no deseado para el usuario final:**</span><span class="sxs-lookup"><span data-stu-id="b5120-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="b5120-429">**Bloquear permiso de** remitente deshabilitado: **el botón** Bloquear remitente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="b5120-430">**Permiso bloquear remitente** habilitado: el botón Bloquear **remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="b5120-431">Para obtener más información acerca de la lista de remitentes bloqueados, vea [Bloquear](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) mensajes de alguien y [Usar Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)para configurar la colección de listas seguras en un buzón.</span><span class="sxs-lookup"><span data-stu-id="b5120-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="b5120-432">Permiso de eliminación</span><span class="sxs-lookup"><span data-stu-id="b5120-432">Delete permission</span></span>

<span data-ttu-id="b5120-433">El **permiso** Eliminar (_PermissionToDelete_) controla la capacidad de los usuarios para eliminar sus mensajes (mensajes en los que el usuario es un destinatario) de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="b5120-434">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="b5120-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b5120-435">**Permiso** de eliminación habilitado: el botón Quitar **de cuarentena** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="b5120-436">**Permiso** de eliminación deshabilitado: el botón Quitar **de cuarentena** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="b5120-437">**Notificaciones de correo no deseado para el usuario** final: sin efecto.</span><span class="sxs-lookup"><span data-stu-id="b5120-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="b5120-438">Permiso de vista previa</span><span class="sxs-lookup"><span data-stu-id="b5120-438">Preview permission</span></span>

<span data-ttu-id="b5120-439">El **permiso de** vista previa (_PermissionToPreview_) controla la capacidad de los usuarios para obtener una vista previa de sus mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="b5120-440">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="b5120-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b5120-441">**Permiso de** vista previa habilitado: el **botón Vista previa del** mensaje está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="b5120-442">**Permiso de** vista previa deshabilitado: el **botón Vista previa del** mensaje no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="b5120-443">**Notificaciones de correo no deseado para el usuario** final: sin efecto.</span><span class="sxs-lookup"><span data-stu-id="b5120-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="b5120-444">Permitir que los destinatarios liberen un mensaje del permiso de cuarentena</span><span class="sxs-lookup"><span data-stu-id="b5120-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="b5120-445">El permiso Permitir a los destinatarios para liberar un mensaje de cuarentena _(PermissionToRelease)_ controla la capacidad de los usuarios de liberar sus mensajes en cuarentena directamente y sin la **aprobación** de un administrador.</span><span class="sxs-lookup"><span data-stu-id="b5120-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="b5120-446">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="b5120-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b5120-447">Permiso habilitado: el **botón Liberar mensaje** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="b5120-448">Permiso deshabilitado: el **botón Liberar mensaje** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="b5120-449">**Notificaciones de correo no deseado para el usuario final:**</span><span class="sxs-lookup"><span data-stu-id="b5120-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="b5120-450">Permiso habilitado: el **botón Liberar** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="b5120-451">Permiso deshabilitado: el **botón Liberar** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="b5120-452">Permitir que los destinatarios soliciten que se libera un mensaje del permiso de cuarentena</span><span class="sxs-lookup"><span data-stu-id="b5120-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="b5120-453">El **permiso Permitir que** los destinatarios soliciten que un mensaje se libere del permiso  de cuarentena _(PermissionToRequestRelease)_ controla la capacidad de los usuarios para solicitar la liberación de sus mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="b5120-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="b5120-454">El mensaje solo se libera después de que un administrador apruebe la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b5120-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="b5120-455">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="b5120-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="b5120-456">Permiso habilitado: el **botón Solicitar versión** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="b5120-457">Permiso deshabilitado: el **botón Solicitar versión** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="b5120-458">**Notificaciones de correo no deseado para el usuario** final: el **botón** Liberar no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b5120-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
