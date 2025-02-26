# {{ ES }} settings

For {{ mes-name }} clusters, you can configure settings that relate to {{ ES }}.

The label next to the setting name helps determine which interface is used to set the value of this setting: the management console, CLI, API, or Terraform. The {{ tag-all }} label indicates that all of the above interfaces are supported.

Depending on the selected interface, the same setting is represented in a different way, for example:

* **Fielddata cache size** in the management console corresponds to:

   * `fielddata_cache_size` in the gRPC API, CLI, Terraform.
   * `fielddataCacheSize` in the REST API.

## Cluster-level settings

You can use the following settings:

* **Fielddata cache size**{#setting-fielddata-cache-size} {{ tag-all }}

   Maximum cache size allocated to field data. Specified as a string containing a relative (`20%`) or absolute (`12GB`) value. The maximum value is equal to `40%` of the JVM heap. Not specified by default. The amount of cache allocated to field data is not limited.

   For more information, see the [{{ ES }} documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-fielddata.html).

* **Reindex remote whitelist**{#setting-reindex-remote-whitelist} {{ tag-api }}

   A comma-separated list of host IPs and FQDNs as well as host ports that may be used as a remote source for the [Reindex API]({{ links.es.reindex-api }}).

   You can use the `*` wildcard character to specify an IP or port range, such as:

   ```text
   hostname:9200, 192.168.0.*:9200, localhost:*
   ```

   For more information, see the [{{ ES }} documentation]({{ links.es.reindex-api }}#reindex-from-remote).

* **Reindex SSL CA path**{#setting-reindex-ssl-ca-path} {{ tag-api }}

   The local path to the certificate file for the cluster to use to encrypt the connection to the remote source for the [Reindex API]({{ links.es.reindex-api }}).

   [Add the certificate file as an extension](../operations/cluster-extensions.md#add) to the cluster and specify the path as:

   ```text
   /etc/elasticsearch/extensions/<extension name>/<certificate name>
   ```

   For more information, see the [{{ ES }} documentation]({{ links.es.reindex-api }}#reindex-ssl).
