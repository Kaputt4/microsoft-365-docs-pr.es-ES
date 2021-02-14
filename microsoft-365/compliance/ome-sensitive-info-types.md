---
title: Crear una directiva de tipo de información confidencial mediante el cifrado de mensajes de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Obtenga información sobre cómo crear una directiva de tipo de información confidencial para su organización mediante el cifrado de mensajes de Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfc77fa88ff798f98d260682dfbdbdd57b17af69
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545990"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="ca004-103">Crear una directiva de tipo de información confidencial para su organización mediante el cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="ca004-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="ca004-104">Puede usar reglas de flujo de correo de Exchange o prevención de pérdida de datos (DLP) para crear una directiva de tipo de información confidencial con cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca004-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="ca004-105">Para crear una regla de flujo de correo de Exchange, puede usar el Centro de administración de Exchange (EAC) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca004-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="ca004-106">Para crear la directiva mediante reglas de flujo de correo en el EAC</span><span class="sxs-lookup"><span data-stu-id="ca004-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="ca004-107">Inicie sesión en el Centro de administración de Exchange (EAC) y vaya a **Reglas de flujo de**  >  **correo.**</span><span class="sxs-lookup"><span data-stu-id="ca004-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="ca004-108">En la página Reglas, cree una regla que aplique el cifrado de mensajes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca004-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="ca004-109">Puede crear una regla basada en condiciones como la presencia de determinadas palabras clave o tipos de información confidencial en el mensaje o datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="ca004-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="ca004-110">Para crear la directiva mediante reglas de flujo de correo en PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca004-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="ca004-111">Use una cuenta de trabajo o escuela que tenga permisos de administrador global en su organización, inicie una sesión de Windows PowerShell y conéctese a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ca004-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ca004-112">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="ca004-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="ca004-113">Use los cmdlets Set-IRMConfiguration y New-TransportRule para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="ca004-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="ca004-114">Ejemplo de regla de flujo de correo creada con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca004-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="ca004-115">Ejecute los siguientes comandos en PowerShell para crear una regla de flujo de  correo de Exchange que cifre automáticamente los correos electrónicos enviados fuera de la organización con la directiva De solo cifrado si los correos electrónicos o sus datos adjuntos contienen los siguientes tipos de información confidencial:</span><span class="sxs-lookup"><span data-stu-id="ca004-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="ca004-116">Número de enrutamiento ABA</span><span class="sxs-lookup"><span data-stu-id="ca004-116">ABA routing number</span></span>
- <span data-ttu-id="ca004-117">Número de tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="ca004-117">Credit card Number</span></span>
- <span data-ttu-id="ca004-118">Número de la Agencia Antidrogas (DEA)</span><span class="sxs-lookup"><span data-stu-id="ca004-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="ca004-119">EE.UU. / Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ca004-119">U.S. / U.K.</span></span> <span data-ttu-id="ca004-120">passport number</span><span class="sxs-lookup"><span data-stu-id="ca004-120">passport number</span></span>
- <span data-ttu-id="ca004-121">Número de cuenta bancaria de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ca004-121">U.S. bank account number</span></span>
- <span data-ttu-id="ca004-122">Número de identificación de contribuyente individual (ITIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ca004-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="ca004-123">Número de seguridad social (SSN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="ca004-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="ca004-124">Para obtener más información, [vea Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) y [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="ca004-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="ca004-125">Cómo acceden los destinatarios a los datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="ca004-125">How recipients access attachments</span></span>

<span data-ttu-id="ca004-126">Después de que Microsoft cifre un mensaje, los destinatarios tendrán acceso sin restricciones a los datos adjuntos cuando accedan y abran su correo electrónico cifrado.</span><span class="sxs-lookup"><span data-stu-id="ca004-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="ca004-127">Para prepararse para este cambio</span><span class="sxs-lookup"><span data-stu-id="ca004-127">To prepare for this change</span></span>

<span data-ttu-id="ca004-128">Es posible que desee actualizar la documentación y los materiales de aprendizaje aplicables para el usuario final a fin de preparar a los usuarios de su organización para este cambio.</span><span class="sxs-lookup"><span data-stu-id="ca004-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="ca004-129">Comparta estos recursos de cifrado de mensajes de Office 365 con los usuarios según corresponda:</span><span class="sxs-lookup"><span data-stu-id="ca004-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="ca004-130">Enviar, ver y responder mensajes cifrados en Outlook para PC</span><span class="sxs-lookup"><span data-stu-id="ca004-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="ca004-131">Vídeo de Microsoft 365 Essentials: Cifrado de mensajes de Office</span><span class="sxs-lookup"><span data-stu-id="ca004-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="ca004-132">Ver estos cambios en el registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="ca004-132">View these changes in the audit log</span></span>

<span data-ttu-id="ca004-133">Microsoft 365 audita esta actividad y la pone a disposición de los administradores.</span><span class="sxs-lookup"><span data-stu-id="ca004-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="ca004-134">La operación es "New-TransportRule" y a continuación se muestra un fragmento de código de una entrada de auditoría de ejemplo de la búsqueda de registros de auditoría en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="ca004-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="ca004-135">Para deshabilitar o personalizar la directiva de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="ca004-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="ca004-136">Una vez que haya creado la regla [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) de flujo de correo de Exchange, puede deshabilitar o editar la regla yendo a Reglas de flujo de correo en el Centro de administración de Exchange (EAC) y deshabilitando la regla " Cifrar mensajes de correo electrónico confidenciales  >   *salientes (regla* de configuración) ".</span><span class="sxs-lookup"><span data-stu-id="ca004-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
