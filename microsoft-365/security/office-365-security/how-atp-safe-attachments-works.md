---
title: Cómo funcionan los datos adjuntos seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información acerca de cómo puede mantener su organización segura contra archivos malintencionados mediante datos adjuntos seguros de ATP para Office 365.
ms.openlocfilehash: a0d5923ccac525b23aa2ef6b45936524f0a7b483
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036661"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="5db4f-103">Cómo funcionan los datos adjuntos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="5db4f-103">How ATP Safe Attachments works</span></span>

## <a name="how-it-works"></a><span data-ttu-id="5db4f-104">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="5db4f-104">How it works</span></span>

<span data-ttu-id="5db4f-105">La característica de datos adjuntos seguros de ATP comprueba los datos adjuntos del correo electrónico de las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="5db4f-105">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="5db4f-106">Cuando se implementa una directiva de datos adjuntos seguros de ATP y alguien que cubre esa Directiva ve su correo electrónico en Office 365, se comprueban los datos adjuntos del correo electrónico y se realizan las acciones adecuadas, según las directivas de datos adjuntos seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="5db4f-106">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="5db4f-107">Según cómo se hayan definido las directivas, los usuarios pueden seguir trabajando sin saber nunca que se les enviaron archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="5db4f-107">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="5db4f-108">A continuación se muestran dos ejemplos de datos adjuntos seguros de ATP en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="5db4f-108">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="5db4f-109">**Ejemplo 1: datos adjuntos de correo electrónico** Supongamos que lee recibe un mensaje de correo electrónico que tiene datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="5db4f-109">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="5db4f-110">No es obvio si esos datos adjuntos son seguros o contiene malware diseñado para robar las credenciales de usuario de Lee.</span><span class="sxs-lookup"><span data-stu-id="5db4f-110">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="5db4f-111">En la organización de Lee, un administrador de seguridad definió una directiva de datos adjuntos seguros de ATP hace unos días.</span><span class="sxs-lookup"><span data-stu-id="5db4f-111">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="5db4f-112">Con la característica de datos adjuntos seguros de ATP, los datos adjuntos de correo electrónico se abren y se prueban en un entorno virtual antes de que Lucas los reciba.</span><span class="sxs-lookup"><span data-stu-id="5db4f-112">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="5db4f-113">Si los datos adjuntos se determinan como malintencionados, se eliminarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5db4f-113">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="5db4f-114">Si los datos adjuntos son seguros, se abrirán como se esperaba cuando lee hace clic en él.</span><span class="sxs-lookup"><span data-stu-id="5db4f-114">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="5db4f-115">**Ejemplo 2: archivo en SharePoint Online** Supongamos que Jean ha recibido un archivo y lo ha cargado en una biblioteca en SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5db4f-115">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="5db4f-116">Jean comparte el vínculo al archivo con el resto del equipo, sin saber que el archivo es realmente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="5db4f-116">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="5db4f-117">Afortunadamente, [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md) detecta el archivo malintencionado y lo bloquea.</span><span class="sxs-lookup"><span data-stu-id="5db4f-117">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="5db4f-118">Unos días más tarde, Carlos abrirá el documento.</span><span class="sxs-lookup"><span data-stu-id="5db4f-118">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="5db4f-119">Aunque Carlos puede ver el archivo está allí, Carlos no puede abrirlo ni compartirlo, lo que protege al equipo de Cristina y a otros usuarios del archivo malintencionado.</span><span class="sxs-lookup"><span data-stu-id="5db4f-119">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="5db4f-120">Las directivas de datos adjuntos seguros de ATP se pueden aplicar a personas o grupos específicos de la organización o a todo el dominio.</span><span class="sxs-lookup"><span data-stu-id="5db4f-120">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="5db4f-121">Además, las directivas de datos adjuntos seguros de ATP se pueden configurar para usar datos adjuntos de marcador de posición mientras se analizan los datos adjuntos reales.</span><span class="sxs-lookup"><span data-stu-id="5db4f-121">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="5db4f-122">Para obtener más información, consulte **[configurar las directivas de datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="5db4f-122">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="5db4f-123">El análisis de datos adjuntos seguros de ATP tiene lugar en la misma región en la que residen los datos.</span><span class="sxs-lookup"><span data-stu-id="5db4f-123">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="5db4f-124">Para más información sobre la geografía de centros de datos, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="5db4f-124">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

