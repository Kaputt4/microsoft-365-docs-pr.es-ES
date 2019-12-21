---
title: Microsoft 365 para empresas, cargas de trabajo y escenarios
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Incorpore a los usuarios de su organización en las cargas de trabajo de productividad de Microsoft 365 para empresas
ms.openlocfilehash: ff0e4b06972ed53933eb7780759bfcd53e286353
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801905"
---
# <a name="microsoft-365-for-enterprise-workloads-and-scenarios"></a>Microsoft 365 para empresas, cargas de trabajo y escenarios

Implemente estas cargas de trabajo en su infraestructura de base para obtener los beneficios de la creatividad y el trabajo en equipo de Microsoft 365 para empresas:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint y OneDrive](sharepoint-online-onedrive-workload.md)

Vea el artículo sobre la [migración](migration-microsoft-365-enterprise-workload.md) para obtener un plan de desarrollo que le permita migrar toda la organización a Microsoft 365 para empresas, que incluye los productos del cliente de Microsoft Office, productos locales de Office Server y dispositivos basados en Microsoft Windows.

Los escenarios usan características y servicios de una forma integrada para responder a las necesidades empresariales de Microsoft 365 para empresas. 

Una de estas necesidades es asegurarse de que los empleados puedan trabajar de forma productiva y segura cuando no estén conectados directamente a la intranet. Vea el escenario [Capacitar a los trabajadores remotos](empower-people-to-work-remotely.md) para obtener una plan de desarrollo que le permita implementar los elementos de infraestructura e impulsar la adopción de usuarios remotos para cargas de trabajo de gran importancia, como por ejemplo, Teams y Exchange Online.

Otra necesidad de este tipo de información es la protección de los datos altamente regulados almacenados en Microsoft 365. Entre los datos altamente regulados, se incluyen estos recursos digitales:

- Datos sujetos a regulaciones regionales.
- Los datos más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización.

Para proteger estos datos de las amenazas internas y externas, vea:

- [Teams para datos altamente regulados](secure-teams-highly-regulated-data-scenario.md)
- [Sitios de SharePoint para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md) 

Estos escenarios le guiarán en la configuración de un sitio de SharePoint o un equipo de Microsoft Teams para almacenar de forma segura sus datos más importantes.

En la ilustración siguiente se muestran las cargas de trabajo y los escenarios de la guía de implementación general de Microsoft 365 para empresas:

![Las cargas de trabajo y los escenarios en la guía de implementación general de Microsoft 365 para empresas.](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

Vea la[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)para escenarios adicionales. 

## <a name="foundation-infrastructure-prerequisites"></a>Requisitos previos de infraestructura básica

*Idealmente*, debe implementar las cargas de trabajo después de completar la configuración de las fases de la [infraestructura básica](deploy-foundation-infrastructure.md). Esto garantiza que todas las capas subyacentes estén correctamente implementadas para proporcionar integración, seguridad y la mejor experiencia a sus usuarios y sus dispositivos.

| Fase | Resultado |
|:-------|:-----|
| Red | Su red se actualiza para obtener un rendimiento óptimo para los servicios en la nube de Microsoft 365. |
| Identidad | La identidad se sincroniza y se protege mediante autenticación segura para cuentas de usuario y protección para cuentas de administrador. |
| Windows 10 Enterprise | Los equipos que ejecuten Windows 7 o Windows 8.1 se pueden actualizar a Windows 10 Enterprise, e instalar los nuevos dispositivos con Windows 10 Enterprise. |
| Office 365 ProPlus | Los usuarios existentes de Microsoft Office pueden actualizar a Office 365 ProPlus. |
| Administración de dispositivos móviles | Se pueden inscribir y administrar los dispositivos. |
| Protección de la información | Las características de protección de información de Microsoft 365 están configuradas y sus etiquetas de confidencialidad o de Azure Information Protection están listas para proteger documentos y el correo electrónico. |

Recuerde que esta es una situación ideal y la planificación, configuración, prueba y pilotaje puede llevar cierto tiempo, en especial en organizaciones de gran tamaño con infraestructuras ya existentes y ubicaciones múltiples. No es necesario completar todas estas fases en las ubicaciones para permitirle obtener el valor empresarial de Microsoft 365 para empresas con mayor rapidez. 

Estas son algunas cargas de trabajo comunes para implementar inmediatamente: 

- Después de que la fase de **identidad** de la infraestructura básica esté implementada en los usuarios, muchas organizaciones implementan:
  - [Office 365 ProPlus](office365proplus-infrastructure.md) combinado con [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Office 365 ProPlus ofrece la seguridad de la autenticación moderna y la última experiencia del usuario del cliente de Microsoft Office. La migración de archivos personales del usuario a OneDrive reduce la infraestructura y la necesidad de prestar soporte a carpetas y unidades particulares.
  - [Exchange Online](exchangeonline-workload.md) para que los usuarios puedan empezar a usar el correo electrónico en la nube.
- Si no tiene necesidad inmediata de almacenar en la nube activos digitales altamente regulados, implemente [Microsoft Teams](teams-workload.md) y [SharePoint](sharepoint-online-onedrive-workload.md) para los usuarios antes de la fase de **protección de la información**.

Debe decidir la forma más adecuada de ordenar e implementar la configuración de las fases de requisitos previos de la infraestructura básica a fin de satisfacer de la mejor manera sus necesidades empresariales.

### <a name="best-practice"></a>Procedimiento recomendado

Se recomienda implementar fase de **identidad** de la infraestructura básica antes de incorporar los usuarios a las cargas de trabajo o escenarios.

La fase de **identidad** garantiza que su identidad basada en la nube, tanto si se realiza únicamente en la nube o se sincroniza con su Active Directory Domain Services (AD DS) local, contiene las cuentas y grupos de usuario y equipo para gestionar la autenticación y el acceso. La autenticación segura es requerida para todos los usuarios con cuentas de protección segura de administrador antes de ubicar los recursos digitales de la organización en la nube de Microsoft 365.

Aunque es fundamental y muy importante para el rendimiento general, la implementación de la fase **Redes** puede estar en marcha mientras se incorporan usuarios a las cargas de trabajo, teniendo en cuenta que la carga de trabajo y el rendimiento del servicio de Microsoft 365 mejorarán con el tiempo. Esto es especialmente aplicable a organizaciones empresariales con múltiples ubicaciones y una combinación de conexiones locales y a Internet.
