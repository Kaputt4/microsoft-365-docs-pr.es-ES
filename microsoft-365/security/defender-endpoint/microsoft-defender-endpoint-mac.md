---
title: Microsoft Defender para punto de conexión en Mac
ms.reviewer: ''
description: Obtenga información sobre cómo instalar, configurar, actualizar y usar Microsoft Defender para punto de conexión en Mac.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, deploy, uninstallation, intune, jamf, macos, monterey, big sur, catalina, mojave, mde for mac
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d6438c7af3d3dbb8f4b2c19fdfdd04640cc8b4d2
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174978"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender para punto de conexión en Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Defender para punto de conexión en Mac.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para punto de conexión en Mac genere problemas de rendimiento y efectos secundarios impredecibles. Si la protección de puntos de conexión que no son de Microsoft es un requisito absoluto en su entorno, puede aprovechar de forma segura la funcionalidad de Defender para punto de conexión en Mac EDR después de configurar la funcionalidad antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enforcement-level-for-antivirus-engine).

## <a name="whats-new-in-the-latest-release"></a>Novedades de la versión más reciente

[Novedades de Microsoft Defender para punto de conexión](whats-new-in-microsoft-defender-endpoint.md)

[Novedades de Microsoft Defender para punto de conexión en Mac](mac-whatsnew.md)

> [!TIP]
> Si tiene algún comentario que le gustaría compartir, envíelo abriendo Microsoft Defender para punto de conexión en Mac en el dispositivo y navegando a **Ayuda** \> **para enviar comentarios**.

Para obtener las características más recientes, incluidas las funcionalidades de versión preliminar (como detección y respuesta de puntos de conexión para los dispositivos Mac), configure el dispositivo macOS que ejecuta Microsoft Defender para punto de conexión para que sea un dispositivo "Insider".

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Instalación de Microsoft Defender para punto de conexión en Mac

### <a name="prerequisites"></a>Requisitos previos

- Una suscripción de Defender para punto de conexión y acceso al portal de Microsoft 365 Defender
- Experiencia de nivel principiante en scripts de macOS y BASH
- Privilegios administrativos en el dispositivo (en caso de implementación manual)

### <a name="installation-instructions"></a>Instrucciones de instalación

Hay varios métodos y herramientas de implementación que puede usar para instalar y configurar Defender para punto de conexión en Mac.

- Herramientas de administración de terceros:
    - [Implementación basada en Microsoft Intune](mac-install-with-intune.md)
    - [Implementación basada en JAMF](mac-install-with-jamf.md)
    - [Otros productos MDM](mac-install-with-other-mdm.md)

- Herramienta de línea de comandos:
    - [Implementación manual](mac-install-manually.md)

### <a name="system-requirements"></a>Requisitos del sistema

Se admiten las tres versiones principales más recientes de macOS.

> [!IMPORTANT]
> En macOS 11 (Big Sur) y versiones posteriores, Microsoft Defender para punto de conexión requiere perfiles de configuración adicionales. Si es un cliente existente que actualiza desde versiones anteriores de macOS, asegúrese de implementar los perfiles de configuración adicionales que aparecen en [Nuevos perfiles de configuración para macOS Catalina y versiones más recientes de macOS](mac-sysext-policies.md).

- 12 (Monterrey), 11 (Big Sur), 10.15 (Catalina)
- Espacio en disco: 1 GB

No se admiten las versiones beta de macOS.

La compatibilidad con dispositivos macOS con procesadores basados en chip M1 se ha admitido oficialmente desde la versión 101.40.84 del agente.

Después de habilitar el servicio, es posible que tenga que configurar la red o el firewall para permitir las conexiones salientes entre él y los puntos de conexión.

### <a name="licensing-requirements"></a>Requisitos de licencias

Microsoft Defender para punto de conexión en Mac requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

- Microsoft 365 E5 (M365 E5)
- Seguridad de Microsoft 365 E5
- Microsoft 365 A5 (M365 A5)
- Windows 10 Enterprise E5
- Microsoft 365 Empresa Premium
- Windows 11 Empresas E5
- Microsoft Defender para punto de conexión

> [!NOTE]
> Los usuarios con licencia aptos pueden usar Microsoft Defender para punto de conexión en hasta cinco dispositivos simultáneos.
> Microsoft Defender para punto de conexión también está disponible para su compra en un Proveedor de soluciones en la nube (CSP). Cuando se compra a través de un CSP, no requiere ofertas de licencias por volumen de Microsoft enumeradas.

### <a name="configuring-exclusions"></a>Configuración de exclusiones

Al agregar exclusiones, tenga en cuenta los [errores comunes de exclusión de Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus).

### <a name="network-connections"></a>Conexiones de red

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Debe asegurarse de que no haya reglas de filtrado de red o de firewall que denieguen el acceso a estas direcciones URL, o puede que tenga que crear una regla *de permiso* específicamente para ellas.


|Hoja de cálculo de la lista de dominios| Descripción|
|---|---|
|Microsoft Defender para punto de conexión lista de direcciones URL para clientes comerciales| Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes comerciales. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender para punto de conexión lista de direcciones URL de Gov/GCC/DoD | Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo para clientes de Gov/GCC/DoD. <p> [Descargue la hoja de cálculo aquí.](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Microsoft Defender para punto de conexión puede detectar un servidor proxy mediante los métodos de detección siguientes:

- Configuración automática de proxy (PAC)
- Protocolo de detección automática de proxy web (WPAD)
- Configuración de proxy estático manual

Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que se permite el tráfico anónimo en las direcciones URL enumeradas anteriormente.

> [!WARNING]
> No se admiten servidores proxy autenticados. Asegúrese de que solo se usa PAC, WPAD o un proxy estático.
>
> Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para la inspección SSL y el servidor proxy para pasar directamente los datos de Microsoft Defender para punto de conexión en macOS a las direcciones URL pertinentes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.

Para probar que una conexión no está bloqueada, abra <https://x.cp.wd.microsoft.com/api/report> y <https://cdn.x.cp.wd.microsoft.com/ping> en un explorador.

Si prefiere la línea de comandos, también puede comprobar la conexión ejecutando el siguiente comando en Terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

La salida de este comando debe ser similar a la siguiente:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> Se recomienda mantener la [protección de integridad del sistema](https://support.apple.com/HT204899) (SIP) habilitada en los dispositivos cliente. SIP es una característica de seguridad integrada de macOS que evita la manipulación de bajo nivel con el sistema operativo y está habilitada de forma predeterminada.

Una vez instalado Microsoft Defender para punto de conexión, la conectividad se puede validar ejecutando el siguiente comando en Terminal:

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Actualización de Microsoft Defender para punto de conexión en Mac

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características. Para actualizar Microsoft Defender para punto de conexión en Mac, se usa un programa denominado Microsoft AutoUpdate (MAU). Para más información, consulte [Implementación de actualizaciones para Microsoft Defender para punto de conexión en Mac](mac-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Configuración de Microsoft Defender para punto de conexión en Mac

Las instrucciones para configurar el producto en entornos empresariales están disponibles en [Establecer preferencias para Microsoft Defender para punto de conexión en Mac](mac-preferences.md).

## <a name="macos-kernel-and-system-extensions"></a>extensiones de sistema y kernel de macOS

A partir de macOS 11 (Big Sur), Microsoft Defender para punto de conexión se ha migrado completamente de la extensión del kernel a las extensiones del sistema. La extensión kernel se sigue usando en macOS 10.15 (Catalina).

## <a name="resources"></a>Recursos

- Para obtener más información sobre el registro, la desinstalación u otros temas, consulte [Recursos para Microsoft Defender para punto de conexión en Mac](mac-resources.md).
- [Privacidad para Microsoft Defender para punto de conexión en Mac](mac-privacy.md).
