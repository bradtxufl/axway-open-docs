{
"title": "Manage externalized files",
"linkTitle": "Manage externalized files",
"weight":"60",
"date": "2020-09-24",
"description": "Learn how to work with externalized files within YAML configuration."
}

{{% alert title="Note" %}}This topic is not related to [Environmentalization](/docs/apim_yamles/yamles_environmentalization).{{% /alert %}}

Some entities have fields that contain the content of a file, for example, a script or a certificate. In the XML federated configuration, these files are embedded within the XML, which makes them hard to edit. In a YAML configuration, the content of these files is stored in separate external files, which provides the following advantages:

* They can be easily read without unnecessary encoding.
* You can create and edit these files using a text editor (IDE) of your choice.
* Files and directory can have long names by default, but you can rename your external file as you wish.

For example, the following YAML file contains a field `Set Backend message`, which content is stored in a JSON file:

```yaml
---
type: FilterCircuit
fields:
  name: Get organizationId
children:
- type: ChangeMessageFilter
  fields:
    name: Set Backend message
    outputContentType: application/json
    body#ref: Get organizationId - Set Backend message.json # the message has been externalized
                                                            # field "body" has been renamed in "body#ref"
```

Content of `Get organizationId - Set Backend message.json`:

```json
{
  "name": "${targetName}",
  "serviceType": "rest",
  "description": "Streamed backend",
  "version": "1.0",
  "basePath": "https://${StreamsSSEVHOST}",
  "resourcePath": "/subscribers",
  "models": {},
  "consumes": [],
  "produces": [],
  "organizationId": "${backend.organizationId}"
}
```

The location of an externalized file is always relative to the directory of the YAML file referencing it. In the above example, both files are in the same directory.

## Externalized files default naming scheme

During conversion from FED, externalized file names are generated as in the following table, and you cannot use this convention afterwards.

| Entity | EntityType | Field | Externalized file name scheme | Possible extensions | Additional rules | Environmentalization possible inside file content |
| --- | --- | --- | --- | --- | --- | --- |
| Script language / Scripts (in Resources) | `JavaScriptFilter`, `Script` | `script#ref` | `<Parent entity>-Files/<entity field "name">` | `.groovy`, `.js`, `.nashorn.js`, `.py` |  | Yes |
| Set Message (Policy Filter) | `FilterCircuit` | `body#ref` | `<Parent entity>-Files/<entity field "name">` | `.json`, `.html`, `.xml`, `.txt` | Only multi-line body is externalize. Extension depends on content type content. | Yes |
| Attribute Extract Database  (Policy Filter) | `FilterCircuit` | `sqlStatement#ref` | `<Parent entity>-Files/<entity field "name">` | `.sql` | Only multi-line body is externalize | Yes |
| JSON Schema | `JSONSchema` | `contents#ref` | `<entity field "name">` | `.json` |  | Yes |
| Certificate | `Certificate` | `content#ref` | `<entity field "dname">-cert` | `.pem` | [How to add a new certificate](/docs/apim_yamles/yamles_edit/#how-to-add-a-new-certificate-and-private-key-to-a-yaml-configuration) | No |
|             |               | `key#refbinay` | `<entity field "dname">-key` | `.pem` | [How to add a private key](/docs/apim_yamles/yamles_edit/#how-to-add-a-new-certificate-and-private-key-to-a-yaml-configuration) | No |
| XML Schema Document Bundles / WSDL Document Bundles | `ResourceBlob` | `content#binary` | `<entity fields "ID">` (generated by Policy Studio but can be manually set) | `.xsd`, `.dtd`, `.wsdl` | Extension depends on content on type | No |
| Alert type > OPSEC   | `OpsecAlertSystem` | `connectionInfo#ref` | `<entity fields "name">` | `.conf` | Entity name is the file name. | No |
| Alert type > OPSEC  > Files to upload | `UpLoadFile` | `contents#refbinary` | `upload-files/<entity fields "name">` | n/a | Entity name is the file name. | No |
| Security Loadable Module | `OESSecurityRuntimeLoadableModule` | `nameAuthorityDefinition#ref` | `<entity fields "name">` | `.xml` | Entity name is the file name. | No |
| PGP Key Pair | `PGPKeyPair` | `publicKey#refbinary`  | `<entity field "alias">-pub` | `.crt` |  | No |
|              |            | `privateKey#refbinary` | `<entity field "alias">-sec` | `.asc` |  | No |
| Key Pair | `KeyPair` | `publicKey#refbinary`  | `<entity field "alias">` | `.pub` |  | No |
|          |         | `privateKey#refbinary` | `<entity field "alias">` | `.pem` |  | No |
| Authentication Repository Group → Authentication Repository Database → Query   | `Query` | `sqlStatement#ref`  | `<Grand Parent entity field "name">/<Parent entity field "name"> - <entity field "name">` | `.sql` |  | No |
| Tivoli Connection | `TivoliSettings` | `configFile#ref`         | `<entity field "name">` | `.conf` | Tivoli configuration File                        | No |
|                   |                | `configDatabaseFile#refbinary` | `<entity field "name">` | `.db.conf`   | Tivoli Configuration Database File. | No |
|                   |                | `sslStashFile#refbinary`       | `<entity field "name">` | `.ssl.key`   | SSL Stash file                      | No |
|                   |                | `sslKeyFile#refbinary`         | `<entity field "name">` | `.ssl.stash` | SSL Key file                        | No |

* The entities are named as in Policy Studio.
* `#ref` and `#refbinary` naming convention might evolve in the future.
