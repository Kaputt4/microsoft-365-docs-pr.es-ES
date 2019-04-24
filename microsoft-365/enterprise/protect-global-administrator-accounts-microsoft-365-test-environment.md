---
title: Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Siga estos pasos para proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290863"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteger las cuentas de administrador global en su entorno de prueba de Microsoft 365 Enterprise

Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible. En este artículo se describe cómo usar Office 365 Cloud App Security y directivas de acceso condicional de Azure AD para proteger las cuentas de administrador global.

Existen dos fases para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 Enterprise:

1.  Cree el entorno de prueba de Microsoft 365 Enterprise.
2.  Proteja su cuenta de administrador global dedicada.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

> [!NOTE]
> El entorno de prueba de Microsoft 365 Enterprise usa versiones E5 de Office 365 y Enterprise Management + Security (EMS). La característica de seguridad de aplicaciones en la nube de Office 365 solo está disponible en la versión de E5 Office 365. 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise

Si solo quiere probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).

  
> [!NOTE]
> La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>Fase 2: configurar la seguridad de aplicación de nube y directivas de acceso condicional

En primer lugar, cree una directiva de seguridad de la aplicación de nube de Office 365 para supervisar la actividad de la cuenta de administrador global y enviar alertas a la dirección de correo electrónico de su cuenta de administrador global. 

1. Inicie sesión en el [portal de cumplimiento de Office 365 Security &](https://protection.office.com/) con su cuenta de administrador global.
2. En el panel de navegación izquierdo, haga clic en **alertas > de administración de alertas avanzadas**.
3. En la página **Administrar alertas avanzadas** , haga clic en **activar Office 365 Cloud App Security**y, a continuación, haga clic en **ir a Office 365 Cloud App Security**.
4. En la pestaña nuevo **Panel** , haga clic en **directivas de > de control**.
5. En la página **Directiva** , haga clic en **crear Directiva**y, a continuación, haga clic en **Directiva de actividad**.
6. En **nombre**de la Directiva, escriba **actividad administrativa**.
7. En **Gravedad de directiva**, haga clic en **Alto**.
8. En **categoría**, haga clic en **cuentas con privilegios**.
9. En **crear filtros para la Directiva**, en **actividades que coincidan con todas las opciones siguientes**, haga clic en **actividad administrativa**.
10. En **Alertas**, haga clic en **Enviar alerta como mensaje de correo electrónico**. En **Para**, escriba la dirección de correo electrónico de la cuenta de administrador global.
11. En la parte inferior de la página, haga clic en **Crear**.
12. Cierre la pestaña **Panel** .
    
A continuación, cree una nueva cuenta de usuario como administrador global dedicado.

1. En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).
2. En **usuarios activos**, haga clic en **Agregar un usuario**.
3. En la página **nuevo usuario** , escriba **DedicatedAdmin** en **nombre**, **nombre para mostrar**y nombre de **usuario**.
4. Haga clic en **contraseña**, en **deseo crear la contraseña**y, a continuación, escriba una contraseña segura. Registre la contraseña de esta nueva cuenta en una ubicación segura.
5. DesActive **la casilla hacer que este usuario cambie su contraseña la primera vez que inicie sesión**.
6. Haga clic en **roles**y, a continuación, en **administrador global**.
7. Haga clic en **licencias de producto**y, a continuación, active las licencias de **Enterprise Mobility + Security e5** y **Office 365 Enterprise E5** en.
8. Haga clic en **Agregar**.
9. En la **página se ha agregado el usuario**, desactive **Enviar contraseña en correo electrónico**y, a continuación, haga clic en **cerrar**.

A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.

1. En la pestaña **centro de administración de 365 de Microsoft** , haga clic en el icono grupos en el panel de navegación izquierdo y, a continuación, haga clic en **grupos**.
2. Haga clic en **Agregar un grupo**.
3. En la página **nuevo grupo** , escriba **GlobalAdmins**.
4. Haga clic en **seleccionar propietario, seleccione** su cuenta de administrador global y, a continuación, haga clic en **Agregar > cerrar**.
5. En la lista de grupos, haga clic en el grupo **GlobalAdmins** .
6. En la página **GlobalAdmins** , haga clic en **Editar para miembro**y, a continuación, haga clic en **Agregar miembros**.
7. En la lista, haga clic en la cuenta **DedicatedAdmin** y, a continuación, haga clic en **Guardar _GT_ cerrar > cerrar _GT_ centro de administración**.

A continuación, cree directivas de acceso condicional para requerir la autenticación multifactor para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.

Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.

1. En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com).
2. Haga clic en **Azure Active Directory > acceso condicional**.
3. En la hoja de **acceso condicional-directivas** , haga clic en **Directiva de línea de base: requerir MFA para administradores (versión preliminar)**.
4. En las **directivas de línea base...** Blade, haga clic en **usar Directiva inmediatamente _GT_ guardar**.

Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.

1. En la hoja de **acceso condicional-directivas** , haga clic en **nueva Directiva**.
2. En la hoja **nueva** , escriba **administradores globales** en **nombre**.
3. En la sección **asignaciones** , haga clic en **usuarios y grupos**.
4. En la ficha **incluir** de la hoja **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos _GT_ usuarios y grupos > seleccione**.
5. En la hoja **Select** Blade, haga clic en el **> GlobalAdmins seleccione > listo**.
6. En la sección **asignaciones** , haga clic en **condiciones**.
7. En la **hoja condiciones** , haga clic en **riesgo de inicio de sesión**, haga clic en **sí** para **configurar**, haga clic en **alta** y **media**y, a continuación, haga clic en **seleccionar** y **listo**.
8. En la sección **controles de acceso** de la **nueva** hoja, haga clic en **conceder**.
9. En la **** hoja conceder, haga clic en **Bloquear acceso**y, a continuación, haga clic en **seleccionar**.
10. En la hoja **nueva** , haga **** clic en **Habilitar Directiva**y, a continuación, haga clic en **crear**.
11. Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .

Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin. Se le pedirá que configure la MFA en la cuenta de usuario. Esto demuestra que se está aplicando la primera Directiva.

Consulte el paso [proteger las cuentas de administrador global](identity-designate-protect-admin-accounts.md#identity-global-admin) en la fase de identidad para obtener información y vínculos para proteger las cuentas de administrador global en producción.

## <a name="next-step"></a>Siguiente paso

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
