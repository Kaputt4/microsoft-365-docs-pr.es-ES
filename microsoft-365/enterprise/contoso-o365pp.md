---
title: Implementación de Aplicaciones de Microsoft 365 para empresas en Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entienda cómo Contoso usa Microsoft Endpoint Configuration Manager para implementar Aplicaciones de Microsoft 365 para empresas.
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754355"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implementación de Aplicaciones de Microsoft 365 para empresas en Contoso

Contoso actualizó sus equipos a Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas para permitir una colaboración más eficaz, una mejor seguridad y una experiencia de escritorio más moderna. Después de evaluar sus necesidades empresariales y de infraestructura, Contoso identificó estos requisitos clave para la implementación:

- Todos los equipos deben ejecutar Aplicaciones de Microsoft 365 para empresas.
- La implementación debe usar las herramientas de administración e infraestructura existentes siempre que sea posible.
- La implementación debe admitir varios idiomas y arquitecturas existentes en los dispositivos de los usuarios.
- Los equipos deben mantenerse actualizados y seguros con mínimos costos administrativos de IT y un impacto mínimo en los usuarios.

## <a name="deployment-tools"></a>Herramientas de implementación

En función de sus requisitos, Contoso decidió implementar Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas a través de Configuration Manager (rama actual). Configuration Manager se escala para entornos de gran tamaño y proporciona un amplio control sobre la instalación, las actualizaciones y la configuración. También tiene características integradas para que sea más fácil y eficaz implementar y administrar Office, entre las que se incluyen:

- Caché del mismo nivel, que puede ayudar con una capacidad de red limitada al implementar en dispositivos en ubicaciones remotas.
- El panel de administración de clientes de Office, que facilita la implementación de Office y supervisa las actualizaciones, y proporciona a los administradores acceso a las características de implementación y administración más recientes.
- Implementación inteligente de paquetes de idioma, incluida la implementación automática del mismo idioma que el sistema operativo.
- Un método totalmente compatible y fácil de usar para quitar versiones existentes de Office de un cliente durante la implementación.

Además de Configuration Manager, Contoso usó [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)para complementos de Office y VBA , una herramienta gratuita de Microsoft, para evaluar los problemas de compatibilidad con sus macros y complementos de Office.

## <a name="managing-deployment-and-updates"></a>Administración de la implementación y las actualizaciones

Aplicaciones de Microsoft 365 para empresas tiene un nuevo modelo de lanzamiento: Office como servicio. El modelo de servicio facilita mantenerse al día con las nuevas características. Pero a menudo requiere que los departamentos de TI cambien la forma en que implementan y prueban nuevas versiones. Para minimizar los problemas de compatibilidad y garantizar que sus equipos se mantienen actualizados, Contoso implementó Windows y Office en dos fases:

- En primer lugar, implementaron Aplicaciones de Microsoft 365 para empresas en un pequeño conjunto de dispositivos representativos en toda la organización. Este grupo piloto se usó para probar aplicaciones, complementos y hardware con Aplicaciones de Microsoft 365 para empresas.
- Cuatro meses más tarde, después de solucionar todos los problemas críticos relacionados con las aplicaciones, los complementos y el hardware en el grupo piloto, Contoso implementó Aplicaciones de Microsoft 365 para empresas en el resto de los dispositivos de la organización (el grupo general).

En lugar de administrar las actualizaciones de Office mediante Configuration Manager, Contoso habilitó las actualizaciones automáticas desde la nube. Las actualizaciones basadas en la nube reducen la sobrecarga administrativa y garantizan que los dispositivos se mantienen actualizados.

Contoso siguió el mismo enfoque de dos fases para las actualizaciones de características que usaban para implementar Office: los dispositivos del grupo piloto recibieron actualizaciones de características cuatro meses antes que los dispositivos del resto de la organización (el grupo general). Para habilitar esta opción para Office, Contoso usó dos [canales de actualización](https://docs.microsoft.com/DeployOffice/overview-update-channels) recomendados:

- Canal semestral empresarial (versión preliminar) para actualizaciones al grupo piloto
- Semi-Annual Canal empresarial para actualizaciones para el grupo general

Como el canal semestral empresarial (versión preliminar) publica una versión de Aplicaciones de Microsoft 365 para empresas cuatro meses antes que el canal empresarial semestral, Contoso tiene tiempo para validar las actualizaciones sin tener que administrarlas.

## <a name="deployment-process"></a>Proceso de implementación

Para completar la implementación de Office, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:

1. Antes de la implementación, Contoso usó Readiness Toolkit para el complemento de Office y VBA para probar sus aplicaciones y complementos de Office para evaluar su compatibilidad con Aplicaciones de Microsoft 365 para empresas.
1. En Configuration Manager, habilitaban la memoria caché del mismo nivel en sus dispositivos cliente, lo que ayuda con una capacidad de red limitada al implementar en dispositivos cliente en ubicaciones remotas. 
1. Contoso definió dos grupos de implementación como colecciones de dispositivos en Configuration Manager: un grupo piloto y un grupo amplio. El grupo piloto, que incluía un pequeño conjunto de dispositivos representativos en toda la organización, se usó para realizar pruebas adicionales de aplicaciones, complementos y hardware con Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas.
1. Crearon paquetes de implementación para Office mediante el panel de administración de clientes de Office y el Asistente para instaladores de Office 365, que forman parte de la consola de Configuration Manager. Han creado dos paquetes de Aplicaciones de Microsoft 365 para empresas, uno para el grupo piloto en el Canal empresarial de Semi-Annual (versión preliminar) y otro para el grupo general en el Canal empresarial de Semi-Annual.
2. Cada paquete de Office incluía paquetes de inglés, francés y alemán. Si un dispositivo requería un idioma que no estaba incluido en el paquete de Office, ese paquete de idioma se descargó automáticamente de la red de entrega de contenido (CDN) de Office.
3. Para eliminar de forma automática todas las versiones MSI existentes de Office antes de instalar Aplicaciones de Microsoft 365 para empresas, usaron las características integradas en el paquete de Office.
4. En Configuration Manager, implementaron los paquetes de Windows y Office en puntos de distribución a través de su red. A continuación, ejecutaron las secuencias de tareas de implementación de Configuration Manager para implementar el paquete piloto aplicaciones de Microsoft 365 para empresas en el grupo piloto.
5. Después de solucionar problemas de compatibilidad con el grupo piloto, Contoso ejecutó las secuencias de tareas para implementar el paquete aplicaciones de Microsoft 365 para empresas en el grupo general.

Dado que Contoso decidió actualizar automáticamente los dispositivos desde la nube, no era necesario administrar el proceso en Configuration Manager. Sus dispositivos se actualizan automáticamente directamente desde la nube en función del canal de actualización que se definió en la implementación inicial.

Esta es la arquitectura de implementación de aplicaciones de Microsoft 365 para empresas de Contoso y actualizaciones continuas.

![La infraestructura de implementación de Contoso para Aplicaciones de Microsoft 365 para empresas](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso usa [Microsoft Intune](contoso-mdm.md) en Microsoft 365 para empresas para administrar sus dispositivos y las aplicaciones que ejecutan en toda la organización.

## <a name="see-also"></a>Vea también

[Aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
