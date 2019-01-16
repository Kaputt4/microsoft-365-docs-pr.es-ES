---
title: Entorno de prueba de la autenticación multifactor para su empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configuración de la autenticación multifactor mediante mensajes de texto enviados a un teléfono inteligente en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 353f09253794670e8107e084acb3a01cd309fd60
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871161"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Entorno de prueba de la autenticación multifactor para su empresa de 365 de Microsoft

Para obtener un nivel adicional de seguridad para iniciar sesión en Office 365 o cualquier servicio o aplicación que usa el inquilino de Azure AD para su organización, puede habilitar la autenticación multifactor Azure, lo cual requiere algo más que un nombre de usuario y una contraseña para comprobar un cuenta. Con la autenticación multifactor, los usuarios son necesarios para confirmar una llamada de teléfono, escriba un código de comprobación enviado en un mensaje de texto o especificar una contraseña de la aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas. Puede iniciar sesión sólo después de que se haya probado este segundo factor de autenticación. 
  
En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta específica.
  
Hay dos fases para configurar la autenticación multifactor para una cuenta en su entorno de prueba de Microsoft 365 Enterprise:
  
1. Crear el entorno de prueba de Microsoft 365 Enterprise.
    
2. Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea probar la autenticación multifactor en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Probar la autenticación multifactor no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la autenticación multifactor y experimentar con él en un entorno que representa una organización típica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2

Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:
  
1. Abra una sesión independiente, privada de su explorador, vaya al portal de Office ([https://office.com](https://office.com)) y, a continuación, inicie sesión con su cuenta de administrador global.
    
2. En la página principal del portal, haga clic en **Administración**.
    
3. En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
4. En el panel usuarios activos, haga clic en **más > el programa de instalación de la autenticación multifactor**.
    
5. En la lista, seleccione la cuenta de **usuario 2** .
    
6. En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.
    
7. En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.
    
8. En el cuadro de diálogo **actualiza correctamente** , haga clic en **Cerrar**.
    
9. En la pestaña **Página principal de Microsoft Office**, haga clic en el icono de cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.
    
10. Cierre la instancia del explorador.
   
Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:
  
1. Abra una nueva instancia del explorador privada.
    
2. Vaya al portal de Office ([https://office.com](https://office.com)) y el inicio de sesión con la cuenta de usuario 2 (user2 @\<nombre de la organización >. onmicrosoft.com) y la contraseña.
    
3. Después de iniciar sesión, se le pide para configurar la cuenta para obtener más información. Haga clic en **siguiente**.
    
4. En la página **Comprobación de seguridad adicional**: 
    
   - Seleccione el país o región.
    
   - Escriba el número de teléfono del smartphone que va a recibir los mensajes de texto.
    
   - En **método**, haga clic en **Enviarme un código por mensaje de texto**.
    
5. Haga clic en **Siguiente**.
    
6. Escriba el código de comprobación incluido en el mensaje de texto que ha recibido en el smartphone y, después, haga clic en **Comprobar**.
    
7. En la página **Step 3: Keep your existing applications** (Paso 3: conservar las aplicaciones existentes), guarde en una ubicación segura la contraseña de aplicación que se muestra para la cuenta Usuario 2 y, después, haga clic en **Listo**.
    
8. Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y la contraseña nueva dos veces y, después, haga clic en **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.
    
    Debería ver el portal de Office para el usuario 2 en la ficha **Página principal de Microsoft Office** del explorador.


Consulte el paso [Configurar la autenticación multifactor](identity-multi-factor-authentication.md) en la fase de identidad de información y vínculos para implementar la autenticación multifactor en producción.
    
## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
