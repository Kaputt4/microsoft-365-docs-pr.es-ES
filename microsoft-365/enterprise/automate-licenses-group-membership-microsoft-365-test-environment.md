---
title: Automatizar la pertenencia a grupo y de la licencia para el entorno de prueba de Microsoft 365 Enterprise
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
description: Configurar licencias basadas en grupos y pertenencia a grupos dinámicos en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871547"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatizar la pertenencia a grupo y de la licencia para el entorno de prueba de Microsoft 365 Enterprise

Basadas en grupos de licencias automáticamente asignan o quitan las licencias para una cuenta de usuario en función de la pertenencia a grupos. Pertenencia al grupo dinámico agrega o quita a miembros a un grupo en función de las propiedades de cuenta de usuario, como el departamento o país. En este artículo le guiará por una demostración de ambos tipos en el entorno de prueba de Microsoft 365 Enterprise.

Hay dos fases para configurar la pertenencia a grupos de licencias automático y dinámico en su entorno de prueba de Microsoft 365 Enterprise:

1. Crear el entorno de prueba de Microsoft 365 Enterprise.
2. Configurar y probar la pertenencia al grupo dinámico y licencias automática.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea probar licencias automatizada y la pertenencia a grupos en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar licencias automatizada y la pertenencia a grupos en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas automatizadas de licencias y pertenencia a grupos no requiere el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurar y probar la pertenencia al grupo dinámico y licencias automática

En primer lugar, cree un nuevo grupo de ventas y agregar una regla de pertenencia a grupo dinámico para que las cuentas de usuario con el departamento de ventas se agregan automáticamente al grupo de ventas.

1. Uso de una instancia privada de su explorador de Internet, inicie sesión en el portal de Office 365 en [https://portal.office.com](https://portal.office.com) con la cuenta de administrador global de su suscripción de prueba de Office 365 E5.
2. En una ficha independiente del explorador, vaya al portal de Azure en [https://portal.azure.com](https://portal.azure.com).
3. En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.
4. En el servidor blade de **todos los grupos** , haga clic en **nuevo grupo**.
5. En **tipo de grupo**, seleccione **Office 365**.
6. En **nombre de grupo**, escriba **ventas**.
7. En **tipo de pertenencia**, seleccione **usuario dinámico** .
8. Haga clic en **Agregar una consulta dinámica**.
9. En **Add users where** (Agregar usuarios donde), seleccione **departamento**.
10. En el siguiente campo, seleccione **Es igual a**.
11. En el siguiente campo, escriba **ventas**.
12. Haga clic en **Agregar consulta** luego en **Crear**.
13. Cierre los módulos de **grupo** y **grupos a todos los grupos** .

A continuación, configure el grupo de ventas para que los miembros se les asigna automáticamente Office 365 E5 y movilidad en la empresa + licencias E5 de seguridad.

1. En el módulo de **información general** para Azure Active Directory, haga clic en **licencias > todos los productos de**.
2. En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y, después, haga clic en **+ Asignar**.
3. En el servidor blade **Asignar licencia** , haga clic en **usuarios y grupos**.
4. En la lista de grupos, seleccione el grupo de **ventas** .
5. Haga clic en **Seleccionar** y, después, en **Asignar**.
6. Cierre la pestaña Azure Portal del explorador.

A continuación, se prueba la pertenencia al grupo dinámico y licencias automática en la cuenta de usuario 4. 

1. En la ficha **Página principal de Microsoft Office** en el explorador, haga clic en **Admin**.
2. En la ficha del **Centro de administración de Office** , haga clic en **usuarios activos**.
3. En la página **usuarios activos** , haga clic en la cuenta de **usuario 4** .
4. En el panel **de usuario 4** , haga clic en **Editar** para **licencias de producto**.
5. En el panel de **licencias de producto** , activar la **movilidad de la empresa + E5 de seguridad** y licencias de **Office 365 Enterprise E5** desactivada y, a continuación, haga clic en **Guardar > Cerrar**.
6. En las propiedades de la cuenta de usuario 4, compruebe que se han asignado ninguna licencia de producto y no hay ningún pertenencias a grupo.
7. Para **obtener información de contacto**, haga clic en **Editar** .
8. En el panel de **información de contacto de editar** , haga clic en **información de contacto**.
9. En el campo **departamento** , escriba **ventas**y, a continuación, haga clic en **Guardar > Cerrar**.
10. Espere unos minutos y, a continuación, haga clic periódicamente en el icono de actualización en la parte superior derecha del panel de la cuenta de usuario 4. 

En el tiempo debería ver el:

- Propiedad **pertenencias a grupo** actualizado con el grupo de **ventas** .
- Propiedad de **licencias de producto** que se ha actualizado con las licencias de **movilidad en la empresa + seguridad E5** y **Office 365 Enterprise E5** .

En la fase de identidad para obtener información y vínculos para implementar la pertenencia a grupos dinámicos y licencias automática en producción, vea estos pasos:

- [Configurar las licencias automáticas](identity-group-based-licensing.md)
- [Configurar pertenencia a grupo dinámico](identity-automatic-group-membership.md)

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
