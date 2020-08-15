---
title: Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas
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
description: Siga estos pasos para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695187"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible. En este artículo se describe cómo usar las directivas de acceso condicional de Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.

Hay dos fases para proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas:

1.  Cree el entorno de prueba de Microsoft 365 para empresas.
2.  Proteja su cuenta de administrador global dedicada.

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurar directivas de acceso condicional

En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.

1. En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).
2. Haga clic en **usuarios > usuarios activos**y, a continuación, haga clic en **Agregar un usuario**.
3. En el panel **Agregar usuario** , escriba **DedicatedAdmin** en **nombre**, **nombre para mostrar**y nombre de **usuario**.
4. Haga clic en **contraseña**, en **deseo crear la contraseña**y, a continuación, escriba una contraseña segura. Registre la contraseña de esta nueva cuenta en una ubicación segura.
5. Haga clic en **Siguiente**.
6. En el panel **asignar licencias de producto** , seleccione **Microsoft 365 E5**y, a continuación, haga clic en **siguiente**.
7. En el panel **configuración opcional** , haga clic en **roles**y, a continuación, seleccione **acceso al centro de administración** y **administrador global**. Haga clic en **siguiente**.
8. En el panel **está casi terminado** , haga clic en **Finalizar adición**y, a continuación, haga clic en **cerrar**.

A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.

1. En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **grupos** en el panel de navegación izquierdo y, después, haga clic en **grupos**.
2. Haga clic en **Agregar un grupo**.
3. En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, haga clic en **siguiente**.
4. En el panel **configurar conceptos básicos** , haga clic en **Crear grupo**y, a continuación, haga clic en **cerrar**.
5. En el panel **revisar y finalizar agregar grupo** , escriba **GlobalAdmins**y, a continuación, haga clic en **siguiente**.
7. En la lista de grupos, haga clic en el grupo **GlobalAdmins** .
8. En el panel **GlobalAdmins** , haga clic en **miembros**y, a continuación, haga clic en **Ver todos y administrar miembros**.
9. En el panel **GlobalAdmins** , haga clic en **Agregar miembros**, seleccione la cuenta **DedicatedAdmin** y la cuenta de administrador global y, a continuación, haga clic en **Guardar > cerrar > cerrar**.

A continuación, cree directivas de acceso condicional para requerir la autenticación multifactor para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.

Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.

1. En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .
2. Haga clic en **Azure active directory > Security > el acceso condicional**.
3. En el panel **acceso condicional-directivas** , haga clic en **Directiva de línea de base: requerir MFA para administradores (versión preliminar)**.
4. En el panel **Directiva de línea de base** , haga clic en usar la **Directiva inmediatamente > guardar**.

Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.

1. En el panel **acceso condicional-directivas** , haga clic en **nueva Directiva**.
2. En el panel **nuevo** , escriba **administradores globales** en **nombre**.
3. En la sección **asignaciones** , haga clic en **usuarios y grupos**.
4. En la ficha **incluir** del panel **usuarios y grupos** , haga clic en **Seleccionar usuarios y grupos > usuarios y grupos > seleccione**.
5. En el panel de **selección** , haga clic en el grupo **GlobalAdmins** y, a continuación, haga clic en **seleccionar > listo**.
6. En la sección **asignaciones** , haga clic en **condiciones**.
7. En el panel de **condiciones** , haga clic en **riesgo de inicio de sesión**, haga clic en **sí** para **configurar**, haga clic en **alta** y **media**y, a continuación, haga clic en **seleccionar** y **listo**.
8. En la sección **controles de acceso** del panel **nuevo** , haga clic en **conceder**.
9. En el panel **conceder** , haga clic en **Bloquear acceso**y, a continuación, haga clic en **seleccionar**.
10. En el panel **nuevo** , haga clic **en** **Habilitar Directiva**y, a continuación, haga clic en **crear**.
11. Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .

Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin. Se le pedirá que configure la MFA. Esto demuestra que se está aplicando la primera Directiva.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
