---
title: Configuración del período de tiempo de espera del bloque de nube de Microsoft Defender Antivirus
description: Puede configurar cuánto tiempo Microsoft Defender Antivirus bloqueará la ejecución de un archivo mientras espera una determinación de la nube.
keywords: Microsoft Defender Antivirus, antimalware, security, defender, cloud, timeout, block, period, seconds
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.topic: conceptual
ms.date: 10/18/2021
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: cfbad83a62db423eab510dcde5658974bc781005
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68628255"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurar el período de espera de bloqueo en la nube

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Cuando Microsoft Defender Antivirus encuentra un archivo sospechoso, puede impedir que el archivo se ejecute mientras consulta el servicio en la [nube Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).

El período predeterminado en el que se [bloquea](configure-block-at-first-sight-microsoft-defender-antivirus.md) el archivo es de 10 segundos. Si es administrador de seguridad, puede especificar más tiempo de espera antes de que se permita ejecutar el archivo. La ampliación del período de tiempo de espera del bloque de nube puede ayudar a garantizar que haya suficiente tiempo para recibir una determinación adecuada del servicio en la nube Microsoft Defender Antivirus.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Requisitos previos para usar el tiempo de espera extendido del bloque de nube

[Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) y sus requisitos previos deben estar habilitados para poder especificar un período de tiempo de espera extendido.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Especifique el período de tiempo de espera extendido mediante Microsoft Endpoint Manager

Puede especificar el período de tiempo de espera del bloque en la nube con una [directiva de seguridad de punto de conexión en Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).

1. Vaya al centro de administración de Endpoint Manager ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) e inicie sesión.

2. Seleccione **Seguridad del punto de conexión** y, a continuación, en **Administrar**, elija **Antivirus**.

3. Seleccione (o cree) una directiva antivirus.

4. En la sección **Configuración** , expanda **Protección en la nube**. A continuación, en el **cuadro Microsoft Defender Tiempo de espera extendido de Antivirus en segundos**, especifique el tiempo más, en segundos, de 1 segundo a 50 segundos. Cualquier cosa que especifique se agregará al valor predeterminado de 10 segundos.

5. (Este paso es opcional) Realice cualquier otro cambio en la directiva antivirus. (¿Necesita ayuda? Consulte [Configuración de Microsoft Defender directiva antivirus en Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)).

6. Elija **Siguiente** y termine de configurar la directiva.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Especifique el período de tiempo de espera extendido mediante समूह नीति

Puede usar समूह नीति para especificar un tiempo de espera extendido para las comprobaciones en la nube.

1. En el equipo de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón derecho en el objeto समूह नीति que desea configurar y, a continuación, seleccione **Editar**.

3. En el **Editor de administración de समूह नीति**, vaya a **Configuración del equipo** y, a continuación, seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes** \> **de Windows Microsoft Defender Antivirus** \> **MpEngine**.

4. Haga doble clic en **Configurar la comprobación de nube extendida** y asegúrese de que la opción está habilitada. 

   Especifique la cantidad de tiempo adicional para evitar que el archivo se ejecute mientras espera una determinación de la nube. Especifique el tiempo adicional, en segundos, de 1 segundo a 50 segundos. Cualquier cosa que especifique se agregará al valor predeterminado de 10 segundos.

5. Seleccione **Aceptar**.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md) 
