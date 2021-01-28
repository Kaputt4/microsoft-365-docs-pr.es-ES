---
title: Requisitos del dispositivo
description: Resumen de los requisitos mínimos de hardware y software para que los dispositivos funcionen con escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88b1ba657b4823d90a41b28b01362760676410ba
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032708"
---
# <a name="device-requirements"></a>Requisitos del dispositivo

Escritorio administrado de Microsoft evalúa periódicamente los requisitos del dispositivo para incluirse en el servicio. En este artículo se describen los requisitos de hardware y software que un dispositivo debe cumplir para poder trabajar con escritorio administrado de Microsoft. Puedes revisar una lista de dispositivos [específicos ya aprobados](device-list.md) para su uso con el servicio en función de estos requisitos.

> [!NOTE]
> Estos requisitos pueden cambiar en cualquier momento, pero proporcionaremos un aviso de 90 días de cualquiera de estos cambios. Los requisitos modificados más recientemente se marcan con **\*** . 

## <a name="check-hardware-requirements"></a>Comprobar los requisitos de hardware

Además de revisar las especificaciones del dispositivo, también puedes usar el comprobador de evaluación de preparación descargable para comprobar que un dispositivo determinado cumple los requisitos necesarios. [](../get-ready/readiness-assessment-downloadable.md) Esta herramienta también comprueba la configuración de red y los puntos de conexión que también son necesarios para que el servicio funcione.

## <a name="minimum-requirements"></a>Requisitos mínimos

Para inscribirse en el Escritorio administrado de Microsoft, un dispositivo debe cumplir o superar todos estos requisitos.

### <a name="manufacturer"></a>Fabricante

Uno de estos fabricantes debe haber creado el dispositivo:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software instalado

El dispositivo debe tener este software preinstalado:

- Windows 10 Enterprise, Pro o Pro Workstation Edition
- {the 64-bit version of Office click-to-run {I will double-check name w/ Office colleagues]}
- Todos los controladores de dispositivo aplicables


### <a name="physical-features"></a>Características físicas

Los dispositivos deben tener estas capacidades:

- Habilitado para el arranque seguro de UEFI 
- Módulo de plataforma segura 2.0 
- Capaz de una seguridad basada en virtualización 
- Admite la integridad de código protegida por hipervisor 

Para obtener más información sobre estas capacidades y las tecnologías relacionadas con ellas que usa el servicio, vea Tecnologías de [Escritorio administrado de Microsoft.](../intro/technologies.md)

> [!NOTE]
> ARM procesadores no son compatibles.

Los dispositivos deben cumplir o superar los siguientes límites de almacenamiento y memoria:

- La unidad de arranque debe ser de cualquier tipo que no sea un disco duro. Por ejemplo, las unidades SSD, NVMe y eMMC son opciones válidas.
- La unidad de arranque debe tener una capacidad de al menos 128 GB.

Si el dispositivo se hizo después del 1 de julio de 2020, también debe tener una cámara IR, un lector de huellas digitales o ambos, para admitir [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Requisitos recomendados

Aunque no son requisitos absolutos, los usuarios tendrán una experiencia mucho mejor si elige dispositivos que tienen estas características:

- Un procesador intel vPro-platform o un procesador AMD Ryzen Pro
- Unidad de arranque del tipo SSD con una capacidad de al menos 256 GB
- Compatibilidad con espera moderna
- El dispositivo es de tipo de equipo de núcleo seguro
- Compatible con la protección de DMA de kernel