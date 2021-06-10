---
title: Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro
description: Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalación, implementación, desinstalación, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933102"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="a1b33-104">Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="a1b33-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1b33-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a1b33-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1b33-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a1b33-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a1b33-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1b33-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a1b33-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a1b33-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a1b33-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a1b33-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="a1b33-110">Inscribir dispositivos macOS</span><span class="sxs-lookup"><span data-stu-id="a1b33-110">Enroll macOS devices</span></span>

<span data-ttu-id="a1b33-111">Existen varios métodos para inscribirse en JamF.</span><span class="sxs-lookup"><span data-stu-id="a1b33-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="a1b33-112">Este artículo le guiará en dos métodos:</span><span class="sxs-lookup"><span data-stu-id="a1b33-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="a1b33-113">Método 1: Invitaciones de inscripción</span><span class="sxs-lookup"><span data-stu-id="a1b33-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="a1b33-114">Método 2: Inscripción de prestage</span><span class="sxs-lookup"><span data-stu-id="a1b33-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="a1b33-115">Para obtener una lista completa, vea [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span><span class="sxs-lookup"><span data-stu-id="a1b33-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="a1b33-116">Método de inscripción 1: Invitaciones de inscripción</span><span class="sxs-lookup"><span data-stu-id="a1b33-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="a1b33-117">En el panel de Pro Jamf, vaya a **Invitaciones de inscripción**.</span><span class="sxs-lookup"><span data-stu-id="a1b33-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Imagen de las opciones de configuración1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="a1b33-119">Seleccione **+ Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a1b33-119">Select **+ New**.</span></span>

    ![Un cierre de un logotipo Description generado automáticamente](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="a1b33-121">En **Especificar destinatarios para la lista** de > en Direcciones de correo electrónico, escriba las direcciones de correo electrónico de los destinatarios. </span><span class="sxs-lookup"><span data-stu-id="a1b33-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Imagen de las opciones de configuración2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Imagen de configuración3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="a1b33-124">Por ejemplo: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a1b33-124">For example: janedoe@contoso.com</span></span>

    ![Imagen de las opciones de configuración4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="a1b33-126">Configure el mensaje de la invitación.</span><span class="sxs-lookup"><span data-stu-id="a1b33-126">Configure the message for the invitation.</span></span>

    ![Imagen de configuración5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Imagen de las opciones de configuración6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Imagen de configuración7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Imagen de las opciones de configuración8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="a1b33-131">Método enrollment 2: Prestage Enrollments</span><span class="sxs-lookup"><span data-stu-id="a1b33-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="a1b33-132">En el panel de Pro Jamf, vaya a **Prestage enrollments**.</span><span class="sxs-lookup"><span data-stu-id="a1b33-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Imagen de configuración9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="a1b33-134">Siga las instrucciones de [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span><span class="sxs-lookup"><span data-stu-id="a1b33-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="a1b33-135">Inscribir dispositivo macOS</span><span class="sxs-lookup"><span data-stu-id="a1b33-135">Enroll macOS device</span></span>

1. <span data-ttu-id="a1b33-136">Seleccione **Continuar** e instale el certificado de ca desde una **ventana preferencias del** sistema.</span><span class="sxs-lookup"><span data-stu-id="a1b33-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Imagen de Jamf Pro enrollment1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="a1b33-138">Una vez instalado el certificado de entidad de certificación, vuelva a la ventana del explorador y seleccione **Continuar** e instale el perfil mdm.</span><span class="sxs-lookup"><span data-stu-id="a1b33-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Imagen de Jamf Pro enrollment2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="a1b33-140">Selecciona **Permitir** descargas desde JAMF.</span><span class="sxs-lookup"><span data-stu-id="a1b33-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Imagen de Jamf Pro enrollment3](images/jamfpro-download.png)

4. <span data-ttu-id="a1b33-142">Selecciona **Continuar** para continuar con la instalación del perfil MDM.</span><span class="sxs-lookup"><span data-stu-id="a1b33-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Imagen de Jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="a1b33-144">Selecciona **Continuar** para instalar el perfil mdm.</span><span class="sxs-lookup"><span data-stu-id="a1b33-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Imagen de Jamf Pro enrollment5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="a1b33-146">Seleccione **Continuar**  para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a1b33-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Imagen de Jamf Pro enrollment6](images/jamfpro-mdm-profile.png)
