#### {{ roles-vpc-public-admin }} {#vpc-public-admin}

Роль `{{ roles-vpc-public-admin }}` позволяет создавать и удалять [статические публичные IP-адреса](../vpc/concepts/address.md). Также она включает все разрешения роли `{{ roles-vpc-viewer }}`.

Наличие роли `{{ roles-vpc-public-admin }}` также необходимо для создания ресурсов с публичными IP-адресами, например: виртуальных машин или кластеров управляемых баз данных.

{% include [roles-restriction-only-parents](iam/roles-restriction-only-parents.md) %}

Важно: если сеть и подсеть находятся в разных каталогах, то наличие роли `{{ roles-vpc-public-admin }}` проверяется на том каталоге, в котором находится _сеть_.
