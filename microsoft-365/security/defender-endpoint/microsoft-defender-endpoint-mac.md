---
title: Microsoft Defender para endpoint en Mac
ms.reviewer: ''
description: Obtén información sobre cómo instalar, configurar, actualizar y usar Microsoft Defender para Endpoint en Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalación, implementación, desinstalación, intune, jamf, macos, monterey, big sur, catalina, mojave, mde para mac
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3943c5c9e477dc114b74d7f3f9a76b5b00119dd6
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587734"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender para endpoint en Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En este tema se describe cómo instalar, configurar, actualizar y usar Defender para Endpoint en Mac.

> [!CAUTION]
> Es probable que la ejecución de otros productos de protección de puntos de conexión de terceros junto con Microsoft Defender para Endpoint en Mac lleve a problemas de rendimiento y efectos secundarios impredecibles. Si la protección de extremo que no es de Microsoft es un requisito absoluto en su entorno, puede aprovechar de forma segura la funcionalidad de Defender para Endpoint en Mac EDR después de configurar la funcionalidad antivirus para que se ejecute en modo [pasivo.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>Novedades de la versión más reciente

[Novedades de Microsoft Defender para punto de conexión](whats-new-in-microsoft-defender-atp.md)

[Novedades de Microsoft Defender para Endpoint en Mac](mac-whatsnew.md)

> [!TIP]
> Si tienes algún comentario que quieras compartir, envíalo abriendo Microsoft Defender para Endpoint en Mac en el dispositivo y navegando a **Ayuda** para \> **enviar comentarios.**

Para obtener las características más recientes, incluidas las funcionalidades de vista previa (como detección y respuesta de puntos de conexión para los dispositivos Mac), configura el dispositivo macOS que ejecuta Microsoft Defender para Endpoint para que sea un dispositivo "Insider".

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Cómo instalar Microsoft Defender para Endpoint en Mac

### <a name="prerequisites"></a>Requisitos previos

- Una suscripción a Defender for Endpoint y acceso al portal de Microsoft 365 Defender web
- Experiencia de nivel principiante en scripting de macOS y BASH
- Privilegios administrativos en el dispositivo (en caso de implementación manual)

### <a name="installation-instructions"></a>Instrucciones de instalación

Existen varios métodos y herramientas de implementación que puedes usar para instalar y configurar Defender para Endpoint en Mac.

- Herramientas de administración de terceros:
    - [Implementación basada en Microsoft Intune](mac-install-with-intune.md)
    - [Implementación basada en JAMF](mac-install-with-jamf.md)
    - [Otros productos MDM](mac-install-with-other-mdm.md)

- Herramienta de línea de comandos:
    - [Implementación manual](mac-install-manually.md)

### <a name="system-requirements"></a>Requisitos del sistema

Se admiten las tres versiones principales más recientes de macOS.

> [!IMPORTANT]
> En macOS 11 (Big Sur) y posteriores, Microsoft Defender para Endpoint requiere perfiles de configuración adicionales. Si es un cliente existente que actualiza desde versiones anteriores de macOS, asegúrese de implementar los perfiles de configuración adicionales enumerados en Nuevos perfiles de configuración para [macOS Catalina](mac-sysext-policies.md)y versiones más recientes de macOS .

- 12 (Monterrey), 11 (Big Sur), 10,15 (Catalina), 10,14 (Mojave)
- Espacio en disco: 1 GB

No se admiten versiones beta de macOS.

La compatibilidad con dispositivos macOS con procesadores basados en chip M1 se ha admitido oficialmente desde la versión 101.40.84 del agente.

Después de habilitar el servicio, es posible que deba configurar la red o el firewall para permitir conexiones salientes entre él y los puntos de conexión.

### <a name="licensing-requirements"></a>Requisitos de licencias

Microsoft Defender para Endpoint en Mac requiere una de las siguientes ofertas de licencias por volumen de Microsoft:

- Microsoft 365 E5 (M365 E5)
- Seguridad de Microsoft 365 E5
- Microsoft 365 A5 (M365 A5)
- Windows 10 Enterprise E5
- Windows 11
- Microsoft Defender para punto de conexión

> [!NOTE]
> Los usuarios con licencia elegibles pueden usar Microsoft Defender para Endpoint en hasta cinco dispositivos simultáneos.
> Microsoft Defender para endpoint también está disponible para la compra desde un Proveedor de soluciones en la nube (CSP). Cuando se compra a través de un CSP, no requiere ofertas de licencias por volumen de Microsoft enumeradas.

### <a name="configuring-exclusions"></a>Configuración de exclusiones

Al agregar exclusiones a Microsoft Defender, debes tener en cuenta los errores de [exclusión comunes para Antivirus de Microsoft Defender](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>Conexiones de red

En la siguiente hoja de cálculo descargable se enumeran los servicios y sus direcciones URL asociadas a las que la red debe poder conectarse. Debe asegurarse de que no hay reglas de filtrado de red o firewall que denieguen el acceso *a* estas direcciones URL, o puede que necesite crear una regla de permitir específicamente para ellas.

|Hoja de cálculo de la lista de dominios|Descripción|
|---|---|
|![Imagen digital de la hoja de cálculo de direcciones URL de Microsoft Defender para puntos de conexión.](images/mdatp-urls.png)|Hoja de cálculo de registros DNS específicos para ubicaciones de servicio, ubicaciones geográficas y sistema operativo. <p> Descargue la hoja de cálculo aquí: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).

Microsoft Defender para endpoint puede detectar un servidor proxy mediante los siguientes métodos de detección:

- Proxy autoconfig (PAC)
- Protocolo de detección automática de proxy web (WPAD)
- Configuración manual de proxy estático

Si un proxy o firewall bloquea el tráfico anónimo, asegúrese de que el tráfico anónimo está permitido en las direcciones URL enumeradas anteriormente.

> [!WARNING]
> No se admiten servidores proxy autenticados. Asegúrese de que solo se usa PAC, WPAD o un proxy estático.
>
> Los servidores proxy de inspección e interceptación de SSL tampoco se admiten por motivos de seguridad. Configure una excepción para que la inspección SSL y el servidor proxy pasen directamente los datos de Microsoft Defender para endpoint en macOS a las direcciones URL relevantes sin interceptación. Agregar el certificado de interceptación al almacén global no permitirá la interceptación.

Para probar que una conexión no está bloqueada, abra <https://x.cp.wd.microsoft.com/api/report> y <https://cdn.x.cp.wd.microsoft.com/ping> en un explorador.

Si prefiere la línea de comandos, también puede comprobar la conexión ejecutando el siguiente comando en Terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

El resultado de este comando debe ser similar al siguiente:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> Se recomienda mantener la Protección de [integridad del](https://support.apple.com/HT204899) sistema (SIP) habilitada en dispositivos cliente. SIP es una característica de seguridad de macOS integrada que evita la manipulación de bajo nivel con el sistema operativo y está habilitada de forma predeterminada.

Una vez instalado Microsoft Defender para endpoint, la conectividad se puede validar ejecutando el siguiente comando en Terminal:

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Cómo actualizar Microsoft Defender para Endpoint en Mac

Microsoft publica periódicamente actualizaciones de software para mejorar el rendimiento, la seguridad y ofrecer nuevas características. Para actualizar Microsoft Defender para Endpoint en Mac, se usa un programa denominado Microsoft AutoUpdate (MAU). Para obtener más información, vea [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Cómo configurar Microsoft Defender para endpoint en Mac

Las instrucciones sobre cómo configurar el producto en entornos empresariales están disponibles en Establecer preferencias para [Microsoft Defender para Endpoint en Mac](mac-preferences.md).

## <a name="macos-kernel-and-system-extensions"></a>Extensiones de kernel y sistema de macOS

En alineación con la evolución de macOS, estamos preparando una actualización de Microsoft Defender para Endpoint en Mac que aprovecha las extensiones del sistema en lugar de las extensiones de kernel. Para obtener información relevante, consulta [Novedades de Microsoft Defender para Endpoint en Mac](mac-whatsnew.md).

## <a name="resources"></a>Recursos

- Para obtener más información sobre el registro, la desinstalación u otros temas, vea [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).
- [Privacidad de Microsoft Defender para Endpoint en Mac](mac-privacy.md).
