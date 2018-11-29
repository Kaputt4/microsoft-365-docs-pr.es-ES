---
title: Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise
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
description: Siga estos pasos para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871182"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise

Para evitar los ataques digitales en su organización, asegurarse de que las cuentas de administrador sean tan seguras como sea posible. En este artículo se describe cómo usar las directivas de acceso condicional de seguridad de la aplicación de nube de Office 365 y Azure AD para proteger las cuentas de administrador global.

Existen dos fases a proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise:

1.  Crear el entorno de prueba de Microsoft 365 Enterprise.
2.  Proteger la cuenta de administrador global dedicado.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea probar la protección de la cuenta de administrador global de una manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Comprobación de la cuenta de administrador global protección no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectado a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con él en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>Fase 2: Configuración de seguridad de la aplicación en la nube y las directivas de acceso condicional

En primer lugar, cree una directiva de seguridad de la aplicación de Office 365 en la nube para supervisar la actividad de la cuenta de administrador global y enviar alertas a la dirección de correo electrónico de su cuenta de administrador global. 

1. Inicie sesión el portal de Office 365 en [http://portal.office.com](http://portal.office.com) con su cuenta de administrador global.
2. Haga clic en el icono de **administración** . En la ficha del **Centro de administración de Office** , haga clic en **centros de administración > seguridad y cumplimiento**.
3. En el panel de navegación izquierdo, haga clic en **alertas > Administrar avanzada alertas**.
4. En la página **Administrar alertas de avanzada** , haga clic en **activar la seguridad de la aplicación de nube de Office 365**y, a continuación, haga clic en **Ir a la seguridad de la aplicación de nube de Office 365**.
5. En la ficha nuevo del **panel** , haga clic en **Control > directivas**.
6. En la página **Directiva** , haga clic en **Crear directiva**y, a continuación, haga clic en **Directiva de actividad**.
7. En **nombre de directiva**, escriba **actividad administrativa**.
8. En **Gravedad de directiva**, haga clic en **Alto**.
9. En **categoría**, haga clic en **cuentas con privilegios**.
10. **Crear filtros para la directiva**, en **las actividades que coincidan con todos los elementos siguientes**, haga clic en **actividades administrativas**.
11. En **Alertas**, haga clic en **Enviar alerta como mensaje de correo electrónico**. En **Para**, escriba la dirección de correo electrónico de la cuenta de administrador global.
12. En la parte inferior de la página, haga clic en **Crear**.
13. Cierre la ficha de **panel** .
    
A continuación, cree una nueva cuenta de usuario como administrador global dedicado.

1. En la ficha del **Centro de administración de Office** , en **usuarios activos**, haga clic en **Agregar un usuario**.
2. En la página **nuevo usuario** , escriba **DedicatedAdmin** en el **nombre**, el **nombre para mostrar**y el **nombre de usuario**.
3. Haga clic en **contraseña**, haga clic en **Permitir la creación de la contraseña**y, a continuación, escriba una contraseña segura. Registre la contraseña para esta cuenta nueva en una ubicación segura.
4. Desactive **hacer que este usuario cambiar su contraseña cuando inician sesión por primera vez en**.
5. Haga clic en **funciones**y, a continuación, haga clic en **Administrador Global**.
6. Haga clic en **licencias de producto**y, a continuación, activar la **movilidad de la empresa + E5 de seguridad** y **licencias de Office 365 Enterprise E5** .
7. Haga clic en **Agregar**.
8. En la **página se agregó el usuario**, desactive **Enviar contraseña en correo electrónico**y, a continuación, haga clic en **Cerrar**.

A continuación, cree un nuevo grupo denominado GlobalAdmins y agregue la cuenta DedicatedAdmin a ella.

1. En la ficha del **Centro de administración de Office** , haga clic en el icono de grupos en el panel de navegación izquierdo y, a continuación, haga clic en **grupos**.
2. Haga clic en **Agregar un grupo**.
3. En la página **Nuevo grupo** , escriba **GlobalAdmins**.
4. Haga clic en **Seleccionar propietario de** la cuenta de administrador global y, a continuación, haga clic en **Agregar > Cerrar**.
5. En la lista de grupos, haga clic en el grupo **GlobalAdmins** .
6. En la página **GlobalAdmins** , haga clic en **Editar para el miembro**y, a continuación, haga clic en **Agregar miembros**.
7. En la lista, haga clic en la cuenta de **DedicatedAdmin** y, a continuación, haga clic en **Guardar > Close > Close > Centro de administración de**.

A continuación, cree las directivas de acceso condicional requerir la autenticación con varios factores para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.

Esta primera directiva requiere que todas las cuentas de administrador global usar MFA.

1. En una nueva ficha del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).
2. Haga clic en **Azure Active Directory > acceso condicional**.
3. En el servidor blade de **acceso condicional – las directivas** , haga clic en **Directiva de línea de base: requieren MFA para los administradores (vista previa)**.
4. En el servidor blade de **las directivas de línea de base...** , haga clic en **usar inmediatamente la directiva > Guardar**.

Esta segunda directiva bloquea el acceso a la autenticación de cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.

1. En el servidor blade de **acceso condicional – las directivas** , haga clic en **nueva directiva**.
2. En el servidor blade de **nuevo** , escriba **los administradores globales** en **nombre**.
3. En la sección **asignaciones** , haga clic en **usuarios y grupos**.
4. En la ficha **incluir** de blade de **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.
5. En el servidor blade **Seleccione** , haga clic en el **GlobalAdmins > seleccione > realiza**.
6. En la sección **asignaciones** , haga clic en **condiciones**.
7. En el servidor blade de **condiciones** , haga clic en **Inicio de sesión de riesgo**, haga clic en **Sí** para **Configurar**y, a continuación, haga clic en **alto** y **medio**y, a continuación, haga clic en **Seleccionar** y **Listo**.
8. En la sección de **controles de acceso** del módulo **nuevo** , haga clic en **conceder**.
9. En el servidor blade **Grant** , haga clic en **bloquear el acceso**y, a continuación, haga clic en **Seleccionar**.
10. En el servidor blade de **nuevo** , haga clic **en** para **Habilitar la directiva**y, a continuación, haga clic en **crear**.
11. Cierre las fichas de **Centro de administración de Office** y **portal de Azure** .

Para probar la primera directiva, cierre la sesión e inicie sesión con la cuenta DedicatedAdmin. Debe pedir para configurar MFA en la cuenta de usuario. Esto demuestra que se aplica la primera directiva.

Consulte el paso de [las cuentas de administrador global de Protect](identity-designate-protect-admin-accounts.md) en la fase de identidad para obtener información y vínculos para proteger las cuentas de administrador global en producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
