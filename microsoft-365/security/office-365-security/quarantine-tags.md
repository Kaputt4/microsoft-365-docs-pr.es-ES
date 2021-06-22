---
title: Directivas de cuarentena
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
description: Los administradores pueden aprender a usar directivas de cuarentena para controlar lo que los usuarios pueden hacer con sus mensajes en cuarentena.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055231"
---
# <a name="quarantine-policies"></a><span data-ttu-id="2afb8-103">Directivas de cuarentena</span><span class="sxs-lookup"><span data-stu-id="2afb8-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="2afb8-104">Las características que se describen en este artículo están actualmente en Versión preliminar, no están disponibles para todos y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="2afb8-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="2afb8-105">Las directivas de cuarentena (anteriormente conocidas como etiquetas de cuarentena) en Exchange Online Protection (EOP) permiten a los administradores controlar lo que los usuarios pueden hacer con sus mensajes en cuarentena en función de cómo el mensaje llegó a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="2afb8-106">Tradicionalmente, EOP ha permitido o impedido [](find-and-release-quarantined-messages-as-a-user.md) ciertos niveles de interactividad para los mensajes en cuarentena y en las notificaciones de [correo no deseado del usuario final.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="2afb8-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="2afb8-107">Por ejemplo, los usuarios pueden ver y liberar mensajes que fueron puestos en cuarentena por el filtrado contra correo no deseado como correo no deseado o masivo, pero no pueden ver ni liberar mensajes que se han puesto en cuarentena como phishing de elevada confianza (solo los administradores pueden hacerlo).</span><span class="sxs-lookup"><span data-stu-id="2afb8-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="2afb8-108">Para [las características](#step-2-assign-a-quarantine-policy-to-supported-features)de protección admitidas, las directivas de cuarentena especifican lo que los usuarios pueden hacer en los mensajes de notificación de correo no deseado del usuario final y en sus mensajes en cuarentena en cuarentena (mensajes en los que el usuario es un destinatario).</span><span class="sxs-lookup"><span data-stu-id="2afb8-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="2afb8-109">Las directivas de cuarentena predeterminadas se asignan automáticamente para aplicar las capacidades históricas de los usuarios en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="2afb8-110">O bien, puede crear y asignar directivas de cuarentena personalizadas para permitir o impedir que los usuarios finales realicen acciones específicas en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="2afb8-111">Los permisos individuales se combinan en los siguientes grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="2afb8-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="2afb8-112">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="2afb8-112">No access</span></span>
- <span data-ttu-id="2afb8-113">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="2afb8-113">Limited access</span></span>
- <span data-ttu-id="2afb8-114">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="2afb8-114">Full access</span></span>

<span data-ttu-id="2afb8-115">Los permisos individuales disponibles y lo que se incluye o no en los grupos de permisos preestablecidos se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="2afb8-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="2afb8-116">Permiso</span><span class="sxs-lookup"><span data-stu-id="2afb8-116">Permission</span></span>|<span data-ttu-id="2afb8-117">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="2afb8-117">No access</span></span>|<span data-ttu-id="2afb8-118">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="2afb8-118">Limited access</span></span>|<span data-ttu-id="2afb8-119">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="2afb8-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="2afb8-120">**Permitir remitente** (_PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="2afb8-122">**Bloquear remitente** (_PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="2afb8-125">**Delete** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-125">**Delete** (_PermissionToDelete_)</span></span>||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="2afb8-128">**Vista** previa (_PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-128">**Preview** (_PermissionToPreview_)</span></span>||![Marca de verificación](../../media/checkmark.png)|![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="2afb8-131">**Permitir que los destinatarios liberen un mensaje de cuarentena** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![Marca de verificación](../../media/checkmark.png)|
|<span data-ttu-id="2afb8-133">**Permitir que los destinatarios soliciten la puesta en** cuarentena de un mensaje (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![Marca de verificación](../../media/checkmark.png)||
|

<span data-ttu-id="2afb8-135">Si no le gustan los permisos predeterminados en los grupos de permisos preestablecidos, puede usar permisos personalizados al crear o modificar directivas de cuarentena personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2afb8-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="2afb8-136">Para obtener más información acerca de lo que hace cada permiso, vea la sección Detalles de permisos de directiva [de cuarentena](#quarantine-policy-permission-details) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2afb8-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="2afb8-137">Puede crear y asignar directivas de cuarentena en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones de correo de Exchange Online; PowerShell de EOP independiente en organizaciones de EOP sin Exchange Online buzones).</span><span class="sxs-lookup"><span data-stu-id="2afb8-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2afb8-138">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="2afb8-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2afb8-139">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="2afb8-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="2afb8-140">O bien, para ir directamente a la página **Directivas de** cuarentena, abra <https://security.microsoft.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="2afb8-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="2afb8-141">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2afb8-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2afb8-142">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="2afb8-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2afb8-143">Para ver, crear, modificar o quitar directivas de cuarentena,  debe  ser miembro de los roles Administración de la organización o Administrador de seguridad en el portal Microsoft 365 Defender seguridad.</span><span class="sxs-lookup"><span data-stu-id="2afb8-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="2afb8-144">Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="2afb8-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2afb8-145">Paso 1: Crear directivas de cuarentena en el portal de Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="2afb8-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="2afb8-146">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2afb8-147">En la **página Directiva de** cuarentena, haga clic en Agregar icono de directiva personalizada Agregar directiva ![ ](../../media/m365-cc-sc-create-icon.png) **personalizada.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="2afb8-148">Se **abrirá el Asistente para nueva** directiva.</span><span class="sxs-lookup"><span data-stu-id="2afb8-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="2afb8-149">En la **página Nombre de** directiva, escriba un nombre breve pero único en el cuadro Nombre **de** directiva.</span><span class="sxs-lookup"><span data-stu-id="2afb8-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="2afb8-150">Deberá identificar y seleccionar la directiva de cuarentena por su nombre en los próximos pasos.</span><span class="sxs-lookup"><span data-stu-id="2afb8-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="2afb8-151">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2afb8-152">En la **página Acceso a mensajes de** destinatario, seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2afb8-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="2afb8-153">**Sin acceso**</span><span class="sxs-lookup"><span data-stu-id="2afb8-153">**No access**</span></span>
   - <span data-ttu-id="2afb8-154">**Acceso limitado**</span><span class="sxs-lookup"><span data-stu-id="2afb8-154">**Limited access**</span></span>
   - <span data-ttu-id="2afb8-155">**Acceso completo**</span><span class="sxs-lookup"><span data-stu-id="2afb8-155">**Full access**</span></span>

   <span data-ttu-id="2afb8-156">Los permisos individuales que se incluyen en estos grupos de permisos se describen anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2afb8-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="2afb8-157">Para especificar permisos personalizados, seleccione **Establecer acceso específico (Avanzado)** y configure las siguientes opciones que aparecen:</span><span class="sxs-lookup"><span data-stu-id="2afb8-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="2afb8-158">**Seleccionar preferencia de acción de lanzamiento:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2afb8-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="2afb8-159">**Sin acción de lanzamiento:** este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2afb8-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="2afb8-160">**Permitir que los destinatarios liberen un mensaje de cuarentena**</span><span class="sxs-lookup"><span data-stu-id="2afb8-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="2afb8-161">**Permitir que los destinatarios soliciten un mensaje que se liberará de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="2afb8-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="2afb8-162">**Seleccionar acciones adicionales que los** destinatarios pueden realizar en mensajes en cuarentena: seleccione algunos, todos o ninguno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="2afb8-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="2afb8-163">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="2afb8-163">**Delete**</span></span>
       - <span data-ttu-id="2afb8-164">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="2afb8-164">**Preview**</span></span>
       - <span data-ttu-id="2afb8-165">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="2afb8-165">**Block sender**</span></span>

   <span data-ttu-id="2afb8-166">Estos permisos y su efecto en los mensajes en cuarentena y en las notificaciones de correo no deseado del usuario final se describen en la sección [Detalles](#quarantine-policy-permission-details) de permisos de directiva de cuarentena más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2afb8-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="2afb8-167">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2afb8-168">En la **página Revisar directiva** que aparece, revisa la configuración.</span><span class="sxs-lookup"><span data-stu-id="2afb8-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="2afb8-169">Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="2afb8-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="2afb8-170">También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.</span><span class="sxs-lookup"><span data-stu-id="2afb8-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="2afb8-171">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="2afb8-172">En la página de confirmación que aparece, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="2afb8-173">Ahora ya está listo para asignar la directiva de cuarentena a una característica de cuarentena, tal como se describe en la [sección Paso 2.](#step-2-assign-a-quarantine-policy-to-supported-features)</span><span class="sxs-lookup"><span data-stu-id="2afb8-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="2afb8-174">Crear directivas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="2afb8-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="2afb8-175">Si prefiere usar PowerShell para crear directivas de cuarentena, conéctese Exchange Online PowerShell o Exchange Online Protection PowerShell y use el cmdlet **New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="2afb8-176">Tiene dos métodos diferentes entre los que elegir:</span><span class="sxs-lookup"><span data-stu-id="2afb8-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="2afb8-177">Use el _parámetro EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="2afb8-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="2afb8-178">Use el _parámetro EndUserQuarantinePermissions._</span><span class="sxs-lookup"><span data-stu-id="2afb8-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="2afb8-179">Estos métodos se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="2afb8-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="2afb8-180">Usar el parámetro EndUserQuarantinePermissionsValue</span><span class="sxs-lookup"><span data-stu-id="2afb8-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="2afb8-181">Para crear una directiva de cuarentena mediante el _parámetro EndUserQuarantinePermissionsValue,_ use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="2afb8-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="2afb8-182">El _parámetro EndUserQuarantinePermissionsValue_ usa un valor decimal que se convierte a partir de un valor binario.</span><span class="sxs-lookup"><span data-stu-id="2afb8-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="2afb8-183">El valor binario corresponde a los permisos de cuarentena de usuario final disponibles en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="2afb8-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="2afb8-184">Para cada permiso, el valor 1 es True y el valor 0 es False.</span><span class="sxs-lookup"><span data-stu-id="2afb8-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="2afb8-185">El orden y los valores necesarios para cada permiso individual en grupos de permisos preestablecidos se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="2afb8-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="2afb8-186">Permiso</span><span class="sxs-lookup"><span data-stu-id="2afb8-186">Permission</span></span>|<span data-ttu-id="2afb8-187">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="2afb8-187">No access</span></span>|<span data-ttu-id="2afb8-188">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="2afb8-188">Limited access</span></span>|<span data-ttu-id="2afb8-189">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="2afb8-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="2afb8-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="2afb8-190">PermissionToAllowSender</span></span>|<span data-ttu-id="2afb8-191">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-191">0</span></span>|<span data-ttu-id="2afb8-192">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-192">0</span></span>|<span data-ttu-id="2afb8-193">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-193">1</span></span>|
|<span data-ttu-id="2afb8-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="2afb8-194">PermissionToBlockSender</span></span>|<span data-ttu-id="2afb8-195">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-195">0</span></span>|<span data-ttu-id="2afb8-196">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-196">1</span></span>|<span data-ttu-id="2afb8-197">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-197">1</span></span>|
|<span data-ttu-id="2afb8-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="2afb8-198">PermissionToDelete</span></span>|<span data-ttu-id="2afb8-199">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-199">0</span></span>|<span data-ttu-id="2afb8-200">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-200">1</span></span>|<span data-ttu-id="2afb8-201">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-201">1</span></span>|
|<span data-ttu-id="2afb8-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2afb8-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="2afb8-203">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-203">0</span></span>|<span data-ttu-id="2afb8-204">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-204">0</span></span>|<span data-ttu-id="2afb8-205">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-205">0</span></span>|
|<span data-ttu-id="2afb8-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="2afb8-206">PermissionToPreview</span></span>|<span data-ttu-id="2afb8-207">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-207">0</span></span>|<span data-ttu-id="2afb8-208">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-208">1</span></span>|<span data-ttu-id="2afb8-209">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-209">1</span></span>|
|<span data-ttu-id="2afb8-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="2afb8-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="2afb8-211">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-211">0</span></span>|<span data-ttu-id="2afb8-212">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-212">0</span></span>|<span data-ttu-id="2afb8-213">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-213">1</span></span>|
|<span data-ttu-id="2afb8-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="2afb8-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="2afb8-215">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-215">0</span></span>|<span data-ttu-id="2afb8-216">1</span><span class="sxs-lookup"><span data-stu-id="2afb8-216">1</span></span>|<span data-ttu-id="2afb8-217">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-217">0</span></span>|
|<span data-ttu-id="2afb8-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2afb8-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="2afb8-219">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-219">0</span></span>|<span data-ttu-id="2afb8-220">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-220">0</span></span>|<span data-ttu-id="2afb8-221">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-221">0</span></span>|
|<span data-ttu-id="2afb8-222">Valor binario</span><span class="sxs-lookup"><span data-stu-id="2afb8-222">Binary value</span></span>|<span data-ttu-id="2afb8-223">00000000</span><span class="sxs-lookup"><span data-stu-id="2afb8-223">00000000</span></span>|<span data-ttu-id="2afb8-224">01101010</span><span class="sxs-lookup"><span data-stu-id="2afb8-224">01101010</span></span>|<span data-ttu-id="2afb8-225">11101100</span><span class="sxs-lookup"><span data-stu-id="2afb8-225">11101100</span></span>|
|<span data-ttu-id="2afb8-226">Valor decimal que se usará</span><span class="sxs-lookup"><span data-stu-id="2afb8-226">Decimal value to use</span></span>|<span data-ttu-id="2afb8-227">0</span><span class="sxs-lookup"><span data-stu-id="2afb8-227">0</span></span>|<span data-ttu-id="2afb8-228">106</span><span class="sxs-lookup"><span data-stu-id="2afb8-228">106</span></span>|<span data-ttu-id="2afb8-229">236</span><span class="sxs-lookup"><span data-stu-id="2afb8-229">236</span></span>|
|

<span data-ttu-id="2afb8-230"><sup>\*</sup> Actualmente, este valor es siempre 0.</span><span class="sxs-lookup"><span data-stu-id="2afb8-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="2afb8-231">Para PermissionToViewHeader, el valor 0  no oculta el botón Ver encabezado del mensaje en los detalles del mensaje en cuarentena (el botón siempre está disponible).</span><span class="sxs-lookup"><span data-stu-id="2afb8-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="2afb8-232"><sup>\*\*</sup> No establezca ambos valores en 1.</span><span class="sxs-lookup"><span data-stu-id="2afb8-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="2afb8-233">Establezca uno en 1 y el otro en 0, o establezca ambos en 0.</span><span class="sxs-lookup"><span data-stu-id="2afb8-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="2afb8-234">En este ejemplo se crea un nuevo nombre de directiva de cuarentena NoAccess que asigna los permisos Sin acceso, tal como se describe en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="2afb8-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="2afb8-235">Para permisos de acceso limitado, use el valor 106.</span><span class="sxs-lookup"><span data-stu-id="2afb8-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="2afb8-236">Para obtener permisos de acceso completo, use el valor 236.</span><span class="sxs-lookup"><span data-stu-id="2afb8-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="2afb8-237">Para los permisos personalizados, use la tabla anterior para obtener el valor binario que corresponde a los permisos que desea.</span><span class="sxs-lookup"><span data-stu-id="2afb8-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="2afb8-238">Convierta el valor binario en un valor decimal y use el valor decimal para el parámetro _EndUserQuarantinePermissionsValue._</span><span class="sxs-lookup"><span data-stu-id="2afb8-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="2afb8-239">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="2afb8-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="2afb8-240">Usar el parámetro EndUserQuarantinePermissions</span><span class="sxs-lookup"><span data-stu-id="2afb8-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="2afb8-241">Para crear una directiva de cuarentena mediante el _parámetro EndUserQuarantinePermissionsValue,_ siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2afb8-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="2afb8-242">R:</span><span class="sxs-lookup"><span data-stu-id="2afb8-242">A.</span></span> <span data-ttu-id="2afb8-243">Almacene un objeto de permisos de cuarentena en una variable mediante el cmdlet **New-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="2afb8-244">B.</span><span class="sxs-lookup"><span data-stu-id="2afb8-244">B.</span></span> <span data-ttu-id="2afb8-245">Use la variable como el _valor EndUserQuarantinePermissions_ en el **comando New-QuarantineTag.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="2afb8-246">Paso A: Almacenar un objeto de permisos de cuarentena en una variable</span><span class="sxs-lookup"><span data-stu-id="2afb8-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="2afb8-247">Utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="2afb8-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="2afb8-248">El valor predeterminado de los parámetros no usados es , por lo que solo necesita usar los parámetros donde desea establecer `$false` el valor en `$true` .</span><span class="sxs-lookup"><span data-stu-id="2afb8-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="2afb8-249">En los ejemplos siguientes se muestra cómo crear objetos de permisos que corresponden a los grupos de permisos preestablecidos:</span><span class="sxs-lookup"><span data-stu-id="2afb8-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="2afb8-250">**Sin acceso**:</span><span class="sxs-lookup"><span data-stu-id="2afb8-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="2afb8-251">**Acceso limitado:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="2afb8-252">**Acceso completo:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="2afb8-253">Para ver los valores que ha establecido, ejecute el nombre de la variable como un comando (por ejemplo, ejecute el comando `$NoAccess` ).</span><span class="sxs-lookup"><span data-stu-id="2afb8-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="2afb8-254">Para los permisos personalizados, no establezca los parámetros _PermissionToRelease_ y _PermissionToRequestRelease en_ `$true` .</span><span class="sxs-lookup"><span data-stu-id="2afb8-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="2afb8-255">Establezca uno en `$true` y deje el otro como , o deje ambos como `$false` `$false` .</span><span class="sxs-lookup"><span data-stu-id="2afb8-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="2afb8-256">También puede modificar una variable de objeto permissions existente después de crearla, pero antes de usarla mediante el cmdlet **Set-QuarantinePermissions.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="2afb8-257">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) y [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span><span class="sxs-lookup"><span data-stu-id="2afb8-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="2afb8-258">Paso B: Usar la variable en el New-QuarantineTag comando</span><span class="sxs-lookup"><span data-stu-id="2afb8-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="2afb8-259">Después de crear y almacenar el objeto permissions en una variable, use la variable para el valor del parámetro _EndUserQuarantinePermission_ en el siguiente comando **New-QuarantineTag:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="2afb8-260">En este ejemplo se crea una nueva directiva de cuarentena denominada LimitedAccess mediante el objeto permissions que se describió y `$LimitedAccess` creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2afb8-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="2afb8-261">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="2afb8-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="2afb8-262">Paso 2: Asignar una directiva de cuarentena a las características compatibles</span><span class="sxs-lookup"><span data-stu-id="2afb8-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="2afb8-263">En _las características_ de protección admitidas que ponen en cuarentena mensajes o archivos (automáticamente o como una acción configurable), puede asignar una directiva de cuarentena a las acciones de cuarentena disponibles.</span><span class="sxs-lookup"><span data-stu-id="2afb8-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="2afb8-264">En la tabla siguiente se describen las características que ponen en cuarentena los mensajes y la disponibilidad de las directivas de cuarentena:</span><span class="sxs-lookup"><span data-stu-id="2afb8-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="2afb8-265">Característica</span><span class="sxs-lookup"><span data-stu-id="2afb8-265">Feature</span></span>|<span data-ttu-id="2afb8-266">¿Se admiten directivas de cuarentena?</span><span class="sxs-lookup"><span data-stu-id="2afb8-266">Quarantine policies supported?</span></span>|<span data-ttu-id="2afb8-267">Directivas de cuarentena predeterminadas usadas</span><span class="sxs-lookup"><span data-stu-id="2afb8-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="2afb8-268">[Directivas contra correo no deseado:](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2afb8-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="2afb8-269">**Correo no deseado** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="2afb8-270">**Correo no deseado de elevada** confianza (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="2afb8-271">**Phishing** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="2afb8-272">**Phishing de elevada confianza** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="2afb8-273">**Bulk** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="2afb8-274">Sí</span><span class="sxs-lookup"><span data-stu-id="2afb8-274">Yes</span></span>|<ul><li><span data-ttu-id="2afb8-275">DefaultSpamTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="2afb8-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="2afb8-276">DefaultHighConfSpamTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="2afb8-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="2afb8-277">DefaultPhishTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="2afb8-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="2afb8-278">DefaultHighConfPhishTag (sin acceso)</span><span class="sxs-lookup"><span data-stu-id="2afb8-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="2afb8-279">DefaultBulkTag (acceso completo)</span><span class="sxs-lookup"><span data-stu-id="2afb8-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="2afb8-280">Directivas contra suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="2afb8-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="2afb8-281">[Protección de inteligencia suplantada](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="2afb8-282">[Protección de suplantación:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2afb8-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="2afb8-283">**Si se detecta message como un usuario suplantado** (_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="2afb8-284">**Si el mensaje se detecta como un dominio suplantado** (_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="2afb8-285">**Si la inteligencia de buzones detecta y suplanta al usuario** (_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="2afb8-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="2afb8-286">No</span><span class="sxs-lookup"><span data-stu-id="2afb8-286">No</span></span>|<span data-ttu-id="2afb8-287">n/a</span><span class="sxs-lookup"><span data-stu-id="2afb8-287">n/a</span></span>|
|<span data-ttu-id="2afb8-288">[Directivas antimalware:](configure-anti-malware-policies.md)todos los mensajes detectados siempre se ponen en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="2afb8-289">No</span><span class="sxs-lookup"><span data-stu-id="2afb8-289">No</span></span>|<span data-ttu-id="2afb8-290">n/a</span><span class="sxs-lookup"><span data-stu-id="2afb8-290">n/a</span></span>|
|[<span data-ttu-id="2afb8-291">Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2afb8-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="2afb8-292">No</span><span class="sxs-lookup"><span data-stu-id="2afb8-292">No</span></span>|<span data-ttu-id="2afb8-293">n/a</span><span class="sxs-lookup"><span data-stu-id="2afb8-293">n/a</span></span>|
|<span data-ttu-id="2afb8-294">[Reglas de flujo de](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) correo (también conocidas como reglas de transporte) con la acción: Entregar el mensaje a la cuarentena **hospedada** (_Cuarentena_).</span><span class="sxs-lookup"><span data-stu-id="2afb8-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="2afb8-295">No</span><span class="sxs-lookup"><span data-stu-id="2afb8-295">No</span></span>|<span data-ttu-id="2afb8-296">n/a</span><span class="sxs-lookup"><span data-stu-id="2afb8-296">n/a</span></span>|
|

<span data-ttu-id="2afb8-297"><sup>\*</sup>La configuración de protección de suplantación solo está disponible en las directivas contra suplantación de identidad en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="2afb8-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="2afb8-298">Si está satisfecho con los permisos de usuario final proporcionados por las directivas de cuarentena predeterminadas, no necesita hacer nada.</span><span class="sxs-lookup"><span data-stu-id="2afb8-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="2afb8-299">Si desea personalizar las capacidades del usuario final (botones disponibles) en notificaciones de correo no deseado del usuario final o en detalles de mensajes en cuarentena, puede asignar una directiva de cuarentena personalizada.</span><span class="sxs-lookup"><span data-stu-id="2afb8-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2afb8-300">Asignar directivas de cuarentena en directivas contra correo no deseado en el portal Microsoft 365 Defender correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2afb8-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2afb8-301">Las instrucciones completas para crear y modificar directivas contra correo no deseado se describen en [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2afb8-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="2afb8-302">En el portal de Microsoft 365 Defender, vaya a Correo electrónico **y &** de colaboración directivas & sección Directivas contra \>  \>  correo \> **no deseado.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="2afb8-303">O bien, abra <https://security.microsoft.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="2afb8-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="2afb8-304">En la **página Directivas contra correo** no deseado, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2afb8-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="2afb8-305">Busque y seleccione una directiva **contra** correo no deseado entrante existente.</span><span class="sxs-lookup"><span data-stu-id="2afb8-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="2afb8-306">Cree una nueva **directiva contra** correo no deseado entrante.</span><span class="sxs-lookup"><span data-stu-id="2afb8-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="2afb8-307">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2afb8-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="2afb8-308">**Editar la directiva contra correo no** deseado existente: en el control desplegable de detalles de la directiva, vaya a la sección Acciones y, a continuación, haga clic en Editar **acciones**. </span><span class="sxs-lookup"><span data-stu-id="2afb8-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="2afb8-309">**Crear una nueva directiva contra correo no deseado:** en el asistente para nueva directiva, vaya a la **página** Acciones.</span><span class="sxs-lookup"><span data-stu-id="2afb8-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="2afb8-310">En la **página** Acciones.</span><span class="sxs-lookup"><span data-stu-id="2afb8-310">On the **Actions** page.</span></span> <span data-ttu-id="2afb8-311">cada veredicto que tenga la **acción Mensaje de** cuarentena también tendrá el cuadro **Seleccionar** directiva de cuarentena para que seleccione una directiva de cuarentena correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2afb8-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="2afb8-312">**Nota:** Al crear una nueva directiva, se usa un valor de directiva de cuarentena **Select** en blanco que indica la directiva de cuarentena predeterminada para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="2afb8-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="2afb8-313">Cuando más adelante edite la directiva, los valores en blanco se reemplazan por los nombres de directiva de cuarentena predeterminados reales, como se describe en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="2afb8-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![Selecciones de directivas de cuarentena en una directiva contra correo no deseado](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="2afb8-315">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="2afb8-316">Asignar directivas de cuarentena en directivas contra correo no deseado en PowerShell</span><span class="sxs-lookup"><span data-stu-id="2afb8-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="2afb8-317">Si prefiere usar PowerShell para asignar directivas de cuarentena en directivas contra correo no deseado, conéctese a Exchange Online PowerShell o Exchange Online Protection PowerShell y use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="2afb8-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="2afb8-318">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="2afb8-318">**Notes**:</span></span>

- <span data-ttu-id="2afb8-319">El valor predeterminado del parámetro _HighConfidencePhishAction_ es Quarantine, por lo que no es necesario establecer la acción Cuarentena para detecciones de phishing de elevada confianza en nuevas directivas contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="2afb8-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="2afb8-320">Para todos los demás veredictos de filtrado de correo no deseado en directivas antispam nuevas o existentes, la directiva de cuarentena solo es eficaz si el valor de la acción es Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="2afb8-321">Para ver los valores de acción en las directivas contra correo no deseado existentes, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2afb8-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="2afb8-322">Para obtener información sobre los valores de acción predeterminados y los valores de acción recomendados para Standard y Strict, consulte [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="2afb8-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="2afb8-323">Un veredicto de filtrado de correo no deseado sin un parámetro de directiva de cuarentena correspondiente significa que se usa la directiva de [cuarentena](#step-2-assign-a-quarantine-policy-to-supported-features) predeterminada para ese veredicto.</span><span class="sxs-lookup"><span data-stu-id="2afb8-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="2afb8-324">Solo necesita reemplazar una directiva de cuarentena predeterminada por una directiva de cuarentena personalizada si desea cambiar las funcionalidades predeterminadas del usuario final en los mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="2afb8-325">Una nueva directiva contra correo no deseado en PowerShell requiere una directiva de filtro de correo no deseado (configuración) mediante el cmdlet **New-HostedContentFilterPolicy** y una nueva regla de filtro de correo no deseado (filtros de destinatarios) mediante el cmdlet **New-HostedContentFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="2afb8-326">Para obtener instrucciones, [vea Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span><span class="sxs-lookup"><span data-stu-id="2afb8-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="2afb8-327">En este ejemplo se crea una nueva directiva de filtro de correo no deseado denominada Departamento de investigación con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="2afb8-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="2afb8-328">La acción de todos los veredictos de filtrado de correo no deseado se establece en Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="2afb8-329">La directiva de cuarentena personalizada denominada NoAccess que asigna **ningún** permiso de acceso reemplaza a las directivas de cuarentena predeterminadas que aún **no** asignan permisos de acceso de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2afb8-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="2afb8-330">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="2afb8-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="2afb8-331">En este ejemplo se modifica la directiva de filtro de correo no deseado existente denominada Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="2afb8-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="2afb8-332">La acción del veredicto de cuarentena de correo no deseado se establece en Cuarentena y se asigna la directiva de cuarentena personalizada denominada NoAccess.</span><span class="sxs-lookup"><span data-stu-id="2afb8-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="2afb8-333">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="2afb8-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2afb8-334">Configurar las opciones de notificación de cuarentena global en el portal de Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="2afb8-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2afb8-335">La configuración global de las directivas de cuarentena permite personalizar las notificaciones de correo no deseado del usuario final que se envían a los destinatarios de los mensajes que se han puesto en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="2afb8-336">Para obtener más información acerca de estas notificaciones, vea [Notificaciones de correo no deseado del usuario final.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="2afb8-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="2afb8-337">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2afb8-338">En la **página Directiva de** cuarentena, seleccione Configuración **global**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="2afb8-339">En el **control desplegable De** notificaciones de cuarentena que se abre, configure algunas o todas las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2afb8-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="2afb8-340">**Nombre para mostrar:** personalice el nombre para mostrar del remitente que se usa en las notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="2afb8-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="2afb8-341">Para cada idioma que haya agregado, seleccione el idioma del segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro Nombre **para** mostrar.</span><span class="sxs-lookup"><span data-stu-id="2afb8-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="2afb8-342">La siguiente captura de pantalla muestra el nombre para mostrar personalizado en una notificación de correo no deseado del usuario final:</span><span class="sxs-lookup"><span data-stu-id="2afb8-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![Un nombre para mostrar del remitente personalizado en una notificación de correo no deseado del usuario final](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="2afb8-344">**Aviso** de declinación de responsabilidades: agregue un aviso de declinación de responsabilidades personalizado a la parte inferior de las notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="2afb8-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="2afb8-345">El texto localizado, **Un aviso de declinación de responsabilidades de su organización:** siempre se incluye primero, seguido del texto que especifique.</span><span class="sxs-lookup"><span data-stu-id="2afb8-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="2afb8-346">Para cada idioma que haya agregado, seleccione el idioma del segundo cuadro de idioma (no haga clic en la X) y escriba el valor de texto que desee en el cuadro **Declinación de** responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="2afb8-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="2afb8-347">La siguiente captura de pantalla muestra el aviso de declinación de responsabilidades personalizado en una notificación de correo no deseado del usuario final:</span><span class="sxs-lookup"><span data-stu-id="2afb8-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![Un aviso de declinación de responsabilidades personalizado en la parte inferior de una notificación de correo no deseado para el usuario final](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="2afb8-349">**Elegir idioma:** las notificaciones de correo no deseado del usuario final ya están localizadas en función de la configuración de idioma del destinatario.</span><span class="sxs-lookup"><span data-stu-id="2afb8-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="2afb8-350">Puede especificar texto personalizado en diferentes idiomas para los valores **Nombre para mostrar** y **Declinación de** responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="2afb8-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="2afb8-351">Seleccione al menos un idioma en el primer cuadro de idioma y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="2afb8-352">Puede seleccionar varios idiomas haciendo clic **en Agregar** después de cada uno.</span><span class="sxs-lookup"><span data-stu-id="2afb8-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="2afb8-353">Un cuadro de idioma de sección muestra todos los idiomas que ha seleccionado:</span><span class="sxs-lookup"><span data-stu-id="2afb8-353">A section language box shows all of the languages that you've selected:</span></span>

     ![Idiomas seleccionados en el segundo cuadro de idioma de la configuración de notificación de cuarentena global de directivas de cuarentena](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="2afb8-355">**Usar el logotipo de mi** empresa: seleccione esta opción para reemplazar el logotipo predeterminado de Microsoft que se usa en la parte superior de las notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="2afb8-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="2afb8-356">Antes de hacerlo, debes seguir las instrucciones de Personalizar el [tema Microsoft 365 de](../../admin/setup/customize-your-organization-theme.md) la organización para cargar el logotipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="2afb8-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="2afb8-357">La siguiente captura de pantalla muestra un logotipo personalizado en una notificación de correo no deseado del usuario final:</span><span class="sxs-lookup"><span data-stu-id="2afb8-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![Logotipo personalizado en una notificación de correo no deseado del usuario final](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2afb8-359">Ver directivas de cuarentena en el Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="2afb8-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="2afb8-360">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2afb8-361">La **página Directiva de** cuarentena muestra la lista de directivas por **Nombre** y Última **fecha actualizada.**</span><span class="sxs-lookup"><span data-stu-id="2afb8-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="2afb8-362">Para ver la configuración de directivas de cuarentena integradas o personalizadas, seleccione la directiva de cuarentena de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="2afb8-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="2afb8-363">Para ver la configuración global, haga clic **en Configuración global**</span><span class="sxs-lookup"><span data-stu-id="2afb8-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="2afb8-364">Ver directivas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="2afb8-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="2afb8-365">Si prefiere usar PowerShell para ver directivas de cuarentena, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2afb8-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="2afb8-366">Para ver una lista resumida de todas las directivas integradas o personalizadas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2afb8-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="2afb8-367">Para ver la configuración de directivas de cuarentena integradas o personalizadas, reemplace por el nombre de la directiva de cuarentena y \<QuarantinePolicyName\> ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2afb8-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="2afb8-368">Para ver la configuración global, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2afb8-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="2afb8-369">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="2afb8-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2afb8-370">Modificar directivas de cuarentena en el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="2afb8-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="2afb8-371">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2afb8-372">En la **página Directivas de** cuarentena, seleccione la directiva haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="2afb8-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="2afb8-373">Después de seleccionar la directiva, haga clic en el icono Editar directiva ![ ](../../media/m365-cc-sc-edit-icon.png) **Editar** icono de directiva que aparece.</span><span class="sxs-lookup"><span data-stu-id="2afb8-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="2afb8-374">El **Asistente para editar** directivas que  se abre es prácticamente idéntico al Asistente para nueva directiva, tal como se describe en la sección Crear directivas de cuarentena en la sección del portal [de Microsoft 365 Defender](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2afb8-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="2afb8-375">La diferencia principal es que no se puede cambiar el nombre de una directiva existente.</span><span class="sxs-lookup"><span data-stu-id="2afb8-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="2afb8-376">Cuando haya terminado de modificar la directiva, vaya a la página **Resumen y** haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="2afb8-377">Modificar directivas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="2afb8-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="2afb8-378">Si prefiere usar PowerShell para modificar una directiva de cuarentena personalizada, reemplace por el nombre de la directiva de cuarentena y \<QuarantinePolicyName\> use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="2afb8-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="2afb8-379">La configuración disponible es la misma que se describe para crear directivas de cuarentena anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2afb8-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="2afb8-380">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="2afb8-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="2afb8-381">Quitar directivas de cuarentena en el Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="2afb8-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="2afb8-382">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="2afb8-382">**Notes**:</span></span>

- <span data-ttu-id="2afb8-383">No puede quitar directivas de cuarentena integradas.</span><span class="sxs-lookup"><span data-stu-id="2afb8-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="2afb8-384">Antes de quitar una directiva de cuarentena personalizada, compruebe que no se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="2afb8-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="2afb8-385">Por ejemplo, ejecute el siguiente comando en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2afb8-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="2afb8-386">Si se usa la directiva de cuarentena, [reemplace la directiva](#step-2-assign-a-quarantine-policy-to-supported-features) de cuarentena asignada antes de quitarla.</span><span class="sxs-lookup"><span data-stu-id="2afb8-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="2afb8-387">En el portal Microsoft 365 Defender, vaya a Correo electrónico **&** sección Directivas de amenazas Sección Directivas de cuarentena y, a continuación, \>  \>  \>  seleccione Directivas **de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="2afb8-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="2afb8-388">En la **página Directiva de** cuarentena, seleccione la directiva de cuarentena personalizada que desea quitar haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="2afb8-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="2afb8-389">Después de seleccionar la directiva, haga clic en el icono Eliminar directiva ![ ](../../media/m365-cc-sc-delete-icon.png) **Eliminar** icono de directiva que aparece.</span><span class="sxs-lookup"><span data-stu-id="2afb8-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="2afb8-390">Haga **clic en Quitar** directiva en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="2afb8-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="2afb8-391">Quitar directivas de cuarentena en PowerShell</span><span class="sxs-lookup"><span data-stu-id="2afb8-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="2afb8-392">Si prefiere usar PowerShell para quitar una directiva de cuarentena personalizada, reemplace por el nombre de la directiva de cuarentena y \<QuarantinePolicyName\> ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="2afb8-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="2afb8-393">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span><span class="sxs-lookup"><span data-stu-id="2afb8-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="2afb8-394">Detalles de permisos de directiva de cuarentena</span><span class="sxs-lookup"><span data-stu-id="2afb8-394">Quarantine policy permission details</span></span>

<span data-ttu-id="2afb8-395">En las secciones siguientes se describen los efectos de los grupos de permisos preestablecidos y los permisos individuales en los detalles de los mensajes en cuarentena y en las notificaciones de correo no deseado del usuario final.</span><span class="sxs-lookup"><span data-stu-id="2afb8-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="2afb8-396">Grupos de permisos preestablecidos</span><span class="sxs-lookup"><span data-stu-id="2afb8-396">Preset permissions groups</span></span>

<span data-ttu-id="2afb8-397">Los permisos individuales que se incluyen en grupos de permisos preestablecidos se enumeran en la tabla al principio de este artículo.</span><span class="sxs-lookup"><span data-stu-id="2afb8-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="2afb8-398">Sin acceso</span><span class="sxs-lookup"><span data-stu-id="2afb8-398">No access</span></span>

<span data-ttu-id="2afb8-399">Si la directiva de cuarentena asigna los **permisos Sin acceso** (sin permisos), los usuarios aún obtienen algunas funcionalidades de línea base:</span><span class="sxs-lookup"><span data-stu-id="2afb8-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="2afb8-400">**Detalles del mensaje en cuarentena:** el **botón Ver encabezado del** mensaje siempre está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![Botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena proporciona al usuario permisos sin acceso](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="2afb8-402">**Notificaciones de correo no deseado del** usuario final: el botón **Revisar** que lleva al usuario al mensaje en cuarentena siempre está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![Botones disponibles en la notificación de correo no deseado del usuario final si la directiva de cuarentena proporciona al usuario Permisos de acceso sin acceso](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="2afb8-404">Acceso limitado</span><span class="sxs-lookup"><span data-stu-id="2afb8-404">Limited access</span></span>

<span data-ttu-id="2afb8-405">Si la directiva de cuarentena asigna los **permisos de** acceso limitado, los usuarios obtienen las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="2afb8-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="2afb8-406">**Detalles del mensaje en cuarentena:** los botones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2afb8-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="2afb8-407">**Versión de solicitud**</span><span class="sxs-lookup"><span data-stu-id="2afb8-407">**Request release**</span></span>
  - <span data-ttu-id="2afb8-408">**Ver encabezado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="2afb8-408">**View message header**</span></span>
  - <span data-ttu-id="2afb8-409">**Mensaje de vista previa**</span><span class="sxs-lookup"><span data-stu-id="2afb8-409">**Preview message**</span></span>
  - <span data-ttu-id="2afb8-410">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="2afb8-410">**Block sender**</span></span>
  - <span data-ttu-id="2afb8-411">**Quitar de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="2afb8-411">**Remove from quarantine**</span></span>

  ![Botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso limitado](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="2afb8-413">**Notificaciones de correo no deseado del** usuario final: los botones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2afb8-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="2afb8-414">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="2afb8-414">**Block sender**</span></span>
  - <span data-ttu-id="2afb8-415">**Revisar**</span><span class="sxs-lookup"><span data-stu-id="2afb8-415">**Review**</span></span>

  ![Botones disponibles en la notificación de correo no deseado del usuario final si la directiva de cuarentena concede al usuario permisos de acceso limitado](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="2afb8-417">Acceso completo</span><span class="sxs-lookup"><span data-stu-id="2afb8-417">Full access</span></span>

<span data-ttu-id="2afb8-418">Si la directiva de cuarentena asigna los **permisos de** acceso completo (todos los permisos disponibles), los usuarios obtienen las siguientes funcionalidades:</span><span class="sxs-lookup"><span data-stu-id="2afb8-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="2afb8-419">**Detalles del mensaje en cuarentena:** los botones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2afb8-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="2afb8-420">**Mensaje de versión**</span><span class="sxs-lookup"><span data-stu-id="2afb8-420">**Release message**</span></span>
  - <span data-ttu-id="2afb8-421">**Ver encabezado de mensaje**</span><span class="sxs-lookup"><span data-stu-id="2afb8-421">**View message header**</span></span>
  - <span data-ttu-id="2afb8-422">**Mensaje de vista previa**</span><span class="sxs-lookup"><span data-stu-id="2afb8-422">**Preview message**</span></span>
  - <span data-ttu-id="2afb8-423">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="2afb8-423">**Block sender**</span></span>
  - <span data-ttu-id="2afb8-424">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="2afb8-424">**Allow sender**</span></span>
  - <span data-ttu-id="2afb8-425">**Quitar de la cuarentena**</span><span class="sxs-lookup"><span data-stu-id="2afb8-425">**Remove from quarantine**</span></span>

  ![Botones disponibles en los detalles del mensaje en cuarentena si la directiva de cuarentena concede al usuario permisos de acceso total](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="2afb8-427">**Notificaciones de correo no deseado del** usuario final: los botones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2afb8-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="2afb8-428">**Bloquear remitente**</span><span class="sxs-lookup"><span data-stu-id="2afb8-428">**Block sender**</span></span>
  - <span data-ttu-id="2afb8-429">**Liberar**</span><span class="sxs-lookup"><span data-stu-id="2afb8-429">**Release**</span></span>
  - <span data-ttu-id="2afb8-430">**Revisar**</span><span class="sxs-lookup"><span data-stu-id="2afb8-430">**Review**</span></span>

  ![Botones disponibles en la notificación de correo no deseado del usuario final si la directiva de cuarentena concede al usuario permisos de acceso completo](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="2afb8-432">Permisos individuales</span><span class="sxs-lookup"><span data-stu-id="2afb8-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="2afb8-433">Recuerde que los usuarios siempre obtienen los botones descritos en la [sección Sin](#no-access) acceso.</span><span class="sxs-lookup"><span data-stu-id="2afb8-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="2afb8-434">Estos botones no se incluyen en las descripciones de permisos individuales.</span><span class="sxs-lookup"><span data-stu-id="2afb8-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="2afb8-435">Permitir permiso de remitente</span><span class="sxs-lookup"><span data-stu-id="2afb8-435">Allow sender permission</span></span>

<span data-ttu-id="2afb8-436">El permiso Permitir **remitente** (_PermissionToAllowSender_) controla el acceso al botón que permite a los usuarios agregar cómodamente el remitente del mensaje en cuarentena a su lista Caja fuerte remitentes.</span><span class="sxs-lookup"><span data-stu-id="2afb8-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="2afb8-437">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2afb8-438">**Permitir permiso de** remitente habilitado: **el botón Permitir remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="2afb8-439">**Permitir permiso de** remitente deshabilitado: **el botón Permitir remitente** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="2afb8-440">**Notificaciones de correo no deseado del usuario final:** Sin efecto.</span><span class="sxs-lookup"><span data-stu-id="2afb8-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="2afb8-441">Para obtener más información acerca de la lista Caja fuerte remitentes, vea Prevent [trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) y Use Exchange Online [PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span><span class="sxs-lookup"><span data-stu-id="2afb8-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="2afb8-442">Bloquear el permiso del remitente</span><span class="sxs-lookup"><span data-stu-id="2afb8-442">Block sender permission</span></span>

<span data-ttu-id="2afb8-443">El **permiso bloquear remitente** (_PermissionToBlockSender_) controla el acceso al botón que permite a los usuarios agregar cómodamente el remitente del mensaje en cuarentena a su lista de remitentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2afb8-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="2afb8-444">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2afb8-445">**Bloquear permiso de** remitente habilitado: el **botón Bloquear remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="2afb8-446">**Bloquear el permiso** del remitente deshabilitado: **el botón Bloquear remitente** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="2afb8-447">**Notificaciones de correo no deseado del usuario final:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="2afb8-448">**Bloquear el permiso** del remitente deshabilitado: **el botón Bloquear remitente** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="2afb8-449">**Bloquear permiso de** remitente habilitado: el **botón Bloquear remitente** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="2afb8-450">Para obtener más información acerca de la lista Remitentes bloqueados, vea [Bloquear](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) mensajes de alguien y Usar Exchange Online PowerShell para configurar la colección de listas seguras [en un buzón.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)</span><span class="sxs-lookup"><span data-stu-id="2afb8-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="2afb8-451">Permiso de eliminación</span><span class="sxs-lookup"><span data-stu-id="2afb8-451">Delete permission</span></span>

<span data-ttu-id="2afb8-452">El **permiso Delete** (_PermissionToDelete_) controla la capacidad de los usuarios para eliminar sus mensajes (mensajes donde el usuario es un destinatario) de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="2afb8-453">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2afb8-454">**Permisos** de eliminación habilitados: **el botón Quitar de cuarentena** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="2afb8-455">**Eliminar** permiso deshabilitado: el **botón Quitar de cuarentena** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="2afb8-456">**Notificaciones de correo no deseado del usuario final:** Sin efecto.</span><span class="sxs-lookup"><span data-stu-id="2afb8-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="2afb8-457">Permiso de vista previa</span><span class="sxs-lookup"><span data-stu-id="2afb8-457">Preview permission</span></span>

<span data-ttu-id="2afb8-458">El **permiso Vista** previa (_PermissionToPreview_) controla la capacidad de los usuarios para obtener una vista previa de sus mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="2afb8-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="2afb8-459">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2afb8-460">**Permiso** de vista previa habilitado: **el botón Vista previa del** mensaje está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="2afb8-461">**Permiso** de vista previa deshabilitado: **el botón Vista previa del** mensaje no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="2afb8-462">**Notificaciones de correo no deseado del usuario final:** Sin efecto.</span><span class="sxs-lookup"><span data-stu-id="2afb8-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="2afb8-463">Permitir que los destinatarios liberen un mensaje del permiso de cuarentena</span><span class="sxs-lookup"><span data-stu-id="2afb8-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="2afb8-464">Allow **recipients to release a message from quarantine** permission (_PermissionToRelease_) controla la capacidad de los usuarios para liberar sus mensajes en cuarentena directamente y sin la aprobación de un administrador.</span><span class="sxs-lookup"><span data-stu-id="2afb8-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="2afb8-465">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2afb8-466">Permiso habilitado: el **botón Liberar mensaje** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="2afb8-467">Permiso deshabilitado: el **botón Liberar mensaje** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="2afb8-468">**Notificaciones de correo no deseado del usuario final:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="2afb8-469">Permiso habilitado: el **botón Liberar** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="2afb8-470">Permiso deshabilitado: el **botón Liberar** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="2afb8-471">Permitir que los destinatarios soliciten un mensaje que se liberará del permiso de cuarentena</span><span class="sxs-lookup"><span data-stu-id="2afb8-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="2afb8-472">Allow **recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span><span class="sxs-lookup"><span data-stu-id="2afb8-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="2afb8-473">El mensaje solo se libera después de que un administrador apruebe la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2afb8-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="2afb8-474">**Detalles del mensaje en cuarentena:**</span><span class="sxs-lookup"><span data-stu-id="2afb8-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="2afb8-475">Permiso habilitado: el **botón Solicitar versión** está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="2afb8-476">Permiso deshabilitado: el **botón Solicitar versión** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="2afb8-477">**Notificaciones de correo no deseado del** usuario final: el botón **Liberar** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="2afb8-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
