---
title: Configurar las nuevas capacidades de cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Obtenga más información sobre las nuevas funcionalidades de cifrado de mensajes de Office 365 que permiten la comunicación por correo electrónico protegido con personas de dentro y fuera de su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d6e37da7456cfbb0b7cbf8d986b54615aca60f0
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819190"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="69bc4-103">Configurar las nuevas capacidades de cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="69bc4-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="69bc4-104">Las nuevas funcionalidades de cifrado de mensajes de Office 365 (OME) permiten que las organizaciones compartan mensajes de correo electrónico protegidos con cualquier persona en cualquier dispositivo.</span><span class="sxs-lookup"><span data-stu-id="69bc4-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="69bc4-105">Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Microsoft 365, así como con quienes no son clientes, usando Outlook.com, Gmail y otros servicios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="69bc4-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="69bc4-106">Siga los pasos que se indican a continuación para asegurarse de que las nuevas funcionalidades de OME estén disponibles en su organización.</span><span class="sxs-lookup"><span data-stu-id="69bc4-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="69bc4-107">Verificar que Azure Rights Management está habilitada</span><span class="sxs-lookup"><span data-stu-id="69bc4-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="69bc4-108">Las nuevas funcionalidades de OME aprovechan las características de protección de [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), la tecnología usada por [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) para proteger los correos electrónicos y los documentos mediante controles de acceso y encriptación.</span><span class="sxs-lookup"><span data-stu-id="69bc4-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="69bc4-109">El único requisito previo para usar las nuevas funcionalidades de OME es que la funcionalidad [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) debe estar activada en el espacio empresarial de su organización.</span><span class="sxs-lookup"><span data-stu-id="69bc4-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="69bc4-110">Si lo está, Microsoft 365 activa automáticamente las nuevas funcionalidades de OME y no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="69bc4-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="69bc4-111">Azure RMS también se activa automáticamente en la mayoría de los planes compatibles, por lo que probablemente tampoco tendrá que hacer nada al respecto.</span><span class="sxs-lookup"><span data-stu-id="69bc4-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="69bc4-112">Vea [Activar Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="69bc4-112">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="69bc4-113">Si usa los servicios de Active Directory Rights Management (AD RMS) con Exchange Online, tendrá que [migrar a Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) antes de poder usar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="69bc4-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="69bc4-114">OME no es compatible con AD RMS.</span><span class="sxs-lookup"><span data-stu-id="69bc4-114">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="69bc4-115">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="69bc4-115">For more information, see:</span></span>

- <span data-ttu-id="69bc4-116">[¿Qué suscripciones necesito para usar las nuevas funcionalidades de OME?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye la funcionalidad de Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="69bc4-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="69bc4-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) para obtener información sobre cómo comprar una suscripción apta.</span><span class="sxs-lookup"><span data-stu-id="69bc4-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="69bc4-118">Activar Azure Rights Management manualmente</span><span class="sxs-lookup"><span data-stu-id="69bc4-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="69bc4-119">Si deshabilitó Azure RMS, o si no se activó automáticamente por algún motivo, puede activarlo manualmente en:</span><span class="sxs-lookup"><span data-stu-id="69bc4-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="69bc4-120">**El Centro de administración de Microsoft 365**: vea [Cómo activar Azure Rights Management desde el centro de administración](https://docs.microsoft.com/azure/information-protection/activate-office365) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="69bc4-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="69bc4-121">**Azure Portal**: vea [Cómo activar Azure Rights Management desde Azure Portal](https://docs.microsoft.com/azure/information-protection/activate-azure) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="69bc4-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="69bc4-122">Configurar la administración del espacio empresarial de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="69bc4-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="69bc4-123">Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="69bc4-123">This is an optional step.</span></span> <span data-ttu-id="69bc4-124">Permitir que Microsoft administre la clave raíz de Azure Information Protection es la configuración predeterminada y el procedimiento recomendado para la mayoría de organizaciones.</span><span class="sxs-lookup"><span data-stu-id="69bc4-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="69bc4-125">Si este es el caso, no es necesario que realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="69bc4-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="69bc4-126">Hay muchos motivos, por ejemplo, los requisitos de cumplimiento, que pueden requerir la creación y administración de su propia clave raíz (también conocido como Bring your own key (BYOK)).</span><span class="sxs-lookup"><span data-stu-id="69bc4-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="69bc4-127">Si este es el caso, le recomendamos que complete los pasos requeridos antes de configurar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="69bc4-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="69bc4-128">Vea [Planificar e implementar la clave de espacio empresarial de Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="69bc4-128">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="69bc4-129">Comprobar la nueva configuración de OME en PowerShell de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="69bc4-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="69bc4-130">Puede comprobar que su espacio empresarial de Microsoft 365 está configurado correctamente para usar las nuevas funcionalidades de OME en [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="69bc4-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="69bc4-131">[Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69bc4-131">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="69bc4-132">Ejecute el cmdlet Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="69bc4-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="69bc4-133">Debería ver un valor $True para el parámetro AzureRMSLicensingEnabled, el cuál indica que OME está configurado en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="69bc4-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="69bc4-134">Si no lo está, utilice set-IRMConfiguration para establecer el valor de AzureRMSLicensingEnabled en $True para habilitar OME.</span><span class="sxs-lookup"><span data-stu-id="69bc4-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="69bc4-135">Ejecute el cmdlet test-IRMConfiguration usando la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="69bc4-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="69bc4-136">**Ejemplo**:</span><span class="sxs-lookup"><span data-stu-id="69bc4-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="69bc4-137">Proporcionar un correo electrónico del remitente es opcional, pero obliga al sistema a ejecutar comprobaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="69bc4-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="69bc4-138">Use la dirección de correo electrónico de cualquier usuario de su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69bc4-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="69bc4-139">Sus resultados deben ser similares a estos:</span><span class="sxs-lookup"><span data-stu-id="69bc4-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="69bc4-140">El nombre de su organización reemplazará a *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="69bc4-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="69bc4-141">Los nombres de las plantillas predeterminadas pueden diferir de los que se muestran arriba.</span><span class="sxs-lookup"><span data-stu-id="69bc4-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="69bc4-142">Vea [Configurar y administrar plantillas para Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="69bc4-142">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="69bc4-143">Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.</span><span class="sxs-lookup"><span data-stu-id="69bc4-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="69bc4-144">Pasos siguientes: defina reglas de flujo de correo para usar las nuevas funcionalidades de OME</span><span class="sxs-lookup"><span data-stu-id="69bc4-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="69bc4-145">Si existen reglas de flujo de correo configuradas previamente para cifrar el correo electrónico de su organización, debe actualizar las reglas existentes para usar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="69bc4-145">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="69bc4-146">Para las nuevas implementaciones, debe crear nuevas reglas de flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="69bc4-146">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="69bc4-147">Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado con el formato de archivo adjunto HTML anterior, en lugar de la nueva experiencia de OME de conexión directa.</span><span class="sxs-lookup"><span data-stu-id="69bc4-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="69bc4-148">Las reglas de flujo de correo determinan bajo qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar ese cifrado.</span><span class="sxs-lookup"><span data-stu-id="69bc4-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="69bc4-149">Al establecer una acción para una regla, todos los mensajes que coinciden con las condiciones de la regla se cifran al enviarse.</span><span class="sxs-lookup"><span data-stu-id="69bc4-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="69bc4-150">Para conocer los pasos para crear reglas de flujo de correo para OME, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="69bc4-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="69bc4-151">Para actualizar las reglas existentes para poder usar las nuevas funcionalidades de OME:</span><span class="sxs-lookup"><span data-stu-id="69bc4-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="69bc4-152">En el centro de administración de Microsoft 365, vaya a **Centros de administración > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="69bc4-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="69bc4-153">En el centro de administración de Exchange, vaya a **Flujo de correo > Reglas**.</span><span class="sxs-lookup"><span data-stu-id="69bc4-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="69bc4-154">Para cada regla, en **Hacer lo siguiente**:</span><span class="sxs-lookup"><span data-stu-id="69bc4-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="69bc4-155">Seleccione **Modificar la seguridad de los mensajes**.</span><span class="sxs-lookup"><span data-stu-id="69bc4-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="69bc4-156">Seleccione **Aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.</span><span class="sxs-lookup"><span data-stu-id="69bc4-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="69bc4-157">Seleccione una plantilla RMS de la lista.</span><span class="sxs-lookup"><span data-stu-id="69bc4-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="69bc4-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="69bc4-158">Select **Save**.</span></span>
    - <span data-ttu-id="69bc4-159">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="69bc4-159">Select **OK**.</span></span>
