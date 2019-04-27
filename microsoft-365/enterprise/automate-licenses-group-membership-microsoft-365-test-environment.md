---
title: Automatizar la concesión de licencias y la pertenencia a grupos para el entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure las licencias basadas en grupos y la pertenencia a grupos dinámica en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 4ee929b345469d9cab05968a4a4c7f7399635b32
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353082"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatizar la concesión de licencias y la pertenencia a grupos para el entorno de prueba de Microsoft 365 Enterprise

Las licencias basadas en grupos asignan o eliminan automáticamente licencias de una cuenta de usuario en función de la pertenencia a grupos. La pertenencia al grupo dinámico agrega o quita miembros de un grupo en función de las propiedades de la cuenta de usuario, como departamento o país. Este artículo le guiará por el proceso de demostración tanto en el entorno de prueba de Microsoft 365 Enterprise.

Hay dos fases para configurar la licencia automática y la pertenencia a grupos dinámica en el entorno de prueba de Microsoft 365 Enterprise:

1. Crear el entorno de pruebas de Microsoft 365 Enterprise.
2. Configurar y probar la pertenencia a grupos dinámica y las licencias automáticas.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise

Si solo quiere probar la concesión de licencias automatizadas y la pertenencia a grupos de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la concesión de licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas

En primer lugar, cree un nuevo grupo de ventas y agregue una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el Departamento establecido en ventas se agreguen automáticamente al grupo ventas.

1. Con una instancia privada del explorador de Internet, inicie sesión en el portal de Office 365 [https://portal.office.com](https://portal.office.com) en con la cuenta de administrador global de la suscripción a Office 365 E5 del laboratorio de pruebas.
2. En una pestaña independiente del explorador, vaya a Azure portal en [https://portal.azure.com](https://portal.azure.com).
3. En Azure Portal, haga clic en **Azure Active Directory > Usuarios y grupos > Todos los grupos**.
4. En la hoja **todos los grupos** , haga clic en **nuevo grupo**.
5. En **tipo de grupo**, seleccione **Office 365**.
6. En **nombre de grupo**, escriba **sales**.
7. En **tipo**de pertenencia, seleccione **usuario dinámico** .
8. Haga clic en **Agregar una consulta dinámica**.
9. En **Add users where** (Agregar usuarios donde), seleccione **departamento**.
10. En el siguiente campo, seleccione **Es igual a**.
11. En el campo NEXT, escriba **sales**.
12. Haga clic en **Agregar consulta** luego en **Crear**.
13. Cierre los blades **Grupo** y **grupos-todos los grupos** .

A continuación, configure el grupo ventas para que a los miembros se les asigne automáticamente licencias de Office 365 E5 y Enterprise Mobility + Security E5.

1. En la hoja de **información general** de Azure Active Directory, haga clic en **licencias > todos los productos**.
2. En la lista, seleccione **Enterprise Mobility + Security E5** y **Office 365 Enterprise E5** y, después, haga clic en **+ Asignar**.
3. En la hoja **asignar licencia** , haga clic en **usuarios y grupos**.
4. En la lista de grupos, seleccione el grupo **ventas** .
5. Haga clic en **Seleccionar** y luego en **Siguiente**.
6. Cierre la pestaña Azure Portal del explorador.

A continuación, pruebe la pertenencia a grupos dinámica y las licencias automáticas en la cuenta de usuario 4. 

1. Desde la pestaña **Página principal de Microsoft Office** del explorador, haga clic en **Administración**.
2. En la pestaña **centro de administración de 365 de Microsoft** , haga clic en **usuarios activos**.
3. En la página **usuarios activos** , haga clic en la cuenta de **usuario 4** .
4. En el panel **usuario 4** , haga clic en **Editar** para **licencias de productos**.
5. En el **Panel licencias de productos** , active las licencias de **Enterprise Mobility + Security e5** y **Office 365 Enterprise E5** y, después, haga clic en **Guardar > cerrar**.
6. En las propiedades de la cuenta usuario 4, compruebe que no se haya asignado ninguna licencia de producto y que no hay pertenencias a grupos.
7. Haga clic en **Editar** para obtener **información de contacto**.
8. En el panel **editar información de contacto** , haga clic en **información de contacto**.
9. En el campo **Departamento** , escriba **ventas**y, a continuación, haga clic en **Guardar > cerrar**.
10. Espere unos minutos y, a continuación, haga clic periódicamente en el icono de actualización en la esquina superior derecha del panel de la cuenta de usuario 4. 

En el tiempo debería ver lo siguiente:

- Pertenencias a **grupos** (propiedad) actualizada con el grupo **ventas** .
- Propiedad de **licencias de producto** actualizada con las licencias de **Enterprise Mobility + Security e5** y **Office 365 Enterprise E5** .

Consulte estos pasos en la fase de identidad para obtener información y vínculos para implementar la pertenencia a grupos dinámica y las licencias automáticas en producción:

- [Configurar las licencias automáticas](identity-self-service-group-management.md#identity-group-license)
- [Configurar la pertenencia a grupos dinámica](identity-self-service-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Fase 2: Identidad](identity-infrastructure.md)

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementación de Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
