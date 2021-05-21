---
title: Configurar dispositivos Windows para Microsoft 365 Empresa Premium usuarios
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Configure los dispositivos Windows que ejecutan Windows 10 Pro para Microsoft 365 Empresa Premium usuarios, lo que habilita controles de seguridad y administración centralizados.
ms.openlocfilehash: 3d32a033a1a1c89d7d4d557cea6a28e24543ab2c
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594029"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Configurar dispositivos Windows para Microsoft 365 Empresa Premium usuarios

## <a name="before-you-begin"></a>Antes de empezar

Antes de configurar Windows dispositivos para Microsoft 365 Empresa Premium usuarios, asegúrese de que todos los dispositivos Windows están ejecutando Windows 10 Pro, versión 1703 (Creators Update). Windows 10 Pro es un requisito previo para implementar Windows 10 Business, que es un conjunto de servicios en la nube y capacidades de administración de dispositivos que complementan Windows 10 Pro y habilitan la administración centralizada y los controles de seguridad de Microsoft 365 Empresa Premium.
  
Si tienes dispositivos Windows que ejecutan Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, la suscripción Microsoft 365 Empresa Premium te da derecho a una actualización Windows 10.
  
Para obtener más información sobre cómo actualizar los dispositivos Windows a Windows 10 Pro Creators Update, siga los pasos indicados en este tema: [Actualizar dispositivos Windows a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)
  
Consulta [Comprobar que el dispositivo está conectado a Azure AD](#verify-the-device-is-connected-to-azure-ad) para comprobar que tienes la actualización o para asegurarte de que la actualización ha funcionado.

Vea un breve vídeo sobre cómo conectar Windows a Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../business-video/index.yml).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Unir dispositivos Windows 10 en la cuenta de Azure AD de una organización

Cuando todos los dispositivos Windows de su organización se hayan actualizado a Windows 10 Pro Creators Update o ya estén ejecutando Windows 10 Pro Creators Update, puede unir estos dispositivos a los Azure Active Directory. Una vez que se unen los dispositivos, se actualizarán automáticamente a Windows 10 Business, que forma parte de la Microsoft 365 Empresa Premium suscripción.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Dispositivos Windows 10 Pro nuevos o actualizados recientemente

En el caso de los dispositivos nuevos que ejecuten Windows 10 Pro Creators Update, o en el de los dispositivos que se hayan actualizado a dicho producto pero no hayan pasado por el proceso de configuración de dispositivos Windows 10, siga estos pasos.
  
1. Siga el proceso de configuración de dispositivos Windows 10 hasta que llegue a la página **¿Cómo quiere realizar la configuración?**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Aquí, elija **Configurar para una organización** y, a continuación, escriba su nombre de usuario y contraseña para Microsoft 365 Empresa Premium. 
    
3. Finalice la configuración del dispositivo Windows 10.
    
   Una vez que haya terminado, el usuario se conectará a la cuenta de Azure AD de su organización. Para asegurarse de que la configuración es correcta, consulte [Comprobar que un dispositivo está conectado a Azure AD](#verify-the-device-is-connected-to-azure-ad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Dispositivos ya configurados con Windows 10 Pro

 **Conectar usuarios a Azure AD:**
  
1. En el equipo Windows del usuario, que está ejecutando Windows 10 Pro, versión 1703 (Creators Update) (vea [Requisitos previos](pre-requisites-for-data-protection.md)), haga clic en el logotipo de Windows y, después, en el icono Configuración.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. En **Configuración**, vaya a **Cuentas**.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. En la página **Tu información**, haga clic en **Obtener acceso a trabajo o escuela** \> **Conectar**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. En el cuadro de diálogo **Configurar una cuenta de trabajo o escuela**, en **Acciones alternativas**, elija **Unir este dispositivo a Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. En la página **Vamos a iniciar sesión**, escriba su cuenta profesional o educativa \> **Siguiente**.
  
   En la página **Escribir contraseña**, escriba la contraseña \> **Iniciar sesión**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. En la **página Asegúrese de que esta es su organización,** compruebe que la información es correcta y elija **Unirse.**
  
   En el **conjunto You're all!** page, chosse **Done**.
  
   ![En la pantalla Asegúrese de que esta es su organización, elija Unirse](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Si ha cargado archivos a OneDrive para la Empresa, vuelva a sincronizarlos. Si usó una herramienta de terceros para migrar perfiles y archivos, sincronice también los con el nuevo perfil.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Comprobar que un dispositivo está conectado a Azure AD

Para comprobar el estado  de sincronización, en la página Acceso al trabajo o escuela de **Configuración**, seleccione el área Conectado a **_** _ para exponer los botones \<organization name\> **Información** y **Desconectar**. Elige **Información** para obtener el estado de sincronización. 
  
En la **página Estado de sincronización,** elija **Sincronizar** para obtener las directivas de administración de dispositivos móviles más recientes en el equipo.
  
Para empezar a usar la cuenta Microsoft 365 Empresa Premium, vaya  al botón Inicio Windows, haga clic con el botón secundario en la imagen de la cuenta actual y, a continuación, **Cambie cuenta**. Inicie sesión con el correo electrónico y la contraseña de la organización.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Comprobar que el equipo se actualiza a Windows 10 Business

Compruebe que los dispositivos unidos Windows 10 Azure AD se actualicen a Windows 10 Business como parte de su Microsoft 365 Empresa Premium suscripción.
  
1. Vaya a **Configuración** \> **Sistema** \> **Acerca de**.
    
2. Confirme que la **Edición** es **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Pasos siguientes

Para configurar los dispositivos móviles, consulta Configurar dispositivos móviles para usuarios de [Microsoft 365 Empresa Premium](set-up-mobile-devices.md), Para establecer directivas de protección de dispositivos o protección de aplicaciones, consulta Administrar [Microsoft 365 para empresas.](manage.md)
  
## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 vídeos de aprendizaje para empresas](../business-video/index.yml) (página de vínculos)
