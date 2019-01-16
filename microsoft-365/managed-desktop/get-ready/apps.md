---
title: Preparación de aplicaciones para Microsoft administrado de escritorio
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871362"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparación de aplicaciones para Microsoft administrado de escritorio

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Los clientes de Microsoft y administrado de escritorio de Microsoft igualmente tienen críticas, aún diferentes responsabilidades alrededor de las aplicaciones que se utiliza con Microsoft Managed Desktop.

## <a name="microsoft-responsibilities"></a>Responsabilidades de Microsoft
**Aplicaciones de Office 365** Microsoft proporcionará servicio completo para la implementación, la actualización y la compatibilidad de aplicaciones específicas de Office 365. Todos los usuarios recibirán el conjunto base de Office 365, haga clic para ejecutar la versión de 64 bits de aplicaciones incluidas en la imagen del dispositivo para que un usuario rápidamente puede llegar a ser productivo. Las aplicaciones de Project y Visio en del conjunto de programas de Office 365 se concede bajo licencia por separado.  Microsoft Managed Desktop proporcionará grupos de implementación permite al administrador de TI administrar las licencias e implementar estas aplicaciones de forma adecuada para su organización. Microsoft admitirá los usuarios finales de estas aplicaciones a través de los canales de soporte técnico de Microsoft administrado.

**Aplicaciones de línea de negocio** Microsoft proporciona herramientas para los administradores de TI a administrar e implementar sus aplicaciones de línea de negocio (LOB) a los usuarios finales como parte del producto Intune. Microsoft será compatible con problemas de implementación de aplicaciones como se detalla en [aplicaciones de línea de negocio](#line-of-business-applications) 

**Implementar con Intune** Intune se vinculará a la **Tienda de Microsoft para la empresa** durante la incorporación de escritorio administrado de Microsoft que permite a las aplicaciones adquiridas a implementarse a través de Intune. Microsoft también implementar la versión basada en web del Portal de la empresa a los usuarios finales para que los administradores de TI puede proporcionar una experiencia de autoayuda para los usuarios finales.

**Administración de aplicaciones** Microsoft puede identificar restringido las aplicaciones que no son adecuadas para el área de trabajo moderno debido a su impacto en el sistema. Cuando se identifica una aplicación de este tipo informar al cliente de Microsoft y esa aplicación deberá quitarse del inquilino. 

Para obtener más información sobre los comportamientos de la aplicación restringidos y los requisitos de la aplicación, vea [requisitos de la aplicación de escritorio administrado de Microsoft](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Responsabilidades del cliente
El conjunto de aplicaciones de Office 365 es esencial en las ofertas de productividad de Microsoft y se incluye en la licencia de 365 de Microsoft para todos los usuarios de escritorio administrado de Microsoft. Mientras Microsoft implementa, actualiza y es compatible con las aplicaciones de Office en los dispositivos de escritorio administrado de Microsoft hay algunas áreas para la que es responsabilidad del cliente.
- **Asignar licencias** - los clientes son responsables de la asignación de las licencias adecuadas a los usuarios finales de Office 365. 
- **Agregar usuarios a grupos de seguridad** - para los clientes con los usuarios que necesiten Project o Visio, los administradores de TI deben agregar los usuarios a los grupos de implementación apropiada. Los administradores de TI también son responsables de administrar el final del ciclo de vida para esos usuarios. 
- **Implementar Office 365 complementos** - los clientes son responsables de la implementación de los complementos en el conjunto de aplicaciones de Office 365 que se considera necesario. 

Puesto que las aplicaciones de línea de negocio (LOB) son exclusivos para cada cliente, los clientes son responsables de la administración de todas las aplicaciones dentro de su organización no ha implementado por Microsoft. Esto incluye:
- Decidir qué aplicaciones se necesitan y quién necesita ellos
- Asignación de aplicaciones a los usuarios
- Crear y mantener grupos de Azure Active Directory (AD) para la administración de asignaciones de aplicación 

El cliente debe cargar aplicaciones LOB en Intune. A continuación, que son responsables de la implementación, actualizar y retirar dichas aplicaciones a través de sus ciclos de vida respectivos, así como la administración de soporte para estas aplicaciones para sus usuarios.

## <a name="office-applications"></a>Aplicaciones de Office
Como parte de la licencia de Microsoft 365 E5, Office 365 Standard Suite (64 bits) se implementa por Microsoft. 

Para obtener información detallada, vea [tecnologías de escritorio administrado de Microsoft](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Aplicaciones de línea de negocio
Esta tabla resumen las responsabilidades a través de las distintas fases para aplicaciones de línea de negocio (LOB). 

Elementos de trabajo de la aplicación |    Cliente    | Microsoft
--- | --- | ---
**Aplicaciones de incorporación** |  |
Identificar las aplicaciones que sea necesarias para los grupos de usuarios de destino   | ![sí](images/checkmark.png)  |
Crear y administrar grupos de Azure AD para la implementación de aplicaciones | ![sí](images/checkmark.png) |   
**Empaquetado de la aplicación** |  |
Paquete de aplicaciones para satisfacer los estándares de implementación Intune |  ![sí](images/checkmark.png) |  
Cargar aplicaciones en Intune | ![sí](images/checkmark.png)     |
Aplicaciones de prueba en el entorno de escritorio administrado de Microsoft |    ![sí](images/checkmark.png) |  
Aplicaciones de prueba con los usuarios finales    | ![sí](images/checkmark.png) |    
**Implementación** | |
Administrar y asignar a usuarios a las aplicaciones  | ![sí](images/checkmark.png)  |
Herramientas de implementación de Intune ofrece la aplicación a los clientes remotos| |   ![sí](images/checkmark.png)
Identificar e implementar actualizaciones de la aplicación a través de Intune | ![sí](images/checkmark.png)    |
Desinstalar y quitar aplicaciones cuando se han retirado    | ![sí](images/checkmark.png) |    
**Administración** | |
Adquirir y asignar licencias |   ![sí](images/checkmark.png)     |
Proporcionar soporte técnico para el usuario final para las aplicaciones de línea de negocio  | ![sí](images/checkmark.png) |
Administrar la configuración de la aplicación remota    | ![sí](images/checkmark.png) |

Para obtener información sobre los requisitos de la aplicación de LOB, vea [requisitos de la aplicación de escritorio administrado de Microsoft](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Implementación de la aplicación Intune
Administración de aplicaciones se puede controlar a través del portal de administración de escritorio administrado de Microsoft o a través del portal Intune. Portal de administración de aplicación de Intune muestra las aplicaciones que se implementan para iOS, Android y Windows. Portal de administración de escritorio administrado de Microsoft limita la vista para las aplicaciones de Windows 10. Ambos están disponibles a través del Portal de Azure. 
* [Conceptos básicos de administración de aplicación Intune](https://docs.microsoft.com/intune/app-management)
* [Agregar aplicaciones al Intune](https://docs.microsoft.com/intune/app-management)
   * [Agregar una aplicación de línea de negocio](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Agregar aplicaciones de Win32 a Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Adición de aplicaciones web](https://docs.microsoft.com/intune/web-app)
* [Implementación de aplicaciones](https://docs.microsoft.com/intune/apps-deploy)
   * [Implementar aplicaciones para Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Portal de la compañía
   * [Implemente el Portal de la compañía](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configuración de la aplicación del Portal de la compañía](https://docs.microsoft.com/intune/company-portal-app)
