---
title: 'Paso 1: Planear los usuarios y grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Planee el conjunto de usuarios y grupos que funcionarán para su organización.
ms.openlocfilehash: ac7f5e56bae882e01c31cacee856f73b0ead772f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071639"
---
# <a name="step-1-plan-for-users-and-groups"></a>Paso 1: Planear los usuarios y grupos

*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, creará una infraestructura de identidades que combine usuarios, grupos y pertenencia a grupos, con características de seguridad en la configuración correcta. Esto le permite:

- Mantener el control sobre quién tiene acceso a recursos en su entorno.
- Proteger el acceso con controles que ofrecen garantías seguras de identidad (usuarios que son quienes afirman ser) y el acceso desde dispositivos seguros.
- Aprovisionar los recursos de su entorno con permisos adecuados que reducen los posibles daños y pérdidas de datos. 
- Supervisar el entorno para detectar comportamientos de usuario anómalos y tomar medidas automáticamente.

## <a name="plan-your-primary-identity-provider"></a>Planear el proveedor de identidades principal

Para crear una infraestructura de identidades, designará un proveedor de identidades principal. Este servicio almacena cuentas de usuario y sus atributos, grupos y pertenencias, y facilita la administración continuada de estos.

Cuando su organización adopte Microsoft 365 Enterprise, el proveedor de identidades principal será:

- **Active Directory Domain Services (AD DS)**, un proveedor de identidades de intranet hospedado en equipos que ejecutan Windows Server. Normalmente lo usan organizaciones que tienen un proveedor de identidades local existente.
- **Azure Active Directory (Azure AD)**, una identidad como servicio (IDaaS) basada en la nube que ofrece una amplia variedad de funciones para administrar y proteger su entorno. Esta opción suelen usarla las organizaciones que no tienen una infraestructura local existente.

Si su organización ya cuenta con un proveedor de identidades local, necesita sincronizar las cuentas de usuario y grupos de AD DS con Azure AD para ofrecer un acceso más fluido a los servicios basados en la nube de Microsoft 365 Enterprise. También puede usar Azure AD para crear y administrar grupos que solo existan en la nube de Microsoft.

Cuando tenga los usuarios y grupos en Azure AD, puede:

- Administrar todas las cuentas de Azure AD para todas sus aplicaciones en la nube. 
- Usar el mismo conjunto de controles para proteger el acceso a aplicaciones en su entorno.
- Colaborar con socios externos.
- Supervisar comportamientos de cuenta anómalos, como intentos de inicio de sesión sospechosos, y tomar medidas automáticamente.

Siga las instrucciones que se indican en las dos secciones siguientes para planear e implementar las cuentas de usuario y grupos.

## <a name="categorize-your-users"></a>Clasificar por categorías los usuarios
Los usuarios de las organizaciones se pueden clasificar por categorías de distintas formas. Por ejemplo, algunos son empleados y tienen un estado permanente. Otros son proveedores, contratistas o socios que tienen un estado temporal. Y otros son usuarios externos que no tienen cuentas de usuario, pero a los que es necesario conceder acceso a servicios y recursos específicos para facilitar la interacción y la colaboración. Por ejemplo:

- Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube
- Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración

Cuente el número de tipos de usuario de su organización. ¿Cuáles son las agrupaciones? Por ejemplo, puede agrupar usuarios por funciones de alto nivel o finalidades para su organización.

Además, algunos servicios en la nube se pueden compartir con usuarios externos a la organización sin cuentas de usuario. También necesitará identificar estos grupos de usuarios.

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>Planear grupos de AD DS y Azure AD

Puede usar grupos en Azure AD para distintas finalidades que simplifiquen la administración de su entorno de nube. Por ejemplo, para grupos de Azure AD, puede:

- Use licencias basadas en grupos para asignar licencias a sus cuentas de usuario automáticamente en cuanto se agreguen a Azure AD o se sincronicen desde AD DS. 
- Agregue cuentas de usuario a grupos específicos dinámicamente basándose en los atributos de cuenta de usuario, como el departamento.  
- Aprovisionar automáticamente usuarios para aplicaciones de software como servicio (SaaS) y proteger el acceso a esas aplicaciones con autenticación multifactor y otras reglas de acceso condicional.
- Conceda permisos y niveles de acceso para sitios de grupo de SharePoint Online. Los grupos de Azure AD también se pueden usar con etiquetas de confidencialidad o de Azure Information Protection para proteger archivos con cifrado y permisos. 

## <a name="results"></a>Resultados

Cuando complete este paso, tendrá:

- Una lista de cuentas de usuario en Azure AD que se corresponde con los empleados de su organización y los proveedores, contratistas y socios externos que trabajan para su organización o con su organización.
- Un conjunto de grupos y sus pertenencias en Azure AD que reflejan conjuntos lógicos de cuentas de usuario y otros grupos para el aprovisionamiento de licencias automáticas de opciones de configuración de seguridad para Servicios en la nube de Microsoft.

Una vez que se creen los usuarios y los grupos de Azure AD, podrá empezar a asignar licencias y usar cargas de trabajo de productividad como OneDrive para la Empresa o Exchange Online.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Protección de identidades con privilegios](identity-designate-protect-admin-accounts.md) |

