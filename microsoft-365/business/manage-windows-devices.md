---
title: Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Obtenga información sobre cómo habilitar Microsoft 365 para proteger dispositivos locales Unidos a Windows 10.
ms.openlocfilehash: 661e5bf8205a661eb4382b4bdd8fcf3a54ecc12f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660365"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local. Para configurar esto primero, sincronice Active Directory con Azure Active Directory y, a continuación, registre los dispositivos Windows 10 con Azure AD y Inscríbase para la administración de dispositivos móviles en Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Configurar dispositivos Unidos a un dominio para que los administre Microsoft 365 Business

Para configurar los dispositivos Unidos a un dominio de su organización con el fin de beneficiarse de las funciones que ofrece Azure Active Directory además de Active Directory local, puede implementar **dispositivos híbridos de Azure ad híbridos**. Se trata de dispositivos que se unen a la implementación local de Active Directory y a Azure Active Directory. Microsoft 365 Business puede proteger y administrar los dispositivos de Azure AD Unidos híbridos. 
  
Complete los pasos siguientes para que los dispositivos con Windows 10 Hybrid Azure AD se unan y administren con Microsoft 365 Business.
  
1. Para sincronizar los usuarios, los grupos y los contactos de Active Directory local a Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure Active Directory Connect como se describe en [configurar la sincronización de directorios para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > Los pasos son exactamente iguales para Microsoft 365 Business. 
  
2. Antes de completar el paso 3 para habilitar los dispositivos Windows 10 para que sean Unidos a Azure AD híbrido, debe asegurarse de que cumple los siguientes requisitos previos:

   - Está ejecutando la última versión de Azure AD Connect.

   - Azure AD Connect ha sincronizado todos los objetos de equipo de los dispositivos que desea que sean Unidos a Azure AD híbrido. Si los objetos de equipo pertenecen a unidades organizativas específicas (OU), asegúrese de que estas ou estén configuradas para la sincronización en Azure AD Connect también.
    
3. Registrar los dispositivos existentes de Windows 10 Unidos a un dominio para que estén Unidos a Azure AD híbridos e inscribirlos para la administración de dispositivos móviles mediante Intune (Microsoft 365 Business):
    
4. Siga las instrucciones paso a paso sobre [Cómo configurar los dispositivos Unidos de Azure Active Directory híbridos](https://go.microsoft.com/fwlink/p/?linkid=872870). Esto permitirá la sincronización de los equipos Windows 10 locales Unidos a través de Active Directory y los pondrá a disposición en la nube.
    
5. Para inscribir un dispositivo con Windows 10 para la administración de dispositivos móviles, consulte [inscribir un dispositivo con Windows 10 con Intune mediante una directiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obtener instrucciones. Puede establecer la Directiva de grupo en el nivel de equipo local o en operaciones masivas, puede crear esta opción de directiva de grupo en el servidor del controlador de dominio.