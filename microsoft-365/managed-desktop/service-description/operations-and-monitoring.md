---
title: Las operaciones de escritorio de Microsoft administrado y supervisión
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.openlocfilehash: 66945d44df150b5be9af9a9dfe52daa4d7468298
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871333"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Las operaciones de escritorio de Microsoft administrado y supervisión

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Administración de cambios

En un oferta de servicio, el equilibrio de responsabilidad para acciones como la seguridad y el mantenimiento de hardware actualizaciones se desplazan al proveedor de servicios (Microsoft) en lugar del cliente (usted). Sin embargo, aún necesita para asegurarse de que terceros y sigue funcionando según lo esperado cuando se implementan actualizaciones de software personalizado.

Para los productos local, su organización asume toda la responsabilidad de administración de cambios.

### <a name="balance-of-responsibility"></a>Saldo de responsabilidad

Responsibility | Servicio de escritorio administrado de Microsoft | Software de cliente de Microsoft 365 | Clientes y servidores locales | parte 3 y el software personalizado
----- | ----- | ----- | ----- | -----
Proporciona nuevas funciones | Microsoft | Microsoft | Ambos | Cliente
Probar las características nuevas como control de calidad |  Microsoft | Microsoft | Ambos | Cliente
Comunicar las características nuevas | Ambos | Ambos | Ambos | Cliente
Integrar software personalizado | Ambos | Ambos | Cliente | Cliente
Aplicar las actualizaciones de seguridad | Microsoft | Microsoft | Cliente | Cliente
Mantener el software del sistema | Microsoft | Microsoft | Cliente | Cliente
Paquete de implementación | Microsoft | Microsoft | Cliente | Cliente


### <a name="change-process-overview"></a>Información general sobre el proceso de cambio

Éste es un resumen de cómo el proceso de cambio se comparte entre Microsoft y los clientes. 



<table>
<tr><th></th><th><p>Función de Microsoft:</p></th><th><p>Rol del cliente:</p></th></tr>
<tr><td>Antes de un cambio</td><td><ul><li>Establecer las expectativas en relación con los cambios en el servicio.</li><li>Notificar a los clientes 5 días por adelantado para que los cambios que requieren la acción del administrador.</li><li>Cambios de emergencia, aplicar una mitigación antes de la notificación.</li></ul></td><td><ul><li>Comprender qué esperar de los cambios y las comunicaciones.</li><li>Lectura Microsoft administrados escritorio centro de mensajes con regularidad.</li><li>Revisar y actualizar los procesos de administración de cambios internos.</li><li>Comprender y comprobar el cumplimiento de los requisitos de escritorio administrado de Microsoft. </li><li>Confirmar y aprobar, cuando sea necesario.</li></ul></td></tr><tr><td>Durante un cambio</td><td><ul><li>Liberar e implementar las actualizaciones de seguridad y comunes de mensual para clientes 10 de Windows y Office 365.</li><li>Supervisar las señales de datos y compatibilidad con colas impacto.</li></ul></td><td><ul><li>Compruebe el Microsoft Managed Desktop Message Center y revisar cualquier información adicional.</li><li>   Realice ninguna acción necesaria, si procede y probar aplicaciones.</li><li>Si se produjo un escenario de correcciones y, cree una solicitud de soporte técnico.</li></ul></td></tr><tr><td>Después de un cambio</td><td><ul><li>Recopilar comentarios de los clientes para mejorar la implantación de cambios en el futuro.</li><li>Supervisar las señales de datos y compatibilidad con colas impacto.</li></ul></td><td><ul><li>Trabajar con las personas de su organización a adoptar el cambio.</li><li>   Revisión de los procesos de administración de cambio y adopción de oportunidades mejorar la eficacia.</li><li>Proporcionar comentarios generales y comentarios específicos en la herramienta de administración de comentarios.</li><li>Entrenar a los usuarios proporcionar comentarios específicas de la aplicación con el concentrador de comentarios de Windows y el botón sonrisa en las aplicaciones de Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de cambio

Hay varios tipos de cambios que se realizan en el servicio de forma regular. Varía el canal de comunicación para esos cambios y las acciones que son responsables de los clientes.

No todos los cambios tengan el mismo impacto en los usuarios o requieren la acción. Algunas son algunas planificado y por su naturaleza (por lo general no planificadas actualizaciones de seguridad comunes y actualizaciones de seguridad). Según el tipo de cambio, puede variar el canal de comunicación. En la siguiente tabla se enumera los tipos de cambios que se pueden esperar para el servicio de escritorio administrado de Microsoft.

|   | Funcionalidad |   Actualizaciones no relacionadas con la seguridad |  Seguridad
--- | --- | --- | ---
**Tipo de cambio** | -Las actualizaciones de la característica<br>-Nuevas características o aplicaciones<br>-En desuso de características | Revisiones de cliente para problemas | Revisiones de seguridad
**Aviso por adelantado** | aviso de 5 días para que los cambios que requieren la acción |    No, estos se incluyen en la versión mensual   | No, estos se incluyen en la versión mensual 
**Canal de comunicación** | : Centro de mensajes<br>-Alerta por correo electrónico | : Centro de mensajes<br>-Alerta por correo electrónico | : Centro de mensajes<br>-Alerta por correo electrónico<br>-Boletín de seguridad o CVE 
**Requiere una acción de administración de inquilinos** | A veces |  Rara vez |    Rara vez 
**Tipo de acción** | Cambiar configuración | Comunicar los cambios a los usuarios | Cambiar la configuración de administración     
**Requiere prueba** | Comprobación de aplicaciones empresariales, incluidos los servicios de acceso remoto |  A veces: probar la corrección en relación con los procesos o las personalizaciones. |   De forma muy ocasional 
**Ejemplos de cambio** | -Las actualizaciones de la característica: Portal de administración de TI simplificado el envío de vale de soporte técnico y la revisión<br>-Nuevas características o aplicaciones: publicación semestral de una actualización de la característica de 10 de Windows | Revisiones basadas en errores notificados por los clientes |  


## <a name="standard-operating-procedures"></a>Procedimientos operativos estándar

El servicio de escritorio de Microsoft administrado se implementa y operado por Microsoft en la instancia de nube de Microsoft donde puede llevar a cabo otras actividades administrativas. Microsoft es único responsable del programa de instalación, configuración y operación de específicos de Microsoft Managed Desktop. 

Para los productos local, su organización asume responsabilidad para administrar el programa de instalación, configuración y actividades operativas.

Categorías |    Va Microsoft | Va cliente
--- | --- | ---
Red (proxy, la inspección de paquetes, VPN)  | Aviso y planeación con los clientes para minimizar el riesgo para los usuarios empresariales. | -Crear una solicitud de soporte que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado.
Cuentas de servicio |-Implemente, forma segura almacenar y administrar las credenciales.<br> -Comunicarse acceso no autorizado o el uso de estas credenciales a su equipo de operaciones de seguridad. | -Crear una solicitud de soporte que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado.<br>-No asignar directiva, la autenticación multifactor, acceso condicional o implementación de la aplicación a las cuentas de servicio administradas de escritorio de Microsoft.<br>-No restablecer la contraseña o usar las credenciales.<br>-Abra una solicitud de soporte Sev C para operaciones de escritorio administrado de Microsoft si se observa una actividad sospechosa en los registros de auditoría Intune o Azure, relacionados con estas cuentas de servicio.
Grupos de dispositivos | -Implementar y administrar la pertenencia de dispositivos dentro de los grupos de escritorio administrado de Microsoft.<br>-Use los grupos de escritorio administrado de Microsoft para administrar la asignación y liberación de configuración y las actualizaciones en los dispositivos. | -Crear una solicitud de soporte que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado.<br>-No modificar la pertenencia de cualquier grupo administrado de escritorio de Microsoft.<br>-Sólo puede utilizar los grupos para asignar certificados corporativos para servicios como VPN, Windows Hello para empresariales o correo electrónico cifrado o configuración de perfil de Wi-Fi corporativa.<br>-Donde se encuentra CO-administración, excluir explícitamente todos los grupos de escritorio de Microsoft administrado al implementar el cliente de Configuration Manager.
Policies |  -Implementar y administrar las directivas de escritorio administrado de Microsoft que rigen el estado de configuración de dispositivos dentro de servicio.<br>-Implementar actualizaciones, en la directiva o Windows, de forma incremental mediante grupos de dispositivos.<br> -Excluir explícitamente grupos de destinatarios que no sean - Microsoft Managed Desktop. | -Crear una solicitud de soporte que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado.<br>-No editar o asignar directivas de escritorio administrado de Microsoft a dispositivos o usuarios no administrados por el servicio de escritorio administrado de Microsoft.
Protección contra amenazas avanzada de Windows Defender | Supervisar e investigar los dispositivos dentro del ámbito del servicio de escritorio administrado de Microsoft. | -Crear una solicitud de soporte que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado
Microsoft Store para Empresas |  Configurar y mantener el perfil de piloto automático de Windows para el servicio de escritorio administrado de Microsoft. | -Crear una solicitud de soporte que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado.<br>-No modificar la configuración del perfil de piloto automático Windows de escritorio de Microsoft administrados o agregar o quitar dispositivos asignados.
Certificados | | -Crear una solicitud de soporte técnico de 60 días antes de un certificado a expirar, que solicita información de un cambio en la configuración planeada, incluidos los detalles de configuración, ámbito, escala de tiempo y otros detalles pertinentes de Microsoft revisar.<br>-Sólo se aplican un cambio una vez que se evalúan y aconseja Microsoft Operations de escritorio administrado.<br>-Actualizar todos los certificados que son necesarios para configurar perfiles de certificados, los perfiles de VPN y perfiles de Wi-Fi.




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
