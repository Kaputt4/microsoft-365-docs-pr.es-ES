---
title: Migrar a Microsoft 365 Business desde Office 365 empresa Premium
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
description: Obtenga información sobre cómo mover su empresa a Microsoft 365 Business.
ms.openlocfilehash: ae9ca0fe97916fdae6104a6edbb04efba5d9299e
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575886"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migrar a Microsoft 365 Business desde Office 365 empresa Premium

Si ya tiene una suscripción de Office 365 para empresas, por ejemplo, Office 365 empresa Premium, puede agregar fácilmente licencias a Microsoft 365 Business y asignarlas a algunos o a todos los usuarios.
  
> [!NOTE]
> No puede usar el botón [cambiar de plan](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) para actualizar a Microsoft 365 Business todavía. 
  
## <a name="add-microsoft-365-business-licenses"></a>Agregar licencias de Microsoft 365 empresa

Tiene dos maneras de obtener Microsoft 365 Business. Un socio puede comprar Microsoft 365 Business para usted desde el [centro de Partners de Microsoft](get-microsoft-365-business.md). Su compañero también puede ayudarle a realizar la transición a Microsoft 365 Business.
  
Si administra su propia suscripción, puede [ponerse en contacto con sales](https://www.microsoft.com/microsoft-365/business) para comprar licencias de Microsoft 365 Business. 
  
Consulte [Agregar, cambiar o eliminar un partner Asesor de suscripción](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) para averiguar cómo puede empezar a trabajar con un partner. 
  
Si recibe un vínculo para comprar las licencias, le guiará por un asistente como el que se muestra a continuación. Elija **sí, agregar a mi cuenta**. También puede elegir el número de licencias y el método de pago.
  
![En el vínculo comprar a Microsoft 365 Business Direct, elija Agregar a su cuenta actual o regístrese para obtener una nueva cuenta.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Asignar licencias de 365 de Microsoft

1. Una vez que haya adquirido licencias nuevas y esta es la primera vez que lo hizo, el banner de configuración de Microsoft 365 Business se mostrará en la parte superior del centro de administración.
    
    > [!NOTE]
    > El banner de configuración es una oportunidad para agregar nuevos usuarios, un nuevo dominio y migrar el correo electrónico de los nuevos usuarios. Si no tiene previsto realizar ninguna, debe seguir adelante con el asistente y elegir opciones predeterminadas para que desaparezca de la Página principal de administración. 
  
   ![Elija Iniciar configuración en Microsoft 365 Business está preparado para configurar la pancarta.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Seleccione **Iniciar configuración**.
    
2. En la página **personalizar el inicio de sesión y el correo electrónico** , puede Agregar un dominio si elige **conectar un dominio que ya posee** si desea usar esta oportunidad para agregar otro dominio a la suscripción. 
    
    Si ya ha configurado un dominio, el segundo campo indicará que y **seguirá usando** \< _su nombre_ \> **de dominio para el correo electrónico y el inicio de sesión**.   Si no ha configurado un dominio con su suscripción, dirá **seguir usando** \< _su empresa Name.onmicrosoft.com_ \> **para el correo electrónico y el inicio de sesión**.  
    
    Elija **Siguiente**.
    
    ![En la página personalizar el inicio de sesión y el correo electrónico, elija entre agregar un dominio o usar el que ha estado usando.](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. En la página **agregar nuevos usuarios** , puede agregar nuevos usuarios si tiene empleados nuevos a los que desea asignar licencias de Microsoft 365 Business. 
    
    Si no tiene empleados nuevos para agregar y desea asignar licencias a los usuarios existentes, elija **siguiente**.
    
4. En la página * * migrar mensajes de correo electrónico * *, puede elegir migrar el correo electrónico de cualquiera de los nuevos usuarios que agregó en el paso 3. También puede omitir este paso. Elija **Siguiente**.
    
5. En la última página, elija **ir al centro de administración**y continúe con la instalación.
    
6. En el centro de administración, vaya a **usuarios** \> **activos**.
    
7. Seleccione el usuario al que desea asignar la licencia de **Microsoft 365 Business** y, a continuación, elija **Editar** junto a **licencias de producto**.
    
    ![En la tarjeta de usuario, elija Editar junto a licencias de productos.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. En la diapositiva licencias de **producto** , **Microsoft 365 empresa** **para** \> **Guardar**y, después, **cierre**.
    
Una vez que haya adquirido la licencia inicial para Microsoft 365 Business, ahora podrá agregar más en **servicios de compra**de **facturación** \> . En la página **servicios de compra** , puede hacer clic en los puntos suspensivos de la tarjeta de presentación de **Microsoft 365** y elegir **cambiar cantidad de licencia** para comprar más. 
  
## <a name="protect-user-devices-and-files"></a>Proteger los archivos y dispositivos de usuario

Una vez que haya asignado las licencias a Microsoft 365 Business, puede empezar a proteger los dispositivos y archivos de los usuarios.
  
1. En el centro de administración, en el panel de navegación izquierdo, vaya a **directivas**de **dispositivos** \> .
    
2. En la página **directivas de dispositivos** , elija **Agregar**.
    
3. En el panel **Agregar Directiva** , asigne un nombre a la Directiva y, a continuación, elija un **tipo de directiva** en la lista desplegable. 
    
    Puede configurar directivas de aplicación para proteger los archivos en dispositivos Android y iPhone, así como en Windows 10, y puede configurar directivas de configuración de dispositivo para dispositivos Windows 10 que pertenecen a la empresa. Consulte los siguientes vínculos para obtener más información:
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Establecer la configuración de protección de dispositivos para equipos con Windows 10](protection-settings-for-windows-10-pcs.md)
    
   ![En el panel agregar Directiva, escriba un nombre para el mismo y elija el tipo de directiva en el menú desplegable.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. Una vez que haya configurado las directivas, usted y sus empleados podrán configurar dispositivos:
    
  - Si sus ventanas ya no están en la actualización del creador de Windows Pro, tendrá que [actualizarlas a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
    
  - Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para conocer los pasos para dispositivos Windows. 
    
  - Consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md) para conocer los pasos para Android Phones y iPhone. 
    
5. Para instalar automáticamente las aplicaciones cliente de Office, consulte [preparar la implementación del cliente de Office en Microsoft 365 Business](prepare-for-office-client-deployment.md) y [instalar o desinstalar automáticamente Office en dispositivos Windows 10](auto-install-or-uninstall-office.md).
    


