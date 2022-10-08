---
title: Buscar correos electrónicos y corregir amenazas mediante el Explorador de amenazas en Microsoft 365 Defender
description: Los pasos para realizar la corrección manual en el Explorador de amenazas en Microsoft 365 Defender, incluido cómo obtener el mejor rendimiento y escenarios que llaman a la corrección.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-guidance-templates
- m365-security
- tier3
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: c55cad1ccca7f28806b724d26eb232fcc315ca7c
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224918"
---
# <a name="steps-to-use-manual-email-remediation-in-threat-explorer"></a>Pasos para usar la corrección manual de correo electrónico en el Explorador de amenazas

Email corrección es una característica ya existente que ayuda a los administradores a actuar en los correos electrónicos que son amenazas.

## <a name="what-youll-need"></a>Lo que necesitará
- Microsoft Defender para Office 365 plan 2 (incluido en los planes E5)
- Permisos suficientes (asegúrese de conceder el rol [de búsqueda y purga](https://sip.security.microsoft.com/securitypermissions) de la cuenta)

## <a name="create-and-track-the-remediation"></a>Creación y seguimiento de la corrección

1. **Seleccione una amenaza para corregirla** en el [Explorador de amenazas](https://security.microsoft.com/threatexplorer) y seleccione el botón **Acciones del mensaje** , que le ofrecerá opciones como *Eliminación temporal* o *Eliminación rígida*.
1. El panel lateral se abrirá y pedirá detalles, como un nombre para la corrección, la gravedad y la descripción. Una vez que se revise la información, presione **Enviar**.
1. En cuanto el administrador apruebe esta acción, verá aquí el identificador de aprobación y un vínculo [al Centro de](https://security.microsoft.com/action-center/history) acciones de Microsoft 365 Defender. En esta página se **puede realizar un seguimiento de las acciones**.

    1. **Administración alerta de acción**: se muestra una alerta del sistema en la cola de alertas con el nombre "Acción administrativa enviada por un administrador". Esto indica que un administrador tomó la acción de corregir una entidad. Proporciona detalles como el nombre del administrador que realizó la acción y el vínculo de investigación y el tiempo. Esto hace que los administradores conozcan cada acción importante, como la corrección, realizada en las entidades.
    1. **Administración investigación de acciones**: dado que el administrador ya realizó el análisis de las entidades y eso es lo que llevó a la acción realizada, el sistema no realiza ningún análisis adicional. Muestra detalles como alerta relacionada, entidad seleccionada para la corrección, acción realizada, estado de corrección, recuento de entidades y aprobador de la acción. Esto permite a los administradores realizar un seguimiento de la investigación y las acciones que se llevan a cabo *manualmente*(una investigación de acción de administrador).
1. **Registros de acciones en el centro de acciones unificado**: los registros de historial y acción de acciones de correo electrónico, como la eliminación temporal y el traslado a la carpeta de elementos eliminados, están *disponibles en una vista centralizada en* la **pestaña Historial** **del Centro** >  de acciones unificado. 
1. **Filtros en el centro de acciones unificado** : hay varios filtros, como el nombre de la corrección, el identificador de aprobación, el identificador de investigación, el estado, el origen de la acción y el tipo de acción. Estos son útiles para buscar y realizar un seguimiento de las acciones de correo electrónico en el Centro de acciones unificado.

> [!IMPORTANT]
> Rendimiento Para mejorar el rendimiento, la corrección debe realizarse en lotes de *50 000 o menos*. Reduzca el resultado de la búsqueda mediante la *ubicación de entrega más reciente* y desencadene la corrección de correo electrónico si el correo electrónico está en una carpeta corregida como Bandeja de entrada, Correo no deseado, Eliminado, por ejemplo.

## <a name="scenarios-that-call-for-email-remediation"></a>Escenarios que llaman a la corrección de correo electrónico

Estos son los escenarios de corrección de correo electrónico:

1. Como parte de una investigación, SecOps identifica una amenaza en el buzón de un usuario final y quiere borrar los correos electrónicos problemáticos.
1. Cuando SecOps aprueba las acciones de correo electrónico sugeridas en Investigación y respuesta automatizadas (AIR), la acción de corrección se desencadena automáticamente para el clúster de correo electrónico o correo electrónico determinado.

Dos escenarios de corrección de correo electrónico manual:

1. El escenario principal:
    1. Las acciones manuales realizadas en los correos electrónicos (por ejemplo, mediante el Explorador de amenazas o la búsqueda avanzada) solo son visibles en el Centro de acciones de Defender para Office 365 heredado (Email y La colaboración > Revisar > Centro de acciones en el Centro de acciones: seguridad de Microsoft 365).  
1. Escenario de aprobación en dos pasos:
    1. Acciones manuales pendientes de aprobación mediante el proceso de aprobación en dos pasos (1. Un analista agregó el correo electrónico a la corrección, 2. El correo electrónico fue revisado y aprobado por otro analista).

Dados los escenarios comunes, la corrección de correo electrónico se puede desencadenar de tres maneras diferentes.

1. **Corrección basada en consultas**: al seleccionar todos los resultados de búsqueda con una consulta (se pueden enviar 200 000 correos electrónicos como máximo).
1. **Corrección seleccionada a mano**: para seleccionar correos electrónicos uno a uno, haga clic en la casilla (se pueden enviar 100 correos electrónicos a la vez).
1. **Corrección basada en consultas con exclusiones**: selección de todos los correos electrónicos y eliminación manual de algunos mensajes (la consulta puede contener un máximo de 1000 correos electrónicos y el número máximo de exclusiones es 100).

## <a name="next-steps"></a>Pasos siguientes
1. Vaya al [portal de Microsoft 365 Defender](https://security.microsoft.com) e inicie sesión.
1. En el panel de navegación, seleccione **Centro de acciones**.
1. Vaya a la pestaña **Historial** y haga clic en cualquier lista de aprobación en espera. Se abre un panel lateral.  
1. Realice un seguimiento del estado de la acción en el centro de acciones unificado.

## <a name="more-information"></a>Más información

[Más información sobre la corrección de correo electrónico](../../office-365-security/air-review-approve-pending-completed-actions.md)
