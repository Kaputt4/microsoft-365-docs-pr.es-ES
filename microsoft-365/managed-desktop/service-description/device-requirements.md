---
title: Requisitos del dispositivo
description: Resumen de los requisitos mínimos de hardware y software para que los dispositivos funcionen con Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 5fb600434c8f6d7b62e7fd7408c3567a34c0eda0
ms.sourcegitcommit: bcea69bacd1b48827bd60af2880909593a1609a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2022
ms.locfileid: "62202058"
---
# <a name="device-requirements"></a>Requisitos del dispositivo

Microsoft Managed Desktop evalúa periódicamente los requisitos del dispositivo que se incluirán en el servicio. En este artículo se describen los requisitos de hardware y software que debe cumplir un dispositivo para poder trabajar con Microsoft Managed Desktop. Puedes revisar una lista de dispositivos específicos ya aprobados para su uso con el servicio en función de estos requisitos. Filtro de Escritorio administrado de Microsoft en el sitio [de Windows Pro de dispositivos empresariales](https://www.microsoft.com/en-us/windows/business/devices)

> [!NOTE]
> Estos requisitos pueden cambiar en cualquier momento, pero proporcionaremos un aviso de 30 días de cualquier cambio en los requisitos de hardware. Los requisitos modificados más recientemente se marcan con <b>\*</b> . 

## <a name="check-hardware-requirements"></a>Comprobar requisitos de hardware

Además de revisar las especificaciones del dispositivo, también puedes usar el control de evaluación de preparación descargable para comprobar que un dispositivo determinado cumple los requisitos necesarios. [](../get-ready/readiness-assessment-downloadable.md) Esta herramienta también comprueba la configuración de red y los puntos de conexión que también son necesarios para que el servicio funcione.

## <a name="minimum-requirements"></a>Requisitos mínimos

Para inscribirse en Microsoft Managed Desktop, un dispositivo debe cumplir o superar todos estos requisitos.

### <a name="manufacturer"></a>Fabricante

El dispositivo debe haber sido creado por uno de estos fabricantes:

- Dell
- HP
- Lenovo
- Microsoft

> [!NOTE] 
> A partir del 01 de marzo de 2022, los dispositivos administrados por Microsoft Managed Desktop deben ser compatibles con el OEM. Trabaje con su OEM para averiguar cuándo los dispositivos de su cartera alcanzarán el soporte técnico de fin de vida. Los clientes serán responsables de garantizar que los dispositivos se reemplazan antes del fin de la vida útil. Cualquier dispositivo que no sea compatible con OEM seguirá siendo administrado por Microsoft Managed Desktop, pero la compatibilidad con estos dispositivos puede ser limitada, ya que están en riesgo de problemas de seguridad y rendimiento que puede que nuestro servicio no pueda mitigar.
</b>

### <a name="installed-software"></a>Software instalado

El dispositivo debe tener preinstalado este software:

- <b>\*</b>Windows 10 o Windows 11: Enterprise, Pro o Pro Workstation Edition
- la versión de 64 bits de Aplicaciones Microsoft 365 para empresas 
- Todos los controladores de dispositivo aplicables


### <a name="physical-features"></a>Características físicas

Los dispositivos deben tener estas capacidades:

- Habilitado para el arranque seguro de UEFI 
- Módulo de plataforma de confianza 2.0 
- Compatible con la seguridad basada en virtualización 
- [Integridad de código protegida por hipervisor](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) compatible con el BIOS

Para obtener más información sobre estas capacidades y las tecnologías relacionadas con ellas que usa el servicio, vea [Tecnologías de Escritorio administrado de Microsoft](../intro/technologies.md).

> [!NOTE]
>- ARM procesadores no son compatibles.
>- <b>\*</b>Windows 11 tiene requisitos de [hardware adicionales.](/windows/whats-new/windows-11-requirements)

Los dispositivos deben cumplir o superar los siguientes límites de almacenamiento y memoria:

- La unidad de arranque debe ser de cualquier tipo que no sea un disco duro. Por ejemplo, las unidades SSD, NVMe y eMMC son opciones válidas.
- La unidad de arranque debe tener una capacidad de al menos 128 GB.
- La memoria interna del dispositivo (RAM) debe ser igual o superior a 8 GB.

Si el dispositivo se hizo después del 1 de julio de 2020, también debe tener una cámara IR, un lector de huellas digitales o [ambos,](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)para admitir Windows Hello .

## <a name="recommended-features"></a>Características recomendadas

Los usuarios tendrán una experiencia mucho mejor si eliges dispositivos que tengan estas características:

- Un procesador intel vPro-platform o un procesador amd ryzen Pro procesador
- Unidad de arranque del tipo SSD con una capacidad de al menos 256 GB
- Memoria de dispositivo interna (RAM) de al menos 16 GB
- Compatibilidad con espera moderna
- El dispositivo es de tipo PC de núcleo seguro
- Admite protección de kernel DMA
