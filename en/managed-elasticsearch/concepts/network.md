# Network in {{ mes-name }}


When creating a cluster, you can:

- Set the network for the cluster itself.
- Set the subnets for each host in the cluster.
- Request a public IP address to access cluster hosts with the [_Data node_ role](./index.md) from outside {{ yandex-cloud }}.

You can create a cluster without specifying any subnets for the hosts, if the availability zone selected for each host contains exactly one subnet of the cluster network.

## Hostname and FQDN {#hostname}

{{ mes-short-name }} generates a name for each cluster host during creation. This name will be the host's fully qualified domain name (FQDN). The hostname and, consequently, the FQDN cannot be changed.


You can use the FQDN to access the host within a single cloud network. Read more in the [{{ vpc-full-name }} documentation](../../vpc/).

## Public access to a host {#public-access-to-a-host}

Any cluster host can be accessible from outside {{ yandex-cloud }} if you requested public access when creating the host. To connect to this kind of host, use its FQDN.

It is not possible to request a public address after creating a host, but you can replace one of the existing hosts with a new host that has a public address.

When deleting a host with a public FQDN, the assigned IP address is revoked.

## Security groups {#security-groups}

Security groups follow the principle "All traffic that is not allowed is prohibited". Therefore, security group rules for a cluster's cloud network might prevent connections to the cluster if one or more groups are assigned to it.

Say, for example, that a host with the _Data node_ role is assigned a public IP address. If there's no security group rule that allows connecting to it from the internet on port `443`, you won't be able to connect to the Kibana web interface. You also won't be able to access a host that has no security group rule that explicitly allows incoming traffic on port `9200`.

{% note tip %}

If you connect to a cluster from within its cloud network, [configure](../operations/cluster-connect.md#configuring-security-groups) security groups both for the cluster and the connecting host.

{% endnote %}

{% include [sg-rules-concept](../../_includes/mdb/sg-rules-concept.md) %}
