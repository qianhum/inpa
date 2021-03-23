# Is New Package Available REST API Spec

## Package type

### List all package types

```sh
GET /package_types
```

Code samples

Shell

```sh
curl https://is.package.updated/package_types
```

Default response

```sh
Status: 200 OK
```

```json
{
  "packageTypes": [
    {
      "packageTypeName": "npm",
      "registry": "https://registry.npmjs.org"
    }
  ]
}
```

### Get a package type

```sh
GET /package_type/{packageTypeName}
```

Parameters

Name | Type | In
--- | --- | ---
packageTypeName | string | path

Code samples

Shell

```sh
curl https://is.package.updated/package_type/npm
```

Default response

```sh
Status: 200 OK
```

```json
{
  "packageType": {
    "packageTypeName": "npm",
    "registry": "https://registry.npmjs.org"
  }
}
```

### Update a package type

```sh
GET /package_type/{packageTypeName}
```

Parameters

Name | Type | In
--- | --- | ---
packageTypeName | string | path
registry | string | body

Code samples

Shell

```sh
curl -X PATCH -d "registry=https://registry.npmjs.org" https://is.package.updated/package_type/npm
```

Default response

```sh
Status: 200 OK
```

```json
{ "message": "packageType successfully added" }
```

## Package

### List all packages

```sh
GET /packages
```

Code samples

Shell

```sh
curl https://is.package.updated/packages
```

Default response

```sh
Status: 200 OK
```

```json
{
  "packages": [
    {
      "packageName": "react",
      "packageTypeName": "npm",
      "latestVersion": "17.0.0-rc.1",
      "latestModifyTime": 1598614500000,
      "latestCheckTime": 1599568080084
    },
    {
      "packageName": "vue",
      "packageTypeName": "npm",
      "latestVersion": "3.0.0-rc.10",
      "latestModifyTime": 1599064985000,
      "latestCheckTime": 1599568085102
    }
  ]
}
```

### Get a package

```sh
GET /package/{packageTypeName}/{packageName}
```

Parameters

Name | Type | In
--- | --- | ---
packageName | string | path
packageTypeName | string | path

Code samples

Shell

```sh
curl https://is.package.updated/package/npm/react
```

Default response

```sh
Status: 200 OK
```

```json
{
  "package": {
    "packageName": "react",
    "packageTypeName": "npm",
    "latestVersion": "17.0.0-rc.1",
    "latestModifyTime": 1598614500000,
    "latestCheckTime": 1599568260157
  }
}
```

### Add a packages

```sh
POST /package/{packageTypeName}/{packageName}
```

Parameters

Name | Type | In
--- | --- | ---
packageName | string | path
packageTypeName | string | path

Code samples

Shell

```sh
curl -X POST https://is.package.updated/package/npm/react
```

Default response

```sh
Status: 201 Created
```

```json
{ "message": "package successfully added" }
```

### Remove a package

```sh
DELETE /package/{packageTypeName}/{packageName}
```

Parameters

Name | Type | In
--- | --- | ---
packageName | string | path
packageTypeName | string | path

Code samples

Shell

```sh
curl -X DELETE https://is.package.updated/package/npm/react
```

Default response

```sh
Status: 204 No Content
```

## Package version

### List package versions

Sort by publishTime in descending order and return the first 50 rows

```sh
GET /package_versions
```

Code samples

Shell

```sh
curl https://is.package.updated/package_versions
```

Default response

```sh
Status: 200 OK
```

```json
{
  "packageVersions": [
    {
      "packageName": "vue",
      "packageTypeName": "npm",
      "version": "3.0.0-rc.10",
      "publishTime": 1599064964965
    },
    {
      "packageName": "react",
      "packageTypeName": "npm",
      "version": "17.0.0-rc.1",
      "publishTime": 1598614483243
    },
    {
      "packageName": "react",
      "packageTypeName": "npm",
      "version": "0.0.0-4e6999103",
      "publishTime": 1598575537342
    },
    {
      "packageName": "vue",
      "packageTypeName": "npm",
      "version": "3.0.0-rc.9",
      "publishTime": 1598480524113
    }
  ]
}
```

### List package versions for a package

```sh
GET /package_versions/{packageTypeName}/{packageName}
```

Parameters

Name | Type | In
--- | --- | ---
packageName | string | path
packageTypeName | string | path

Code samples

Shell

```sh
curl https://is.package.updated/package_versions/npm/react
```

Default response

```sh
Status: 200 OK
```

```json
{
  "packageName": "react",
  "packageTypeName": "npm",
  "versions": [
    {
      "version": "17.0.0-rc.1",
      "publishTime": 1598614483243
    },
    {
      "version": "0.0.0-4e6999103",
      "publishTime": 1598575537342
    },
    {
      "version": "17.0.0-rc.0",
      "publishTime": 1597089567120
    }
  ]
}
```
