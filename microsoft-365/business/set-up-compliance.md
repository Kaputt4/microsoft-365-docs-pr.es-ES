---
title: Aumentar la protección contra amenazas para Microsoft 365 empresa Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configure las características de cumplimiento para evitar la pérdida de datos y ayude a mantener segura la información confidencial de sus clientes.
ms.openlocfilehash: 18886ff3a0ba5e99e63c70ef083d7a69c75bac91
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785840"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="83476-103">Configurar las características de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="83476-103">Set up compliance features</span></span>

<span data-ttu-id="83476-104">Su Microsoft 365 empresa Premium incluye características para proteger sus datos y dispositivos y ayudarle a mantener segura la información confidencial de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="83476-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="83476-105">Configurar las características de DLP</span><span class="sxs-lookup"><span data-stu-id="83476-105">Set up DLP features</span></span>

<span data-ttu-id="83476-106">Consulte [crear una directiva DLP a partir de una plantilla](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) para obtener un ejemplo sobre cómo configurar una directiva para protegerla contra información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="83476-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="83476-107">DLP incluye varias plantillas de directiva listas para usarse para muchas configuraciones regionales diferentes.</span><span class="sxs-lookup"><span data-stu-id="83476-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="83476-108">Por ejemplo, datos financieros de Australia, Act de información personal de Canadá, datos financieros de Estados Unidos, etc.</span><span class="sxs-lookup"><span data-stu-id="83476-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="83476-109">Vea [Qué incluyen las plantillas de directiva de DLP](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) para obtener una lista completa.</span><span class="sxs-lookup"><span data-stu-id="83476-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="83476-110">Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla PII.</span><span class="sxs-lookup"><span data-stu-id="83476-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="83476-111">Configurar la retención de correo electrónico con el archivado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="83476-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="83476-112">Las características de licencia de **archivado de Exchange Online** ayudan a mantener el cumplimiento normativo y preservar el contenido de correo electrónico para eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="83476-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="83476-113">También ayuda a reducir el riesgo si existe un litigio y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando se necesitan recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="83476-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="83476-114">Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.</span><span class="sxs-lookup"><span data-stu-id="83476-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="83476-115">**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, al poner el buzón completo de un usuario en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="83476-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="83476-116">Para poner un buzón de correo en retención por juicio, en el centro de administración:</span><span class="sxs-lookup"><span data-stu-id="83476-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="83476-117">En el panel de navegación izquierdo, **vaya a usuarios** \> **activos**.</span><span class="sxs-lookup"><span data-stu-id="83476-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="83476-118">Seleccione un usuario cuyo buzón quiera poner en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="83476-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="83476-119">En el panel de usuario, expanda **configuración de correo**y, junto a **más configuraciones**, elija **Editar propiedades de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="83476-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="83476-120">En la página buzón del usuario, elija \* \* características de buzón \* \* en el panel de navegación izquierdo y, a continuación, elija el vínculo **Habilitar** en **retención por juicio**.</span><span class="sxs-lookup"><span data-stu-id="83476-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="83476-121">En el cuadro de diálogo **retención por juicio** , puede especificar la duración de retención por juicio en el campo **duración** de retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="83476-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="83476-122">Deje el campo vacío si desea realizar una suspensión infinita.</span><span class="sxs-lookup"><span data-stu-id="83476-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="83476-123">También puede agregar notas y dirigir al propietario del buzón a un sitio web que tenga que explicar más sobre la retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="83476-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="83476-124">\>**Guardar**.</span><span class="sxs-lookup"><span data-stu-id="83476-124">\> **Save**.</span></span>
    
<span data-ttu-id="83476-125">**Retención:** Puede habilitar las directivas de retención personalizadas, por ejemplo, para conservarlas durante un período de tiempo determinado o eliminar el contenido de forma permanente al final del período de retención.</span><span class="sxs-lookup"><span data-stu-id="83476-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="83476-126">Para obtener más información, vea [información general sobre las directivas de retención](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span><span class="sxs-lookup"><span data-stu-id="83476-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="83476-127">Configurar las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="83476-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="83476-128">Las etiquetas de confidencialidad incluyen el plan 1 de Azure Information Protection (AIP) y le ayudan a clasificar y, de manera opcional, a proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="83476-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="83476-129">Las etiquetas pueden ser aplicadas automáticamente por los administradores que definen las reglas y condiciones, manualmente por los usuarios o mediante una combinación en la que los usuarios obtienen recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="83476-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="83476-130">Para configurar las etiquetas de confidencialidad, vea [crear y administrar las etiquetas de confidencialidad](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) de vídeo.</span><span class="sxs-lookup"><span data-stu-id="83476-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="83476-131">Instalar el cliente de Azure Information Protection de forma manual</span><span class="sxs-lookup"><span data-stu-id="83476-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="83476-132">Para instalar manualmente el cliente de AIP:</span><span class="sxs-lookup"><span data-stu-id="83476-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="83476-133">Descargue **AzinfoProtection_UL.exe** desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="83476-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="83476-134">Puede comprobar que la instalación se ha realizado viendo un documento de Word y asegurándose de que la opción de **sensibilidad** esté disponible en la pestaña **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="83476-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="83476-135">![Cuadro desplegable de la pestaña protección en un documento de Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="83476-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="83476-136">Para obtener más información, vea [Install the Client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="83476-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
