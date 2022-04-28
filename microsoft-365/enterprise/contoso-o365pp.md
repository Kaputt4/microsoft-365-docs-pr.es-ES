---
title: Implementación de Aplicaciones de Microsoft 365 para empresas en Contoso
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entienda cómo Contoso usa Microsoft Endpoint Configuration Manager para implementar Aplicaciones de Microsoft 365 para empresas.
ms.openlocfilehash: 8b6fb639083145c728870156d848b75897483d25
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096554"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Implementación de Aplicaciones de Microsoft 365 para empresas en Contoso

Contoso actualizó sus equipos a Windows 10 Enterprise y Aplicaciones Microsoft 365 para empresas para permitir una colaboración más eficaz, una mejor seguridad y una experiencia de escritorio más moderna. Después de evaluar sus necesidades empresariales y de infraestructura, Contoso identificó estos requisitos clave para la implementación:

- Todos los equipos deben ejecutar Aplicaciones Microsoft 365 para empresas.
- La implementación debe usar herramientas de administración e infraestructura existentes siempre que sea posible.
- La implementación debe admitir varios idiomas y arquitecturas existentes en los dispositivos de los usuarios.
- Los equipos deben mantenerse actualizados y seguros con costos administrativos de TI mínimos y un impacto mínimo para los usuarios.

## <a name="deployment-tools"></a>Herramientas de implementación

En función de sus requisitos, Contoso eligió implementar Windows 10 Enterprise y Aplicaciones Microsoft 365 para empresas a través de Configuration Manager (rama actual). Configuration Manager funciona para entornos grandes y proporciona un amplio control sobre la instalación, las actualizaciones y la configuración. También cuenta con características integradas para que sea más fácil y más eficaz implementar y administrar Office, entre las que se incluyen:

- Caché del mismo nivel, que puede ayudar con una capacidad de red limitada al implementar en dispositivos en ubicaciones remotas.
- El panel Office Administración de clientes, que facilita la implementación Office y la supervisión de actualizaciones, y proporciona a los administradores acceso a las características de implementación y administración más recientes.
- Implementación inteligente del paquete de idioma, incluida la implementación automática del mismo idioma que el sistema operativo.
- Un método totalmente compatible y fácil de usar para quitar las versiones existentes de Office de un cliente durante la implementación.

Además de Configuration Manager, Contoso usó la [Toolkit de preparación para complementos de Office y VBA](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), una herramienta gratuita de Microsoft, para evaluar los problemas de compatibilidad con sus macros y complementos de Office.

## <a name="managing-deployment-and-updates"></a>Administración de la implementación y las actualizaciones

Aplicaciones Microsoft 365 para empresas tiene un nuevo modelo de versión: Office como servicio. El modelo de servicio facilita la puesta al día de las nuevas características. Pero a menudo requiere que los departamentos de TI cambien la forma en que implementan y prueban nuevas versiones. Para minimizar los problemas de compatibilidad y asegurarse de que sus equipos permanezcan actualizados, Contoso implementó Windows y Office en dos fases:

- En primer lugar, implementaron Aplicaciones Microsoft 365 para empresas en un pequeño conjunto de dispositivos representativos de toda la organización. Este grupo piloto se usó para probar aplicaciones, complementos y hardware con Aplicaciones Microsoft 365 para empresas.
- Cuatro meses más tarde, después de solucionar todos los problemas críticos relacionados con las aplicaciones, los complementos y el hardware en el grupo piloto, Contoso implementó Aplicaciones de Microsoft 365 para empresas en el resto de los dispositivos de la organización (el grupo general).

En lugar de administrar las actualizaciones de Office mediante Configuration Manager, Contoso ha habilitado las actualizaciones automáticas desde la nube. Las actualizaciones basadas en la nube reducen la sobrecarga administrativa y garantizan que los dispositivos permanezcan actualizados.

Contoso siguió el mismo enfoque de dos fases para las actualizaciones de características que usaron para implementar Office: los dispositivos del grupo piloto recibieron actualizaciones de características cuatro meses antes que los dispositivos del resto de la organización (el grupo amplio). Para habilitar esta opción para Office, Contoso usó dos [canales de actualización](/DeployOffice/overview-update-channels) recomendados:

- Canal semestral empresarial (versión preliminar) para actualizaciones al grupo piloto
- canal de Semi-Annual Enterprise para las actualizaciones del grupo amplio

Como el canal semestral empresarial (versión preliminar) publica una versión de Aplicaciones de Microsoft 365 para empresas cuatro meses antes que el canal empresarial semestral, Contoso tiene tiempo para validar las actualizaciones sin tener que administrarlas.

## <a name="deployment-process"></a>Proceso de implementación

Para completar la implementación de Office, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:

1. Antes de la implementación, Contoso usó la Toolkit de preparación para Office Complemento y VBA para probar sus aplicaciones y complementos de Office a fin de evaluar su compatibilidad con Aplicaciones Microsoft 365 para empresas.
1. En Configuration Manager, habilitaron la caché del mismo nivel en sus dispositivos cliente, lo que ayuda con una capacidad de red limitada al implementar en dispositivos cliente en ubicaciones remotas. 
1. Contoso definió dos grupos de implementación como recopilaciones de dispositivos en Configuration Manager: un grupo piloto y un grupo amplio. El grupo piloto, que incluía un pequeño conjunto de dispositivos representativos en toda la organización, se usó para realizar pruebas adicionales de aplicaciones, complementos y hardware con Windows 10 Enterprise y Aplicaciones Microsoft 365 para empresas.
1. Crearon paquetes de implementación para Office mediante el panel de administración de cliente de Office y el asistente del instalador de Office 365, que forman parte de la consola de Configuration Manager. Crearon dos paquetes de Aplicaciones Microsoft 365 para empresas, uno para el grupo piloto en el canal de Semi-Annual Enterprise (versión preliminar) y otro para el grupo amplio en el canal de Semi-Annual Enterprise.
2. Cada paquete Office incluye paquetes en inglés, francés y alemán. Si un dispositivo requiere un idioma que no se incluyó en el paquete de Office, ese paquete de idioma se descargó automáticamente de la Office Content Delivery Network (CDN).
3. Para eliminar de forma automática todas las versiones MSI existentes de Office antes de instalar Aplicaciones de Microsoft 365 para empresas, usaron las características integradas en el paquete de Office.
4. En Configuration Manager, implementaron los paquetes de Windows y Office en puntos de distribución a través de su red. A continuación, ejecutaron las secuencias de tareas de implementación Configuration Manager para implementar el paquete piloto Aplicaciones Microsoft 365 para empresas en el grupo piloto.
5. Después de solucionar problemas de compatibilidad con el grupo piloto, Contoso ejecutó las secuencias de tareas para implementar el paquete Aplicaciones Microsoft 365 para empresas en el grupo amplio.

Dado que Contoso eligió actualizar automáticamente los dispositivos desde la nube, no era necesario administrar el proceso en Configuration Manager. Sus dispositivos se actualizan automáticamente directamente desde la nube en función del canal de actualización que se definió en la implementación inicial.

Esta es la arquitectura de implementación de la instalación y las actualizaciones continuas de Contoso Aplicaciones Microsoft 365 para empresas.

![La infraestructura de implementación de Contoso para Aplicaciones Microsoft 365 para empresas.](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo Contoso [usa Microsoft Intune](contoso-mdm.md) en Microsoft 365 para empresas para administrar sus dispositivos y las aplicaciones que ejecutan en toda la organización.

## <a name="see-also"></a>Vea también

[Aplicaciones de Microsoft 365 para empresas](/deployoffice/deployment-guide-microsoft-365-apps)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Guías del laboratorio de pruebas](m365-enterprise-test-lab-guides.md)