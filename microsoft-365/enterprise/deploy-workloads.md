---
title: Cargas de trabajo de Microsoft 365 para empresas
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Incorpore a los usuarios de su organización en las cargas de trabajo de productividad de Microsoft 365 para empresas
ms.openlocfilehash: 0e1658655c4b97a7e571d1ac09c4b2edcc6c82ce
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268290"
---
# <a name="microsoft-365-for-enterprise-workloads"></a>Cargas de trabajo de Microsoft 365 para empresas

Implemente estas cargas de trabajo en su infraestructura de base para obtener los beneficios de la creatividad y el trabajo en equipo de Microsoft 365 para empresas:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint y OneDrive](sharepoint-online-onedrive-workload.md)

Vea el artículo sobre la [migración](migration-microsoft-365-enterprise-workload.md) para obtener un plan de desarrollo que le permita migrar toda la organización a Microsoft 365 para empresas, que incluye los productos del cliente de Microsoft Office, productos locales de Office Server y dispositivos basados en Microsoft Windows.

Estas son las cargas de trabajo de la guía de implementación general de Microsoft 365 para empresas:

![Las cargas de trabajo de la guía de implementación general de Microsoft 365 para empresas](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a>Requisitos previos de infraestructura básica

*Idealmente*, debe implementar las cargas de trabajo después de completar la configuración de las fases de la [infraestructura básica](deploy-foundation-infrastructure.md). Esto garantiza que todas las capas subyacentes estén correctamente implementadas para proporcionar integración, seguridad y la mejor experiencia a sus usuarios y sus dispositivos.

| Fase | Resultado |
|:-------|:-----|
| Red | Su red se actualiza para obtener un rendimiento óptimo para los servicios en la nube de Microsoft 365. |
| Identidad | La identidad se sincroniza y se protege mediante autenticación segura para cuentas de usuario y protección para cuentas de administrador. |
| Windows 10 Enterprise | Los equipos que ejecuten Windows 7 o Windows 8.1 se pueden actualizar a Windows 10 Enterprise, e instalar los nuevos dispositivos con Windows 10 Enterprise. |
| Aplicaciones de Microsoft 365 para empresas | Los usuarios existentes de Microsoft Office pueden actualizar a Aplicaciones de Microsoft 365 para empresas |
| Administración de dispositivos móviles | Se pueden inscribir y administrar los dispositivos. |
| Protección de la información | Las características de protección de información de Microsoft 365 están configuradas y sus etiquetas de confidencialidad o de Azure Information Protection están listas para proteger documentos y el correo electrónico. |

Recuerde que esta es una situación ideal y la planificación, configuración, prueba y pilotaje puede llevar cierto tiempo, en especial en organizaciones de gran tamaño con infraestructuras ya existentes y ubicaciones múltiples. No es necesario completar todas estas fases en las ubicaciones para permitirle obtener el valor empresarial de Microsoft 365 para empresas con mayor rapidez. 

Estas son algunas cargas de trabajo comunes para implementar inmediatamente: 

- Después de que la fase de **identidad** de la infraestructura básica esté implementada en los usuarios, muchas organizaciones implementan:
  - [Aplicaciones de Microsoft 365 para empresas](office365proplus-infrastructure.md) en combinación con [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Aplicaciones de Microsoft 365 para empresas ofrece la seguridad de la autenticación moderna y la experiencia del usuario del último cliente de Microsoft Office. La migración de archivos personales del usuario a OneDrive reduce la infraestructura y la necesidad de prestar soporte a carpetas y unidades particulares.
  - [Exchange Online](exchangeonline-workload.md) para que los usuarios puedan empezar a usar el correo electrónico en la nube.
- Si no tiene necesidad inmediata de almacenar en la nube activos digitales altamente regulados, implemente [Microsoft Teams](teams-workload.md) y [SharePoint](sharepoint-online-onedrive-workload.md) para los usuarios antes de la fase de **protección de la información**.

Debe decidir la forma más adecuada de ordenar e implementar la configuración de las fases de requisitos previos de la infraestructura básica a fin de satisfacer de la mejor manera sus necesidades empresariales.

### <a name="best-practice"></a>Procedimiento recomendado

Se recomienda implementar fase de **identidad** de la infraestructura básica antes de incorporar los usuarios a las cargas de trabajo o escenarios.

La fase de **identidad** garantiza que su identidad basada en la nube, tanto si se realiza únicamente en la nube o se sincroniza con su Active Directory Domain Services (AD DS) local, contiene las cuentas y grupos de usuario y equipo para gestionar la autenticación y el acceso. La autenticación segura es requerida para todos los usuarios con cuentas de protección segura de administrador antes de ubicar los recursos digitales de la organización en la nube de Microsoft 365.

Aunque es fundamental y muy importante para el rendimiento general, la implementación de la fase **Redes** puede estar en marcha mientras se incorporan usuarios a las cargas de trabajo, teniendo en cuenta que la carga de trabajo y el rendimiento del servicio de Microsoft 365 mejorarán con el tiempo. Esto es especialmente aplicable a organizaciones empresariales con múltiples ubicaciones y una combinación de conexiones locales y a Internet.
