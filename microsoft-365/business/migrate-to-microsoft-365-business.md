---
title: Actualizar a Microsoft 365 Empresa Premium desde Microsoft 365 Empresa Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Conozca la diferencia entre Microsoft 365 Empresa Standard y Microsoft 365 Empresa Premium y cómo puede actualizar a Microsoft 365 Empresa Premium.
ms.openlocfilehash: bdab8165623170926b17efa4cae9408b78a2f5f5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401390"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a>Actualizar a Microsoft 365 Empresa Premium desde Microsoft 365 Empresa Standard

Si tiene una suscripción a [Microsoft 365](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)para empresas, por ejemplo, Microsoft 365 Empresa Standard, puede actualizar fácilmente a Microsoft 365 Empresa Premium. Actualice a Microsoft 365 Empresa Premium si desea agregar:

- Windows 10 Pro (a equipos que ejecutan Windows 8 o posterior)

- Controles simples que administran datos empresariales en dispositivos

- Capacidades de seguridad avanzadas.
Más información sobre Microsoft 365 Empresa Premium en [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a>¿Cuál es la diferencia entre Microsoft 365 Empresa Standard y Microsoft 365 Empresa Premium?

Hemos agregado una comparación en paralelo de estos dos planes a la descripción del servicio [Microsoft 365 Empresa Premium.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description) 

## <a name="before-you-get-started"></a>Antes de empezar

- **¿Cuándo debo elegir actualizar?** La actualización es la opción adecuada cuando se desea actualizar todos **los usuarios** asignados a un solo plan. Al elegir la actualización, todos los usuarios del plan cambian a otro plan al mismo tiempo. Si no desea actualizar a todos los usuarios asignados a un solo plan, compre licencias para el [](../admin/manage/assign-licenses-to-users.md) nuevo plan (en este caso Microsoft 365 Empresa Premium) y asigne esas licencias individualmente a cada usuario que desee actualizar.

- **Algunos complementos podrían impedir la actualización** Si intenta iniciar una actualización y tiene un complemento que le impide continuar, puede quitar el complemento primero y, a continuación, volver a agregarlo más tarde si aún lo necesita.

- **Si ha pagado por adelantado su plan** No hay una ruta de actualización sencilla para los planes de prepago. Sabrás si tienes un plan de prepago porque configuraste tu plan con un id. de producto que podrías haber comprado en una tienda. Ponte en contacto con un partner, ve a Microsoft Store o espera hasta que expire el plan de prepago para cambiar a un nuevo plan.

## <a name="upgrade-to-microsoft-365-business-premium"></a>Actualizar a Microsoft 365 Empresa Premium

1. Inicie sesión en el centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .

2. Vaya al panel de navegación y seleccione **Facturación** \> **de sus productos.** Busque su suscripción actual y selecciónelo para ver los detalles.

3. En la página siguiente, seleccione **Actualizar**.

  > [!NOTE]
  > Si ve un mensaje que indica que la actualización de su suscripción no es compatible con licencias basadas en grupos en **Azure Active Directory,** puede omitir esto de forma segura a menos que tenga una organización muy grande. Las organizaciones que han seleccionado esta opción tendrán en cuenta que usan licencias basadas en grupos.

4. A continuación, puede ver una lista de planes a los que puede actualizar. En este caso, busque el plan de Microsoft 365 Empresa Premium. Puedes desplazarte hacia abajo si quieres ver todas las aplicaciones y servicios que se incluyen con este plan. En **Microsoft 365 Empresa Premium,** seleccione **Actualizar** para agregar Microsoft 365 Empresa Premium a su carro.

5. En el carro:

    1. Incluiremos automáticamente licencias para todos los usuarios actuales. Si necesita más o menos licencias, debe comprar y asignar esas licencias [individualmente.](../admin/manage/assign-licenses-to-users.md)  
    2. Puedes ajustar cómo quieres pagar: mensual o anual. Seleccione el menú desplegable para elegir.

6. Selecciona **Ir a La desprotección,** donde verás un resumen de la compra, incluido el método de pago de esta cuenta. También puedes agregar un código de promoción aquí si tienes uno.

7. Seleccione **Realizar pedido** para completar la compra.\
Microsoft tarda unos minutos en configurar los nuevos planes de servicio. Para comprobar el progreso, seleccione **Comprobar el estado de actualización.**

8. Cuando el plan esté listo, es posible que deba completar algunos pasos de configuración adicionales en el centro de administración. En el panel de navegación, seleccione **Inicio** para completar los pasos de configuración adicionales.

> [!NOTE]
> Recibirá un reembolso prorrateado de las licencias de Microsoft 365 que ya no necesite. A su cuenta bancaria o tarjeta de crédito se le cobrará aproximadamente dos días después de configurar el nuevo plan.
  
## <a name="protect-user-devices-and-files"></a>Proteger archivos y dispositivos de usuario

Ahora que se han asignado licencias de Microsoft 365 Empresa Premium, complete los pasos para empezar a proteger los dispositivos y archivos. Usará algunas opciones nuevas incluidas en el panel de navegación del centro de administración.
  
1. En el centro de administración, en el panel de navegación, vaya a **Directivas de** \> **dispositivos.**

2. En la **página Directivas de** dispositivo, seleccione **Agregar**.

3. En el **panel Agregar directiva,** asigne un nombre **a** la directiva (por ejemplo, Proteger archivos de trabajo) y, a continuación, elija un tipo de directiva en la lista desplegable.

    Puedes configurar directivas de aplicación para proteger archivos en dispositivos Android y iPhone, así como en Windows 10, y puedes configurar directivas de configuración de dispositivos para dispositivos windows 10 que pertenecen a la empresa. Vea los siguientes vínculos para obtener más información:

    - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)

    - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)

    - [Establecer la configuración de protección de dispositivos para equipos con Windows 10](protection-settings-for-windows-10-pcs.md)

4. Después de configurar las directivas, tú y tus empleados pueden configurar dispositivos:

    - Si los dispositivos Windows aún no usan la actualización de Windows Pro Creator, tendrás que actualizarlos [a Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)

    - Consulte [Configurar dispositivos Windows para los usuarios de Microsoft 365 Empresa Premium](set-up-windows-devices.md) para ver los pasos para los dispositivos Windows.

    - Consulte [Configurar dispositivos móviles para usuarios de Microsoft 365 Empresa Premium](set-up-mobile-devices.md) para ver los pasos para teléfonos Android y iPhone.