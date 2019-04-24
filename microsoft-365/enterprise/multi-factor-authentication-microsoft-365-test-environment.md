---
title: Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 8e202936451030718c0c86601c2c621c50f78e1a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291145"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise

Para obtener un nivel adicional de seguridad para iniciar sesión en Office 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su organización, puede habilitar la autenticación multifactor de Azure, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta. Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o especificar una contraseña de aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas. Pueden iniciar sesión solo después de que se haya cumplido este segundo factor de autenticación. 
  
En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta específica.
  
Hay dos fases para configurar la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 Enterprise:
  
1. Cree el entorno de prueba de Microsoft 365 Enterprise.
    
2. Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise

Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2

Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:
  
1. Abra una instancia independiente y privada del explorador, vaya al portal de Office ([https://office.com](https://office.com)) y, a continuación, inicie sesión con su cuenta de administrador global.
    
2. En la página principal del portal, haga clic en **Administración**.
    
3. En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
4. En el panel usuarios activos, haga clic en **más _GT_ multi-factor Authentication Setup**.
    
5. En la lista, seleccione la cuenta **usuario 2** .
    
6. En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.
    
7. En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.
    
8. En el cuadro de diálogo **actualizaciones correctas** , haga clic en **cerrar**.
    
9. En la pestaña **Página principal de Microsoft Office**, haga clic en el icono de cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.
    
10. Cierre la instancia del explorador.
   
Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:
  
1. Abra una nueva instancia privada del explorador.
    
2. Vaya al portal de Office ([https://office.com](https://office.com)) e inicie sesión con la cuenta usuario 2 (usuario2 @\<Organization name>. en Microsoft. com) y la contraseña.
    
3. Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información. Haga clic en **Siguiente**.
    
4. En la página **Comprobación de seguridad adicional**: 
    
   - Seleccione el país o región.
    
   - Escriba el número de teléfono del smartphone que va a recibir los mensajes de texto.
    
   - En **método**, haga clic en **enviarme un código por mensaje de texto**.
    
5. Haga clic en **Siguiente**.
    
6. Escriba el código de comprobación incluido en el mensaje de texto que ha recibido en el smartphone y, después, haga clic en **Comprobar**.
    
7. En la página **Step 3: Keep your existing applications** (Paso 3: conservar las aplicaciones existentes), guarde en una ubicación segura la contraseña de aplicación que se muestra para la cuenta Usuario 2 y, después, haga clic en **Listo**.
    
8. Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y la contraseña nueva dos veces y, después, haga clic en **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.
    
    Debe ver el portal de Office para el usuario 2 en la pestaña **Página principal de Microsoft Office** del explorador.


Consulte el paso [configurar la autenticación multifactor](identity-multi-factor-authentication.md#identity-mfa) en la fase de identidad para obtener información y vínculos para implementar la autenticación multifactor en producción.
    
## <a name="next-step"></a>Siguiente paso

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
