---
title: Evaluar protección de red
description: Vea cómo funciona la protección de red probando escenarios comunes contra los que protege.
keywords: Protección de red, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, evaluación, prueba, demostración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ade50e85dbfcf5f59921a65d5b97bb47d21e5b12
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570929"
---
# <a name="evaluate-network-protection"></a>Evaluar protección de red

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

1. Escriba **powershell** en el menú Inicio, haga clic con el botón Windows PowerShell **y** seleccione Ejecutar como **administrador**
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Visitar un dominio malintencionado (falso)

1. Abre Internet Explorer, Google Chrome o cualquier otro explorador de tu elección.

1. Vaya a [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

Se permitirá la conexión de red y se mostrará un mensaje de prueba.

![Notificación de ejemplo que indica Conexión bloqueada: el administrador de TI Seguridad de Windows bloquear esta conexión de red. Póngase en contacto con el servicio de soporte de IT.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Revisar eventos de protección de red en Windows visor de eventos

Para revisar las aplicaciones que se habrían bloqueado, abra el Visor de eventos y filtre el identificador de evento 1125 en el registro de Microsoft-Windows-Windows-Defender/Operational. En la tabla siguiente se enumeran todos los eventos de protección de red.

| Id. de evento | Provide/Source | Descripción |
|-|-|-|
|5007 | Windows Defender (operativo) | Evento cuando se cambia la configuración |
|1125 | Windows Defender (operativo) | Evento cuando se audita una conexión de red |
|1126 | Windows Defender (operativo) | Evento cuando se bloquea una conexión de red |

## <a name="see-also"></a>Consulte también

* [Protección de red](network-protection.md)
* [Habilitar la protección de red](enable-network-protection.md)
* [Solucionar problemas de protección de red](troubleshoot-np.md)
