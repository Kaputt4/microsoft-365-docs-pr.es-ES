---
title: Notas de la versión sobre la compatibilidad del Centro de cumplimiento de Microsoft 365 con juegos de caracteres de doble byte (vista previa)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de la versión para la compatibilidad con juegos de caracteres de doble byte.
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681506"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="f4313-103">Notas de la versión sobre la compatibilidad con juegos de caracteres de doble byte (vista previa)</span><span class="sxs-lookup"><span data-stu-id="f4313-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="f4313-104">Microsoft 365 Information Protection ahora es compatible con la vista previa de idiomas con conjunto de caracteres de doble byte para:</span><span class="sxs-lookup"><span data-stu-id="f4313-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="f4313-105">Chino (simplificado)</span><span class="sxs-lookup"><span data-stu-id="f4313-105">Chinese (simplified)</span></span>
- <span data-ttu-id="f4313-106">Chino (tradicional)</span><span class="sxs-lookup"><span data-stu-id="f4313-106">Chinese (traditional)</span></span>
- <span data-ttu-id="f4313-107">Coreano</span><span class="sxs-lookup"><span data-stu-id="f4313-107">Korean</span></span>
- <span data-ttu-id="f4313-108">Japonés</span><span class="sxs-lookup"><span data-stu-id="f4313-108">Japanese</span></span>

<span data-ttu-id="f4313-109">Esta compatibilidad está disponible para tipos de información confidencial y diccionarios de palabras clave y se reflejará en las soluciones de prevención de pérdida de datos, cumplimiento de las comunicaciones, Exchange Online, SharePoint Online, OneDrive para la Empresa y Teams.</span><span class="sxs-lookup"><span data-stu-id="f4313-109">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f4313-110">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="f4313-110">Known issues</span></span>

- <span data-ttu-id="f4313-111">Cuando un archivo de texto adjunto a un correo electrónico está en formato UTF-8 sin marca de orden de bytes (BOM), el correo electrónico no se detecta mediante la directiva de cumplimiento de cumplimiento de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4313-111">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="f4313-112">Las directivas de cumplimiento de comunicaciones no pueden detectar valores si se especifica una frase para la condición de la directiva: "el mensaje contiene alguna de estas palabras".</span><span class="sxs-lookup"><span data-stu-id="f4313-112">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="f4313-113">Si el texto especificado en la directiva está escrito como una palabra, puede detectarse; sin embargo, si está escrito en mitad de una oración, no se detectará.</span><span class="sxs-lookup"><span data-stu-id="f4313-113">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="f4313-114">Las directivas de Cumplimiento de comunicaciones que especifican diccionarios como información de tipo no detectan chats privados y chats de canales de Teams.</span><span class="sxs-lookup"><span data-stu-id="f4313-114">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="f4313-115">Las condiciones siguientes no son compatibles con el Cumplimiento de comunicaciones en este momento (pensamos solucionar estos problemas en el futuro):</span><span class="sxs-lookup"><span data-stu-id="f4313-115">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="f4313-116">"El mensaje contiene cualquiera de estas palabras"</span><span class="sxs-lookup"><span data-stu-id="f4313-116">“Message contains any of these words”</span></span>
  - <span data-ttu-id="f4313-117">"El mensaje no contiene ninguna de estas palabras"</span><span class="sxs-lookup"><span data-stu-id="f4313-117">“Message contains none of these words”</span></span>
  - <span data-ttu-id="f4313-118">"Los datos adjuntos contienen cualquiera de estas palabras"</span><span class="sxs-lookup"><span data-stu-id="f4313-118">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="f4313-119">"Los datos adjuntos contienen cualquiera de estas palabras"</span><span class="sxs-lookup"><span data-stu-id="f4313-119">“Attachment contains any of these words”</span></span>

<span data-ttu-id="f4313-120">En su lugar, recomendamos crear un Tipo de información confidencial personalizado (SIT) con el diccionario de palabras clave que detectará los patrones en mensajes y datos adjuntos, utilizando este SIT personalizado como condición de la directiva de Cumplimiento de las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4313-120">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
