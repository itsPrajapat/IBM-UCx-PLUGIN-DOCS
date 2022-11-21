
# CircleCI - Usage

## Usage

To use the CircleCI plug-in, the plug-in must be loaded and an instance created before you can configure the plug-in integration. Configuration properties are defined using the product user interface or a JSON file.

### Integration type

The CircleCI plug-in supports scheduled events integration which are listed in the following table.

| Name | Description |
| --- | --- |
| SyncCCPipeline | Synchronize CircleCI pipeline data. |

### Integration

here are two methods to integrate the plug-in:

* Using the user interface
* Using a JSON file

The tables in the Configuration properties topic describe the properties used to define the integration.

#### Using the user interface

1. From the Plugins page, click **Settings** > **Integrations** > **Plugins**.
2. Under the **Action** column for the plug-in, click **Add Integration**.
3. On the Add Integration page enter values for the fields used to configure the integration and define communication.
4. Click **Save**.

#### Using a JSON file

The JSON file contains the information for creating a value stream. Within the JSON file is a section for integrations. It is in this section that plug-in properties can be defined.

1. From a value stream page, download the value stream map. The value stream map is a JSON file used to define integrations.
2. Edit the JSON file to include the plug-in configuration properties.
3. Save and upload the JSON file. This replaces the current JSON file with the new content.
4. View the new integration on the Integrations page.

### Configuration properties

The following tables describe the properties used to configure the integration. Each table contains the field name when using the user interface and the property name when using a JSON file.

* The General Configuration Properties table describes configuration properties used by all plug-in integrations.
* The CircleCI Configuration Properties table describes the configuration properties used to communicate with IBM UrbanCode Velocity.

#### General Configuration Properties table

| Name | Description | Required | Property Name |
| --- | --- | ---| --- |
| NA | The version of the plug-in that you want to use. To view available versions, click the **Version History** tab. If a value is not specified, the latest version is used. | No | image |
| Integration Name | An assigned name to the value stream. | Yes | name |
| Logging Level | The level of Log4j messages to display in the log file. Valid values are: all, debug, info, warn, error, fatal, off, and trace. | No | loggingLevel |
| NA | List of configuration properties used to connect and communicate with the GitHub server. Enclose the properties within braces. | Yes | properties |
|  | The name of the tenant. | Yes | tenant_id |
| NA | Unique identifier assigned to the plug-in. The value for the GitHub plug-in is `ucv-ext-circleci` | Yes | type |

#### CircleCI Configuration Properties table

| Name | Type | Description | Required | Project Name |
| --- | --- | --- | --- | --- |
| Access Token | String | The access token to authenticate with CircleCI. | Yes | accessToken |
| Branch | String | GitHub repositories branch, The branch to pull commits from. | No | branch |
| Organization Name | String | The username or organization name in the version control system.| Yes | orgName |
| Project type (VCS provider) | String | The Version Control System that is used, eg: github, bitbucket. | Yes | projectType |
| Proxy Password | String | The password used to authenticate with the proxy server. | No | proxyPassword |
| Proxy Server | String | The URL of the proxy server including the port number. | No | proxyServer |
| Proxy User Name | String | The user name used to authenticate with the proxy server. | No | proxyUsername |
| Repositories | Array | A comma seperated list of repositories from which to import pull requests, commits, and build data. | Yes | repositories |
| URL| String | API URL of CircleCI. | Yes | apiUrl |
| User Access Key | String | The user access key to authenticate with the IBM UrbanCode Velocity server.| Yes | velocityAccessKey |




#### JSON code example

The following example can be used as a template to define the integration within the JSON file for a value stream. Copy and paste the template into the JSON file and make the appropriate changes.

```json

"integrations": [
    {
      "type": "ucv-ext-circleci",
      "tenant_id": "tenantid",
      "name": "CircleCI_Plugin ",
      "properties": {
        "apiUrl": "circleci_server_url",
        "velocityAccessKey": "velocity_access_key",
        "accessToken": "circleci_access_token",
        "projectType": "circleci_projct_type",
        "orgName": "circleci_org_name",
        "repositories": [
          "CiecleCI-Project"
        ],
        "proxyServer": "proxy_server_url",
        "proxyUsername": "proxy_server_user_name",
        "proxyPassword": "proxy_server_password"
      }
    }  ]

```

|Back to ...||Latest Version|CircleCI |||
| :---: | :---: | :---: | :---: | :---: | :---: |
|[All Plugins](../../index.md)|[Velocity Plugins](../README.md)|[1.0.22](https://raw.githubusercontent.com/UrbanCode/IBM-UCV-PLUGINS/main/files/ucv-ext-circleci/ucv-ext-circleci-1.0.22.tar.7z.001)|[Readme](README.md)|[Overview](overview.md)|[Usage](usage.md)|