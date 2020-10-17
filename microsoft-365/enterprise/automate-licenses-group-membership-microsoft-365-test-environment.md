---
title: Automatizar la concesión de licencias y la pertenencia a grupos de un entorno de prueba de Microsoft 365 para empresas
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
description: Configure las licencias basadas en grupos y la pertenencia a grupos dinámicas en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d770e7be3b0b55855f1fee26a45d55260c3074cb
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487581"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatizar la concesión de licencias y la pertenencia a grupos de un entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*

Las licencias basadas en grupos asignan o eliminan automáticamente licencias de una cuenta de usuario en función de la pertenencia a grupos. La pertenencia al grupo dinámico agrega o quita miembros de un grupo en función de las propiedades de la cuenta de usuario, como **Departamento** o **país**. En este artículo se explican las demostraciones de agregar y quitar miembros de grupo en el entorno de prueba de Microsoft 365 para empresas.

La configuración de licencias automáticas y la pertenencia a grupos dinámicas en el entorno de prueba de Microsoft 365 para empresas implica dos fases:

- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere probar la concesión de licencias automatizadas y la pertenencia a grupos de una manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea probar la concesión de licencias automatizadas y la pertenencia a grupos en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la concesión de licencias automatizada y la pertenencia a grupos no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Fase 2: configurar y probar la pertenencia a grupos dinámica y las licencias automáticas

En primer lugar, cree un nuevo grupo denominado ventas y agregue una regla de pertenencia a grupos dinámicos para que las cuentas de usuario con el **Departamento** establecido en **ventas** se unan automáticamente al grupo ventas.

1. En una instancia privada del explorador de Internet, inicie sesión en el [centro de administración de microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global de la suscripción al laboratorio de pruebas de Microsoft 365 E5.
2. En una pestaña independiente del explorador, vaya a Azure portal en [https://portal.azure.com](https://portal.azure.com) .
3. En el portal de Azure, escriba **grupos** en el cuadro de búsqueda y, a continuación, seleccione **grupos**.
4. en el panel **todos los grupos** , seleccione **nuevo grupo**.
5. En **tipo de grupo**, seleccione **Microsoft 365**.
6. En **nombre de grupo**, escriba **ventas**.
7. En **tipo de pertenencia**, seleccione **usuario dinámico**.
8. Seleccione **miembros de usuario dinámicos**.
9. En el panel **reglas de pertenencia dinámica** : 
   - Seleccione la propiedad **Department** .
   - Seleccione el operador **es igual** a.
   - En el cuadro **valor** , escriba **sales**.
10. Seleccione **Guardar**.
11. Seleccione **Crear**.

A continuación, configure el grupo ventas para que a los miembros se les asigne automáticamente la licencia 365 E5 de Microsoft.

1. Seleccione el grupo **ventas** y, a continuación, seleccione **licencias**.
2. En el panel **Actualizar asignaciones de licencia** , seleccione **Microsoft 365 E5**y, a continuación, seleccione **Guardar**.
3. En el explorador, cierre la pestaña Azure portal.

A continuación, pruebe la pertenencia al grupo dinámico y la licencia automática en la cuenta de usuario 4:

1. En la pestaña **Página principal de Microsoft Office** del explorador, seleccione **Administración**.
2. En la pestaña **centro de administración de 365 de Microsoft** , seleccione **usuarios activos**.
3. En la página **usuarios activos** , seleccione la cuenta de **usuario 4** .
4. En el panel **usuario 4** , seleccione **Editar** para **licencias de productos**.
5. En el panel **licencias de productos** , deshabilite la licencia de **Microsoft 365 E5** y, a continuación, seleccione **Guardar**  >  **cierre**.
6. En las propiedades de la cuenta usuario 4, compruebe que no se haya asignado ninguna licencia de producto y que no hay pertenencias a grupos.
7. Para obtener **información de contacto**, seleccione **Editar**.
8. En el panel **editar información de contacto** , seleccione **información de contacto**.
9. En el cuadro **Departamento** , escriba **sales**y, a continuación, seleccione **Guardar**  >  **cierre**.
10. Espere unos minutos y, a continuación, seleccione periódicamente el icono de **actualización** en la esquina superior derecha del panel de la cuenta de usuario 4.

En el tiempo, debería ver lo siguiente:

- **Pertenencias a grupos** (propiedad) actualizada con el grupo **ventas** .
- Propiedad de **licencias de producto** actualizada con la licencia de **Microsoft 365 E5** .

Consulte estos artículos para implementar la pertenencia a grupos dinámica y las licencias automáticas en producción:

- [Licencias basadas en grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Grupos dinámicos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Mapa de ruta de identidad](identity-roadmap-microsoft-365.md)

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
