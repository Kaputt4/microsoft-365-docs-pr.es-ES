---
title: Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Aprende a crear, editar o eliminar una directiva de administración de aplicaciones y a proteger archivos de trabajo en dispositivos Android o iOS.
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580302"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS

Este artículo se aplica a Microsoft 365 Empresa Premium.

## <a name="create-an-app-management-policy"></a>Crear una directiva de administración de aplicaciones

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. En la navegación izquierda, elija **Directivas de** \>  \> **dispositivos Agregar**.
  
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
    
4. En **Tipo de directiva,** elija **Administración de aplicaciones** para Android o Administración de aplicaciones para **iOS,** en función del conjunto de directivas que desee crear. 
    
5. Expande **Proteger archivos de trabajo cuando se pierden o** roban dispositivos y Administrar cómo los usuarios acceden Office archivos en **dispositivos móviles.** Configure las opciones de configuración que le gustarían. **Administrar cómo los usuarios acceden Office archivos** en dispositivos móviles está  desactivado de forma predeterminada, pero se recomienda activarlo y aceptar los valores predeterminados.  Para obtener más información, vea [Configuración disponible](#available-settings). 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no desea usar el  grupo de seguridad predeterminado Todos los usuarios, elija Cambiar **,** elija los grupos de seguridad que obtienen esta configuración \> **Seleccione**.
    
7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 
    
## <a name="edit-an-app-management-policy"></a>Editar una directiva de administración de aplicaciones

1. En la **tarjeta Directivas,** elija **Editar directiva**.
    
2. En el panel **Editar directiva**, seleccione la directiva que quiere cambiar. 
    
3. Elija **Editar** junto a cada configuración para cambiar los valores de la directiva. Al cambiar un valor, se guarda automáticamente en la directiva.
    
4. Cuando haya terminado, cierre el **panel Editar directiva.** 
    
## <a name="delete-an-app-management-policy"></a>Eliminar una directiva de administración de aplicaciones

1. En la **página Directivas,** elija una directiva y, a continuación, **Elimine**.
    
2. En el **panel Eliminar directiva,** elija **Confirmar** para eliminar la directiva o directivas que eligió. 
    
## <a name="available-settings"></a>Configuración disponible

En las tablas siguientes se proporciona información detallada acerca de la configuración disponible para proteger los archivos de trabajo en dispositivos y la configuración que controla la forma en que los usuarios acceden Office archivos desde sus dispositivos móviles.
  
 Para obtener más información, [vea How do protection features in Microsoft 365 Empresa Premium map to Intune settings](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Opciones de configuración que protegen los archivos de trabajo

Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días  <br/> |Si un dispositivo no se usa durante el número de días que especifiques aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.  <br/> |
|Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa  <br/> |Si esta configuración es **On**, la única ubicación de guardado disponible para los archivos de trabajo es OneDrive para la Empresa.  <br/> |
|Cifrar los archivos de trabajo  <br/> |Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo. Incluso si el dispositivo se pierde o se roba, nadie puede leer los datos de la empresa.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles

Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:
  
|||
|:-----|:-----|
|Configuración  <br/> |Descripción  <br/> |
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  <br/> |Si esta configuración es **On,** los usuarios deben proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar Office aplicaciones en sus dispositivos móviles.<br/> |
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  <br/> |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  <br/> |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  <br/> |Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que inicie sesión de nuevo.  <br/> |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  <br/> |Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.  <br/> |
|No permitir que los usuarios copien contenido de aplicaciones Office en aplicaciones personales  <br/> |Se permite de manera predeterminada, pero si la configuración está **activada**, el usuario podría copiar información de un archivo de trabajo en uno personal. Si la configuración está **desactivada**, el usuario no podrá copiar información de una cuenta de trabajo a una aplicación o cuenta personales.  <br/> |
