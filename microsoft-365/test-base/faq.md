---
title: Preguntas más frecuentes sobre la base de pruebas
description: Revisar las preguntas más frecuentes
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7fd01b95d461332baaf4eac90aee4715da3e55e
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953038"
---
# <a name="test-base-faq"></a>Preguntas más frecuentes sobre la base de pruebas

**P: ¿Cómo se envían los paquetes al equipo base de pruebas?**

**Un:** Envíe los paquetes directamente al entorno base de prueba mediante nuestro portal de autoservicio.

Para enviar el paquete de aplicación, vaya a [Azure Portal](https://www.aka.ms/testbaseportal "Página principal base de prueba") y cargue una carpeta comprimida que contenga los archivos binarios, las dependencias y los scripts de prueba de la aplicación a través del panel del portal base de pruebas de autoservicio.

Consulte la guía del usuario de incorporación para obtener más información o póngase en contacto con nuestro equipo en <testbasepreview@microsoft.com> para obtener ayuda y más información.

**P: ¿Qué son las pruebas integradas (OOB)?**

**Un:** Las pruebas integradas (OOB) están estandarizadas, las pruebas predeterminadas se ejecutan donde los paquetes de aplicación se instalan, se inician y cierran treinta (30) veces y, a continuación, se desinstalan.

Los paquetes creados para Test Base tendrán los siguientes scripts de prueba: instalar, iniciar, cerrar y, opcionalmente, el script de desinstalación.

Las pruebas integradas (OOB) proporcionan telemetría estandarizada en la aplicación para compararlas entre Windows compilaciones.

**P: ¿Podemos enviar pruebas fuera de las pruebas integradas (instalar, iniciar, cerrar, desinstalar scripts de prueba)?**

**Un:** Sí, los clientes también pueden cargar paquetes de aplicaciones para **pruebas funcionales** a través del panel del portal de autoservicio.
**Las pruebas funcionales** son pruebas que permiten a los clientes ejecutar sus scripts para ejecutar funcionalidad personalizada en su aplicación.

## <a name="testing"></a>Pruebas

**P: ¿Admite pruebas funcionales?**

**Un:** Sí, Test Base admite pruebas funcionales. Las pruebas funcionales son pruebas que permiten a nuestros clientes ejecutar sus scripts para ejecutar funcionalidad personalizada en su aplicación.

Para enviar el paquete de aplicación para pruebas funcionales, cargue la carpeta comprimida que contiene los archivos binarios, las dependencias y los scripts de prueba de la aplicación a través de nuestro panel del portal de autoservicio.

Consulte la guía del usuario de incorporación para obtener más información o póngase en contacto con nuestro equipo en <testbasepreview@microsoft.com> para obtener ayuda y más información.

**P: ¿Cómo controla Test Base nuestros datos de prueba?**

**Un:** Test Base recopila y administra de forma segura los datos de prueba en el entorno de Azure.

**P: ¿Puede Test Base admitir nuestras pruebas automatizadas?**

**Un:** Sí, Test Base admite pruebas automatizadas; sin embargo, no se admiten pruebas manuales en este momento debido a las capacidades del servicio.

**P: ¿Qué lenguajes y marcos de pruebas automatizadas admite?**

**Un:** Se admiten todos los lenguajes y marcos. Invocamos todos los scripts a través de PowerShell.

También tendrá que proporcionar (cargar) los archivos binarios dependientes del marco necesario.

**P: ¿Cuánto tiempo proporciona Test Base los resultados de las pruebas?**

**Un:** Para cada prueba que se ejecute en las compilaciones anteriores a la versión, proporcionaremos resultados en un plazo de 48 horas en el panel de [Azure Portal](https://www.aka.ms/testbaseportal "Página principal base de prueba") .

**P: ¿Puede reiniciar después de la instalación?**

**Un:** Sí, nuestro proceso admite el reinicio después de la instalación. Asegúrese de seleccionar esta opción en la lista desplegable "Configuración opcional" al establecer **las tareas** en el portal de incorporación.

En el caso de las pruebas integradas (OOB), puede especificar si se necesita un reinicio para el _script de instalación._

![Imagen de reinicio.](Media/reboot.png)

Mientras que para las pruebas funcionales, puede especificar si se requiere un reinicio para cada script que se agrega.

![Cómo seleccionar pruebas funcionales.](Media/functionalreboot.png)

**P: ¿Qué versiones de Windows admite?**

**Un:** Actualmente se admiten clientes Windows 10, Windows Server 2016, Windows Server 2016 versión Core, Windows Server 2019 y Windows Server 2019 Core.

**P: ¿Cuál es la diferencia entre las pruebas de actualización de seguridad y las pruebas de actualización de características?**

**Un:** En el caso de las pruebas de actualización de seguridad, se prueban **<ins>las actualizaciones de seguridad de versión preliminar mensuales</ins>** en Windows, que se centran en mantener a nuestros usuarios siempre protegidos y protegidos. En el caso de las pruebas de actualización de características, se prueban las **<ins>actualizaciones de características de versión preliminar bianuales</ins>** que presentan nuevas características y funcionalidades en Windows.

## <a name="debugging-options"></a>Opciones de depuración

**P: ¿Obtenemos acceso a la Virtual Machines (VM) en caso de errores? ¿Qué comparte Test Base?**

**Un:** Para que el servicio sea compatible y las actualizaciones de versión preliminar sean seguras, solo Microsoft tiene acceso a las máquinas virtuales. Sin embargo, los clientes pueden ver los resultados de las pruebas y otras métricas de prueba en el panel del portal, como señales de bloqueo y bloqueo, métricas de confiabilidad, uso de memoria y CPU, etc. También generamos y proporcionamos registros de ejecuciones de prueba en el panel para su descarga y análisis posterior.

También podemos proporcionar volcados de memoria para la depuración de bloqueos según sea necesario.

**P: Si se han detectado problemas durante las pruebas, ¿cuáles son los pasos siguientes para resolver estos problemas?**

**Un:** El equipo de Test Base realizará un proceso de evaluación de prioridades inicial para determinar la causa principal del error y, a continuación, en función de nuestros resultados, se enrutará al cliente o a los equipos internos de Microsoft para la depuración.

Siempre trabajamos estrechamente con nuestros clientes en la corrección conjunta para resolver cualquier problema.

**P: ¿Microsoft mantiene la versión de la revisión de seguridad hasta que se resuelva el problema? ¿Qué resoluciones alternativas están disponibles?**

**Un:** El objetivo de Test Base es asegurarse de que nuestros clientes finales conjuntos no se enfrentan a ningún problema. Trabajaremos duro con los proveedores de software para solucionar cualquier problema antes de la versión, pero en caso de que la corrección no sea factible, tenemos otras resoluciones, como correcciones de compatibilidad y bloques.

## <a name="miscellaneous"></a>Varios

**P: ¿Cómo funcionará el servicio con un servidor local?**

**Un:** Actualmente no se proporciona compatibilidad con servidores locales. Sin embargo, si el servidor expone el punto de conexión HTTP, podemos conectarnos a él a través de Internet.

**P: Quién hospeda las máquinas virtuales?**

**Un:** Microsoft aprovisiona la máquina virtual para este servicio, tomando la carga de hacerlo desde el cliente.

**P: ¿Este servicio admite aplicaciones web, móviles o de escritorio?**

**Un:** Actualmente, nuestro enfoque está en las aplicaciones de escritorio, sin embargo, tenemos planes para incorporar aplicaciones web en el futuro, pero no se admiten aplicaciones móviles en este momento.

**P: ¿Cuál es la diferencia entre test base y SUVP?**

**Un:** La mayor diferencia entre Test Base y SUVP es que nuestros asociados incorporan sus aplicaciones al entorno de Azure de La base de pruebas para que la validación se ejecute con actualizaciones de versión preliminar en lugar de realizar las propias pruebas.

Además de las pruebas de actualizaciones de seguridad de versión preliminar, se admiten las pruebas de actualizaciones de características de versión preliminar en nuestra plataforma. Tenemos muchos otros tipos de actualizaciones y pruebas del sistema operativo en nuestra hoja de ruta.

**P: ¿Hay algún costo asociado al servicio?**

**Un:** A partir del 1 de marzo de 2022, se le proporcionarán 100 horas gratuitas (valoradas en 800 USD) que expirarán en 6 meses en la suscripción para sus necesidades de validación. Una vez consumidas las horas libres (o expiradas antes de usarlas), se le medirá automáticamente en 8 USD por hora en comparación con el uso.

**P: ¿Cómo puedo proporcionar comentarios sobre test base?**

**Un:** Para compartir sus comentarios sobre test base, seleccione el icono **Comentarios** en la parte inferior izquierda del portal. Incluya una captura de pantalla con el envío para ayudar a Microsoft a comprender mejor sus comentarios.

También puede enviar sugerencias de productos y enviar otras ideas en <testbasepreview@microsoft.com>.
