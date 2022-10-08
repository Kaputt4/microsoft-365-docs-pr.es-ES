---
title: Inscribir Microsoft Defender para punto de conexión en dispositivos macOS en Jamf Pro
description: Inscribir Microsoft Defender para punto de conexión en dispositivos macOS en Jamf Pro
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: c4e10dc812b90d9e2eb025855617787cbf685957
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68225424"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Inscribir Microsoft Defender para punto de conexión en dispositivos macOS en Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Inscripción de dispositivos macOS

Hay varios métodos para inscribirse en JamF.

Este artículo le guiará sobre dos métodos:

- [Método 1: Invitaciones de inscripción](#enrollment-method-1-enrollment-invitations)
- [Método 2: Preconfigurar inscripciones](#enrollment-method-2-prestage-enrollments)

Para obtener una lista completa, consulte [Acerca de la inscripción de equipos](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).

## <a name="enrollment-method-1-enrollment-invitations"></a>Método de inscripción 1: invitaciones de inscripción

1. En el panel de Jamf Pro, vaya a **Invitaciones de inscripción**.

   :::image type="content" source="images/a347307458d6a9bbfa88df7dbe15398f.png" alt-text="Los valores de configuración1" lightbox="images/a347307458d6a9bbfa88df7dbe15398f.png":::

2. Seleccione **+ Nuevo**.

   :::image type="content" source="images/b6c7ad56d50f497c38fc14c1e315456c.png" alt-text="El primer plano de una descripción del logotipo generado automáticamente" lightbox="images/b6c7ad56d50f497c38fc14c1e315456c.png":::

3. En **Especificar destinatarios para el > de invitación** en **Direcciones de Email escriba las direcciones** de correo electrónico de los destinatarios.

    :::image type="content" source="images/718b9d609f9f77c8b13ba88c4c0abe5d.png" alt-text="Los valores de configuración2" lightbox="images/718b9d609f9f77c8b13ba88c4c0abe5d.png":::

    :::image type="content" source="images/ae3597247b6bc7c5347cf56ab1e820c0.png" alt-text="La configuración de configuración3" lightbox="images/ae3597247b6bc7c5347cf56ab1e820c0.png":::

    Por ejemplo: janedoe@contoso.com

    :::image type="content" source="images/4922c0fcdde4c7f73242b13bf5e35c19.png" alt-text="Los valores de configuración4" lightbox="images/4922c0fcdde4c7f73242b13bf5e35c19.png":::

4. Configure el mensaje para la invitación.

   :::image type="content" source="images/ce580aec080512d44a37ff8e82e5c2ac.png" alt-text="La configuración5" lightbox="images/ce580aec080512d44a37ff8e82e5c2ac.png":::

   :::image type="content" source="images/5856b765a6ce677caacb130ca36b1a62.png" alt-text="Los valores de configuración6" lightbox="images/5856b765a6ce677caacb130ca36b1a62.png":::

   :::image type="content" source="images/3ced5383a6be788486d89d407d042f28.png" alt-text="Los valores de configuración7" lightbox="images/3ced5383a6be788486d89d407d042f28.png":::

   :::image type="content" source="images/54be9c6ed5b24cebe628dc3cd9ca4089.png" alt-text="La configuración8" lightbox="images/54be9c6ed5b24cebe628dc3cd9ca4089.png":::

## <a name="enrollment-method-2-prestage-enrollments"></a>Método de inscripción 2: Preconfigurar inscripciones

1. En el panel de Jamf Pro, vaya a **Preconfigurar inscripciones**.

   :::image type="content" source="images/6fd0cb2bbb0e60a623829c91fd0826ab.png" alt-text="Los valores de configuración9" lightbox="images/6fd0cb2bbb0e60a623829c91fd0826ab.png":::

2. Siga las instrucciones de [Inscripción](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html) previa del equipo.

## <a name="enroll-macos-device"></a>Inscripción de un dispositivo macOS

1. Seleccione **Continuar** e instale el certificado de CA desde una ventana **Preferencias del sistema** .

   :::image type="content" source="images/jamfpro-ca-certificate.png" alt-text="Inscripción de Jamf Pro1" lightbox="images/jamfpro-ca-certificate.png":::

2. Una vez instalado el certificado de CA, vuelva a la ventana del explorador y seleccione **Continuar** e instale el perfil de MDM.

   :::image type="content" source="images/jamfpro-install-mdm-profile.png" alt-text="Inscripción de Jamf Pro2" lightbox="images/jamfpro-install-mdm-profile.png":::

3. Seleccione **Permitir** descargas desde JAMF.

   :::image type="content" source="images/jamfpro-download.png" alt-text="Inscripción de Jamf Pro3" lightbox="images/jamfpro-download.png":::

4. Seleccione **Continuar** para continuar con la instalación del perfil mdm.

   :::image type="content" source="images/jamfpro-install-mdm.png" alt-text="Inscripción de Jamf Pro4" lightbox="images/jamfpro-install-mdm.png":::

5. Seleccione **Continuar** para instalar el perfil de MDM.

   :::image type="content" source="images/jamfpro-mdm-unverified.png" alt-text="Inscripción de Jamf Pro5" lightbox="images/jamfpro-mdm-unverified.png":::

6. Seleccione **Continuar**  para completar la configuración.

   :::image type="content" source="images/jamfpro-mdm-profile.png" alt-text="Inscripción de Jamf Pro6" lightbox="images/jamfpro-mdm-profile.png":::
