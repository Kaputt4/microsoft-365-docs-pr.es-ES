---
title: Administración de la versión de prueba de primera línea en Teams
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo configurar una evaluación de Teams de 90 días para trabajadores de primera línea para su organización.
ms.localizationpriority: high
ms.collection:
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 311d0a5b1204f022a993bbef24ea4bc1edda324c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66998654"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Administración de la versión de prueba de primera línea en Teams

> [!NOTE]
> Esta experiencia de prueba estará disponible próximamente. Puede comprobar cuándo está disponible para su organización si busca un mensaje en el [Centro de mensajes](https://go.microsoft.com/fwlink/p/?linkid=2070717) del centro de Administración de Microsoft 365.

La experiencia de prueba en primera línea de Microsoft Teams permite a los usuarios de su organización que están en Teams iniciar una experiencia de Teams para todo su equipo de primera línea, siempre y cuando los demás miembros estén en Azure Active Directory (Azure AD). Puede deshabilitar esta característica para los usuarios de su organización mediante el [módulo AllowSelfServicePurchase de PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

## <a name="what-services-are-included"></a>Qué servicios se incluyen

La prueba incluye todo lo que se incluye en la [licencia de Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3) con las siguientes excepciones:

- La versión de prueba de primera línea incluye Exchange Foundation en lugar de Exchange Kiosk. Es posible que a los usuarios les falten otras funcionalidades de Teams debido a este cambio.

## <a name="eligibility"></a>Requisitos de idoneidad

> [!NOTE]
> Puede comprobar si su organización forma parte del piloto de prueba si busca un anuncio en el [Centro de mensajes](https://go.microsoft.com/fwlink/p/?linkid=2070717) del centro de Administración de Microsoft 365. Su organización tendrá que formar parte de la prueba piloto para que los usuarios inicien o participen en una prueba. Esta oferta no está disponible para los clientes de GCC, GCC High, DoD o EDU.

La versión de prueba en primera línea puede alojar un máximo de 300 usuarios por prueba.

Los usuarios pueden iniciar una prueba de primera línea para su equipo si:

- Tienen una licencia activa que les proporcione acceso a Teams.
- No han iniciado anteriormente una prueba de trabajo de primera línea.

> [!IMPORTANT]
> Si el usuario que inició la prueba deja la organización antes de que finalice la evaluación, usted, como administrador, tendrá que supervisar la prueba, consultar con el equipo para ver quién se beneficia de estas características y decidir qué usuarios necesitará actualizar a una licencia de pago.

Los usuarios pueden participar en una prueba de trabajo de primera línea si tienen una dirección de correo electrónico de dominio de Azure Active Directory administrada.

Los usuarios pueden participar si han iniciado anteriormente una prueba, pero no pueden iniciar otra prueba.

> [!NOTE]
> Los usuarios sin acceso existente a Teams solo se pueden agregar al equipo de prueba en el momento de la creación del equipo. Los usuarios existentes de Teams todavía se pueden agregar a la prueba una vez creado el equipo.

## <a name="set-up-the-trial"></a>Configuración de la prueba

Los usuarios aptos pueden iniciar una prueba de primera línea iniciando sesión en la aplicación Tareas en Teams desde el escritorio o la [aplicación web](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks). En este momento, no se admite el inicio de una prueba de primera línea a través de dispositivos móviles. Cuando se inicia una prueba, a todo el equipo se le asignará automáticamente la licencia de prueba de primera línea. A los usuarios con licencias de pago existentes que les proporcionen acceso a Teams también se les asignarán licencias de prueba, pero mantendrán la funcionalidad de sus licencias existentes a lo largo de la prueba y conservarán sus licencias de pago existentes una vez finalizada la prueba. El usuario que inició la prueba recibirá notificaciones por correo electrónico durante el transcurso de la prueba.

## <a name="manage-the-frontline-trials-experience"></a>Administración de la experiencia de prueba en primera línea

Los administradores pueden impedir que los usuarios finales inicien la prueba de primera línea dentro de su organización mediante el módulo **AllowSelfServicePurchase** de PowerShell. Esto es solo para licencias de prueba. [Obtenga información sobre cómo usar el módulo AllowSelfServicePurchase de PowerShell](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Administración de Teams para los usuarios que tienen la licencia de prueba de primera línea

Puede administrar los usuarios que tienen la licencia de prueba de primera línea, al igual que los usuarios que tienen una licencia de pago normal. Para más información, consulte [Administrar la configuración de Teams para su organización](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Eliminación de una licencia de prueba

Puede quitar la licencia de prueba de primera línea a través de PowerShell o el Centro de administración de Microsoft 365.

[Obtenga información sobre cómo quitarla con PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Más información sobre quitarla centro de administración](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Actualización de usuarios desde la versión de prueba en primera línea

Los usuarios pueden ponerse en contacto con usted para solicitar licencias cuando finalice la prueba. Necesitará privilegios de administrador para actualizar los usuarios.

### <a name="when-to-upgrade"></a>Cuándo actualizar

Cerca del final de la prueba de 90 días, tendrá que consultar con los usuarios para ver quién necesita continuar con una licencia de pago. Asegúrese de hacerlo antes de que expire la suscripción de prueba de primera línea para evitar cualquier interrupción en las experiencias de los usuarios.

> [!IMPORTANT]
> Si finaliza la licencia de prueba de primera línea y un usuario no tiene asignada inmediatamente una licencia que incluya Teams, perderá el acceso a Teams. Después de 30 días, se eliminarán sus datos (archivos, mensajes, etc.). El usuario seguirá existiendo en Azure Active Directory. Si se asigna una nueva licencia al usuario para habilitar la funcionalidad de Teams en el período de 30 días, todo su contenido en Teams seguirá existiendo.

### <a name="choose-an-upgrade-path"></a>Elegir una ruta de actualización

> [!TIP]
> La prueba de primera línea se basa en la [licencia de Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3).

En función de las suscripciones que tenga actualmente su organización, hay tres maneras de actualizar de una versión de prueba de primera línea a una licencia de pago:

- **Actualice una suscripción de Microsoft 365 existente.** Use esta opción si su organización tiene suscripciones a otros productos de Office que no incluyen Teams. Para obtener más información, vea [Actualizar a un plan diferente](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Para ver los usuarios activos de una suscripción existente, vaya a **Usuarios >** [usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822) en el Centro de administración de Microsoft 365.

- **Agregar usuarios a una suscripción de Microsoft 365 existente.** Use esta opción si su organización no tiene suficientes licencias de Teams de pago para cubrir el equipo de primera línea. Para obtener más información, vea [Comprar o quitar licencias](/microsoft-365/commerce/licenses/buy-licenses). Para agregar usuarios a una suscripción existente que ya tiene suficientes licencias disponibles, consulte [Mover usuarios a una suscripción diferente](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Para ver los usuarios activos de una suscripción existente, vaya a **Usuarios >** [usuarios activos](https://go.microsoft.com/fwlink/p/?linkid=834822) en el Centro de administración de Microsoft 365.

- **Comprar una nueva suscripción a Microsoft 365** Use esta opción si su organización no tiene ninguna suscripción existente a los productos de Office o si su organización quiere comprar una suscripción diferente de la existente para cubrir a los usuarios de primera línea. Para obtener más información, consulte [Microsoft 365 para trabajadores de primera línea](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Si no está seguro de a qué suscripción de Microsoft 365 actualizar, consulte [Microsoft 365 para trabajadores de primera línea](https://www.microsoft.com/microsoft-365/enterprise/frontline). Si necesita ayuda adicional para elegir una suscripción, o si su organización necesita más de 300 licencias, póngase en contacto con su [asociado de Microsoft](https://www.microsoft.com/solution-providers/home) o representante de la cuenta de Microsoft.

### <a name="assign-paid-licenses"></a>Asignar licencias de pago

Para asignar las licencias recién adquiridas, consulte [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).  

Después de asignar las nuevas licencias, anule la asignación de las licencias de Teams Exploratory. Consulte [Cancelar la asignación de licencias de usuarios](/microsoft-365/admin/manage/remove-licenses-from-users), para obtener más información.

## <a name="faq"></a>Preguntas más frecuentes

**¿Cuánto tiempo dura la prueba?** <br>
La versión de prueba de primera línea dura 90 días.

**¿Qué deben hacer los administradores al final de la experiencia de prueba en primera línea de 90 días?** <br>
Al final de la prueba de 90 días, tendrá que consultar con los usuarios para ver quién necesita continuar con una licencia de pago. A continuación, deberá [actualizar los usuarios](#upgrade-users-from-frontline-trial).

**¿Qué ocurre si el usuario que inició la prueba deja la organización?** <br>
Como administrador, deberá supervisar la prueba durante el resto del período de 90 días y actualizar a licencias de pago para los usuarios que las necesiten cuando finalice la prueba.

**¿Cuál es la directiva de retención de datos?** <br>
Puede obtener información sobre la retención de datos en la [información de suscripción de Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?).

**¿Qué ocurre si un usuario encuentra un error al iniciar la versión de prueba en primera línea?** <br>
Asegúrese de que su organización, el usuario que inicia la prueba y los usuarios que se agregan a la prueba cumplen los [criterios de idoneidad](#eligibility).