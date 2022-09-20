---
title: Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)
description: Proporciona instrucciones para implementar la implementación de reglas de reducción de superficie expuesta a ataques.
keywords: Implementación de reglas de reducción de superficie expuesta a ataques, implementación de ASR, habilitación de reglas de asr, configuración de ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades de seguridad, protección contra vulnerabilidades de seguridad, reglas de vulnerabilidad de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas asr
search.product: eADQiWindows 10XVcnh
ms.mktglfcycl: manage
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.topic: article
ms.collection:
- M365-security-compliance
- m365solution-asr-rules
- highpri
ms.date: 09/19/2022
search.appverid: met150
ms.openlocfilehash: dbfdf76791309f637e3380d748ff4c6533d1daa8
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67811821"
---
# <a name="enable-attack-surface-reduction-asr-rules"></a>Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)

La implementación de reglas de reducción de superficie expuesta a ataques (ASR) mueve el primer anillo de prueba a un estado funcional habilitado.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-implementation-steps.png" alt-text="Procedimiento para implementar reglas de ASR" lightbox="images/asr-rules-implementation-steps.png":::
  

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>Paso 1: Transición de reglas asr de auditoría a bloque

1. Una vez que se determinen todas las exclusiones en modo de auditoría, empiece a establecer algunas reglas de ASR en el modo "bloquear", empezando por la regla que tiene el menor número de eventos desencadenados. Consulte [" Habilitar reglas de reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md).
2. Revise la página de informes en el portal de Microsoft 365 Defender; consulte [Informe de protección contra amenazas en Microsoft Defender para punto de conexión](threat-protection-reports.md). Revise también los comentarios de los campeones de ASR.
3. Refine las exclusiones o cree nuevas exclusiones según sea necesario.
4. Vuelva a cambiar las reglas problemáticas a Auditoría.

  >[!Note]
  >En el caso de las reglas problemáticas (reglas que crean demasiado ruido), es mejor crear exclusiones que desactivar las reglas o volver a auditar. Tendrá que determinar qué es lo mejor para su entorno.

  >[!Tip]
  >Cuando esté disponible, aproveche la configuración del modo Advertir en las reglas para limitar las interrupciones. La habilitación de reglas de ASR en el modo de advertencia le permite capturar eventos desencadenados y ver sus posibles interrupciones, sin bloquear realmente el acceso del usuario final. Más información: [Modo de advertencia para los usuarios](attack-surface-reduction.md#warn-mode-for-users).

### <a name="how-does-warn-mode-work"></a>¿Cómo funciona el modo Warn?

El modo de advertencia es efectivamente una instrucción Block, pero con la opción de que el usuario "Desbloquee" las ejecuciones posteriores del flujo o la aplicación especificados. El modo de advertencia se desbloquea en una combinación por dispositivo, usuario, archivo y proceso. La información del modo de advertencia se almacena localmente y tiene una duración de 24 horas.

### <a name="step-2-expand-deployment-to-ring-n--1"></a>Paso 2: Expandir la implementación al anillo n + 1

Cuando esté seguro de que ha configurado correctamente las reglas de ASR para el anillo 1, puede ampliar el ámbito de la implementación al siguiente anillo (anillo n + 1).

El proceso de implementación, los pasos 1 a 3, es básicamente el mismo para cada anillo posterior:

1. Reglas de prueba en Auditoría
2. Revisión de eventos de auditoría desencadenados por ASR en el portal de Microsoft 365 Defender
3. Creación de exclusiones
4. Revisión: refinar, agregar o quitar exclusiones según sea necesario
5. Establecer reglas en "block"
6. Revise la página de informes en el portal de Microsoft 365 Defender.
7. Crear exclusiones.
8. Deshabilite las reglas problemáticas o vuelva a cambiarlas a Auditoría.

#### <a name="customize-attack-surface-reduction-rules"></a>Personalizar las reglas de la reducción de superficie expuesta a ataques

A medida que continúe expandiendo la implementación de las reglas de reducción de la superficie expuesta a ataques, es posible que le resulte necesario o beneficioso personalizar las reglas de reducción de superficie expuesta a ataques que ha habilitado.

##### <a name="exclude-files-and-folders"></a>Excluir archivos y carpetas

Puede optar por excluir archivos y carpetas de que se evalúen mediante reglas de reducción de superficie expuesta a ataques. Cuando se excluye, no se bloqueará la ejecución del archivo aunque una regla de reducción de superficie expuesta a ataques detecte que el archivo contiene un comportamiento malintencionado.

Por ejemplo, tenga en cuenta la regla ransomware:

La regla de ransomware está diseñada para ayudar a los clientes empresariales a reducir los riesgos de ataques de ransomware, a la vez que garantiza la continuidad empresarial. De forma predeterminada, los errores de regla ransomware en el lado de la precaución y proteger contra los archivos que aún no han alcanzado suficiente reputación y confianza. Para reemphasize, la regla ransomware solo se desencadena en los archivos que no han ganado suficiente reputación positiva y prevalencia, en función de las métricas de uso de millones de nuestros clientes. Normalmente, los bloques se resuelven automáticamente, ya que los valores de "reputación y confianza" de cada archivo se actualizan incrementalmente a medida que aumenta el uso no problemático.

En los casos en los que los bloques no se resuelven automáticamente de forma oportuna, los clientes pueden, _en su propio riesgo_ , usar el mecanismo de autoservicio o una funcionalidad de "lista de permitidos" basada en el Indicador de compromiso (IOC) para desbloquear los propios archivos.

> [!WARNING]
> Excluir o desbloquear archivos o carpetas podría permitir que los archivos no seguros se ejecuten e infecten los dispositivos. Excluir archivos o carpetas puede reducir considerablemente la protección proporcionada por las reglas de reducción de la superficie expuesta a ataques. Los archivos que habrían sido bloqueados por una regla podrán ejecutarse y no habrá ningún informe o evento registrado.

La exclusión se aplica a todas las reglas que permiten exclusiones. Puede especificar un archivo individual, una ruta de acceso de carpeta o el nombre de dominio completo para un recurso. Sin embargo, no se puede limitar una exclusión a una regla específica.

Una exclusión solo se aplica cuando se inicia la aplicación o el servicio excluidos. Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.

La reducción de la superficie expuesta a ataques admite variables de entorno y caracteres comodín. Para obtener información sobre el uso de caracteres comodín, vea [Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y nombre de archivo](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).
Si tiene problemas con las reglas que detectan archivos que cree que no deben detectarse, [use el modo de auditoría para probar la regla](evaluate-attack-surface-reduction.md).

Consulte el tema [de referencia de las reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md) para obtener más información sobre cada regla.

##### <a name="use-group-policy-to-exclude-files-and-folders"></a>Uso de directiva de grupo para excluir archivos y carpetas

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y haga clic en **Plantillas administrativas**.

3. Expanda el árbol a **componentes** \> de **Windows Antivirus** \> de Microsoft Defender **Reducción de la superficie de ataque** de **Protección contra vulnerabilidades** \> de seguridad de Microsoft Defender.

4. Haga doble clic en la opción **Excluir archivos y rutas de acceso de Reglas de reducción de superficie expuesta a ataques** y establezca la opción **en Habilitado**. Seleccione **Mostrar** y escriba cada archivo o carpeta en la columna **Nombre de valor** . Escriba **0** en la columna **Valor** de cada elemento.

> [!WARNING]
> No use comillas, ya que no se admiten para la columna **Nombre de valor** ni para la columna **Valor** .

##### <a name="use-powershell-to-exclude-files-and-folders"></a>Uso de PowerShell para excluir archivos y carpetas

1. Escriba **powershell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Continúe usando `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` para agregar más carpetas a la lista.

    > [!IMPORTANT]
    > Use `Add-MpPreference` para anexar o agregar aplicaciones a la lista. El uso del `Set-MpPreference` cmdlet sobrescribirá la lista existente.

##### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Uso de CSP de MDM para excluir archivos y carpetas

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) para agregar exclusiones.

##### <a name="customize-the-notification"></a>Personalizar la notificación

Puede personalizar la notificación para cuando se desencadene una regla y bloquee una aplicación o un archivo. Consulte el artículo [Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center).

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Introducción a la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment.md)

[Planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-plan.md)

[Probar las reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-test.md)

[Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-operationalize.md)

[Referencia de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-reference.md)
