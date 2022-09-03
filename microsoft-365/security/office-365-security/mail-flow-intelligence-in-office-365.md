---
title: Inteligencia de flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.custom: ''
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Los administradores pueden obtener información sobre los códigos de error asociados a la entrega de mensajes mediante conectores (también conocidos como inteligencia de flujo de correo).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: b83b2011af516359d219061ee88f06c7ac170369
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599008"
---
# <a name="mail-flow-intelligence-in-eop"></a>Inteligencia de flujo de correo en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, normalmente se usa un conector para enrutar mensajes de correo electrónico de EOP al entorno de correo electrónico local. También puede usar un conector para enrutar mensajes de Microsoft 365 a una organización asociada. Cuando Microsoft 365 no puede entregar estos mensajes a través del conector, se ponen en cola en Microsoft 365. Microsoft 365 seguirá reintentar la entrega de cada mensaje durante 24 horas. Después de 24 horas, el mensaje en cola expirará y el mensaje se devolverá al remitente original en un informe de no entrega (también conocido como NDR o mensaje de rebote).

Microsoft 365 genera un error cuando un mensaje no se puede entregar mediante un conector. Los errores más comunes y sus soluciones se describen en este artículo. Colectivamente, los errores de cola y notificación de mensajes no entregados enviados a través de conectores se conocen como _inteligencia de flujo de correo_.

## <a name="error-code-450-44312-dns-query-failed"></a>Código de error: error en la consulta DNS 450 4.4.312

Normalmente, este error significa que Microsoft 365 intentó conectarse al host inteligente especificado en el conector, pero se produjo un error en la consulta DNS para buscar las direcciones IP del host inteligente. Las posibles causas de este error son:

- Hay un problema con el servicio de hospedaje DNS del dominio (la entidad que mantiene los servidores de nombres autoritativos del dominio).

- El dominio ha expirado recientemente, por lo que no se puede recuperar el registro MX.

- El registro MX del dominio ha cambiado recientemente y los servidores DNS todavía tienen información de DNS almacenada previamente en caché para el dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Cómo corregir el código de error 450 4.4.312?

- Trabaje con el servicio de hospedaje DNS para identificar y corregir el problema con el dominio.

- Si el error procede de la organización del asociado (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con el asociado para solucionar el problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Código de error: se agotó el tiempo de espera de la conexión 450 4.4.315

Normalmente, esto significa que Microsoft 365 no puede conectarse al servidor de correo electrónico de destino. Los detalles del error explicarán el problema. Por ejemplo:

- El servidor de correo electrónico local está inactivo.

- Hay un error en la configuración de host inteligente del conector, por lo que Microsoft 365 está intentando conectarse a la dirección IP incorrecta.

### <a name="how-do-i-fix-error-code-450-44315"></a>Cómo corregir el código de error 450 4.4.315?

- Averigüe qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha funcionado correctamente y no ha cambiado la configuración del conector, debe comprobar el entorno de correo electrónico local para ver si el servidor está inactivo o si ha habido cambios en la infraestructura de red (por ejemplo, ha cambiado los proveedores de servicios de Internet, por lo que ahora tiene direcciones IP diferentes).

- Si el error procede de la organización del asociado (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con el asociado para solucionar el problema.

## <a name="error-code-450-44316-connection-refused"></a>Código de error: 450 4.4.316 Conexión denegada

Normalmente, este error significa que Microsoft 365 encontró un error de conexión cuando intentó conectarse al servidor de correo electrónico de destino. Una causa probable de este error es que el firewall está bloqueando las conexiones desde direcciones IP de Microsoft 365. O bien, este error podría ser por diseño si ha migrado completamente el sistema de correo electrónico local a Microsoft 365 y ha cerrado el entorno de correo electrónico local.

### <a name="how-do-i-fix-error-code-450-44316"></a>Cómo corregir el código de error 450 4.4.316?

- Si tiene buzones en el entorno local, debe modificar la configuración del firewall para permitir conexiones desde direcciones IP de Microsoft 365 en el puerto TCP 25 a los servidores de correo electrónico locales. Para obtener una lista de las direcciones IP de Microsoft 365, consulte [Direcciones URL y intervalos de direcciones IP de Microsoft 365](../../enterprise/urls-and-ip-address-ranges.md).

- Si no se deben entregar más mensajes en el entorno local, haga clic en **Corregir ahora** en la alerta para que Microsoft 365 pueda rechazar inmediatamente los mensajes con destinatarios no válidos. Esto reducirá el riesgo de superar la cuota de la organización para los destinatarios no válidos, lo que podría afectar a la entrega normal de mensajes. O bien, puede usar las siguientes instrucciones para corregir manualmente el problema:

  - En el Centro de administración de Exchange, deshabilite o elimine el conector que envía correo electrónico de Microsoft 365 al entorno de correo electrónico local:

    1. En el EAC de <https://admin.exchange.microsoft.com>, vaya a **Conectores** de **flujo** \> de correo. Para ir directamente a la página **Conectores** , use <https://admin.exchange.microsoft.com/#/connectors>.

    2. Seleccione el conector con el valor **De** **Office 365** y el **servidor de correo electrónico** **De valor para** su organización y realice uno de los pasos siguientes:
       - Para eliminar el conector, haga clic en el icono **Eliminar** ![quitar.](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - Para deshabilitar el conector, haga clic en **el icono Editar** ![edición.](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) y borrar **Activarlo**.

  - Cambie el dominio aceptado en Microsoft 365 asociado al entorno de correo electrónico local de **Retransmisión interna** a **Autoritativo**. Para obtener instrucciones, consulte [Administración de dominios aceptados en Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Nota**: Normalmente, estos cambios tardan entre 30 minutos y una hora en surtir efecto. Después de una hora, compruebe que ya no recibe el error.

- Si el error procede de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su asociado para solucionar el problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de error: 450 4.4.317 No se puede conectar al servidor remoto

Normalmente, este error significa que Microsoft 365 está conectado al servidor de correo electrónico de destino, pero el servidor respondió con un error inmediato o no cumple los requisitos de conexión. Los detalles del error explicarán el problema. Por ejemplo:

- El servidor de correo electrónico de destino respondió con un error "Servicio no disponible", que indica que el servidor no puede mantener la comunicación con Microsoft 365.
- El conector está configurado para requerir TLS, pero el servidor de correo electrónico de destino no admite TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Cómo corregir el código de error 450 4.4.317?

- Compruebe la configuración de TLS y los certificados en los servidores de correo electrónico locales y la configuración de TLS en el conector.
- Si el error procede de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su asociado para solucionar el problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de error: 450 4.4.318 Conexión se cerró abruptamente

Normalmente, este error significa que Microsoft 365 tiene dificultades para comunicarse con el entorno de correo electrónico local, por lo que se quitó la conexión. Las posibles causas de este error son:

- El firewall usa reglas de examen de paquetes SMTP y esas reglas no funcionan correctamente.
- El servidor de correo electrónico local no funciona correctamente (por ejemplo, se bloquea el servicio, se bloquea o se reducen los recursos del sistema), lo que hace que el servidor agote el tiempo de espera y cierre la conexión a Microsoft 365.
- Hay problemas de red entre el entorno local y Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Cómo corregir el código de error 450 4.4.318?

- Averigüe qué escenario se aplica a usted y realice las correcciones necesarias.
- Si el problema se debe a problemas de red entre el entorno local y Microsoft 365, póngase en contacto con el equipo de red para solucionar el problema.
- Si el error procede de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su asociado para solucionar el problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de error: error de validación de certificados 450 4.7.320

Normalmente, este error significa que Microsoft 365 encontró un error al intentar validar el certificado del servidor de correo electrónico de destino. Los detalles del error explicarán el error. Por ejemplo:

- Certificado expirado
- Error de coincidencia del firmante del certificado
- El certificado ya no es válido

### <a name="how-do-i-fix-error-code-450-47320"></a>Cómo corregir el código de error 450 4.7.320?

- Corrija el certificado o la configuración del conector para que se puedan entregar los mensajes en cola de Microsoft 365.
- Si el error procede de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su asociado para solucionar el problema.

## <a name="other-error-codes"></a>Otros códigos de error

Microsoft 365 tiene dificultades para entregar mensajes al servidor de correo electrónico local o asociado. Use la información del **servidor de destino** en el error para examinar el problema en el entorno o modifique el conector si hay un error de configuración.

Si el error procede de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su asociado para solucionar el problema.
