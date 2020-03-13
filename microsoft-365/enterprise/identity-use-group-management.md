---
title: 'Paso 5: Usar grupos para administración'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Se pueden usar grupos para automatizar la administración de algunas tareas administrativas.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544049"
---
# <a name="step-5-use-groups-for-management"></a>Paso 5: Usar grupos para administración

![Fase 2-Identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Permitir a los usuarios crear y administrar sus propios grupos

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*

En esta sección, podrá identificar grupos de Azure Active Directory (Azure AD) que pueden ser administrados por los propietarios del grupo en lugar de los administradores de TI. Conocida como *administración autoservicio de grupos*, esta característica permite a los propietarios del grupo que no están asignados a un rol de administrador crear y administrar grupos de seguridad. 

Los usuarios pueden solicitar la pertenencia a un grupo de seguridad y esa solicitud va al propietario del grupo, en lugar de un administrador de TI. Esto permite delegar el control diario de la pertenencia al grupo a los propietarios del equipo, proyecto o empresa que comprenden el uso empresarial del grupo y pueden administrar su pertenencia.

>[!Note]
>La administración de grupos de autoservicio está disponible solo para grupos de seguridad de Azure AD y Office 365. No está disponible para grupos habilitados por correo electrónico listas de distribución o grupos sincronizados desde su Active Directory Domain Services (AD DS) local.
>

Para obtener más información, consulte las [instrucciones para configurar un grupo de Azure AD para la administración de autoservicio](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-self-service-groups) correspondientes a esta sección.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Configurar la pertenencia a grupo dinámico

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*

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
|![Guías de laboratorio de pruebas en Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-dyn-groups) correspondientes a esta sección.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Configurar las licencias automáticas

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*

En esta sección, deberá configurar los grupos de seguridad en Azure AD para asignar automáticamente licencias de un conjunto de suscripciones para todos los miembros del grupo. Esto se conoce como *licencias basadas en grupos*. Si una cuenta de usuario se añade o se elimina del grupo, se asignará o quitará la asignación de las licencias de suscripciones del grupo automáticamente desde la cuenta de usuario.

Para Microsoft 365 Enterprise, configurará grupos de seguridad de Azure AD para asignar la licencia apropiada de Microsoft 365 Enterprise.

Asegúrese de que tiene suficientes licencias para todos los miembros del grupo. Si se queda sin licencias, no se asignarán licencias a nuevos usuarios hasta que estén disponibles otras nuevas.

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
|![Guías de laboratorio de pruebas en Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Automatizar licencias y la pertenencia a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-group-license) correspondientes a esta sección.

|||
|:-------|:-----|
|![Paso 6](../media/stepnumbers/Step6.png)| [Configure Identity Governance](identity-configure-identity-governance.md) |
