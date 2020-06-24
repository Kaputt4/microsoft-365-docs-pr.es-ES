---
title: ¿Qué viene con la puntuación segura de Microsoft?
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 48ff6d6f5cac0991895c40cae90ca31657cfedff
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844887"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="7a2c3-104">¿Qué viene con la puntuación segura de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="7a2c3-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="7a2c3-105">Para hacer que la [puntuación segura de Microsoft](microsoft-secure-score.md) sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="7a2c3-106">Se cambiará la puntuación y la puntuación máxima posible.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="7a2c3-107">Sin embargo, esto no implica un cambio en su postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7a2c3-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="7a2c3-108">Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="7a2c3-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="june-2020"></a><span data-ttu-id="7a2c3-109">Junio de 2020</span><span class="sxs-lookup"><span data-stu-id="7a2c3-109">June 2020</span></span>

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7a2c3-110">Quitar la acción de mejora para la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="7a2c3-110">Remove improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="7a2c3-111">Activar las reglas de reducción de la superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="7a2c3-111">Turn on Attack Surface Reduction rules</span></span>

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7a2c3-112">Agregar acciones de mejora para la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="7a2c3-112">Add improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="7a2c3-113">Impedir que Adobe Reader cree procesos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a2c3-113">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="7a2c3-114">Usar protección avanzada contra ransomware</span><span class="sxs-lookup"><span data-stu-id="7a2c3-114">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="7a2c3-115">Bloquear todas las aplicaciones de Office para crear procesos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a2c3-115">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="7a2c3-116">Impedir que las aplicaciones de Office creen contenido ejecutable</span><span class="sxs-lookup"><span data-stu-id="7a2c3-116">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="7a2c3-117">Impedir que JavaScript o VBScript inicien contenido ejecutable descargado</span><span class="sxs-lookup"><span data-stu-id="7a2c3-117">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="7a2c3-118">Bloquear la ejecución de scripts potencialmente ofuscados</span><span class="sxs-lookup"><span data-stu-id="7a2c3-118">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="7a2c3-119">Bloquear contenido ejecutable del cliente de correo electrónico y Webmail</span><span class="sxs-lookup"><span data-stu-id="7a2c3-119">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="7a2c3-120">Impedir que la aplicación de comunicación de Office cree procesos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a2c3-120">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="7a2c3-121">Bloquear procesos no habilitados y no firmados que se ejecutan desde USB</span><span class="sxs-lookup"><span data-stu-id="7a2c3-121">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="7a2c3-122">Bloquear la persistencia a través de la suscripción de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="7a2c3-122">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="7a2c3-123">Impedir que las aplicaciones de Office inserten código en otros procesos</span><span class="sxs-lookup"><span data-stu-id="7a2c3-123">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="7a2c3-124">Bloquear la ejecución de los archivos ejecutables a menos que cumplan un criterio de predominio, edad o lista de confianza</span><span class="sxs-lookup"><span data-stu-id="7a2c3-124">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="7a2c3-125">Bloquear creaciones de procesos procedentes de PSExec y comandos WMI</span><span class="sxs-lookup"><span data-stu-id="7a2c3-125">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="7a2c3-126">Bloquear credenciales de robo desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="7a2c3-126">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="7a2c3-127">Bloquear llamadas a la API Win32 desde macros de Office</span><span class="sxs-lookup"><span data-stu-id="7a2c3-127">Block Win32 API calls from Office macros</span></span>
