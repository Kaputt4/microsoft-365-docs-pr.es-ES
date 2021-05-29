---
title: Actualizar a Microsoft 365 Empresa Premium desde Microsoft 365 Empresa Estándar
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Obtenga información sobre la diferencia entre Microsoft 365 Empresa Estándar y Microsoft 365 Empresa Premium y cómo puede actualizar a Microsoft 365 Empresa Premium.
ms.openlocfilehash: 0968b877820590987f6f3ceca3efbd106b62cbd1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705498"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a>Actualizar a Microsoft 365 Empresa Premium desde Microsoft 365 Empresa Estándar

Si tiene una [suscripción](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)Microsoft 365 para empresas, por ejemplo, Microsoft 365 Empresa Estándar, puede actualizar fácilmente a Microsoft 365 Empresa Premium. Actualice a Microsoft 365 Empresa Premium si desea agregar:

- Windows 10 Pro (a equipos que se ejecutan Windows 8 o posterior)

- Controles simples que administran datos empresariales en dispositivos

- Capacidades de seguridad avanzadas.
Encontrará más información sobre Microsoft 365 Empresa Premium en [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a>¿Cuál es la diferencia entre Microsoft 365 Empresa Estándar y Microsoft 365 Empresa Premium?

Hemos agregado una comparación en paralelo de estos dos planes a la descripción Microsoft 365 Empresa Premium [servicio](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-begin"></a>Antes de empezar

- **¿Cuándo debo elegir actualizar?** La actualización es la opción correcta cuando desea actualizar todos **los usuarios** asignados a un solo plan. Al elegir la actualización, todos los usuarios del plan cambian a otro plan al mismo tiempo. Si no desea actualizar todos los usuarios asignados a un solo plan, compre licencias para [](../admin/manage/assign-licenses-to-users.md) el nuevo plan (en este caso Microsoft 365 Empresa Premium) y asigne esas licencias individualmente a cada usuario que desee actualizar.

- **Algunos complementos podrían impedir la actualización** Si intenta iniciar una actualización y tiene un complemento que le impide continuar, puede quitar el complemento primero y, a continuación, volver a agregarlo más adelante si aún lo necesita.

- **Si prepagó su plan** No hay una ruta de actualización sencilla para los planes de prepago. Sabrás si tienes un plan de prepago porque configuraste el plan con un identificador de producto que podrías haber comprado en una tienda. Póngase en contacto con un partner, vaya al Microsoft Store o espere hasta que expire el plan de prepago para cambiar a un nuevo plan.

## <a name="upgrade-to-microsoft-365-business-premium"></a>Actualizar a Microsoft 365 Empresa Premium

1. Inicie sesión en el Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .

2. Vaya al panel de  navegación y seleccione \> **Facturar sus productos**. Busque la suscripción actual y selecciónelo para ver los detalles.

3. En la página siguiente, seleccione **Actualizar**.

  > [!NOTE]
  > Si ve un mensaje que indica que la actualización de la suscripción no se admite con licencias basadas en grupos en **Azure Active Directory**, puede omitir esto de forma segura a menos que tenga una organización muy grande. Las organizaciones que han seleccionado esta opción tendrán en cuenta que usan licencias basadas en grupos.

4. A continuación, puede ver una lista de planes a los que puede actualizar. En este caso, busque el Microsoft 365 Empresa Premium plan. Puedes desplazarte hacia abajo si quieres ver todas las aplicaciones y servicios que se incluyen con este plan. En **Microsoft 365 Empresa Premium**, seleccione **Actualizar** para agregar Microsoft 365 Empresa Premium al carro.

5. En el carro:

    1. Incluiremos automáticamente licencias para todos los usuarios actuales. Si necesita más o menos licencias, debe comprar y [asignar esas licencias individualmente.](../admin/manage/assign-licenses-to-users.md)  
    2. Puedes ajustar cómo quieres pagar: mensual o anual. Seleccione el menú desplegable para elegir.

6. Selecciona **Ir a Checkout** donde verás un resumen de la compra, incluido el método de pago de esta cuenta. También puedes agregar un código de promoción aquí si tienes uno.

7. Seleccione **Realizar pedido** para completar la compra.\
Microsoft tarda unos minutos en configurar los nuevos planes de servicio. Para comprobar el progreso, seleccione **Comprobar el estado de actualización**.

8. Cuando el plan esté listo, es posible que deba completar algunos pasos de configuración adicionales en el Centro de administración. En el panel de navegación, seleccione **Inicio** para completar los pasos de configuración adicionales.

> [!NOTE]
> Recibirá un reembolso prorrateado para las Microsoft 365 licencias que ya no necesita. Se le cobrará a su cuenta bancaria o tarjeta de crédito unos dos días después de configurar el nuevo plan.
  
## <a name="protect-user-devices-and-files"></a>Proteger los archivos y dispositivos de usuario

Ahora que Microsoft 365 Empresa Premium licencias de usuario se han asignado, complete los pasos para empezar a proteger los dispositivos y archivos. Usarás algunas opciones nuevas incluidas en el panel de navegación del Centro de administración.
  
1. En el Centro de administración, en el panel de navegación, vaya a **Directivas de** \> **dispositivos**.

2. En la **página Directivas de dispositivo,** seleccione **Agregar**.

3. En el **panel Agregar directiva,** asigne un nombre a la directiva (por ejemplo, Proteger archivos de trabajo) y, **a** continuación, elija un tipo de directiva en la lista desplegable.

    Puedes configurar directivas de aplicación para proteger archivos en dispositivos Android y iPhone, así como Windows 10, y puedes configurar directivas de configuración de dispositivos para dispositivos de Windows 10 empresa. Vea los siguientes vínculos para obtener más información:

    - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)

    - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)

    - [Establecer la configuración de protección de dispositivos Windows 10 equipos](protection-settings-for-windows-10-pcs.md)

4. Después de configurar directivas, tú y tus empleados pueden configurar dispositivos:

    - Si los dispositivos Windows ya no están usando la actualización Windows Pro Creator, tendrás que actualizarlos a [Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

    - Consulta [Configurar dispositivos Windows para Microsoft 365 Empresa Premium usuarios para](set-up-windows-devices.md) ver los pasos para Windows dispositivos.

    - Consulta [Configurar dispositivos móviles para Microsoft 365 Empresa Premium usuarios para](set-up-mobile-devices.md) ver los pasos para teléfonos Android y iPhones.