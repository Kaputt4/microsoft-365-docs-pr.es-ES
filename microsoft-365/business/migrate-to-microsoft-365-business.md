---
title: Actualización a Microsoft 365 Business desde Office 365 empresa Premium
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Pasos para actualizar su empresa de Office 365 empresa Premium a Microsoft 365 Business.
ms.openlocfilehash: f3a25746cf123fa471c29084a62a6fcfc1542a02
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231419"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Actualización a Microsoft 365 Business desde Office 365 empresa Premium

Si tiene una [suscripción de office 365 para empresas](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), por ejemplo, Office 365 empresa Premium, puede actualizar fácilmente a Microsoft 365 Business. Actualice a Microsoft 365 Business si desea agregar: 
- Windows 10 Pro (para equipos que ejecutan Windows 8 o versiones posteriores)
- Controles sencillos que administran los datos profesionales en los dispositivos
- Capacidades de seguridad avanzadas.
Obtenga más información sobre Microsoft 365 Business en [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>¿Cuál es la diferencia entre Office 365 Business Premium y Microsoft 365 Business?
Hemos agregado una comparación en paralelo de estos dos planes a la descripción del servicio de [negocio de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-get-started"></a>Antes de empezar

- **¿Cuándo debe elegirse la actualización?** La actualización es la opción correcta cuando desea actualizar **todos los usuarios** asignados a un solo plan. Cuando elige actualizar, todos los usuarios del plan se cambian a otro plan al mismo tiempo. Si no desea actualizar todos los usuarios asignados a un solo plan, compre licencias para el nuevo plan (en este caso, Microsoft 365 Business) y [asígneles estas licencias individualmente](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) para cada usuario que quiera actualizar. 
- **Algunos complementos pueden impedir la actualización** Si intenta iniciar una actualización y tiene un complemento que le impide continuar, puede quitar el complemento en primer lugar y, a continuación, volver a agregarlo si todavía lo necesita. 
- **Si prepagó el plan** No existe una ruta de actualización sencilla para los planes de prepago. Sabrá si tiene un plan de prepago porque ha configurado su plan con un identificador de producto que puede haber comprado en una tienda. Póngase en contacto con un partner, vaya a Microsoft Store o espere hasta que el plan de prepago expire para cambiar a un nuevo plan.

## <a name="upgrade-to-microsoft-365-business"></a>Actualización a Microsoft 365 Business
Para comprar sus licencias, siga estos pasos en el [nuevo centro de administración](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):
1. Inicie sesión en el centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>administración en.
2. Vaya al panel de navegación y seleccione productos de **facturación** \> **& servicios**. Busque su suscripción a Office 365 y selecciónela para ver los detalles. 

    ![Una captura de pantalla que muestra cómo buscar y seleccionar la suscripción en el centro de administración.](media/FindYourSubscription.png)

3. En la página siguiente, seleccione **Actualizar**. 

      ![Una captura de pantalla muestra dónde seleccionar la actualización en el centro de administración.](media/SelectUpgrade.png)

  > [!NOTE]
  > Si ve un mensaje que indica "no se admite la actualización de la suscripción con licencias basadas en grupos en Azure Active Directory", puede omitirlo sin problemas a menos que tenga una organización muy grande. Las organizaciones que hayan seleccionado esta opción sabrán que están usando licencias basadas en grupos.

4. A continuación, puede ver una lista de los planes de Office a los que puede actualizar. En este caso, busque el plan de negocio de Microsoft 365. Puede desplazarse hacia abajo si desea ver todas las aplicaciones y servicios de Office que se incluyen en este plan. En **microsoft 365 Business**, seleccione **Actualizar** para agregar un negocio de Microsoft 365 a su carro.
5. En el carro:
    1. Se incluirán automáticamente licencias para todos los usuarios actuales en el carro. Si necesita más o menos licencias, necesitará [comprar y asignar dichas licencias de forma individual](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).  
    2. Puede ajustar el modo en que desea pagar: mensual o anual. Seleccione el menú desplegable para elegir.
6. Seleccione **ir a la retirada** para ver un resumen de la compra, incluido el método de pago de esta cuenta. También puede Agregar un código de promoción aquí si tiene uno.
7. Seleccione **realizar pedido** para completar la compra.
Necesita Microsoft unos minutos para configurar los nuevos planes de servicio. Para comprobar el progreso, seleccione **comprobar el estado**de la actualización. 
1. Una vez que el plan esté listo, es posible que deba completar algunos pasos de configuración adicionales en el centro de administración. En el panel de navegación, seleccione **Inicio** para completar los pasos de configuración adicionales.

> [!NOTE]
> Recibirá una restitución prorrateada para las licencias de Ofifce 365 que ya no necesita. La cuenta bancaria o la tarjeta de crédito se cargarán dos días después de configurar el nuevo plan.
  
## <a name="protect-user-devices-and-files"></a>Proteger los archivos y dispositivos de usuario

Ahora que se han asignado las licencias de Microsoft 365 Business, siga los pasos para empezar a proteger dispositivos y archivos. Utilizará algunas nuevas opciones incluidas en el panel de navegación del centro de administración.
  
1. En el panel de navegación del centro de administración, vaya a **** \> **directivas**de dispositivos.
    
2. En la página **directivas de dispositivos** , seleccione **Agregar**.
    
3. En el panel **Agregar Directiva** , asigne un nombre a la Directiva (por ejemplo, proteger archivos de trabajo) y, a continuación, elija un **tipo de directiva** en la lista desplegable. 
    
    Puede configurar directivas de aplicación para proteger los archivos en dispositivos Android y iPhone, así como en Windows 10, y puede configurar directivas de configuración de dispositivo para dispositivos Windows 10 que pertenecen a la empresa. Consulte los siguientes vínculos para obtener más información:
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Establecer la configuración de protección de dispositivos para equipos con Windows 10](protection-settings-for-windows-10-pcs.md)
    
  
4. Una vez configuradas las directivas, usted y sus empleados pueden configurar dispositivos:
    
  - Si los dispositivos Windows ya no usan la actualización del creador de Windows Pro, tendrás que [actualizarlos a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
    
  - Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para conocer los pasos para dispositivos Windows. 
    
  - Consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md) para conocer los pasos para Android Phones y iPhone. 



