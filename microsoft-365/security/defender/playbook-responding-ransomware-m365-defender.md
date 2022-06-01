---
title: Respuesta a ataques de ransomware
description: En este artículo se proporciona un cuaderno de estrategias generalizado para responder a ataques de ransomware.
search.appverid: MET150
author: nic-name
ms.author: noriordan
manager: dolmont
audience: ITPro
ms.topic: article
ms.date: 05/30/2022
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection: M365-security-compliance
f1.keywords: NOCSH
ms.openlocfilehash: a7c03947cc159ed9933854c9fd1041af63c3f55c
ms.sourcegitcommit: aff1732dfa21e9283b173d8e5ca5bcbeeaaa26d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65811185"
---
# <a name="responding-to-ransomware-attacks"></a>Respuesta a ataques de ransomware

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Cuando sospeche que estaba o está actualmente bajo un ataque de ransomware, establezca comunicaciones seguras con el equipo de respuesta a incidentes inmediatamente. Pueden realizar las siguientes fases de respuesta para interrumpir el ataque y mitigar el daño:

* Investigación y contención
* Erradicación y recuperación

En este artículo se proporciona un cuaderno de estrategias generalizado para responder a ataques de ransomware. Considere la posibilidad de adaptar los pasos y tareas descritos en este artículo a su propio cuaderno de estrategias de operaciones de seguridad.
NOTA: Para obtener información sobre la prevención de ataques de ransomware, vea [Rápidamente proteger contra ransomware y extorsión](/security/compass/protect-against-ransomware).

## <a name="containment"></a>Contención

La contención y la investigación deben producirse lo más simultáneamente posible; sin embargo, debe centrarse en lograr rápidamente la contención, por lo que tiene más tiempo para investigar. Estos pasos le ayudan a determinar el ámbito del ataque y a aislarlo solo a entidades afectadas, como cuentas de usuario y dispositivos.

### <a name="step-1-assess-the-scope-of-the-incident"></a>Paso 1: Evaluar el ámbito del incidente

Ejecute esta lista de preguntas y tareas para detectar la extensión del ataque. Microsoft 365 Defender puede proporcionar una vista consolidada de todos los recursos afectados o en riesgo para ayudar en la evaluación de la respuesta a incidentes. Consulte [Respuesta a incidentes con Microsoft 365 Defender | Microsoft Docs](/incidents-overview.md). Puede usar las alertas y la lista de pruebas del incidente para determinar:

* ¿Qué cuentas de usuario pueden estar en peligro?
  * ¿Qué cuentas se usaron para entregar la carga útil?
* ¿Qué dispositivos [incorporados](../defender-endpoint/investigate-machines.md) y [detectados](../defender-endpoint/device-discovery.md) se ven afectados y cómo?
  * Dispositivos de origen
  * Dispositivos afectados
  * Dispositivos sospechosos
* Identifique cualquier comunicación de red asociada al incidente.
* ¿Qué aplicaciones se ven afectadas?
* ¿Qué cargas se han distribuido?
* ¿Cómo se comunica el atacante con los dispositivos en peligro? (La protección de red debe estar [habilitada](../defender-endpoint/enable-network-protection.md)):
  * Vaya a la [página indicadores](../defender-endpoint/indicator-ip-domain.md#create-indicators-for-ips-and-urlsdomains) para agregar un bloque para la dirección IP y la dirección URL (si tiene esa información).
* ¿Cuál era el medio de entrega de carga útil?

### <a name="step-2-preserve-existing-systems"></a>Paso 2: Conservación de sistemas existentes

Ejecute esta lista de tareas y preguntas para proteger los sistemas existentes frente a ataques:

* Si tiene copias de seguridad en línea, considere la posibilidad de desconectar el sistema de copia de seguridad de la red hasta que esté seguro de que el ataque está contenido, consulte [Backup and restore plan to protect against ransomware | Microsoft Docs](/security/compass/backup-plan-to-protect-against-ransomware).
* Si está experimentando o espera una implementación de ransomware inminente y activa:
  * [Suspenda las cuentas con privilegios y locales](/investigate-users.md) que sospecha que forman parte del ataque. Puede hacerlo desde la pestaña **Usuarios** de las propiedades del incidente en el portal de Microsoft 365 Defender.
  * Detenga todas [las sesiones de inicio de sesión remoto](/defender-for-identity/playbook-domain-dominance).
  * Restablezca las contraseñas de cuenta de usuario en peligro y exija a los usuarios de cuentas de usuario en peligro que vuelvan a iniciar sesión.
  * Haga lo mismo con las cuentas de usuario que puedan estar en peligro.
  * Si las cuentas locales compartidas están en peligro, haga que el administrador de TI le ayude a aplicar un cambio de contraseña en todos los dispositivos expuestos. Ejemplo Kusto consulta:

```kusto
DeviceLogonEvents | where DeviceName  contains (AccountDomain) | take 10 
```

* Para los dispositivos que aún no están aislados y no forman parte de la infraestructura crítica:
  * Aísle los dispositivos en peligro de la red, pero no los apague.
  * Si identifica los dispositivos de origen o de dispersión, aíslelos primero.
* Conservar los sistemas en peligro para su análisis.

### <a name="step-3-prevent-the-spread"></a>Paso 3: Impedir la propagación

Use esta lista para evitar que el ataque se propague a entidades adicionales.

* Si se usan cuentas locales compartidas en el ataque, considere la posibilidad [de bloquear el uso remoto de cuentas locales](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/blocking-remote-use-of-local-accounts/ba-p/701042).
  * Kusto consulta de todos los inicios de sesión de red que son administradores locales:

```kusto
DeviceLogonEvents
| where IsLocalAdmin == true and AccountDomain == DeviceName
| extend IsLocalLogon = tobool(todynamic(AdditionalFields).IsLocalLogon)
| where IsLocalLogon==false
```

* Kusto consulta de inicios de sesión que no son RDP (más realistas para la mayoría de las redes):

```kusto
DeviceLogonEvents
| where IsLocalAdmin == true and AccountDomain == DeviceName and LogonType != 'RemoteInteractive'
| extend IsLocalLogon = tobool(todynamic(AdditionalFields).IsLocalLogon)
| where IsLocalLogon==false
```

* Ponga en cuarentena y agregue indicadores para los archivos infectados.
* Asegúrese de que la solución antivirus se puede configurar en su estado de protección óptimo. Para Antivirus de Microsoft Defender, esto incluye:
  * [La protección en tiempo real](../defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus.md) está habilitada.
  * [La protección contra alteraciones](../defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada. En el portal de Microsoft 365 Defender, seleccione **Configuración > Puntos de conexión > Características avanzadas > Protección contra alteraciones**.
  * Las reglas de [reducción de superficie expuesta a ataques (ASR)](../defender-endpoint/enable-attack-surface-reduction.md) están habilitadas.
  * [La protección en la nube](../defender-endpoint/enable-attack-surface-reduction.md) está habilitada.
* Deshabilite Exchange ActiveSync y Sincronización de OneDrive.
  * Para deshabilitar Exchange ActiveSync de un buzón de correo, consulte [Cómo deshabilitar Exchange ActiveSync para los usuarios de Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-exchange-activesync).
  * Para deshabilitar otros tipos de acceso a un buzón de correo, consulte:
    * [Habilite o deshabilite MAPI para un buzón](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).
    * [Habilite o deshabilite el acceso POP3 o IMAP4 para un usuario](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access).
  * Pausar Sincronización de OneDrive ayudará a proteger los datos en la nube de que los dispositivos potencialmente infectados actualicen los datos en la nube. Para obtener más información, vea [Pausar y reanudar la sincronización en OneDrive](https://support.microsoft.com/office/how-to-pause-and-resume-sync-in-onedrive-2152bfa4-a2a5-4d3a-ace8-92912fb4421e).
* Aplique las revisiones y los cambios de configuración pertinentes en los sistemas afectados.
* Bloquear las comunicaciones de ransomware mediante controles internos y externos.
* Purgar contenido almacenado en caché

## <a name="investigation"></a>Investigación

Use esta sección para investigar el ataque y planear la respuesta.

### <a name="assess-your-current-situation"></a>Evaluación de la situación actual

* ¿Qué inicialmente le hizo consciente del ataque ransomware?
  * Si el personal de TI identificó la amenaza inicial, como la eliminación de copias de seguridad, las alertas antivirus, las alertas de detección y respuesta de puntos de conexión (EDR) o los cambios sospechosos del sistema, a menudo es posible tomar medidas decisivas rápidas para frustrar el ataque, normalmente por las acciones de contención descritas en este artículo.
* ¿Qué fecha y hora se enteró por primera vez del incidente?
  * ¿Qué actualizaciones del sistema y de seguridad no se instalaron en los dispositivos en esa fecha? Esto es importante para comprender qué vulnerabilidades podrían haberse aprovechado para que se puedan abordar en otros dispositivos.
  * ¿Qué cuentas de usuario se usaron en esa fecha?
  * ¿Qué nuevas cuentas de usuario se crearon desde esa fecha?
  * ¿Qué programas se agregaron para iniciarse automáticamente alrededor del momento en que se produjo el incidente?
* ¿Hay alguna indicación de que el atacante está accediendo actualmente a los sistemas?
  * ¿Hay algún sistema en peligro sospechoso que esté experimentando una actividad inusual?
  * ¿Hay sospechas de cuentas en peligro que parezcan ser utilizadas activamente por el adversario?
  * ¿Hay alguna evidencia de servidores de comando y control activos (C2) en EDR, firewall, VPN, proxy web y otros registros?

### <a name="identify-the-ransomware-process"></a>Identificar el proceso de ransomware

* Mediante la [búsqueda avanzada](/microsoft-365/security/defender/advanced-hunting-overview.md), busque el proceso identificado en los eventos de creación de procesos en otros dispositivos.

### <a name="look-for-exposed-credentials-in-the-infected-devices"></a>Buscar credenciales expuestas en los dispositivos infectados

* En el caso de las cuentas de usuario cuyas credenciales podrían estar en peligro, restablezca las contraseñas de cuenta y exija a los usuarios que vuelvan a iniciar sesión.
* Las siguientes E/SA pueden indicar el movimiento lateral:

<details>
  <summary>Haga clic para expandir</summary>

* SuspiciousExploratoryCommands
* MLFileBasedAlert
* IfeoDebuggerPersistence
* SuspiciousRemoteFileDropAndExecution
* ExploratoryWindowsCommands
* IoaStickyKeys
* Amplificador de Mimikatz Defender
* Herramienta de examen de red usada por PARINACOTA
* DefenderServerAlertMSSQLServer
* SuspiciousLowReputationFileDrop
* SuspiciousServiceExecution
* AdminUserAddition
* MimikatzArtifactsDetector
* Scuba-WdigestEnabledToAccessCredentials
* DefenderMalware
* MLSuspCmdBehavior
* MLSuspiciousRemoteInvocation
* SuspiciousRemoteComponentInvocation
* SuspiciousWmiProcessCreation
* MLCmdBasedWithRemoting
* Lsass de accesos de proceso
* Ejecución sospechosa del proceso rundll32
* BitsAdmin
* DefenderCobaltStrikeDetection
* DefenderHacktool
* IoaSuspPSCommandline
* Metasploit
* MLSuspToolBehavior
* RegistryQueryForPasswords
* SuspiciousWdavExclusion
* ASEPRegKey
* CobaltStrikeExecutionDetection
* DefenderBackdoor
* DefenderBehaviorSuspiciousActivity
* DefenderMalwareExecuted
* DefenderServerAlertDomainController
* DupTokenPrivilegeEscalationDetector
* FakeWindowsBinary
* IoaMaliciousCmdlets
* LivingOffTheLandBinary
* MicrosoftSignedBinaryAbuse
* MicrosoftSignedBinaryScriptletAbuse
* MLFileBasedWithRemoting
* MLSuspSvchostBehavior
* ReadSensitiveMemory
* RemoteCodeInjection-IREnabled
* Scuba-EchoSeenOverPipeOnLocalhost
* Scuba-SuspiciousWebScriptFileDrop
* Registro dll sospechoso por odbcconf
* Actividad de DPAPI sospechosa
* Ejecución sospechosa Exchange proceso
* Inicio de tarea programada sospechosa
* SuspiciousLdapQueryDetector
* SuspiciousScheduledTaskRegistration
* La aplicación que no es de confianza abre una conexión RDP

</details>

### <a name="identify-the-line-of-business-lob-apps-that-are-unavailable-due-to-the-incident"></a>Identificar las aplicaciones de línea de negocio (LOB) que no están disponibles debido al incidente

* ¿La aplicación requiere una identidad?
  * ¿Cómo se realiza la autenticación?
  * ¿Cómo se almacenan y administran credenciales como certificados o secretos?
* ¿Están disponibles las copias de seguridad evaluadas de la aplicación, su configuración y sus datos?
* Determine el proceso de recuperación en peligro.

## <a name="eradication-and-recovery"></a>Erradicación y recuperación

Siga estos pasos para erradicar la amenaza y recuperar los recursos dañados.

### <a name="step-1-verify-your-backups"></a>Paso 1: Comprobar las copias de seguridad

Si tiene copias de seguridad sin conexión, es probable que pueda restaurar los datos cifrados después de quitar la carga útil de ransomware (malware) de su entorno y después de comprobar que no hay acceso no autorizado en el inquilino de Microsoft 365.

### <a name="step-2-add-indicators"></a>Paso 2: Agregar indicadores

Agregue los canales de comunicación de atacante conocidos como indicadores, bloqueados en firewalls, en los servidores proxy y en los puntos de conexión.

### <a name="step-3-reset-compromised-users"></a>Paso 3: Restablecer usuarios en peligro

Restablezca las contraseñas de las cuentas de usuario en peligro conocidas y requiera un nuevo inicio de sesión.

* Considere la posibilidad de restablecer las contraseñas de cualquier cuenta con privilegios con una autoridad administrativa amplia, como los miembros del grupo Administradores de dominio.
* Si un atacante puede haber creado una cuenta de usuario, deshabilite la cuenta. No elimine la cuenta a menos que no haya planes para realizar análisis forenses de seguridad para el incidente.

### <a name="step-4-isolate-attacker-control-points"></a>Paso 4: Aislar los puntos de control del atacante

Aísle de Internet cualquier punto de control de atacante conocido dentro de la empresa.

### <a name="step-5-remove-malware"></a>Paso 5: Quitar malware

Quite el malware de los dispositivos afectados.

* Ejecute un examen antivirus completo y actual en todos los equipos y dispositivos sospechosos para detectar y quitar la carga que está asociada con el ransomware.
* No olvide examinar los dispositivos que sincronizan datos o los destinos de las unidades de red asignadas.

### <a name="step-6-recover-files-on-a-cleaned-device"></a>Paso 6: Recuperación de archivos en un dispositivo limpio

Recuperar archivos en un dispositivo limpio.

* Puede usar [el historial de](https://support.microsoft.com/help/17128) archivos en Windows 11, Windows 10, Windows 8.1 y Protección del sistema en Windows 7 para intentar recuperar los archivos y carpetas locales.

### <a name="step-7-recover-files-in-onedrive-for-business"></a>Paso 7: Recuperación de archivos en OneDrive para la Empresa

Recuperar archivos en OneDrive para la Empresa.

* Restauración de archivos en OneDrive para la Empresa permite restaurar un OneDrive completo a un momento dado anterior en los últimos 30 días. Para obtener más información, consulte [Restaurar su OneDrive](https://support.microsoft.com/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15).

### <a name="step-8-recover-deleted-email"></a>Paso 8: Recuperar correo electrónico eliminado

Recuperar correo electrónico eliminado.

* En el raro caso de que el ransomware eliminó todo el correo electrónico en un buzón de correo, puede recuperar los elementos eliminados. Consulte [Recuperación de mensajes eliminados en el buzón de correo de un usuario en Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages).

### <a name="step-9-re-enable-exchange-activesync-and-onedrive-sync"></a>Paso 9: Volver a habilitar Exchange ActiveSync y Sincronización de OneDrive

* Después de limpiar los equipos y dispositivos y recuperar los datos, puede volver a habilitar Exchange ActiveSync y Sincronización de OneDrive que ha deshabilitado anteriormente en el paso 3 de contención.
