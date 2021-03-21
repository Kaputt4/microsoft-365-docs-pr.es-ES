---
title: Proteger las cuentas de administrador global de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: En este artículo se proporciona información sobre cómo proteger el acceso de administrador global a su suscripción de Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ade5fd8070a656f976caa75c16ab92cadb7b64a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929053"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Proteger las cuentas de administrador global de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las infracciones de seguridad de una suscripción a Microsoft 365, incluidos los ataques de recolección de información y suplantación de identidad, suelen realizarse al poner en peligro las credenciales de una cuenta de administrador global de Microsoft 365. La seguridad en la nube es una asociación entre usted y Microsoft:
  
- Los servicios en la nube de Microsoft se basan en una base de confianza y seguridad. Microsoft le proporciona controles y capacidades de seguridad para ayudarle a proteger sus datos y aplicaciones.
    
- Es propietario de sus datos e identidades y la responsabilidad de protegerlos, la seguridad de los recursos locales y la seguridad de los componentes de nube que controla.
    
Microsoft proporciona funcionalidades para ayudar a proteger su organización, pero solo son eficaces si las usa. Si no las usa, puede que sea vulnerable a ataques. Para proteger sus cuentas de administrador global, Microsoft está aquí para ayudarle con instrucciones detalladas para:
  
1. Cree cuentas de administrador global de Microsoft 365 dedicadas y úselas solo cuando sea necesario.
    
2. Configure la autenticación multifactor para sus cuentas de administrador global de Microsoft 365 dedicadas y use la forma más segura de autenticación secundaria.
    
> [!Note]
> Aunque este artículo se centra en las cuentas de administrador global, debe considerar si las cuentas adicionales con amplios permisos para obtener acceso a los datos de la suscripción, como el administrador de exhibición de documentos electrónicos o las cuentas de administrador de seguridad o cumplimiento, deben protegerse de la misma manera. <br > Se puede crear una cuenta de administrador global sin agregar ninguna licencia.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Paso 1. Crear cuentas de administrador global de Microsoft 365 dedicadas y usarlas solo cuando sea necesario

Hay relativamente pocas tareas administrativas, como asignar roles a cuentas de usuario, que requieren privilegios de administrador global. Por lo tanto, en lugar de usar cuentas de usuario diarias a las que se ha asignado el rol de administrador global, siga estos pasos:
  
1. Determine el conjunto de cuentas de usuario a las que se ha asignado el rol de administrador global. Puede hacerlo en el Centro de administración de Microsoft 365 o con el siguiente comando PowerShell para Graph de Azure Active (Azure AD):
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Inicie sesión en su suscripción a Microsoft 365 con una cuenta de usuario a la que se le asignó el rol de administrador global.
    
3. Cree hasta un máximo de cuatro cuentas de usuario de administrador global dedicadas. **Usa contraseñas seguras con al menos 12 caracteres de longitud.** Consulta [Crear una contraseña segura](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) para obtener más información. Almacene las contraseñas de las nuevas cuentas en una ubicación segura. 
    
4. Asigne el rol de administrador global a cada una de las nuevas cuentas de usuario de administrador global dedicadas.
    
5. Cerrar sesión en Microsoft 365.
    
6. Inicie sesión con una de las nuevas cuentas de usuario de administrador global dedicadas.
    
7. Para cada cuenta de usuario existente a la que se asignó el rol de administrador global del paso 1:
    
  - Quite el rol de administrador global.
    
  - Asigne roles de administrador a la cuenta que sean adecuados para la función y responsabilidad del trabajo de ese usuario. Para obtener más información acerca de varios roles de administrador en Microsoft 365, vea [About admin roles](/office365/admin/add-users/about-admin-roles).
    
8. Cerrar sesión en Microsoft 365.
    
Los resultados deben ser:
  
- Las únicas cuentas de usuario de su suscripción que tienen el rol de administrador global son aquellas pertenecientes al nuevo conjunto de cuentas de administrador global dedicadas. Compruebe esto con el siguiente comando de PowerShell:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- El resto de las cuentas de usuario habituales que administran la suscripción tienen asignados roles de administrador que están asociados con las funciones del puesto.
    
A partir de este momento, inicia sesión con las cuentas de administrador global dedicadas solo para las tareas que requieren privilegios de administrador global. El resto de la administración de Microsoft 365 debe realizarse asignando otros roles de administración a cuentas de usuario.
  
> [!NOTE]
> Esto requiere pasos adicionales para cerrar sesión como cuenta de usuario diaria e iniciar sesión con una cuenta de administrador global dedicada. Pero esto solo debe hacerse ocasionalmente para las operaciones de administrador global. Ten en cuenta que la recuperación de la suscripción a Microsoft 365 después de una infracción de la cuenta de administrador global requiere muchos más pasos.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Paso 2. Configurar la autenticación multifactor para las cuentas de administrador global de Microsoft 365 dedicadas

La autenticación multifactor (MFA) requiere información adicional más allá del nombre de cuenta y la contraseña. Microsoft 365 admite estos métodos de comprobación adicionales:
  
- La aplicación de Microsoft Authenticator

- Una llamada de teléfono
    
- Un código de verificación generado aleatoriamente enviado a través de un mensaje de texto
    
- Una tarjeta inteligente (física o virtual)
    
- Un dispositivo biométrico
    
>[!Note]
>Para las organizaciones que deben cumplir con los estándares del Instituto Nacional de Estándares y Tecnología (NIST), se restringe el uso de métodos de verificación adicionales basados en mensajes de texto o llamadas telefónicas. Haga [clic aquí](https://pages.nist.gov/800-63-FAQ/#q-b01) para obtener más información.
>

Si es una pequeña empresa que usa cuentas de usuario almacenadas solo en la nube (el modelo de identidad solo en la nube), configure MFA para configurar [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) mediante una llamada telefónica o un código de verificación de mensajes de texto enviado a un teléfono inteligente para cada cuenta de administrador global dedicada.
    
Si es una organización más grande que usa un modelo de identidad híbrida de Microsoft 365, tiene más opciones de comprobación. Si ya dispone de la infraestructura de seguridad para un método de autenticación secundario más sólido, configure [MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) y configure cada cuenta de administrador global dedicada para el método de comprobación adecuado.
  
Si la infraestructura de seguridad del método de comprobación más seguro deseado no está en funcionamiento para MFA de Microsoft 365, se recomienda encarecidamente configurar cuentas de administrador global dedicadas con MFA mediante la aplicación Microsoft Authenticator, una llamada telefónica o un código de verificación de mensajes de texto enviados a un teléfono inteligente para sus cuentas de administrador global como medida de seguridad provisional. No deje las cuentas de administrador global dedicadas sin la protección adicional proporcionada por MFA.
  
Para obtener más información, vea [MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).
  
Para conectarse a los servicios de Microsoft 365 con MFA y PowerShell, consulte estos artículos:

- [PowerShell para Microsoft 365 para cuentas de usuario, grupos y licencias](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype Empresarial Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Protecciones adicionales para organizaciones empresariales

Use estos métodos adicionales para asegurarse de que la cuenta de administrador global y la configuración que realice con ella sean lo más seguras posible.
  
### <a name="privileged-access-workstation"></a>Estación de trabajo de acceso con privilegios

Para garantizar que la ejecución de tareas con privilegios elevados sea lo más segura posible, use una estación de trabajo de acceso con privilegios (PAW). Un PAW es un equipo dedicado que solo se usa para tareas de configuración confidenciales, como la configuración de Microsoft 365 que requiere una cuenta de administrador global. Dado que este equipo no se usa diariamente para la exploración de Internet o el correo electrónico, está mejor protegido de los ataques y amenazas de Internet.
  
Para obtener instrucciones sobre cómo configurar una PATA, vea [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) .

Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador, vea los [pasos para configurar PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

En lugar de que las cuentas de administrador global se asignen permanentemente al rol de administrador global, puede usar Azure AD Privileged Identity Management (PIM) para habilitar la asignación a petición y a tiempo del rol de administrador global cuando sea necesario.
  
Las cuentas de administrador global van de ser administradores permanentes a administradores elegibles. El rol de administrador global está inactivo hasta que alguien lo necesite. A continuación, complete un proceso de activación para agregar el rol de administrador global a la cuenta de administrador global durante un período de tiempo predeterminado. Cuando expira el tiempo, PIM quita el rol de administrador global de la cuenta de administrador global.
  
El uso de PIM y este proceso reduce significativamente la cantidad de tiempo que las cuentas de administrador global son vulnerables a ataques y uso por parte de usuarios malintencionados.

PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 E5. Como alternativa, puede comprar licencias individuales de Azure Active Directory Premium P2 para las cuentas de administrador.
  
Para obtener más información, vea [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Administración del acceso con privilegios

La administración de acceso con privilegios se habilita configurando las directivas que especifiquen el acceso puntual para las actividades basadas en tareas en el espacio empresarial. Puede ayudar a proteger la organización contra infracciones que puedan usar las cuentas existentes de administrador con privilegios con acceso permanente a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración de acceso con privilegios que requiera una autorización explícita para acceder y modificar la configuración del buzón de correo del espacio empresarial.

En este paso, habilitará la administración de acceso con privilegios en el espacio empresarial y configurará las directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a los datos y las opciones de configuración de la organización. Para empezar con el acceso con privilegios en la organización, debe seguir estos tres pasos básicos:

- Crear un grupo de aprobadores
- Habilitar el acceso con privilegios
- Crear directivas de aprobación

La administración de acceso con privilegios permite a la organización operar con cero privilegios permanentes y proporcionar una capa de defensa contra las vulnerabilidades que surgen debido a dicho acceso administrativo permanente. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea que tenga definida una directiva de aprobación asociada. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deben solicitar y obtener la aprobación de acceso.

Para habilitar la administración de acceso con privilegios, vea [Configure privileged access management](/office365/securitycompliance/privileged-access-management-configuration).

Para obtener más información, vea [Privileged access management](/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Software de administración de eventos y información de seguridad (SIEM) para el registro de Microsoft 365

El software SIEM que se ejecuta en un servidor realiza un análisis en tiempo real de alertas de seguridad y eventos creados por aplicaciones y hardware de red. Para permitir que el servidor SIEM incluya alertas y eventos de seguridad de Microsoft 365 en sus funciones de análisis e informes, integre Azure AD en seim. Consulte [Introduction to Azure Log Integration](/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Paso siguiente

Si está configurando la identidad de su suscripción a Microsoft 365, vea:

- [Identidades de solo nube](cloud-only-identities.md) si usa la identidad de solo nube
- [Preparar la sincronización de](prepare-for-directory-synchronization.md) directorios si usa la identidad híbrida

  
## <a name="see-also"></a>Vea también

[Guía básica de seguridad de Microsoft 365](/office365/securitycompliance/security-roadmap)