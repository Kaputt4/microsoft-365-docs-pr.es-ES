---
title: Proteger cuentas de administrador global en su Microsoft 365 entorno de prueba empresarial
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
description: Siga estos pasos para proteger las cuentas de administrador global en su Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918887"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteger cuentas de administrador global en su Microsoft 365 entorno de prueba empresarial

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

Puede evitar ataques digitales en su organización asegurándose de que sus cuentas de administrador sean lo más seguras posible. 

En este artículo se describe cómo usar directivas de acceso condicional Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.

La protección de cuentas de administrador global en Microsoft 365 entorno de prueba de empresa implica dos fases:
- [Fase 1: Crear su Microsoft 365 entorno de prueba empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar directivas de acceso condicional](#phase-2-configure-conditional-access-policies)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear su Microsoft 365 entorno de prueba empresarial

Si desea probar la protección de cuentas de administrador global de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la protección de cuentas de administrador global en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Probar la protección de cuentas de administrador global no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la protección de cuentas de administrador global y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: Configurar directivas de acceso condicional

En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.

1. En una pestaña independiente, abra el centro [Microsoft 365 de administración](https://admin.microsoft.com/).
2. Seleccione **Usuarios**  >  **Usuarios activos** y, a continuación, seleccione Agregar un **usuario**.
3. En el **panel Agregar usuario,** escriba **DedicatedAdmin** en los cuadros **Nombre,** **Nombre para** mostrar y **Nombre de** usuario.
4. Seleccione **Contraseña**, **seleccione Permitirme crear la contraseña** y, a continuación, escriba una contraseña segura. Registre la contraseña de esta nueva cuenta en una ubicación segura.
5. Seleccione **Siguiente**.
6. En el **panel Asignar licencias de producto,** seleccione **Microsoft 365 E5** y, a continuación, **seleccione Siguiente**.
7. En el **panel Configuración opcional,** seleccione **Roles Admin** center  >  **access**  >  **Global admin**  >  **Next**.
8. En el **panel Ya casi** terminado, seleccione Finalizar **adición** y, a continuación, **seleccione Cerrar**.

A continuación, cree un nuevo grupo denominado GlobalAdmins y agréle la cuenta DedicatedAdmin.

1. En la **Microsoft 365 centro de administración,** seleccione **Grupos** en la navegación izquierda y, a continuación, **seleccione Grupos**.
2. Seleccione **Agregar un grupo**.
3. En el **panel Elegir un tipo de grupo,** seleccione **Seguridad** y, a continuación, **seleccione Siguiente**.
4. En el **panel Configurar los conceptos** básicos, seleccione **Crear grupo** y, a continuación, **seleccione Cerrar**.
5. En el **panel Revisar y terminar de agregar grupo,** escriba **GlobalAdmins** y, a continuación, **seleccione Siguiente**.
7. En la lista de grupos, seleccione el **grupo GlobalAdmins.**
8. En el **panel GlobalAdmins,** seleccione **Miembros** y, a continuación, **seleccione Ver todos y administrar miembros**.
9. En el **panel GlobalAdmins,** seleccione **Agregar** miembros, seleccione la cuenta **DedicatedAdmin** y la cuenta de administrador global y, a continuación, **seleccione Guardar**  >  **cerrar**  >  **cerrar**.

A continuación, cree directivas de acceso condicional para requerir autenticación multifactor para cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.

Esta primera directiva requiere que todas las cuentas de administrador global usen MFA.

1. En una nueva pestaña del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .
2. Haga **clic Azure Active Directory** acceso  >  **condicional** de  >  **seguridad**.
3. En el **panel Acceso condicional: directivas,** seleccione **Directiva de línea base: Requerir MFA para administradores (versión preliminar).**
4. En el **panel Directiva de** línea base, seleccione Usar directiva inmediatamente > **Guardar**.

Esta segunda directiva bloquea el acceso a la autenticación de cuentas de administrador global cuando el riesgo de inicio de sesión es medio o alto.

1. En el **panel Acceso condicional: directivas,** seleccione **Nueva directiva**.
2. En el **panel Nuevo,** escriba **Administradores globales** en **Nombre**.
3. En la **sección Asignaciones,** seleccione **Usuarios y grupos**.
4. En la **pestaña Incluir** del panel Usuarios **y grupos,** seleccione **Seleccionar usuarios y grupos** Usuarios  >  **y grupos**  >  **Seleccionar**.
5. En el **panel Seleccionar,** seleccione el **grupo GlobalAdmins** y, a continuación, **seleccione Seleccionar**  >  **listo**.
6. En la **sección Asignaciones,** seleccione **Condiciones**.
7. En el **panel Condiciones,** seleccione **Riesgo de** inicio de sesión, **Seleccione Sí** para **Configurar**, **Seleccione** Alto y Medio **y,** a continuación, **seleccione Seleccionar** y **Listo**.
8. En la **sección Controles de acceso** del panel **Nuevo,** seleccione **Conceder**.
9. En el **panel Conceder,** seleccione **Bloquear acceso** y, a continuación, **seleccione Seleccionar**.
10. En el **panel Nuevo,** seleccione **Activar para** **Habilitar directiva** y, a continuación, **seleccione Crear**.
11. Cierre las **pestañas Azure Portal** **y Microsoft 365 centro de** administración.

Para probar la primera directiva, cerrar sesión e iniciar sesión con la cuenta DedicatedAdmin. Se le pedirá que configure MFA. Esto demuestra que se está aplicando la primera directiva.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)