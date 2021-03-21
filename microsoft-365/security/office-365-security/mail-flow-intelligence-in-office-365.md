---
title: Inteligencia de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Los administradores pueden obtener información sobre los códigos de error asociados con la entrega de mensajes mediante conectores (también conocidos como inteligencia de flujo de correo).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f9cd05664d055b1635583c24000ca4afa604b237
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926873"
---
# <a name="mail-flow-intelligence-in-eop"></a>Inteligencia de flujo de correo en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, normalmente se usa un conector para enrutar mensajes de correo electrónico de EOP a su entorno de correo electrónico local. También puede usar un conector para enrutar mensajes de Microsoft 365 a una organización asociada. Cuando Microsoft 365 no puede entregar estos mensajes a través del conector, se ponen en cola en Microsoft 365. Microsoft 365 seguirá reintentiendo la entrega de cada mensaje durante 24 horas. Después de 24 horas, el mensaje en cola expirará y el mensaje se devolverá al remitente original en un informe de no entrega (también conocido como NDR o mensaje de devolución).

Microsoft 365 genera un error cuando no se puede entregar un mensaje mediante un conector. Los errores más comunes y sus soluciones se describen en este artículo. Colectivamente, los errores de cola y notificación de mensajes no entregados enviados a través de conectores se conocen como inteligencia de _flujo de correo_.

## <a name="error-code-450-44312-dns-query-failed"></a>Código de error: error en la consulta DNS 4.4.312

Normalmente, este error significa que Microsoft 365 intentó conectarse al host inteligente especificado en el conector, pero la consulta DNS para encontrar las direcciones IP del host inteligente produjo un error. Las causas posibles de este error son:

- Hay un problema con el servicio de hospedaje DNS de su dominio (la parte que mantiene los servidores de nombres autoritativo para su dominio).

- El dominio ha expirado recientemente, por lo que no se puede recuperar el registro MX.

- El registro MX del dominio ha cambiado recientemente y los servidores DNS aún tienen información de DNS almacenada previamente en caché para el dominio.

### <a name="how-do-i-fix-error-code-450-44312"></a>¿Cómo se corrige el código de error 450 4.4.312?

- Trabaje con el servicio de hospedaje DNS para identificar y solucionar el problema con su dominio.

- Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Código de error: 450 4.4.315 Tiempo de espera de conexión

Normalmente, esto significa que Microsoft 365 no puede conectarse al servidor de correo electrónico de destino. Los detalles del error explicarán el problema. Por ejemplo:

- El servidor de correo electrónico local no está disponible.

- Hay un error en la configuración de host inteligente del conector, por lo que Microsoft 365 está intentando conectarse a la dirección IP incorrecta.

### <a name="how-do-i-fix-error-code-450-44315"></a>¿Cómo se corrige el código de error 450 4.4.315?

- Descubra qué escenario se aplica a usted y realice las correcciones necesarias. Por ejemplo, si el flujo de correo ha funcionado correctamente y no ha cambiado la configuración del conector, debe comprobar el entorno de correo electrónico local para ver si el servidor está abajo o si ha habido cambios en la infraestructura de red (por ejemplo, ha cambiado los proveedores de servicios de Internet, por lo que ahora tiene diferentes direcciones IP).

- Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), póngase en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44316-connection-refused"></a>Código de error: 450 4.4.316 Conexión rechazada

Normalmente, este error significa que Microsoft 365 encontró un error de conexión cuando intentó conectarse al servidor de correo electrónico de destino. Una causa probable de este error es que el firewall bloquea las conexiones de direcciones IP de Microsoft 365. O bien, este error puede deberse al diseño si ha migrado completamente el sistema de correo electrónico local a Microsoft 365 y ha apagado el entorno de correo electrónico local.

### <a name="how-do-i-fix-error-code-450-44316"></a>¿Cómo se corrige el código de error 450 4.4.316?

- Si tiene buzones en el entorno local, debe modificar la configuración del firewall para permitir conexiones de direcciones IP de Microsoft 365 en el puerto TCP 25 a los servidores de correo electrónico locales. Para obtener una lista de las direcciones IP de Microsoft 365, vea Direcciones URL e [intervalos de direcciones IP de Microsoft 365](../../enterprise/urls-and-ip-address-ranges.md).

- Si no se deben entregar más mensajes en  el entorno local, haga clic en Corregir ahora en la alerta para que Microsoft 365 pueda rechazar inmediatamente los mensajes con destinatarios no válidos. Esto reducirá el riesgo de exceder la cuota de la organización para destinatarios no válidos, lo que podría afectar a la entrega normal de mensajes. O bien, puede usar las siguientes instrucciones para solucionar manualmente el problema:

  - En el [Centro de administración de Exchange (EAC),](/Exchange/exchange-admin-center)deshabilite o elimine el conector que entrega correo electrónico de Microsoft 365 a su entorno de correo electrónico local:

    1. En el EAC, vaya a **Flujo de correo** \> **Conectores**.

    2. Seleccione el conector con el valor **De** de  **Office 365** y el valor **Para** del servidor de correo electrónico de su organización y siga uno de los pasos siguientes:

       - Para eliminar el conector, haga clic **en Eliminar** ![ icono Quitar](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Para deshabilitar el conector, **haga clic en Editar** icono editar y desactive ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **Activar**.

  - Cambie el dominio aceptado en Microsoft 365 asociado al entorno de correo electrónico local de **Retransmisión interna** a **Autoritativo.** Para obtener instrucciones, vea [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Nota:** Estos cambios suelen tardar entre 30 minutos y una hora en tener efecto. Después de una hora, compruebe que ya no recibe el error.

- Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de error: 450 4.4.317 No se puede conectar al servidor remoto

Normalmente, este error significa Microsoft 365 conectado al servidor de correo electrónico de destino, pero el servidor respondió con un error inmediato o no cumple los requisitos de conexión. Los detalles del error explicarán el problema. Por ejemplo:

- El servidor de correo electrónico de destino respondió con un error "Servicio no disponible", que indica que el servidor no puede mantener la comunicación con Microsoft 365.

- El conector está configurado para requerir TLS, pero el servidor de correo electrónico de destino no admite TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>¿Cómo se corrige el código de error 450 4.4.317?

- Compruebe la configuración de TLS y los certificados en los servidores de correo electrónico locales y la configuración de TLS en el conector.

- Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de error: 450 4.4.318 Connection se cerró abruptamente

Normalmente, este error significa que Microsoft 365 tiene dificultades para comunicarse con el entorno de correo electrónico local, por lo que se ha descartado la conexión. Las causas posibles de este error son:

- El firewall usa reglas de examen de paquete SMTP y esas reglas no funcionan correctamente.

- El servidor de correo electrónico local no funciona correctamente (por ejemplo, el servicio se bloquea, se bloquea o tiene pocos recursos del sistema), lo que hace que el servidor de tiempo de espera y cierre la conexión a Microsoft 365.

- Hay problemas de red entre el entorno local y Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>¿Cómo se corrige el código de error 450 4.4.318?

- Descubra qué escenario se aplica a usted y realice las correcciones necesarias.

- Si el problema se debe a problemas de red entre el entorno local y Microsoft 365, póngase en contacto con el equipo de red para solucionar el problema.

- Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de error: error en la validación del certificado 4.7.320 450

Normalmente, este error significa que Microsoft 365 encontró un error al intentar validar el certificado del servidor de correo electrónico de destino. Los detalles del error explicarán el error. Por ejemplo:

- Certificado expirado

- Error de coincidencia del asunto del certificado

- El certificado ya no es válido

### <a name="how-do-i-fix-error-code-450-47320"></a>¿Cómo se corrige el código de error 450 4.7.320?

- Corrija el certificado o la configuración del conector para que se puedan entregar los mensajes en cola en Microsoft 365.

- Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.

## <a name="other-error-codes"></a>Otros códigos de error

Microsoft 365 tiene dificultades para entregar mensajes a su servidor de correo electrónico local o asociado. Use la **información del servidor** de destino en el error para examinar el problema en el entorno o modificar el conector si hay un error de configuración.

Si el error es de su organización asociada (por ejemplo, un proveedor de servicios en la nube de terceros), debe ponerse en contacto con su partner para solucionar el problema.