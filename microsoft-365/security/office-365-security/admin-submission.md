---
title: Envíos de administración, envíos, problema de correo no deseado, falso negativo, enviar phish, enviar correo electrónico para análisis, correo electrónico sospechoso en Office 365, analizar un mensaje, hacer que Microsoft analice el phishing, hacer que Microsoft analice en busca de correo no deseado, enviar correo electrónico, enviar correo electrónico, Dodgy correo electrónico de estafa a Microsoft, informar de un correo electrónico malintencionado a Microsoft, informar de mensajes de phishing a Microsoft , notificar malware en correo electrónico a Microsoft, correo no deseado en la bandeja de entrada, virus en correo electrónico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo enviar correos sospechosos, mensajes de suplantación de identidad (phishing), correo no deseado y otros mensajes potencialmente perjudiciales, direcciones URL y archivos de la empresa a Microsoft para su análisis.
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631386"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="59659-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="59659-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="59659-104">Si es administrador de una organización de Microsoft 365 con buzones en Exchange Online, puede usar el portal de envíos del centro de seguridad & cumplimiento para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="59659-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="59659-105">Al enviar un correo electrónico, recibirá información sobre las directivas que puedan haber permitido el correo entrante en su inquilino, así como el examen de las direcciones URL y los datos adjuntos del correo.</span><span class="sxs-lookup"><span data-stu-id="59659-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="59659-106">Las directivas que pueden haber permitido un correo incluyen la lista de remitentes seguros de un usuario individual, así como directivas de nivel de inquilino, como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="59659-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="59659-107">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, consulte</span><span class="sxs-lookup"><span data-stu-id="59659-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="59659-108">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="59659-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="59659-109">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="59659-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="59659-110">Para ir directamente a la página de **envío** , <https://protection.office.com/reportsubmission>use.</span><span class="sxs-lookup"><span data-stu-id="59659-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="59659-111">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="59659-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="59659-112">Para conectarse a Exchange Online Protection PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="59659-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="59659-113">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="59659-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="59659-114">Para agregar, modificar y eliminar directivas contra correo no deseado, debe ser miembro de los grupos de funciones **Administración**de la organización, **Administrador de seguridad**o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="59659-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="59659-115">Para obtener más información acerca de los grupos de roles en el centro de seguridad & cumplimiento, consulte [Permissions in the security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="59659-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="59659-116">Para obtener más información sobre cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [informar sobre mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="59659-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a><span data-ttu-id="59659-117">Cómo dirigir contenido sospechoso a Microsoft Scanning</span><span class="sxs-lookup"><span data-stu-id="59659-117">How to direct suspicious content to Microsoft scanning</span></span>

<span data-ttu-id="59659-118">Para enviar contenido a Microsoft, haga clic en el botón **nuevo envío** en el lado superior izquierdo de la página envíos.</span><span class="sxs-lookup"><span data-stu-id="59659-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="59659-119">Un control flotante en el lado derecho de la página aparece con la opción de enviar un correo electrónico, una dirección URL o un archivo.</span><span class="sxs-lookup"><span data-stu-id="59659-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="59659-120">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="59659-120">Submit a questionable email to Microsoft</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="59659-122">Para enviar un correo electrónico, seleccione **correo electrónico** y especifique el **identificador de mensaje de red** de correo electrónico o cargue el archivo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="59659-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="59659-123">Especifique el destinatario o los destinatarios con los que desea ejecutar la comprobación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="59659-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="59659-124">La comprobación de la Directiva determinará si se ha omitido el análisis del correo electrónico debido a directivas de nivel de usuario o de inquilino.</span><span class="sxs-lookup"><span data-stu-id="59659-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="59659-125">Especifique si el correo electrónico se debe haber bloqueado o no.</span><span class="sxs-lookup"><span data-stu-id="59659-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="59659-126">Si el correo electrónico debe haberse bloqueado, especifique si debe haberse bloqueado como correo no deseado, suplantación de identidad (phishing) o malware.</span><span class="sxs-lookup"><span data-stu-id="59659-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="59659-127">Si no está seguro de qué tipo puede ser, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="59659-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="59659-128">Si se ha omitido el filtro debido a las directivas tras el envío, verá información sobre esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="59659-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="59659-129">Si no se ha omitido el filtro debido a una o más directivas, el análisis se completará en varios minutos.</span><span class="sxs-lookup"><span data-stu-id="59659-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="59659-130">Para ver más información sobre el envío, haga clic en el vínculo estado.</span><span class="sxs-lookup"><span data-stu-id="59659-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="59659-131">Esto incluye los resultados de la comprobación de la Directiva y el veredicto de reescaneo.</span><span class="sxs-lookup"><span data-stu-id="59659-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="59659-132">Nota Esto no ejecuta el correo electrónico a través de la pila de filtrado completo de ATP de Office 365, sino que ejecuta un nuevo análisis parcial en función de determinados atributos del correo, la dirección URL o el archivo.</span><span class="sxs-lookup"><span data-stu-id="59659-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="59659-133">Haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="59659-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="59659-134">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="59659-134">Send a suspect URL to Microsoft</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

1. <span data-ttu-id="59659-136">Para enviar una dirección URL, seleccione **dirección URL** en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="59659-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="59659-137">Escriba la dirección URL completa, incluido el protocolo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="59659-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="59659-138">Si seleccionó **debería haber sido filtrada**, especifique si la dirección URL es phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="59659-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="59659-139">Haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="59659-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="59659-140">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="59659-140">Submit a suspected file to Microsoft</span></span>

![Ejemplo de envío de correo electrónico](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="59659-142">Para enviar un **archivo de selección de archivo desde** el control flotante y cargar el archivo que desea examinar.</span><span class="sxs-lookup"><span data-stu-id="59659-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="59659-143">Haga clic en el botón **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="59659-143">Click the **Submit** button.</span></span>
