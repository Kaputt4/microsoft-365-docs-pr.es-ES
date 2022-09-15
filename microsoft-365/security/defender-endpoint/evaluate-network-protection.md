---
title: Evaluar protección de red
description: Vea cómo funciona la protección de red mediante la prueba de escenarios comunes contra los que protege.
keywords: Protección de red, vulnerabilidades de seguridad, sitio web malintencionado, ip, dominio, dominios, evaluación, prueba, demostración
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- M365-security-compliance
ms.date: ''
search.appverid: met150
ms.openlocfilehash: 3206ace163574cdca2cd9131296bab9069bde934
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67695415"
---
# <a name="evaluate-network-protection"></a>Evaluar protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[La protección de red](network-protection.md) ayuda a evitar que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet.

Este artículo le ayuda a evaluar la protección de red habilitando la característica y guiándole a un sitio de prueba. Los sitios de este artículo de evaluación no son malintencionados. Son sitios web especialmente creados que fingen ser malintencionados. El sitio replicará el comportamiento que se produciría si un usuario visitara un sitio o dominio malintencionados.

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
