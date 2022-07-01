---
title: Evaluar protección de red
description: Vea cómo funciona la protección de red mediante la prueba de escenarios comunes contra los que protege.
keywords: Protección de red, vulnerabilidades de seguridad, sitio web malintencionado, ip, dominio, dominios, evaluación, prueba, demostración
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection:
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: 2826c623437760d86aad54e4aa36900bdad68082
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66603954"
---
# <a name="evaluate-network-protection"></a>Evaluar protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[La protección de red](network-protection.md) ayuda a evitar que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet.

Este artículo le ayuda a evaluar la protección de red habilitando la característica y guiándole a un sitio de prueba. Los sitios de este artículo de evaluación no son malintencionados. Son sitios web especialmente creados que fingen ser malintencionados. El sitio replicará el comportamiento que se produciría si un usuario visitara un sitio o dominio malintencionados.

> [!TIP]
> También puede visitar el sitio web de escenarios de demostración de Microsoft Defender en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funcionan otras características de protección.

> [!NOTE]
> El sitio de demostración de Defender para punto de conexión en demo.wd.microsoft.com está en desuso y se eliminará en el futuro.

## <a name="enable-network-protection-in-audit-mode"></a>Habilitación de la protección de red en modo de auditoría

Habilite la protección de red en modo de auditoría para ver qué direcciones IP y dominios se habrían bloqueado. Puede asegurarse de que no afecte a las aplicaciones de línea de negocio o hacerse una idea de la frecuencia con la que se producen los bloques.

1. Escriba **powershell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Visita de un dominio malintencionado (falso)

1. Abra Internet Explorer, Google Chrome o cualquier otro navegador que prefiera.

2. Vaya a [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

    Se permitirá la conexión de red y se mostrará un mensaje de prueba.
    
    :::image type="content" source="images/np-notif.png" alt-text="Notificación de bloqueo de conexión" lightbox="images/np-notif.png":::

> [!NOTE]
> Las conexiones de red pueden ser correctas aunque la protección de red bloquee un sitio. Para más información, consulte [Protección de red y protocolo de enlace triple TCP](network-protection.md#network-protection-and-the-tcp-three-way-handshake).

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revise los eventos de protección de red en Windows Visor de eventos

Para revisar las aplicaciones que se habrían bloqueado, abra Visor de eventos y filtre por el identificador de evento 1125 en el registro Microsoft-Windows-Windows Defender/Operational. En la tabla siguiente se enumeran todos los eventos de protección de red.

| Id. de evento | Proporcionar o origen | Descripción |
|---|---|---|
| 5007 | Windows Defender (operativo) | Evento cuando se cambia la configuración |
| 1125 | Windows Defender (operativo) | Evento cuando se audita una conexión de red |
| 1126 | Windows Defender (operativo) | Evento cuando se bloquea una conexión de red |

## <a name="see-also"></a>Vea también

- [Protección de red](network-protection.md)

- [Protección de red y protocolo de enlace de tres vías TCP](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [Habilitación de la protección de red](enable-network-protection.md)

- [Solución de problemas de protección de red](troubleshoot-np.md)
