---
title: Automatizar las licencias y la pertenencia a grupos para Microsoft 365 entorno de pruebas empresariales
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
description: Configure las licencias basadas en grupos y la pertenencia a grupos dinámicos en su Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905373"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizar las licencias y la pertenencia a grupos para Microsoft 365 entorno de pruebas empresariales

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

Las licencias basadas en grupos asignan o quitan automáticamente las licencias de una cuenta de usuario en función de la pertenencia a grupos. La pertenencia dinámica a grupos agrega o quita miembros a un grupo en función de las propiedades de la cuenta de usuario, como **Department** o **Country**. En este artículo se le indican las demostraciones de agregar y quitar miembros de grupo en el entorno Microsoft 365 de prueba empresarial.

La configuración de licencias automáticas y la pertenencia a grupos dinámicos en su Microsoft 365 entorno de prueba empresarial implica dos fases:

- [Fase 1: Crear su Microsoft 365 entorno de prueba empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar y probar la pertenencia dinámica a grupos y las licencias automáticas](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear su Microsoft 365 entorno de prueba empresarial

Si solo desea probar las licencias automatizadas y la pertenencia a grupos de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar las licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas de licencias automatizadas y pertenencia a grupos no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: Configurar y probar la pertenencia dinámica a grupos y las licencias automáticas

En primer lugar, cree un nuevo grupo denominado Ventas y agregue  una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el Departamento establecido en **Ventas** se unan automáticamente al grupo Ventas.

1. En una instancia privada de su explorador de Internet, inicie sesión en el centro de administración de [Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global de la suscripción Microsoft 365 E5 laboratorio de pruebas.
2. En una pestaña independiente del explorador, vaya a Azure Portal en [https://portal.azure.com](https://portal.azure.com) .
3. En Azure Portal, escriba **grupos en** el cuadro de búsqueda y, a continuación, **seleccione Grupos**.
4. en el **panel Todos los** grupos, seleccione Nuevo **grupo**.
5. En **Tipo de grupo,** **seleccione Microsoft 365**.
6. En **Nombre del grupo**, escriba **Ventas**.
7. En **Tipo de pertenencia,** seleccione **Usuario dinámico**.
8. Seleccione **Miembros de usuario dinámicos**.
9. En el **panel Reglas de pertenencia dinámica:** 
   - Seleccione la **propiedad department.**
   - Seleccione el **operador Equals.**
   - En el **cuadro** Valor, escriba **Ventas**.
10. Seleccione **Guardar**.
11. Seleccione **Crear**.

A continuación, configure el grupo Ventas para que los miembros se asignen automáticamente la Microsoft 365 E5 licencia.

1. Seleccione el **grupo** Ventas y, a continuación, **licencias**.
2. En el **panel Actualizar asignaciones de** licencias, seleccione **Microsoft 365 E5** y, a continuación, **seleccione Guardar**.
3. En el explorador, cierre la pestaña Azure Portal.

A continuación, pruebe la pertenencia a grupos dinámicos y las licencias automáticas en la cuenta de usuario 4:

1. En la **Microsoft Office inicio** del explorador, seleccione **Administrador**.
2. En la **pestaña Microsoft 365 centro de administración,** seleccione Usuarios **activos**.
3. En la **página Usuarios activos,** seleccione la **cuenta Usuario 4.**
4. En el **panel Usuario 4,** seleccione **Editar para** licencias **de producto.**
5. En el **panel Licencias de productos,** deshabilite **la Microsoft 365 E5** y, a continuación, **seleccione Guardar**  >  **cerrar**.
6. En las propiedades de la cuenta de usuario 4, compruebe que no se han asignado licencias de productos y que no hay pertenencias a grupos.
7. Para **Información de contacto,** seleccione **Editar**.
8. En el **panel Editar información de contacto,** seleccione Información de **contacto**.
9. En el **cuadro Departamento,** escriba **Ventas** y, a continuación, **seleccione Guardar**  >  **cerrar**.
10. Espere unos minutos y, a continuación, seleccione periódicamente el icono **Actualizar** en la esquina superior derecha del panel cuenta usuario 4.

Con el tiempo, debería ver lo siguiente:

- **Propiedad pertenencias a grupos** actualizada con el **grupo** Ventas.
- **Propiedad de licencias de** producto actualizada con **la Microsoft 365 E5** licencia.

Vea estos artículos para implementar la pertenencia dinámica a grupos y las licencias automáticas en producción:

- [Licencias basadas en grupos en Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Grupos dinámicos en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guía básica de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)