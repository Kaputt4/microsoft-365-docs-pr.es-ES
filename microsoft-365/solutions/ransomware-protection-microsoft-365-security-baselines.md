---
title: Paso 1. Configurar las líneas base de seguridad
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
ms.custom: seo-marvel-jun2020
keywords: ransomware, ransomware operado por humanos, ransomware operado por seres humanos, HumOR, ataque de extorsión, ataque ransomware, cifrado, criptovirología, confianza cero
description: Use las líneas base de seguridad para proteger los recursos de Microsoft 365 frente a ataques de ransomware.
ms.openlocfilehash: db1733e326de45597b0b69638bb2033e7e8892be
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986034"
---
# <a name="step-1-configure-security-baselines"></a>Paso 1. Configurar las líneas base de seguridad

Como primer paso para combatir a los atacantes de ransomware, debe configurar las siguientes líneas base de seguridad definidas por Microsoft:

- [Seguridad de Microsoft 365](#microsoft-365-security-baseline)
- [Administración del correo de Exchange](#exchange-email-management-baseline)
- [Líneas base adicionales para dispositivos Windows y software cliente](#additional-baselines)

Estas líneas base contienen opciones de configuración y reglas conocidas por los atacantes, cuya ausencia se detecta rápidamente y se aprovecha con frecuencia.

## <a name="microsoft-365-security-baseline"></a>Línea base de seguridad de Microsoft 365

En primer lugar, evalúe y mida su posición de seguridad mediante la [Puntuación de seguridad de Microsoft](/microsoft-365/security/defender/microsoft-secure-score) y siga las instrucciones para mejorarla según sea necesario.

Next, use [attack surface reduction rules](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-deployment) to help block suspicious activity and vulnerable content. These rules include preventing:

- Las aplicaciones de Office creen procesos secundarios
- El contenido ejecutable del cliente de correo electrónico y el correo web
- La ejecución de archivos ejecutables, excepto si cumplen un criterio de prevalencia, antigüedad o lista de confianza
- La ejecución de scripts potencialmente confusos
- JavaScript o VBScript inicien contenido ejecutable descargado
- Las aplicaciones de Office creen contenido ejecutable
- Las aplicaciones de Office inyecten código en otros procesos
- La aplicación de comunicación de Office cree procesos secundarios
- Se ejecuten desde una unidad USB procesos no firmados y que no sean de confianza
- La persistencia a través de la suscripción de eventos de Interfaz de Administración de Windows (WMI)
- El hurto de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)
- La creación de procesos procedentes de comandos de PSExec y WMI

## <a name="exchange-email-management-baseline"></a>Línea base de administración de correo electrónico de Exchange

Ayude a evitar el acceso inicial a su espacio empresarial desde un ataque basado en correo electrónico con esta configuración de línea base de correo electrónico de Exchange:

- Habilite el [examen de correo por parte del Antivirus de Windows Defender](/microsoft-365/security/defender-endpoint/configure-advanced-scan-types-microsoft-defender-antivirus).
- Use Microsoft Defender para Office 365 para [mejorar la protección contra suplantación de identidad](/microsoft-365/security/office-365-security/anti-phishing-protection) y la cobertura contra nuevas amenazas y variantes polimórficas.
- Compruebe la configuración de filtrado de correo electrónico de Office 365 para asegurarse de bloquear correos electrónicos falsificados, correo no deseado y correos electrónicos con malware. Use Defender para Office 365 para mejorar la protección contra suplantación de identidad (phishing) y la cobertura contra nuevas amenazas y variantes polimórficas. Configure Defender para Office 365 para [volver a comprobar los vínculos al hacer clic](/microsoft-365/security/office-365-security/atp-safe-links) y [eliminar los correos entregados](/microsoft-365/security/office-365-security/zero-hour-auto-purge) en respuesta a la inteligencia de amenazas recién adquirida.
- Revise y actualice a la [configuración recomendada más reciente para la de seguridad de EOP y Defender para Office 365](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp).
- Configure Defender para Office 365 para [volver a comprobar los vínculos al hacer clic](/microsoft-365/security/office-365-security/set-up-safe-links-policies) y eliminar los correos entregados en respuesta a la inteligencia de amenazas recién adquirida.

## <a name="additional-baselines"></a>Líneas base adicionales

Aplique [líneas base de seguridad](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/bg-p/Microsoft-Security-Baselines) para lo siguiente:

- Microsoft Windows 11 o 10
- Aplicaciones de Microsoft 365 para empresas
- Microsoft Edge

## <a name="impact-on-users-and-change-management"></a>Impacto en los usuarios y administración de cambios

Como procedimiento recomendado para una regla de reducción de superficie expuesta a ataques, evalúe cómo podría afectar una regla a la red abriendo la recomendación de seguridad para esa regla en Administración de vulnerabilidades de Defender. El panel de detalles de la recomendación describe el impacto en el usuario, que puede usar para determinar qué porcentaje de los dispositivos pueden aceptar una nueva directiva que habilita la regla en modo de bloqueo sin afectar negativamente a la productividad del usuario.

Además, la configuración de línea base de correo electrónico de Exchange puede bloquear el correo electrónico entrante e impedir el envío de correo electrónico o el hacer clic en vínculos dentro del correo electrónico. Informe a sus trabajadores sobre este comportamiento y el motivo por el que se toman estas precauciones.

## <a name="resulting-configuration"></a>Configuración resultante

Esta es la protección contra ransomware para el espacio empresarial después de este paso.

![Protección contra ransomware para su espacio empresarial de Microsoft 365 después del paso 1](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture-step1.png)

## <a name="next-step"></a>Paso siguiente

[![Paso 2 para la protección contra ransomware con Microsoft 365](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step2.png)](ransomware-protection-microsoft-365-attack-detection-response.md)

Continúe con el [Paso 2](ransomware-protection-microsoft-365-attack-detection-response.md) para implementar funcionalidades de detección y respuesta contra ataques para su espacio empresarial de Microsoft 365.
