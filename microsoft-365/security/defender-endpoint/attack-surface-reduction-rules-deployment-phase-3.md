---
title: 'Fase 3 de implementación de reglas de ASR: implementar'
description: Proporciona instrucciones para implementar la implementación de reglas de reducción de superficie de ataque.
keywords: Implementación de reglas de reducción de superficie de ataque, implementación de ASR, habilitar reglas asr, configurar ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades, anti exploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Microsoft Defender para endpoint, configurar reglas ASR
search.product: eADQiWindows 10XVcnh
ms.reviewer: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 8cd03198fb94bfba582fb148b1f8f0da00beecf1
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074767"
---
# <a name="asr-rules-deployment-phase-3-implement"></a>Fase 3 de implementación de reglas ASR: implementar

La fase de implementación mueve el anillo de las pruebas al estado funcional.

> [!div class="mx-imgBorder"]
> ![Pasos de implementación de reglas ASR](images/asr-rules-implementation-steps.png)

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>Paso 1: Transición de reglas ASR de auditoría a bloqueo

1. Una vez determinadas todas las exclusiones durante el modo de auditoría, empieza a establecer algunas reglas ASR en modo "bloquear", empezando por la regla que tiene el menor número de eventos desencadenados. Vea " [Habilitar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md).
2. Revise la página de informes en el portal de Microsoft 365 Defender web; vea Informe de protección contra amenazas [en Microsoft Defender para endpoint](threat-protection-reports.md). Revisa también los comentarios de tus campeones de ASR.
3. Refine las exclusiones o cree nuevas exclusiones según se determine necesario.
4. Vuelva a cambiar las reglas problemáticas a Auditoría.

  >[!Note]
  >Para las reglas problemáticas (reglas que crean demasiado ruido), es mejor crear exclusiones que desactivar las reglas o volver a auditar. Tendrá que determinar qué es lo mejor para su entorno.

  >[!Tip]
  >Cuando esté disponible, aproveche la configuración del modo de advertencia en las reglas para limitar las interrupciones. Habilitar reglas ASR en modo de advertencia permite capturar eventos desencadenados y ver sus posibles interrupciones, sin bloquear realmente el acceso del usuario final. Más información: [Modo de advertencia para usuarios.](attack-surface-reduction.md#warn-mode-for-users)

### <a name="how-does-warn-mode-work"></a>¿Cómo funciona el modo de advertencia?

El modo de advertencia es efectivamente una instrucción Block, pero con la opción de que el usuario "desbloquee" las ejecuciones posteriores del flujo o aplicación dados. El modo de advertencia desbloquea en una combinación de dispositivo, usuario, archivo y proceso. La información del modo de advertencia se almacena localmente y tiene una duración de 24 horas.

### <a name="step-2-expand-deployment-to-ring-n--1"></a>Paso 2: Expandir la implementación para que suene n + 1

Cuando esté seguro de haber configurado correctamente las reglas de ASR para el anillo 1, puede ampliar el ámbito de la implementación al siguiente anillo (anillo n + 1).

El proceso de implementación, pasos del 1 al 3, es esencialmente el mismo para cada anillo posterior:

1. Reglas de prueba en Auditoría
2. Revisar eventos de auditoría desencadenados por ASR en el portal de Microsoft 365 Defender web
3. Crear exclusiones
4. Revisión: refinar, agregar o quitar exclusiones según sea necesario
5. Establecer reglas en "bloquear"
6. Revise la página de informes en el Microsoft 365 Defender web.
7. Crear exclusiones.
8. Deshabilite las reglas problemáticas o vuelva a cambiarlas a Auditoría.

#### <a name="customize-attack-surface-reduction-rules"></a>Personalizar las reglas de la reducción de superficie expuesta a ataques

A medida que continúas expandiendo la implementación de las reglas de reducción de superficie de ataque, es posible que sea necesario o beneficioso personalizar las reglas de reducción de superficie de ataque que has habilitado.

##### <a name="exclude-files-and-folders"></a>Excluir archivos y carpetas

Puedes excluir archivos y carpetas para que no se evalúen mediante reglas de reducción de superficie de ataque. Cuando se excluye, no se bloqueará la ejecución del archivo incluso si una regla de reducción de superficie de ataque detecta que el archivo contiene comportamiento malintencionado.

Por ejemplo, considere la regla de ransomware:

La regla ransomware está diseñada para ayudar a los clientes empresariales a reducir los riesgos de ataques de ransomware al mismo tiempo que garantiza la continuidad del negocio. De forma predeterminada, los errores de la regla ransomware en el lado de la precaución y proteger contra archivos que aún no han alcanzado suficiente reputación y confianza. To reemphasize, the ransomware rule only triggers on files that have not gained enough positive reputation and prevalence, based on usage metrics of millions of our customers. Normalmente, los bloques se resuelven automáticamente, ya que los valores de "reputación y confianza" de cada archivo se actualizan incrementalmente a medida que aumenta el uso no problemático.

En los casos en los que los bloques no  se resuelven automáticamente de forma oportuna, los clientes pueden , bajo su propio riesgo, usar el mecanismo de autoservicio o una funcionalidad de "lista de permitidos" basada en indicador de compromiso (IOC) para desbloquear los propios archivos.

> [!WARNING]
> Excluir o desbloquear archivos o carpetas podría permitir potencialmente que los archivos no seguros se ejecuten e infecten los dispositivos. Excluir archivos o carpetas puede reducir considerablemente la protección proporcionada por las reglas de reducción de la superficie expuesta a ataques. Los archivos que se habrían bloqueado por una regla podrán ejecutarse y no se registrará ningún informe o evento.

La exclusión se aplica a todas las reglas que permiten exclusiones. Puede especificar un archivo individual, una ruta de acceso de carpeta o el nombre de dominio completo para un recurso. Sin embargo, no se puede limitar una exclusión a una regla específica.

Solo se aplica una exclusión cuando se inicia la aplicación o servicio excluidos. Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.

La reducción de superficie de ataque admite variables de entorno y caracteres comodín. Para obtener información acerca del uso de caracteres comodín, vea usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de [carpeta y nombre de archivo.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Si tiene problemas con las reglas que detectan archivos que cree que no deben detectarse, use el modo de auditoría [para probar la regla](evaluate-attack-surface-reduction.md).

Consulta el tema [de referencia de reglas de reducción de](attack-surface-reduction-rules-reference.md) superficie de ataque para obtener más información sobre cada regla.

##### <a name="use-group-policy-to-exclude-files-and-folders"></a>Usar la directiva de grupo para excluir archivos y carpetas

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** \>  \> **Protección contra vulnerabilidades de seguridad de Microsoft Defender** \> **reducción de superficie de ataque**.

4. Haga doble clic en la **configuración Excluir archivos y rutas** de acceso de las reglas de reducción de superficie de ataque y establezca la opción en **Habilitado**. Seleccione **Mostrar** e introduzca cada archivo o carpeta en la **columna Nombre de** valor. Escriba **0 en** la **columna Valor** de cada elemento.

> [!WARNING]
> No use comillas, ya que no son compatibles con la columna **Nombre de** valor o la **columna** Valor.

##### <a name="use-powershell-to-exclude-files-and-folders"></a>Usar PowerShell para excluir archivos y carpetas

1. Escriba **powershell** en el menú Inicio, haga clic con el botón secundario **en Windows PowerShell** y seleccione Ejecutar como **administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Siga usando para `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` agregar más carpetas a la lista.

    > [!IMPORTANT]
    > Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista. El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.

##### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Usar CSP mdm para excluir archivos y carpetas

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) para agregar exclusiones.

##### <a name="customize-the-notification"></a>Personalizar la notificación

Puedes personalizar la notificación para cuando se desencadena una regla y bloquea una aplicación o archivo. Consulte el [Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) artículo.

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Introducción a la implementación de reglas ASR](attack-surface-reduction-rules-deployment.md)

[Fase 1: Planear](attack-surface-reduction-rules-deployment-phase-1.md)

[Fase 2: Prueba](attack-surface-reduction-rules-deployment-phase-2.md)

[Fase 4: Operationalize](attack-surface-reduction-rules-deployment-phase-4.md)
