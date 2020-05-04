---
title: Implementación de Aplicaciones de Microsoft 365 para empresas en Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entienda cómo Contoso usa Microsoft Endpoint Configuration Manager para implementar Aplicaciones de Microsoft 365 para empresas.
ms.openlocfilehash: 2ff05a079d83389ed94445fc011b9f7902c6de56
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011892"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implementación de Aplicaciones de Microsoft 365 para empresas en Contoso

Contoso actualizó sus equipos a Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas para mejorar la colaboración y la seguridad, y para disfrutar de un escritorio más moderno. Después de evaluar su infraestructura y las necesidades empresariales, Contoso identificó estos requisitos principales para la implementación:

- Todos los equipos deben ejecutar Aplicaciones de Microsoft 365 para empresas
- La implementación debe usar la infraestructura y las herramientas de administración existentes cuando sea posible.
- La implementación debe admitir varios idiomas y arquitecturas existentes en los dispositivos del usuario final.
- Los equipos se deben mantener actualizados y protegidos con los mínimos costos administrativos de TI y el menor impacto en los usuarios finales.

## <a name="deployment-tools"></a>Herramientas de implementación

Basándose en sus requisitos, Contoso optó por implementar Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas con Configuration Manager (rama actual). Configuration Manager se escala en entornos de gran tamaño y proporciona un amplio control sobre la instalación, las actualizaciones y la configuración. También incluye características integradas para que sea más fácil y eficaz implementar y administrar Office, entre las que se incluyen:

- La caché del mismo nivel, que puede ayudar con la capacidad de red limitada cuando se implementa en dispositivos en ubicaciones remotas.
- El panel de administración de clientes de Office, que facilita la implementación de Office y supervisa las actualizaciones. Asimismo, proporciona acceso a los administradores a las características de administración e implementación más recientes.
- Implementación inteligente de paquetes de idioma, incluida la implementación automática del mismo idioma del sistema operativo.
- Método fácil de usar y totalmente compatible para quitar las versiones existentes de Office de un cliente durante la implementación.

Además de Configuration Manager, Contoso usa [Readiness Toolkit](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), una herramienta gratuita de Microsoft para evaluar los problemas de compatibilidad con los complementos y macros de Office.

## <a name="managing-the-deployment-and-updates"></a>Administración de la implementación y las actualizaciones

Aplicaciones de Microsoft 365 para empresas tiene un nuevo modelo de versiones: Office como servicio. El modelo de servicio facilita mantenerse al día de las características nuevas, pero a menudo requiere un enfoque diferente por parte de los departamentos de TI en la forma de implementar y probar las versiones nuevas. Para minimizar los problemas de compatibilidad y asegurarse de que los equipos permanecían actualizados, Contoso implementó Windows y Office en dos fases: 

- En la primera fase, implementaron Aplicaciones de Microsoft 365 para empresas en un pequeño conjunto de dispositivos representativos de la organización. Este grupo piloto se usó para probar aplicaciones, complementos y hardware con Aplicaciones de Microsoft 365 para empresas.
- Cuatro meses más tarde, después de solucionar todos los problemas críticos relacionados con las aplicaciones, los complementos y el hardware en el grupo piloto, Contoso implementó Aplicaciones de Microsoft 365 para empresas en el resto de los dispositivos de la organización (el grupo general). 

En lugar de administrar las actualizaciones de Office con Configuration Manager, Contoso habilitó actualizaciones automáticas desde la nube. Las actualizaciones basadas en la nube redujeron la sobrecarga administrativa además de garantizar que los dispositivos permanecían actualizados. 

Contoso siguió el mismo enfoque de dos fases de implementación de Office para las actualizaciones de características: los dispositivos del grupo piloto recibieron las actualizaciones de características cuatro meses antes que el resto de los dispositivos de la organización (el grupo general). Para habilitar esta opción en Office, Contoso usó dos [canales de actualización](https://docs.microsoft.com/DeployOffice/overview-update-channels)recomendados: 

- Canal semianual (dirigido) para las actualizaciones del grupo piloto 
- Canal semianual para las actualizaciones del grupo general 

Como el canal semianual (dirigido) publica una versión de Aplicaciones de Microsoft 365 para empresas cuatro meses antes que el canal semianual, Contoso tiene tiempo para validar las actualizaciones sin tener que administrarlas. 

## <a name="deployment-process"></a>Proceso de implementación

Para completar la implementación de Office, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:

1. Antes de la implementación, usaron Readiness Toolkit para probar sus aplicaciones y los complementos de Office con el fin de evaluar la compatibilidad con Aplicaciones de Microsoft 365 para empresas.
2. En Configuration Manager, Contoso habilitó la caché del mismo nivel en los dispositivos cliente, lo que contribuyó a compensar la capacidad de red limitada al implementar en los dispositivos cliente en ubicaciones remotas. 
3. Definieron dos grupos de implementación como colecciones de dispositivo en Configuration Manager: un grupo piloto y un grupo general. El grupo piloto, que incluía un pequeño conjunto de dispositivos representativos en toda la organización, se usó para realizar pruebas adicionales de aplicaciones, complementos y hardware con Windows 10 Enterprise y Aplicaciones de Microsoft 365 para empresas. 
4. Crearon paquetes de implementación de Office con el panel de administración de clientes de Office y el Asistente de instalación de Office 365, que forman parte de la consola de Configuration Manager. Crearon dos paquetes de Aplicaciones de Microsoft 365 para empresas, uno para el grupo piloto en el canal semianual (dirigido) y otro para el grupo general en el canal semianual. 
5. En cada paquete de Office, incluyeron los paquetes de los idiomas inglés, francés y alemán. Si un dispositivo requería un idioma que no estaba incluido en el paquete de Office, se descargaba de forma automática de la Red de entrega de contenido (CDN) de Office.
6. Para eliminar de forma automática todas las versiones MSI existentes de Office antes de instalar Aplicaciones de Microsoft 365 para empresas, usaron las características integradas en el paquete de Office.
7. En Configuration Manager, implementaron los paquetes de Windows y Office en puntos de distribución en la red y, después, ejecutaron las secuencias de tareas de implementación de Configuration Manager para implementar el paquete piloto de Aplicaciones de Microsoft 365 para empresas en el grupo piloto.
8. Después de corregir los problemas de compatibilidad con el grupo piloto, Contoso ejecutó las secuencias de tareas para implementar el paquete general de Aplicaciones de Microsoft 365 para empresas en el grupo general.

Como Contoso decidió actualizar de forma automática los dispositivos desde la nube, no fue necesario administrar el proceso en el Administrador de configuración. Los dispositivos se actualizaron de forma automática directamente desde la nube según el canal de actualización definido como parte de la implementación inicial. 

Aquí se muestra la arquitectura de implementación de la instalación y las actualizaciones continuas de Aplicaciones de Microsoft 365 para empresas de Contoso.

![Infraestructura de implementación de Aplicaciones de Microsoft 365 para empresas en Contoso](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Paso siguiente

[Aprenda](contoso-mdm.md)cómo Contoso está usando Microsoft Intune en Microsoft 365 Enterprise para administrar los dispositivos y las aplicaciones que se ejecutan en ellos en toda la organización.

## <a name="see-also"></a>Vea también

[Aplicaciones de Microsoft 365 para empresas para Microsoft 365 Enterprise](office365proplus-infrastructure.md)

[Guía de implementación](deploy-microsoft-365-enterprise.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)
