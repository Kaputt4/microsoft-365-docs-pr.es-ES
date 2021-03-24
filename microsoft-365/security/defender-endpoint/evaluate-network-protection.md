---
title: Evaluar la protección de red
description: Vea cómo funciona la protección de red probando escenarios comunes contra los que protege.
keywords: Protección de red, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, evaluación, prueba, demostración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41d1c9400720e20185922a97463e776c3ce0d80a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072232"
---
# <a name="evaluate-network-protection"></a>Evaluar la protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[La protección de](network-protection.md) red ayuda a evitar que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de suplantación de identidad(phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet.

Este artículo le ayuda a evaluar la protección de red habilitando la característica y guiándolo a un sitio de prueba. Los sitios de este artículo de evaluación no son malintencionados. Son sitios web especialmente creados que pretenden ser malintencionados. El sitio replicará el comportamiento que se produciría si un usuario visitase un sitio o dominio malintencionado.

> [!TIP]
> También puedes visitar el sitio web del campo de prueba de Microsoft Defender [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para ver cómo funcionan otras características de protección.

## <a name="enable-network-protection-in-audit-mode"></a>Habilitar la protección de red en modo auditoría

Habilite la protección de red en modo auditoría para ver qué direcciones IP y dominios se habrían bloqueado. Puedes asegurarte de que no afecta a las aplicaciones de línea de negocio u obtener una idea de la frecuencia con la que se producen los bloqueos.

1. Escriba **powershell** en el menú Inicio, haga clic con el Windows PowerShell **y** seleccione Ejecutar como **administrador**
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Visitar un dominio malintencionado (falso)

1. Abre Internet Explorer, Google Chrome o cualquier otro explorador de tu elección.

1. Vaya a [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

Se permitirá la conexión de red y se mostrará un mensaje de prueba.

![Notificación de ejemplo que indica conexión bloqueada: el administrador de TI hizo que Seguridad de Windows bloqueara esta conexión de red. Póngase en contacto con el servicio de soporte de IT.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisar eventos de protección de red en el Visor de eventos de Windows

Para revisar las aplicaciones que se habrían bloqueado, abra el Visor de eventos y filtre el identificador de evento 1125 en el registro operativo/Microsoft-Windows-Windows-Defender. En la tabla siguiente se enumeran todos los eventos de protección de red.

| Id. de evento | Provide/Source | Descripción |
|-|-|-|
|5007 | Windows Defender (operativo) | Evento cuando se cambia la configuración |
|1125 | Windows Defender (operativo) | Evento cuando se audita una conexión de red |
|1126 | Windows Defender (operativo) | Evento cuando se bloquea una conexión de red |

## <a name="see-also"></a>Ver también

* [Protección de red](network-protection.md)
* [Habilitar la protección de red](enable-network-protection.md)
* [Solucionar problemas de protección de red](troubleshoot-np.md)
