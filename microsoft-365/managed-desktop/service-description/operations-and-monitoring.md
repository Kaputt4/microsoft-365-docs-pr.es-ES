---
title: Supervisión y operaciones de escritorio administradas de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: c618c5bf2acf50d84aca354975670ed84b581601
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431921"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Supervisión y operaciones de escritorio administradas de Microsoft

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Administración de cambios

En un oferta de servicio, el equilibrio de las responsabilidades en lo relativo a aspectos como el mantenimiento del hardware y las actualizaciones de seguridad se inclina hacia el proveedor de servicios (Microsoft), en lugar de hacia el cliente (usted). Sin embargo, aún tiene que asegurarse de que el software de terceros y el personalizado sigue funcionando del modo previsto cuando se implementan las actualizaciones.

En el caso de los productos locales, la organización asume toda la responsabilidad de la administración de cambios.

### <a name="balance-of-responsibility"></a>Equilibrio de responsabilidad

Responsibility | Servicio de escritorio administrado por Microsoft | Software de cliente de Microsoft 365 | Clientes y servidores locales | terceros y software personalizado
----- | ----- | ----- | ----- | -----
Proporciona nuevas funciones | Microsoft | Microsoft | Ambas | Clientes
Probar las características nuevas como control de calidad |  Microsoft | Microsoft | Ambas | Clientes
Comunicar las características nuevas | Ambas | Ambas | Ambas | Clientes
Integrar software personalizado | Ambas | Ambas | Clientes | Clientes
Aplicar las actualizaciones de seguridad | Microsoft | Microsoft | Clientes | Clientes
Mantener el software del sistema | Microsoft | Microsoft | Clientes | Clientes
Paquete para implementación | Microsoft | Microsoft | Clientes | Clientes


### <a name="change-process-overview"></a>Información general sobre el cambio de proceso

A continuación, se muestra un resumen de cómo se comparte el proceso de cambio entre Microsoft y los clientes. 



<table>
<tr><th></th><th><p>Rol de Microsoft:</p></th><th><p>Rol del cliente:</p></th></tr>
<tr><td>Antes de un cambio</td><td><ul><li>Establecer las expectativas en relación con los cambios en el servicio.</li><li>Notifique a los clientes 5 días antes de los cambios que requieren acciones del administrador.</li><li>Para cambios de emergencia, aplique una mitigación antes de la notificación.</li></ul></td><td><ul><li>Comprender qué esperar de los cambios y las comunicaciones.</li><li>Lea periódicamente el centro de mensajes de escritorio administrado de Microsoft.</li><li>Revisar y actualizar los procesos de administración de cambios internos.</li><li>Comprenda y compruebe el cumplimiento de los requisitos de escritorio administrado por Microsoft. </li><li>Confirmar y aprobar, cuando sea necesario.</li></ul></td></tr><tr><td>Durante un cambio</td><td><ul><li>Lanzamiento e implementación de actualizaciones de seguridad y no relacionadas con la seguridad mensual para clientes de Windows 10 y Office 365.</li><li>Supervisar las señales de datos y admitir colas para que tengan impacto.</li></ul></td><td><ul><li>Compruebe el centro de mensajes de escritorio administrado de Microsoft y revise la información adicional.</li><li>   Realizar cualquier acción necesaria, si es aplicable, y probar las aplicaciones.</li><li>Si se experimenta un escenario de interrupción/corrección, cree una solicitud de soporte técnico.</li></ul></td></tr><tr><td>Después de un cambio</td><td><ul><li>Recopilar los comentarios de los clientes para mejorar el lanzamiento de futuros cambios.</li><li>Supervisar las señales de datos y admitir colas para que tengan impacto.</li></ul></td><td><ul><li>Trabaje con las personas de su organización para adoptar el cambio.</li><li>   Revisar los procesos de administración de cambios y adopción para oportunidades para obtener eficiencias.</li><li>Proporcionar comentarios generales y comentarios específicos en la herramienta de comentarios del administrador.</li><li>Entrenar a los usuarios para que proporcionen comentarios específicos de la aplicación con el centro de comentarios de Windows y el botón sonrisa en las aplicaciones de Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de cambios

Hay varios tipos de cambios que se realizan con regularidad en el servicio. El canal de comunicación de los cambios y las acciones que los clientes son responsables de la misma varían.

No todos los cambios afectan igual a los usuarios o requieren acciones. Algunas están planeadas y otras no planificadas por su naturaleza (las actualizaciones no relacionadas con la seguridad y las actualizaciones de seguridad no suelen estar planeadas). Según el tipo de cambio, el canal de comunicación puede variar. En la siguiente tabla se enumeran los tipos de cambios que puede esperar para el servicio de escritorio administrado de Microsoft.

|   | Funcionalidad |   Actualizaciones que no son de seguridad |  Seguridad
--- | --- | --- | ---
**Tipo de cambio** | -Actualizaciones de características<br>-Nuevas características o aplicaciones<br>-Características en desuso | Revisiones de cliente para problemas | Revisiones de seguridad
**Comunicación con la antelación suficiente** | 5 días de antelación para los cambios que requieren acción |    No, estos se incluyen en la versión mensual   | No, estos se incluyen en la versión mensual 
**Canal de comunicación** | -Centro de mensajes<br>-Alerta de correo electrónico | -Centro de mensajes<br>-Alerta de correo electrónico | -Centro de mensajes<br>-Alerta de correo electrónico
**Requiere la acción de administrador de inquilinos** | A veces |  Rara vez |    Rara vez 
**Tipo de acción** | Cambiar configuración | Comunicar los cambios a los usuarios | Cambiar la configuración de administración     
**Requiere pruebas** | Comprobar las aplicaciones empresariales, incluidos los servicios de acceso remoto |  A veces: probar la corrección en relación con los procesos o las personalizaciones. |   De forma muy ocasional 
**Ejemplos de cambio** | -Actualizaciones de características: portal de administración de ti el envío y revisión de incidencias de soporte simplificado<br>-Nuevas características o aplicaciones: lanzamiento semi-anual de una actualización de características de Windows 10 | Revisiones basadas en errores notificados por los clientes |  


## <a name="standard-operating-procedures"></a>Procedimientos operativos estándar

El servicio de escritorio administrado de Microsoft es implementado y operado por Microsoft en su instancia de Microsoft Cloud donde puede llevar a cabo otras actividades administrativas. Microsoft es el único responsable de la configuración, la configuración y el funcionamiento específicos del escritorio administrado por Microsoft. 

En el caso de los productos locales, la organización asume toda la responsabilidad para administrar la configuración y las actividades operativas y de configuración.

Categorias |    Microsoft le | Cliente se
--- | --- | ---
Red (proxy, inspección de paquetes, VPN)  | Aconseje y planifique con los clientes para minimizar el riesgo para los usuarios profesionales. | -Cree una solicitud de soporte técnico que solicite información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft se han evaluado y aconsejado.
Cuentas de servicio |-Implemente, almacene y administre las credenciales de forma segura.<br> -Comunique el acceso no autorizado o el uso de estas credenciales al equipo de operaciones de seguridad. | -Cree una solicitud de soporte técnico que solicite información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft se han evaluado y aconsejado.<br>-No asignar la Directiva, la autenticación multifactor, el acceso condicional o la implementación de aplicaciones a las cuentas de servicio de escritorio administradas de Microsoft.<br>-No restablecer la contraseña ni usar las credenciales.<br>-Abra una solicitud de soporte de gravedad C a operaciones de escritorio administradas de Microsoft si se observa actividad sospechosa en los registros de auditoría de Intune o Azure, relacionados con estas cuentas de servicio.
Grupos de dispositivos | : Implemente y administre la pertenencia de dispositivos en grupos de escritorio administrado por Microsoft.<br>-Use los grupos de Microsoft Managed Desktop para administrar la asignación y la publicación de la configuración y las actualizaciones de los dispositivos. | -Cree una solicitud de soporte técnico que solicite información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft se han evaluado y aconsejado.<br>-No modifique la pertenencia de ningún grupo de escritorio administrado por Microsoft.<br>-Use solo los grupos para asignar certificados corporativos para servicios como VPN, Windows Hello para empresas o cifrado de correo electrónico, o configuración de Perfil de Wi-Fi corporativo.<br>-Donde hay coadministración, excluya explícitamente todos los grupos de escritorio administrados por Microsoft al implementar el cliente de Configuration Manager.
Directivas |  : Implemente y administre las directivas de escritorio administradas por Microsoft que rigen el estado de configuración de los dispositivos dentro del servicio.<br>-Implementar actualizaciones, en la Directiva o en las ventanas, con grupos de dispositivos de forma incremental.<br> -Excluya explícitamente los grupos de escritorio administrados que no son de Microsoft. | -Cree una solicitud de soporte técnico que solicite información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft se han evaluado y aconsejado.<br>-No edite ni asigne directivas de escritorio administradas por Microsoft a dispositivos o usuarios que no estén administrados por el servicio de escritorio administrado de Microsoft.
Protección contra amenazas avanzada de Windows Defender | Supervisar e investigar los dispositivos que se encuentran dentro del ámbito del servicio de escritorio administrado por Microsoft. | -Cree una solicitud de soporte técnico que solicite información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft hayan evaluado y aconsejado
Microsoft Store para Empresas |  Configurar y mantener el perfil de Windows AutoPilot para el servicio de escritorio administrado por Microsoft. | -Cree una solicitud de soporte técnico que solicite información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft se han evaluado y aconsejado.<br>-No modifique la configuración del perfil Microsoft Managed Desktop Windows AutoPilot o agregue o quite dispositivos asignados.
Certificados | | -Cree una solicitud de soporte 60 días antes de que expire el certificado, solicitando información para un cambio de configuración planificado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles relevantes que Microsoft debe revisar.<br>-Solo aplique un cambio una vez que las operaciones de escritorio administradas por Microsoft se han evaluado y aconsejado.<br>-Actualizar todos los certificados necesarios para configurar los perfiles de certificados, los perfiles de VPN y los perfiles de Wi-Fi.




## <a name="device-wipe-with-factory-reset"></a>Borrado de dispositivo con restablecimiento de fábrica

El equipo de operaciones de escritorio administrado puede realizar un restablecimiento de fábrica en los dispositivos administrados por el escritorio administrados por Microsoft que deben volver a crearse en la imagen. Esto es útil si necesita dar un dispositivo a un empleado diferente o si un empleado abandona la compañía. 

Hay algunos requisitos:

- El administrador de inquilinos del cliente debe enviar una solicitud de servicio
- Necesitamos el nombre del equipo para el dispositivo
- La cuenta de usuario debe estar en Azure AD antes de restablecer

El equipo de operaciones de escritorio administrado hará lo siguiente:

- Buscar el nombre del dispositivo en Intune
- Enviar el comando de restablecimiento de fábrica al dispositivo

>[!NOTE]
>No quite la cuenta de usuario de Azure AD antes del restablecimiento de fábrica. Si el usuario no está en Azure AD, Intune no puede enviar el comando de restablecimiento de fábrica al dispositivo. 

El dispositivo se iniciará en OOBE y se volverán a aplicar todas las aplicaciones y configuraciones preinstaladas. El usuario del dispositivo debe proporcionar otra vez la información de configuración inicial. 

Una vez restablecido el dispositivo, puede asignarlo a una persona distinta de la organización. Ninguno de los datos de la empresa o del usuario anterior estarán en el dispositivo. El siguiente usuario pasará por el mismo proceso que la persona anterior hacía con un nuevo dispositivo de escritorio administrado por Microsoft.

BitLocker es un componente clave de la seguridad de datos en este proceso. Con el cifrado de BitLocker en dispositivos de escritorio administrados por Microsoft, los datos de la unidad permanecen seguros incluso después de que se haya aplicado el restablecimiento de fábrica al dispositivo. Los datos que estuvieran en la unidad no estarán disponibles para el siguiente usuario del dispositivo. Para obtener más información, vea información [General de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Para obtener más información, consulte [restablecimiento de fábrica de un dispositivo](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device). 
