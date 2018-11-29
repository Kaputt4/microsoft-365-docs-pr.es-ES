---
title: Habilitar dispositivos de Windows 10 unido a un dominio administrado por Microsoft 365 empresarial
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Obtenga información sobre cómo habilitar Microsoft 365 proteger AD local se unió a dispositivos de Windows 10.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871308"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Habilitar dispositivos de Windows 10 unido a un dominio administrado por Microsoft 365 empresarial

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 empresarial para proteger los dispositivos de Windows 10, al tiempo que mantiene el acceso a los recursos locales que requieren autenticación local. Puede configurar esto mediante la primera sincronización de Active Directory con Azure Active Directory, seguido de registrar los dispositivos de Windows 10 con Azure AD y realizar una inscripción para administración de dispositivos móviles por Microsoft 365 empresarial.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Configurar dispositivos unido a un dominio para ser administrado por Microsoft 365 empresarial

Para configurar los dispositivos unido a un dominio de la organización para sacar partido de las funciones proporcionadas por Azure Active Directory además de Active Directory local, puede implementar **híbrida Azure AD se unió a dispositivos**. Estos son los dispositivos que se unen tanto a su Active Directory local y Azure Active Directory. Híbrido Azure AD se unió a dispositivos estén protegidos y administrados por Microsoft 365 Business.. 
  
Complete los pasos siguientes para hacer que los dispositivos de Windows 10 híbrida Azure AD Unido y administrados por Microsoft 365 empresarial.
  
1. Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, ejecute el Asistente para la sincronización de Active Directory y Azure Active Directory Connect tal como se describe en [Configurar la sincronización de Active directory para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Los pasos son exactamente los mismos para la empresa de Microsoft 365. 
  
2. Antes de completar el paso 3 para habilitar los dispositivos de Windows 10 para ser híbrida se unió Azure AD, debe asegurarse de que cumple los siguientes requisitos previos:
    
   - Está ejecutando la versión más reciente de Azure AD conectarse.
    
   - Conectar Azure AD se ha sincronizado con todos los objetos de equipo de los dispositivos que desea que sean híbrida se unió Azure AD. Si los objetos de equipo pertenecen a determinadas unidades organizativas (OU), a continuación, asegúrese de que estas unidades organizativas se establecen para la sincronización en Azure AD conectarse así como.
    
3. Registre los dispositivos de Windows 10 unido a un dominio existentes para ser híbrida se unió Azure AD y les inscribirse en administración de dispositivos móviles mediante Intune (Microsoft 365 Business):
    
4. Siga las instrucciones paso a paso [cómo configurar los dispositivos de Azure Active Directory se unió a híbrida](https://go.microsoft.com/fwlink/p/?linkid=872870). Esto permitirá que la sincronización de Active Directory local se unió a equipos Windows 10 y hacerlas está preparada para la nube.
    
5. Para poder inscribirse un dispositivo de Windows 10 para administración de dispositivos móviles, vea [inscribirse en un dispositivo de Windows 10 con Intune mediante el uso de una directiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obtener instrucciones. Puede establecer la directiva de grupo en un equipo local nivel o para las operaciones masivas, puede crear esta configuración de directiva de grupo en el servidor de controlador de dominio. 
    

