---
title: Configuración de GDAP para los clientes
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: magarlan, chrigreen
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo configurar GDAP para los clientes.
ms.openlocfilehash: b7baa473b19c2431edf1f5e85c9f106cc60e962d
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785909"
---
# <a name="set-up-gdap-for-your-customers"></a>Configuración de GDAP para los clientes


> [!NOTE]
> Esta característica se está implementando a diferentes velocidades para nuestros clientes. Si aún no ve esta característica, debería verla pronto.

Los partners incorporados a Microsoft 365 Lighthouse ahora pueden configurar todos sus clientes con privilegios administrativos delegados granulares (GDAP) a través de Lighthouse, independientemente de sus licencias o tamaño. Lighthouse permite a los asociados realizar una transición rápida de su organización a GDAP y comenzar el viaje a los privilegios mínimos para su acceso delegado a los clientes. Al configurar su organización con GDAP para los inquilinos de cliente que administra, los usuarios de la organización tienen los permisos necesarios para realizar su trabajo y, al mismo tiempo, proteger a los inquilinos del cliente.

El acceso delegado a través de DAP o GDAP es un requisito previo para que los clientes estén totalmente incorporados a Lighthouse. Por lo tanto, la creación de relaciones GDAP puede ser el primer paso para administrar los clientes en Lighthouse.

Durante el proceso de configuración de GDAP, asignará roles a niveles de funciones de trabajo para los empleados de su organización y, a continuación, creará plantillas de GDAP que asignarán esos roles en capas a grupos de seguridad específicos con usuarios para grupos de clientes. Los roles GDAP se limitan a [los roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference) y, al configurar GDAP, verá recomendaciones para un conjunto de roles necesarios para cada nivel.

## <a name="before-you-begin"></a>Antes de empezar

- Tendrá que tener permisos específicos en su propio inquilino:

  - Para establecer grupos de seguridad de GDAP y agregar usuarios, necesitará administrador global, administrador de usuarios o administrador de grupos para configurar usuarios con acceso permanente a roles de GDAP. Puede asignar estos roles en Azure Active Directory (ADD).

    - Para habilitar el nivel Solo just-in-time (JIT), deberá tener un administrador global o una combinación de administrador de usuarios y administrador de roles con privilegios.

  - Para crear y completar relaciones de GDAP, debe ser miembro del grupo agentes de Administración en el Centro de partners.

- Cualquier cliente puede ser administrado por un asociado de Lighthouse, si está configurado en el Centro de partners con una relación de revendedor o una relación delegada existente (DAP o GDAP).

- Para habilitar los permisos de nivel solo JIT, también necesitará una licencia de Azure AD P2.

## <a name="set-up-gdap-for-the-first-time"></a>Configurar GDAP por primera vez

Al configurar GDAP por primera vez, debe completar las secciones siguientes en orden. Una vez completado, puede volver y editar cualquier sección según sea necesario.

Para empezar:

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Inicio.**

2. En la tarjeta **Configurar GDAP para su organización** , seleccione **Iniciar configuración.**

3. Complete las secciones siguientes en orden.

    [Paso 1: Definir niveles de permisos](#step-1-define-tiers-of-permissions)

    [Paso 2: Crear plantillas GDAP](#step-2-create-gdap-templates)

    [Paso 3: Creación de grupos de seguridad](#step-3-create-security-groups)

    [Paso 4: Asignación de inquilinos de clientes](#step-4-assign-customer-tenants)

    [Paso 5: Revisar la configuración](#step-5-review-settings)

### <a name="step-1-define-tiers-of-permissions"></a>Paso 1: Definir niveles de permisos

Elija los roles necesarios para cada nivel en función de las funciones de trabajo de los empleados.

1. En la página **Definir niveles de permisos** , seleccione los roles necesarios para cada nivel en función de las funciones de trabajo de los empleados. Puede

    - Adoptar configuraciones recomendadas o

    - Asigne manualmente un rol a cada nivel.

2. Seleccione **Siguiente** para ir a la sección siguiente o seleccione **Guardar y cerrar** para guardar la configuración y salir del programa de instalación de GDAP.

Puede cambiar el nombre de los niveles para que coincidan con sus necesidades organizativas. Puede quitar roles de cada nivel dentro de las recomendaciones. Algunos roles no se pueden agregar a niveles diferentes; por ejemplo, los roles del nivel Solo JIT no se pueden agregar a ningún otro nivel.

### <a name="step-2-create-gdap-templates"></a>Paso 2: Crear plantillas GDAP

Una plantilla GDAP es una colección de:

- Niveles con roles

- Grupos de seguridad por nivel

- Usuarios de cada grupo de seguridad
 
Para crear una plantilla GDAP:

1. En la página **Crear plantillas GDAP** , seleccione **Crear plantilla**.

2. En el panel de plantillas, escriba el nombre y la descripción de la plantilla en los campos adecuados.

3. Seleccione uno o varios niveles de la lista.

4. Seleccione **Guardar**.

5. Seleccione **Siguiente** para ir a la sección siguiente o seleccione **Guardar y cerrar** para guardar la configuración y salir del programa de instalación de GDAP.

### <a name="step-3-create-security-groups"></a>Paso 3: Creación de grupos de seguridad

Necesitará al menos un grupo de seguridad por nivel para cada plantilla. Para la primera plantilla, creará un nuevo grupo de seguridad, pero en las plantillas posteriores, puede reutilizar los grupos si lo desea.

1. En la página **Crear grupos de seguridad** , seleccione **Crear grupo de seguridad**.

2. En el panel del grupo de seguridad, escriba el nombre y la descripción.

3. Seleccione **Agregar usuarios**.

4. En la lista Agregar usuarios, seleccione los usuarios que desea incluir en este grupo de seguridad.

5. Seleccione **Guardar.**

6. Seleccione **Guardar** nuevamente.

7. Seleccione **Siguiente** para ir a la sección siguiente o seleccione **Guardar y cerrar** para guardar la configuración y salir del programa de instalación de GDAP.

### <a name="step-4-assign-customer-tenants"></a>Paso 4: Asignación de inquilinos de clientes

Asigne grupos de clientes a cada plantilla. Cada cliente solo se puede asignar a una plantilla, por lo que, una vez seleccionado, ese inquilino del cliente no se mostrará como una opción en las plantillas posteriores.

Si desea reasignar un inquilino de cliente, vuelva a ejecutar el programa de instalación de GDAP y anule la selección de ese cliente de la asignación existente. A continuación, puede reasignarlo a otra plantilla. Puede filtrar la lista mediante el cuadro de búsqueda de la esquina superior derecha.

1. En la página **Asignar inquilinos de cliente** , seleccione los inquilinos que desea asociar con el grupo de seguridad que ha creado.

2. Seleccione **Siguiente** para ir a la sección siguiente o seleccione **Guardar y cerrar** para guardar la configuración y salir del programa de instalación de GDAP.

### <a name="step-5-review-settings"></a>Paso 5: Revisar la configuración

1. En la página **Revisar configuración** , revise la configuración que creó y, a continuación, seleccione **Finalizar.**

2. Seleccione **Listo.**

Si los inquilinos de clientes ya tenían una relación DAP, durante la ventana sin consentimiento, esta configuración se aplicará automáticamente. En el caso de los clientes sin DAP o si no se ha cerrado la ventana de consentimiento, al elegir **Finalizar** se le llevará a la última página donde se generan vínculos de consentimiento para cada cliente según sea necesario. Una vez que el cliente da su consentimiento a la relación GDAP, el resto de la configuración se aplicará automáticamente.

Una vez que haya completado la configuración de GDAP, puede navegar a diferentes pasos para realizar actualizaciones o cambios en niveles, roles, grupos de seguridad o plantillas. Las relaciones de GDAP también estarán visibles en el Centro de partners y los grupos de seguridad también estarán visibles en Azure AD.

## <a name="related-content"></a>Contenido relacionado

[Introducción a los permisos](m365-lighthouse-overview-of-permissions.md) (artículo)\
[Configuración de la seguridad del portal](m365-lighthouse-configure-portal-security.md) (artículo)\
[Introducción a los privilegios de administrador delegados pormenorizadas (GDAP)](/partner-center/gdap-introduction) (artículo)\
[Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference) (artículo)\
[Obtenga información sobre los grupos y los derechos de acceso en Azure Active Directory](/azure/active-directory/fundamentals/concept-learn-about-groups) (artículo)\
[¿Qué es la administración de derechos de Azure AD?](/azure/active-directory/governance/entitlement-management-overview) (artículo)