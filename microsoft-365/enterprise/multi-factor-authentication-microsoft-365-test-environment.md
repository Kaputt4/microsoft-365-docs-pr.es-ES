---
title: Microsoft 365 para la autenticación multifactor del entorno de prueba empresarial
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
- admindeeplinkMAC
description: Configure la autenticación multifactor mediante mensajes de texto enviados a un teléfono inteligente en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 0100f6a7ea6844943f15420a722a471279bc9746
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67694467"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticación multifactor para el entorno de prueba de Microsoft 365 para empresas

*Esta guía de laboratorio de pruebas se puede usar para Microsoft 365 para entornos de prueba empresariales y Office 365 Enterprise.*

Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o en cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure AD, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta.

Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de verificación enviado en un mensaje de texto o comprobar la autenticación con una aplicación en sus teléfonos inteligentes después de escribir correctamente sus contraseñas. Solo pueden iniciar sesión una vez que se cumpla este segundo factor de autenticación.
  
En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.
  
La configuración de la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 para empresas implica dos fases y una tercera fase opcional:
- [Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: Habilitación y prueba de la autenticación multifactor con una directiva de acceso condicional](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para enterprise Test Lab Guide Stack (Pila de guía del laboratorio de pruebas empresariales).](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2

Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:
  
1. Abra una instancia privada independiente del explorador, vaya a la Centro de administración de Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) y, a continuación, inicie sesión con su cuenta de administrador global.
    
2. En el panel de navegación izquierdo, seleccione **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**activos**</a>.
    
3. En el panel Usuarios activos, seleccione **Autenticación multifactor**.
    
4. En la lista, seleccione la cuenta **usuario 2** .
    
5. En la sección **Usuario 2** , en **Pasos rápidos**, seleccione **Habilitar**.
    
6. En el cuadro **de diálogo Acerca de cómo habilitar la autenticación multifactor** , seleccione **Habilitar autenticación multifactor**.
    
7. En el cuadro de diálogo **Novedades correcto**, seleccione **Cerrar**.
    
8. En la pestaña **Centro de administración de Microsoft 365**, seleccione el icono de cuenta de usuario en la esquina superior derecha y, a continuación, seleccione **Cerrar sesión**.
    
9. Cierre la instancia del explorador.
   
Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:
  
1. Abra una nueva instancia privada del explorador.
    
2. Vaya al [Centro de administración de Microsoft 365](https://admin.microsoft.com) e inicie sesión con el nombre y la contraseña de la cuenta del usuario 2.
    
3. Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información. Seleccione **Siguiente**.
    
4. En la página **Comprobación de seguridad adicional**: 
    
   - Seleccione el país o región.
    
   - Escriba el número de teléfono del teléfono inteligente que recibirá mensajes de texto.
    
   - En **Método**, seleccione **Enviarme un código por mensaje de texto**.
    
5. Seleccione **Siguiente**.
    
6. Escriba el código de verificación del mensaje de texto recibido en el teléfono inteligente y, a continuación, seleccione **Comprobar**.
    
7. En la página **Paso 3: Mantener las aplicaciones existentes** , seleccione **Listo**.
    
8. Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba dos veces la contraseña original y una nueva y, a continuación, seleccione **Actualizar contraseña e inicie sesión**. Anote la contraseña nueva en un lugar seguro.
    
    Debería ver el portal de Office para el usuario 2 en la pestaña **Inicio de Microsoft Office** del explorador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Habilitación y prueba de la autenticación multifactor con una directiva de acceso condicional

*Esta fase solo se puede usar para un entorno de prueba de Microsoft 365 para empresas.*

En esta fase, habilitará la autenticación multifactor para la cuenta de usuario 3 mediante un grupo y una directiva de acceso condicional.

A continuación, cree un nuevo grupo denominado MFAUsers y agréguele la cuenta de usuario 3.

1. En la pestaña **Centro de administración de Microsoft 365**, seleccione **Grupos** en el panel de navegación izquierdo y, a continuación, seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Grupos**</a>.
2. Seleccione **Agregar un grupo**.
3. En el panel **Elegir un tipo de grupo** , seleccione **Seguridad** y, a continuación, seleccione **Siguiente**.
4. En el panel **Configurar los aspectos básicos** , seleccione **Crear grupo** y, a continuación, seleccione **Cerrar**.
5. En el panel **Revisar y finalizar la adición del grupo** , escriba **MFAUsers** y, a continuación, seleccione **Siguiente**.
6. En la lista de grupos, seleccione el grupo **MFAUsers** .
7. En el panel **MFAUsers** , seleccione **Miembros** y, a continuación, seleccione **Ver todos y administrar miembros**.
8. En el panel **MFAUsers**, seleccione **Agregar miembros**, seleccione la cuenta **usuario 3** y, a continuación, seleccione **Guardar** > **cierre** > **.**

A continuación, cree una directiva de acceso condicional para requerir la autenticación multifactor para los miembros del grupo MFAUsers.

1. En una nueva pestaña del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).
2. Seleccione **Acceso condicional** **de seguridad de** >  **Azure Active Directory** > .
3. En el panel **Acceso condicional: directivas** , seleccione **Nueva directiva**.
4. En el panel **Nuevo** , escriba **MFA para cuentas de usuario** en el cuadro **Nombre** .
5. En la sección **Asignaciones** , seleccione **Usuarios y grupos**.
6. En la pestaña **Incluir** del panel **Usuarios y grupos** , seleccione **Seleccionar usuarios y grupos** > **Usuarios y grupos** > **Seleccione**.
7. En el panel **Seleccionar** , seleccione el grupo **MFAUsers** y seleccione **Seleccionar** > **listo**.
8. En la sección **Controles de acceso** del panel **Nuevo** , seleccione **Conceder**.
9. En el panel **Conceder** , seleccione **Requerir autenticación multifactor** y seleccione **Seleccionar**.
10. En el panel **Nuevo** , seleccione **Activado** en **Habilitar directiva** y, a continuación, seleccione **Crear**.
11. Cierre las pestañas **Azure Portal** y **Centro de administración de Microsoft 365**.

Para probar esta directiva, cierre la sesión e inicie sesión con la cuenta de usuario 3. Se le pedirá que configure MFA. Esto muestra que se está aplicando la directiva MFAUsers.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Implementación de la identidad](deploy-identity-solution-overview.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)