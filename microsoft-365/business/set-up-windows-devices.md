---
title: Configurar dispositivos con Windows para usuarios de Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Obtenga información sobre cómo configurar dispositivos Windows que ejecuten Windows 10 Pro para usuarios de Microsoft 365 Business, lo que permite controles de seguridad y administración centralizados.
ms.openlocfilehash: 6ecc45f825a783d9d47c4b069a6021143d96597c
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561168"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Configurar dispositivos con Windows para usuarios de Microsoft 365 Business

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-users"></a>Requisitos previos para configurar dispositivos Windows para usuarios profesionales de Microsoft 365

Para poder configurar dispositivos Windows para los usuarios de Microsoft 365 Business, asegúrese de que todos los dispositivos Windows estén ejecutando la versión 1703 de Windows 10 Pro (Creators Update). Windows 10 Pro es un requisito previo para implementar Windows 10 Business, que es un conjunto de servicios en la nube y funciones de administración de dispositivos que funciona como complemento de Windows 10 Pro y, además, proporciona una administración centralizada y controles de seguridad de Microsoft 365 Business.
  
Si tiene dispositivos Windows que ejecutan Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, su suscripción de Microsoft 365 Business le permite hacer una actualización a Windows 10.
  
Para obtener más información sobre cómo actualizar los dispositivos Windows a Windows 10 Pro Creators Update, siga los pasos indicados en este tema: [Actualizar dispositivos Windows a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md)
  
Consulte [comprobar que el dispositivo está conectado a Azure ad](#verify-the-device-is-connected-to-azure-ad) para comprobar que tiene la actualización o para asegurarse de que la actualización ha funcionado.

Vea un breve vídeo sobre cómo conectar Windows a Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Unir dispositivos Windows 10 en la cuenta de Azure AD de una organización

Cuando todos los dispositivos Windows de su organización se hayan actualizado a Windows 10 Pro Creators Update o ya ejecuten la actualización de Windows 10 Pro Creators, puede unir estos dispositivos al Azure Active Directory de la organización. Una vez que se hayan unido los dispositivos, se actualizarán automáticamente a Windows 10 Business, que forma parte de su suscripción de Microsoft 365 empresa.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Dispositivos Windows 10 Pro nuevos o actualizados recientemente

En el caso de los dispositivos nuevos que ejecuten Windows 10 Pro Creators Update, o en el de los dispositivos que se hayan actualizado a dicho producto pero no hayan pasado por el proceso de configuración de dispositivos Windows 10, siga estos pasos.
  
1. Siga el proceso de configuración de dispositivos Windows 10 hasta que llegue a la página **¿Cómo quiere realizar la configuración?**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Elija **Configurar para una organización** y, después, escriba el nombre de usuario y contraseña de Microsoft 365 Business. 
    
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
  
6. En la página Asegúrese de que **es su organización** , compruebe que la información es correcta y haga clic en **unirse**.
  
   En la página **Listo**, haga clic en **Listo**.
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Si ha cargado archivos a OneDrive para la Empresa, vuelva a sincronizarlos. Si ha usado una herramienta de terceros para migrar perfiles y archivos, sincronice también los archivos con el nuevo perfil.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Comprobar que un dispositivo está conectado a Azure AD

Para comprobar el estado de sincronización, en la página **Obtener acceso a trabajo o escuela** de **Configuración**, haga clic en el área **Conectado a** _ \<organization name\> _ para mostrar los botones **Información** y **Desconectar**. Haga clic en **Información** para obtener el estado de sincronización. 
  
En la página Estado de sincronización, haga clic en Sincronizar para recibir las directivas de administración de dispositivos móviles más recientes en el equipo.
  
Para empezar a usar la cuenta de Microsoft 365 Business, vaya al botón **Inicio** de Windows, haga clic con el botón secundario en la imagen de cuenta actual y, a continuación, **cambie de cuenta**. Inicie sesión con el correo electrónico y la contraseña de la organización.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Comprobar que un dispositivo está actualizado a Windows 10 Business

Compruebe que los dispositivos Windows 10 unidos a Azure AD se hayan actualizado a Windows 10 Business como parte de una suscripción a Microsoft 365 Business.
  
1. Vaya a **Configuración** \> **Sistema** \> **Acerca de**.
    
2. Confirme que la **Edición** es **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Pasos siguientes

Para configurar dispositivos móviles, vea [Configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md). Para establecer las directivas de protección de dispositivos o de aplicaciones, consulte [Administrar Microsoft 365 Business](manage.md).
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business"></a>Para obtener más información sobre la configuración y el uso de Microsoft 365 Business

[Vídeos de aprendizaje de Microsoft 365 Empresa](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
