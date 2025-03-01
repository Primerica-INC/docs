---
title: Solución de problemas
intro: Aprende cómo resolver los problemas más comunes que las personas pueden encontrar en la API de REST.
redirect_from:
  - /v3/troubleshooting
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - API
---



Si estás encontrando algunas situaciones extrañas en la API, aquí hay una lista de posibles soluciones a algunos de estos problemas que podrías estar experimentando.

## Error `404` para un repositorio existente

Habitualmente, enviamos un error `404` cuando tu cliente no está autenticado adecuadamente. Puede que esperes ver un `403 Forbidden` en estos casos. Sin embargo, ya que no queremos proporcionar _ningun_ tipo de información acerca de los repositorios privados, en vez de esto, la API devuelve un `404`.

Para solucionar problemas, asegúrate de que [te estás autenticando correctamente](/guides/getting-started/), que [tu token de acceso OAuth tenga los alcances requeridos](/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/), que las [restricciones de aplicaciones de terceros][oap-guide] no estén bloqueando el acceso y que [el token no haya vencido ni se haya revocado](/github/authenticating-to-github/keeping-your-account-and-data-secure/token-expiration-and-revocation).

## No se devolvieron todos los resultados

La mayoría de las llamadas a la API que acceden a una lista de recursos (_por ejemplo_, usuarios, informes de problemas, _etc._) son compatibles con la paginación. Si estás haciendo solicitudes y recibes un conjunto de resultados incompleto, probablemente solo estás viendo la primera página. Necesitarás solicitar las páginas restantes para obtener más resultados.

Es importante que *no* intentes adivinar el formato de la URL de paginación. No todas las llamadas a la API utilizan la misma estructura. En vez de esto, extrae la información de paginación del [Encabezado de Enlace](/rest#pagination), el cual se envía en cada solicitud.

{% ifversion fpt or ghec %}
## Errores de autenticación básicos

Desde el 13 de noviembre de 2020, la autenticación con nombre de usuario y contraseña a la API de REST y a la API de Autorizaciones de OAuth se obsoletizaron y ya no funcionan.

### Utilizar `username`/`password` para la autenticación básica

Si estás utilizando `username` y `password` para las llamadas a la API, éstas credenciales ya no funcionarán para que te autentiques. Por ejemplo:

```bash
curl -u my_user:my_password https://api.github.com/user/repos
```

En vez de esto, utiliza un [token de acceso personal](/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) cuando pruebes las terminales o cuando realices desarrollos locales:

```bash
curl -H 'Authorization: Bearer my_access_token' https://api.github.com/user/repos
```

Para las Apps de Oauth, debes utilizar el [flujo de aplicaciones web](/apps/building-oauth-apps/authorizing-oauth-apps/#web-application-flow) para generar un token de OAuth para utilizar el encabezado de la llamada a la API:

```bash
curl -H 'Authorization: Bearer my-oauth-token' https://api.github.com/user/repos
```

## Exceder el tiempo de espera

Si a {% data variables.product.product_name %} le toma más de 10 segundos procesar una solicitud de la API, {% data variables.product.product_name %} terminará la solicitud y recibirás una respuesta de tiempo de espera excedido.

{% endif %}

[oap-guide]: https://developer.github.com/changes/2015-01-19-an-integrators-guide-to-organization-application-policies/
