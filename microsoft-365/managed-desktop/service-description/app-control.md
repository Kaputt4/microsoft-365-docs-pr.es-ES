---
title: Control de aplicaciones
description: Cómo usar el control de aplicaciones y la confianza con las aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841308"
---
# <a name="app-control"></a><span data-ttu-id="fc260-104">Control de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fc260-104">App control</span></span>

<span data-ttu-id="fc260-105">El control de aplicaciones es una práctica de seguridad opcional en el Escritorio administrado de Microsoft que restringe la ejecución de código en dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="fc260-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="fc260-106">Este control mitiga el riesgo de malware o scripts malintencionados al requerir que solo se pueda ejecutar el código firmado por una lista de editores aprobada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="fc260-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="fc260-107">Este control ofrece muchas ventajas de seguridad, pero principalmente tiene como objetivo proteger los datos y la identidad de las vulnerabilidades de seguridad basadas en el cliente.</span><span class="sxs-lookup"><span data-stu-id="fc260-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="fc260-108">Escritorio administrado de Microsoft simplifica la administración de directivas de control de aplicaciones mediante la creación de una directiva base que permite escenarios de productividad principales.</span><span class="sxs-lookup"><span data-stu-id="fc260-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="fc260-109">Puedes ampliar la confianza a otros firmantes que son específicos de las aplicaciones y scripts de tu entorno.</span><span class="sxs-lookup"><span data-stu-id="fc260-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="fc260-110">Cualquier tecnología de seguridad requiere un equilibrio entre la experiencia del usuario, la seguridad y el costo.</span><span class="sxs-lookup"><span data-stu-id="fc260-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="fc260-111">El control de aplicaciones reduce la amenaza de software malintencionado en su entorno, pero hay consecuencias para el usuario y otras acciones para el administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="fc260-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="fc260-112">**Seguridad adicional:**</span><span class="sxs-lookup"><span data-stu-id="fc260-112">**Additional security:**</span></span>

<span data-ttu-id="fc260-113">Las aplicaciones o scripts que no son de confianza para la directiva de control de aplicaciones están bloqueadas para que no se ejecuten en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fc260-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="fc260-114">**Sus responsabilidades adicionales:**</span><span class="sxs-lookup"><span data-stu-id="fc260-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="fc260-115">Eres responsable de probar las aplicaciones para identificar si la directiva de control de aplicaciones las bloquearía.</span><span class="sxs-lookup"><span data-stu-id="fc260-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="fc260-116">Si una aplicación está (o estaría) bloqueada, eres responsable de identificar los detalles de firmante necesarios y de solicitar un cambio a través del portal de administración.</span><span class="sxs-lookup"><span data-stu-id="fc260-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="fc260-117">**Responsabilidades de Escritorio administrado de Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="fc260-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="fc260-118">Escritorio administrado de Microsoft mantiene la directiva base que habilita los productos principales de Microsoft, como Aplicaciones de M365, Windows, Teams, OneDrive, entre otros.</span><span class="sxs-lookup"><span data-stu-id="fc260-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="fc260-119">Escritorio administrado de Microsoft inserta los firmantes de confianza e implementa la directiva actualizada en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fc260-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="fc260-120">Administración de la confianza en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fc260-120">Managing trust in applications</span></span>

<span data-ttu-id="fc260-121">Escritorio administrado de Microsoft administra una directiva base que confía en los componentes principales de las tecnologías de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc260-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="fc260-122">A *continuación,* agregue confianza para sus propias aplicaciones y scripts informando a Escritorio administrado de Microsoft de cuáles ya confía.</span><span class="sxs-lookup"><span data-stu-id="fc260-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="fc260-123">Directiva base</span><span class="sxs-lookup"><span data-stu-id="fc260-123">Base policy</span></span>

<span data-ttu-id="fc260-124">Escritorio administrado de Microsoft, en colaboración con expertos en ciberseguridad de Microsoft, crea y mantiene una directiva estándar que habilita la mayoría de las aplicaciones implementadas a través de Microsoft Intune, al tiempo que bloquea actividades peligrosas como la compilación de código o la ejecución de archivos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="fc260-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="fc260-125">La directiva base adopta el siguiente enfoque para restringir la ejecución de software:</span><span class="sxs-lookup"><span data-stu-id="fc260-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="fc260-126">Los archivos ejecutados por los administradores podrán ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="fc260-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="fc260-127">Se permitirá la  ejecución de archivos en ubicaciones que no estén en directorios modificables por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fc260-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="fc260-128">Los archivos están firmados por un [firmante de confianza.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="fc260-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="fc260-129">La mayoría de los archivos firmados por Microsoft se ejecutarán, pero algunos se bloquean para evitar acciones de alto riesgo, como la compilación de código.</span><span class="sxs-lookup"><span data-stu-id="fc260-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="fc260-130">Si un usuario que no es un administrador puede haber agregado una aplicación o un script a un dispositivo (es decir, está en un directorio que se puede escribir por el usuario), no lo permitiremos para que se ejecute a menos que ya lo haya permitido específicamente un administrador.</span><span class="sxs-lookup"><span data-stu-id="fc260-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="fc260-131">Si se engañará a un usuario para que intente instalar malware, si una vulnerabilidad de una aplicación ejecuta intentos de instalar malware, o si un usuario intenta ejecutar intencionalmente una aplicación o un script no autorizados, nuestra directiva detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fc260-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="fc260-132">Solicitudes del firmante</span><span class="sxs-lookup"><span data-stu-id="fc260-132">Signer requests</span></span>

<span data-ttu-id="fc260-133">Para informarnos de las aplicaciones que proporcionan los editores de software de confianza, presenta una solicitud *de firmante.*</span><span class="sxs-lookup"><span data-stu-id="fc260-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="fc260-134">Al hacerlo, agregamos esa información de confianza a la directiva de control de aplicaciones de línea base y permitimos que cualquier software firmado con el certificado de ese editor se ejecute en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fc260-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="fc260-135">Auditoría y directivas aplicadas</span><span class="sxs-lookup"><span data-stu-id="fc260-135">Audit and Enforced policies</span></span>

<span data-ttu-id="fc260-136">Escritorio administrado de Microsoft usa dos directivas de Microsoft Intune para proporcionar control de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="fc260-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="fc260-137">Directiva de auditoría</span><span class="sxs-lookup"><span data-stu-id="fc260-137">Audit policy</span></span>
<span data-ttu-id="fc260-138">Esta directiva crea registros para registrar si la directiva aplicada bloquearía una aplicación o un script.</span><span class="sxs-lookup"><span data-stu-id="fc260-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="fc260-139">Las directivas de auditoría no aplican reglas de control de aplicaciones y están pensadas para realizar pruebas con el fin de identificar si una aplicación requerirá una exención de editor.</span><span class="sxs-lookup"><span data-stu-id="fc260-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="fc260-140">Registra advertencias (eventos 8003 u 8006) en el Visor de eventos en lugar de bloquear la ejecución o instalación de aplicaciones o scripts especificados.</span><span class="sxs-lookup"><span data-stu-id="fc260-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="fc260-141">Directiva aplicada</span><span class="sxs-lookup"><span data-stu-id="fc260-141">Enforced policy</span></span>
<span data-ttu-id="fc260-142">Esta directiva bloquea la ejecución de aplicaciones y scripts que no son de confianza y crea registros cada vez que se bloquea una aplicación o un script.</span><span class="sxs-lookup"><span data-stu-id="fc260-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="fc260-143">Las directivas aplicadas impiden que los usuarios estándar ejecuten aplicaciones o scripts almacenados en directorios que se pueden escribir por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fc260-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="fc260-144">Los dispositivos del grupo De prueba tienen aplicada una directiva de auditoría para que puedas usarlos para validar si alguna aplicación causará problemas.</span><span class="sxs-lookup"><span data-stu-id="fc260-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="fc260-145">Todos los demás grupos (First, Fast y Broad) usan una directiva aplicada, por lo que los usuarios de esos grupos no podrán ejecutar aplicaciones o scripts que no sean de confianza.</span><span class="sxs-lookup"><span data-stu-id="fc260-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







