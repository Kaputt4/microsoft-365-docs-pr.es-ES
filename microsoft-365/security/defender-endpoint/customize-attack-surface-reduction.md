---
title: Personalizar las reglas de la reducción de superficie expuesta a ataques
description: Establecer reglas individualmente en los modos de auditoría, bloquear o deshabilitados, y agregar archivos y carpetas que deben excluirse de las reglas de reducción de superficie de ataque
keywords: Reducción de superficie de ataque, hips, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, exploit, prevención de infecciones, personalizar, configurar, excluir
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6d2770dec270e2d1c1b9750387a0f07f82b357f9
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177098"
---
# <a name="customize-attack-surface-reduction-rules"></a>Personalizar las reglas de la reducción de superficie expuesta a ataques

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

[Las reglas de reducción de superficie de](enable-attack-surface-reduction.md) ataque ayudan a evitar comportamientos de software que a menudo se abusan para poner en peligro el dispositivo o la red. Por ejemplo, un atacante puede intentar ejecutar un script sin signo desde una unidad USB o hacer que una macro de un documento Office realice llamadas directamente a la API de Win32. Las reglas de reducción de superficie de ataque pueden restringir estos tipos de comportamientos de riesgo y mejorar la posición defensiva de la organización.

Aprende a personalizar las reglas [](#exclude-files-and-folders) de reducción [](#customize-the-notification) de superficie de ataques excluyendo archivos y carpetas o agregando texto personalizado a la alerta de notificación que aparece en el equipo de un usuario.

Puedes establecer reglas de reducción de superficie de ataque para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:

- Windows 10 Pro versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Servidor, [versión 1803 (canal semianual)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Puede usar la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP) de Administración de dispositivos móviles (MDM) para configurar estas opciones.

Consulta [Requisitos](enable-attack-surface-reduction.md#requirements) en el artículo "Habilitar reglas de reducción de superficie de ataque" para obtener información sobre los sistemas operativos compatibles y la información de requisitos adicional.

## <a name="exclude-files-and-folders"></a>Excluir archivos y carpetas

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

| Descripción de la regla | GUID |
|:----|:----|
| Bloquear el uso indebido de controladores firmados vulnerables explotados | `56a863a9-875e-4185-98a7-b882c64b5ce5` |
| Impedir que Adobe Reader cree procesos secundarios | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| Bloquear todas Office aplicaciones de creación de procesos secundarios | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe) | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| Bloquear la ejecución de archivos ejecutables a menos que cumplan con criterios de prevalencia, antigüedad o lista de confianza | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| Bloquear la ejecución de scripts potencialmente ofuscados | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| Impedir que JavaScript o VBScript inicien contenido ejecutable descargado | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| Bloquear Office aplicaciones de creación de contenido ejecutable | `3B576869-A4EC-4529-8536-B80A7769E899` |
| Bloquear Office aplicaciones para que no inyecten código en otros procesos | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| Bloquear Office aplicaciones de comunicación para que no creen procesos secundarios | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| Bloquear la persistencia a través de la suscripción de eventos WMI | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |
| Bloquear creaciones de proceso que se originen en comandos PSExec y WMI | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| Bloquear llamadas a la API de Win32 desde Office macro | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| Usar protección avanzada contra ransomware | `c1db55ab-c21a-4637-bb3f-a12568109d35` |

Consulta el tema [de reducción de](attack-surface-reduction.md) superficie de ataque para obtener más información sobre cada regla.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Usar la directiva de grupo para excluir archivos y carpetas

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender**  >    >  **Protección contra vulnerabilidades de seguridad de Microsoft Defender**  >  **reducción de superficie de ataque**.

4. Haga doble clic en la **configuración Excluir archivos y rutas** de acceso de las reglas de reducción de superficie de ataque y establezca la opción en **Habilitado**. Seleccione **Mostrar** e introduzca cada archivo o carpeta en la **columna Nombre de** valor. Escriba **0 en** la **columna Valor** de cada elemento.

> [!WARNING]
> No use comillas, ya que no son compatibles con la columna **Nombre de** valor o la **columna** Valor.

### <a name="use-powershell-to-exclude-files-and-folders"></a>Usar PowerShell para excluir archivos y carpetas

1. Escriba **powershell** en el menú Inicio, haga clic con el botón secundario **en Windows PowerShell** y seleccione Ejecutar como **administrador**
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Siga usando para `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` agregar más carpetas a la lista.

> [!IMPORTANT]
> Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista. El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Usar CSP mdm para excluir archivos y carpetas

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) para agregar exclusiones.

## <a name="customize-the-notification"></a>Personalizar la notificación

Puedes personalizar la notificación para cuando se desencadena una regla y bloquea una aplicación o archivo. Consulte el [Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) artículo.

## <a name="related-topics"></a>Temas relacionados

- [Reducir superficies de ataque con reglas de reducción de superficie de ataque](attack-surface-reduction.md)
- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
- [Evaluar las reglas de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
- [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
