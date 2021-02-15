---
title: Automatizar las licencias y la pertenencia a grupos para su entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure las licencias basadas en grupos y la pertenencia a grupos dinámicos en su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487581"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizar las licencias y la pertenencia a grupos para su entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo se puede usar para Entornos de prueba de Microsoft 365 para empresas.*

Las licencias basadas en grupos asignan o quitan automáticamente licencias de una cuenta de usuario en función de la pertenencia a grupos. La pertenencia a grupos dinámicos agrega o quita miembros a un grupo en función de las propiedades de la cuenta de usuario, como **Departamento** o **País.** En este artículo se indican las demostraciones de agregar y quitar miembros del grupo en el entorno de prueba de Microsoft 365 para empresas.

La configuración de licencias automáticas y la pertenencia a grupos dinámicos en el entorno de prueba de Microsoft 365 para empresas consta de dos fases:

- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar y probar la pertenencia a grupos dinámicos y las licencias automáticas](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si solo desea probar las licencias automatizadas y la pertenencia a grupos de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea probar las licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Las pruebas de licencias automatizadas y pertenencia a grupos no requieren el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurar y probar la pertenencia a grupos dinámicos y las licencias automáticas

En primer lugar, cree un nuevo grupo denominado Ventas y agregue  una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el departamento establecido en **Ventas** se unan automáticamente al grupo Ventas.

1. En una instancia privada del explorador de Internet, inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global de su suscripción al laboratorio de pruebas de Microsoft 365 E5.
2. En una pestaña independiente del explorador, vaya a Azure Portal en [https://portal.azure.com](https://portal.azure.com) .
3. En Azure Portal, escriba **grupos en** el cuadro de búsqueda y, a continuación, **seleccione Grupos**.
4. en el **panel Todos los** grupos, seleccione Nuevo **grupo.**
5. En **Tipo de grupo,** seleccione **Microsoft 365**.
6. En **Nombre del grupo,** escriba **Ventas**.
7. En **Tipo de pertenencia,** seleccione **Usuario dinámico.**
8. Seleccione **Miembros de usuario dinámicos.**
9. En el panel **Reglas de pertenencia dinámica:** 
   - Seleccione la **propiedad department.**
   - Seleccione el **operador Igual** a.
   - En el **cuadro** Valor, escriba **Ventas**.
10. Seleccione **Guardar**.
11. Seleccione **Crear**.

A continuación, configure el grupo ventas para que se asigne automáticamente a los miembros la licencia de Microsoft 365 E5.

1. Seleccione el **grupo** Ventas y, a continuación, **seleccione Licencias.**
2. En el **panel Actualizar asignaciones de** licencias, seleccione Microsoft **365 E5** y, a continuación, **seleccione Guardar**.
3. En el explorador, cierre la pestaña de Azure Portal.

A continuación, pruebe la pertenencia a grupos dinámicos y las licencias automáticas en la cuenta usuario 4:

1. En la **Microsoft Office inicio** del explorador, seleccione **Administrador.**
2. En la pestaña Centro de administración de **Microsoft 365,** seleccione **Usuarios activos.**
3. En la **página Usuarios activos,** seleccione la **cuenta Usuario 4.**
4. En el **panel Usuario 4,** seleccione **Editar para** licencias **de producto.**
5. En el **panel Licencias de productos,** deshabilite la licencia de **Microsoft 365 E5** y, a continuación, **seleccione Guardar**  >  **cerrar.**
6. En las propiedades de la cuenta usuario 4, compruebe que no se han asignado licencias de producto y que no hay pertenencias a grupos.
7. Para **obtener información de** contacto, seleccione **Editar**.
8. En el **panel Editar información de contacto,** seleccione Información de **contacto.**
9. En el **cuadro Departamento,** escriba **Ventas** y, a continuación, **seleccione Guardar**  >  **cerrar**.
10. Espere unos minutos y, a  continuación, seleccione periódicamente el icono Actualizar en la esquina superior derecha del panel de cuentas usuario 4.

Con el tiempo, debería ver lo siguiente:

- **Propiedad de pertenencia a grupos** actualizada con el **grupo** Ventas.
- **Propiedad de licencias de** producto actualizada con la **licencia de Microsoft 365 E5.**

Vea estos artículos para implementar la pertenencia a grupos dinámicos y las licencias automáticas en producción:

- [Licencias basadas en grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Grupos dinámicos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
