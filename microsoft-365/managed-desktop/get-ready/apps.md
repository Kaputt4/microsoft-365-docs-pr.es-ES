---
title: Preparación de aplicaciones para el escritorio administrado por Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289075"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparación de aplicaciones para el escritorio administrado por Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Los clientes de escritorio administrados de Microsoft y Microsoft tienen la misma importancia, pero distintas responsabilidades en torno a las aplicaciones usadas con Microsoft manAged Desktop.

## <a name="microsoft-responsibilities"></a>Responsabilidades de Microsoft
**Aplicaciones de Office 365** Microsoft proporcionará servicio completo para la implementación, actualización y soporte técnico de aplicaciones de Office 365 específicas. Todos los usuarios recibirán el conjunto base de Office 365 haga clic para ejecutar, la versión de 64 bits de las aplicaciones incluidas en la imagen del dispositivo, de modo que el usuario pueda llegar a ser productivo rápidamente. Las aplicaciones de Project y Visio del conjunto de aplicaciones de Office 365 tienen una licencia por separado.  El escritorio administrado de Microsoft proporcionará grupos de implementación que permiten al administrador de ti administrar las licencias e implementarlas de forma adecuada para su organización. Microsoft proporcionará soporte a los usuarios finales de estas aplicaciones a través de los canales de soporte técnico de Microsoft administrados para equipos de escritorio.

**Aplicaciones de línea de negocio** Microsoft proporciona herramientas para que los administradores de ti administren e implementen sus aplicaciones de línea de negocio (LOB) para los usuarios finales como parte del producto Intune. Microsoft admitirá problemas de implementación de aplicaciones como se detalla en [aplicaciones de línea de negocio](#line-of-business-applications) . 

**Implementar con Intune** Intune se vinculará a **Microsoft Store para empresas** durante la incorporación de escritorio administrada de Microsoft, lo que permite que las aplicaciones se implementen a través de Intune. Microsoft también implementará la aplicación de portal de empresa de Microsoft Store en los usuarios finales para que los administradores de ti puedan proporcionar una experiencia de autoservicio para los usuarios finales.

**Administración de aplicaciones** Microsoft puede identificar Aplicaciones restringidas no adecuadas para el lugar de trabajo moderno debido a su impacto en el sistema. Cuando se identifica una aplicación de este tipo, Microsoft notificará al cliente y la aplicación tendrá que quitarse del espacio empresarial. 

Para obtener más información sobre los requisitos de aplicación y los comportamientos de la aplicación restringida, consulte [requisitos de Microsoft Managed Desktop App](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Responsabilidades del cliente
El conjunto de aplicaciones de Office 365 es fundamental para las ofertas de productividad de Microsoft y se incluye en la licencia 365 de Microsoft para todos los usuarios de escritorio administrados por Microsoft. Mientras Microsoft implementa, actualiza y admite aplicaciones de Office para dispositivos de escritorio administrados por Microsoft, todavía hay algunas áreas de las que el cliente es responsable.
- **Asignar licencias** : los clientes son responsables de asignar las licencias adecuadas a los usuarios finales para Office 365. 
- **Agregar usuarios a grupos de seguridad** : para los clientes con usuarios que necesitan Project o Visio, el administrador de TI debe agregar dichos usuarios a los grupos de implementación adecuados. Los administradores de ti también son responsables de administrar el fin del ciclo de vida de los usuarios. 
- **Implemente Office 365 Add ONSS** : los clientes son responsables de implementar todos los complementos en el conjunto de aplicaciones de Office 365 que se consideran necesarios. 

Como las aplicaciones de línea de negocio (LOB) son únicas para cada cliente, los clientes son responsables de administrar todas las aplicaciones de la organización no implementadas por Microsoft. Esto incluye:
- Decidir qué aplicaciones son necesarias y cuáles las necesitan
- Asignación de aplicaciones a esos usuarios
- Crear y mantener grupos de Azure Active Directory (AD) para administrar asignaciones de aplicaciones 

El cliente debe cargar las aplicaciones de LOB en Intune. A continuación, son responsables de implementar, actualizar y retirar esas aplicaciones sobre sus respectivos ciclos de vida, así como de administrar la compatibilidad con estas aplicaciones para sus usuarios.

## <a name="office-applications"></a>Aplicaciones de Office
Como parte de la licencia 365 E5 de Microsoft, Office 365 Standard Suite (bit 64) implementado por Microsoft. 

Para obtener más información, consulte [tecnologías de escritorio administraDas de Microsoft](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Aplicaciones de línea de negocio
En esta tabla se resumen las responsabilidades de las distintas fases para las aplicaciones de línea de negocio (LOB). 

Elementos de trabajo de la aplicación |    Clientes    | Microsoft
--- | --- | ---
**Aplicaciones de incorporación** |  |
Identificación de las aplicaciones necesarias para los grupos de usuarios de destino   | ![sí](images/checkmark.png)  |
Crear y administrar grupos de Azure AD para la implementación de aplicaciones | ![sí](images/checkmark.png) |   
**Empaquetado de aplicaciones** |  |
Empaquetar aplicaciones para cumplir los estándares de implementación de Intune |  ![sí](images/checkmark.png) |  
Cargar aplicaciones a Intune | ![sí](images/checkmark.png)     |
Probar aplicaciones en un entorno de escritorio administrado de Microsoft |    ![sí](images/checkmark.png) |  
Probar aplicaciones con usuarios finales    | ![sí](images/checkmark.png) |    
**Implementación** | |
Administrar y asignar usuarios a las aplicaciones  | ![sí](images/checkmark.png)  |
Las herramientas de implementación de Intune proporcionan aplicaciones a clientes remotos| |   ![sí](images/checkmark.png)
Identificación e implementación de actualizaciones de la aplicación mediante Intune | ![sí](images/checkmark.png)    |
Desinstalar y quitar aplicaciones cuando se han retirado    | ![sí](images/checkmark.png) |    
**Administración** | |
Adquirir y asignar licencias |   ![sí](images/checkmark.png)     |
Proporcionar compatibilidad con el usuario final para las aplicaciones de línea de negocio  | ![sí](images/checkmark.png) |
Administrar la configuración de la aplicación de forma remota    | ![sí](images/checkmark.png) |

Para obtener información sobre los requisitos de las aplicaciones LOB, consulte [requisitos de aplicaciones de escritorio administrado por Microsoft](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Implementación de aplicaciones de Intune
La administración de aplicaciones puede controlarse a través del portal de administración de escritorio administrado de Microsoft o a través del portal de Intune. El portal de administración de aplicaciones de Intune muestra las aplicaciones implementadas para Windows, Android e iOS. El portal de administración de escritorio administrado de Microsoft limita la vista a las aplicaciones de Windows 10. Ambos están disponibles a través de Azure portal. 
* [Conceptos básicos de la administración de aplicaciones de Intune](https://docs.microsoft.com/intune/app-management)
* [Agregar aplicaciones a Intune](https://docs.microsoft.com/intune/app-management)
   * [Agregar una aplicación de línea de negocio](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Agregar aplicaciones Win32 a Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Adición de aplicaciones Web](https://docs.microsoft.com/intune/web-app)
* [Implementación de aplicaciones](https://docs.microsoft.com/intune/apps-deploy)
   * [Implementar aplicaciones en Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Portal de empresa
   * [Implementar el portal de empresa](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configuración de la aplicación portal de empresa](https://docs.microsoft.com/intune/company-portal-app)
