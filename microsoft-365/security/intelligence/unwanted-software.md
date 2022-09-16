---
title: Software no deseado
ms.reviewer: ''
description: Obtenga información sobre cómo el software no deseado cambia la configuración predeterminada sin su consentimiento y lo que puede hacer para protegerse a sí mismo.
keywords: security, malware, protection, unwanted, software, alter, infect, unwanted software, software bundlers, browser modifiers, privacy, security, computing experience, prevent infection, solution, WDSI, MMPC, Centro de protección contra malware de Microsoft, virus research threats, research malware, pc protection, computer infection, virus infection, descriptions, remediation, latest Amenazas
ms.service: microsoft-365-security
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
ms.openlocfilehash: db9a37bf18296e23763e6652bc25d0c50fd282cc
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67742319"
---
# <a name="unwanted-software"></a>Software no deseado

El software no deseado son programas que modifican la experiencia de Windows sin su consentimiento o control. Esto puede adoptar la forma de experiencia de exploración modificada, la falta de control sobre las descargas y la instalación, mensajes engañosos o cambios no autorizados en la configuración de Windows.

## <a name="how-unwanted-software-works"></a>Funcionamiento del software no deseado

El software no deseado se puede introducir cuando un usuario busca y descarga aplicaciones de Internet. Algunas aplicaciones son agrupaciones de software, lo que significa que están empaquetadas con otras aplicaciones. Como resultado, otros programas se pueden instalar involuntariamente cuando se descarga la aplicación original.

Estas son algunas indicaciones de software no deseado:

- Hay programas que no ha instalado y que pueden ser difíciles de desinstalar

- Las características o la configuración del explorador han cambiado y no se pueden ver ni modificar

- Hay mensajes excesivos sobre el estado del dispositivo o sobre archivos y programas

- Hay anuncios que no se pueden cerrar fácilmente

Algunos indicadores son más difíciles de reconocer porque son menos perturbadores, pero siguen siendo no deseados. Por ejemplo, el software no deseado puede modificar páginas web para mostrar anuncios específicos, supervisar actividades de exploración o quitar el control del explorador.

Microsoft usa un amplio [criterio de evaluación](criteria.md) para identificar software no deseado.

## <a name="how-to-protect-against-unwanted-software"></a>Protección contra software no deseado

Para evitar una infección de software no deseada, descargue software solo desde sitios web oficiales o desde Microsoft Store. Tenga cuidado con la descarga de software de sitios de terceros.

Use [Microsoft Edge](/microsoft-edge/deploy/index) al navegar por Internet. Microsoft Edge incluye protecciones adicionales que bloquean eficazmente los modificadores de explorador que pueden cambiar la configuración del explorador. Microsoft Edge también bloquea los sitios web conocidos que hospedan software no deseado mediante [Windows Defender SmartScreen](/microsoft-edge/deploy/index) (también utilizado por Internet Explorer).

Habilite [antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-in-windows-10) en Windows 10. Proporciona protección en tiempo real contra amenazas y detecta y elimina software no deseado conocido.

Descargue [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201) para obtener protección en tiempo real en Windows 7 o Windows Vista.

Para obtener sugerencias más generales, consulte [prevención de la infección por malware](prevent-malware-infection.md).

### <a name="what-should-i-do-if-my-device-is-infected"></a>¿Qué debo hacer si mi dispositivo está infectado? 

Si sospecha que tiene software no deseado, puede [enviar archivos para su análisis](https://www.microsoft.com/wdsi/filesubmission).

Algunos software no deseado agrega entradas de desinstalación, lo que significa que puede **quitarlas mediante Configuración**.
1. Seleccione el botón Inicio.
2. Vaya a **Configuración > Aplicaciones > Aplicaciones & características**.
3. Seleccione la aplicación que desea desinstalar y, a continuación, haga clic en **Desinstalar**.

Si usted sólo recientemente notó síntomas de infección de software no deseado, considere la posibilidad de ordenar las aplicaciones por fecha de instalación, y luego desinstalar las aplicaciones más recientes que no se instaló.

También es posible que tenga que **quitar los complementos del explorador** en sus exploradores, como Internet Explorer, Firefox o Chrome.

En caso de que la eliminación de amenazas no sea correcta, lea sobre [la solución de problemas de detección y eliminación de malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).