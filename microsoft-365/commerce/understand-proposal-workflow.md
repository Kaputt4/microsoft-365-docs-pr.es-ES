---
title: Descripción del flujo de trabajo de la propuesta
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: presharm, jmueller
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_purchase
- AdminSurgePortfolio
search.appverid: MET150
description: Obtenga información sobre las propuestas que le ayudarán a comprar productos y servicios de Microsoft.
ROBOTS: NOINDEX
ms.date: 07/11/2022
ms.openlocfilehash: 154691dea57c7ee95583f9a8903278e012e7d9d6
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68733202"
---
# <a name="understand-the-microsoft-proposal-workflow"></a>Descripción del flujo de trabajo de propuestas de Microsoft

Una propuesta es una oferta formal de Microsoft para que su organización compre productos y servicios de Microsoft. Las propuestas representan grandes pedidos que la adquisición de su organización o el departamento de TI realizan con Microsoft.

Antes de que comience el flujo de trabajo de la propuesta, el departamento de adquisiciones trabaja directamente con un representante designado de Microsoft para determinar los productos y servicios específicos que necesita su organización. A continuación, el representante de Microsoft redacta una propuesta y envía al departamento de adquisiciones un correo electrónico con un vínculo para aceptar la propuesta en el portal de Azure Marketplace. El sitio contiene la propuesta preparada específicamente para usted y su organización.

Después de seguir el vínculo e iniciar sesión en el sitio de propuesta, puede iniciar el proceso de revisión de la propuesta. Después de completar la revisión y el des check-out de la propuesta, recibirá una factura para los productos comprados según el plan de facturación seleccionado. Para obtener información sobre cómo funciona la facturación de las propuestas, consulte [Descripción de la facturación](#understand-invoicing) a continuación.

## <a name="prerequisites-for-buying-items-with-a-proposal"></a>Requisitos previos para comprar artículos con una propuesta

Para poder comprar artículos para una propuesta, debe tener una cuenta de facturación y un contrato con Microsoft.

### <a name="billing-account"></a>Cuenta de facturación

Use una cuenta de facturación para administrar la configuración de la cuenta, las facturas, los perfiles de facturación y los productos y servicios. Si aún no tiene una cuenta de facturación, su representante de Microsoft crea una para usted. De lo contrario, usan una cuenta de facturación existente para su organización, siempre y cuando tenga permiso para usar esa cuenta de facturación.

Los permisos de la cuenta de facturación los administra el propietario de la cuenta de facturación. Los administradores globales pueden asignarse a sí mismos al rol de propietario de la cuenta de facturación y, a continuación, hacer que otros usuarios facturan a los propietarios de la cuenta.

Para obtener más información sobre las cuentas de facturación, consulte [Administración de cuentas de facturación](manage-billing-accounts.md).

### <a name="microsoft-customer-agreement"></a>Contrato de cliente de Microsoft

El Contrato de cliente de Microsoft (MCA) permite a una organización comprar productos y servicios de Microsoft. Para obtener más información, consulte [Contrato de cliente de Microsoft](https://www.microsoft.com/Licensing/how-to-buy/microsoft-customer-agreement).

## <a name="permissions-needed-to-sign-an-agreement-or-pay-for-items"></a>Permisos necesarios para firmar un contrato o pagar por artículos

Debe ser propietario de la cuenta de facturación o colaborador de la cuenta de facturación para firmar correctamente un contrato o comprar productos y servicios. Si es un administrador global pero no tiene uno de esos roles, puede asignar los roles a sí mismo. Si no es un administrador global, pida al administrador global o al propietario de la cuenta de facturación que le asigne uno de los roles.

El propietario de la cuenta de facturación y los roles de colaborador de la cuenta de facturación se asignan mediante cualquiera de los métodos siguientes.

### <a name="assign-roles-in-the-microsoft-365-admin-center"></a>Asignación de roles en el Centro de administración de Microsoft 365

1. En el Centro de administración de Microsoft 365, vaya a la página Cuentas de **facturación** > .<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank"></a>
2. En la página **Cuentas de facturación** , en la sección **Roles de cuenta de facturación** , seleccione **Asignar roles**.
3. En el panel **Asignar roles** , busque el nombre de la persona a la que desea asignar un rol.
4. Seleccione el cuadro del nombre de rol que desea que tenga la persona y, a continuación, seleccione **Asignar**.

### <a name="assign-roles-in-the-azure-portal"></a>Asignar roles en el Azure Portal

1. En el Azure Portal, vaya a la página Control de <a href="https://portal.azure.com/#blade/Microsoft_Azure_GTM/ModernBillingMenuBlade/Overview" target="_blank">acceso (IAM).</a>
2. En la página **Control de acceso (IAM),** seleccione **Agregar**.
3. En el panel **Agregar permiso** , seleccione el **rol** que se va a asignar al usuario.
4. Seleccione el usuario y, a continuación, seleccione **Guardar**.

Para obtener más información sobre los roles de cuenta de facturación, consulte [Descripción del acceso a las cuentas de facturación](manage-billing-accounts.md#understand-access-to-billing-accounts).

Si se trata de una nueva cuenta de facturación y nadie ha aceptado un contrato, se convierte automáticamente en el propietario de la cuenta de facturación, siempre que:

- ¿Es la persona nombrada en la propuesta o
- Ya es [un administrador global de Azure Active Directory](/azure/active-directory/roles/permissions-reference#global-administrator) para su organización

## <a name="what-is-the-overall-workflow"></a>¿Cuál es el flujo de trabajo general?

El flujo de trabajo general de la propuesta tiene este aspecto:

- Su representante de Microsoft crea una propuesta y le envía un vínculo en un correo electrónico.
- Use el vínculo para ir a la página de inicio de sesión de la propuesta.
- Revise la información de su organización.
- Revise la propuesta, acepte el MCA si es necesario y finalice el proceso de compra.
  > [!IMPORTANT]
  > Debe tener la autoridad para firmar una MCA en nombre de su organización. Si no tiene esa autoridad, alguien que lo haga debe realizar este paso.
- Una vez finalizada la compra, se le proporcionan más vínculos para configurar los productos y servicios.

## <a name="proposal-terms"></a>Términos de la propuesta

La tabla siguiente contiene términos y definiciones que aparecen en la propuesta y en el sitio de la propuesta.

| Término | Definición |
|---|---|
| Cuenta de facturación | Una cuenta que se usa para administrar la configuración de la cuenta, las facturas, los métodos de pago y los productos. |
| Perfil de facturación | Información sobre su organización que le permite personalizar qué elementos se incluyen en la factura y cómo se paga por las facturas. El perfil de facturación incluye el nombre de la cuenta de facturación, los métodos de pago usados para el perfil de facturación específico, la información de contacto, la configuración de la factura y los permisos que le permiten cambiar el perfil de facturación, pagar facturas y comprar productos y servicios. |
| Acuerdos existentes | Cualquier acuerdo que su organización ya tenga en vigor con Microsoft. Los contratos pueden incluir, entre otros, un Enterprise Agreement, un Contrato de servicios de & de productos de Microsoft o Contrato de cliente de Microsoft. |
| Contrato de cliente de Microsoft (MCA) | Un acuerdo que describe los términos y condiciones de la cuenta que mantiene su organización con Microsoft. |
| Representante de Microsoft | Un representante autorizado de Microsoft que prepara una propuesta para usted y su organización. |
| Organización | Entidad jurídica que usa productos, tecnologías o servicios de Microsoft. |
| Preparado por | Dirección de correo electrónico del representante de Microsoft que preparó la propuesta. |
| Términos complementarios | Enmiendas a la MCA que contienen términos específicos de su organización. Para aceptar términos complementarios, debe usar DocuSign para registrar una firma electrónica. |

## <a name="step-1-review-organization-information"></a>Paso 1: Revisión de la información de la organización

Después de iniciar sesión, lo primero que hace es revisar la información de su organización.

### <a name="your-organization"></a>Su organización

En la sección **Su organización** se muestra la cuenta de facturación asociada a ella. La información de la cuenta de facturación se extrae de una cuenta de facturación existente o la crea automáticamente el representante de Microsoft. Si su organización es una filial de otra organización, también verá una sección **de organización de clientes potenciales** con el nombre y la dirección de esa organización.

Si este pedido es la primera vez que su organización establece una relación comercial con Microsoft y aún no ha firmado una MCA, si la información de **su organización** o **organización de clientes potenciales** es incorrecta, póngase en contacto con el representante para realizar cambios. Una vez que haya aceptado una MCA, puede revisar y cambiar la dirección de la organización y la información de contacto en la página [Cuentas de facturación](https://go.microsoft.com/fwlink/p/?linkid=2084771) de la Centro de administración de Microsoft 365. Si cambia el nombre de la organización, abra una solicitud de soporte técnico para que se actualice. [Obtenga información sobre cómo abrir una solicitud de soporte técnico](../admin/get-help-support.md).

### <a name="your-information"></a>Su información

Si es un nuevo cliente, escriba su nombre, dirección de correo electrónico y número de teléfono en **Su información** y, a continuación, seleccione **Guardar**. Si es un cliente existente, compruebe que la información es correcta. Para realizar correcciones, seleccione **Editar**, realice los cambios necesarios y, a continuación, seleccione **Guardar**.

Cuando esté listo, seleccione **Continuar** para pasar al paso siguiente.

## <a name="step-2-review-proposal"></a>Paso 2: Revisión de la propuesta

La propuesta contiene los detalles de los elementos que ha analizado con su representante de Microsoft. Puede reenviar el correo electrónico con el vínculo de propuesta para compartirlo con otras partes interesadas de su organización. Cualquier otra persona que use el vínculo tiene una vista de solo lectura de la propuesta.

Si desea realizar cambios en la propuesta después de la revisión, póngase en contacto con su representante de Microsoft.

### <a name="proposal-contents"></a>Contenido de la propuesta

La propuesta contiene la siguiente información:

| Sección | Descripción |
|---|---|
| Nombre de la organización | Nombre de la organización para la que se preparó la propuesta. |
| Válido hasta la fecha | Fecha en la que expira la oferta de propuesta. Si se pierde esta fecha de expiración, póngase en contacto con su representante de Microsoft para informarle de que todavía le interesa la propuesta. |
| Divisa | Moneda utilizada para calcular el costo de los artículos de la propuesta. |
| Preparado para | El nombre de la cuenta de facturación, la dirección, la dirección de correo electrónico de contacto y el número de teléfono de la persona que solicitó la propuesta. |
| Preparado por | Dirección de correo electrónico del representante de Microsoft que preparó la propuesta. |
| Resumen | Muestra el subtotal asociado a la propuesta. Si es necesario, también mostrará la tasa de divisas (FX) que se usa para calcular los costos. |
| Elementos de línea de propuesta | Esta sección contiene la cantidad, el precio unitario y el subtotal de todos los artículos incluidos en la propuesta. |
| Paso siguiente | Esta sección indica la acción necesaria que debe realizar. |

Para firmar un MCA, seleccione el botón en **Paso siguiente**. Si debe firmar términos complementarios, un vínculo le lleva al sitio de DocuSign, donde sigue los pasos para firmar el documento.

Después de firmar los contratos necesarios o los términos complementarios, seleccione **Ir a la compra**.

## <a name="step-3-checkout"></a>Paso 3: Desprotección

La página de desprotección contiene las secciones siguientes:

### <a name="sold-to"></a>Vendido a

En esta sección se muestra la cuenta de facturación utilizada para la propuesta. Si necesita cambiar cualquier información, seleccione el vínculo **Editar** . También puede usar el vínculo **Editar** para agregar el identificador de impuestos de su organización. El id. fiscal debe estar relacionado con el país que aparece en la sección **Vendido a** . Si tiene una exención fiscal, debe abrir una incidencia de soporte técnico para solicitar el estado exento de impuestos.

Para obtener más información sobre los identificadores de impuestos y cómo solicitar el estado de exención de impuestos, consulte [Información fiscal de Microsoft 365](billing-and-payments/tax-information.md).

### <a name="billed-to"></a>Facturado a

En esta sección se muestra el perfil de facturación que se usa para determinar qué artículos se incluyen en la factura y cómo se pagan las facturas. Cada ciclo de facturación, recibirá una factura independiente para cada perfil de facturación. El pago de facturas se realiza mediante cheques o transferencias bancarias, o el prepago de Azure. Si aún no tiene un perfil de facturación, su representante de Microsoft crea uno para usted. Durante la compra, puede seleccionar un perfil de facturación diferente, si tiene uno, cambiar el nombre del perfil de facturación o agregar un P.O. Número. También puede crear un nuevo perfil de facturación.

Para obtener información sobre los perfiles de facturación, consulte [Administración de perfiles de facturación](billing-and-payments/manage-billing-profiles.md).

### <a name="proposal-items-in-this-order"></a>Elementos de propuesta en este orden

En esta sección se muestra una lista de todos los elementos incluidos en la propuesta, que pueden incluir una o varias de las categorías siguientes:

- **Términos complementarios** Una lista de las enmiendas a la MCA que contienen términos para su organización. Por ejemplo, esta lista podría incluir términos HIPAA o RGPD.
- **Comprar ahora** Una lista de los elementos que paga durante la compra al final del flujo de trabajo de aceptación de la propuesta.
- **Descuentos (aplicados a cargos futuros)** Una lista de descuentos que recibe como parte de la propuesta.
- **Incluido** Una lista de los elementos incluidos como parte del paquete de propuestas sin cargo adicional. Algunos de estos artículos podrían tener un costo asociado a ellos en el futuro.

> [!NOTE]
> La propuesta puede incluir suscripciones con una fecha de inicio futura. Para obtener más información, consulte [Descripción de la facturación para futuras fechas de inicio](billing-and-payments/future-start-date.md).

### <a name="summary"></a>Resumen

En esta sección se muestra el número de artículos pagados, el subtotal, los impuestos estimados y el importe total del pedido.

Para realizar el pedido, seleccione **Realizar pedido** o **Aceptar pedido de colocación del contrato&amp;**.

Después de realizar el pedido, recibirá una confirmación con los pasos siguientes. Si compró un plan de Azure, el siguiente paso es configurar la cuenta de facturación en el Azure Portal.

## <a name="step-4-set-up-your-new-billing-account-azure-customers-only"></a>Paso 4: Configuración de la nueva cuenta de facturación (solo clientes de Azure)

Si es un nuevo cliente y ha comprado productos de Azure como parte de la propuesta, el siguiente paso es configurar la nueva cuenta de facturación. Para obtener información sobre cómo hacerlo, consulte [Configuración de la cuenta de facturación para una Contrato de cliente de Microsoft](/azure/cost-management-billing/manage/mca-setup-account).

Si es un cliente de Azure existente con un Enterprise Agreement y firma una MCA por primera vez, el siguiente paso es obtener información sobre los cambios entre los contratos y cómo completar tareas con la nueva cuenta de facturación. Para obtener más información, consulte [Completar tareas de Enterprise Agreement en la cuenta de facturación para obtener una Contrato de cliente de Microsoft](/azure/cost-management-billing/manage/mca-enterprise-operations).

## <a name="understand-invoicing"></a>Descripción de la facturación

Después de realizar el check-out y completar el pedido, se envía una factura inicial en un plazo de 24 a 48 horas. Después de eso, recibe facturas alrededor del quinto de cada mes. La factura mensual contiene cargos del mes anterior. Si tiene créditos para su cuenta, se deducirán de los créditos monetarios de su perfil de facturación y se aplicarán al saldo de la factura. El saldo restante después de aplicar los créditos es el saldo vencido. Tiene 30 días a partir de la fecha de facturación para pagar la factura.

Las instrucciones de pago sobre dónde enviar cheques o transferencias bancarias se incluyen en la copia EN PDF de la factura. Para ver o descargar la factura, consulte [Ver la factura o la factura](billing-and-payments/view-your-bill-or-invoice.md).
