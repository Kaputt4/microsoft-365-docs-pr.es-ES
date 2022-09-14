---
title: Aumento del cumplimiento de la línea base de seguridad Microsoft Defender para punto de conexión
description: La línea base de seguridad Microsoft Defender para punto de conexión establece controles de seguridad para proporcionar una protección óptima.
keywords: Intune administración, Microsoft Defender para punto de conexión, Microsoft Defender, ASR de Microsoft Defender para punto de conexión, línea base de seguridad
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 462a3df8ca9bdff5e769e2d15d58bab4d36b5e7c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67680227"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a>Aumento del cumplimiento de la línea base de seguridad Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Las líneas base de seguridad garantizan que las características de seguridad se configuran según las instrucciones de expertos en seguridad y administradores expertos del sistema de Windows. Cuando se implementa, la línea base de seguridad de Defender para punto de conexión establece los controles de seguridad de Defender para punto de conexión para proporcionar una protección óptima.

Para comprender las líneas base de seguridad y cómo se asignan en Intune mediante perfiles de configuración, [lea estas preguntas más frecuentes](/intune/security-baselines#q--a).

Para poder implementar y realizar un seguimiento del cumplimiento de las líneas base de seguridad:

- [Inscribir los dispositivos en la administración de Intune](configure-machines.md#enroll-devices-to-intune-management)
- [Asegúrese de que tiene los permisos necesarios.](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a>Comparación de las líneas base de seguridad Microsoft Defender para punto de conexión y windows Intune

La línea de base de seguridad de Windows Intune proporciona un conjunto completo de opciones recomendadas necesarias para configurar de forma segura los dispositivos que ejecutan Windows, incluida la configuración del explorador, la configuración de PowerShell y la configuración de algunas características de seguridad, como el Antivirus de Microsoft Defender. Por el contrario, la línea base de Defender para punto de conexión proporciona una configuración que optimiza todos los controles de seguridad de la pila de Defender para punto de conexión, incluida la configuración para la detección y respuesta de puntos de conexión (EDR), así como la configuración que también se encuentra en la línea base de seguridad de Windows Intune. Para obtener más información sobre cada línea base, consulte:

- [Configuración de línea base de seguridad de Windows para Intune](/intune/security-baseline-settings-windows)
- [Microsoft Defender para punto de conexión configuración de línea base para Intune](/intune/security-baseline-settings-defender-atp)

Lo ideal es que los dispositivos incorporados a Defender para punto de conexión se implementen en ambas líneas base: la línea base de seguridad de Windows Intune para proteger inicialmente Windows y, a continuación, la línea base de seguridad de Defender para punto de conexión superpuesta para configurar de forma óptima los controles de seguridad de Defender para punto de conexión. Para beneficiarse de los datos más recientes sobre riesgos y amenazas y para minimizar los conflictos a medida que evolucionan las líneas base, aplique siempre las versiones más recientes de las líneas base en todos los productos en cuanto se publiquen.

> [!NOTE]
> La línea base de seguridad de Defender para punto de conexión se ha optimizado para dispositivos físicos y actualmente no se recomienda su uso en máquinas virtuales o puntos de conexión de VDI. Ciertas configuraciones de base de referencia pueden afectar a las sesiones interactivas remotas en entornos virtualizados.

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a>Supervisión del cumplimiento de la línea base de seguridad de Defender para punto de conexión

La tarjeta **Base de referencia de seguridad** en [la administración de configuración de dispositivos](configure-machines.md) proporciona información general sobre el cumplimiento entre los dispositivos Windows 10 y Windows 11 a los que se ha asignado la línea base de seguridad de Defender para punto de conexión.

:::image type="content" source="images/secconmgmt_baseline_card.png" alt-text="Tarjeta base de referencia de seguridad" lightbox="images/secconmgmt_baseline_card.png":::

*Tarjeta que muestra el cumplimiento de la línea base de seguridad de Defender para punto de conexión*

A cada dispositivo se le asigna uno de los siguientes tipos de estado:

- **Coincide con la línea base**: la configuración del dispositivo coincide con todas las opciones de la línea base.
- **No coincide con la línea base**: al menos un valor de dispositivo no coincide con la línea base.
- **Mal configurado**: al menos una configuración de línea base no está configurada correctamente en el dispositivo y está en un estado de conflicto, error o pendiente.
- **No aplicable**: al menos una configuración de línea base no es aplicable en el dispositivo.

Para revisar dispositivos específicos, seleccione **Configurar línea base de seguridad** en la tarjeta. Esto le lleva a Intune administración de dispositivos. Desde allí, seleccione **Estado del dispositivo** para los nombres y estados de los dispositivos.

> [!NOTE]
> Es posible que experimente discrepancias en los datos agregados que se muestran en la página de administración de configuración del dispositivo y en las pantallas de información general de Intune.

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a>Revisión y asignación de la línea de base de seguridad Microsoft Defender para punto de conexión

La administración de configuración de dispositivos supervisa el cumplimiento de línea base solo de los dispositivos de Windows 10 y Windows 11 a los que se ha asignado específicamente la línea base de seguridad Microsoft Defender para punto de conexión. Puede revisar convenientemente la línea base y asignarla a los dispositivos en Intune administración de dispositivos.

1. Seleccione **Configurar línea de base de seguridad** en la tarjeta **Base de referencia** de seguridad para ir a Intune administración de dispositivos. Se muestra una introducción similar al cumplimiento de la línea base.

   > [!TIP]
   > Como alternativa, puede navegar a la línea de base de seguridad de Defender para punto de conexión en Microsoft Azure Portal desde **Todos los servicios > Intune > Las líneas base de seguridad > seguridad de dispositivos > línea base de ATP de Microsoft Defender**.

2. Cree un nuevo perfil.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile1.png" alt-text="La pestaña Crear perfil de la línea de base de seguridad de Microsoft Defender para punto de conexión información general sobre Intune" lightbox="images/secconmgmt_baseline_intuneprofile1.png":::<br>
   *Microsoft Defender para punto de conexión información general sobre la línea de base de seguridad en Intune*

3. Durante la creación del perfil, puede revisar y ajustar configuraciones específicas en la línea base.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile2.png" alt-text="Opciones de línea base de seguridad durante la creación del perfil en Intune" lightbox="images/secconmgmt_baseline_intuneprofile2.png":::<br>
   *Opciones de línea base de seguridad durante la creación del perfil en Intune*

4. Asigne el perfil al grupo de dispositivos adecuado.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile3.png" alt-text="Perfiles de línea base de seguridad en Intune" lightbox="images/secconmgmt_baseline_intuneprofile3.png":::<br>
   *Asignación del perfil de línea base de seguridad en Intune*

5. Cree el perfil para guardarlo e implementarlo en el grupo de dispositivos asignado.

   :::image type="content" source="images/secconmgmt_baseline_intuneprofile4.png" alt-text="Asignación de la línea base de seguridad en Intune" lightbox="images/secconmgmt_baseline_intuneprofile4.png":::<br>
   *Creación del perfil de línea base de seguridad en Intune*

> [!TIP]
> Las líneas base de seguridad en Intune proporcionan una manera cómoda de proteger y proteger los dispositivos de forma completa. [Obtenga más información sobre las líneas base de seguridad en Intune](/intune/security-baselines).

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Asegurarse de que los dispositivos estén configurados de manera adecuada](configure-machines.md)
- [Incorporación de dispositivos a Microsoft Defender para punto de conexión](configure-machines-onboarding.md)
- [Optimizar la implementación y las detecciones de reglas de ASR](configure-machines-asr.md)
