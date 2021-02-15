---
title: Autenticación multifactor de Entorno de pruebas de Microsoft 365 para empresas
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
- seo-marvel-apr2020
description: Configure la autenticación multifactor mediante mensajes de texto enviados a un smartphone en su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558447"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticación multifactor para su entorno de prueba de Microsoft 365 para empresas

*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*

Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure AD, que requiere algo más que un nombre de usuario y una contraseña para comprobar una cuenta.

Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de verificación enviado en un mensaje de texto o comprobar la autenticación con una aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas. Solo pueden iniciar sesión después de que se cumple este segundo factor de autenticación.
  
En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.
  
La configuración de la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 para empresas implica dos fases y una tercera fase opcional:
- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: Habilitar y probar la autenticación multifactor con una directiva de acceso condicional](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Probar la autenticación multifactor no requiere el entorno de pruebas de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2

Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:
  
1. Abra una instancia privada independiente del explorador, vaya al Centro de administración de Microsoft 365 ( ) y, a continuación, inicie sesión [https://portal.microsoft.com](https://portal.microsoft.com) con su cuenta de administrador global.
    
2. En el panel de navegación izquierdo, seleccione **Usuarios**  >  **activos.**
    
3. En el panel Usuarios activos, seleccione **Autenticación multifactor.**
    
4. En la lista, seleccione la **cuenta Usuario 2.**
    
5. En la **sección Usuario 2,** en **Pasos rápidos,** seleccione **Habilitar**.
    
6. En el cuadro de diálogo Acerca de cómo habilitar **la autenticación multifactor,** seleccione **Habilitar autenticación multifactor**.
    
7. En el **cuadro de diálogo** Actualizaciones correctas, seleccione **Cerrar**.
    
8. En la pestaña Centro de administración de **Microsoft 365,** seleccione el icono de cuenta de usuario en la esquina superior derecha y, a continuación, **seleccione Cerrar sesión.**
    
9. Cierre la instancia del explorador.
   
Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:
  
1. Abra una nueva instancia privada del explorador.
    
2. Vaya al Centro [de administración de Microsoft 365](https://admin.microsoft.com) e inicie sesión con el nombre y la contraseña de la cuenta usuario 2.
    
3. Después de iniciar sesión, se te pedirá que configures la cuenta para obtener más información. Seleccione **Siguiente**.
    
4. En la página **Comprobación de seguridad adicional**: 
    
   - Seleccione el país o región.
    
   - Escriba el número de teléfono del teléfono inteligente que recibirá mensajes de texto.
    
   - In **Method**, select **Send me a code by text message**.
    
5. Seleccione **Siguiente**.
    
6. Escriba el código de verificación del mensaje de texto recibido en su smartphone y, a continuación, seleccione **Comprobar**.
    
7. En el **paso 3: Conservar las aplicaciones existentes,** seleccione **Listo.**
    
8. Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y una nueva contraseña dos veces y, a continuación, seleccione **Actualizar contraseña e inicie sesión.** Anote la contraseña nueva en un lugar seguro.
    
    Debería ver el portal de Office para el usuario 2 en la **Microsoft Office** inicio del explorador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Habilitar y probar la autenticación multifactor con una directiva de acceso condicional

*Esta fase solo se puede usar para un entorno de prueba de Microsoft 365 para empresas.*

En esta fase, habilitará la autenticación multifactor para la cuenta usuario 3 mediante un grupo y una directiva de acceso condicional.

A continuación, cree un nuevo grupo denominado MFAUsers y agréle la cuenta Usuario 3.

1. En la pestaña Centro de administración de **Microsoft 365,** seleccione **Grupos** en el panel de navegación izquierdo y, a continuación, **seleccione Grupos.**
2. Seleccione **Agregar un grupo.**
3. En el **panel Elegir un tipo de** grupo, **seleccione** Seguridad y, a continuación, **seleccione Siguiente**.
4. En el **panel Configurar los conceptos** básicos, seleccione **Crear grupo** y, a continuación, **seleccione Cerrar**.
5. En el **panel Revisar y terminar de agregar** grupo, escriba **MFAUsers** y, a continuación, seleccione **Siguiente**.
6. En la lista de grupos, seleccione el **grupo MFAUsers.**
7. En el **panel MFAUsers,** seleccione **Miembros** y, a continuación, seleccione **Ver todos y administrar miembros.**
8. En el **panel MFAUsers,** seleccione **Agregar miembros,** seleccione la cuenta usuario **3** y, a continuación, **seleccione Guardar**  >  **cerrar**  >  **cerrar**.

A continuación, cree una directiva de acceso condicional para requerir la autenticación multifactor para los miembros del grupo MFAUsers.

1. En una nueva pestaña del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .
2. Seleccione **Acceso condicional de seguridad** de Azure Active  >    >  Directory.
3. En el **panel Acceso condicional – Directivas,** seleccione Nueva **directiva**.
4. En el **panel Nuevo,** escriba **MFA para cuentas de usuario** en el **cuadro** Nombre.
5. En la **sección Asignaciones,** seleccione **Usuarios y grupos.**
6. En la **pestaña Incluir** del panel **Usuarios** y grupos, seleccione Seleccionar usuarios **y grupos** Usuarios  >  **y grupos**  >  **Seleccionar.**
7. En el **panel** Seleccionar, seleccione el grupo **MFAUsers** y, a continuación, **seleccione Seleccionar**  >  **listo.**
8. En la **sección Controles de acceso** del **panel** Nuevo, seleccione **Conceder**.
9. En el **panel Conceder,** seleccione **Requerir autenticación multifactor** y, a continuación, **seleccione Seleccionar**.
10. En el **panel** Nuevo, seleccione **Activar** para **Habilitar directiva** y, a continuación, seleccione **Crear**.
11. Cierre las **pestañas del Portal de Azure** y del Centro de administración de Microsoft **365.**

Para probar esta directiva, cerrar sesión e iniciar sesión con la cuenta Usuario 3. Se le pedirá que configure MFA. Esto demuestra que se está aplicando la directiva MFAUsers.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
