---
title: 'Paso 6: Uso de grupos para facilitar la administración'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la administración de grupos de autoservicio de Azure AD.
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283533"
---
# <a name="step-6-use-groups-for-easier-management"></a>Paso 6: Uso de grupos para facilitar la administración

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Permitir a los usuarios crear y administrar sus propios grupos

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, podrá identificar grupos de Azure Active Directory (Azure AD) que pueden ser administrados por los propietarios del grupo en lugar de los administradores de TI. Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad. 

Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.

>[!Note]
>La administración de grupos de autoservicio está disponible solo para grupos de seguridad de Azure AD y Office 365. No está disponible para grupos habilitados por correo electrónico listas de distribución o grupos sincronizados desde su Active Directory Domain Services (AD DS) local.
>

Para obtener más información, consulte las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-self-service-groups) correspondientes a esta sección.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Configurar la pertenencia a grupo dinámico

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, creará una serie de reglas para añadir o eliminar automáticamente cuentas de usuario como miembros de un grupo de Azure AD. Esto se conoce como *pertenencia a grupo dinámico*. Las reglas se basan en atributos de cuenta de usuario, como el país o el departamento.

Las reglas se aplican de esta forma:

- Si la nueva cuenta de usuario coincide con todas las reglas del grupo, se convierte en un miembro.
- Si una cuenta de usuario no es miembro del grupo, pero sus atributos cambian para que coincidan con todas las reglas del grupo, se convierte en un miembro de ese grupo.
- Si una cuenta de usuario no coincide con todas las reglas del grupo, no se agregará al grupo.
- Si una cuenta de usuario es miembro del grupo, pero sus atributos cambian, por lo que ya no coinciden con todas las reglas del grupo, se quitará como miembro del grupo.

Para usar la pertenencia dinámica, primero necesita determinar los conjuntos de grupos que tienen un conjunto común de atributos de cuenta de usuario. Por ejemplo, todos los miembros del departamento de ventas necesitan estar en el grupo de Azure AD “Ventas”, basándose en el atributo de cuenta de usuario “Departamento” establecido en “Ventas”.

Vea las [instrucciones para crear y configurar las reglas para un grupo de Azure AD dinámico](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Los resultados de esta sección son:

- Un conjunto de grupos de Azure AD que se puede configurar para la pertenencia dinámica.
- Un conjunto de reglas para cada grupo dinámico.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-dyn-groups) correspondientes a esta sección.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Configurar las licencias automáticas

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, deberá configurar los grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones para todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si una cuenta de usuario se añade o se elimina del grupo, las licencias de suscripciones del grupo se asignan o se eliminan automáticamente de la cuenta de usuario.

Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar estas dos licencias:

- Office 365 Enterprise E3 o E5
- Enterprise Mobility + Security (EMS) E3 o E5

Con los grupos que identificó en el paso 2, busque grupos que contengan una lista de cuentas donde todos los usuarios del grupo necesiten tener licencias de Office 365 y EMS. Asegúrese de tener licencias suficientes para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a los nuevos usuarios hasta que haya más licencias disponibles.

>[!Note]
>No configure las *licencias basadas en grupos* para los grupos que contengan cuentas entre empresas (B2B) de Azure.
>

Para obtener más información, vea [Conceptos básicos de las licencias basadas en grupos de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Vea los [pasos para configurar las licencias basadas en grupos para un grupo de seguridad de Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Los resultados de esta sección son:

- Identificó los grupos de seguridad adecuados para las licencias basadas en grupos.
- Configuró estos grupos para las licencias basadas en grupos.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-group-license) correspondientes a esta sección.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de identidades](identity-exit-criteria.md)
