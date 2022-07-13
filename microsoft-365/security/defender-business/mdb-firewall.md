---
title: Firewall en Microsoft Defender para Empresas
description: Obtenga información sobre la configuración de Firewall de Windows Defender en Defender para empresas. El firewall puede ayudar a evitar que el tráfico de red no deseado fluya a los dispositivos de la empresa.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: ce3c3ec98d45341544d146f6e614c3df048b3d90
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772913"
---
# <a name="firewall-in-microsoft-defender-for-business"></a>Firewall en Microsoft Defender para Empresas

Defender for Business incluye funcionalidades de firewall a través [de Firewall de Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). La protección del firewall ayuda a proteger los dispositivos mediante el establecimiento de reglas que determinan qué tráfico de red puede fluir hacia y desde los dispositivos.

Puede usar la protección del firewall para especificar si se permiten o bloquean las conexiones en los dispositivos de varias ubicaciones. Por ejemplo, la configuración del firewall puede permitir conexiones entrantes en dispositivos que están conectados a la red interna de la empresa, pero evitar las conexiones cuando el dispositivo está en una red con dispositivos que no son de confianza.

**En este artículo se describe**:

- [Configuración predeterminada del firewall en Defender para empresas](#default-firewall-settings-in-defender-for-business)
- [Configuración de firewall que puede configurar en Defender para empresas](#firewall-settings-you-can-configure-in-defender-for-business)


## <a name="default-firewall-settings-in-defender-for-business"></a>Configuración predeterminada del firewall en Defender para empresas

Defender for Business incluye directivas y configuraciones de firewall predeterminadas para ayudar a proteger los dispositivos de su empresa desde el primer día. En cuanto los dispositivos de la empresa se incorporen a Defender for Business, la directiva de firewall predeterminada funciona de la siguiente manera:

- Las conexiones salientes desde dispositivos se permiten de forma predeterminada, independientemente de la ubicación.
- Cuando los dispositivos están conectados a la red de la empresa, todas las conexiones entrantes se bloquean de forma predeterminada.
- Cuando los dispositivos están conectados a una red pública o a una red privada, todas las conexiones entrantes se bloquean de forma predeterminada.

En Defender para empresas, puede definir excepciones para bloquear o permitir conexiones entrantes. Estas excepciones se definen mediante la creación de reglas personalizadas. Consulte [Administración de reglas personalizadas para directivas de firewall](mdb-custom-rules-firewall.md).

## <a name="firewall-settings-you-can-configure-in-defender-for-business"></a>Configuración de firewall que puede configurar en Defender para empresas

Defender for Business incluye protección contra firewalls a través de Firewall de Windows Defender. En la tabla siguiente se enumeran los valores que se pueden configurar en Defender para empresas.

| Valor | Descripción |
|--|--|
| **Red de dominio** | El perfil de red de dominio se aplica a la red de su empresa. La configuración de firewall de la red de dominio se aplica a las conexiones entrantes que se inician en otros dispositivos de la misma red. De forma predeterminada, las conexiones entrantes se establecen en **Bloquear todo**.  |
| **Red pública** | El perfil de red pública se aplica a las redes que se pueden usar en una ubicación pública, como una cafetería o un aeropuerto. La configuración de firewall de las redes públicas se aplica a las conexiones entrantes que se inician en otros dispositivos de la misma red. Dado que una red pública puede incluir dispositivos que no conoce o en los que no confía, las conexiones entrantes se establecen en **Bloquear todo** de forma predeterminada.  |
| **Red privada** | El perfil de red privada se aplica a las redes de una ubicación privada, como su hogar. La configuración de firewall de las redes privadas se aplica a las conexiones entrantes que se inician en otros dispositivos de la misma red. En general, en una red privada, se supone que todos los demás dispositivos de la misma red son dispositivos de confianza. Sin embargo, de forma predeterminada, las conexiones entrantes se establecen en **Bloquear todo**. |
| **Reglas personalizadas** | [Las reglas personalizadas](mdb-custom-rules-firewall.md) permiten bloquear o permitir conexiones específicas. Por ejemplo, supongamos que desea bloquear todas las conexiones entrantes en los dispositivos que están conectados a una red privada, excepto las conexiones a través de una aplicación específica en un dispositivo. En este caso, establecería **Red privada** para bloquear todas las conexiones entrantes y, a continuación, agregaría una regla personalizada para definir la excepción. <p>Puede usar reglas personalizadas para definir excepciones para archivos o aplicaciones específicos, una dirección de protocolo de Internet (IP) o un intervalo de direcciones IP. En función del tipo de regla personalizada que esté creando, estos son algunos ejemplos de valores que podría usar:<ul><li>Ruta de acceso del archivo de aplicación: `C:\Windows\System\Notepad.exe or %WINDIR%\Notepad.exe`</li><li>IP: una dirección IPv4/IPv6 válida, como `192.168.11.0` o `192.168.1.0/24`</li><li>IP: intervalo de direcciones IPv4/IPv6 válido, con formato similar `192.168.1.0-192.168.1.9` (sin espacios incluidos)</li></ul> |

## <a name="next-steps"></a>Pasos siguientes

- [Administración de la configuración del firewall en Defender para empresas](mdb-custom-rules-firewall.md)
- [Más información sobre Firewall de Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)