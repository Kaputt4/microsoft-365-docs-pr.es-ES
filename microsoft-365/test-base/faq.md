---
title: Preguntas más frecuentes sobre la base de pruebas
description: Revisar las preguntas más frecuentes
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323384"
---
# <a name="test-base-faq"></a>Preguntas más frecuentes sobre la base de pruebas

**P: ¿Cómo se envían los paquetes al equipo base de pruebas?**

**A:** Envíe los paquetes directamente al entorno base de prueba mediante nuestro portal de autoservicio.

Para enviar el paquete de la aplicación, vaya a [Azure Portal](https://www.aka.ms/testbaseportal "Página principal de base de prueba") y cargue una carpeta comprimida que contenga los archivos binarios, las dependencias y los scripts de prueba de la aplicación a través del panel del portal de prueba base de autoservicio. 

Consulte la guía del usuario de incorporación para obtener más información o póngase en contacto con nuestro equipo en para obtener <testbasepreview@microsoft.com> ayuda y más información.

**P: ¿Qué son las pruebas de salida (OOB)**

**A:** Las pruebas de fábrica (OOB) se estandarizan, se ejecuta la prueba predeterminada donde se instalan, se inician y se cierran treinta (30) veces los paquetes de aplicación y, a continuación, se desinstalan. 

Los paquetes creados para Test Base tendrán los siguientes scripts de prueba: instalar, iniciar, cerrar y, opcionalmente, el script de desinstalación. 

Las pruebas de lista para usar (OOB) le proporcionan telemetría estandarizada en la aplicación para comparar entre Windows compilaciones.

**P: ¿Podemos enviar pruebas fuera de las pruebas lista para usar (instalar, iniciar, cerrar, desinstalar scripts de prueba)?**

**A:** Sí, los clientes también pueden cargar paquetes de aplicaciones para **pruebas funcionales** a través del panel del portal de autoservicio.
**Las pruebas funcionales** son pruebas que permiten a los clientes ejecutar sus scripts para ejecutar funciones personalizadas en su aplicación.


## <a name="testing"></a>Pruebas

**P: ¿Admite pruebas funcionales?**

**A:** Sí, Test Base admite pruebas funcionales. Las pruebas funcionales son pruebas que permiten a nuestros clientes ejecutar sus scripts para ejecutar funciones personalizadas en su aplicación. 

Para enviar el paquete de la aplicación para pruebas funcionales, basta con cargar la carpeta comprimida que contiene los archivos binarios, dependencias y scripts de prueba de la aplicación a través de nuestro panel del portal de autoservicio. 

Consulte la guía del usuario de incorporación para obtener más información o póngase en contacto con nuestro equipo en para obtener <testbasepreview@microsoft.com> ayuda y más información.

**P: ¿Cómo controla Test Base nuestros datos de prueba?**

**A:** Test Base recopila y administra los datos de prueba de forma segura en el entorno de Azure. 

**P: ¿La base de pruebas puede admitir nuestras pruebas automatizadas?**

Sí, Test Base admite pruebas automatizadas, pero no se admiten pruebas manuales en este momento debido a las capacidades de servicio.

**P: ¿Qué idiomas y marcos de pruebas automatizadas admite?**

**A:** Se admiten todos los idiomas y marcos. Invocamos todos los scripts a través de PowerShell. 

También tendrá que proporcionar (cargar) los archivos binarios dependientes del marco necesario.

**P: ¿Cuánto tiempo proporciona Test Base los resultados de las pruebas?**

**A:** Para cada prueba que ejecutemos en las compilaciones de versión previa, proporcionaremos resultados en un plazo de 48 horas en el panel [de Azure Portal.](https://www.aka.ms/testbaseportal "Página principal de base de prueba")

**P: ¿Puede reiniciar después de la instalación?**

**A:** Sí, nuestro proceso admite el reinicio después de la instalación. Asegúrese de seleccionar esta opción en la lista desplegable "Configuración opcional" al configurar las **tareas** en el portal de incorporación.

Para las pruebas de lista para usar (OOB), puede especificar si se necesita un reinicio para el _script Install._

![Imagen de reinicio](Media/reboot.png)

Aunque para las pruebas funcionales, puede especificar si se requiere un reinicio para cada script que se agrega.

![Cómo seleccionar pruebas funcionales](Media/functionalreboot.png)

**P: ¿Windows versiones compatibles?**

**A:** Actualmente, se admiten Windows 10, Windows Server 2016, Windows Server 2016 Core, Windows Server 2019 y Windows Server 2019 Core.

**P: ¿Cuál es la diferencia entre las pruebas de actualización de seguridad y las pruebas de actualización de características?**

**A:** Para las pruebas de **<ins></ins>** actualización de seguridad, se prueban las actualizaciones de seguridad mensuales previas a la publicación en Windows que se centran en mantener a nuestros usuarios siempre seguros y protegidos. Para las pruebas de actualización **<ins></ins>** de características, se prueba con las actualizaciones de características binacionales previas a la versión, que introducen nuevas características y capacidades en Windows.

## <a name="debugging-options"></a>Opciones de depuración

**P: ¿Tenemos acceso a las máquinas virtuales (VM) en caso de errores? ¿Qué comparte Test Base?**

**A:** Para que el servicio sea compatible y las actualizaciones de versión previa sean seguras, solo Microsoft tiene acceso a las máquinas virtuales. Sin embargo, los clientes pueden ver los resultados de las pruebas y otras métricas de prueba en el panel del portal, incluidas las señales de bloqueo y bloqueo, las métricas de confiabilidad, la memoria y el uso de la CPU, etc. También generamos y proporcionamos registros de ejecuciones de pruebas en el panel para su descarga y análisis posterior. 

También podemos proporcionar volcados de memoria para la depuración de bloqueos según sea necesario.

**P: Si se han encontrado problemas durante las pruebas, ¿cuáles son los siguientes pasos para resolver estos problemas?**

**A:** El equipo base de prueba realizará un proceso de evaluación inicial para determinar la causa raíz del error y, según nuestros resultados, se enrutaremos al cliente o a los equipos internos de Microsoft para la depuración. 

Siempre trabajamos estrechamente con nuestros clientes en la corrección conjunta para resolver cualquier problema. 

**P: ¿Microsoft mantiene la versión de la revisión de seguridad hasta que se resuelva el problema? ¿Qué resoluciones alternativas están disponibles?**

**A:** El objetivo de Test Base es garantizar que nuestros clientes finales conjuntos no se enfrentan a ningún problema. Trabajaremos duro con los proveedores de software para solucionar cualquier problema antes de la versión, pero en caso de que la corrección no sea viable, tenemos otras resoluciones, como correcciones y bloques.

## <a name="miscellaneous"></a>Varios

**P: ¿Cómo funcionará el servicio con un servidor local?**

**A:** Actualmente no proporcionamos compatibilidad con servidores locales. Sin embargo, si el servidor expone el extremo HTTP, podemos conectarnos a él a través de Internet.

**P: ¿Quién hospeda las máquinas virtuales?**

**A:** Microsoft aprovisiona la máquina virtual para este servicio, tomando la carga de hacerlo desde el cliente.

**P: ¿Este servicio admite aplicaciones web, móviles o de escritorio?**

**A:** Actualmente, nuestro enfoque está en las aplicaciones de escritorio, sin embargo, tenemos planes para incorporar aplicaciones web en el futuro, pero no se admiten aplicaciones móviles en este momento.

**P: ¿Cuál es la diferencia entre Test Base y SUVP?**

**A:** La mayor diferencia entre Test Base y SUVP es que nuestros partners incorporaron sus aplicaciones en el entorno de Azure de Base de pruebas para que la validación se ejecute con actualizaciones de versión previa en lugar de realizar las propias pruebas. 

Además de las pruebas de actualizaciones de seguridad previas a la versión, se admiten pruebas de actualizaciones de características previas a la versión en nuestra plataforma. Tenemos muchos otros tipos de actualizaciones y pruebas del sistema operativo en nuestra guía básica.

**P: ¿Hay un costo asociado con el servicio?**

**A:** El servicio Base de prueba será gratuito para los usuarios hasta la Disponibilidad general (GA). En ese momento, anunciaremos una estructura de costos que estará en vigor para todos los clientes. 

**P: ¿Cómo puedo proporcionar comentarios sobre Test Base?**

**A:** Para compartir sus comentarios sobre Test Base, seleccione el icono **Comentarios** en la parte inferior izquierda del portal. Incluye una captura de pantalla con el envío para ayudar a Microsoft a comprender mejor tus comentarios. 

También puede enviar sugerencias de productos y enviar otras ideas en <testbasepreview@microsoft.com> .
