---
title: Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Obtenga información sobre cómo crear, editar o eliminar una directiva de administración de aplicaciones y proteger los archivos de trabajo en dispositivos Android o iOS.
ms.openlocfilehash: e81ff8a4bd71dbbbf7ccc31249d450e03f4bd241
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277467"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS

## <a name="create-an-app-management-policy"></a>Crear una directiva de administración de aplicaciones

1. Inicie sesión en el [centro de administración de Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=837890) con credenciales de administrador global. 
    
2. En el centro de administración, elija **directivas** \> de **dispositivos** \> **Agregar Directiva**.
  
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
    
4. En **Tipo de directiva**, elija **Administración de aplicaciones para Android** o **Administración de aplicaciones para iOS** según el conjunto de directivas que quiera crear. 
    
5. Expanda **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo** y **Administrar la forma en la que los usuarios tienen acceso a los archivos de Office en dispositivos móviles** \> configure las opciones como quiera. La opción **Administrar la forma en que los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** está **desactivada** de forma predeterminada, pero se recomienda que la **active** y acepte los valores predeterminados. Vea [available Settings](#available-settings) para obtener más información. 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> **Seleccionar**.
    
7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 
    
## <a name="edit-an-app-management-policy"></a>Editar una directiva de administración de aplicaciones

1. En la tarjeta **directivas** , elija **Editar Directiva**.
    
2. En el panel **Editar directiva**, seleccione la directiva que quiere cambiar. 
    
3. Elija **Editar** junto a cada configuración para cambiar los valores de la directiva. Cuando cambia un valor, se guarda automáticamente en la directiva. 
    
4. Cuando haya terminado, cierre el panel **Editar directiva**. 
    
## <a name="delete-an-app-management-policy"></a>Eliminar una directiva de administración de aplicaciones

1. En la tarjeta **Directivas**, seleccione **Eliminar directiva**.
    
2. En el panel **Eliminar directiva**, elija las directivas que quiere eliminar \> **Seleccionar** y después **Confirmar** para eliminar la directiva o las directivas que haya elegido. 
    
## <a name="available-settings"></a>Configuración disponible

En las siguientes tablas, se ofrece información detallada sobre la configuración disponible para proteger los archivos de trabajo en dispositivos y la configuración que controla la forma en que los usuarios obtienen acceso a archivos de Office desde sus dispositivos móviles.
  
 Consulte [Cómo se asignan las características de protección de Microsoft 365 Empresa a la configuración de Intune](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Configuración que protegen los archivos de trabajo

Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días  <br/> |Si un dispositivo no se usa durante el número de días que especifique aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.  <br/> |
|Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa  <br/> |Si esta configuración está **activada**, la única ubicación de almacenamiento disponible para los archivos de trabajo será OneDrive para la Empresa.  <br/> |
|Cifrar los archivos de trabajo  <br/> |Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo. Incluso en caso de pérdida o robo del dispositivo, nadie podrá leer los datos de la compañía.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configuraciones que controlan la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles

Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  <br/> |Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar aplicaciones de Office en su dispositivo móvil.  <br/> |
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  <br/> |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  <br/> |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  <br/> |Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.  <br/> |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  <br/> |Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  <br/> |
|Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales  <br/> |Se permite de manera predeterminada, pero si la configuración está **activada**, el usuario podría copiar información de un archivo de trabajo en uno personal. Si la configuración está **desactivada**, el usuario no podrá copiar información de una cuenta de trabajo a una aplicación o cuenta personales.  <br/> |
   

  

