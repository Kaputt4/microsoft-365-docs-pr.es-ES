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
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487641"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteger las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Puede evitar ataques digitales en su organización asegurándose de que las cuentas de administrador son lo más seguras posible. 

En este artículo se describe cómo usar las directivas de acceso condicional de Azure Active Directory (Azure AD) para proteger las cuentas de administrador global.

La protección de las cuentas de administrador global en el entorno de prueba de Microsoft 365 para empresas implica dos fases:
- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurar directivas de acceso condicional](#phase-2-configure-conditional-access-policies)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si desea probar la protección de la cuenta de administrador global de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la protección de la cuenta de administrador global en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La comprobación de la protección de la cuenta de administrador global no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la protección de la cuenta de administrador global y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurar directivas de acceso condicional

En primer lugar, cree una nueva cuenta de usuario como administrador global dedicado.

1. En una pestaña independiente, abra el [centro de administración de Microsoft 365](https://admin.microsoft.com/).
2. Seleccione **usuarios**  >  **activos**y, a continuación, seleccione **Agregar un usuario**.
3. En el panel **Agregar usuario** , escriba **DedicatedAdmin** en los cuadros **nombre**, **nombre para mostrar**y nombre de **usuario** .
4. Seleccione **contraseña**, seleccione **me permite crear la contraseña**y, a continuación, escriba una contraseña segura. Registre la contraseña de esta nueva cuenta en una ubicación segura.
5. Seleccione **Siguiente**.
6. En el panel **asignar licencias de producto** , seleccione **Microsoft 365 E5**y, a continuación, seleccione **siguiente**.
7. En el panel **configuración opcional** , seleccione **roles**de administrador global de  >  **acceso al centro de administración**  >  **Global admin**  >  **Next**.
8. En el panel **está casi listo** , seleccione **terminar de agregar**y, a continuación, haga clic en **cerrar**.

A continuación, cree un nuevo grupo denominado GlobalAdmins y agréguele la cuenta DedicatedAdmin.

1. En la pestaña **centro de administración de 365 de Microsoft** , seleccione **grupos** en el panel de navegación izquierdo y, a continuación, seleccione **grupos**.
2. Seleccione **Agregar un grupo**.
3. En el panel **elegir un tipo de grupo** , seleccione **seguridad**y, a continuación, seleccione **siguiente**.
4. En el panel **configurar conceptos básicos** , seleccione **Crear grupo**y, a continuación, haga clic en **cerrar**.
5. En el panel **revisar y finalizar agregar grupo** , escriba **GlobalAdmins**y, a continuación, seleccione **siguiente**.
7. En la lista de grupos, seleccione el grupo **GlobalAdmins** .
8. En el panel **GlobalAdmins** , seleccione **miembros**y, a continuación, seleccione **Ver todos y administrar miembros**.
9. En el panel **GlobalAdmins** , seleccione **Agregar miembros**, seleccione la cuenta **DedicatedAdmin** y la cuenta de administrador global y, a continuación, seleccione **Guardar**  >  **cerrar**  >  **Close**.

A continuación, cree directivas de acceso condicional para requerir multi-factor Authentication para las cuentas de administrador global y para denegar la autenticación si el riesgo de inicio de sesión es medio o alto.

Esta primera Directiva requiere que todas las cuentas de administrador global usen MFA.

1. En una pestaña nueva del explorador, vaya a [https://portal.azure.com](https://portal.azure.com) .
2. Haga **Azure Active Directory**clic en  >  **Security**  >  **acceso condicional**de seguridad de Azure Active Directory.
3. En el panel **acceso condicional-directivas** , seleccione **Directiva de línea de base: solicitar MFA para administradores (versión preliminar)**.
4. En el panel **Directiva de línea de base** , seleccione usar la **Directiva inmediatamente > guardar**.

Esta segunda Directiva bloquea el acceso a la autenticación de la cuenta de administrador global cuando el riesgo de inicio de sesión es medio o alto.

1. En el panel **acceso condicional-directivas** , seleccione **nueva Directiva**.
2. En el panel **nuevo** , escriba **administradores globales** en **nombre**.
3. En la sección **asignaciones** , seleccione **usuarios y grupos**.
4. En la ficha **incluir** del panel **usuarios y grupos** , seleccione **Seleccionar usuarios y**grupos, seleccione usuarios y  >  **grupos**  >  **Select**.
5. En el panel de **selección** , seleccione el grupo **GlobalAdmins** y, a continuación, seleccione **seleccionar**  >  **listo**.
6. En la sección **asignaciones** , seleccione **condiciones**.
7. En el panel de **condiciones** , seleccione **riesgo de inicio de sesión**, seleccione **sí** para **configurar**, seleccione **alta** y **media**y, a continuación, seleccione **seleccionar** y **listo**.
8. En la sección **controles de acceso** del panel **nuevo** , seleccione **conceder**.
9. En el panel **conceder** , seleccione **Bloquear acceso**y, a continuación, seleccione **seleccionar**.
10. En el panel **nuevo** , seleccione **activado** para **Habilitar Directiva**y, a continuación, seleccione **crear**.
11. Cierre las pestañas **Azure portal** y **centro de administración de Microsoft 365** .

Para probar la primera Directiva, cierre e inicie sesión con la cuenta DedicatedAdmin. Se le pedirá que configure la MFA. Esto demuestra que se está aplicando la primera Directiva.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
