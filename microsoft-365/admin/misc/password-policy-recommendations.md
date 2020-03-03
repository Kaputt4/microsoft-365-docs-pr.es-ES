---
title: Recomendaciones de directiva de contraseñas para Office 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Obtenga información acerca de cómo hacer que su organización sea más segura frente a ataques a contraseñas y por qué debe prohibir contraseñas comunes y habilitar la autenticación multifactor basada en riesgos.
ms.openlocfilehash: 7136243aa0a358a59e4be6c348f53ca459e8a65d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361331"
---
# <a name="password-policy-recommendations-for-office-365"></a>Recomendaciones de directiva de contraseñas para Office 365
 
Como administrador de una organización de Office 365, usted es el responsable de configurar la Directiva de contraseñas para los usuarios de su organización. El establecimiento de la Directiva de contraseñas puede resultar complicado y confuso, y en este artículo se proporcionan recomendaciones para que la organización sea más segura frente a ataques de contraseñas.
  
Para determinar con qué frecuencia expiran las contraseñas de Office 365 en la organización, consulte [establecer la Directiva de expiración de contraseñas para Office 365](../manage/set-password-expiration-policy.md).
  
## <a name="understanding-password-recommendations"></a>Comprender las recomendaciones de contraseña

Los procedimientos recomendados para las contraseñas se dividen en algunas amplias categorías:
  
- **Resisten los ataques comunes** esto implica la elección del lugar donde los usuarios introducen las contraseñas (dispositivos conocidos y de confianza con una detección de malware, sitios validados) y la elección de la contraseña que debe elegir (longitud y unicidad).

- **Refrenan ataques exitosos** el contener ataques de hackers satisfactoriamente consiste en limitar la exposición a un servicio específico, o bien evitar que se produzcan daños, en caso de que se robe la contraseña de un usuario. Por ejemplo, si se asegura de que una infracción de las credenciales de la red social no haga que su cuenta bancaria sea vulnerable, o no permita que una cuenta guardada mal protegida acepte vínculos de restablecimiento de una cuenta importante.

- **Entender la naturaleza humana** muchos de los procedimientos válidos de contraseñas no se encuentran en el comportamiento humano natural. Entender la naturaleza humana es fundamental, ya que la investigación muestra que casi todas las reglas que se imponen a los usuarios tendrán como resultado debilitar la calidad de la contraseña. Los requisitos de longitud, los requisitos de caracteres especiales y los requisitos de cambio de contraseña todos provocan la normalización de las contraseñas, lo que hace que resulte más fácil averiguar o descifrar contraseñas.

## <a name="password-guidelines-for-administrators"></a>Instrucciones de contraseña para administradores

El principal objetivo de un sistema de contraseña más seguro es la diversidad de las contraseñas. Desea que la Directiva de contraseñas contenga una gran cantidad de contraseñas distintas y difíciles de adivinar. Estas son algunas recomendaciones para mantener su organización lo más segura posible.
  
- Mantenga como requisito el que la longitud mínima sea de 8 caracteres (una contraseña más larga no siempre es mejor)

- No solicite requisitos de composición de caracteres. Por ejemplo, \*&amp;(^%$

- No requiera una configuración de contraseña periódica obligatoria para cuentas de usuario.

- Prohíba las contraseñas comunes para evitar el uso de las contraseñas más vulnerables en el sistema. 

- Instruya a los usuarios para que no vuelvan a usar las contraseñas de la organización para propósitos no relacionados con el trabajo

- Exija el registro para la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)

- Permitir desafíos de autenticación multifactor basada en riesgos

### <a name="password-guidance-for-your-users"></a>Guía de contraseñas para los usuarios

Esta es una guía de contraseñas para los usuarios de su organización. Asegúrese de que los usuarios sepan estas recomendaciones y apliquen las directivas de contraseñas recomendadas en el nivel de organización.
  
- No use una contraseña igual o similar a una que use en otros sitios web

- No use solo una palabra, por ejemplo, **contraseña**, ni una frase que use habitualmente, como **ILOVEYOU.**

- Haga que las contraseñas sean difíciles de adivinar, incluso las personas que sepan mucho sobre usted, como el nombre y el cumpleaños de sus amigos y familiares, sus bandas favoritas y las frases que quiera usar.

## <a name="some-common-approaches-and-their-negative-impacts"></a>Algunos métodos comunes y sus repercusiones negativas

Éstas son algunas de las prácticas de administración de contraseñas más usadas, pero la búsqueda nos avisa sobre las consecuencias negativas que tienen.
  
### <a name="password-expiration-requirements-for-users"></a>Requisitos de expiración de contraseña para usuarios

Los requisitos de expiración de contraseñas son más dañinos que los que hacen que los usuarios seleccionen contraseñas predecibles, formadas por palabras secuenciales y números estrechamente relacionados entre sí. En estos casos, la contraseña siguiente puede predecirse en función de la contraseña anterior. Los requisitos de expiración de contraseñas no proporcionan ventajas de contención ya que los ciberdelincuentes casi siempre usan credenciales tan pronto como los comprometen.
  
### <a name="requiring-long-passwords"></a>Requerir contraseñas largas

Los requisitos de longitud de contraseña (con un tamaño superior a 10 caracteres) pueden dar lugar a un comportamiento de usuario predecible e indeseable. Por ejemplo, es posible que los usuarios que tengan que disponer de una contraseña de 16 caracteres elijan patrones de repetición como **fourfourfourfour** o **passwordpassword** que cumplan con los requisitos de longitud de caracteres y no sean difíciles de adivinar. Además, los requisitos de longitud aumentan las posibilidades de que los usuarios adopten otras prácticas que no sean seguras, como escribir su contraseña, volver a usarlas o almacenarlas sin cifrar en sus documentos. Para animar a los usuarios a considerar una contraseña única, le recomendamos que mantenga un requisito de longitud mínima de 8 caracteres. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Requerir el uso de varios juegos de caracteres

Los requisitos de complejidad de las contraseñas reducen el espacio clave y provocan que los usuarios actúen de formas predecibles, que hacen más daño que bien. La mayoría de los sistemas aplican algunos niveles de complejidad de contraseña. Por ejemplo, las contraseñas necesitan caracteres de las tres categorías siguientes:
  
- Caracteres en mayúsculas 

- Caracteres en minúsculas

- Caracteres no alfanuméricos

La mayoría de los usuarios usa patrones similares, por ejemplo, una letra mayúscula en la primera posición, un símbolo en la última y un número las últimas 2. Los ciberdelincuentes lo saben, por lo que ejecutan sus ataques de diccionario utilizando las sustituciones más comunes, "$" para "s", "@" para "a", "1" para "l". Obligar a sus usuarios a elegir una combinación de letras en mayúsculas, minúsculas, dígitos y caracteres especiales tiene un efecto negativo. Algunos requisitos de complejidad incluso evitan que los usuarios usen contraseñas seguras y fáciles de recordar, y obligan a que se encuentren con contraseñas menos seguras y menos fáciles de recordar.
  
## <a name="successful-patterns"></a>Patrones correctos

En cambio, estas son algunas recomendaciones para favorecer la diversidad de contraseñas.
  
### <a name="ban-common-passwords"></a>Prohibir contraseñas comunes

El requisito de contraseña más importante que debe aplicar a los usuarios al crear contraseñas es vetar el uso de contraseñas comunes para reducir la susceptibilidad de la organización a ataques violentos de contraseñas. Las contraseñas de usuario comunes son, por ejemplo **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Instruya a los usuarios para no volver a usar contraseñas de la organización en otro lugar

Uno de los mensajes más importantes para tener acceso a los usuarios de su organización es no volver a usar la contraseña de su organización en ningún otro lugar. El uso de las contraseñas de organización en sitios web externos aumenta considerablemente la probabilidad de que los ciberdelincuentes puedan comprometer estas contraseñas.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Exigir registro de Multi-Factor Authentication

Asegúrese de que los usuarios actualizan la información de contacto y seguridad, como una dirección de correo electrónico alternativa, un número de teléfono o un dispositivo registrado para las notificaciones de inserción, de modo que pueden responder a los desafíos de seguridad y recibir notificaciones de eventos de seguridad. La información actualizada de contacto y seguridad ayuda a los usuarios a verificar su identidad si alguna vez olvidan su contraseña o si alguien más intenta hacerse cargo de su cuenta. También proporciona un canal de notificación fuera de banda en caso de eventos de seguridad como intentos de inicio de sesión o cambio de contraseñas. 
  
Para obtener más información, consulte [configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Habilitar la autenticación multifactor basada en riesgos

La autenticación multifactor basada en riesgos garantiza que, cuando nuestro sistema detecta actividad sospechosa, puede poner a prueba al usuario para asegurarse de que es el propietario legítimo de la cuenta. 
  
## <a name="want-to-know-more-recommended-reading"></a>¿Desea obtener más información? Lectura recomendada

- [¿Las contraseñas de web seguras realizan alguna acción?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Carteras de contraseñas y el usuario de esfuerzo finito](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Prevenir contraseñas vulnerables leyendo las mentes de los usuarios](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Elegir contraseñas seguras](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Tiempo para reconsiderar los cambios en la contraseña obligatoria](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Las peores contraseñas de 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

- [Descargar archivos desde la web](https://go.microsoft.com/fwlink/p/?linkid=861029)
