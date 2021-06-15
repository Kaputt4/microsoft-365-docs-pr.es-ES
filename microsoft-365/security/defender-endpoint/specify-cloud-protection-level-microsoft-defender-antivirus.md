---
title: Especifique el nivel de protección entregado en la nube para Antivirus de Microsoft Defender
description: Establezca el nivel de protección entregada en la nube para Antivirus de Microsoft Defender.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defensa, nube, agresividad, nivel de protección
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: fb4dd3114c411385f1a38cf7b0fd391a1b159b99
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924476"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Especificar el nivel de protección proporcionado en la nube

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede especificar el nivel de protección de entrega en la nube que ofrece Antivirus de Microsoft Defender mediante Microsoft Endpoint Manager (recomendado) o directiva de grupo.

> [!TIP]
> La protección en la nube no es simplemente protección para los archivos almacenados en la nube. El Antivirus de Microsoft Defender en la nube es un mecanismo para ofrecer protección actualizada a la red y los dispositivos (también denominados puntos de conexión). La protección en la nube con Antivirus de Microsoft Defender recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales. Microsoft Intune y Microsoft Endpoint Manager ahora forman parte de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Use Microsoft Endpoint Manager para especificar el nivel de protección entregada en la nube

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Elija **Endpoint security**  >  **Antivirus**.

3. Seleccione un perfil antivirus. (Si aún no tienes uno, o si quieres crear un perfil nuevo, consulta Configurar la configuración de restricción de [dispositivos en Microsoft Intune](/intune/device-restrictions-configure).

4. Seleccione **Propiedades**. A continuación, junto **a Configuración,** elija **Editar**.

5. Expanda **Protección en la** nube y, a continuación, en la lista Nivel de protección entregado en **la** nube, seleccione una de las siguientes opciones:

    1. **High:** aplica un nivel de detección fuerte.
    2. **High plus:** usa el **nivel alto** y aplica medidas de protección adicionales (puede afectar al rendimiento del cliente).
    3. **Tolerancia cero:** bloquea todos los ejecutables desconocidos.

6. Elija **Revisar + guardar** y, a continuación, elija **Guardar**. 

> [!TIP]
> ¿Necesita ayuda? Vea los siguientes recursos:
> - [Configurar Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Agregar configuración de protección de puntos de conexión en Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Usar la directiva de grupo para especificar el nivel de protección entregada en la nube

1.  En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.

3.  En el **Editor de administración de directivas de grupo** vaya a **Configuración** del equipo  >  **Plantillas administrativas.**

4.  Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **MpEngine**.

5.  Haga doble clic en la **configuración Seleccionar nivel de** protección en la nube y estabóla en **Habilitado**. Seleccione el nivel de protección:
    - **El nivel de bloqueo predeterminado** proporciona una detección segura sin aumentar el riesgo de detectar archivos legítimos.
    - **El nivel de bloqueo moderado** proporciona moderación solo para detecciones de elevada confianza
    - **El nivel alto de bloqueo** aplica un alto nivel de detección a la vez que optimiza el rendimiento del cliente (pero también puede ofrecer una mayor probabilidad de falsos positivos).
    - **Alto + nivel de bloqueo** aplica medidas de protección adicionales (puede afectar al rendimiento del cliente y aumentar la probabilidad de falsos positivos).
    - **El nivel de bloqueo de tolerancia cero** bloquea todos los ejecutables desconocidos.
    
    > [!WARNING]
    > Aunque es poco probable, establecer este cambio en **High** o **High +** puede provocar que se detecten algunos archivos legítimos (aunque tendrá la opción de desbloquear o disputar esa detección).

6. Haga clic en **Aceptar**.

7. Implemente el objeto de directiva de grupo actualizado. Consulta [Consola de administración de directivas de grupo](/windows/win32/srvnodes/group-policy)

> [!TIP]
> ¿Usa objetos de directiva de grupo local? Vea cómo se traducen en la nube. [Analice los objetos de directiva de grupo locales mediante el análisis](/mem/intune/configuration/group-policy-analytics)de directivas de grupo en Microsoft Endpoint Manager - Vista previa . 
  
## <a name="related-articles"></a>Artículos relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Cómo crear e implementar directivas antimalware: Servicio de protección en la nube](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)