---
title: 'Paso 5: Configurar la prevención de pérdida de datos de Office 365'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprender e implementar la prevención de pérdida de datos de Office 365 en Microsoft 365.
ms.openlocfilehash: 896670e9ae83324a1220d64f49a8ea48aee85169
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067227"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a><span data-ttu-id="40dcf-103">Paso 5: Configurar la prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="40dcf-103">Step 5: Configure Office 365 Data Loss Prevention</span></span>

<span data-ttu-id="40dcf-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="40dcf-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Protección de la información](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="40dcf-106">Con directivas de prevención de pérdida de datos (DLP) del Centro de seguridad y cumplimiento de Office 365, puede identificar, supervisar y proteger automáticamente información confidencial en todo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40dcf-106">With data loss prevention (DLP) policies in the Office 365 Security & Compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span> <span data-ttu-id="40dcf-107">Con las directivas DLP, puede:</span><span class="sxs-lookup"><span data-stu-id="40dcf-107">With DLP policies, you can:</span></span>

- <span data-ttu-id="40dcf-108">Identificar información confidencial en varias ubicaciones, como Exchange Online, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40dcf-108">Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
- <span data-ttu-id="40dcf-109">Evitar el uso compartido accidental de información confidencial, bloqueando el acceso a un documento o el correo electrónico que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="40dcf-109">Prevent the accidental sharing of sensitive information by blocking access to a document or blocking the email that contains it.</span></span>
- <span data-ttu-id="40dcf-110">Supervisar y proteger información confidencial en las versiones de escritorio de Excel, PowerPoint y Word.</span><span class="sxs-lookup"><span data-stu-id="40dcf-110">Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.</span></span>
- <span data-ttu-id="40dcf-111">Ayudar a los usuarios a aprender a cumplir las directivas sin interrumpir el flujo de trabajo con notificaciones por correo electrónico y sugerencias de directivas.</span><span class="sxs-lookup"><span data-stu-id="40dcf-111">Help users learn how to stay compliant without interrupting their workflow with email notifications and policy tips.</span></span> 
- <span data-ttu-id="40dcf-112">Ver informes de DLP con contenido que coincida con las directivas DLP de su organización.</span><span class="sxs-lookup"><span data-stu-id="40dcf-112">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="40dcf-113">Una directiva DLP especifica:</span><span class="sxs-lookup"><span data-stu-id="40dcf-113">A DLP policy specifies:</span></span>

- <span data-ttu-id="40dcf-114">**Dónde:** ubicaciones, como los sitios de Exchange Online, SharePoint Online y OneDrive para la Empresa, así como chats y canales de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="40dcf-114">**Where:** Locations such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chats and channels.</span></span>
- <span data-ttu-id="40dcf-115">**Cuándo:** condiciones que debe cumplir el contenido dentro de una regla de directiva específica.</span><span class="sxs-lookup"><span data-stu-id="40dcf-115">**When:** Conditions the content must match within a specific policy rule.</span></span>
- <span data-ttu-id="40dcf-116">**Cómo:** acciones dentro de esa regla coincidente de directiva para realizar automáticamente cuando se cumplan las condiciones.</span><span class="sxs-lookup"><span data-stu-id="40dcf-116">**How:** Actions within that matching policy rule to take automatically for the matching conditions.</span></span>

<span data-ttu-id="40dcf-117">Dicho de otra manera:</span><span class="sxs-lookup"><span data-stu-id="40dcf-117">In other words:</span></span>

- <span data-ttu-id="40dcf-118">Para un documento en esta ubicación (dónde), si el contenido coincide con las condiciones de una regla (cuándo), automáticamente realizar las acciones especificadas en la regla (cómo).</span><span class="sxs-lookup"><span data-stu-id="40dcf-118">For a document in this location (where), if the content matches the conditions of a rule (when), then automatically take the actions specified in the rule (how).</span></span>

<span data-ttu-id="40dcf-119">Para determinar el conjunto de directivas DLP que necesita, debe analizar sus documentos y los tipos de datos dentro de los mismos que necesitan protección contra la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="40dcf-119">To determine the set of DLP policies you need, you must analyze your documents and the types of data within them that need protection from data loss.</span></span> <span data-ttu-id="40dcf-120">Por ejemplo, si tiene una organización financiera en Estados Unidos, podría crear una directiva DLP que impide que los documentos con los números de la seguridad social se compartan fuera de la organización o se envíen por correo electrónico a ubicaciones fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="40dcf-120">For example, if you are a financial organization in the United States of America, you would create a DLP policy that prevents documents with social security numbers from being shared outside the organization or sent in email to locations outside the organization.</span></span>

<span data-ttu-id="40dcf-121">Después, configurar y comprobar las directivas con ubicaciones de prueba para garantizar el comportamiento DLP correcto y minimizar los falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="40dcf-121">Next, you configure and test the policies with test locations to ensure the correct DLP behavior and to minimize false positives.</span></span>

<span data-ttu-id="40dcf-122">Por último, implementarla en su organización para informar a los empleados de las nuevas directivas y su comportamiento deseado y ampliar el ámbito de las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="40dcf-122">Finally, you roll it out to your organization by informing the employees of the new policies and their desired behavior and widening the scope of the locations.</span></span>

<span data-ttu-id="40dcf-123">Para obtener información, consulte [Introducción a las recomendaciones de la directiva DLP](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span><span class="sxs-lookup"><span data-stu-id="40dcf-123">For more information, see [Get started with DLP policy recommendations](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).</span></span>

<span data-ttu-id="40dcf-124">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step5) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="40dcf-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step5) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="40dcf-125">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="40dcf-125">Next step</span></span>

|||
|:-------|:-----|
|![Paso 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="40dcf-127">Configurar el cifrado de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="40dcf-127">Configure email encryption</span></span>](infoprotect-email-encryption.md)|


