---
title: Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Obtenga información sobre cómo habilitar Microsoft 365 para proteger dispositivos locales Unidos a Windows 10.
ms.openlocfilehash: 452e884f952a4b2c2e87148bb7203ed48a48d944
ms.sourcegitcommit: 3a632d8ec009abf1aac57363eaf78aeeda5db136
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37376103"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business

Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local.
Para configurar esto, puede implementar **dispositivos híbridos de Azure ad híbridos**. Se trata de dispositivos que se unen a la implementación local de Active Directory y a Azure Active Directory.

En el vídeo siguiente se detallan los pasos para configurar esto para el escenario más común que también se detalla en los pasos siguientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. preparar la sincronización de directorios 

Antes de sincronizar los usuarios y los equipos desde el dominio local de Active Directory, revise [preparar la sincronización de directorios en Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). En particular:

   - Asegúrese de que no existen duplicados en el directorio para los siguientes atributos: **mail**, **proxyAddresses**y **userPrincipalName**. Estos valores deben ser únicos y se deben quitar todos los duplicados.
   
   - Se recomienda que el atributo **userPrincipalName** (UPN) de cada cuenta de usuario local esté configurado para coincidir con la dirección de correo electrónico principal que corresponde al usuario de Microsoft 365 con licencia. Por ejemplo *Mary.Shelley@contoso.com* en lugar de *María @ contoso. local*
   
   - Si el dominio de Active Directory termina en un sufijo no enrutable como *. local* o *. LAN*, en lugar de un sufijo enrutable de Internet como *. com* o. *org*, deberá ajustar primero el sufijo UPN de las cuentas de usuario locales como se describe en [Prepare un dominio no enrutable para la sincronización de directorios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. instalar y configurar Azure AD Connect

Para sincronizar los usuarios, los grupos y los contactos de Active Directory local con Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios. Consulte [configurar la sincronización de directorios para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para obtener más información.

> [!NOTE]
> Los pasos son exactamente iguales para Microsoft 365 Business. 

A medida que configure las opciones de Azure AD Connect, le recomendamos que habilite la **sincronización de contraseña** y el **Inicio de sesión único sin problemas**, así como la característica de **escritura diferida de contraseñas** , que también es compatible con Microsoft 365 Business.

> [!NOTE]
> Hay algunos pasos adicionales para la escritura diferida de contraseñas más allá de la casilla en Azure AD Connect. Para obtener más información, consulte [How-to: configure password reescritura](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. configurar una Unión híbrida de Azure AD

Antes de habilitar los dispositivos Windows 10 para que sean Unidos a Azure AD híbrido, debe asegurarse de que cumple los siguientes requisitos previos:

   - Está ejecutando la última versión de Azure AD Connect.

   - Azure AD Connect ha sincronizado todos los objetos de equipo de los dispositivos que desea que sean Unidos a Azure AD híbrido. Si los objetos de equipo pertenecen a unidades organizativas específicas (OU), asegúrese de que estas ou estén configuradas para la sincronización en Azure AD Connect también.

Para registrar los dispositivos existentes de Windows 10 Unidos a un dominio como Unidos de híbrido de Azure AD, siga los pasos descritos en el [Tutorial: configure Hybrid Azure Active Directory join for Managed Domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Esto habilitará el entorno híbrido existente de Active Directory conectado a equipos con Windows 10 y lo pondrá a disposición en la nube.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. habilitar la inscripción automática para Windows 10

 Para inscribir automáticamente dispositivos Windows 10 para la administración de dispositivos móviles en Intune, consulte [inscribir automáticamente un dispositivo con Windows 10 mediante la Directiva de grupo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Puede establecer la Directiva de grupo en el nivel de equipo local o en operaciones masivas, puede crear esta opción de directiva de grupo en el controlador de dominio con la consola de administración de directivas de grupo y las plantillas ADMX.

## <a name="5-configure-seamless-single-sign-on"></a>5. configurar el inicio de sesión único sin interrupciones

  El SSO sin problemas iniciará automáticamente la sesión de los usuarios en los recursos de nube de Microsoft 365 cuando usen equipos corporativos. Simplemente, implemente una de las dos opciones de directiva de grupo descritas en [Azure Active Directory de inicio de sesión único: Inicio rápido](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). La opción de **Directiva de grupo** no permite a los usuarios cambiar su configuración, mientras que la opción de preferencia de la **Directiva de grupo** establece los valores, pero también deja que el usuario los pueda configurar.

## <a name="6-set-up-windows-hello-for-business"></a>6. configurar Windows Hello para empresas

 Windows Hello para empresas reemplaza contraseñas con la autenticación segura en dos fases (2FA) para iniciar sesión en un equipo local. Un factor es un par de claves asimétricas y el otro es un PIN u otro movimiento local, como el reconocimiento facial o de la huella digital, si el dispositivo lo admite. Le recomendamos que reemplace las contraseñas con 2FA y Windows Hello para empresas siempre que sea posible.

Para configurar la implementación híbrida de Windows Hello para empresas, revise los [requisitos previos de confianza de clave híbrida de Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). A continuación, siga las instrucciones que se indican en [Configure Hybrid Windows Hello for Business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
