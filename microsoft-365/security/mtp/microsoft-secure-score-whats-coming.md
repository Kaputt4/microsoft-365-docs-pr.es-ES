---
title: Qué llega a la puntuación segura de Microsoft
description: Describe los nuevos cambios que vienen a la puntuación segura de Microsoft en el centro de seguridad de Microsoft 365.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779253"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="92a67-104">Qué llega a la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="92a67-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="92a67-105">Estamos realizando algunos cambios en un futuro próximo para hacer que [Microsoft califique](microsoft-secure-score.md) con seguridad una mejor representativo de su postura de seguridad y mejorar el uso.</span><span class="sxs-lookup"><span data-stu-id="92a67-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="92a67-106">Su puntuación y la puntuación máxima posible pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="92a67-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="92a67-107">Cambios propuestos</span><span class="sxs-lookup"><span data-stu-id="92a67-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="92a67-108">2020 de noviembre</span><span class="sxs-lookup"><span data-stu-id="92a67-108">November 2020</span></span>

<span data-ttu-id="92a67-109">Eliminación de la capacidad de crear vales de ServiceNow a través de la calificación segura yendo a **compartir co> ServiceNow** .</span><span class="sxs-lookup"><span data-stu-id="92a67-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="92a67-110">El período de versión preliminar del conector de ServiceNow está finalizando.</span><span class="sxs-lookup"><span data-stu-id="92a67-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="92a67-111">Esta capacidad ya no estará disponible al final del 2020.</span><span class="sxs-lookup"><span data-stu-id="92a67-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="92a67-112">Gracias por sus comentarios y el soporte técnico continuo mientras determinamos los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="92a67-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="92a67-113">Adición de 18 acciones de mejora relacionadas con Microsoft defender para el punto de conexión (ATP anterior de Microsoft defender):</span><span class="sxs-lookup"><span data-stu-id="92a67-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="92a67-114">Recomendaciones relacionadas con la reducción de superficie de ataques (ASR):</span><span class="sxs-lookup"><span data-stu-id="92a67-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="92a67-115">Bloquear contenido ejecutable del cliente de correo electrónico y Webmail</span><span class="sxs-lookup"><span data-stu-id="92a67-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="92a67-116">Bloquear todas las aplicaciones de Office para crear procesos secundarios</span><span class="sxs-lookup"><span data-stu-id="92a67-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="92a67-117">Impedir que las aplicaciones de Office creen contenido ejecutable</span><span class="sxs-lookup"><span data-stu-id="92a67-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="92a67-118">Impedir que las aplicaciones de Office inserten código en otros procesos</span><span class="sxs-lookup"><span data-stu-id="92a67-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="92a67-119">Impedir que JavaScript o VBScript inicien contenido ejecutable descargado</span><span class="sxs-lookup"><span data-stu-id="92a67-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="92a67-120">Bloquear la ejecución de scripts potencialmente ofuscados</span><span class="sxs-lookup"><span data-stu-id="92a67-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="92a67-121">Bloquear llamadas a la API Win32 desde macros de Office</span><span class="sxs-lookup"><span data-stu-id="92a67-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="92a67-122">Bloquear la ejecución de los archivos ejecutables a menos que cumplan un criterio de predominio, edad o lista de confianza</span><span class="sxs-lookup"><span data-stu-id="92a67-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="92a67-123">Usar protección avanzada contra ransomware</span><span class="sxs-lookup"><span data-stu-id="92a67-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="92a67-124">Bloquear credenciales de robo desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="92a67-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="92a67-125">Bloquear creaciones de procesos procedentes de PSExec y comandos WMI</span><span class="sxs-lookup"><span data-stu-id="92a67-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="92a67-126">Bloquear procesos no habilitados y no firmados que se ejecutan desde USB</span><span class="sxs-lookup"><span data-stu-id="92a67-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="92a67-127">Impedir que la aplicación de comunicación de Office cree procesos secundarios</span><span class="sxs-lookup"><span data-stu-id="92a67-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="92a67-128">Impedir que Adobe Reader cree procesos secundarios</span><span class="sxs-lookup"><span data-stu-id="92a67-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="92a67-129">Bloquear la persistencia a través de la suscripción de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="92a67-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="92a67-130">Recomendaciones relacionadas con los servicios:</span><span class="sxs-lookup"><span data-stu-id="92a67-130">Services related recommendations:</span></span>
- <span data-ttu-id="92a67-131">Corregir la ruta del servicio sin comillas para los servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="92a67-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="92a67-132">Cambiar la ruta de acceso del ejecutable del servicio a una ubicación común protegida</span><span class="sxs-lookup"><span data-stu-id="92a67-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="92a67-133">Cambiar la cuenta de servicio para evitar la contraseña almacenada en caché en el registro de Windows</span><span class="sxs-lookup"><span data-stu-id="92a67-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="92a67-134">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="92a67-134">Related resources</span></span>

- [<span data-ttu-id="92a67-135">Introducción a la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="92a67-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="92a67-136">Evaluar su postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="92a67-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="92a67-137">Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos</span><span class="sxs-lookup"><span data-stu-id="92a67-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="92a67-138">Novedades</span><span class="sxs-lookup"><span data-stu-id="92a67-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
