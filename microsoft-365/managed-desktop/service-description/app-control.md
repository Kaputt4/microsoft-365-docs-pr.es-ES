---
title: Control de aplicaciones
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: e9d33df0ae11d01c8c214fbe0f001a16e8f4908d
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170744"
---
# <a name="app-control"></a><span data-ttu-id="fd67b-103">Control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fd67b-103">App control</span></span>

<span data-ttu-id="fd67b-104">El control de aplicaciones es un procedimiento de seguridad opcional en el escritorio administrado de Microsoft que restringe la ejecución de código en los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="fd67b-104">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="fd67b-105">Este control mitiga el riesgo de los scripts malintencionados o de malware al requerir que solo se pueda ejecutar el código firmado por una lista de publicadores aprobados por el cliente.</span><span class="sxs-lookup"><span data-stu-id="fd67b-105">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="fd67b-106">Hay muchas ventajas de seguridad de este control, pero principalmente se pretende proteger los datos y la identidad de los ataques basados en el cliente.</span><span class="sxs-lookup"><span data-stu-id="fd67b-106">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="fd67b-107">Microsoft Managed Desktop simplifica la administración de las directivas de control de aplicaciones mediante la creación de una directiva de base que permite escenarios de productividad principales.</span><span class="sxs-lookup"><span data-stu-id="fd67b-107">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="fd67b-108">Puede ampliar la confianza a los firmantes adicionales específicos de las aplicaciones y los scripts de su entorno.</span><span class="sxs-lookup"><span data-stu-id="fd67b-108">You can extend trust to additional signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="fd67b-109">Cualquier tecnología de seguridad requiere un equilibrio entre la experiencia del usuario, la seguridad y el costo.</span><span class="sxs-lookup"><span data-stu-id="fd67b-109">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="fd67b-110">El control de aplicaciones reduce la amenaza de software malintencionado en su entorno, pero hay consecuencias para el usuario final y acciones adicionales para el administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="fd67b-110">App control reduces the threat of malicious software in your environment, but there are consequences to the end user and additional actions for your IT administrator.</span></span>

<span data-ttu-id="fd67b-111">**Seguridad adicional:**</span><span class="sxs-lookup"><span data-stu-id="fd67b-111">**Additional security:**</span></span>

<span data-ttu-id="fd67b-112">Las aplicaciones o scripts que no son de confianza para la Directiva de control de la aplicación tienen bloqueado su ejecución en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd67b-112">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="fd67b-113">**Sus responsabilidades adicionales:**</span><span class="sxs-lookup"><span data-stu-id="fd67b-113">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="fd67b-114">Usted es el responsable de probar las aplicaciones para identificar si podrían ser bloqueadas por la Directiva de control de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd67b-114">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="fd67b-115">Si una aplicación está (o estaría) bloqueada, usted es responsable de identificar los detalles del firmante necesarios y solicitar un cambio a través del portal de administración.</span><span class="sxs-lookup"><span data-stu-id="fd67b-115">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="fd67b-116">**Responsabilidades del escritorio administradas de Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="fd67b-116">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="fd67b-117">Microsoft Managed Desktop mantiene la Directiva base que habilita los productos principales de Microsoft, como M365 Apps, Windows, Teams, OneDrive, etc.</span><span class="sxs-lookup"><span data-stu-id="fd67b-117">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="fd67b-118">Microsoft Managed Desktop inserta los firmantes de confianza e implementa la directiva actualizada en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd67b-118">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="fd67b-119">Administrar la confianza en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fd67b-119">Managing trust in applications</span></span>

<span data-ttu-id="fd67b-120">Microsoft Managed Desktop curates una directiva básica que confía en los componentes principales de las tecnologías de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd67b-120">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="fd67b-121">A continuación, puede *Agregar* confianza para sus propias aplicaciones y scripts informando al escritorio administrado de Microsoft en el que ya confía.</span><span class="sxs-lookup"><span data-stu-id="fd67b-121">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="fd67b-122">Directiva de base</span><span class="sxs-lookup"><span data-stu-id="fd67b-122">Base policy</span></span>

<span data-ttu-id="fd67b-123">Microsoft Managed Desktop, en colaboración con expertos de Microsoft Cybersecurity, crea y mantiene una directiva estándar que permite la mayoría de las aplicaciones que se implementan a través de Microsoft Intune y que bloquea actividades peligrosas como la compilación de código o la ejecución de archivos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="fd67b-123">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="fd67b-124">La Directiva base adopta el siguiente enfoque para restringir la ejecución de software:</span><span class="sxs-lookup"><span data-stu-id="fd67b-124">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="fd67b-125">Se permitirá que se ejecuten los archivos ejecutados por los administradores.</span><span class="sxs-lookup"><span data-stu-id="fd67b-125">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="fd67b-126">Se permitirá que se ejecuten los archivos de las ubicaciones que *no* estén en Directorios modificables por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd67b-126">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="fd67b-127">Los archivos están firmados por un [firmante de confianza](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="fd67b-127">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="fd67b-128">La mayoría de los archivos firmados por Microsoft se ejecutarán, pero algunos están bloqueados para evitar acciones de alto riesgo como la compilación de código.</span><span class="sxs-lookup"><span data-stu-id="fd67b-128">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="fd67b-129">Si un usuario que no sea administrador pudiera haber agregado una aplicación o un script a un dispositivo (es decir, en un directorio de escritura de usuario), no permitiría que se ejecutara a menos que un administrador lo haya permitido específicamente.</span><span class="sxs-lookup"><span data-stu-id="fd67b-129">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="fd67b-130">Si se engaña a un usuario para que intente instalar malware, si una vulnerabilidad en una aplicación que el usuario ejecuta intenta instalar malware o si un usuario intenta ejecutar intencionadamente una aplicación o un script no autorizado, la Directiva detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd67b-130">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="fd67b-131">Solicitudes de firmante</span><span class="sxs-lookup"><span data-stu-id="fd67b-131">Signer requests</span></span>

<span data-ttu-id="fd67b-132">Nos informamos sobre qué aplicaciones proporcionan los proveedores de software en los que confía mediante la presentación de una *solicitud de firmante*.</span><span class="sxs-lookup"><span data-stu-id="fd67b-132">You inform us of which apps are provided by software vendors you trust by filing a *signer request*.</span></span> <span data-ttu-id="fd67b-133">Al hacerlo, agregamos esa información de confianza a la Directiva de control de la aplicación de línea de base y permite que cualquier software firmado con el certificado de ese editor se ejecute en sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd67b-133">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="fd67b-134">Directivas de auditoría y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="fd67b-134">Audit and Enforced policies</span></span>

<span data-ttu-id="fd67b-135">Microsoft Managed Desktop usa dos directivas de Microsoft Intune para proporcionar control de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="fd67b-135">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="fd67b-136">Directiva de auditoría</span><span class="sxs-lookup"><span data-stu-id="fd67b-136">Audit policy</span></span>
<span data-ttu-id="fd67b-137">Esta directiva crea registros para registrar si una aplicación o script estaría bloqueado por la Directiva exigida.</span><span class="sxs-lookup"><span data-stu-id="fd67b-137">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="fd67b-138">Las directivas de auditoría no aplican las reglas de control de aplicaciones y tienen como objetivo realizar pruebas para identificar si una aplicación necesitará una exención de Publisher.</span><span class="sxs-lookup"><span data-stu-id="fd67b-138">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="fd67b-139">Registra las advertencias (8003 o 8006 eventos) en el visor de eventos en lugar de bloquear la ejecución o la instalación de las aplicaciones o scripts especificados.</span><span class="sxs-lookup"><span data-stu-id="fd67b-139">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="fd67b-140">Directiva forzada</span><span class="sxs-lookup"><span data-stu-id="fd67b-140">Enforced policy</span></span>
<span data-ttu-id="fd67b-141">Esta directiva impide que se ejecuten aplicaciones y scripts que no sean de confianza y crea registros siempre que se bloquee una aplicación o un script.</span><span class="sxs-lookup"><span data-stu-id="fd67b-141">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="fd67b-142">Las directivas aplicadas impiden que los usuarios estándar ejecuten aplicaciones o scripts almacenados en directorios de escritura del usuario.</span><span class="sxs-lookup"><span data-stu-id="fd67b-142">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="fd67b-143">Se aplica una directiva de auditoría a los dispositivos del grupo de prueba para que pueda usarlos para validar si hay alguna aplicación que causará problemas.</span><span class="sxs-lookup"><span data-stu-id="fd67b-143">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="fd67b-144">Todos los demás grupos (primero, rápido y amplio) usan una directiva obligatoria, por lo que los usuarios finales de esos grupos no podrán ejecutar aplicaciones o scripts que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="fd67b-144">All other groups (First, Fast, and Broad) use an Enforced policy, so end users in those groups won't be able to run untrusted apps or scripts.</span></span>







