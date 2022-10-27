---
title: Administración de la facturación entre varios inquilinos de la Centro de administración de Microsoft 365
f1.keywords: NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: amberb, vikdesai
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
search.appverid: MET150
description: Obtenga información sobre cómo usar relaciones de facturación multiinquilino para compartir cuentas de facturación entre inquilinos de la Centro de administración de Microsoft 365.
ms.date: 08/15/2022
ms.openlocfilehash: 03e0f16f8f457ef95b6161a15078ba5374027476
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68720314"
---
# <a name="manage-billing-across-multiple-tenants-in-the-microsoft-365-admin-center"></a>Administración de la facturación entre varios inquilinos de la Centro de administración de Microsoft 365

Puede simplificar la administración de facturación para su organización mediante la creación de relaciones de facturación multiinquilino con otros inquilinos. Una relación de facturación multiinquilino le permite compartir de forma segura la cuenta de facturación de su organización con otros inquilinos, a la vez que mantiene el control sobre los datos de facturación. Puede crear suscripciones en distintos inquilinos y proporcionar a los usuarios de esos inquilinos acceso a la cuenta de facturación de su organización. Esta relación permite a los usuarios de esos inquilinos realizar actividades de facturación, como ver y descargar facturas o administrar licencias.

> [!IMPORTANT]
> Este artículo solo se aplica a los clientes de cuentas de la organización con un Contrato de cliente de Microsoft.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser propietario de la cuenta de facturación para realizar las tareas descritas en este artículo. Para obtener más información, consulte [Descripción de las cuentas de facturación de Microsoft](../manage-billing-accounts.md).

## <a name="decide-which-billing-tenant-solution-is-right-for-your-organization"></a>Decidir qué solución de inquilino de facturación es adecuada para su organización

La elección de configurar varios inquilinos de facturación podría ser el enfoque adecuado, en función de las necesidades de su organización. En la tabla siguiente se compara el uso de un enfoque de inquilino único o multiinquilino para ayudarle a decidir qué enfoque es adecuado para su organización.

| **Para este área de facturación**   | **Considere la posibilidad de usar cuentas de facturación de un solo inquilino si:**  | **Considere la posibilidad de usar varios inquilinos que comparten una sola cuenta de facturación si:**  |
|-----------------------------|--------------------------------------------------------|------------------------------------------------------------------------------|
| **Invoicing**               | Quiere que las compras realizadas por diferentes cuentas de facturación estén siempre en facturas diferentes.    | Quiere que las compras realizadas por los usuarios de distintos inquilinos estén en las mismas facturas o en distintas, en función de su elección.  |
| **Administración de las compras** | Quiere que las suscripciones solo se creen en el inquilino en el que se compran.   | Quiere que las suscripciones compradas en un inquilino se creen en un inquilino diferente que comparta la misma cuenta de facturación.  |
| **Contratos**              | Quiere que cada cuenta de facturación de su propio inquilino firme su propio contrato con Microsoft. Los Términos de compra de afiliados al cliente (CAPT) pueden definir contratos de afiliación entre diferentes cuentas de facturación en inquilinos únicos.  | Quiere que los contratos se firmen con una sola cuenta de facturación y que los mismos contratos se apliquen a todos los inquilinos que comparten la cuenta de facturación. |
| **Precios y descuentos**   | No quiere que se compartan descuentos entre varias cuentas de facturación a menos que esas cuentas compartan términos capt.  | Quiere que se apliquen descuentos en una cuenta de facturación, independientemente del inquilino en el que un usuario realice una compra o de dónde se creen las suscripciones debido al uso compartido de un contrato. |
| **Visibility**              | Solo quiere que los usuarios de una cuenta de facturación tengan visibilidad sobre lo que hay en esa cuenta de facturación y no sobre lo que hay en un inquilino diferente. Por ejemplo, solo quiere que los usuarios vean los costos y las facturas, compren productos y realicen un seguimiento de los pagos de su propio inquilino. | Quiere que los usuarios con cuentas de facturación compartidas tengan la misma vista de la cuenta de facturación independientemente del inquilino en el que se encuentren. |
| **Seguridad**                | Quiere que todos los usuarios con acceso a su cuenta de facturación sigan las directivas de seguridad del inquilino.  | Quiere que los usuarios que invitó a compartir su cuenta de facturación sigan las directivas de seguridad de su propio inquilino. |

## <a name="what-are-the-types-of-tenants-in-a-multi-tenant-billing-relationship"></a>¿Cuáles son los tipos de inquilinos en una relación de facturación multiinquilino?

Hay dos tipos de inquilinos en un escenario de facturación multiinquilino:

1. **Inquilino de facturación principal**: el inquilino de facturación principal es el inquilino que se usa cuando se configura la cuenta de facturación. De forma predeterminada, todas las suscripciones se compran en este inquilino y solo los usuarios de este inquilino pueden obtener acceso a la cuenta de facturación.
2. **Inquilino de facturación asociado**: un inquilino de facturación asociado es un inquilino que está vinculado a la cuenta de facturación del inquilino de facturación principal. Estos inquilinos pueden comprar suscripciones con su cuenta de facturación o pueden aceptar suscripciones suyas. También puede asignar roles de cuenta de facturación a los usuarios de un inquilino de facturación asociado.

## <a name="what-access-settings-are-available-for-associated-billing-tenants"></a>¿Qué configuración de acceso está disponible para los inquilinos de facturación asociados?

Al agregar un inquilino de facturación asociado a la cuenta de facturación, puede habilitar una o ambas opciones de acceso siguientes.

- **El aprovisionamiento** permite la creación de suscripciones en los inquilinos de facturación asociados.
- **La administración de facturación** permite a los propietarios de cuentas de facturación asignar roles a los usuarios de un inquilino de facturación asociado, conciéndoles permiso para acceder a la información de facturación y tomar decisiones de compra.

## <a name="add-an-associated-billing-tenant"></a>Agregar un inquilino de facturación asociado

Antes de empezar, asegúrese de que tiene el identificador de inquilino o el nombre de dominio principal del inquilino que desea invitar. Para obtener más información, consulte [Buscar un identificador de inquilino o un nombre de dominio](https://aka.ms/findtenantiddomain).

1. En el centro de administración, vaya a la página **Cuentas de facturación**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank"></a>
2. Seleccione el nombre de la cuenta de facturación que desea usar como inquilino de facturación principal.
3. En la página de detalles de la cuenta de facturación, seleccione la pestaña **Inquilinos de facturación asociados** y, a continuación, seleccione **Agregar un inquilino de facturación asociado**.
4. En el panel **Agregar un** **inquilino de facturación asociado** , escriba el identificador de inquilino o el nombre de dominio y escriba un nombre descriptivo para el inquilino.
5. En la sección **Configuración de acceso** , seleccione una o ambas opciones para **Administración de aprovisionamiento** y **facturación**.
6. Lea y seleccione el cuadro situado junto a la instrucción de visibilidad del usuario.
7. Seleccione **Agregar inquilino**.

Si la opción **Acceso de aprovisionamiento** está activada, se crea un vínculo único para que se envíe al administrador global en el inquilino de facturación asociado. Deben aceptar la solicitud para poder mover suscripciones a su inquilino.

## <a name="assign-roles-to-users-from-the-associated-billing-tenant-optional"></a>Asignar roles a los usuarios desde el inquilino de facturación asociado (opcional)

1. En el centro de administración, vaya a la página **Cuentas de facturación**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank"></a>
2. Seleccione el nombre de la cuenta de facturación para asignar roles.
3. En la página de detalles de la cuenta de facturación, seleccione la pestaña **Roles de cuenta de facturación** y, a continuación, seleccione **Asignar roles.**
4. En el panel **Asignar rol** , busque el inquilino de facturación asociado, seleccione un rol y escriba la dirección de correo electrónico de los usuarios a los que desea asignar un rol.
5. Seleccione **Asignar.**

El usuario recibe un correo electrónico con un vínculo para revisar la solicitud de asignación de roles. Después de aceptar el rol, tienen acceso a la cuenta de facturación. Para obtener información sobre los roles de cuenta de facturación, consulte [Descripción de las cuentas de facturación de Microsoft](../manage-billing-accounts.md).

> [!IMPORTANT]
> Cualquier usuario con un rol en la cuenta de facturación puede ver todos los usuarios de todos los inquilinos que tienen acceso a esa cuenta de facturación. Por ejemplo, si Contoso.com es el inquilino de facturación principal y el propietario de una cuenta de facturación agrega Fabrikam.com como inquilino de facturación asociado y, a continuación, agrega Katarina como propietario de la cuenta de facturación, Katarina puede ver todos los usuarios que tienen acceso a la cuenta de facturación tanto en Contoso.com como en Fabrikam.com.

## <a name="move-subscriptions-to-an-associated-billing-tenant-optional"></a>Traslado de suscripciones a un inquilino de facturación asociado (opcional)

El administrador global del inquilino de facturación asociado debe aceptar la solicitud de aprovisionamiento del inquilino de facturación principal para poder mover las suscripciones a su inquilino de facturación asociado.

> [!IMPORTANT]
> Solo puede mover una suscripción a un inquilino de facturación asociado si todas las licencias de la suscripción están disponibles. Si se asignan licencias, no se puede mover la suscripción.

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. Seleccione el nombre del producto que desea mover al inquilino de facturación asociado.
3. En la página de detalles del producto, en la sección **Licencias asignadas de todas las suscripciones** , seleccione **Mover a otro inquilino**.
4. En el panel **Mover suscripción a otro inquilino** , busque un nombre de inquilino o seleccione un inquilino de la lista y, a continuación, seleccione **Mover** **suscripción**.

## <a name="remove-an-associated-billing-tenant"></a>Eliminación de un inquilino de facturación asociado

Quitar un inquilino de facturación asociado es una acción permanente y no se puede deshacer. El acceso se quita para todos los usuarios de inquilino a los que se les asignan roles en la cuenta de facturación y ya no se pueden mover suscripciones al inquilino. Las suscripciones que ya se han movido permanecen en el inquilino y se siguen facturando a su cuenta de facturación.

1. En el centro de administración, vaya a la página **Cuentas de facturación**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank"></a>
2. Seleccione el nombre de la cuenta de facturación que es el inquilino de facturación principal.
3. En la página de detalles de la cuenta de facturación, seleccione la pestaña **Inquilinos de facturación asociados** .
4. Seleccione el inquilino de facturación asociado que desea quitar.
5. En el panel inquilino de facturación asociado, seleccione **Quitar acceso.**
6. En el panel Quitar **acceso de** **administración de aprovisionamiento y facturación**, seleccione **Quitar acceso.**
7. En el cuadro de diálogo de confirmación, seleccione **Sí**.

## <a name="accept-or-decline-an-invitation-for-provisioning-access-to-your-associated-billing-tenant"></a>Aceptar o rechazar una invitación para el acceso de aprovisionamiento al inquilino de facturación asociado

Como administrador global de un inquilino de facturación asociado, puede aceptar o rechazar una solicitud del propietario de la cuenta de facturación para crear suscripciones en el inquilino. Cuando el propietario de una cuenta de facturación agrega el inquilino como inquilino de facturación asociado y habilita la configuración **De aprovisionamiento** de acceso, recibe un vínculo del propietario de la cuenta de facturación para aceptar o rechazar la invitación.

1. Seleccione el vínculo compartido por el propietario de la cuenta de facturación.
2. En la página **Invitación para ser un inquilino de facturación asociado** , seleccione **Aceptar** o **Rechazar**.

> [!NOTE]
> Si más adelante decide revocar el acceso **de aprovisionamiento** , puede usar el mismo vínculo.

## <a name="related-articles"></a>Artículos relacionados

[Descripción de las cuentas de facturación de Microsoft](../manage-billing-accounts.md) (artículo)\
[Descripción de los perfiles de facturación](manage-billing-profiles.md) (artículo)
