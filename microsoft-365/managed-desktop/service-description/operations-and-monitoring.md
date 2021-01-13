---
title: Supervisión y operaciones de Escritorio administrado de Microsoft
description: Quién hace qué para varios procesos de cambio
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
ms.openlocfilehash: 5d7c6a7b836d0044ba9cde188170dd51f117dd2b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840378"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Supervisión y operaciones de Escritorio administrado de Microsoft

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Administración de cambios

En un oferta de servicio, el equilibrio de las responsabilidades en lo relativo a aspectos como el mantenimiento del hardware y las actualizaciones de seguridad se inclina hacia el proveedor de servicios (Microsoft), en lugar de hacia el cliente (usted). Sin embargo, debe asegurarse de que el software que no es de Microsoft y el software personalizado siga funcionando según lo esperado cuando se van a realizar actualizaciones.

Para los productos locales, su organización asume toda la responsabilidad de administrar los cambios.

### <a name="balance-of-responsibility"></a>Equilibrio de responsabilidades

Responsibility | Servicio de escritorio administrado de Microsoft | Software cliente de Microsoft 365 | Clientes y servidores locales | software que no es de Microsoft y personalizado
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
<tr><td>Antes de un cambio</td><td><ul><li>Establecer las expectativas en relación con los cambios en el servicio.</li><li>Notifica a los clientes con 5 días de antelación si hay cambios que requieran una acción del administrador.</li><li>Para los cambios de emergencia, aplica una mitigación antes de notificar.</li></ul></td><td><ul><li>Comprender qué esperar de los cambios y las comunicaciones.</li><li>Lea el Centro de mensajes de Escritorio administrado de Microsoft con regularidad.</li><li>Revisar y actualizar los procesos de administración de cambios internos.</li><li>Comprender y comprobar el cumplimiento de los requisitos de Escritorio administrado de Microsoft. </li><li>Confirmar y aprobar, cuando sea necesario.</li></ul></td></tr><tr><td>Durante un cambio</td><td><ul><li>Publicar e implementar actualizaciones mensuales de seguridad y no seguridad para clientes de Windows 10 y Office 365.</li><li>Supervisar las señales de datos y las colas de soporte para el impacto.</li></ul></td><td><ul><li>Compruebe el Centro de mensajes de Escritorio administrado de Microsoft y revise cualquier información adicional.</li><li>   Realizar cualquier acción necesaria, si procede, y probar aplicaciones.</li><li>Si se experimenta un escenario de interrupción o corrección, cree una solicitud de soporte técnico.</li></ul></td></tr><tr><td>Después de un cambio</td><td><ul><li>Recopilar comentarios de los clientes para mejorar la implementación de cambios futuros.</li><li>Supervisar las señales de datos y las colas de soporte para el impacto.</li></ul></td><td><ul><li>Trabaje con las personas de su organización para adoptar el cambio.</li><li>   Revisar los procesos de administración de cambios y adopción para obtener oportunidades para obtener eficiencia.</li><li>Proporcionar comentarios generales y comentarios específicos en la herramienta de comentarios del administrador.</li><li>Entrena a los usuarios para que proporcionen comentarios específicos de la aplicación mediante el Centro de opiniones de Windows y el botón Sonriente en las aplicaciones de Office.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Tipos de cambio

Hay varios tipos de cambios que se hacen en el servicio periódicamente. El canal de comunicación de esos cambios y las acciones de las que usted es responsable varía.

No todos los cambios afectan igual a los usuarios o requieren acciones. Algunas están planeadas y otras no planeadas por su naturaleza (las actualizaciones no de seguridad y las actualizaciones de seguridad no suelen planearse). Según el tipo de cambio, el canal de comunicación puede variar. En la tabla siguiente se enumeran los tipos de cambios que puede esperar para el servicio de escritorio administrado de Microsoft.

|   | Funcionalidad |   Actualizaciones que no son de seguridad |  Seguridad
--- | --- | --- | ---
**Tipo de cambio** | - Actualizaciones de características<br>- Nuevas características o aplicaciones<br>- Características en desuso | Revisiones de cliente para problemas | Actualizaciones de seguridad
**Comunicación con la antelación suficiente** | Aviso de cinco días para los cambios que requieren acción | No, estos cambios se incluyen en la versión mensual    | No, los cambios se incluyen en la versión mensual 
**Canal de comunicación** | - Centro de mensajes<br>- Alerta de correo electrónico | - Centro de mensajes<br>- Alerta de correo electrónico | - Centro de mensajes<br>- Alerta de correo electrónico
**Requiere acción de administrador global** | A veces |  Rara vez |    Rara vez 
**Tipo de acción** | Cambiar configuración | Comunicar los cambios a los usuarios | Cambiar la configuración de administración     
**Requiere pruebas** | Comprobar las aplicaciones empresariales, incluidos los servicios de acceso remoto |  A veces: probar la corrección en relación con los procesos o las personalizaciones. |   De forma muy ocasional 
**Ejemplos de cambios** | - Actualizaciones de características: revisión y envío de vales de soporte simplificado del Portal de administración de TI<br>- Nuevas características o aplicaciones: Semi-Annual de una actualización de características de Windows 10 | Revisiones basadas en errores notificados por los clientes |  


## <a name="standard-operating-procedures"></a>Procedimientos operativos estándar

Microsoft implementa y opera el servicio de Escritorio administrado de Microsoft en la instancia de nube de Microsoft donde puede llevar a cabo otras actividades administrativas. Microsoft es el único responsable de la configuración, configuración y funcionamiento específicos del Escritorio administrado de Microsoft. 

Para los productos locales, su organización asume toda la responsabilidad de administrar la configuración, la configuración y las actividades operativas.

Categorías |    Microsoft will | El cliente lo hará
--- | --- | ---
Red (proxy, inspección de paquetes, VPN)  | Aconsejar y planear con los clientes para minimizar el riesgo para los usuarios empresariales. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Solo aplica un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado.
Cuentas de servicio  |- Implementar, almacenar y administrar las credenciales de forma segura.<br> - Comunique el acceso no autorizado o el uso de estas credenciales al equipo de operaciones de seguridad. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Solo aplica un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado.<br>- No asignar directivas, autenticación multifactor, acceso condicional o implementación de aplicaciones a las cuentas de servicio de escritorio administrado de Microsoft.<br>- No restablecer la contraseña ni usar las credenciales.<br>- Abra una solicitud de soporte técnico de Sev C a las operaciones de escritorio administrado de Microsoft si se observa actividad sospechosa en los registros de auditoría de Intune o Azure, relacionados con estas cuentas de servicio.
Grupos de dispositivos | - Implementar y administrar la pertenencia de dispositivos dentro de los grupos de Escritorio administrado de Microsoft.<br>- Use los grupos de Escritorio administrado de Microsoft para administrar la asignación y el lanzamiento de la configuración y las actualizaciones de los dispositivos. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Solo aplica un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado.<br>- No modificar la pertenencia de ningún grupo de Escritorio administrado de Microsoft.<br>- Usa solo los grupos para asignar certificados corporativos para servicios como VPN, Windows Hello para empresas o cifrado de correo electrónico, o configuración de perfiles de Wi-Fi corporativos.<br>- Si existe la administración, excluya explícitamente todos los grupos de Escritorio administrado de Microsoft al implementar el cliente de Configuration Manager.
Directivas |  - Implementar y administrar las directivas de Escritorio administrado de Microsoft que rigen el estado de configuración de los dispositivos en el servicio.<br>- Implementar actualizaciones, para directivas o Windows, de forma incremental mediante grupos de dispositivos.<br> - Excluir explícitamente los grupos de escritorio administrado que no son de Microsoft. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Solo aplica un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado.<br>- No editar ni asignar directivas de Escritorio administrado de Microsoft a dispositivos o usuarios no administrados por el servicio de Escritorio administrado de Microsoft.
Microsoft Defender para punto de conexión | Supervisar e investigar dispositivos dentro del ámbito del servicio de Escritorio administrado de Microsoft. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Aplicar solo un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado
Microsoft Store para Empresas |  Configurar y mantener el perfil de Windows Autopilot para el servicio de escritorio administrado de Microsoft. | - Crear una solicitud de soporte técnico que solicite información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Solo aplica un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado.<br>- No modificar la configuración del perfil de Windows Autopilot de escritorio administrado de Microsoft ni agregar o quitar dispositivos asignados.
Certificados | | - Cree una solicitud de soporte técnico 60 días antes de que expire un certificado, solicitando información para un cambio de configuración planeado, incluidos los detalles de configuración, el ámbito, la escala de tiempo y otros detalles pertinentes para que Microsoft los revise.<br>- Solo aplica un cambio una vez que Las operaciones de escritorio administrado de Microsoft han evaluado y recomendado.<br>- Actualizar todos los certificados necesarios para configurar perfiles de certificado, perfiles de VPN y Wi-Fi certificados.




## <a name="device-wipe-with-factory-reset"></a>Borrado del dispositivo con restablecimiento de fábrica

El equipo de Operaciones de escritorio administrado de Microsoft puede realizar un restablecimiento de fábrica de los dispositivos inscritos en el servicio cuando sea necesario. El restablecimiento es útil si necesitas dar un dispositivo a un empleado diferente o si un empleado deja la empresa. 

Existen algunos requisitos:

- El administrador global debe enviar una solicitud de servicio.
- Incluye el nombre del equipo del dispositivo en la solicitud.
- La cuenta de usuario debe estar en Azure AD antes de restablecer el dispositivo.

El equipo de operaciones de escritorio administrado hará lo siguiente:

- Buscar el nombre del dispositivo en Intune
- Enviar el comando de restablecimiento de fábrica al dispositivo

>[!NOTE]
>No quite la cuenta de usuario de Azure AD antes de restablecer el dispositivo. Si el usuario no está en Azure AD, Intune no puede enviar el comando de restablecimiento de fábrica al dispositivo. 

El dispositivo arrancará en la "experiencia de fábrica" y todas las aplicaciones preinstaladas y la configuración se volverán a aplicar. El usuario del dispositivo debe proporcionar información de configuración inicial de nuevo. 

Cuando se haya restablecido el dispositivo, puedes dálelo a otra persona de la organización. Ninguno de los datos del usuario anterior ni de la empresa estarán en el dispositivo. El siguiente usuario pasará por el mismo proceso que la persona anterior hizo con un nuevo dispositivo de Escritorio administrado de Microsoft.

BitLocker es un componente clave de la seguridad de datos en este proceso. Con el cifrado de BitLocker en dispositivos de Escritorio administrado de Microsoft, los datos de la unidad permanecen seguros incluso después de que el dispositivo se haya restablecido de fábrica. Los datos que se encontraban en la unidad no estarán disponibles para el siguiente usuario del dispositivo. Para obtener más información, consulta Información [general de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

Para obtener más información, consulta [Restablecer un dispositivo de fábrica.](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device) 