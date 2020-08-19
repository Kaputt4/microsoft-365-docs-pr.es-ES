---
title: Usar etiquetas de retención para declarar registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usar etiquetas de retención para declarar registros.
ms.openlocfilehash: d637817e8d1bcc8c72bfe011dfd288ac4e2d0298
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778520"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="76b00-103">Usar etiquetas de retención para declarar registros</span><span class="sxs-lookup"><span data-stu-id="76b00-103">Declare records by using retention labels</span></span>

><span data-ttu-id="76b00-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="76b00-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="76b00-105">Para declarar elementos como un registro, use las [etiquetas de retención](retention.md#retention-labels) que marcan el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="76b00-105">To declare items as a record, you use [retention labels](retention.md#retention-labels) that mark the content as a record.</span></span> <span data-ttu-id="76b00-106">Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.</span><span class="sxs-lookup"><span data-stu-id="76b00-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="76b00-107">Configurar etiquetas de retención para declarar registros</span><span class="sxs-lookup"><span data-stu-id="76b00-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="76b00-108">Cuando cree o configure una etiqueta de retención, seleccione la opción para marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="76b00-108">When you create or configure a retention label, select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="76b00-109">La opción para marcar el contenido como un registro no está disponible al crear o configurar las etiquetas de retención de **Gobierno de la información** en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76b00-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="76b00-110">En su lugar, debe usar **Administración de registros**.</span><span class="sxs-lookup"><span data-stu-id="76b00-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="76b00-111">Siga estos pasos para crear una nueva etiqueta de retención que marque el contenido como un registro:</span><span class="sxs-lookup"><span data-stu-id="76b00-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="76b00-112">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de registros** \> **Plan de archivos**.</span><span class="sxs-lookup"><span data-stu-id="76b00-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="76b00-113">En la página **Plan de archivos**, seleccione **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="76b00-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="76b00-114">En la página **Configuración de la etiqueta** del asistente, elija la opción para clasificar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="76b00-114">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Haga clic en la casilla Usar una etiqueta para clasificar contenido como un "registro"](../media/recordversioning6.png)

3. <span data-ttu-id="76b00-116">Aplique la etiqueta de retención a los documentos de SharePoint o OneDrive y los correos electrónicos de Exchange, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76b00-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="76b00-117">Para obtener instrucciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="76b00-117">For instructions:</span></span>
    
    - [<span data-ttu-id="76b00-118">Crear etiquetas de retención y aplicarlas en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="76b00-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="76b00-119">Aplicar una etiqueta de retención automáticamente al contenido</span><span class="sxs-lookup"><span data-stu-id="76b00-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="76b00-120">Aplicar una etiqueta de retención configurada al contenido</span><span class="sxs-lookup"><span data-stu-id="76b00-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="76b00-121">Cuando las etiquetas de retención que marcan el contenido como un registro se ponen a disposición de los usuarios para que las usen en aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="76b00-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="76b00-122">Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="76b00-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="76b00-123">Para SharePoint y OneDrive, cualquier usuario del grupo predeterminado de miembros (con nivel de permisos de contribución) puede aplicar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="76b00-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="76b00-124">Ejemplo de un documento marcado como registro con una etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="76b00-124">Example of a document marked as record by using a retention label:</span></span>

![Panel de detalles para los documentos etiquetados como registro](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="76b00-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="76b00-126">Next steps</span></span>

<span data-ttu-id="76b00-127">Para obtener una lista de los escenarios admitidos por la administración de registros, vea [Escenarios comunes de la administración de registros](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="76b00-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
