---
title: Migrar a Microsoft 365 Business desde Office 365 Business Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Obtenga información sobre cómo mover su negocio a Microsoft 365 empresarial.
ms.openlocfilehash: fd6f18c02453e6751d6163ab79e726eae9c951a9
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871636"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migrar a Microsoft 365 Business desde Office 365 Business Premium

Si ya tiene un Office 365 para suscripción empresarial, por ejemplo, Office 365 Business Premium, fácilmente puede agregar licencias a Microsoft 365 Business y asignarlas a algunos o todos los usuarios.
  
> [!NOTE]
> No puede usar el botón de [planes de modificador](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) para actualizar a Microsoft Business de 365 todavía. 
  
## <a name="add-microsoft-365-business-licenses"></a>Agregar licencias de Microsoft 365 empresarial

Tiene dos maneras de obtener Microsoft 365 empresarial. Si dispone de un socio, navegará puede comprar Microsoft 365 empresarial para usted desde el [Centro de socio de Microsoft](get-microsoft-365-business.md). Su socio también puede ayudar a la transición a Microsoft 365 empresarial.
  
Si administra su propia suscripción, puede [ponerse en contacto con ventas](https://www.microsoft.com/microsoft-365/business) para adquirir licencias de Microsoft 365 empresarial. 
  
Vea el tema [Agregar, cambiar o eliminar a un socio de Asesor de suscripción](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) para averiguar cómo puede comenzar a trabajar con un socio. 
  
Si se le da un vínculo a sus licencias de compra, le guiará a través de un asistente como la siguiente. Elija **Sí, agregarlo a mi cuenta**. También puede seleccionar el número de licencias y el método de pago.
  
![En la empresa de 365 Microsoft directa comprar vínculo, elija Agregar a su cuenta actual, o suscribirse a una cuenta nueva.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Asignación de licencias de Microsoft 365

1. Una vez que han adquirido licencias nuevas y es la primera vez que se hizo, se mostrará la pancarta del programa de instalación para la empresa de 365 de Microsoft sobre el centro de administración.
    
    > [!NOTE]
    > El titular del programa de instalación es una oportunidad para agregar nuevos usuarios, un nuevo dominio y migrar correo electrónico para los nuevos usuarios. Si no planea realizar alguna, debe pasar por el asistente y elija opciones predeterminadas para hacer que desaparezca de la página principal de administración. 
  
   ![Elija el programa de instalación de inicio en la empresa de 365 Microsoft está listo para configurar la pancarta.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Seleccione **Iniciar configuración**.
    
2. En la página **Personalizar el inicio de sesión y correo electrónico** , puede agregar un dominio seleccionando **Conectar un dominio ya posee** si desea utilizar esta oportunidad para agregar otro dominio a su suscripción. 
    
    Si ya ha configurado un dominio, el segundo campo indicará que y dirá **continuar utilizando** \< _su nombre de dominio_ \> **para correo electrónico e inicio de sesión**. Si no ha configurado un dominio con suscripción, dirá **continuar utilizando** \< _su compañía nombre.onmicrosoft.com_ \> **para correo electrónico e inicio de sesión**.    
    
    Elija **Siguiente**.
    
    ![En la página de correo electrónico y personalizar el inicio de sesión de, elija Agregar un dominio, o utilice el que ha estado utilizando.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. En la página **Agregar nuevos usuarios** , puede agregar nuevos usuarios, si tiene nuevos empleados que desea asignar las licencias de Microsoft 365 Business a. 
    
    Si no dispone de nuevos empleados para agregar y desea asignar licencias a los usuarios existentes, elija **siguiente**.
    
4. En el ** migrar mensajes de correo electrónico ** página puede elegir para migrar el correo electrónico para cualquiera de los nuevos usuarios que agregó en el paso 3. También puede omitir este paso. Elija **siguiente**.
    
5. En la última página, elija **Ir al centro de administración**y continuar con la instalación no existe.
    
6. En el centro de administración, vaya a **los usuarios** \> **usuarios activos**.
    
7. Seleccione el usuario a quien desea asignar la licencia de **Microsoft Business de 365** para y, a continuación, elija **Editar** junto a **Licencias de producto**.
    
    ![En la tarjeta de usuario, elija Editar junto a licencias de producto.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. En **las licencias de producto** de diapositiva **Microsoft 365 Business** **activado** \> **Guardar**y, a continuación, en **Cerrar**.
    
Una vez que ha adquirido la licencia inicial para la empresa de 365 de Microsoft, ahora también puede agregar de en más **de facturación** \> **Servicios de compra**. En la página **Servicios de compra** puede haga clic en los puntos suspensivos en la tarjeta de **Presentación de 365 de Microsoft** y elija **cambie la cantidad de licencia** a comprar más. 
  
## <a name="protect-user-devices-and-files"></a>Proteger los archivos y los dispositivos de usuario

Después de que tengan licencias asignadas a Microsoft 365 empresarial, puede iniciar la protección de dispositivos y archivos de los usuarios.
  
1. En el centro de administración, en el panel de navegación izquierdo, vaya a **dispositivos** \> **directivas**.
    
2. En la página de **directivas de dispositivo** , elija **Agregar**.
    
3. En el panel **Agregar directiva** dé un nombre a la directiva y, a continuación, elija un **tipo de directiva** de la lista desplegable. 
    
    Puede configurar las directivas de aplicación para la protección de archivos en los dispositivos iPhone y Android, así como 10 de Windows, y puede configurar las directivas de configuración de dispositivo para la empresa que pertenecen a los dispositivos de Windows 10. Consulte los siguientes vínculos para obtener más información:
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Establecer la configuración de protección de dispositivos para equipos con Windows 10](protection-settings-for-windows-10-pcs.md)
    
   ![En el panel Agregar directiva, escriba un nombre para el mismo y elija el tipo de directiva en el menú desplegable.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. Una vez que la configuración de directivas, usted y sus empleados pueden configurar dispositivos:
    
  - Si las ventanas ya no están en la actualización de creador de profesionales de TI de Windows, debe [actualizarlas a los creadores de profesionales de TI de Windows Update](upgrade-to-windows-pro-creators-update.md).
    
  - Para ver los pasos para los dispositivos de Windows, vea [configurar los dispositivos de Windows para los usuarios de Microsoft Business de 365](set-up-windows-devices.md) . 
    
  - Los pasos de teléfonos Android e iPhone, vea [Configurar dispositivos móviles para los usuarios de Microsoft Business de 365](set-up-mobile-devices.md) . 
    
5. Para instalar automáticamente las aplicaciones cliente de Office, consulte [Prepare para una implementación de cliente de Office mediante Microsoft 365 Business](prepare-for-office-client-deployment.md) e [instalar o desinstalar Office en dispositivos de Windows 10 automáticamente](auto-install-or-uninstall-office.md).
    


