---
title: Las operaciones de escritorio de Microsoft administrado y supervisión
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871333"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Las operaciones de escritorio de Microsoft administrado y supervisión

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Administración de cambios

Microsoft y los clientes a compartir administración de cambios para el servicio de escritorio administrado de Microsoft. Responsabilidades difieren para un servicio en línea frente a un servidor local o cliente. 

### <a name="change-process-overview"></a>Información general sobre el proceso de cambio

Éste es un resumen de cómo el proceso de cambio se comparte entre Microsoft y los clientes. 



<table>
<tr><th></th><th><p>Microsoft hará lo siguiente:</p></th><th><p>Los clientes hará lo siguiente:</p></th></tr>
<tr><td>Antes de un cambio</td><td><ul><li>Notificar a los clientes 5 días por adelantado para que los cambios que requieren la acción del administrador.</li><li>Cambios de emergencia, aplicar una mitigación antes de la notificación.</li></ul></td><td><ul><li>Leer y comprender el correo electrónico de notificación.</li><li>Confirmar y aprobar, cuando sea necesario.</li></ul></td></tr><tr><td>Durante un cambio</td><td><ul><li>Implementar cambio para 10 de Windows y Office, la versión de seguridad y las actualizaciones de seguridad comunes, según sea necesario.</li><li>Supervisar la telemetría y escalaciones de soporte técnico para detectar problemas inesperados.</li></ul></td><td><ul><li>Administrar el proceso de administración de cambio interno.</li><li>Crear una solicitud de soporte, si es necesario.</li></ul></td></tr><tr><td>Después de un cambio</td><td><ul><li>Recopilar comentarios de los clientes para mejorar la implantación de cambios en el futuro.</li><li>Supervisar la telemetría y escalaciones de soporte técnico para detectar problemas inesperados.</li></ul></td><td><ul><li>Leer y comprender el correo electrónico de notificación.</li><li>Proporcionar comentarios generales y comentarios específicos en la herramienta de administración de comentarios.</li><li>Entrenar a los usuarios proporcionar comentarios específicas de la aplicación con el concentrador de comentarios de Windows y el botón sonrisa en las aplicaciones de Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de cambio

Hay varios tipos de cambios que se realizan en el servicio de forma regular. Varía el canal de comunicación para esos cambios y las acciones que son responsables de los clientes.

Se pueden esperar que los siguientes tipos de cambios:

Tipo de cambio | Notificación | Acción del cliente.
--- | --- | ---
Característica actualizaciones y nuevos componentes de servicio | Correo electrónico | -Comunicar el cambio a los usuarios<br><br> -Act según sea necesario por Microsoft<br><br> -Acción se debe realizar dentro de 48 horas
Seguridad de las actualizaciones, actualizaciones mensuales y configuración de línea base | Correo electrónico, el boletín de seguridad o entrada las vulnerabilidades de seguridad comunes y riesgos (CVE) | -Las actualizaciones se implementarán mediante nuestra [estrategia de administración de actualización](updates.md)de seguridad mensual.<br><br> -Configuración a mitigar una amenaza se implementarán en toda la organización para proteger la organización. (ESTO NO PARECE SER UNA ACCIÓN DE ATENCIÓN AL CLIENTE)
Actualizaciones de calidad, incluidas las revisiones, actualizaciones de servicio y directiva de línea de base de seguridad comunes que afecta | Correo electrónico | Le indicará cuando sea necesario.
Actualizaciones de emergencia: necesarios de actualizaciones de software, la configuración o el servicio para mitigar:<br><br> -Riesgos de seguridad crítico<br><br> -Posibles pérdidas de datos<br><br> -Acceso a los datos de telemetría para administrar dispositivos de escritorio administrado de Microsoft | Le indicará cuando sea necesario.

## <a name="standard-operating-procedures"></a>Procedimientos operativos estándar

Este servicio se implementa y operado por Microsoft en su entorno donde realizar otras actividades administrativas. Microsoft es único responsable del programa de instalación, configuración y operación de específicos de Microsoft Managed Desktop. 

Para los productos local, su organización asume todas la responsabilidad de administrar operativas y actividades de configuración.

Categorías |    Acciones
--- | ---
Cuentas de servicio |  Microsoft hará lo siguiente:<br><br> -Implemente, forma segura almacenar y administrar las credenciales<br><br> -Comunicarse acceso no autorizado o el uso de estas credenciales a su equipo de operaciones de seguridad<br><br><br><br>Los clientes hará lo siguiente:<br><br> -Abra una solicitud de soporte técnico informativo con Microsoft Operations de escritorio administrado al planear un cambio que puede afectar a las cuentas<br><br> -No asignar la directiva, la autenticación multifactor, acceso condicional o implementación de aplicaciones a las cuentas de servicio administradas de escritorio de Microsoft<br><br> -No restablecer la contraseña o usar las credenciales<br><br> -Abra una solicitud de soporte Sev C a las operaciones de escritorio administrado de Microsoft si se observa una actividad sospechosa en los registros de auditoría Intune o Azure, relacionados con estas cuentas de servicio
Grupos de dispositivos | Microsoft hará lo siguiente:<br><br> -Implementar y administrar la pertenencia de dispositivos dentro de los grupos de escritorio administrado de Microsoft<br><br> -Usar los grupos de escritorio administrado de Microsoft para administrar la asignación y liberación de configuración y las actualizaciones en los dispositivos<br><br><br><br>Los clientes hará lo siguiente:<br><br> -Abra una solicitud de soporte técnico informativo con Microsoft Operations de escritorio administrado al planear un cambio que puede afectar a los grupos<br><br> -No modificar la pertenencia de cualquier grupo administrado de escritorio de Microsoft<br><br> -Sólo use los grupos para asignar certificados corporativos para servicios como VPN, Windows Hello para empresariales o correo electrónico cifrado o configuración de perfil de Wi-Fi corporativa<br><br> -Donde se encuentra CO-administración, excluir explícitamente todos los grupos de escritorio de Microsoft administrado al implementar el cliente de Configuration Manager
Policies |  Microsoft hará lo siguiente:<br><br> -Implementar y administrar las directivas de escritorio administrado de Microsoft que rigen el estado de configuración de dispositivos dentro de servicio<br><br> -Implementar actualizaciones, en Directiva o Windows, de forma incremental mediante grupos de dispositivos<br><br> -Excluir explícitamente grupos de destinatarios que no sean - administrados escritorio de Microsoft<br><br><br><br>Cliente hará lo siguiente:<br><br> -Abrir un vale de soporte técnico informativo con Microsoft Operations de escritorio administrado al planear un cambio que pueda afectar el estado de la configuración deseada de dispositivos<br><br> -No editar o asignar directivas de escritorio administrado de Microsoft a dispositivos o usuarios no administrados por el servicio de escritorio administrado de Microsoft
Protección contra amenazas avanzada de Windows Defender | Microsoft hará lo siguiente:<br><br> -Supervisar e investigar los dispositivos dentro del ámbito del servicio de escritorio administrado de Microsoft<br><br><br><br>Cliente hará lo siguiente:<br><br> -Abrir un vale de soporte técnico informativo con Microsoft Operations de escritorio administrado al planear un cambio que puede afectar a las capacidades de investigación o supervisión de Microsoft Managed Desktop Security Operations Center
Microsoft Store para Empresas |  Microsoft hará lo siguiente:<br><br> -Configurar y mantener el perfil de piloto automático de Windows para el servicio de escritorio administrado de Microsoft<br><br><br><br>Cliente hará lo siguiente:<br><br> -Abrir un vale de soporte técnico informativo con Microsoft Operations de escritorio administrado al planear un cambio que abrir podría afectar el acceso a la tienda o modificar el perfil de piloto automático Windows de escritorio de Microsoft administrado<br><br> -No modificar la configuración del perfil de piloto automático Windows de escritorio de Microsoft administrados o agregar o quitar dispositivos asignados
Certificados |  Cliente hará lo siguiente:<br><br> -Abrir un vale de soporte técnico informativo con días de 60 de las operaciones de escritorio administrado de Microsoft antes de cualquier certificado a expirar<br><br> -Actualizar todos los certificados que son necesarios para configurar: certificado perfiles, los perfiles de VPN y perfiles de Wi-Fi



## <a name="device-wipe-with-factory-reset"></a>Barrido de dispositivo con el restablecimiento de fábrica

Equipo de operaciones de escritorio administrado puede hacer una fábrica restablecer en dispositivos administrados de escritorio administrado de Microsoft que deben restaurarse. Esto resulta útil si necesita dar un dispositivo a un empleado diferente, o si un empleado deja la compañía. 

Existen algunos requisitos:

- Administrador de inquilinos del cliente debe enviar una solicitud de servicio
- Se necesita el nombre del equipo para el dispositivo
- Cuenta de usuario debe estar en Azure AD antes de que se realice el restablecimiento

Equipo de operaciones de escritorio administrado hará lo siguiente:

- Buscar el nombre del dispositivo en Intune
- Enviar que comando de restablecimiento de la fábrica al dispositivo

>[!NOTE]
>No quite la cuenta de usuario de Azure AD antes el restablecimiento de fábrica. Si el usuario no está en Azure AD, Intune no se puede enviar que la fábrica de restablece el comando en el dispositivo. 

El dispositivo se iniciará en OOBE y todas las aplicaciones preinstaladas y configuración se aplicará nuevo. Usuario del dispositivo debe proporcionar un conjunto inicial de información de nuevo. 

Cuando se ha reiniciado el dispositivo, puede otorgar a una persona diferente de la organización. Ninguno de los datos o los datos de la empresa del usuario anterior estará en el dispositivo. El siguiente usuario pasará por el mismo proceso que la persona anterior hizo con un nuevo dispositivo de escritorio de Microsoft administrado.

BitLocker es un componente clave de seguridad de los datos en este proceso. Con el cifrado BitLocker en dispositivos de escritorio de Microsoft administrado, datos de la unidad permanecen seguros incluso después de que se ha aplicado el restablecimiento de fábrica en el dispositivo. Los datos que estaba en la unidad no estará disponibles para el siguiente usuario del dispositivo. Para obtener más información, vea [información general de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obtener más información, vea [configuración de fábrica restablece un dispositivo](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
