---
title: Recomendaciones de directiva de contraseñas
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Haga que su organización sea más segura contra ataques a contraseñas y prohíba las contraseñas comunes y habilite la autenticación multifactor basada en riesgos.
ms.openlocfilehash: 6f79116b1188eaab1b843b2e3fa612c4ed01c488
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096629"
---
# <a name="password-policy-recommendations"></a>Recomendaciones de directiva de contraseñas

Como administrador de una organización, usted es el responsable de establecer la directiva de contraseñas para los usuarios de su organización. El establecimiento de la directiva de contraseñas puede resultar complicado y confuso, y en este artículo se proporcionan recomendaciones para que la organización sea más segura frente a ataques de contraseñas.
  
Para determinar con qué frecuencia expiran las contraseñas de Microsoft 365 en la organización, vea [Establecer la directiva de expiración de contraseñas para Microsoft 365](../manage/set-password-expiration-policy.md).

Para obtener más información acerca de las contraseñas de Microsoft 365, vea:

[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)

[Establecer la contraseña de un usuario individual para que nunca expire](../add-users/set-password-to-never-expire.md) (artículo)

[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)

[Volver a enviar la contraseña de un usuario: ayuda para administradores](../add-users/resend-user-password.md) (artículo)
  
## <a name="understanding-password-recommendations"></a>Comprender las recomendaciones de contraseña

Los procedimientos recomendados para las contraseñas se dividen en algunas amplias categorías:
  
- **Resisten los ataques comunes** esto implica la elección del lugar donde los usuarios introducen las contraseñas (dispositivos conocidos y de confianza con una detección de malware, sitios validados) y la elección de la contraseña que debe elegir (longitud y unicidad).

- **Refrenan ataques exitosos** el contener ataques de hackers satisfactoriamente consiste en limitar la exposición a un servicio específico, o bien evitar que se produzcan daños, en caso de que se robe la contraseña de un usuario. Por ejemplo, si se asegura de que una infracción de las credenciales de la red social no haga que su cuenta bancaria sea vulnerable, o no permita que una cuenta guardada mal protegida acepte vínculos de restablecimiento de una cuenta importante.

- **Entender la naturaleza humana** muchos de los procedimientos válidos de contraseñas no se encuentran en el comportamiento humano natural. Entender la naturaleza humana es fundamental, ya que la investigación muestra que casi todas las reglas que se imponen a los usuarios tendrán como resultado debilitar la calidad de la contraseña. Los requisitos de longitud, los requisitos de caracteres especiales y los requisitos de cambio de contraseña todos provocan la normalización de las contraseñas, lo que hace que resulte más fácil averiguar o descifrar contraseñas.

## <a name="password-guidelines-for-administrators"></a>Instrucciones de contraseña para administradores

El principal objetivo de un sistema de contraseña más seguro es la diversidad de las contraseñas. Desea que la Directiva de contraseñas contenga una gran cantidad de contraseñas distintas y difíciles de adivinar. Estas son algunas recomendaciones para mantener su organización lo más segura posible.
  
- Mantener un requisito de longitud mínima de 8 caracteres

- No solicite requisitos de composición de caracteres. Por ejemplo, \*&amp;(^%$

- No requiera una configuración de contraseña periódica obligatoria para cuentas de usuario.

- Prohíba las contraseñas comunes para evitar el uso de las contraseñas más vulnerables en el sistema. 

- Instruya a los usuarios para que no vuelvan a usar las contraseñas de la organización para propósitos no relacionados con el trabajo

- Exija el registro para la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)

- Permitir desafíos de autenticación multifactor basada en riesgos

### <a name="password-guidance-for-your-users"></a>Guía de contraseñas para los usuarios

Esta es una guía sobre contraseñas para los usuarios de su organización. Asegúrese de que los usuarios sepan estas recomendaciones y apliquen las directivas de contraseñas recomendadas a nivel de la organización.
  
- No use una contraseña igual o similar a una que use en otros sitios web

- No use solo una palabra, por ejemplo, **contraseña**, ni una frase que use habitualmente, como **ILOVEYOU.**

- Haga que las contraseñas sean difíciles de adivinar, incluso las personas que sepan mucho sobre usted, como el nombre y el cumpleaños de sus amigos y familiares, sus bandas favoritas y las frases que quiera usar.

## <a name="some-common-approaches-and-their-negative-impacts"></a>Algunos métodos comunes y sus repercusiones negativas

Éstas son algunas de las prácticas de administración de contraseñas más usadas, pero la búsqueda nos avisa sobre las consecuencias negativas que tienen.
  
### <a name="password-expiration-requirements-for-users"></a>Requisitos de expiración de contraseña para usuarios

Los requisitos de expiración de contraseñas son más dañinos que los que hacen que los usuarios seleccionen contraseñas predecibles, formadas por palabras secuenciales y números estrechamente relacionados entre sí. En estos casos, la contraseña siguiente puede predecirse en función de la contraseña anterior. Los requisitos de expiración de contraseñas no proporcionan ventajas de contención ya que los ciberdelincuentes casi siempre usan credenciales tan pronto como los comprometen. Consulte [Momento para reconsiderar los cambios en la contraseña obligatoria](https://go.microsoft.com/fwlink/p/?linkid=861018) para más información.
  
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

El requisito de contraseña más importante que debe aplicar a los usuarios al crear contraseñas es vetar el uso de contraseñas comunes para reducir la susceptibilidad de la organización a ataques violentos de contraseñas. Las contraseñas de usuario comunes incluyen: **abcdefg**, **contraseña**, **mono**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Instruya a los usuarios para no volver a usar contraseñas de la organización en otro lugar

Uno de los mensajes más importantes para tener acceso a los usuarios de su organización es no volver a usar la contraseña de su organización en ningún otro lugar. El uso de las contraseñas de organización en sitios web externos aumenta considerablemente la probabilidad de que los ciberdelincuentes puedan comprometer estas contraseñas.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Exigir registro de Multi-Factor Authentication

Asegúrese de que los usuarios actualizan la información de contacto y seguridad, como una dirección de correo electrónico alternativa, un número de teléfono o un dispositivo registrado para las notificaciones de inserción, de modo que pueden responder a los desafíos de seguridad y recibir notificaciones de eventos de seguridad. La información actualizada de contacto y seguridad ayuda a los usuarios a verificar su identidad si alguna vez olvidan su contraseña o si alguien más intenta hacerse cargo de su cuenta. También proporciona un canal de notificación fuera de banda en caso de eventos de seguridad como intentos de inicio de sesión o cambio de contraseñas. 
  
Para obtener más información, consulte [configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Habilitar la autenticación multifactor basada en riesgos

La autenticación multifactor basada en riesgos garantiza que, cuando nuestro sistema detecta actividad sospechosa, puede poner a prueba al usuario para asegurarse de que es el propietario legítimo de la cuenta. 
  
## <a name="next-steps"></a>Siguientes pasos

¿Quiere obtener más información acerca de la administración de contraseñas? Estas son algunas lecturas recomendadas:

- [Olvide las contraseñas, elija una opción sin contraseñas](https://www.microsoft.com/security/business/identity-access-management/passwordless-authentication)

- [Directrices de contraseñas de Microsoft](https://www.microsoft.com/research/wp-content/uploads/2016/06/Microsoft_Password_Guidance-1.pdf)

- [¿Las contraseñas de web seguras realizan alguna acción?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Carteras de contraseñas y el usuario de esfuerzo finito](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Prevenir contraseñas vulnerables leyendo las mentes de los usuarios](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Elegir contraseñas seguras](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Tiempo para reconsiderar los cambios en la contraseña obligatoria](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [Las peores contraseñas de 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a>Contenido relacionado

[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)\
[Establecer la contraseña de un usuario individual para que nunca expire](../add-users/set-password-to-never-expire.md) (artículo)\
[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)\
[Volver a enviar la contraseña de un usuario: ayuda para administradores](../add-users/resend-user-password.md) (artículo)
