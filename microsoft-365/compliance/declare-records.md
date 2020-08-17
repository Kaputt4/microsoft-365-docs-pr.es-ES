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
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695282"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="ec715-103">Usar etiquetas de retención para declarar registros</span><span class="sxs-lookup"><span data-stu-id="ec715-103">Declare records by using retention labels</span></span>

><span data-ttu-id="ec715-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="ec715-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ec715-105">Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="ec715-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="ec715-106">Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.</span><span class="sxs-lookup"><span data-stu-id="ec715-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="ec715-107">Configurar etiquetas de retención para declarar registros</span><span class="sxs-lookup"><span data-stu-id="ec715-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="ec715-108">Cuando cree una [etiqueta de retención](retention.md#retention-labels), seleccione la opción para marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="ec715-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="ec715-109">La opción para marcar el contenido como un registro no está disponible al crear o configurar las etiquetas de retención de **Gobierno de la información** en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec715-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ec715-110">En su lugar, debe usar **Administración de registros**.</span><span class="sxs-lookup"><span data-stu-id="ec715-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="ec715-111">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de registros** \> **Plan de archivos**.</span><span class="sxs-lookup"><span data-stu-id="ec715-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="ec715-112">En la página **Plan de archivos**, seleccione **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="ec715-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="ec715-113">En la página **Configuración de la etiqueta** del asistente, elija la opción para clasificar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="ec715-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Haga clic en la casilla Usar una etiqueta para clasificar contenido como un "registro"](../media/recordversioning6.png)

3. <span data-ttu-id="ec715-115">Aplique la etiqueta de retención a los documentos de SharePoint o OneDrive y los correos electrónicos de Exchange, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ec715-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="ec715-116">Para obtener instrucciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="ec715-116">For instructions:</span></span>
    
    - [<span data-ttu-id="ec715-117">Crear etiquetas de retención y aplicarlas en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ec715-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="ec715-118">Aplicar una etiqueta de retención automáticamente al contenido</span><span class="sxs-lookup"><span data-stu-id="ec715-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="ec715-119">Aplicar una etiqueta de retención configurada al contenido</span><span class="sxs-lookup"><span data-stu-id="ec715-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="ec715-120">Cuando las etiquetas de retención que marcan el contenido como un registro se ponen a disposición de los usuarios para que las usen en aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="ec715-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="ec715-121">Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="ec715-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="ec715-122">Para SharePoint y OneDrive, cualquier usuario del grupo predeterminado de miembros (con nivel de permisos de contribución) puede aplicar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="ec715-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="ec715-123">Ejemplo de un documento marcado como registro con una etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="ec715-123">Example of a document marked as record by using a retention label:</span></span>

![Panel de detalles para los documentos etiquetados como registro](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="ec715-125">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ec715-125">Next steps</span></span>

<span data-ttu-id="ec715-126">Si necesita actualizar documentos que son registros, vea [Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="ec715-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="ec715-127">Para más información sobre la eliminación de registros, consulte [Eliminación del contenido](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="ec715-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
