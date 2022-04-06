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
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
ms.openlocfilehash: 8965f70a19161be24f4276b8dac20c84865d9a71
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635449"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS

Este artículo se aplica a Microsoft 365 Business Premium.

> [!NOTE]
> Microsoft Defender für Unternehmen se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../business-premium/m365bp-app-protection-settings-for-android-and-ios.md).

## <a name="watch-secure-office-apps-on-ios"></a>Watch: Secure Office apps on iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión y también cifre los archivos de trabajo almacenados en sus dispositivos.

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>.

2. En **Directivas**, elija **Agregar directiva**.

3. En el **panel Agregar directiva** , escriba un nombre en **Nombre** de directiva y elija el tipo de directiva que desee en **Tipo de directiva**.

4. Activa Administrar **cómo los usuarios acceden Office archivos en** dispositivos móviles y, a continuación, asegúrate de que las tres opciones de configuración siguientes estén activadas:
 
    - **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**
 
    - **Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**
 
    - **Cifrar archivos de trabajo**

5. En **Archivos de estas aplicaciones se protegerán**, selecciona las Office que quieras proteger en dispositivos móviles.

6. En **Quién se obtienen estas** opciones de configuración, todos los usuarios están seleccionados de forma predeterminada, pero puede  elegir Cambiar para seleccionar los grupos de seguridad que haya creado.

7. Para terminar de crear la directiva, elija **Agregar**.

8. En la **página Agregar directiva** , elija **Cerrar**.

9. En la página principal del Centro de administración, confirme que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.

## <a name="create-an-app-management-policy"></a>Crear una directiva de administración de aplicaciones

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. En el panel de navegación izquierdo, elija **Agregar directivas** \> **de** \> **dispositivos**.
  
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
    
4. En **Tipo de directiva**, elija **Administración de aplicaciones para Android** o Administración de aplicaciones para **iOS**, según el conjunto de directivas que desee crear. 
    
5. **Expande Proteger archivos de trabajo cuando se pierden o** roban dispositivos y administrar cómo los usuarios **acceden Office archivos en dispositivos móviles**. Configure las opciones de configuración que le gustarían. **Administrar cómo los usuarios acceden Office archivos** en dispositivos móviles  está desactivado de forma predeterminada, pero se recomienda activarlo  y aceptar los valores predeterminados. Para obtener más información, consulte [Configuración disponible](#available-settings). 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Captura de pantalla de Crear una directiva con la administración de aplicaciones para Android seleccionada.](/media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no desea usar el grupo de seguridad predeterminado **Todos** los usuarios, elija Cambiar **, elija** los grupos de seguridad que obtienen esta configuración \> **Seleccionar**.
    
7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 
    
## <a name="edit-an-app-management-policy"></a>Editar una directiva de administración de aplicaciones

1. En la **tarjeta Directivas** , elija **Editar directiva**.
    
2. En el panel **Editar directiva**, seleccione la directiva que quiere cambiar. 
    
3. Elija **Editar** junto a cada configuración para cambiar los valores de la directiva. Al cambiar un valor, se guarda automáticamente en la directiva.
    
4. Cuando haya terminado, cierre el **panel Editar directiva** . 
    
## <a name="delete-an-app-management-policy"></a>Eliminar una directiva de administración de aplicaciones

1. En la **página Directivas** , elija una directiva y, a continuación **, Eliminar**.
    
2. En el **panel Eliminar directiva** , elija **Confirmar** para eliminar la directiva o directivas que eligió. 
    
## <a name="available-settings"></a>Configuración disponible

En las tablas siguientes se proporciona información detallada acerca de la configuración disponible para proteger los archivos de trabajo en dispositivos y la configuración que controla cómo los usuarios tienen acceso Office archivos desde sus dispositivos móviles.
  
 Para obtener más información, vea [How do protection features in Microsoft 365 Business Premium map to Intune settings](m365bp-map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Opciones de configuración que protegen los archivos de trabajo

Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:


|Valor  |Descripción  |
|:-----|:-----|
|Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días  |Si un dispositivo no se usa durante el número de días que especifiques aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.  |
|Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa  |Si esta configuración es **On**, la única ubicación de guardado disponible para los archivos de trabajo es OneDrive Entreprise.  |
|Cifrar los archivos de trabajo  |Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo. Incluso si el dispositivo se pierde o se roba, nadie puede leer los datos de la empresa.  |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles

Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:


|Valor  |Descripción  |
|:-----|:-----|
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  |Si esta configuración es **On**, los usuarios deben proporcionar otra forma de autenticación, además de su nombre de usuario y contraseña, para poder usar Office aplicaciones en sus dispositivos móviles.|
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  |Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que inicie sesión de nuevo.  |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  |Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.    |
|No permitir que los usuarios copien contenido de Office aplicaciones en aplicaciones personales  |Se permite de manera predeterminada, pero si la configuración está **activada**, el usuario podría copiar información de un archivo de trabajo en uno personal. Si la configuración está **desactivada**, el usuario no podrá copiar información de una cuenta de trabajo a una aplicación o cuenta personales.  |

## <a name="see-also"></a>Vea también

[Principales 10 formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)