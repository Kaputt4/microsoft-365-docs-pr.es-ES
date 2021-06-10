---
title: Escritorio administrado de Microsoft operaciones y supervisión
description: Quién lo que hace para varios procesos de cambio
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e56066f0b4e63fc9b73bbecf5aaa3180ffd2e4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920425"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Escritorio administrado de Microsoft operaciones y supervisión

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Administración de cambios

En un oferta de servicio, el equilibrio de las responsabilidades en lo relativo a aspectos como el mantenimiento del hardware y las actualizaciones de seguridad se inclina hacia el proveedor de servicios (Microsoft), en lugar de hacia el cliente (usted). Sin embargo, aún debe asegurarse de que el software que no sea de Microsoft y personalizado siga funcionando como se esperaba cuando se desaconsiguen las actualizaciones.

En el caso de los productos locales, la organización asume toda la responsabilidad de administrar los cambios.

### <a name="balance-of-responsibility"></a>Equilibrio de responsabilidades

Responsabilidad | Escritorio administrado de Microsoft servicio | Microsoft 365 cliente | Clientes y servidores locales | software personalizado y que no es de Microsoft
----- | ----- | ----- | ----- | -----
Proporciona nuevas funciones | Microsoft | Microsoft | Ambas | Clientes
Probar las características nuevas como control de calidad |  Microsoft | Microsoft | Ambas | Clientes
Comunicar las características nuevas | Ambas | Ambas | Ambas | Clientes
Integrar software personalizado | Ambas | Ambas | Clientes | Clientes
Aplicar las actualizaciones de seguridad | Microsoft | Microsoft | Clientes | Clientes
Mantener el software del sistema | Microsoft | Microsoft | Clientes | Clientes
Paquete para la implementación | Microsoft | Microsoft | Clientes | Clientes


### <a name="change-process-overview"></a>Introducción al proceso de cambio

Este es un resumen de cómo se comparte el proceso de cambio entre Microsoft y los clientes: 



<table>
<tr><th></th><th><p>Rol de Microsoft:</p></th><th><p>Rol del cliente:</p></th></tr>
<tr><td>Antes de un cambio</td><td><ul><li>Establecer las expectativas en relación con los cambios en el servicio.</li><li>Notifique a los clientes con 5 días de antelación los cambios que requieran una acción de administrador.</li><li>Para los cambios de emergencia, aplique una mitigación antes de notificar.</li></ul></td><td><ul><li>Comprender qué esperar de los cambios y las comunicaciones.</li><li>Lea Escritorio administrado de Microsoft de mensajes periódicamente.</li><li>Revisar y actualizar los procesos de administración de cambios internos.</li><li>Comprender y comprobar el cumplimiento de Escritorio administrado de Microsoft requisitos. </li><li>Confirme y apruebe, cuando sea necesario.</li></ul></td></tr><tr><td>Durante un cambio</td><td><ul><li>Libere e implemente actualizaciones mensuales de seguridad y no de seguridad para Windows 10 y Office 365 clientes.</li><li>Supervisar las señales de datos y las colas de soporte técnico en busca de impacto.</li></ul></td><td><ul><li>Compruebe el centro Escritorio administrado de Microsoft mensajes y revise cualquier información adicional.</li><li>   Realizar cualquier acción necesaria, si procede, y probar aplicaciones.</li><li>Si se experimenta un escenario de interrupción o corrección, cree una solicitud de soporte técnico.</li></ul></td></tr><tr><td>Después de un cambio</td><td><ul><li>Recopila los comentarios de los clientes para mejorar la implementación de futuros cambios.</li><li>Supervisar las señales de datos y las colas de soporte técnico en busca de impacto.</li></ul></td><td><ul><li>Trabaje con personas de su organización para adoptar el cambio.</li><li>   Revise los procesos de administración de cambios y adopción para obtener oportunidades para obtener eficiencias.</li><li>Proporcionar comentarios generales y comentarios específicos en la herramienta de comentarios del administrador.</li><li>Entrena a los usuarios para que proporcionen comentarios específicos de la aplicación mediante el Centro de opiniones sobre Windows y el botón Smile en Office aplicaciones.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de cambio

Hay varios tipos de cambios que se hacen en el servicio con regularidad. El canal de comunicación de esos cambios y las acciones de las que es responsable varía.

No todos los cambios afectan igual a los usuarios o requieren acciones. Algunas están planeadas y otras no planeadas por su naturaleza (las actualizaciones no de seguridad y las actualizaciones de seguridad normalmente no están planeadas). Según el tipo de cambio, el canal de comunicación puede variar. En la tabla siguiente se enumeran los tipos de cambios que puede esperar para el Escritorio administrado de Microsoft servicio.

|   | Funcionalidad |   Actualizaciones que no son de seguridad |  Seguridad
--- | --- | --- | ---
**Tipo de cambio** | - Actualizaciones de características<br>- Nuevas características o aplicaciones<br>- Características en desuso | Revisiones de cliente para problemas | Actualizaciones de seguridad
**Comunicación con la antelación suficiente** | Aviso de cinco días para los cambios que requieren acción | No, estos cambios se incluyen en la versión mensual    | No, los cambios se incluyen en la versión mensual 
**Canal de comunicación** | - Centro de mensajes<br>- Alerta de correo electrónico | - Centro de mensajes<br>- Alerta de correo electrónico | - Centro de mensajes<br>- Alerta de correo electrónico
**Requiere acción de administrador global** | A veces |  Rara vez |    Rara vez 
**Tipo de acción** | Cambiar configuración | Comunicar los cambios a los usuarios | Cambiar la configuración de administración     
**Requiere pruebas** | Comprobar aplicaciones empresariales, incluidos los servicios de acceso remoto |  A veces: probar la corrección en relación con los procesos o las personalizaciones. |   De forma muy ocasional 
**Ejemplos de cambios** | - Actualizaciones de características: envío y revisión de vales de soporte simplificado del Portal de administración de TI<br>- Nuevas características o aplicaciones: Semi-Annual versión de una actualización Windows 10 características | Revisiones basadas en errores notificados por los clientes |  


## <a name="standard-operating-procedures"></a>Procedimientos operativos estándar

Microsoft Escritorio administrado de Microsoft implementar y operar el servicio en la nube de Microsoft, donde puede llevar a cabo otras actividades administrativas. Microsoft es el único responsable de Escritorio administrado de Microsoft configuración, configuración y operación específicas. 

En el caso de los productos locales, la organización asume toda la responsabilidad de administrar la configuración y las actividades operativas y de configuración.

Categorías |    Microsoft will | El cliente lo hará
--- | --- | ---
Red (proxy, inspección de paquetes, VPN)  | Aconsejar y planear con los clientes para minimizar los riesgos para los usuarios empresariales. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Solo aplique un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado.
Cuentas de servicio  |- Implementar, almacenar y administrar de forma segura las credenciales.<br> - Comunicar el acceso no autorizado o el uso de estas credenciales al equipo de operaciones de seguridad. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Solo aplique un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado.<br>- No asignar directivas, autenticación multifactor, acceso condicional o implementación de aplicaciones a las Escritorio administrado de Microsoft de servicio.<br>- No restablecer la contraseña ni usar las credenciales.<br>- Abra una solicitud de soporte técnico de Sev C para Escritorio administrado de Microsoft operaciones si se observa actividad sospechosa en los registros de auditoría de Intune o Azure, relacionados con estas cuentas de servicio.
Grupos de dispositivos | - Implementar y administrar la pertenencia de dispositivos dentro de Escritorio administrado de Microsoft grupos.<br>- Use los grupos Escritorio administrado de Microsoft para administrar la asignación y el lanzamiento de la configuración y las actualizaciones de los dispositivos. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Solo aplique un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado.<br>- No modificar la pertenencia de ningún Escritorio administrado de Microsoft grupo.<br>- Solo use los grupos para asignar certificados corporativos para servicios como VPN, Windows Hello para empresas o cifrado de correo electrónico, o configuración de perfiles Wi-Fi corporativo.<br>- Donde existe la administración en colaboración, excluya explícitamente todos los Escritorio administrado de Microsoft al implementar el cliente de Configuration Manager.
Directivas |  - Implementar y administrar las directivas de Escritorio administrado de Microsoft que rigen el estado de configuración de los dispositivos dentro del servicio.<br>- Implementar actualizaciones, en directivas o Windows, de forma incremental mediante grupos de dispositivos.<br> - Excluir explícitamente los grupos que no Escritorio administrado de Microsoft destino. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Solo aplique un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado.<br>- No editar ni asignar directivas Escritorio administrado de Microsoft a dispositivos o usuarios no administrados por el servicio Escritorio administrado de Microsoft usuario.
Microsoft Defender para punto de conexión | Supervisar e investigar dispositivos dentro del ámbito del Escritorio administrado de Microsoft servicio. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Aplicar solo un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado
Microsoft Store para Empresas |  Configure y mantenga el perfil Windows Autopilot para el Escritorio administrado de Microsoft servicio. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Solo aplique un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado.<br>- No modificar la configuración del perfil Escritorio administrado de Microsoft Windows Autopilot ni agregar o quitar dispositivos asignados.
Certificados | | - Crear una solicitud de soporte técnico 60 días antes de la expiración de un certificado, solicitando información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes que Microsoft debe revisar.<br>- Solo aplique un cambio una vez que Escritorio administrado de Microsoft Operations haya evaluado y recomendado.<br>- Actualice todos los certificados necesarios para configurar perfiles de certificado, perfiles VPN y Wi-Fi perfiles.




## <a name="device-wipe-with-factory-reset"></a>Borrado del dispositivo con restablecimiento de fábrica

El Escritorio administrado de Microsoft operaciones de mantenimiento puede realizar un restablecimiento de fábrica de los dispositivos inscritos en el servicio cuando sea necesario. El restablecimiento es útil si necesitas dar un dispositivo a un empleado diferente o si un empleado deja tu empresa. 

Existen algunos requisitos:

- El administrador global debe enviar una solicitud de servicio.
- Incluya el nombre del equipo del dispositivo en la solicitud.
- La cuenta de usuario debe estar en Azure AD antes de restablecer el dispositivo.

El equipo de operaciones de escritorio administrado hará lo siguiente:

- Buscar el nombre del dispositivo en Intune
- Enviar el comando de restablecimiento de fábrica al dispositivo

>[!NOTE]
>No quite la cuenta de usuario de Azure AD antes de restablecer el dispositivo. Si el usuario no está en Azure AD, Intune no puede enviar el comando de restablecimiento de fábrica al dispositivo. 

El dispositivo arrancará en la "experiencia de inicio" y todas las aplicaciones preinstaladas y la configuración se aplicarán de nuevo. El usuario del dispositivo debe proporcionar información de configuración inicial de nuevo. 

Cuando el dispositivo se haya restablecido, puedes dáslo a otra persona de la organización. Ninguno de los datos del usuario anterior ni los datos de empresa estarán en el dispositivo. El siguiente usuario pasará por el mismo proceso que hizo la persona anterior con un nuevo Escritorio administrado de Microsoft dispositivo.

BitLocker es un componente clave de la seguridad de datos en este proceso. Con BitLocker cifrado en Escritorio administrado de Microsoft dispositivos, los datos de la unidad permanecen seguros incluso después del restablecimiento de fábrica del dispositivo. Los datos que se encontraban en la unidad no estarán disponibles para el siguiente usuario del dispositivo. Para obtener más información, [vea BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obtener más información, consulta [Restablecimiento de fábrica de un dispositivo](/intune/remote-actions/devices-wipe#factory-reset-a-device).