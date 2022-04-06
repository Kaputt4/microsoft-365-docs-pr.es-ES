---
title: Software no deseado
ms.reviewer: ''
description: Obtenga información sobre cómo el software no deseado cambia la configuración predeterminada sin su consentimiento y lo que puede hacer para protegerse.
keywords: security, malware, protection, unwanted, software, alter, infect, unwanted software, software bundlers, browser modifiers, privacy, security, computing experience, prevent infection, solution, WDSI, MMPC, Centro de protección contra malware de Microsoft, virus research threats, research malware, pc protection, computer infection, virus infection, descriptions, remediation, latest amenazas
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 94b3bad5b5653420d91cd422d40a0ff7802e6442
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683671"
---
# <a name="unwanted-software"></a>Software no deseado

El software no deseado son programas que modifican la Windows sin su consentimiento o control. Esto puede tener la forma de experiencia de exploración modificada, falta de control sobre descargas e instalación, mensajes engañosos o cambios no autorizados en la Windows configuración.

## <a name="how-unwanted-software-works"></a>Cómo funciona el software no deseado

El software no deseado se puede introducir cuando un usuario busca y descarga aplicaciones de Internet. Algunas aplicaciones son agrupadores de software, lo que significa que están empaquetadas con otras aplicaciones. Como resultado, otros programas se pueden instalar accidentalmente cuando se descarga la aplicación original.

Estas son algunas indicaciones de software no deseado:

- Hay programas que no se instalaron y que pueden ser difíciles de desinstalar

- Las características o la configuración del explorador han cambiado y no se pueden ver ni modificar.

- Hay mensajes excesivos sobre el estado del dispositivo o sobre archivos y programas

- Hay anuncios que no se pueden cerrar fácilmente

Algunos indicadores son más difíciles de reconocer porque son menos disruptivos, pero siguen siendo no deseados. Por ejemplo, el software no deseado puede modificar páginas web para mostrar anuncios específicos, supervisar actividades de exploración o quitar el control del explorador.

Microsoft usa un amplio criterio [de evaluación para](criteria.md) identificar software no deseado.

## <a name="how-to-protect-against-unwanted-software"></a>Cómo proteger contra software no deseado

Para evitar infecciones de software no deseadas, descargue software solo desde sitios web oficiales o desde el Microsoft Store. Tenga cuidado con la descarga de software de sitios de terceros.

Use [Microsoft Edge](/microsoft-edge/deploy/index) al navegar por Internet. Microsoft Edge incluye protecciones adicionales que bloquean eficazmente los modificadores del explorador que pueden cambiar la configuración del explorador. Microsoft Edge también bloquea los sitios web conocidos que hospedan software no deseado [Windows Defender SmartScreen](/microsoft-edge/deploy/index) (también usado por Internet Explorer).

Habilite [Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10) en Windows 10. Proporciona protección en tiempo real contra amenazas y detecta y elimina software no deseado conocido.

Descargue [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201) protección en tiempo real en Windows 7 o Windows Vista.

Para obtener más sugerencias generales, consulte [Prevent malware infection](prevent-malware-infection.md).

### <a name="what-should-i-do-if-my-device-is-infected"></a>¿Qué debo hacer si mi dispositivo está infectado? 

Si sospecha que tiene software no deseado, puede [enviar archivos para su análisis](https://www.microsoft.com/wdsi/filesubmission).

Algunos software no deseados agregan entradas de desinstalación, lo que significa que puede **quitarlas mediante Configuración**.
1. Seleccione el botón Inicio
2. Ve a **Configuración > aplicaciones > aplicaciones & características**.
3. Selecciona la aplicación que quieres desinstalar y, a continuación, haz clic en **Desinstalar**.

Si solo notó recientemente síntomas de infección de software no deseada, considere ordenar las aplicaciones por fecha de instalación y, a continuación, desinstale las aplicaciones más recientes que no instaló.

También es posible que deba **quitar complementos de** explorador en sus exploradores, como Internet Explorer, Firefox o Chrome.

En caso de que la eliminación de amenazas no se realiza correctamente, lea acerca [de la solución de problemas de detección](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware) y eliminación de malware.