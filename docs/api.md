# API

## Описание <a href="#intro" id="intro"></a>

Marzban предоставляет REST API, который позволяет разработчикам программно взаимодействовать со службами Marzban. Чтобы просмотреть документацию по API в Swagger UI или ReDoc, установите переменную конфигурации `DOCS=True`и перейдите к `/docs`и `/redoc`.

{% swagger src="../.gitbook/assets/openapi.json" path="/api/admin/token" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/admin" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/admin" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/admin/{username}" method="put" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/admin/{username}" method="delete" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/admins" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/sub/{token}/" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/sub/{token}/info" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/sub/{token}/{client_type}" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/system" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/inbounds" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/hosts" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/hosts" method="put" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/core" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/core/restart" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/core/config" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/core/config" method="put" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user/{username}" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user/{username}" method="put" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user/{username}" method="delete" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user/{username}/reset" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user/{username}/revoke_sub" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/users" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/users/reset" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user/{username}/usage" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user_template" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user_template" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user_template/{id}" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user_template/{id}" method="put" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/user_template/{id}" method="delete" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/node" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/node/{node_id}" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/node/{node_id}" method="put" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/node/{node_id}" method="delete" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/nodes" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/node/{node_id}/reconnect" method="post" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/api/nodes/usage" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/openapi.json" path="/" method="get" %}
[openapi.json](../.gitbook/assets/openapi.json)
{% endswagger %}
