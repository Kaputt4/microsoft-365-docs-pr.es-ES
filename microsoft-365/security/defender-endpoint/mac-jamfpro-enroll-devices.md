---
title: Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro
description: Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalación, implementación, desinstalación, intune, jamfpro, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6189b61826cd56e2a8652032998c3b2df8f980ce
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468685"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Inscribir dispositivos macOS

Existen varios métodos para inscribirse en JamF.

Este artículo le guiará en dos métodos:

- [Método 1: Invitaciones de inscripción](#enrollment-method-1-enrollment-invitations)
- [Método 2: Inscripción de prestage](#enrollment-method-2-prestage-enrollments)

Para obtener una lista completa, consulte [Acerca de la inscripción de equipos](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).

## <a name="enrollment-method-1-enrollment-invitations"></a>Método de inscripción 1: Invitaciones de inscripción

1. En el panel de Pro Jamf, vaya a **Invitaciones de inscripción**.

   :::image type="content" source="images/a347307458d6a9bbfa88df7dbe15398f.png" alt-text="Las opciones de configuración1" lightbox="images/a347307458d6a9bbfa88df7dbe15398f.png":::

2. Seleccione **+ Nuevo**.

   :::image type="content" source="images/b6c7ad56d50f497c38fc14c1e315456c.png" alt-text="El cierre de una descripción del logotipo generado automáticamente" lightbox="images/b6c7ad56d50f497c38fc14c1e315456c.png":::

3. En **Especificar destinatarios para la lista** de > en **Direcciones** de correo electrónico, escriba las direcciones de correo electrónico de los destinatarios.

    :::image type="content" source="images/718b9d609f9f77c8b13ba88c4c0abe5d.png" alt-text="Las opciones de configuración2" lightbox="images/718b9d609f9f77c8b13ba88c4c0abe5d.png":::

    :::image type="content" source="images/ae3597247b6bc7c5347cf56ab1e820c0.png" alt-text="Las opciones de configuración3" lightbox="images/ae3597247b6bc7c5347cf56ab1e820c0.png":::

    Por ejemplo: janedoe@contoso.com

    :::image type="content" source="images/4922c0fcdde4c7f73242b13bf5e35c19.png" alt-text="Las opciones de configuración4" lightbox="images/4922c0fcdde4c7f73242b13bf5e35c19.png":::

4. Configure el mensaje de la invitación.

   :::image type="content" source="images/ce580aec080512d44a37ff8e82e5c2ac.png" alt-text="Configuración5" lightbox="images/ce580aec080512d44a37ff8e82e5c2ac.png":::

   :::image type="content" source="images/5856b765a6ce677caacb130ca36b1a62.png" alt-text="Las opciones de configuración6" lightbox="images/5856b765a6ce677caacb130ca36b1a62.png":::

   :::image type="content" source="images/3ced5383a6be788486d89d407d042f28.png" alt-text="Las opciones de configuración7" lightbox="images/3ced5383a6be788486d89d407d042f28.png":::

   :::image type="content" source="images/54be9c6ed5b24cebe628dc3cd9ca4089.png" alt-text="Las opciones de configuración8" lightbox="images/54be9c6ed5b24cebe628dc3cd9ca4089.png":::

## <a name="enrollment-method-2-prestage-enrollments"></a>Método enrollment 2: Prestage Enrollments

1. En el panel de Pro Jamf, vaya a **Inscripción de prestage**.

   :::image type="content" source="images/6fd0cb2bbb0e60a623829c91fd0826ab.png" alt-text="Las opciones de configuración9" lightbox="images/6fd0cb2bbb0e60a623829c91fd0826ab.png":::

2. Siga las instrucciones de [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).

## <a name="enroll-macos-device"></a>Inscribir dispositivo macOS

1. Seleccione **Continuar** e instale el certificado de ca desde una **ventana preferencias del** sistema.

   :::image type="content" source="images/jamfpro-ca-certificate.png" alt-text="El jamf Pro inscripción1" lightbox="images/jamfpro-ca-certificate.png":::

2. Una vez instalado el certificado de entidad de certificación, vuelva a la ventana del explorador y seleccione **Continuar** e instale el perfil mdm.

   :::image type="content" source="images/jamfpro-install-mdm-profile.png" alt-text="El Jamf Pro enrollment2" lightbox="images/jamfpro-install-mdm-profile.png":::

3. Selecciona **Permitir** descargas desde JAMF.

   :::image type="content" source="images/jamfpro-download.png" alt-text="El Jamf Pro enrollment3" lightbox="images/jamfpro-download.png":::

4. Selecciona **Continuar** para continuar con la instalación del perfil MDM.

   :::image type="content" source="images/jamfpro-install-mdm.png" alt-text="El Jamf Pro enrollment4" lightbox="images/jamfpro-install-mdm.png":::

5. Selecciona **Continuar** para instalar el perfil mdm.

   :::image type="content" source="images/jamfpro-mdm-unverified.png" alt-text="El Jamf Pro enrollment5" lightbox="images/jamfpro-mdm-unverified.png":::

6. Seleccione **Continuar**  para completar la configuración.

   :::image type="content" source="images/jamfpro-mdm-profile.png" alt-text="El jamf Pro inscripción6" lightbox="images/jamfpro-mdm-profile.png":::
