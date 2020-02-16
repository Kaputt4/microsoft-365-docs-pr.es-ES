---
title: Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: ea2041a463b224781df101251dab0f4d9f0e8753
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066737"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Multi-factor Authentication para su entorno de prueba de Microsoft 365 Enterprise

*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*

Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta. 

Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o especificar una contraseña de aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas. Pueden iniciar sesión solo después de que se haya cumplido este segundo factor de autenticación. 
  
En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.
  
Hay dos fases para configurar la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 Enterprise:
  
1. Crear el entorno de pruebas de Microsoft 365 Enterprise.
    
2. Habilitar y probar la autenticación multifactor para la cuenta Usuario 2.

3. Habilitar y probar la autenticación multifactor con una directiva de acceso condicional (opcional).

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise

Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2

Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:
  
1. Abra una instancia independiente y privada del explorador, vaya al centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) y, a continuación, inicie sesión con su cuenta de administrador global.
    
2. En el panel de navegación izquierdo, haga clic en **Usuarios > Usuarios activos**.
    
3. En el panel usuarios activos, haga clic en **multi-factor Authentication**.
    
4. En la lista, seleccione la cuenta **usuario 2** .
    
5. En la sección **Usuario 2**, en **Pasos rápidos**, haga clic en **Habilitar**.
    
6. En el cuadro de diálogo **Acerca de la habilitación de autenticación multifactor**, haga clic en **Habilitar Multi-Factor Auth**.
    
7. En el cuadro de diálogo **actualizaciones correctas** , haga clic en **cerrar**.
    
8. En la pestaña **centro de administración de 365 de Microsoft** , haga clic en el icono de la cuenta de usuario en la esquina superior derecha y, después, en **Cerrar sesión**.
    
9. Cierre la instancia del explorador.
   
Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:
  
1. Abra una nueva instancia privada del explorador.
    
2. Vaya al portal de Office 365 ([https://portal.office.com](https://portal.office.com)) e inicie sesión con el nombre de cuenta y la contraseña del usuario 2.
    
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

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: habilitar y probar la autenticación multifactor con una directiva de acceso condicional

*Esta fase solo se puede usar para un entorno de prueba de Microsoft 365 Enterprise.*

En esta fase, se habilita la autenticación multifactor para la cuenta de usuario 3 con un grupo y una directiva de acceso condicional.

A continuación, cree un nuevo grupo denominado MFAUsers y agréguele la cuenta de usuario 3.

1. En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **grupos** en el panel de navegación izquierdo y, después, haga clic en **grupos**.
2. Haga clic en **Agregar un grupo**.
3. En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, haga clic en **siguiente**.
4. En el panel **configurar conceptos básicos** , haga clic en **Crear grupo**y, a continuación, haga clic en **cerrar**.
5. En el panel **revisar y finalizar agregar grupo** , escriba **MFAUsers**y, a continuación, haga clic en **siguiente**.
6. En la lista de grupos, haga clic en el grupo **MFAUsers** .
7. En el panel **MFAUsers** , haga clic en **miembros**y, a continuación, haga clic en **Ver todos y administrar miembros**.
8. En el panel de **MFAUsers** , haga clic en **Agregar miembros**, seleccione la cuenta de **usuario 3** y, a continuación, haga clic en **Guardar > cerrar > cerrar**.

A continuación, cree una directiva de acceso condicional para exigir la autenticación multifactor para los miembros del grupo MFAUsers.

1. En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).
2. Haga clic en **Azure active directory > Security > el acceso condicional**.
3. En el panel **acceso condicional-directivas** , haga clic en **nueva Directiva**.
4. En el panel **nuevo** , escriba **MFA para las cuentas de usuario** en **nombre**.
5. En la sección **asignaciones** , haga clic en **usuarios y grupos**.
6. En la ficha **incluir** del panel **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.
7. En el panel de **selección** , haga clic en el grupo **MFAUsers** y, a continuación, haga clic en **seleccionar > listo**.
8. En la sección **controles de acceso** del panel **nuevo** , haga clic en **conceder**.
9. En el panel **conceder** , haga clic en **requerir multi-factor Authentication**y, a continuación, haga clic en **seleccionar**.
10. En el panel **nuevo** , haga clic **en** **Habilitar Directiva**y, a continuación, haga clic en **crear**.
11. Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .

Para probar esta Directiva, cierre sesión e inicie sesión con la cuenta de usuario 3. Se le pedirá que configure la MFA. Esto demuestra que se está aplicando la Directiva MFAUsers.

Consulte el paso [configurar la autenticación multifactor](identity-secure-user-sign-ins.md#identity-mfa) en la fase de identidad para obtener información y vínculos para implementar la autenticación multifactor en producción.
    
## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
