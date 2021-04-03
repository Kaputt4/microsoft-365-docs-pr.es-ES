---
title: Aumentar la protección contra amenazas para Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Configure las características de cumplimiento para evitar la pérdida de datos y ayudar a proteger la información confidencial de sus clientes y sus clientes.
ms.openlocfilehash: c0accc37d3dcda9ba75813f01a98a3233c5a8369
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579962"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="fa61f-103">Configurar las características de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="fa61f-103">Set up compliance features</span></span>

<span data-ttu-id="fa61f-104">Su Microsoft 365 Empresa Premium incluye características para proteger sus datos y dispositivos y ayudarle a proteger la información confidencial de sus clientes y sus clientes.</span><span class="sxs-lookup"><span data-stu-id="fa61f-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="fa61f-105">Configurar características de DLP</span><span class="sxs-lookup"><span data-stu-id="fa61f-105">Set up DLP features</span></span>

<span data-ttu-id="fa61f-106">Vea [Crear una directiva DLP a partir](../compliance/create-a-dlp-policy-from-a-template.md) de una plantilla para obtener un ejemplo sobre cómo configurar una directiva para proteger contra la pérdida de datos personales.</span><span class="sxs-lookup"><span data-stu-id="fa61f-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="fa61f-107">DLP viene con muchas plantillas de directiva listas para usar para muchas configuraciones regionales diferentes.</span><span class="sxs-lookup"><span data-stu-id="fa61f-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="fa61f-108">Por ejemplo, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="fa61f-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="fa61f-109">Consulta [Qué incluyen las plantillas de directiva DLP](../compliance/what-the-dlp-policy-templates-include.md) para obtener una lista completa.</span><span class="sxs-lookup"><span data-stu-id="fa61f-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="fa61f-110">Todas estas plantillas se pueden habilitar de forma similar al ejemplo de plantilla pii.</span><span class="sxs-lookup"><span data-stu-id="fa61f-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="fa61f-111">Configurar la retención de correo electrónico con Archivado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fa61f-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="fa61f-112">**Archivado de Exchange Online** de licencia ayudan a mantener el cumplimiento y los estándares normativos al conservar el contenido de correo electrónico para la exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="fa61f-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="fa61f-113">También ayuda a reducir el riesgo si hay una demanda y proporciona una forma de recuperar datos después de una infracción de seguridad o cuando necesita recuperar elementos eliminados.</span><span class="sxs-lookup"><span data-stu-id="fa61f-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="fa61f-114">Puede usar la retención por juicio para conservar todo el contenido de un usuario o usar directivas de retención para personalizar lo que desea conservar.</span><span class="sxs-lookup"><span data-stu-id="fa61f-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="fa61f-115">**Retención por juicio:** Puede conservar todo el contenido del buzón, incluidos los elementos eliminados, poniendo todo el buzón de un usuario en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="fa61f-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="fa61f-116">Para colocar un buzón en retención por juicio, en el Centro de administración:</span><span class="sxs-lookup"><span data-stu-id="fa61f-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="fa61f-117">En la navegación izquierda, vaya a **Usuarios** \> **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="fa61f-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="fa61f-118">Seleccione un usuario cuyo buzón desea colocar en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="fa61f-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="fa61f-119">En el panel de usuario, expanda **Configuración de correo** y, junto a Más **opciones,** elija **Editar propiedades de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fa61f-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="fa61f-120">En la página buzón del usuario, elija \*\* características de buzón \*\* en la navegación izquierda y, a continuación, elija el vínculo Habilitar **en** Retención **por juicio**.</span><span class="sxs-lookup"><span data-stu-id="fa61f-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="fa61f-121">En el **cuadro de diálogo** Retención por juicio, puede especificar la duración de retención por juicio en el campo **Duración de retención por** juicio.</span><span class="sxs-lookup"><span data-stu-id="fa61f-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="fa61f-122">Deje el campo vacío si desea colocar una retención infinita.</span><span class="sxs-lookup"><span data-stu-id="fa61f-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="fa61f-123">También puede agregar notas y dirigir al propietario del buzón a un sitio web que quizás tenga que explicar más acerca de la retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="fa61f-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="fa61f-124">\>**Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fa61f-124">\> **Save**.</span></span>
    
<span data-ttu-id="fa61f-125">**Retención:** Puede habilitar directivas de retención personalizadas, por ejemplo, para conservar durante un período de tiempo específico o eliminar contenido de forma permanente al final del período de retención.</span><span class="sxs-lookup"><span data-stu-id="fa61f-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="fa61f-126">Para obtener más información, vea [Overview of retention policies](../compliance/retention.md).</span><span class="sxs-lookup"><span data-stu-id="fa61f-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="fa61f-127">Configurar etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="fa61f-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="fa61f-128">Las etiquetas de confidencialidad vienen con el Plan 1 de Azure Information Protection (AIP) y le ayudan a clasificar y, opcionalmente, proteger sus documentos y correos electrónicos mediante la aplicación de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="fa61f-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="fa61f-129">Los administradores que definen reglas y condiciones pueden aplicar automáticamente las etiquetas, manualmente por los usuarios o mediante una combinación en la que se les dan recomendaciones a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fa61f-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="fa61f-130">Para configurar etiquetas de confidencialidad, vea [crear y administrar el vídeo de etiquetas de](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="fa61f-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="fa61f-131">Instalar el cliente de Azure Information Protection manualmente</span><span class="sxs-lookup"><span data-stu-id="fa61f-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="fa61f-132">Para instalar manualmente el cliente AIP:</span><span class="sxs-lookup"><span data-stu-id="fa61f-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="fa61f-133">Descargue **AzinfoProtection_UL.exe** desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="fa61f-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="fa61f-134">Puede comprobar que la instalación ha funcionado viendo  un documento de Word y asegurándose de que la opción Confidencialidad esté disponible en la **pestaña** Inicio.</span><span class="sxs-lookup"><span data-stu-id="fa61f-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="fa61f-135">![Menú desplegable de la pestaña Protección en un documento de Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="fa61f-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="fa61f-136">Para obtener más información, vea [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="fa61f-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>