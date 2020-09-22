---
title: Ver información sobre los archivos malintencionados detectados por Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Obtenga información sobre dónde ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Teams, y cómo tomar medidas en esos archivos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e6cd0363b546fad063290ae20e8c6c82fd6d0dea
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202000"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="43090-103">Ver información sobre los archivos malintencionados detectados en SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43090-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="43090-104">[Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) protege a su organización de archivos malintencionados en las bibliotecas de documentos y sitios de grupo.</span><span class="sxs-lookup"><span data-stu-id="43090-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="43090-105">Cuando se detecta un archivo malintencionado, se bloquea el archivo para que nadie lo pueda abrir, copiar, mover ni compartir hasta que el equipo de seguridad de la organización haya realizado otras acciones.</span><span class="sxs-lookup"><span data-stu-id="43090-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="43090-106">Lea este artículo para obtener información sobre cómo ver información sobre los archivos detectados y qué acciones llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="43090-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="43090-107">Para realizar las tareas descritas en este artículo, debe tener los [permisos necesarios para el centro de seguridad y &amp; cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="43090-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="43090-108">Ver informes con información sobre los archivos detectados</span><span class="sxs-lookup"><span data-stu-id="43090-108">View reports with information about detected files</span></span>

<span data-ttu-id="43090-109">Para ver información detallada y de estado sobre los archivos detectados por Office 365 ATP, puede usar el informe de estado de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="43090-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="43090-110">En el [centro de seguridad y &amp; cumplimiento](https://protection.office.com), seleccione **informes** de estado de protección contra \> **Dashboard** \> **amenazas**del panel.</span><span class="sxs-lookup"><span data-stu-id="43090-110">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="43090-111">En la esquina superior derecha del informe, elija **ver tabla de detalles**.</span><span class="sxs-lookup"><span data-stu-id="43090-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="43090-112">Ver la lista de los archivos que se han detectado en el informe.</span><span class="sxs-lookup"><span data-stu-id="43090-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="43090-113">Seleccione un elemento de la lista para ver información detallada, incluidas las acciones realizadas, el nombre de archivo, la ruta de acceso al archivo, etc.</span><span class="sxs-lookup"><span data-stu-id="43090-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="43090-114">Elija la pestaña **análisis avanzado** para ver la información, como el comportamiento observado y los detalles de análisis.</span><span class="sxs-lookup"><span data-stu-id="43090-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="43090-115">Ver y emprender acciones en los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="43090-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="43090-116">En el centro de seguridad &amp; y cumplimiento, seleccione Quarantine **Management** \> **Review** \> **Quarantine**.</span><span class="sxs-lookup"><span data-stu-id="43090-116">In the Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="43090-117">(También puede ir directamente a [https://protection.office.com/quarantine](https://protection.office.com/quarantine) ).</span><span class="sxs-lookup"><span data-stu-id="43090-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="43090-118">En la esquina superior izquierda, cambie el menú desplegable de **mensajes de correo electrónico** a **archivos**.</span><span class="sxs-lookup"><span data-stu-id="43090-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="43090-119">Si la lista de resultados incluye demasiados elementos, use la funcionalidad de **filtro** para restringir la selección.</span><span class="sxs-lookup"><span data-stu-id="43090-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="43090-120">Seleccione un elemento de la lista para ver información detallada, incluida la dirección URL del archivo.</span><span class="sxs-lookup"><span data-stu-id="43090-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="43090-121">Elija una acción disponible.</span><span class="sxs-lookup"><span data-stu-id="43090-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="43090-122">Seleccione **liberar archivo** para desbloquear el archivo.</span><span class="sxs-lookup"><span data-stu-id="43090-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="43090-123">Seleccione **Enviar informe a Microsoft** para informar del archivo como falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43090-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="43090-124">Elija **Descargar archivo** para investigar más el archivo.</span><span class="sxs-lookup"><span data-stu-id="43090-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="43090-125">Elija **quitar de cuarentena** para quitar el archivo de la lista de elementos en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="43090-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="43090-126">Si elige esta opción, también debe eliminar el archivo de su biblioteca correspondiente en SharePoint Online, OneDrive para la empresa o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="43090-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="43090-127">Esta opción no bloquea la apertura o el uso compartido de un archivo.</span><span class="sxs-lookup"><span data-stu-id="43090-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="43090-128">Elija **cerrar** para cerrar los detalles de un elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="43090-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

