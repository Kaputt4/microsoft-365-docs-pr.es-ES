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
ms.localizationpriority: high
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
description: Obtenga información sobre cómo crear, editar o eliminar una directiva de administración de aplicaciones y proteger archivos de trabajo en dispositivos Android o iOS.
ms.openlocfilehash: 5f754803677809c91f8f4a64f6089b4febd47d3d
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65320047"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS

Este artículo aplica a Microsoft 365 Empresa Premium.

> [!NOTE]
> Microsoft Defender para Empresas se está implementando para los clientes de Microsoft 365 Empresa Premium desde el 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para los dispositivos. [Más información sobre Defender para Empresas](../business-premium/m365bp-app-protection-settings-for-android-and-ios.md).

## <a name="watch-secure-office-apps-on-ios"></a>Ver: Proteger las aplicaciones de Office en iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles introduzcan un PIN o una huella digital para iniciar sesión y, además, cifre los archivos de trabajo almacenados en sus dispositivos.

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>.

2. En **Directivas**, elija **Agregar directiva**.

3. En el panel **Agregar directiva**, escriba un nombre en **Nombre de directiva** y elija el tipo de directiva que desee en **Tipo de directiva**.

4. Active **Administrar la forma en que los usuarios obtienen acceso a archivos de Office en dispositivos móviles** y, a continuación, asegúrese de que las siguientes tres opciones estén activadas:
 
    - **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**
 
    - **Proteger los archivos de trabajo cuando se produzca extravío o robo de los dispositivos**
 
    - **Cifrar archivos de trabajo**

5. En **Los archivos de estas aplicaciones deben estar protegidos**, seleccione las aplicaciones de Office que quiere proteger en dispositivos móviles.

6. En **¿Quién recibirá esta configuración?**, la opción predeterminada es todos los usuarios, pero puede modificarlo en **Cambiar** para seleccionar los grupos de seguridad que ha creado.

7. Para terminar de crear la directiva, haga clic en **Agregar**.

8. En la página **Agregar directiva**, seleccione **Cerrar**.

9. En la página principal del centro de administración, confirme que se haya agregado la nueva directiva. Para ello, elija **Directivas** y revise la directiva en la página **Directivas**.

## <a name="create-an-app-management-policy"></a>Crear una directiva de administración de aplicaciones

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. En el panel de navegación izquierdo, elija **Dispositivos** \> **Directivas** \> **Agregar**.
  
3. En el panel **Agregar directiva**, escriba un nombre único para esta directiva. 
    
4. En **Tipo de directiva**, elija **Administración de aplicaciones para Android** o **Administración de aplicaciones para iOS**, según el conjunto de directivas que quiera crear. 
    
5. Expanda **Proteger los archivos de trabajo cuando se produzca extravío o robo de los dispositivos** y **Administrar cómo acceden los usuarios a los archivos de Office en dispositivos móviles**. Configure las opciones como lo desee. **Administrar cómo acceden los usuarios a los archivos de Office en dispositivos móviles** está **desactivado** de forma predeterminada, pero se recomienda **activarlo** y aceptar los valores predeterminados. Para obtener más información, vea [Configuración disponible](#available-settings). 
    
    Siempre puede usar el vínculo **Restablecer la configuración predeterminada** para volver a la configuración predeterminada. 
    
    ![Captura de pantalla de Crear una directiva con la opción Administración de aplicaciones para Android seleccionada.](/media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Después, decida **a qué usuarios se aplica esta configuración**. Si no quiere usar el grupo de seguridad predeterminado **Todos los usuarios**, elija **Cambiar**, elija los grupos de seguridad que recibirán esta configuración \> y **Seleccionar**.
    
7. Por último, elija **Listo** para guardar la directiva y asignarla a los dispositivos. 
    
## <a name="edit-an-app-management-policy"></a>Editar una directiva de administración de aplicaciones

1. En la tarjeta **Directivas**, elija **Editar directiva**.
    
2. En el panel **Editar directiva**, seleccione la directiva que quiere cambiar. 
    
3. Elija **Editar** junto a cada configuración para cambiar los valores de la directiva. Cuando se cambia un valor, se guarda automáticamente en la directiva.
    
4. Al acabar, cierre el panel **Editar directiva**. 
    
## <a name="delete-an-app-management-policy"></a>Eliminar una directiva de administración de aplicaciones

1. En la página **Directivas**, elija una directiva y, luego, **Eliminar**.
    
2. En el panel **Eliminar directiva**, elija **Confirmar** para eliminar la directiva o directivas que haya elegido. 
    
## <a name="available-settings"></a>Configuración disponible

En las tablas siguientes se proporciona información detallada sobre la configuración disponible para proteger los archivos de trabajo en los dispositivos y la configuración que controla la forma en que los usuarios acceden a los archivos de Office desde sus dispositivos móviles.
  
 Para obtener más información, consulte [Cómo se asignan las características de protección de Microsoft 365 Empresa Premium a la configuración de Intune](m365bp-map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Opciones de configuración que protegen los archivos de trabajo

Las siguientes opciones de configuración permiten proteger archivos de trabajo en caso de pérdida o robo del dispositivo de un usuario:


|Configuración  |Descripción  |
|:-----|:-----|
|Eliminar archivos de trabajo de un dispositivo inactivo después de este número de días  |Si un dispositivo no se usa durante la cantidad de días que especifique aquí, los archivos de trabajo almacenados en el dispositivo se eliminarán automáticamente.  |
|Exigir que los usuarios guarden todos los archivos de trabajo en OneDrive para la Empresa  |Si esta configuración está **activada**, la única ubicación de almacenamiento disponible para los archivos de trabajo será OneDrive para la Empresa.  |
|Cifrar los archivos de trabajo  |Mantenga **activada** esta opción para proteger con cifrado los archivos de trabajo. Incluso en caso de extravío o robo del dispositivo, nadie podrá leer los datos de la empresa.  |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configuración que controla cómo obtienen acceso los usuarios a los archivos de Office desde dispositivos móviles

Las siguientes opciones de configuración permiten administrar la forma en que los usuarios obtienen acceso a los archivos de trabajo de Office:


|Configuración  |Descripción  |
|:-----|:-----|
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  |Si esta configuración está **Activada**, los usuarios tienen que proporcionar otra forma de autenticación (además de su nombre de usuario y contraseña) para poder usar las aplicaciones de Office en su dispositivo móvil.|
|Restablecer el PIN cuando no se haya podido iniciar sesión el siguiente número de veces  |Para impedir que un usuario no autorizado adivine aleatoriamente un PIN, este se restablecerá después de que se escriba de forma errónea el número de veces que especifique.  |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante  |Esta configuración determina cuánto tiempo puede estar inactivo un usuario antes de que se le pida que vuelva a iniciar sesión.  |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  |Puede que algunos usuarios habilidosos tengan un dispositivo con jailbreak o rooting. Esto quiere decir que el usuario puede modificar el sistema operativo, lo que podría hacer que el dispositivo sea más vulnerable ante ataques de malware. Estos dispositivos se bloquean cuando esta configuración está **activada**.    |
|No permitir que los usuarios copien contenido de aplicaciones de Office en aplicaciones personales  |Se permite de forma predeterminada, pero si la configuración está **activada**, el usuario podría copiar información de un archivo de trabajo en uno personal. Si la configuración está **desactivada**, el usuario no podrá copiar información de una cuenta de trabajo en una aplicación o cuenta personales.  |

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)