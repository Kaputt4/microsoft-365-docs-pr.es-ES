---
title: Imágenes del dispositivo
description: Requisitos de imagen al ordenar nuevos dispositivos o volver a la aplicación de dispositivos existentes
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3d0b0f1adac589b910b5fabf2c22d08cbd65f142
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276934"
---
# <a name="device-images"></a>Imágenes del dispositivo


Ya sea que [ordenes nuevos dispositivos](#new-devices) o reutilices los existentes, tienes varias opciones para asegurarte de que la imagen del dispositivo cumple con nuestros requisitos [de dispositivo.](device-requirements.md#check-hardware-requirements) [](#existing-devices)

## <a name="new-devices"></a>Nuevos dispositivos
Cuando ordenes un nuevo dispositivo a un fabricante [aprobado,](device-requirements.md#minimum-requirements)sigue estos pasos para asegurarte de que envían dispositivos con la configuración Escritorio administrado de Microsoft imagen y software. Cada vez que planees inscribir un modelo de dispositivo determinado en el servicio por primera vez, debes probar un ejemplo para asegurarte de que ofrece la experiencia de usuario que esperas. Para obtener más información, vea [Validate new devices](/microsoft-365/managed-desktop/get-started/validate-device).

### <a name="dell"></a>Dell
Trabaje directamente con el representante de ventas de Dell, que se asegurará de que la imagen aprobada por Escritorio administrado de Microsoft se aplique a los dispositivos para su pedido. Para obtener más preguntas sobre dispositivos Dell, la imagen y el proceso de pedido, póngase en contacto con MMD_at_dell@dell.com.

### <a name="hp"></a>HP 
Cuando ordenes nuevos dispositivos de HP, asegúrate de usar la SKU específica que se muestra en la sección Requisitos adicionales para cada modelo que se encuentra en el sitio de dispositivos empresariales de [Shop Windows 10 Pro](https://www.microsoft.com/windowsforbusiness/view-all-devices) (filtra la vista para mostrar Escritorio administrado de Microsoft dispositivos).

Si estás ordenando un dispositivo de HP [](customizing.md) que se ha aprobado como una excepción pero que no aparece actualmente en la página Lista de dispositivos, asegúrate de solicitar la SKU que se usará para el modelo. Trabajaremos con HP para obtener esta información mediante su solicitud de excepción. También puedes ponerse en contacto directamente con HP para obtener cualquier pregunta sobre dispositivos e instrucciones de ordenación de dispositivos mediante estas direcciones:
 
- Americas: mmd-americas@hp.com
- Europa/Oriente Medio/África: mmd-emea@hp.com
- Asia Pacífico/Japón: mmd-apj@hp.com
- Global: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Cuando ordenes dispositivos de Lenovo para usarlos en Escritorio administrado de Microsoft, tendrás que indicar un número de parte específico incluido como parte del pedido. Póngase en contacto con su representante de ventas de Lenovo o con el partner de canal de Lenovo y pídales que creen un *"modelo* de oferta especial" con un sistema que cumpla con nuestros requisitos [de dispositivo.](device-requirements.md#minimum-requirements) Para incluir una imagen precargado compatible con Escritorio administrado de Microsoft, pida al representante de ventas que haga referencia a "*System building block part number SBB0Q94938 – MMD Enablement*."

Actualmente, los siguientes productos están habilitados Escritorio administrado de Microsoft soporte técnico:

- L13 Gen 1
- L13 Yoga Gen 1
- L14 Gen 1 (Intel)
- L14 Gen 1 (AMD)
- L15 Gen 1 (Intel)
- L15 Gen 1 (AMD)
- X1 Carbon Gen 8
- X1 Yoga Gen 5
- T14 Gen 1 (Intel)
- T14 Gen 1 (AMD)
- T15 Gen 1
- X13 Gen 1 (Intel)


### <a name="microsoft"></a>Microsoft
Todos los dispositivos microsoft que cumplen los requisitos del dispositivo vienen con una imagen que funciona con Escritorio administrado de Microsoft. No se requieren otros pasos.

Para obtener la imagen más reciente disponible en la fábrica en un dispositivo Microsoft, trabaja con el especialista de Surface para usar el proceso de surface "Poteado".

## <a name="existing-devices"></a>Dispositivos existentes

Puedes reutilizar los dispositivos existentes siempre que cumplan los requisitos [del](device-requirements.md#minimum-requirements) dispositivo y los [requisitos de software.](device-requirements.md#installed-software) Siga los pasos relevantes para el fabricante.

Puede volver a crear una imagen de dispositivos con una imagen del fabricante o mediante el Escritorio administrado de Microsoft "imagen universal". Para obtener una imagen de fabricante adecuada, podrías ordenar al menos un [nuevo](#new-devices) dispositivo del modelo que estás reusando. A continuación, puedes obtener la imagen de ese dispositivo y aplicarla a otros dispositivos del mismo modelo.

> [!NOTE]
> Es usted el responsable de crear, probar e implementar imágenes. También se recomienda usar imágenes apropiadas proporcionadas por el fabricante siempre que sea posible en lugar de imágenes personalizadas, incluida la "imagen universal".

### <a name="hp"></a>HP

Los equipos comerciales de HP que se suministran con la imagen de HP Corporate Ready incluyen un . Archivo WIM para la recuperación. Puedes usar esta imagen para aplicar la imagen de restauración de fábrica a otros dispositivos del mismo modelo.

Estos pasos quitarán todos los datos del dispositivo, por lo que antes de iniciar debes hacer una copia de seguridad de los datos que quieras conservar.

1. [Crea una unidad USB de arranque](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) con WinPE.
2. Copie estos archivos de C: \\ SOURCES en la unidad USB:
    - El archivo WIM de recuperación de fábrica (por ejemplo, HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - IMPLEMENTAR. CMD
    - ReCreatePartitions.txt
3. [Arranque el dispositivo en WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) Unidad USB.
4. En un símbolo del sistema, ejecute [Diskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references).
5. En Diskpart, ejecute y, a continuación, anote el número de disco de `list disk` almacenamiento principal (normalmente, Disco 0).
6. Salga de Diskpart escribiendo `exit` .
7. En el símbolo del sistema, ejecute , donde sys_disk es el número de disco del disco de almacenamiento principal que acaba de determinar y recovery_wim es el nombre `deploy.cmd <sys_disk> <recovery_wim>` de archivo del archivo .   ARCHIVO WIM que copió anteriormente.
8. Quita la unidad USB y, a continuación, reinicia el dispositivo.

### <a name="microsoft"></a>Microsoft 

Los dispositivos Microsoft Surface incluyen imágenes de "recuperación [completa"](https://support.microsoft.com/en-us/surfacerecoveryimage) específicas de cada modelo. Puede usar estas imágenes para volver a crear imágenes de dispositivos.

Estas imágenes usan el Windows de recuperación (WinRE) y este es un proceso manual (no automatizado). Sigue los pasos de [Crear y usar una unidad de recuperación USB para Surface](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07).


### <a name="universal-image"></a>Imagen universal
Escritorio administrado de Microsoft ha creado una imagen que contiene Windows 10 Pro y Aplicaciones Microsoft 365 para Enterprise que puede usar con Escritorio administrado de Microsoft. Sin embargo, es mejor usar imágenes adecuadas Escritorio administrado de Microsoft proporcionadas por el fabricante siempre que sea posible, incluso si eso significa una versión de Windows anterior que, a continuación, debe actualizarse una vez que el usuario inicia sesión. El uso Escritorio administrado de Microsoft imagen universal debe ser una opción final.

- Actualizamos la imagen con las actualizaciones de calidad mensuales más recientes Windows cada 30-60 días y Aplicaciones Microsoft 365 actualizaciones Enterprise actualizaciones al menos dos veces al año.
- La imagen contiene un paquete de aprovisionamiento de recuperación para garantizar Aplicaciones Microsoft 365 para Enterprise se restaura después Windows escenarios de recuperación.
- Puedes implementar la imagen con unidades USB. Contiene un proceso que permite insertar controladores (descritos en la documentación incluida con la imagen).
- Puede modificar los scripts y carpetas incluidos para usarlos con otras personalizaciones, como agregar actualizaciones acumulativas específicas, código de copia de archivos o realizar otras comprobaciones.
- Los controladores y las actualizaciones de calidad se agregan a Windows durante la implementación desde la unidad USB.

> [!NOTE]
> Es su responsabilidad agregar todos los controladores necesarios, realizar todas las pruebas y asegurarse de que no haya problemas con la imagen implementada final. Proporcionamos la imagen universal "tal como está", pero proporcionaremos orientación técnica y responderemos a las preguntas. Póngase en contacto MMDImage@microsoft.com.

Envíe solicitudes para el contenido y la documentación de imagen universal creando una solicitud de cambio en el [portal de administración.](../get-started/access-admin-portal.md)


