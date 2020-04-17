---
title: Protección contra suplantación de identidad (phishing) en Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: Office 365 ofrece una amplia variedad de protección contra los ataques de suplantación de identidad de forma predeterminada y a través de características adicionales de Office 365 protección contra amenazas avanzada (ATP). En este tema se presentan los recursos en línea que se pueden usar para obtener información sobre cómo implementar las opciones y estrategias contra la suplantación de identidad (phishing) en Office 365.
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537430"
---
# <a name="anti-phishing-protection-in-office-365"></a>Protección contra suplantación de identidad (phishing) en Office 365

*Suplantación de identidad* : ataque de correo electrónico que intenta robar información confidencial en mensajes que parecen pertenecer a remitentes legítimos o de confianza. Hay categorías específicas de suplantación de identidad. Por ejemplo:

- La **suplantación de identidad (Spear phishing** ) usa contenido muy centrado y personalizado que está específicamente adaptado a los destinatarios de destino (normalmente, después del reconocimiento de los destinatarios por parte del atacante).

- **Whaling** se dirige a ejecutivos u otros objetivos de alto valor dentro de una organización para un efecto máximo.

- El **compromiso de correo electrónico empresarial (BEC)** utiliza remitentes de confianza falsificados (agentes financieros, clientes, asociados de confianza, etc.) en un esfuerzo por engañar al destinatario en la aprobación de pagos, la transferencia de fondos o la revelación de datos de clientes.

- **Ransomware** que cifra los datos y solicita el pago para descifrarlos casi siempre comienza en los mensajes de suplantación de identidad. La protección contra la suplantación de identidad (phishing) no puede ayudarle a descifrar archivos cifrados, pero puede ayudarle a detectar los mensajes de suplantación de identidad asociados con la campaña de ransomware. Para obtener más información acerca de cómo recuperarse de un ataque de ransomware, consulte [Recover from a ransomware Attack in Office 365](recover-from-ransomware.md).

Con la creciente complejidad de los ataques, es incluso difícil que los usuarios con formación puedan identificar sofisticados mensajes de suplantación de identidad. Afortunadamente, Exchange Online Protection (EOP) y las características adicionales de la protección contra amenazas avanzada (ATP) de Office 365 pueden resultarle útiles.

## <a name="anti-phishing-protection-in-eop"></a>Protección contra la suplantación de identidad en EOP

EOP (es decir, las organizaciones de Office 365 sin ATP) contiene características que pueden ayudar a proteger su organización de las amenazas de suplantación de identidad:

- **Inteligencia de identidad**: Revise los mensajes falsificados de remitentes en dominios internos y externos, y permita o bloquee a dichos remitentes. Para obtener más información, consulte [configurar inteligencia de identidades en Office 365](learn-about-spoof-intelligence.md).

- **Directiva antiphishing predeterminada**: activar o desactivar la inteligencia contra la suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y especificar la acción para los remitentes suplantados bloqueados (mover a la carpeta de correo no deseado o cuarentena). Para obtener más información, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

- **Autenticación de correo electrónico implícita**: EOP mejora las comprobaciones de autenticación de correo electrónico estándar para el correo electrónico entrante ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)) con la reputación del remitente, el historial del remitente, el historial del destinatario, el análisis del comportamiento y otras técnicas avanzadas para ayudar a identificar a los remitentes falsificados. Para obtener más información, consulte [autenticación de correo electrónico en Office 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Protección adicional contra suplantación de identidad en Office 365 ATP

Office 365 ATP contiene características adicionales y más avanzadas para la suplantación de identidad:

- **Directivas antiphishing de ATP**: cree nuevas directivas personalizadas, configure las opciones de anti-suplantación (proteger los usuarios y dominios de la suplantación), la configuración de inteligencia de buzones y los umbrales de suplantación de identidad avanzada ajustables. Para obtener más información, consulte [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md). Para obtener más información acerca de las diferencias entre las directivas antiphishing y las directivas contra la suplantación de identidad (phishing) de ATP, consulte [anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).

- **Vistas de campañas**: aprendizaje de máquina y otras heurísticas identifique y analice los mensajes relacionados con los ataques de suplantación de identidad coordinados de todo el servicio y su organización. Para obtener más información, vea [vistas de campañas en Office 365 ATP](campaigns.md).

- **Simulador de ataque**: los administradores pueden crear mensajes de suplantación de identidad falsos y enviarlos a los usuarios internos como una herramienta de educación. Para obtener más información, vea [simulador de ataque en Office 365 ATP](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Otros recursos contra la suplantación de identidad

- Para los usuarios finales: [Protéjase de las tramas de suplantación de identidad y otras formas de fraude en línea](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).

- [Cómo Office 365 valida la dirección de para evitar la suplantación de identidad (phishing)](how-office-365-validates-the-from-address.md).
