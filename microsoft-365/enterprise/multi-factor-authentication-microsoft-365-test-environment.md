---
title: Microsoft 365 para la autenticación multifactor del entorno de prueba de empresa
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
description: Configure multi-factor Authentication mediante mensajes de texto enviados a un smartphone en su Microsoft 365 para el entorno de prueba de la empresa.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558447"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Autenticación multifactor para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

Para obtener un nivel adicional de seguridad para iniciar sesión en Microsoft 365 o cualquier servicio o aplicación que use el inquilino de Azure AD para su suscripción, puede habilitar la autenticación multifactor de Azure AD, que requiere más que un nombre de usuario y una contraseña para comprobar una cuenta.

Con la autenticación multifactor, los usuarios deben confirmar una llamada telefónica, escribir un código de comprobación enviado en un mensaje de texto o verificar la autenticación con una aplicación en su smartphone, después de escribir correctamente sus contraseñas. Solo pueden iniciar sesión después de que se cumpla este segundo factor de autenticación.
  
En este artículo se describe cómo habilitar y probar la autenticación basada en mensajes de texto para una cuenta de usuario específica.
  
La configuración de la autenticación multifactor para una cuenta en el entorno de prueba de Microsoft 365 para empresas implica dos fases y una tercera fase opcional:
- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: habilitar y probar la autenticación multifactor con una directiva de acceso condicional](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar la autenticación multifactor de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la autenticación multifactor en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La comprobación de la autenticación multifactor no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Aquí se ofrece como opción para que pueda probar la autenticación multifactor y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: habilitar y probar la autenticación multifactor para la cuenta Usuario 2

Siga estos pasos para habilitar la autenticación multifactor para la cuenta Usuario 2:
  
1. Abra una instancia independiente y privada del explorador, vaya al centro de administración de Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) y, a continuación, inicie sesión con su cuenta de administrador global.
    
2. En el panel de navegación izquierdo **, seleccione usuarios**  >  **activos**.
    
3. En el panel usuarios activos, seleccione **multi-factor Authentication**.
    
4. En la lista, seleccione la cuenta **usuario 2** .
    
5. En la sección **usuario 2** , en **pasos rápidos**, seleccione **Habilitar**.
    
6. En el cuadro de diálogo **acerca de la habilitación de autenticación multifactor** , seleccione **Habilitar multi-factor auth**.
    
7. En el cuadro de diálogo **actualizaciones correctas** , seleccione **cerrar**.
    
8. En la pestaña **centro de administración de 365 de Microsoft** , seleccione el icono de la cuenta de usuario en la esquina superior derecha y, después, seleccione **Cerrar sesión**.
    
9. Cierre la instancia del explorador.
   
Complete la configuración de la cuenta Usuario 2 para usar un mensaje de texto con fines de validación y prueba mediante los pasos siguientes:
  
1. Abra una nueva instancia privada del explorador.
    
2. Vaya al [centro de administración de 365 de Microsoft](https://admin.microsoft.com) y inicie sesión con el nombre de cuenta y la contraseña del usuario 2.
    
3. Después de iniciar sesión, se le pedirá que configure la cuenta para obtener más información. Seleccione **Siguiente**.
    
4. En la página **Comprobación de seguridad adicional**: 
    
   - Seleccione el país o región.
    
   - Escriba el número de teléfono del smartphone que recibirá los mensajes de texto.
    
   - En el **método**, seleccione **enviarme un código por mensaje de texto**.
    
5. Seleccione **Siguiente**.
    
6. Escriba el código de verificación del mensaje de texto que ha recibido en el smartphone y, después, seleccione **comprobar**.
    
7. En la página **paso 3: conservar las aplicaciones existentes** , seleccione **listo**.
    
8. Si es la primera vez que inicia sesión con la cuenta Usuario 2, se le pedirá que cambie la contraseña. Escriba la contraseña original y una nueva contraseña dos veces y, a continuación, seleccione **Actualizar contraseña e iniciar sesión**. Anote la contraseña nueva en un lugar seguro.
    
    Debe ver el portal de Office para el usuario 2 en la pestaña **Página principal de Microsoft Office** del explorador.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: habilitar y probar la autenticación multifactor con una directiva de acceso condicional

*Esta fase solo puede usarse para un entorno de prueba de Microsoft 365 para empresas.*

En esta fase, habilitará la autenticación multifactor para la cuenta usuario 3 con un grupo y una directiva de acceso condicional.

A continuación, cree un nuevo grupo denominado MFAUsers y agréguele la cuenta de usuario 3.

1. En la pestaña **centro de administración de 365 de Microsoft** , seleccione **grupos** en el panel de navegación izquierdo y, a continuación, seleccione **grupos**.
2. Seleccione **Agregar un grupo**.
3. En el panel **elegir un tipo de grupo** , seleccione **seguridad** y, a continuación, seleccione **siguiente**.
4. En el panel **configurar conceptos básicos** , seleccione **Crear grupo** y, a continuación, haga clic en **cerrar**.
5. En el panel **revisar y finalizar agregar grupo** , escriba **MFAUsers** y, a continuación, seleccione **siguiente**.
6. En la lista de grupos, seleccione el grupo **MFAUsers** .
7. En el panel **MFAUsers** , seleccione **miembros** y, a continuación, seleccione **Ver todos y administrar miembros**.
8. En el panel **MFAUsers** , seleccione **Agregar miembros**, seleccione la cuenta de **usuario 3** y, a continuación, seleccione **Guardar**  >  **cerrar**  >  **Close**.

A continuación, cree una directiva de acceso condicional para exigir la autenticación multifactor para los miembros del grupo MFAUsers.

1. En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .
2. Seleccione **Azure Active Directory**  >  **Security**  >  **acceso condicional** de seguridad de Azure Active Directory.
3. En el panel **acceso condicional-directivas** , seleccione **nueva Directiva**.
4. En el panel **nuevo** , escriba **MFA para las cuentas de usuario** en el cuadro **nombre** .
5. En la sección **asignaciones** , seleccione **usuarios y grupos**.
6. En la ficha **incluir** del panel **usuarios y grupos** , seleccione **Seleccionar usuarios y** grupos, seleccione usuarios y  >  **grupos**  >  **Select**.
7. En el panel de **selección** , seleccione el grupo **MFAUsers** y, a continuación, seleccione **seleccionar**  >  **listo**.
8. En la sección **controles de acceso** del panel **nuevo** , seleccione **conceder**.
9. En el panel **conceder** , seleccione **requerir autenticación multifactor** y, a continuación, seleccione **seleccionar**.
10. En el panel **nuevo** , seleccione **activado** para **Habilitar Directiva** y, a continuación, seleccione **crear**.
11. Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .

Para probar esta Directiva, cierre sesión e inicie sesión con la cuenta de usuario 3. Se le pedirá que configure la MFA. Esto demuestra que se está aplicando la Directiva MFAUsers.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
