---
title: Imágenes del dispositivo
description: Requisitos de imagen al ordenar nuevos dispositivos o volver a la aplicación de dispositivos existentes
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: f1d00c12512b70ffd62372aaeae787acf1911573
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330291"
---
# <a name="device-images"></a>Imágenes del dispositivo

Ya sea que [ordenes nuevos dispositivos](#new-devices) o reutilices los existentes, tienes varias opciones para asegurarte de que la imagen del dispositivo cumple con nuestros requisitos [de dispositivo](device-requirements.md#check-hardware-requirements).[](#existing-devices)

## <a name="new-devices"></a>Nuevos dispositivos

Cuando ordenes un nuevo dispositivo a un fabricante [aprobado, sigue](device-requirements.md#minimum-requirements) estos pasos para asegurarte de que envían dispositivos con la configuración correcta de software y imagen de Escritorio administrado de Microsoft.

Cada vez que planees inscribir un modelo de dispositivo en particular en el servicio por primera vez, debes probar un ejemplo para asegurarte de que ofrece la experiencia del usuario que esperas. Para obtener más información, consulta [Validar nuevos dispositivos](/microsoft-365/managed-desktop/get-started/validate-device).

### <a name="dell"></a>Dell

Trabaje directamente con el representante de ventas de Dell.

El representante se asegurará de que la imagen aprobada por Microsoft Managed Desktop se aplique a dispositivos en su orden. Para obtener más información sobre los dispositivos Dell, la imagen y el proceso de ordenación, póngase en contacto con MMD_at_dell@dell.com.

### <a name="hp"></a>HP

Cuando ordenes nuevos dispositivos de HP, asegúrate de usar la SKU específica que aparece en la sección Requisitos adicionales para cada modelo que se encuentra en la página Comprar [Windows Pro dispositivos](https://www.microsoft.com/windows/business/devices#view-all-filter) empresariales. Filtre la vista para enumerar los dispositivos de Escritorio administrado de Microsoft.

Si estás ordenando un dispositivo de HP que se ha aprobado como una excepción [, pero](customizing.md) que actualmente no aparece en la página Lista de dispositivos, solicita que se utilice la SKU para el modelo. Trabajaremos con HP para obtener esta información mediante su solicitud de excepción. También puedes ponerse en contacto directamente con HP para obtener cualquier pregunta sobre dispositivos e instrucciones de ordenación de dispositivos mediante estas direcciones:

- Americas: mmd-americas@hp.com
- Europa/Oriente Medio/África: mmd-emea@hp.com
- Asia Pacífico/Japón: mmd-apj@hp.com
- Global: mmd@hp.com

### <a name="lenovo"></a>Lenovo

Cuando ordenes dispositivos de Lenovo, debes indicar un número de parte específico en el orden. Póngase en contacto con su representante de ventas de Lenovo o con el partner de canal de Lenovo y pídales que creen *un "modelo* de oferta especial" con un sistema que cumpla con los requisitos [de nuestro dispositivo](device-requirements.md#minimum-requirements).

Para incluir una imagen precargado compatible con Microsoft Managed Desktop, pida al representante de ventas que haga referencia a "System *building block part number SBB0Q94938 - MMD Enablement*". Trabaje con el representante de ventas de Lenovo o el partner de canal de Lenovo para obtener servicios recomendados, soporte técnico e imágenes.

### <a name="microsoft"></a>Microsoft

Todos los dispositivos de Microsoft que cumplen los requisitos del dispositivo vienen con una imagen que funciona con Microsoft Managed Desktop. No se requieren otros pasos.

Para obtener la imagen más reciente disponible en la fábrica en un dispositivo Microsoft, trabaja con el especialista de Surface para usar el proceso de surface "Poteado".

## <a name="existing-devices"></a>Dispositivos existentes

Puedes reutilizar los dispositivos existentes siempre que cumplan ambos:

- [Requisitos del dispositivo](device-requirements.md#minimum-requirements)
- [Requisitos de software](device-requirements.md#installed-software)

Siga los pasos relevantes para el fabricante.

Puede volver a crear una imagen de dispositivos con una imagen del fabricante o mediante la "imagen universal" de Escritorio administrado de Microsoft. Para obtener una imagen de fabricante adecuada, ordena al menos un [nuevo](#new-devices) dispositivo del modelo que estás reusando. A continuación, puedes obtener la imagen de ese dispositivo y aplicarla a otros dispositivos del mismo modelo.

> [!NOTE]
> Es usted el responsable de crear, probar e implementar imágenes. También se recomienda usar imágenes apropiadas proporcionadas por el fabricante siempre que sea posible en lugar de imágenes personalizadas; esto incluye la "imagen universal".

### <a name="hp"></a>HP

Los equipos comerciales de HP incluidos con la imagen hp corporate ready incluyen un `.WIM` archivo para la recuperación. Puedes usar esta imagen para aplicar la imagen de restauración de fábrica a otros dispositivos del mismo modelo.

Los siguientes pasos quitarán todos los datos del dispositivo. Antes de empezar, debes hacer una copia de seguridad de los datos que quieras conservar.

**Para quitar los datos del dispositivo:**

1. [Crea una unidad USB de arranque](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) con WinPE.
2. Copie estos archivos en `C:\\SOURCES` la unidad USB:
    - El archivo WIM de recuperación de fábrica (por ejemplo, `HP\_EliteBook\_840\_G7\_Notebook\_PC\_CR\_2004.wim`)
    - `DEPLOY.CMD`
    - `ReCreatePartitions.txt`
3. [Arranque el dispositivo en WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) Unidad USB.
4. En un símbolo del sistema, ejecute [Diskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references).
5. En Diskpart, ejecute `list disk`y, a continuación, anote el número de disco de almacenamiento principal (normalmente, Disco 0).
6. Salga de Diskpart escribiendo `exit`.
7. En el símbolo del sistema, ejecute `deploy.cmd <sys_disk> <recovery_wim>`, `sys_disk` `recovery_wim` `.WIM` donde es el número de disco del disco de almacenamiento principal que determinó y es el nombre de archivo del archivo que copió anteriormente.
8. Quita la unidad USB y, a continuación, reinicia el dispositivo.

### <a name="microsoft"></a>Microsoft

Los dispositivos Microsoft Surface incluyen imágenes de "recuperación [completa" específicas](https://support.microsoft.com/en-us/surfacerecoveryimage) de cada modelo. Puede usar estas imágenes para volver a crear imágenes de dispositivos.

Estas imágenes usan el Windows de recuperación (WinRE). Este es un proceso manual (no automatizado). Sigue los pasos de [Crear y usar una unidad de recuperación USB para Surface](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07).

### <a name="universal-image"></a>Imagen universal

Microsoft Managed Desktop ha creado una imagen que contiene Windows Pro y Aplicaciones Microsoft 365 para Enterprise que puede usar con Microsoft Managed Desktop.

Sin embargo, es mejor usar imágenes apropiadas para el Escritorio administrado de Microsoft proporcionadas por el fabricante siempre que sea posible, incluso si eso significa que una versión de Windows anterior debe actualizarse una vez que el usuario inicia sesión. El uso de la imagen universal de Escritorio administrado de Microsoft debe ser una opción final.

- Actualizamos la imagen con las actualizaciones de calidad mensuales más recientes Windows cada 30-60 días y Aplicaciones Microsoft 365 actualizaciones Enterprise actualizaciones al menos dos veces al año.
- La imagen contiene un paquete de aprovisionamiento de recuperación para garantizar Aplicaciones Microsoft 365 para Enterprise se restaura después de Windows escenarios de recuperación.
- Puedes implementar la imagen con unidades USB. Contiene un proceso que permite insertar controladores. Este proceso se describe en la documentación incluida con la imagen.
- Puede modificar los scripts y carpetas incluidos con otras personalizaciones, como agregar actualizaciones acumulativas específicas, código de copia de archivos o realizar otras comprobaciones.
- Los controladores y las actualizaciones de calidad se agregan a Windows durante la implementación desde la unidad USB.

> [!NOTE]
> Es su responsabilidad agregar todos los controladores necesarios, realizar todas las pruebas y asegurarse de que no haya problemas con la imagen implementada final. Proporcionamos la imagen universal "tal como está", pero proporcionaremos orientación técnica y responderemos a las preguntas. Póngase en contacto MMDImage@microsoft.com.

Envíe solicitudes para el contenido y la documentación de imagen universal creando una solicitud de cambio en el [portal de administración](../get-started/access-admin-portal.md).
