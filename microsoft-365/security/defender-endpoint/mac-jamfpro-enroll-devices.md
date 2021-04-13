---
title: Inscribir ATP de Microsoft Defender para dispositivos macOS en Jamf Pro
description: Inscribir ATP de Microsoft Defender para dispositivos macOS en Jamf Pro
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: ea71875dedf7e8706c9022420abd63bc5eb20c69
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689730"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Inscribir Microsoft Defender para endpoint en dispositivos macOS en Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Inscribir dispositivos macOS

Existen varios métodos para inscribirse en JamF.

Este artículo le guiará en dos métodos:

- [Método 1: Invitaciones de inscripción](#enrollment-method-1-enrollment-invitations)
- [Método 2: Inscripción de prestage](#enrollment-method-2-prestage-enrollments)

Para obtener una lista completa, vea [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).


## <a name="enrollment-method-1-enrollment-invitations"></a>Método de inscripción 1: Invitaciones de inscripción

1. En el panel de Jamf Pro, vaya a **Invitaciones de inscripción**.

    ![Imagen de las opciones de configuración1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Seleccione **+ Nuevo**.

    ![Un cierre de un logotipo Description generado automáticamente](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. En **Especificar destinatarios para la lista** de > en Direcciones de correo electrónico, escriba las direcciones de correo electrónico de los destinatarios. 

    ![Imagen de las opciones de configuración2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Imagen de configuración3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Por ejemplo: janedoe@contoso.com

    ![Imagen de las opciones de configuración4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Configure el mensaje de la invitación.

    ![Imagen de configuración5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Imagen de las opciones de configuración6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Imagen de configuración7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Imagen de las opciones de configuración8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Método enrollment 2: Prestage Enrollments

1. En el panel de Jamf Pro, vaya a **Prestage enrollments**.

    ![Imagen de configuración9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Siga las instrucciones de [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).

## <a name="enroll-macos-device"></a>Inscribir dispositivo macOS

1. Seleccione **Continuar** e instale el certificado de ca desde una **ventana preferencias del** sistema.

    ![Imagen de inscripción de Jamf Pro1](images/jamfpro-ca-certificate.png)

2. Una vez instalado el certificado de entidad de certificación, vuelva a la ventana del explorador y seleccione **Continuar** e instale el perfil mdm. 

    ![Imagen de inscripción de Jamf Pro2](images/jamfpro-install-mdm-profile.png)

3. Selecciona **Permitir** descargas desde JAMF.

    ![Imagen de inscripción de Jamf Pro3](images/jamfpro-download.png)

4. Selecciona **Continuar** para continuar con la instalación del perfil MDM. 

    ![Imagen de inscripción de Jamf Pro4](images/jamfpro-install-mdm.png)

5. Selecciona **Continuar** para instalar el perfil mdm.

    ![Imagen de la inscripción de Jamf Pro5](images/jamfpro-mdm-unverified.png)

6. Seleccione **Continuar**  para completar la configuración. 

    ![Imagen de inscripción de Jamf Pro6](images/jamfpro-mdm-profile.png)
